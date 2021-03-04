---
title: Completar datos parciais mediante predicións
description: Utilice predicións para cubrir datos de clientes incompletos.
ms.date: 05/05/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: zacook
manager: shellyha
ms.openlocfilehash: 577232c7e901dfd54a195c3e9cfac5d1f0f866e6
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268270"
---
# <a name="complete-your-partial-data-with-predictions"></a><span data-ttu-id="9e575-103">Complete os seus datos parciais con predicións</span><span class="sxs-lookup"><span data-stu-id="9e575-103">Complete your partial data with predictions</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="9e575-104">As predicións permiten crear valores previstos facilmente que poden mellorar a comprensión dun cliente.</span><span class="sxs-lookup"><span data-stu-id="9e575-104">Predictions lets you easily create predicted values that can enhance your understanding of a customer.</span></span> <span data-ttu-id="9e575-105">Na páxina **Intelixencia** > **Predicións**, pode seleccionar **As miñas predicións** para ver predicións que configurou noutras partes das estatísticas do público e permitirlle personalizalas aínda máis.</span><span class="sxs-lookup"><span data-stu-id="9e575-105">On the **Intelligence** > **Predictions** page, you can select **My predictions** to see predictions that you've configured in other parts of audience insights, and allow you to further customize them.</span></span>

> [!NOTE]
> <span data-ttu-id="9e575-106">Non pode usar esta función se o seu contorno usa o almacenamento Azure Data Lake Gen 2.</span><span class="sxs-lookup"><span data-stu-id="9e575-106">You can't use this feature if your environment uses Azure Data Lake Gen 2 storage.</span></span>
>
> <span data-ttu-id="9e575-107">A función de predicións usa medios automatizados para avaliar datos e facer predicións a partir dese dato e, polo tanto, ten a capacidade de ser utilizada como método de perfilado, xa que ese termo está definido polo Regulamento xeral de protección de datos ("RXPD").</span><span class="sxs-lookup"><span data-stu-id="9e575-107">The predictions feature uses automated means to evaluate data and make predictions based on that data, and therefore has the capability to be used as a method of profiling, as that term is defined by the General Data Protection Regulation ("GDPR").</span></span> <span data-ttu-id="9e575-108">O uso desta función para o procesamento de datos por parte do cliente pode estar suxeito a RXPD ou a outras leis ou regulamentos.</span><span class="sxs-lookup"><span data-stu-id="9e575-108">Customer's use of this feature to process data may be subject to GDPR or other laws or regulations.</span></span> <span data-ttu-id="9e575-109">Vostede é responsable de garantir que o seu uso de Dynamics 365 Customer Insights, incluíndo as predicións, cumpre con todas as leis e regulamentos aplicables, incluídas as leis relacionadas coa privacidade, os datos persoais, os datos biométricos, a protección de datos e a confidencialidade das comunicacións.</span><span class="sxs-lookup"><span data-stu-id="9e575-109">You are responsible for ensuring that your use of Dynamics 365 Customer Insights, including predictions, complies with all applicable laws and regulations, including laws related to privacy, personal data, biometric data, data protection, and confidentiality of communications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9e575-110">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="9e575-110">Prerequisites</span></span>

<span data-ttu-id="9e575-111">Antes de que a súa organización poida usar a función de predicións, asegúrese de que se cumpran os seguintes requisitos previos:</span><span class="sxs-lookup"><span data-stu-id="9e575-111">Before your organization can use the predictions feature, the following prerequisites must be met:</span></span>

1. <span data-ttu-id="9e575-112">A súa organización ten unha instancia [configurada em Common Data Service](https://docs.microsoft.com/ai-builder/build-model#prerequisites) e está na mesma organización que Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="9e575-112">Your organization has an instance [set up in the Common Data Service](https://docs.microsoft.com/ai-builder/build-model#prerequisites) and it's in the same organization as Customer Insights.</span></span>

2. <span data-ttu-id="9e575-113">O seu contorno está unido á súa instancia de Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="9e575-113">Your environment is attached to your Common Data Service instance.</span></span>

<span data-ttu-id="9e575-114">Se desexa [crear un ambiente novo](manage-environments.md), configúreo na caixa de diálogo **Crear un ambiente** e seleccione **Avanzado**.</span><span class="sxs-lookup"><span data-stu-id="9e575-114">If you're [creating a new environment](manage-environments.md), configure it in the **Create an environment** dialog and select **Advanced**.</span></span> <span data-ttu-id="9e575-115">Se xa creou un ambiente, diríxase á súa configuración e seleccione **Avanzado**.</span><span class="sxs-lookup"><span data-stu-id="9e575-115">If you've already created an environment, go to its settings and select **Advanced**.</span></span> <span data-ttu-id="9e575-116">De calquera xeito, na sección **Usar predicións**, introduza o URL de instancia de Common Data Service ao que desexa conectar o seu contorno.</span><span class="sxs-lookup"><span data-stu-id="9e575-116">Either way, in the **Use predictions** section, enter the Common Data Service instance URL to which you want to attach your environment.</span></span>

## <a name="create-a-prediction-in-the-customer-entity"></a><span data-ttu-id="9e575-117">Crear unha predición na entidade de Cliente</span><span class="sxs-lookup"><span data-stu-id="9e575-117">Create a prediction in the Customer entity</span></span>

1. <span data-ttu-id="9e575-118">Na información do público, vaia a **Datos** > **Entidades**.</span><span class="sxs-lookup"><span data-stu-id="9e575-118">In audience insights, go to **Data** > **Entities**.</span></span>

2. <span data-ttu-id="9e575-119">Seleccione a entidade **Cliente**.</span><span class="sxs-lookup"><span data-stu-id="9e575-119">Select the **Customer** entity.</span></span>

3. <span data-ttu-id="9e575-120">Na entidade **Cliente: CustomerInsights**, seleccione no separador **Campos**.</span><span class="sxs-lookup"><span data-stu-id="9e575-120">In the **Customer:CustomerInsights** entity, select on the **Fields** tab.</span></span>

4. <span data-ttu-id="9e575-121">Atope o nome do atributo para o que desexe prever os valores e seleccione a icona **Visión xeral** na columna **Resumo**.</span><span class="sxs-lookup"><span data-stu-id="9e575-121">Find the attribute name you wish to predict values for, then select the **Overview** icon in the **Summary** column.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9e575-122">![Icona de vista xeral](media/intelligence-overviewicon.png "Icona de vista xeral")</span><span class="sxs-lookup"><span data-stu-id="9e575-122">![Overview icon](media/intelligence-overviewicon.png "Overview icon")</span></span>

5. <span data-ttu-id="9e575-123">Se hai unha alta taxa de valores que faltan para o seu atributo, seleccione **Prever valores que faltan** para continuar coa súa predición.</span><span class="sxs-lookup"><span data-stu-id="9e575-123">If there's a high rate of missing values for your attribute, select **Predict missing values** to continue with your prediction.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9e575-124">![Vista xeral do estado con botón de predición de valores que faltan](media/intelligence-overviewpredictmissingvalues.png "Vista xeral do estado con botón de predición de valores que faltan")</span><span class="sxs-lookup"><span data-stu-id="9e575-124">![Overview status with predict missing values button shown](media/intelligence-overviewpredictmissingvalues.png "Overview status with predict missing values button shown")</span></span>

6. <span data-ttu-id="9e575-125">Proporcione un **Nome para mostrar** e un **Nome da entidade de saída** para os resultados da predición.</span><span class="sxs-lookup"><span data-stu-id="9e575-125">Provide a **Display name** and an **Output entity name** for the results of the prediction.</span></span>

7. <span data-ttu-id="9e575-126">Unha lista de opcións completada previamente amosará onde pode asignar os valores a unha categoría prevista.</span><span class="sxs-lookup"><span data-stu-id="9e575-126">A pre-populated list of options will show where you can map the values to a predicted category.</span></span> <span data-ttu-id="9e575-127">Neste caso, as súas únicas opcións de categoría serán 0 ou 1 xa que se corresponden coa natureza real/falso ou binaria da predición.</span><span class="sxs-lookup"><span data-stu-id="9e575-127">In this case, your only category options will be 0 or 1, as they map to the true/false or binary nature of the prediction.</span></span> <span data-ttu-id="9e575-128">Na columna Categoría, asigne os valores de campo que desexa clasificar como "0" na predición final en "0" e os elementos que desexa clasificar como "1" na predición final en "1".</span><span class="sxs-lookup"><span data-stu-id="9e575-128">In the Category column, map the field values you'd like to be classified as "0" in the final prediction to "0", and the items you'd like to be classified as "1" in the final prediction to "1".</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9e575-129">![Exemplo que mostra os valores de campo asignados a categorías](media/intelligence-categorymapping.png "Exemplo que mostra os valores de campo asignados a categorías")</span><span class="sxs-lookup"><span data-stu-id="9e575-129">![Example showing mapped field values to categories](media/intelligence-categorymapping.png "Example showing mapped field values to categories")</span></span>

8. <span data-ttu-id="9e575-130">Seleccione **Feito** e a predición procesarase.</span><span class="sxs-lookup"><span data-stu-id="9e575-130">Select **Done** and the prediction will be processed.</span></span> <span data-ttu-id="9e575-131">O procesamento levará algún tempo, dependendo do tamaño e complexidade dos datos.</span><span class="sxs-lookup"><span data-stu-id="9e575-131">The processing will take some time, depending on the size and complexity of data.</span></span> <span data-ttu-id="9e575-132">Os resultados estarán dispoñibles nunha nova entidade en función do **Nome da entidade de saída** da predición que creou.</span><span class="sxs-lookup"><span data-stu-id="9e575-132">Results will be available in a new entity based on the **Output entity name** of the prediction you created.</span></span>

## <a name="create-a-prediction-while-creating-a-segment"></a><span data-ttu-id="9e575-133">Crear unha predición mentres se crea un segmento</span><span class="sxs-lookup"><span data-stu-id="9e575-133">Create a prediction while creating a segment</span></span>

<span data-ttu-id="9e575-134">Predicir os valores que faltan para un atributo específico elixido tamén é posible cando se crea un segmento.</span><span class="sxs-lookup"><span data-stu-id="9e575-134">Predicting missing values for a specific attribute of choice is also possible when creating a segment.</span></span> <span data-ttu-id="9e575-135">En concreto, cando crea rapidamente un segmento baseado na entidade de cliente unificada ou na entidade Customer_Measure.</span><span class="sxs-lookup"><span data-stu-id="9e575-135">Specifically, when you quickly create a segment based on either your unified Customer entity or Customer_Measure entity.</span></span>

<span data-ttu-id="9e575-136">Como parte deste fluxo, vostede elixe un atributo específico no que basear o seu segmento, por exemplo, a satisfacción do cliente ou o importe de compra.</span><span class="sxs-lookup"><span data-stu-id="9e575-136">As part of this flow, you'll choose a specific attribute to base your segment on, such as Customer Satisfaction or Purchase Amount.</span></span> <span data-ttu-id="9e575-137">Despois da creación dun segmento, o sistema suxerirá un método para prever todos os valores que faltan para este atributo.</span><span class="sxs-lookup"><span data-stu-id="9e575-137">Upon segment creation, the system will suggest a method for predicting any missing values for this attribute.</span></span>

1. <span data-ttu-id="9e575-138">Na información do público, vaia a **Segmentos** e seleccione o mosaico **Perfís**.</span><span class="sxs-lookup"><span data-stu-id="9e575-138">In audience insights, go to **Segments** and select the **Profiles** tile.</span></span>

2. <span data-ttu-id="9e575-139">Elixa un **Campo** no que crear un segmento, seleccione un **Operador** e logo seleccione **Revisar**.</span><span class="sxs-lookup"><span data-stu-id="9e575-139">Choose a **Field** to create a segment on and select an **Operator**, then select **Review**.</span></span>

3. <span data-ttu-id="9e575-140">Proporcione un **Nome** e un **Nome para mostrar** para o segmento.</span><span class="sxs-lookup"><span data-stu-id="9e575-140">Provide a **Name** and a **Display name** for the segment.</span></span>

4. <span data-ttu-id="9e575-141">Seleccione **Gardar**.</span><span class="sxs-lookup"><span data-stu-id="9e575-141">Select **Save**.</span></span>

5. <span data-ttu-id="9e575-142">Se o segmento que acaba de crear ten datos incompletos no campo de orixe, pode optar por predicir os valores que faltan.</span><span class="sxs-lookup"><span data-stu-id="9e575-142">If the segment you created has incomplete data in the source field, you can choose to predict the missing values.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9e575-143">![Botón de predición](media/segments-predictoption.png "Botón de predición")</span><span class="sxs-lookup"><span data-stu-id="9e575-143">![Prediction button](media/segments-predictoption.png "Prediction button")</span></span>

6. <span data-ttu-id="9e575-144">Proporcione un **Nome para mostrar** e un **Nome da entidade de saída** para os resultados da predición.</span><span class="sxs-lookup"><span data-stu-id="9e575-144">Provide a **Display name** and an **Output entity name** for the results of the prediction.</span></span>

7. <span data-ttu-id="9e575-145">Seleccione **Feito**.</span><span class="sxs-lookup"><span data-stu-id="9e575-145">Select **Done**.</span></span> <span data-ttu-id="9e575-146">A súa predición xerarase en breve e estará dispoñible nunha nova entidade co nome que indicou para o **Nome da entidade de saída**.</span><span class="sxs-lookup"><span data-stu-id="9e575-146">Your prediction will be generated shortly in a new entity with the name you provided for the **Output entity name**.</span></span>

## <a name="view-a-prediction"></a><span data-ttu-id="9e575-147">Ver unha predición</span><span class="sxs-lookup"><span data-stu-id="9e575-147">View a prediction</span></span>

1. <span data-ttu-id="9e575-148">Na información do público, vaia a **Intelixencia** > **Predicións** > **As miñas predicións**.</span><span class="sxs-lookup"><span data-stu-id="9e575-148">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="9e575-149">Seleccione a predición que desexa revisar.</span><span class="sxs-lookup"><span data-stu-id="9e575-149">Select the prediction you want to review.</span></span>

3. <span data-ttu-id="9e575-150">Seleccione os tres puntos na columna **Accións** e escolla **Ver**.</span><span class="sxs-lookup"><span data-stu-id="9e575-150">Select the ellipsis in the **Actions** column and choose **View**.</span></span>

4. <span data-ttu-id="9e575-151">Verá varios puntos de datos na vista da súa predición.</span><span class="sxs-lookup"><span data-stu-id="9e575-151">You'll see a number of data points in the view of your prediction.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9e575-152">![Páxina de predicións](media/intelligence-predictionsviewpage.png "Páxina de predicións")</span><span class="sxs-lookup"><span data-stu-id="9e575-152">![Predictions page](media/intelligence-predictionsviewpage.png "Predictions page")</span></span>

   - <span data-ttu-id="9e575-153">**Valores preditos** mostra a asignación creada durante a fase de asignación do valor do campo coa categoría.</span><span class="sxs-lookup"><span data-stu-id="9e575-153">**Predicted values** shows the mapping you created during the Field value to Category mapping phase.</span></span> <span data-ttu-id="9e575-154">Estes son os valores do seu conxunto de datos que foron asignados a unha categoría específica.</span><span class="sxs-lookup"><span data-stu-id="9e575-154">These are the values in your dataset that have been mapped to a specific category.</span></span>
   <span data-ttu-id="9e575-155">-**Principais elementos con maior influencia** son os factores dentro do seu conxunto de datos que probablemente influíran na confianza da predición de que o seu valor de campo sexa atribuído a unha categoría específica.</span><span class="sxs-lookup"><span data-stu-id="9e575-155">-**Top influencers** are the factors within your dataset that were most likely to influence the prediction's confidence of your Field value being mapped to a specific category.</span></span>
   - <span data-ttu-id="9e575-156">**Desempeño** indica como se están a facer as predicións.</span><span class="sxs-lookup"><span data-stu-id="9e575-156">**Performance** indicates how the predictions are doing.</span></span> <span data-ttu-id="9e575-157">Seleccione a ligazón para obter máis información.</span><span class="sxs-lookup"><span data-stu-id="9e575-157">Select the link to learn more.</span></span>
   - <span data-ttu-id="9e575-158">**Vista previa** mostra exemplos do conxunto de datos de saída da súa predición e a probabilidade, ou a nosa confianza, do valor predito onde 0 é pouco probable e 1 é seguro.</span><span class="sxs-lookup"><span data-stu-id="9e575-158">**Preview** shows samples of the output dataset from your prediction and the likelihood, or our confidence, of the predicted value where 0 is uncertain, and 1 is certain.</span></span>

## <a name="update-a-prediction"></a><span data-ttu-id="9e575-159">Actualizar unha predición</span><span class="sxs-lookup"><span data-stu-id="9e575-159">Update a prediction</span></span>

1. <span data-ttu-id="9e575-160">Na información do público, vaia a **Intelixencia** > **Predicións** > **As miñas predicións**.</span><span class="sxs-lookup"><span data-stu-id="9e575-160">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="9e575-161">Seleccione a predición que desexa actualizar e seleccione a icona **Actualizar**.</span><span class="sxs-lookup"><span data-stu-id="9e575-161">Select the prediction you want to update and select the **Update** icon.</span></span>

3. <span data-ttu-id="9e575-162">A predición programarase para o procesamento.</span><span class="sxs-lookup"><span data-stu-id="9e575-162">The prediction will be scheduled for processing.</span></span> <span data-ttu-id="9e575-163">Pode ver a hora na que se actualizou por última vez na columna **Actualizado** da páxina **Predicións**.</span><span class="sxs-lookup"><span data-stu-id="9e575-163">You can see the time it was last updated in the **Updated** column of the **Predictions** page.</span></span>

## <a name="edit-a-prediction"></a><span data-ttu-id="9e575-164">Editar unha predición</span><span class="sxs-lookup"><span data-stu-id="9e575-164">Edit a prediction</span></span>

<span data-ttu-id="9e575-165">Despois de crear unha predición, pode personalizar o modelo no AI Builder para aumentar a eficacia do seu modelo.</span><span class="sxs-lookup"><span data-stu-id="9e575-165">After you've created a prediction, you can customize the model in the AI Builder to increase the effectiveness of your model.</span></span>  

1. <span data-ttu-id="9e575-166">Na información do público, vaia a **Intelixencia** > **Predicións** > **As miñas predicións**.</span><span class="sxs-lookup"><span data-stu-id="9e575-166">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="9e575-167">Seleccione a predición que desexa editar.</span><span class="sxs-lookup"><span data-stu-id="9e575-167">Select the prediction you want to edit.</span></span>

3. <span data-ttu-id="9e575-168">Seleccione os tres puntos na columna **Accións** e escolla **Ver**.</span><span class="sxs-lookup"><span data-stu-id="9e575-168">Select the ellipsis in the **Actions** column and choose **View**.</span></span>

4. <span data-ttu-id="9e575-169">Seleccione **Personalizar en AI Builder**.</span><span class="sxs-lookup"><span data-stu-id="9e575-169">Select **Customize in AI Builder**.</span></span>

5. <span data-ttu-id="9e575-170">Actualice o seu modelo en AI Builder.</span><span class="sxs-lookup"><span data-stu-id="9e575-170">Update your model in the AI Builder.</span></span> <span data-ttu-id="9e575-171">[Obteña máis información sobre como xestionar modelos en AI builder](https://docs.microsoft.com/ai-builder/manage-model#retrain-and-republish-existing-models).</span><span class="sxs-lookup"><span data-stu-id="9e575-171">[Learn more about managing models in the AI builder](https://docs.microsoft.com/ai-builder/manage-model#retrain-and-republish-existing-models).</span></span>

<span data-ttu-id="9e575-172">A seguinte execución da súa predición usará o modelo actualizado que creou.</span><span class="sxs-lookup"><span data-stu-id="9e575-172">The next run of your prediction will use the updated model you've created.</span></span>

> [!NOTE]
> <span data-ttu-id="9e575-173">Os novos modelos creados en AI Builder non se amosarán nos datos do público a menos que o modelo se crease a partir das experiencias enumeradas anteriormente.</span><span class="sxs-lookup"><span data-stu-id="9e575-173">New models created in AI Builder will not be displayed in audience insights unless the model was created from the experiences listed above.</span></span>

## <a name="remove-a-prediction"></a><span data-ttu-id="9e575-174">Eliminar unha predición</span><span class="sxs-lookup"><span data-stu-id="9e575-174">Remove a prediction</span></span>

1. <span data-ttu-id="9e575-175">Na información do público, vaia a **Intelixencia** > **Predicións** > **As miñas predicións**.</span><span class="sxs-lookup"><span data-stu-id="9e575-175">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="9e575-176">Seleccione a predición que desexe eliminar.</span><span class="sxs-lookup"><span data-stu-id="9e575-176">Select the prediction you want to delete.</span></span>

3. <span data-ttu-id="9e575-177">Seleccione os tres puntos na columna **Accións** e escolla **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="9e575-177">Select the ellipsis in the **Actions** column and choose **Delete**.</span></span>

4. <span data-ttu-id="9e575-178">Confirme a eliminación.</span><span class="sxs-lookup"><span data-stu-id="9e575-178">Confirm the deletion.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="9e575-179">Resolución de problemas</span><span class="sxs-lookup"><span data-stu-id="9e575-179">Troubleshooting</span></span>

<span data-ttu-id="9e575-180">Se non pode completar o proceso de anexar Common Data Service debido a un erro, poderá tentar completar o proceso manualmente.</span><span class="sxs-lookup"><span data-stu-id="9e575-180">If you can't complete the attach Common Data Service process due to an error, you can try to complete the process manually.</span></span> <span data-ttu-id="9e575-181">Existen dous problemas coñecidos que poden ocorrer no proceso de anexar:</span><span class="sxs-lookup"><span data-stu-id="9e575-181">There are two known issues that can occur in the attach process:</span></span>

- <span data-ttu-id="9e575-182">A solución de complemento de tarxeta de cliente non está instalada.</span><span class="sxs-lookup"><span data-stu-id="9e575-182">The Customer Card Add-in solution is not installed.</span></span>
    1. <span data-ttu-id="9e575-183">Complete as instrucións para [instalar e configurar a solución](customer-card-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="9e575-183">Complete the instructions to [install and configure the solution](customer-card-add-in.md).</span></span>

- <span data-ttu-id="9e575-184">Non se conceden permisos de aplicacións.</span><span class="sxs-lookup"><span data-stu-id="9e575-184">App permissions aren't granted.</span></span>
    1. <span data-ttu-id="9e575-185">Vaia a [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="9e575-185">Go to [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).</span></span>
    1. <span data-ttu-id="9e575-186">Seleccione **Contornos**.</span><span class="sxs-lookup"><span data-stu-id="9e575-186">Select **Environments**.</span></span>
    1. <span data-ttu-id="9e575-187">Seleccione os tres puntos situados xunto ao contorno ao que desexa engadir o permiso e seleccione **Configuración**.</span><span class="sxs-lookup"><span data-stu-id="9e575-187">Select the ellipsis next to the environment you want to add the permission to and select **Settings**.</span></span>
    1. <span data-ttu-id="9e575-188">Amplíe **Usuarios + permisos** e seleccione **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="9e575-188">Expand **Users + permissions** and select **Users**.</span></span>
    1. <span data-ttu-id="9e575-189">Seleccione **+ Novo** e seleccione **Usuario**.</span><span class="sxs-lookup"><span data-stu-id="9e575-189">Select **+ New** and select **User**.</span></span>
    1. <span data-ttu-id="9e575-190">Seleccione **Usuario da aplicación** se non está seleccionado e introduza a seguinte información:</span><span class="sxs-lookup"><span data-stu-id="9e575-190">Select **Application User** if it's not already selected and enter the following information:</span></span>
        - <span data-ttu-id="9e575-191">**Nome do usuario:** cihelp@microsoft.com</span><span class="sxs-lookup"><span data-stu-id="9e575-191">**User Name:** cihelp@microsoft.com</span></span>
        - <span data-ttu-id="9e575-192">**ID da aplicación:** 38c77d00-5fcb-4cce-9d93-af4738258e3c</span><span class="sxs-lookup"><span data-stu-id="9e575-192">**Application ID:** 38c77d00-5fcb-4cce-9d93-af4738258e3c</span></span>
        - <span data-ttu-id="9e575-193">**Nome:** cliente</span><span class="sxs-lookup"><span data-stu-id="9e575-193">**First Name:** Customer</span></span>
        - <span data-ttu-id="9e575-194">**Apelido:** información</span><span class="sxs-lookup"><span data-stu-id="9e575-194">**Last Name:** Insights</span></span>
        - <span data-ttu-id="9e575-195">**Correo electrónico principal:** cihelp@microsoft.com</span><span class="sxs-lookup"><span data-stu-id="9e575-195">**Primary Email:** cihelp@microsoft.com</span></span>
    1. <span data-ttu-id="9e575-196">Seleccione **Gardar e pechar**.</span><span class="sxs-lookup"><span data-stu-id="9e575-196">Select **Save & Close**.</span></span>
    1. <span data-ttu-id="9e575-197">Seleccione o usuario que acaba de crear.</span><span class="sxs-lookup"><span data-stu-id="9e575-197">Select the user you just created.</span></span>
    1. <span data-ttu-id="9e575-198">Seleccione **Xestionar funcións** na barra do menú superior.</span><span class="sxs-lookup"><span data-stu-id="9e575-198">Select **Manage Roles** in the top menu bar.</span></span>
    1. <span data-ttu-id="9e575-199">Seleccione **Administrador do sistema** e logo seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9e575-199">Select **System Administrator**, then select **OK**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]