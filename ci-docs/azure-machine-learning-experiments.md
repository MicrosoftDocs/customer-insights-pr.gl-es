---
title: Usar modelos baseados en Azure Machine Learning
description: Use modelos baseados en Azure Machine Learning en Dynamics 365 Customer Insights.
ms.date: 09/22/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: naravill
ms.author: naravill
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 8d9c9324ea4840b585b9af1a58d505ccaea6f18e
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609823"
---
# <a name="use-azure-machine-learning-based-models"></a>Usar modelos baseados en Azure Machine Learning

Os datos unificados en Dynamics 365 Customer Insights son unha fonte para construír modelos de aprendizaxe automática que poden xerar información comercial adicional. Customer Insights intégrase coa Aprendizaxe automática de Azure para usar os seus propios modelos personalizados.

## <a name="prerequisites"></a>Requisitos previos

- Acceder a Customer Insights
- Activar unha subscrición de Azure Enterprise
- [Perfís de cliente unificados](data-unification.md)
- [Exportación de entidades a Azure Blob Storage](export-azure-blob-storage.md) configurada

## <a name="set-up-azure-machine-learning-workspace"></a>Configurar a área de traballo de Azure Machine Learning

1. Vexa [crear un espazo de traballo de Azure Machine Learning](/azure/machine-learning/concept-workspace#-create-a-workspace) para coñecer diferentes opcións para crear o espazo de traballo. Para obter o mellor rendemento, cree o espazo de traballo nunha rexión de Azure xeograficamente máis próxima ao seu entorno de Customer Insights.

1. Acceda ao seu espazo de traballo a través de [Azure Machine Learning Studio](https://ml.azure.com/). Hai varias [formas de interactuar](/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) co seu espazo de traballo.

## <a name="work-with-azure-machine-learning-designer"></a>Traballar co deseñador de Azure Machine Learning

O deseñador de Azure Aprendizaxe automático ofrece un lenzo visual onde podes arrastrar e soltar conxuntos de datos e módulos. Unha canle por lotes creada a partir do deseñador pódese integrar en Customer Insights se se configura de acordo. 

## <a name="working-with-azure-machine-learning-sdk"></a>Traballar co SDK de Azure Machine Learning

Os científicos de datos e os desenvolvedores de IA usan o [SDK de Azure Machine Learning](/python/api/overview/azure/ml/?preserve-view=true&view=azure-ml-py) para crear fluxos de traballo de aprendizaxe automática. Actualmente, os modelos adestrados usando o SDK non se poden integrar directamente con Customer Insights. Para integrarse con Customer Insights é necesaria unha canle de inferencia por lotes que consuma ese modelo.

## <a name="batch-pipeline-requirements-to-integrate-with-customer-insights"></a>Requisitos da canle por lotes para integrarse con Customer Insights

### <a name="dataset-configuration"></a>Configuración do conxunto de datos

Cree conxuntos de datos para usar os datos de entidades de Customer Insights para a súa canalización de inferencias por lotes. Rexistra estes conxuntos de datos no espazo de traballo. Actualmente, só admitimos [conxuntos de datos tabulares](/azure/machine-learning/how-to-create-register-datasets#tabulardataset) en formato .csv. Parametriza os conxuntos de datos que corresponden aos datos da entidade como parámetro de canalización.

- Parámetros do conxunto de datos no deseñador

  No deseñador, abra **Seleccionar columnas no conxunto de datos** e seleccione **Establecer como parámetro de canle** onde vostede fornece un nome para o parámetro.

  :::image type="content" source="media/intelligence-designer-dataset-parameters.png" alt-text="Parametrización do conxunto de datos no deseñador.":::

- Parámetro do conxunto de datos no SDK (Python)

   ```python
   HotelStayActivity_dataset = Dataset.get_by_name(ws, name='Hotel Stay Activity Data')
   HotelStayActivity_pipeline_param = PipelineParameter(name="HotelStayActivity_pipeline_param", default_value=HotelStayActivity_dataset)
   HotelStayActivity_ds_consumption = DatasetConsumptionConfig("HotelStayActivity_dataset", HotelStayActivity_pipeline_param)
   ```

### <a name="batch-inference-pipeline"></a>Canle de inferencia por lotes
  
- No deseñador, use unha canalización de adestramento para crear ou actualizar unha canalización de inferencia. Actualmente só se admiten canles de inferencia por lotes.

- Usando o SDK, publica a canalización nun punto final. Actualmente, Customer Insights intégrase coa canle predeterminada nun extremo de canle por lotes no espazo de traballo de aprendizaxe automática.

   ```python
   published_pipeline = pipeline.publish(name="ChurnInferencePipeline", description="Published Churn Inference pipeline")
   pipeline_endpoint = PipelineEndpoint.get(workspace=ws, name="ChurnPipelineEndpoint") 
   pipeline_endpoint.add_default(pipeline=published_pipeline)
   ```

### <a name="import-pipeline-data-into-customer-insights"></a>Importar datos da canle a Customer Insights

- O deseñador proporciona o [módulo Exportar datos](/azure/machine-learning/algorithm-module-reference/export-data) que permite exportar a saída dunha canle ao almacenamento de Azure. Actualmente, o módulo debe usar o tipo de almacén de datos **Azure Blob Storage** e parametrizar o **Almacén de datos** e o **Camiño** relativo. Customer Insights anula estes dous parámetros durante a execución da canle cun almacén de datos e unha ruta que é accesible ao produto.

  :::image type="content" source="media/intelligence-designer-importdata.png" alt-text="Exportar configuración do módulo de datos.":::

- Ao escribir a saída da inferencia usando código, cargue a saída a unha ruta dentro de a *almacén de datos rexistrado* no espazo de traballo. Se a ruta e o almacén de datos están parametrizados na canle, Customer Insights poderá ler e importar a saída de inferencia. Actualmente, admítese unha única saída tabular en formato CSV. A ruta debe incluír o directorio e o nome do ficheiro.

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


[!INCLUDE [footer-include](includes/footer-banner.md)]