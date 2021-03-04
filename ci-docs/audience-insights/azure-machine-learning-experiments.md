---
title: Experimentos de Azure Machine Learning
description: Use modelos baseados en Azure Machine Learning en Dynamics 365 Customer Insights.
ms.date: 11/30/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: naravill
ms.author: mhart
ms.reviewer: m-hartmann
manager: shellyha
ms.openlocfilehash: c166015b92596da0c6097e3d25e89579a5186ce0
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267904"
---
# <a name="use-azure-machine-learning-based-models"></a><span data-ttu-id="b5d26-103">Usar modelos baseados en Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="b5d26-103">Use Azure Machine Learning-based models</span></span>

<span data-ttu-id="b5d26-104">Os datos unificados en Dynamics 365 Customer Insights son unha fonte para construír modelos de aprendizaxe automática que poden xerar información comercial adicional.</span><span class="sxs-lookup"><span data-stu-id="b5d26-104">The unified data in Dynamics 365 Customer Insights is a source for building machine learning models that can generate additional business insights.</span></span> <span data-ttu-id="b5d26-105">Customer Insights intégrase con Machine Learning Studio (clásico) e Azure Machine Learning para usar os seus propios modelos personalizados.</span><span class="sxs-lookup"><span data-stu-id="b5d26-105">Customer Insights integrates with Machine Learning Studio (classic) and Azure Machine Learning to use your own custom models.</span></span> <span data-ttu-id="b5d26-106">Consulte os [Experimentos de Machine Learning Studio (clásico)](machine-learning-studio-experiments.md) para ver exemplos de experimentos construídos en Machine Learning Studio (clásico).</span><span class="sxs-lookup"><span data-stu-id="b5d26-106">Refer to [Machine Learning Studio (classic) experiments](machine-learning-studio-experiments.md) for examples of experiments built on Machine Learning Studio (classic).</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="b5d26-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="b5d26-107">Prerequisites</span></span>

- <span data-ttu-id="b5d26-108">Acceder a Customer Insights</span><span class="sxs-lookup"><span data-stu-id="b5d26-108">Access to Customer Insights</span></span>
- <span data-ttu-id="b5d26-109">Activar unha subscrición de Azure Enterprise</span><span class="sxs-lookup"><span data-stu-id="b5d26-109">Active Azure Enterprise subscription</span></span>
- [<span data-ttu-id="b5d26-110">Perfís de cliente unificados</span><span class="sxs-lookup"><span data-stu-id="b5d26-110">Unified customer profiles</span></span>](data-unification.md)
- <span data-ttu-id="b5d26-111">[Exportación de entidades a Azure Blob Storage](export-azure-blob-storage.md) configurada</span><span class="sxs-lookup"><span data-stu-id="b5d26-111">[Entity export to Azure Blob storage](export-azure-blob-storage.md) configured</span></span>

## <a name="set-up-azure-machine-learning-workspace"></a><span data-ttu-id="b5d26-112">Configurar a área de traballo de Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="b5d26-112">Set up Azure Machine Learning workspace</span></span>

1. <span data-ttu-id="b5d26-113">Vexa [crear un espazo de traballo de Azure Machine Learning](https://docs.microsoft.com/azure/machine-learning/concept-workspace#-create-a-workspace) para coñecer diferentes opcións para crear o espazo de traballo.</span><span class="sxs-lookup"><span data-stu-id="b5d26-113">See [create a Azure Machine Learning workspace](https://docs.microsoft.com/azure/machine-learning/concept-workspace#-create-a-workspace) for different options to create the workspace.</span></span> <span data-ttu-id="b5d26-114">Para obter o mellor rendemento, cree o espazo de traballo nunha rexión de Azure xeograficamente máis próxima ao seu entorno de Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="b5d26-114">For best performance, create the workspace in an Azure region that is geographically closest to your Customer Insights environment.</span></span>

1. <span data-ttu-id="b5d26-115">Acceda ao seu espazo de traballo a través de [Azure Machine Learning Studio](https://ml.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="b5d26-115">Access your workspace through the [Azure Machine Learning Studio](https://ml.azure.com/).</span></span> <span data-ttu-id="b5d26-116">Hai varias [formas de interactuar](https://docs.microsoft.com/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) co seu espazo de traballo.</span><span class="sxs-lookup"><span data-stu-id="b5d26-116">There are several [ways to interact](https://docs.microsoft.com/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) with your workspace.</span></span>

## <a name="work-with-azure-machine-learning-designer"></a><span data-ttu-id="b5d26-117">Traballar co deseñador de Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="b5d26-117">Work with Azure Machine Learning designer</span></span>

<span data-ttu-id="b5d26-118">O deseñador de Azure Machine Learning ofrece un lenzo visual onde pode arrastrar e soltar conxuntos de datos e módulos, semellante a Machine Learning Studio (clásico).</span><span class="sxs-lookup"><span data-stu-id="b5d26-118">Azure Machine Learning designer provides a visual canvas where you can drag and drop datasets and modules, similar to Machine Learning Studio (classic).</span></span> <span data-ttu-id="b5d26-119">Unha canle por lotes creada a partir do deseñador pódese integrar en Customer Insights se se configura de acordo.</span><span class="sxs-lookup"><span data-stu-id="b5d26-119">A batch pipeline created from the designer can be integrated into Customer Insights if they are configured accordingly.</span></span> 
   
## <a name="working-with-azure-machine-learning-sdk"></a><span data-ttu-id="b5d26-120">Traballar co SDK de Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="b5d26-120">Working with Azure Machine Learning SDK</span></span>

<span data-ttu-id="b5d26-121">Os científicos de datos e os desenvolvedores de IA usan o [SDK de Azure Machine Learning](https://docs.microsoft.com/python/api/overview/azure/ml/?view=azure-ml-py&preserve-view=true) para crear fluxos de traballo de aprendizaxe automática.</span><span class="sxs-lookup"><span data-stu-id="b5d26-121">Data scientists and AI developers use the [Azure Machine Learning SDK](https://docs.microsoft.com/python/api/overview/azure/ml/?view=azure-ml-py&preserve-view=true) to build machine learning workflows.</span></span> <span data-ttu-id="b5d26-122">Actualmente, os modelos adestrados usando o SDK non se poden integrar directamente con Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="b5d26-122">Currently, models trained using the SDK can't be integrated directly with Customer Insights.</span></span> <span data-ttu-id="b5d26-123">Para integrarse con Customer Insights é necesaria unha canle de inferencia por lotes que consuma ese modelo.</span><span class="sxs-lookup"><span data-stu-id="b5d26-123">A batch inference pipeline that consumes that model is required for integration with Customer Insights.</span></span>

## <a name="batch-pipeline-requirements-to-integrate-with-customer-insights"></a><span data-ttu-id="b5d26-124">Requisitos da canle por lotes para integrarse con Customer Insights</span><span class="sxs-lookup"><span data-stu-id="b5d26-124">Batch pipeline requirements to integrate with Customer Insights</span></span>

### <a name="dataset-configuration"></a><span data-ttu-id="b5d26-125">Configuración do conxunto de datos</span><span class="sxs-lookup"><span data-stu-id="b5d26-125">Dataset Configuration</span></span>

<span data-ttu-id="b5d26-126">Debe crear conxuntos de datos para usar os datos da entidade de Customer Insights na súa canle de inferencia por lotes.</span><span class="sxs-lookup"><span data-stu-id="b5d26-126">You need to create datasets to use entity data from Customer Insights to your batch inference pipeline.</span></span> <span data-ttu-id="b5d26-127">Estes conxuntos de datos deben rexistrarse no espazo de traballo.</span><span class="sxs-lookup"><span data-stu-id="b5d26-127">These datasets need to be registered in the workspace.</span></span> <span data-ttu-id="b5d26-128">Actualmente, só admitimos [conxuntos de datos tabulares](https://docs.microsoft.com/azure/machine-learning/how-to-create-register-datasets#tabulardataset) en formato .csv.</span><span class="sxs-lookup"><span data-stu-id="b5d26-128">Currently, we only support [tabular datasets](https://docs.microsoft.com/azure/machine-learning/how-to-create-register-datasets#tabulardataset) in .csv format.</span></span> <span data-ttu-id="b5d26-129">Os conxuntos de datos que corresponden aos datos da entidade deben ser parametrizados como parámetro de canle.</span><span class="sxs-lookup"><span data-stu-id="b5d26-129">The datasets that correspond to entity data need to be parameterized as a pipeline parameter.</span></span>
   
* <span data-ttu-id="b5d26-130">Parámetros do conxunto de datos no deseñador</span><span class="sxs-lookup"><span data-stu-id="b5d26-130">Dataset parameters in Designer</span></span>
   
     <span data-ttu-id="b5d26-131">No deseñador, abra **Seleccionar columnas no conxunto de datos** e seleccione **Establecer como parámetro de canle** onde vostede fornece un nome para o parámetro.</span><span class="sxs-lookup"><span data-stu-id="b5d26-131">In the designer, open **Select Columns in Dataset** and select **Set as pipeline parameter** where you provide a name for the parameter.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="b5d26-132">![Parametrización do conxunto de datos no deseñador](media/intelligence-designer-dataset-parameters.png "Parametrización do conxunto de datos no deseñador")</span><span class="sxs-lookup"><span data-stu-id="b5d26-132">![Dataset parameterization in designer](media/intelligence-designer-dataset-parameters.png "Dataset parameterization in designer")</span></span>
   
* <span data-ttu-id="b5d26-133">Parámetro do conxunto de datos no SDK (Python)</span><span class="sxs-lookup"><span data-stu-id="b5d26-133">Dataset parameter in SDK (Python)</span></span>
   
   ```python
   HotelStayActivity_dataset = Dataset.get_by_name(ws, name='Hotel Stay Activity Data')
   HotelStayActivity_pipeline_param = PipelineParameter(name="HotelStayActivity_pipeline_param", default_value=HotelStayActivity_dataset)
   HotelStayActivity_ds_consumption = DatasetConsumptionConfig("HotelStayActivity_dataset", HotelStayActivity_pipeline_param)
   ```

### <a name="batch-inference-pipeline"></a><span data-ttu-id="b5d26-134">Canle de inferencia por lotes</span><span class="sxs-lookup"><span data-stu-id="b5d26-134">Batch inference pipeline</span></span>
  
* <span data-ttu-id="b5d26-135">No deseñador pódese usar unha canle de adestramento para crear ou actualizar unha canle de inferencia.</span><span class="sxs-lookup"><span data-stu-id="b5d26-135">In the designer, a training pipeline can be used to create or update an inference pipeline.</span></span> <span data-ttu-id="b5d26-136">Actualmente só se admiten canles de inferencia por lotes.</span><span class="sxs-lookup"><span data-stu-id="b5d26-136">Currently, only batch inference pipelines are supported.</span></span>

* <span data-ttu-id="b5d26-137">Usando o SDK, pode publicar a canle nun punto extremo.</span><span class="sxs-lookup"><span data-stu-id="b5d26-137">Using the SDK, you can publish the pipeline to an endpoint.</span></span> <span data-ttu-id="b5d26-138">Actualmente, Customer Insights intégrase coa canle predeterminada nun extremo de canle por lotes no espazo de traballo de aprendizaxe automática.</span><span class="sxs-lookup"><span data-stu-id="b5d26-138">Currently, Customer Insights integrates with the default pipeline in a batch pipeline endpoint in the Machine Learning workspace.</span></span>
   
   ```python
   published_pipeline = pipeline.publish(name="ChurnInferencePipeline", description="Published Churn Inference pipeline")
   pipeline_endpoint = PipelineEndpoint.get(workspace=ws, name="ChurnPipelineEndpoint") 
   pipeline_endpoint.add_default(pipeline=published_pipeline)
   ```

### <a name="import-pipeline-data-into-customer-insights"></a><span data-ttu-id="b5d26-139">Importar datos da canle a Customer Insights</span><span class="sxs-lookup"><span data-stu-id="b5d26-139">Import pipeline data into Customer Insights</span></span>

* <span data-ttu-id="b5d26-140">O deseñador proporciona o [módulo Exportar datos](https://docs.microsoft.com/azure/machine-learning/algorithm-module-reference/export-data) que permite exportar a saída dunha canle ao almacenamento de Azure.</span><span class="sxs-lookup"><span data-stu-id="b5d26-140">The designer provides the [Export Data module](https://docs.microsoft.com/azure/machine-learning/algorithm-module-reference/export-data) that allows the output of a pipeline to be exported to Azure storage.</span></span> <span data-ttu-id="b5d26-141">Actualmente, o módulo debe usar o tipo de almacén de datos **Azure Blob Storage** e parametrizar o **Almacén de datos** e o **Camiño** relativo.</span><span class="sxs-lookup"><span data-stu-id="b5d26-141">Currently, the module must use the datastore type **Azure Blob Storage** and parameterize the **Datastore** and relative **Path**.</span></span> <span data-ttu-id="b5d26-142">Customer Insights anula estes dous parámetros durante a execución da canle cun almacén de datos e unha ruta que é accesible ao produto.</span><span class="sxs-lookup"><span data-stu-id="b5d26-142">Customer Insights overrides both these parameters during pipeline execution with a datastore and path that is accessible to the product.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b5d26-143">![Exportar configuración do módulo de datos](media/intelligence-designer-importdata.png "Exportar configuración do módulo de datos")</span><span class="sxs-lookup"><span data-stu-id="b5d26-143">![Export Data Module Configuration](media/intelligence-designer-importdata.png "Export Data Module Configuration")</span></span>
   
* <span data-ttu-id="b5d26-144">Ao escribir a saída de inferencia usando código, pode cargar a saída no camiño a dentro dun *almacén de datos rexistrado* no espazo de traballo.</span><span class="sxs-lookup"><span data-stu-id="b5d26-144">When writing the inference output using code, you can upload the output to the a path within a *registered datastore* in the workspace.</span></span> <span data-ttu-id="b5d26-145">Se a ruta e o almacén de datos están parametrizados na canle, Customer Insights poderá ler e importar a saída de inferencia.</span><span class="sxs-lookup"><span data-stu-id="b5d26-145">If the path and datastore are parameterized in the pipeline, Customer insights will be able to read and import the inference output.</span></span> <span data-ttu-id="b5d26-146">Actualmente, admítese unha única saída tabular en formato CSV.</span><span class="sxs-lookup"><span data-stu-id="b5d26-146">Currently, a single tabular output in csv format is supported.</span></span> <span data-ttu-id="b5d26-147">A ruta debe incluír o directorio e o nome do ficheiro.</span><span class="sxs-lookup"><span data-stu-id="b5d26-147">The path must include the directory and filename.</span></span>

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