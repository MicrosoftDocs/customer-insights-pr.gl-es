---
title: Exportar datos de Customer Insights a Adobe Campaign Standard
description: Coñeza como usar segmentos de información de público en Adobe Campaign Standard.
ms.date: 02/26/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: a5d0154c3d7c473dcba03fac0847bafcf97de2f2
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596313"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a><span data-ttu-id="65b3e-103">Utilice segmentos de Customer Insights en Adobe Campaign Standard (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="65b3e-103">Use Customer Insights segments in Adobe Campaign Standard (preview)</span></span>

<span data-ttu-id="65b3e-104">Como usuario Insights for Dynamics 365 Customer Insights de audiencia é posible que crease segmentos para facer máis eficientes as súas campañas de márketing dirixíndose a públicos relevantes.</span><span class="sxs-lookup"><span data-stu-id="65b3e-104">As a user of audience insights for Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="65b3e-105">Para usar un segmento de información de audiencia en Adobe Experience Platform e aplicacións como Adobe Campaign Standard, cómpre seguir algúns pasos descritos neste artigo.</span><span class="sxs-lookup"><span data-stu-id="65b3e-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/ACS-flow.png" alt-text="Diagrama de proceso dos pasos descritos neste artigo.":::

## <a name="prerequisites"></a><span data-ttu-id="65b3e-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="65b3e-107">Prerequisites</span></span>

-   <span data-ttu-id="65b3e-108">LIcenza de Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="65b3e-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="65b3e-109">Licenza de Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="65b3e-109">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="65b3e-110">Conta de Azure Blob Storage</span><span class="sxs-lookup"><span data-stu-id="65b3e-110">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="65b3e-111">Visión xeral da campaña</span><span class="sxs-lookup"><span data-stu-id="65b3e-111">Campaign Overview</span></span>

<span data-ttu-id="65b3e-112">Para comprender mellor como pode usar segmentos de información do público en Adobe Experience Platform, vexamos unha mostra de campaña ficticia.</span><span class="sxs-lookup"><span data-stu-id="65b3e-112">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="65b3e-113">Supoñamos que a súa empresa ofrece un servizo mensual baseado na subscrición aos seus clientes nos Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="65b3e-113">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="65b3e-114">Identifique os clientes cuxas subscricións deben renovarse nos próximos oito días pero aínda non renovaron a súa subscrición.</span><span class="sxs-lookup"><span data-stu-id="65b3e-114">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="65b3e-115">Para manter estes clientes, pode enviarlles unha oferta promocional por correo electrónico mediante Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="65b3e-115">To keep these customers, you want to send them a promotional offer via email, using Adobe Campaign Standard.</span></span>

<span data-ttu-id="65b3e-116">Neste exemplo, debemos executar a campaña de correo electrónico promocional unha vez.</span><span class="sxs-lookup"><span data-stu-id="65b3e-116">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="65b3e-117">Este artigo non cubre o caso de uso de realizar a campaña máis dunha vez.</span><span class="sxs-lookup"><span data-stu-id="65b3e-117">This article doesn’t cover the use-case of running the campaign more than once.</span></span> <span data-ttu-id="65b3e-118">Non obstante, a información do público e Adobe Campaign Standard pódense configurar para que funcionen tamén nun escenario de campaña periódica.</span><span class="sxs-lookup"><span data-stu-id="65b3e-118">However, audience insights and Adobe Campaign Standard can be configured to work for a recurring campaign scenario too.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="65b3e-119">Identificar o seu público obxectivo</span><span class="sxs-lookup"><span data-stu-id="65b3e-119">Identify your target audience</span></span>

<span data-ttu-id="65b3e-120">No noso escenario, supoñemos que os enderezos de correo electrónico dos clientes están dispoñibles en información de audiencia e as súas preferencias promocionais analizáronse para identificar os membros do segmento.</span><span class="sxs-lookup"><span data-stu-id="65b3e-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="65b3e-121">O [segmento que definiu nas estatísticas do público](segments.md) chámase **ChurnProneCustomers** e planea enviar a estes clientes a promoción por correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="65b3e-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Captura de pantalla da páxina de segmentos co segmento ChurnProneCustomers creado.":::

<span data-ttu-id="65b3e-123">O correo electrónico de oferta que desexa enviar conterá o nome, apelidos e a data de finalización da subscrición do cliente.</span><span class="sxs-lookup"><span data-stu-id="65b3e-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="65b3e-124">Informa aos clientes sobre o desconto que obterán se renovan a subscrición antes de que remate.</span><span class="sxs-lookup"><span data-stu-id="65b3e-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="65b3e-125">Exportar o seu público obxectivo</span><span class="sxs-lookup"><span data-stu-id="65b3e-125">Export your target audience</span></span>

<span data-ttu-id="65b3e-126">Co noso público obxectivo identificado, podemos configurar a exportación desde a información de audiencia a unha conta de Azure Blob Storage.</span><span class="sxs-lookup"><span data-stu-id="65b3e-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

1. <span data-ttu-id="65b3e-127">Na información do público, vaia a **Administrar** > **Destinos de exportación**.</span><span class="sxs-lookup"><span data-stu-id="65b3e-127">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="65b3e-128">No mosaico de **Campaña de Adobe**, seleccione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="65b3e-128">In the **Adobe Campaign** tile, select **Set up**.</span></span>

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Mosaico de configuración para Adobe Campaign Standard.":::

1. <span data-ttu-id="65b3e-130">Proporcione un **Nome para mostrar** para este novo destino de exportación e despois introduza o **Nome da conta**, **Clave da conta** e **Contedor** da conta de Azure Blob Storage a onde desexa exportar o segmento.</span><span class="sxs-lookup"><span data-stu-id="65b3e-130">Provide a **Display name** for this new export destination and then enter the **Account name**, **Account key**, and **Container** of the Azure Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Captura de pantalla da configuración da conta de almacenamento. "::: 

   - <span data-ttu-id="65b3e-132">Para obter máis información sobre como atopar o nome da conta de almacenamento BLOB de Azure e a clave da conta, consulte [Xestionar a configuración da conta de almacenamento no portal de Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="65b3e-132">To learn more about how to find the Azure Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

   - <span data-ttu-id="65b3e-133">Para obter máis información acerca de como crear un contedor, consulte [Crear un contedor](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="65b3e-133">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="65b3e-134">Seleccione **Seguinte**.</span><span class="sxs-lookup"><span data-stu-id="65b3e-134">Select **Next**.</span></span>

1. <span data-ttu-id="65b3e-135">Escolla o segmento que quere exportar.</span><span class="sxs-lookup"><span data-stu-id="65b3e-135">Choose the segment that you want to export.</span></span> <span data-ttu-id="65b3e-136">Neste exemplo, é **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="65b3e-136">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Captura de pantalla da interface de usuario de selección de segmento co segmento ChurnProneCustomers seleccionado.":::

1. <span data-ttu-id="65b3e-138">Seleccione **Seguinte**.</span><span class="sxs-lookup"><span data-stu-id="65b3e-138">Select **Next**.</span></span>

1. <span data-ttu-id="65b3e-139">Agora asignamos os campos **Orixe** do segmento de información do público aos nomes do campo **Obxectivo** no esquema de perfil Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="65b3e-139">Now we map the **Source** fields from the audience insights segment to the **Target** field names in the Adobe Campaign Standard profile schema.</span></span>

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Asignación de campo para o conector Adobe Campaign Standard.":::

   <span data-ttu-id="65b3e-141">Se desexa engadir máis atributos, seleccione **Engadir atributo**.</span><span class="sxs-lookup"><span data-stu-id="65b3e-141">If you want to add more attributes, select **Add attribute**.</span></span> <span data-ttu-id="65b3e-142">O nome de destino pode ser diferente do nome do campo de orixe, de xeito que aínda pode asignar a saída de segmentos de información de audiencia a Adobe Campaign Standard se os campos non teñen o mesmo nome nos dous sistemas.</span><span class="sxs-lookup"><span data-stu-id="65b3e-142">The target name can be different from the source field name so you can still map segment output from audience insights to Adobe Campaign Standard if the fields don’t have the same name in the two systems.</span></span>

   > [!NOTE]
   > <span data-ttu-id="65b3e-143">O enderezo de correo electrónico úsase como campo de identidade, pero pode usar calquera outro identificador do perfil de cliente de información de público para asignar datos a Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="65b3e-143">Email address is used as an identity field but you can use any other identifier from your audience insights customer profile to map data to Adobe Campaign Standard.</span></span>

1. <span data-ttu-id="65b3e-144">Seleccione **Gardar**.</span><span class="sxs-lookup"><span data-stu-id="65b3e-144">Select **Save**.</span></span>

<span data-ttu-id="65b3e-145">Despois de gardar o destino da exportación, atoparao en **Administrador** > **Exportacións** > **Os meus destinos de exportación**.</span><span class="sxs-lookup"><span data-stu-id="65b3e-145">After saving the export destination, you find it on **Admin** > **Exports** > **My export destinations**.</span></span>

:::image type="content" source="media/export-destination-adobe-campaign-standard.png" alt-text="Captura de pantalla coa lista de exportacións e segmento de mostra resaltado.":::

<span data-ttu-id="65b3e-147">Xa pode [exportar o segmento baixo demanda](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="65b3e-147">You can now [export the segment on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="65b3e-148">A exportación tamén se executará con todas as [actualizacións programadas](system.md).</span><span class="sxs-lookup"><span data-stu-id="65b3e-148">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="65b3e-149">Asegúrese de que o número de rexistros do segmento exportado estea dentro do límite permitido da súa licenza de Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="65b3e-149">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="65b3e-150">Os datos exportados almacénanse no contedor de almacenamento de Azure Blob que configurou anteriormente.</span><span class="sxs-lookup"><span data-stu-id="65b3e-150">Exported data is stored in the Azure Blob storage container you configured above.</span></span> <span data-ttu-id="65b3e-151">A seguinte ruta de cartafol créase automaticamente no seu contedor:</span><span class="sxs-lookup"><span data-stu-id="65b3e-151">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="65b3e-152">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span><span class="sxs-lookup"><span data-stu-id="65b3e-152">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span></span>

<span data-ttu-id="65b3e-153">Exemplo: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span><span class="sxs-lookup"><span data-stu-id="65b3e-153">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span></span>

## <a name="configure-adobe-campaign-standard"></a><span data-ttu-id="65b3e-154">Configurar Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="65b3e-154">Configure Adobe Campaign Standard</span></span>

<span data-ttu-id="65b3e-155">Cando se exporta un segmento de información de audiencia, contén as columnas que seleccionou ao definir o destino da exportación no paso anterior.</span><span class="sxs-lookup"><span data-stu-id="65b3e-155">When a segment from audience insights is exported, it contains the columns you selected while defining the export destination in the previous step.</span></span> <span data-ttu-id="65b3e-156">Estes datos pódense empregar para [crear perfís en Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span><span class="sxs-lookup"><span data-stu-id="65b3e-156">This data can be used to [create profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span></span>

<span data-ttu-id="65b3e-157">Para usar o segmento en Adobe Campaign Standard, necesitamos ampliar o esquema de perfís en Adobe Campaign Standard para incluír dous campos adicionais.</span><span class="sxs-lookup"><span data-stu-id="65b3e-157">To use the segment in Adobe Campaign Standard, we need to extend the profile schema in Adobe Campaign Standard to include two additional fields.</span></span> <span data-ttu-id="65b3e-158">Aprenda a [ampliar o recurso do perfil](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) con novos campos en Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="65b3e-158">Learn how to [extend the profile resource](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) with new fields in Adobe Campaign Standard.</span></span>

<span data-ttu-id="65b3e-159">No noso exemplo, estes campos son *Nome do segmento e data do segmento (opcional).*</span><span class="sxs-lookup"><span data-stu-id="65b3e-159">In our example, these fields are *Segment Name and Segment Date (optional).*</span></span>

<span data-ttu-id="65b3e-160">Usaremos estes campos para identificar os perfís de Adobe Campaign Standard aos que queremos orientar esta campaña.</span><span class="sxs-lookup"><span data-stu-id="65b3e-160">We will use these fields to identify the profiles in Adobe Campaign Standard we want to target for this campaign.</span></span>

<span data-ttu-id="65b3e-161">Se non hai outros rexistros en Adobe Campaign Standard, ademais do que vai importar, pode omitir este paso.</span><span class="sxs-lookup"><span data-stu-id="65b3e-161">If there are no other records in Adobe Campaign Standard, other than what you are going to import, you can skip this step.</span></span>

## <a name="import-data-into-adobe-campaign-standard"></a><span data-ttu-id="65b3e-162">Importar datos a Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="65b3e-162">Import data into Adobe Campaign Standard</span></span>

<span data-ttu-id="65b3e-163">Agora que todo está no seu lugar, necesitamos importar os datos de audiencia preparados da información da audiencia a Adobe Campaign Standard para crear perfís.</span><span class="sxs-lookup"><span data-stu-id="65b3e-163">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Campaign Standard to create profiles.</span></span> <span data-ttu-id="65b3e-164">Aprenda [como importar perfís en Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) usando un fluxo de traballo.</span><span class="sxs-lookup"><span data-stu-id="65b3e-164">Learn [how to import profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) using a workflow.</span></span>

<span data-ttu-id="65b3e-165">O fluxo de traballo de importación da seguinte imaxe configurouse para executarse cada 8 horas e busca segmentos de información de audiencia exportados (ficheiro .csv en Azure Blob Storage).</span><span class="sxs-lookup"><span data-stu-id="65b3e-165">The import workflow in the image below has been configured to run every 8 hours and looks for exported audience insights segments (.csv file in Azure Blob Storage).</span></span> <span data-ttu-id="65b3e-166">O fluxo de traballo extrae o contido do ficheiro .csv nunha orde de columna especificada.</span><span class="sxs-lookup"><span data-stu-id="65b3e-166">The workflow extracts the .csv file content in a specified column order.</span></span> <span data-ttu-id="65b3e-167">Este fluxo de traballo creouse para realizar un tratamento básico de erros e garantir que cada rexistro teña un enderezo de correo electrónico antes de hidratar os datos en Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="65b3e-167">This workflow has been built to perform basic error handling and ensure that each record has an email address before hydrating the data in Adobe Campaign Standard.</span></span> <span data-ttu-id="65b3e-168">O fluxo de traballo tamén extrae o nome do segmento do nome do ficheiro antes de introducilo nos datos do perfil de ACS.</span><span class="sxs-lookup"><span data-stu-id="65b3e-168">The workflow also extracts the segment name from the filename before upserting into ACS Profile data.</span></span>

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Captura de pantalla dun fluxo de traballo de importación na interface de usuario de Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a><span data-ttu-id="65b3e-170">Recuperar o público en Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="65b3e-170">Retrieve the audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="65b3e-171">Unha vez importados os datos a Adobe Campaign Standard, [pode crear un fluxo de traballo](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) e [consultar](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) os clientes en función do *Nome do segmento* e a *Data do segmento* para seleccionar os perfís identificados para a nosa campaña de mostra.</span><span class="sxs-lookup"><span data-stu-id="65b3e-171">Once the data is imported into Adobe Campaign Standard, you [can create a workflow](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) and [query](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) the customers based on the *Segment Name* and *Segment Date* to select profiles that were identified for our sample campaign.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="65b3e-172">Crear e enviar o correo electrónico usando Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="65b3e-172">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="65b3e-173">Cree o contido do correo electrónico e logo [probe e envíe](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) o seu correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="65b3e-173">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Mostra de correo electrónico con oferta de renovación de Adobe Campaign Standard.":::