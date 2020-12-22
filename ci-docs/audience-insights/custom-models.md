---
title: Modelos de aprendizaxe automático personalizados | Microsoft Docs
description: Traballe con modelos personalizados de Azure Machine Learning en Dynamics 365 Customer Insights.
ms.date: 11/19/2020
ms.reviewer: zacook
ms.service: dynamics-365-ai
ms.topic: article
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ef248086b30b870359970529a7bfb37792be62d5
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668901"
---
# <a name="custom-machine-learning-models"></a><span data-ttu-id="1e06d-103">Modelos de aprendizaxe automático personalizados</span><span class="sxs-lookup"><span data-stu-id="1e06d-103">Custom machine learning models</span></span>

<span data-ttu-id="1e06d-104">**Intelixencia** > **Modelos personalizados** permítelle xestionar fluxos de traballo baseados en modelos de Azure Machine Learning.</span><span class="sxs-lookup"><span data-stu-id="1e06d-104">**Intelligence** > **Custom models** lets you manage workflows based on Azure Machine Learning models.</span></span> <span data-ttu-id="1e06d-105">Os fluxos de traballo axúdanlle a escoller os datos dos que queres xerar información e asignar os resultados aos datos dos seus clientes unificados.</span><span class="sxs-lookup"><span data-stu-id="1e06d-105">Workflows help you choose the data you want to generate insights from and map the results to your unified customer data.</span></span> <span data-ttu-id="1e06d-106">Para obter máis información sobre a creación de modelos de aprendizaxe automática personalizados, consulte [Usar modelos baseados en Azure Machine Learning](azure-machine-learning-experiments.md).</span><span class="sxs-lookup"><span data-stu-id="1e06d-106">For more information about building custom ML models, see [Use Azure Machine Learning-based models](azure-machine-learning-experiments.md).</span></span>

## <a name="responsible-ai"></a><span data-ttu-id="1e06d-107">IA responsable</span><span class="sxs-lookup"><span data-stu-id="1e06d-107">Responsible AI</span></span>

<span data-ttu-id="1e06d-108">As predicións ofrecen capacidades para crear mellores experiencias de cliente, mellorar as capacidades comerciais e os fluxos de ingresos.</span><span class="sxs-lookup"><span data-stu-id="1e06d-108">Predictions offer capabilities to create better customer experiences, improve business capabilities, and revenue streams.</span></span> <span data-ttu-id="1e06d-109">Recomendamos encarecidamente que equilibre o valor da súa predición co impacto que ten e os prexuízos que se poden introducir de xeito ético.</span><span class="sxs-lookup"><span data-stu-id="1e06d-109">We strongly recommend you balance the value of your prediction against the impact it has and biases that may be introduced in an ethical manner.</span></span> <span data-ttu-id="1e06d-110">Máis información sobre como Microsoft está [abordando a IA responsable](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span><span class="sxs-lookup"><span data-stu-id="1e06d-110">Learn more about how Microsoft is [addressing Responsible AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span></span> <span data-ttu-id="1e06d-111">Tamén pode aprender sobre [técnicas e procesos de aprendizaxe automática responsable](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml) específicos para Azure Machine Learning.</span><span class="sxs-lookup"><span data-stu-id="1e06d-111">You can also learn about [techniques and processes for responsible machine learning](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml) specific to Azure Machine Learning.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1e06d-112">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="1e06d-112">Prerequisites</span></span>

- <span data-ttu-id="1e06d-113">Actualmente, esta función admite servizos web publicados a través de [Machine Learning Studio (clásico)](https://studio.azureml.net) e [ canles de lotes de Azure Machine Learning](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines).</span><span class="sxs-lookup"><span data-stu-id="1e06d-113">Currently, this feature supports web services published through [Machine Learning Studio (classic)](https://studio.azureml.net) and [Azure Machine Learning batch pipelines](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines).</span></span>

- <span data-ttu-id="1e06d-114">Necesita unha conta de almacenamento de Azure Data Lake Gen2 asociada á súa instancia de Azure Studio para usar esta función.</span><span class="sxs-lookup"><span data-stu-id="1e06d-114">You need an Azure Data Lake Gen2 storage account associated with your Azure Studio instance to use this feature.</span></span> <span data-ttu-id="1e06d-115">Para obter máis información, consulte [Crear unha conta de almacenamento de Azure Data Lake Storage Gen2](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)</span><span class="sxs-lookup"><span data-stu-id="1e06d-115">For more information, see [Create an Azure Data Lake Storage Gen2 storage account](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)</span></span>

## <a name="add-a-new-workflow"></a><span data-ttu-id="1e06d-116">Engadir un novo fluxo de traballo</span><span class="sxs-lookup"><span data-stu-id="1e06d-116">Add a new workflow</span></span>

1. <span data-ttu-id="1e06d-117">Vaia a **Intelixencia** > **Modelos personalizados** e seleccione **Novo fluxo de traballo**.</span><span class="sxs-lookup"><span data-stu-id="1e06d-117">Go to **Intelligence** > **Custom models** and select **New workflow**.</span></span>

1. <span data-ttu-id="1e06d-118">Déalle ao seu modelo personalizado un nome recoñecible no campo **Nome**.</span><span class="sxs-lookup"><span data-stu-id="1e06d-118">Give your custom model a recognizable name in the **Name** field.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1e06d-119">![Captura de pantalla do panel Fluxo de traballo novo](media/new-workflowv2.png "Captura de pantalla do panel Fluxo de traballo novo")</span><span class="sxs-lookup"><span data-stu-id="1e06d-119">![Screenshot of the New workflow pane](media/new-workflowv2.png "Screenshot of the New workflow pane")</span></span>

1. <span data-ttu-id="1e06d-120">Seleccione a organización que contén o servizo web en **Arrendatario que contén o seu servizo web**.</span><span class="sxs-lookup"><span data-stu-id="1e06d-120">Select the organization that contains the web service in **Tenant that contains your web service**.</span></span>

1. <span data-ttu-id="1e06d-121">Se a súa subscrición a Azure Machine Learning está noutro arrendatario que non sexa Customer Insights, seleccione **Iniciar sesión** coas túas credenciais para a organización seleccionada.</span><span class="sxs-lookup"><span data-stu-id="1e06d-121">If your Azure Machine Learning subscription is in a different tenant than Customer Insights, select **Sign in** with your credentials for the selected organization.</span></span>

1. <span data-ttu-id="1e06d-122">Seleccione os **espazos de traballo** asociados ao seu servizo web.</span><span class="sxs-lookup"><span data-stu-id="1e06d-122">Select the **Workspaces** associated with your web service.</span></span> <span data-ttu-id="1e06d-123">Enumeráronse dúas seccións, unha para Azure Machine Learning v.1 (Machine Learning Studio [clásico]) e Azure Machine Learning v.2 (Azure Machine Learning).</span><span class="sxs-lookup"><span data-stu-id="1e06d-123">There are two sections listed, one for Azure Machine Learning v1 (Machine Learning Studio (classic)) and Azure Machine Learning v2 (Azure Machine Learning).</span></span> <span data-ttu-id="1e06d-124">Se non está seguro de cal é o espazo de traballo adecuado para o seu servizo web de Machine Learning Studio (clásico), seleccione **Calquera**.</span><span class="sxs-lookup"><span data-stu-id="1e06d-124">If you're not sure which workspace is the right one for your Machine Learning Studio (classic) web service, select **Any**.</span></span>

1. <span data-ttu-id="1e06d-125">Escolla o servizo web de Machine Learning Studio (clásico) ou a canle de Azure Machine Learning no menú despregable **Servizo web que contén o seu modelo**.</span><span class="sxs-lookup"><span data-stu-id="1e06d-125">Choose the Machine Learning Studio (classic) web service or Azure Machine Learning pipeline in the **Web service that contains your model** dropdown.</span></span> <span data-ttu-id="1e06d-126">despois, seleccione **Seguinte**.</span><span class="sxs-lookup"><span data-stu-id="1e06d-126">Then, select **Next**.</span></span>
   - <span data-ttu-id="1e06d-127">Máis información sobre a [publicación dun servizo web en Machine Learning Studio (clásico)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span><span class="sxs-lookup"><span data-stu-id="1e06d-127">Learn more about [publishing a web service in Machine Learning Studio (classic)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span></span>
   - <span data-ttu-id="1e06d-128">Máis información sobre a [Publicación dunha canle en Azure Machine Learning usando o deseñador](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) ou [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span><span class="sxs-lookup"><span data-stu-id="1e06d-128">Learn more about [publishing a pipeline in Azure Machine Learning using the designer](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) or [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span></span> 
     > [!NOTE]
     > <span data-ttu-id="1e06d-129">A canle debe publicarse nun [extremo de canle](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span><span class="sxs-lookup"><span data-stu-id="1e06d-129">Your pipeline must be published under a [pipeline endpoint](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span></span>

1. <span data-ttu-id="1e06d-130">Para cada **Entrada do servizo web**, seleccione a **Entidade** coincidente da información sobre o público e seleccione **Seguinte**.</span><span class="sxs-lookup"><span data-stu-id="1e06d-130">For each **Web service input**, select the matching **Entity** from audience insights and select **Next**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1e06d-131">![Configurar un fluxo de traballo](media/intelligence-screen2-updated.png "Configurar un fluxo de traballo")</span><span class="sxs-lookup"><span data-stu-id="1e06d-131">![Configure a workflow](media/intelligence-screen2-updated.png "Configure a workflow")</span></span>

1. <span data-ttu-id="1e06d-132">No paso **Parámetros de saída do modelo**, configure as seguintes propiedades:</span><span class="sxs-lookup"><span data-stu-id="1e06d-132">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="1e06d-133">Machine Learning Studio (clásico)</span><span class="sxs-lookup"><span data-stu-id="1e06d-133">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="1e06d-134">Introduza o **Nome da entidade** de saída á quere que flúan os resultados de saída do servizo web.</span><span class="sxs-lookup"><span data-stu-id="1e06d-134">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="1e06d-135">Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="1e06d-135">Azure Machine Learning</span></span>
      1. <span data-ttu-id="1e06d-136">Introduza o **Nome da entidade** de saída á quere que flúan os resultados de saída da canle.</span><span class="sxs-lookup"><span data-stu-id="1e06d-136">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="1e06d-137">Seleccione o **nome do parámetro do almacén de datos de saída** da súa canle de lotes desde o menú despregable.</span><span class="sxs-lookup"><span data-stu-id="1e06d-137">Select the **Output data store parameter name** of your batch pipeline from the dropdown.</span></span>
      1. <span data-ttu-id="1e06d-138">Seleccione o **nome do parámetro do camiño de saída** da súa canle de lotes desde o menú despregable.</span><span class="sxs-lookup"><span data-stu-id="1e06d-138">Select the **Output Path parameter name** of your batch pipeline from the dropdown.</span></span>
      
      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="1e06d-139">![Panel de parámetros de saída do modelo](media/intelligence-screen3-outputparameters.png "Panel de parámetros de saída do modelo")</span><span class="sxs-lookup"><span data-stu-id="1e06d-139">![Model Output Parameter Pane](media/intelligence-screen3-outputparameters.png "Model Output Parameter Pane")</span></span>

1. <span data-ttu-id="1e06d-140">Seleccione o atributo coincidente na lista despregable **Identificador de cliente nos resultados** que identifica os clientes e seleccione **Gardar**.</span><span class="sxs-lookup"><span data-stu-id="1e06d-140">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>
   
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1e06d-141">![Relacionar resultados co panel de datos do cliente](media/intelligence-screen4-relatetocustomer.png "Relacionar resultados co panel de datos do cliente")</span><span class="sxs-lookup"><span data-stu-id="1e06d-141">![Relate results to Customer data pane](media/intelligence-screen4-relatetocustomer.png "Relate results to Customer data pane")</span></span>

1. <span data-ttu-id="1e06d-142">Verá a pantalla **Fluxo de traballo gardado** con detalles sobre o fluxo de traballo.</span><span class="sxs-lookup"><span data-stu-id="1e06d-142">You'll see the **Workflow Saved** screen with details about the workflow.</span></span>    
   <span data-ttu-id="1e06d-143">Se configurou un fluxo de traballo para unha canle de Azure Machine Learning, a información do público anexarase ao espazo de traballo que contén a canle.</span><span class="sxs-lookup"><span data-stu-id="1e06d-143">If you configured a workflow for an Azure Machine Learning pipeline, audience insights will attach to the workspace that contains the pipeline.</span></span> <span data-ttu-id="1e06d-144">A información do público obterá un rol de **Colaborador** no espazo de traballo de Azure.</span><span class="sxs-lookup"><span data-stu-id="1e06d-144">Audience insights will get a **Contributor** role on the Azure workspace.</span></span>

1. <span data-ttu-id="1e06d-145">Seleccione **Feito**.</span><span class="sxs-lookup"><span data-stu-id="1e06d-145">Select **Done**.</span></span>

1. <span data-ttu-id="1e06d-146">Agora pode executar o fluxo de traballo desde a páxina **Modelos personalizados**.</span><span class="sxs-lookup"><span data-stu-id="1e06d-146">You can now run the workflow from the **Custom Models** page.</span></span>

## <a name="edit-a-workflow"></a><span data-ttu-id="1e06d-147">Editar un fluxo de traballo</span><span class="sxs-lookup"><span data-stu-id="1e06d-147">Edit a workflow</span></span>

1. <span data-ttu-id="1e06d-148">Na páxina **Modelos personalizados**, seleccione os tres puntos verticais na columna **Accións** situada xunto a un fluxo de traballo creado anteriormente e seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="1e06d-148">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created and select **Edit**.</span></span>

1. <span data-ttu-id="1e06d-149">Pode actualizar o nome recoñecible do seu fluxo de traballo no campo **Nome de visualización**, pero non pode cambiar o servizo web ou a canle configurados.</span><span class="sxs-lookup"><span data-stu-id="1e06d-149">You can update your workflow's recognizable name in the **Display name** field, but you can't change the configured web service or pipeline.</span></span> <span data-ttu-id="1e06d-150">Seleccione **Seguinte**.</span><span class="sxs-lookup"><span data-stu-id="1e06d-150">Select **Next**.</span></span>

1. <span data-ttu-id="1e06d-151">Para cada **Entrada do servizo web**, pode actualizar a **Entidade** coincidente da información sobre o público.</span><span class="sxs-lookup"><span data-stu-id="1e06d-151">For each **Web service input**, you can update the matching **Entity** from audience insights.</span></span> <span data-ttu-id="1e06d-152">despois, seleccione **Seguinte**.</span><span class="sxs-lookup"><span data-stu-id="1e06d-152">Then, select **Next**.</span></span>

1. <span data-ttu-id="1e06d-153">No paso **Parámetros de saída do modelo**, configure as seguintes propiedades:</span><span class="sxs-lookup"><span data-stu-id="1e06d-153">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="1e06d-154">Machine Learning Studio (clásico)</span><span class="sxs-lookup"><span data-stu-id="1e06d-154">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="1e06d-155">Introduza o **Nome da entidade** de saída á quere que flúan os resultados de saída do servizo web.</span><span class="sxs-lookup"><span data-stu-id="1e06d-155">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="1e06d-156">Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="1e06d-156">Azure Machine Learning</span></span>
      1. <span data-ttu-id="1e06d-157">Introduza o **Nome da entidade** de saída á quere que flúan os resultados de saída da canle.</span><span class="sxs-lookup"><span data-stu-id="1e06d-157">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="1e06d-158">Seleccione o **Nome do parámetro do almacén de datos de saída** para a súa canle de proba.</span><span class="sxs-lookup"><span data-stu-id="1e06d-158">Select the **Output data store parameter name** for your test pipeline.</span></span>
      1. <span data-ttu-id="1e06d-159">Seleccione o **Nome do parámetro do camiño de saída** para a súa canle de proba.</span><span class="sxs-lookup"><span data-stu-id="1e06d-159">Select the **Output Path parameter name** for your test pipeline.</span></span>

1. <span data-ttu-id="1e06d-160">Seleccione o atributo coincidente na lista despregable **Identificador de cliente nos resultados** que identifica os clientes e seleccione **Gardar**.</span><span class="sxs-lookup"><span data-stu-id="1e06d-160">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>
   <span data-ttu-id="1e06d-161">Debe escoller un atributo da saída de inferencia con valores similares á columna ID de cliente da entidade Cliente.</span><span class="sxs-lookup"><span data-stu-id="1e06d-161">You need to choose an attribute from the inference output with values similar to the Customer ID column of the Customer entity.</span></span> <span data-ttu-id="1e06d-162">Se non ten esa columna no seu conxunto de datos, escolla un atributo que identifique de xeito único a fila.</span><span class="sxs-lookup"><span data-stu-id="1e06d-162">If don't have such a column in your data set, choose an attribute that uniquely identifies the row.</span></span>

## <a name="run-a-workflow"></a><span data-ttu-id="1e06d-163">Executar un fluxo de traballo</span><span class="sxs-lookup"><span data-stu-id="1e06d-163">Run a workflow</span></span>

1. <span data-ttu-id="1e06d-164">Na páxina **Modelos personalizados**, seleccione os tres puntos verticais na columna **Accións** situada xunto a un fluxo de traballo creado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="1e06d-164">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="1e06d-165">Seleccione **Executar**.</span><span class="sxs-lookup"><span data-stu-id="1e06d-165">Select **Run**.</span></span>

<span data-ttu-id="1e06d-166">O seu fluxo de traballo tamén se executa automaticamente con todas as actualizacións programadas.</span><span class="sxs-lookup"><span data-stu-id="1e06d-166">Your workflow also runs automatically with every scheduled refresh.</span></span> <span data-ttu-id="1e06d-167">Obteña máis información acerca de como [configurar actualizacións programadas](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="1e06d-167">Learn more about [setting up scheduled refreshes](system.md#schedule-tab).</span></span>

## <a name="delete-a-workflow"></a><span data-ttu-id="1e06d-168">Eliminar un fluxo de traballo</span><span class="sxs-lookup"><span data-stu-id="1e06d-168">Delete a workflow</span></span>

1. <span data-ttu-id="1e06d-169">Na páxina **Modelos personalizados**, seleccione os tres puntos verticais na columna **Accións** situada xunto a un fluxo de traballo creado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="1e06d-169">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="1e06d-170">Seleccione **Eliminar** e confirme a eliminación.</span><span class="sxs-lookup"><span data-stu-id="1e06d-170">Select **Delete** and confirm your deletion.</span></span>

<span data-ttu-id="1e06d-171">Eliminarase o seu fluxo de traballo.</span><span class="sxs-lookup"><span data-stu-id="1e06d-171">Your workflow will be deleted.</span></span> <span data-ttu-id="1e06d-172">A [entidade](entities.md) que se creou cando creou o fluxo de traballo continuará e poderá verse desde a páxina **Entidades**.</span><span class="sxs-lookup"><span data-stu-id="1e06d-172">The [entity](entities.md) that was created when you created the workflow persists, and can be viewed from the **Entities** page.</span></span>
