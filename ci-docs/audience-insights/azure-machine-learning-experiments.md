---
title: Experimentos de Azure Machine Learning
description: Use modelos baseados en Azure Machine Learning en Dynamics 365 Customer Insights.
ms.date: 11/30/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: naravill
ms.author: naravill
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 3f97e22687ae4f5536d492bac83bdf9c711e2c94
ms.sourcegitcommit: dab2cbf818fafc9436e685376df94c5e44e4b144
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 07/13/2021
ms.locfileid: "6554433"
---
# <a name="use-azure-machine-learning-based-models"></a>Usar modelos baseados en Azure Machine Learning

Os datos unificados en Dynamics 365 Customer Insights son unha fonte para construír modelos de aprendizaxe automática que poden xerar información comercial adicional. Customer Insights intégrase con Machine Learning Studio (clásico) e Azure Machine Learning para usar os seus propios modelos personalizados. Consulte os [Experimentos de Machine Learning Studio (clásico)](machine-learning-studio-experiments.md) para ver exemplos de experimentos construídos en Machine Learning Studio (clásico). 

## <a name="prerequisites"></a>Requisitos previos

- Acceder a Customer Insights
- Activar unha subscrición de Azure Enterprise
- [Perfís de cliente unificados](data-unification.md)
- [Exportación de entidades a Azure Blob Storage](export-azure-blob-storage.md) configurada

## <a name="set-up-azure-machine-learning-workspace"></a>Configurar a área de traballo de Azure Machine Learning

1. Vexa [crear un espazo de traballo de Azure Machine Learning](/azure/machine-learning/concept-workspace#-create-a-workspace) para coñecer diferentes opcións para crear o espazo de traballo. Para obter o mellor rendemento, cree o espazo de traballo nunha rexión de Azure xeograficamente máis próxima ao seu entorno de Customer Insights.

1. Acceda ao seu espazo de traballo a través de [Azure Machine Learning Studio](https://ml.azure.com/). Hai varias [formas de interactuar](/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) co seu espazo de traballo.

## <a name="work-with-azure-machine-learning-designer"></a>Traballar co deseñador de Azure Machine Learning

O deseñador de Azure Machine Learning ofrece un lenzo visual onde pode arrastrar e soltar conxuntos de datos e módulos, semellante a Machine Learning Studio (clásico). Unha canle por lotes creada a partir do deseñador pódese integrar en Customer Insights se se configura de acordo. 
   
## <a name="working-with-azure-machine-learning-sdk"></a>Traballar co SDK de Azure Machine Learning

Os científicos de datos e os desenvolvedores de IA usan o [SDK de Azure Machine Learning](/python/api/overview/azure/ml/?preserve-view=true&view=azure-ml-py) para crear fluxos de traballo de aprendizaxe automática. Actualmente, os modelos adestrados usando o SDK non se poden integrar directamente con Customer Insights. Para integrarse con Customer Insights é necesaria unha canle de inferencia por lotes que consuma ese modelo.

## <a name="batch-pipeline-requirements-to-integrate-with-customer-insights"></a>Requisitos da canle por lotes para integrarse con Customer Insights

### <a name="dataset-configuration"></a>Configuración do conxunto de datos

Debe crear conxuntos de datos para usar os datos da entidade de Customer Insights na súa canle de inferencia por lotes. Estes conxuntos de datos deben rexistrarse no espazo de traballo. Actualmente, só admitimos [conxuntos de datos tabulares](/azure/machine-learning/how-to-create-register-datasets#tabulardataset) en formato .csv. Os conxuntos de datos que corresponden aos datos da entidade deben ser parametrizados como parámetro de canle.
   
* Parámetros do conxunto de datos no deseñador
   
     No deseñador, abra **Seleccionar columnas no conxunto de datos** e seleccione **Establecer como parámetro de canle** onde vostede fornece un nome para o parámetro.

     > [!div class="mx-imgBorder"]
     > ![Parametrización do conxunto de datos no deseñador.](media/intelligence-designer-dataset-parameters.png "Parametrización do conxunto de datos no deseñador")
   
* Parámetro do conxunto de datos no SDK (Python)
   
   ```python
   HotelStayActivity_dataset = Dataset.get_by_name(ws, name='Hotel Stay Activity Data')
   HotelStayActivity_pipeline_param = PipelineParameter(name="HotelStayActivity_pipeline_param", default_value=HotelStayActivity_dataset)
   HotelStayActivity_ds_consumption = DatasetConsumptionConfig("HotelStayActivity_dataset", HotelStayActivity_pipeline_param)
   ```

### <a name="batch-inference-pipeline"></a>Canle de inferencia por lotes
  
* No deseñador pódese usar unha canle de adestramento para crear ou actualizar unha canle de inferencia. Actualmente só se admiten canles de inferencia por lotes.

* Usando o SDK, pode publicar a canle nun punto extremo. Actualmente, Customer Insights intégrase coa canle predeterminada nun extremo de canle por lotes no espazo de traballo de aprendizaxe automática.
   
   ```python
   published_pipeline = pipeline.publish(name="ChurnInferencePipeline", description="Published Churn Inference pipeline")
   pipeline_endpoint = PipelineEndpoint.get(workspace=ws, name="ChurnPipelineEndpoint") 
   pipeline_endpoint.add_default(pipeline=published_pipeline)
   ```

### <a name="import-pipeline-data-into-customer-insights"></a>Importar datos da canle a Customer Insights

* O deseñador proporciona o [módulo Exportar datos](/azure/machine-learning/algorithm-module-reference/export-data) que permite exportar a saída dunha canle ao almacenamento de Azure. Actualmente, o módulo debe usar o tipo de almacén de datos **Azure Blob Storage** e parametrizar o **Almacén de datos** e o **Camiño** relativo. Customer Insights anula estes dous parámetros durante a execución da canle cun almacén de datos e unha ruta que é accesible ao produto.
   > [!div class="mx-imgBorder"]
   > ![Exportar configuración do módulo de datos.](media/intelligence-designer-importdata.png "Exportar configuración do módulo de datos")
   
* Ao escribir a saída de inferencia usando código, pode cargar a saída no camiño a dentro dun *almacén de datos rexistrado* no espazo de traballo. Se a ruta e o almacén de datos están parametrizados na canle, Customer Insights poderá ler e importar a saída de inferencia. Actualmente, admítese unha única saída tabular en formato CSV. A ruta debe incluír o directorio e o nome do ficheiro.

   ```python
   # In Pipeline setup script
      OutputPathParameter = PipelineParameter(name="output_path", default_value="HotelChurnOutput/HotelChurnOutput.csv")
      OutputDatastoreParameter = PipelineParameter(name="output_datastore", default_value="workspaceblobstore")
   ...
   # In pipeline execution script
      run = Run.get_context()
      ws = run.experiment.workspace
      datastore = Datastore.get(ws, output_datastore) # output_datastore is parameterized
      directory_name =  os.path.dirname(output_path)  # output_path is parameterized.
      
      # Datastore.upload() or Dataset.File.upload_directory() are supported methods to uplaod the data
      # datastore.upload(src_dir=<<working directory>>, target_path=directory_name, overwrite=False, show_progress=True)
      output_dataset = Dataset.File.upload_directory(src_dir=<<working directory>>, target = (datastore, directory_name)) # Remove trailing "/" from directory_name
   ```


[!INCLUDE[footer-include](../includes/footer-banner.md)]