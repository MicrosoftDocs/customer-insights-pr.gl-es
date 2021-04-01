---
title: Exportar datos de Customer Insights á plataforma Adobe Experience
description: Coñeza como usar segmentos de información de público na Adobe Experience Platform.
ms.date: 02/26/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: d1856861562be55c6d1d051050fe965560fa42f8
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596267"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a><span data-ttu-id="23d60-103">Utilice segmentos de Customer Insights na Adobe Experience Platform (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="23d60-103">Use Customer Insights segments in Adobe Experience Platform (preview)</span></span>

<span data-ttu-id="23d60-104">Como usuario Insights for Dynamics 365 Customer Insights de audiencia é posible que crease segmentos para facer máis eficientes as súas campañas de márketing dirixíndose a públicos relevantes.</span><span class="sxs-lookup"><span data-stu-id="23d60-104">As a user of audience insights for Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="23d60-105">Para usar un segmento de información de audiencia en Adobe Experience Platform e aplicacións como Adobe Campaign Standard, cómpre seguir algúns pasos descritos neste artigo.</span><span class="sxs-lookup"><span data-stu-id="23d60-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/AEP-flow.png" alt-text="Diagrama de proceso dos pasos descritos neste artigo.":::

## <a name="prerequisites"></a><span data-ttu-id="23d60-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="23d60-107">Prerequisites</span></span>

-   <span data-ttu-id="23d60-108">LIcenza de Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="23d60-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="23d60-109">Licenza de Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="23d60-109">Adobe Experience Platform license</span></span>
-   <span data-ttu-id="23d60-110">Licenza de Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="23d60-110">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="23d60-111">Conta de Azure Blob Storage</span><span class="sxs-lookup"><span data-stu-id="23d60-111">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="23d60-112">Visión xeral da campaña</span><span class="sxs-lookup"><span data-stu-id="23d60-112">Campaign Overview</span></span>

<span data-ttu-id="23d60-113">Para comprender mellor como pode usar segmentos de información do público en Adobe Experience Platform, vexamos unha mostra de campaña ficticia.</span><span class="sxs-lookup"><span data-stu-id="23d60-113">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="23d60-114">Supoñamos que a súa empresa ofrece un servizo mensual baseado na subscrición aos seus clientes nos Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="23d60-114">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="23d60-115">Identifique os clientes cuxas subscricións deben renovarse nos próximos oito días pero aínda non renovaron a súa subscrición.</span><span class="sxs-lookup"><span data-stu-id="23d60-115">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="23d60-116">Para manter estes clientes, pode enviarlles unha oferta promocional por correo electrónico mediante a Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="23d60-116">To keep these customers, you want to send them a promotional offer via email, using Adobe Experience Platform.</span></span>

<span data-ttu-id="23d60-117">Neste exemplo, debemos executar a campaña de correo electrónico promocional unha vez.</span><span class="sxs-lookup"><span data-stu-id="23d60-117">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="23d60-118">Este artigo non cubre o caso de uso de realizar a campaña máis dunha vez.</span><span class="sxs-lookup"><span data-stu-id="23d60-118">This article doesn’t cover the use-case of running the campaign more than once.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="23d60-119">Identificar o seu público obxectivo</span><span class="sxs-lookup"><span data-stu-id="23d60-119">Identify your target audience</span></span>

<span data-ttu-id="23d60-120">No noso escenario, supoñemos que os enderezos de correo electrónico dos clientes están dispoñibles en información de audiencia e as súas preferencias promocionais analizáronse para identificar os membros do segmento.</span><span class="sxs-lookup"><span data-stu-id="23d60-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="23d60-121">O [segmento que definiu nas estatísticas do público](segments.md) chámase **ChurnProneCustomers** e planea enviar a estes clientes a promoción por correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="23d60-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Captura de pantalla da páxina de segmentos co segmento ChurnProneCustomers creado.":::

<span data-ttu-id="23d60-123">O correo electrónico de oferta que desexa enviar conterá o nome, apelidos e a data de finalización da subscrición do cliente.</span><span class="sxs-lookup"><span data-stu-id="23d60-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="23d60-124">Informa aos clientes sobre o desconto que obterán se renovan a subscrición antes de que remate.</span><span class="sxs-lookup"><span data-stu-id="23d60-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="23d60-125">Exportar o seu público obxectivo</span><span class="sxs-lookup"><span data-stu-id="23d60-125">Export your target audience</span></span>

<span data-ttu-id="23d60-126">Co noso público obxectivo identificado, podemos configurar a exportación desde a información de audiencia a unha conta de Azure Blob Storage.</span><span class="sxs-lookup"><span data-stu-id="23d60-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

1. <span data-ttu-id="23d60-127">Na información do público, vaia a **Administrar** > **Destinos de exportación**.</span><span class="sxs-lookup"><span data-stu-id="23d60-127">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="23d60-128">No mosaico **Azure Blob Storage**, seleccione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="23d60-128">In the **Azure Blob Storage** tile, select **Set up**.</span></span>

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Mosaico de configuración para Azure Blob Storage.":::

1. <span data-ttu-id="23d60-130">Proporcione un **Nome para mostrar** para este novo destino de exportación e despois introduza o **Nome da conta**, **Clave da conta** e **Contedor** da conta de Azure Blob Storage a onde desexa exportar o segmento.</span><span class="sxs-lookup"><span data-stu-id="23d60-130">Provide a **Display name** for this new export destination and then enter the **Account name**, **Account key**, and **Container** of the Azure Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Captura de pantalla da configuración da conta de almacenamento. "::: 

   - <span data-ttu-id="23d60-132">Para obter máis información sobre como atopar o nome da conta de almacenamento BLOB de Azure e a clave da conta, consulte [Xestionar a configuración da conta de almacenamento no portal de Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="23d60-132">To learn more about how to find the Azure Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

   - <span data-ttu-id="23d60-133">Para obter máis información acerca de como crear un contedor, consulte [Crear un contedor](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="23d60-133">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="23d60-134">Seleccione **Seguinte**.</span><span class="sxs-lookup"><span data-stu-id="23d60-134">Select **Next**.</span></span>

1. <span data-ttu-id="23d60-135">Escolla o segmento que quere exportar.</span><span class="sxs-lookup"><span data-stu-id="23d60-135">Choose the segment that you want to export.</span></span> <span data-ttu-id="23d60-136">Neste exemplo, é **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="23d60-136">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Captura de pantalla da interface de usuario de selección de segmento co segmento ChurnProneCustomers seleccionado.":::

1. <span data-ttu-id="23d60-138">Seleccione **Gardar**.</span><span class="sxs-lookup"><span data-stu-id="23d60-138">Select **Save**.</span></span>

<span data-ttu-id="23d60-139">Despois de gardar o destino da exportación, atoparao en **Administrador** > **Exportacións** > **Os meus destinos de exportación**.</span><span class="sxs-lookup"><span data-stu-id="23d60-139">After saving the export destination, you find it on **Admin** > **Exports** > **My export destinations**.</span></span>

:::image type="content" source="media/export-destination-azure-blob-storage.png" alt-text="Captura de pantalla coa lista de exportacións e segmento de mostra resaltado.":::

<span data-ttu-id="23d60-141">Xa pode [exportar o segmento baixo demanda](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="23d60-141">You can now [export the segment on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="23d60-142">A exportación tamén se executará con todas as [actualizacións programadas](system.md).</span><span class="sxs-lookup"><span data-stu-id="23d60-142">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="23d60-143">Asegúrese de que o número de rexistros do segmento exportado estea dentro do límite permitido da súa licenza de Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="23d60-143">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="23d60-144">Os datos exportados almacénanse no contedor de almacenamento de Azure Blob que configurou anteriormente.</span><span class="sxs-lookup"><span data-stu-id="23d60-144">Exported data is stored in the Azure Blob storage container you configured above.</span></span> <span data-ttu-id="23d60-145">A seguinte ruta de cartafol créase automaticamente no seu contedor:</span><span class="sxs-lookup"><span data-stu-id="23d60-145">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="23d60-146">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span><span class="sxs-lookup"><span data-stu-id="23d60-146">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span></span>

<span data-ttu-id="23d60-147">Exemplo: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span><span class="sxs-lookup"><span data-stu-id="23d60-147">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span></span>

<span data-ttu-id="23d60-148">O *model.json* das entidades exportadas reside a nivel de *%ExportDestinationName%*.</span><span class="sxs-lookup"><span data-stu-id="23d60-148">The *model.json* for the exported entities resides at the *%ExportDestinationName%* level.</span></span>

<span data-ttu-id="23d60-149">Exemplo: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span><span class="sxs-lookup"><span data-stu-id="23d60-149">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span></span>

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a><span data-ttu-id="23d60-150">Definir o Experience Data Model (XDM) na Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="23d60-150">Define Experience Data Model (XDM) in Adobe Experience Platform</span></span>

<span data-ttu-id="23d60-151">Para poder usar os datos exportados de estatísticas de audiencia na Adobe Experience Platform, debemos definir o esquema do Experience Data Model e [configurar os datos para o perfil de cliente en tempo real](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span><span class="sxs-lookup"><span data-stu-id="23d60-151">Before the exported data from audience insights can be used within Adobe Experience Platform, we need to define the Experience Data Model schema and [configure the data for the Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span></span>

<span data-ttu-id="23d60-152">Aprenda [que é XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) e os [conceptos básicos da composición do esquema](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span><span class="sxs-lookup"><span data-stu-id="23d60-152">Learn [what XDM is](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) and understand the [basics of schema composition](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span></span>

## <a name="import-data-into-adobe-experience-platform"></a><span data-ttu-id="23d60-153">Importar datos a Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="23d60-153">Import data into Adobe Experience Platform</span></span>

<span data-ttu-id="23d60-154">Agora que todo está no seu lugar, necesitamos importar os datos de audiencia preparados da información da audiencia á Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="23d60-154">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Experience Platform.</span></span>

<span data-ttu-id="23d60-155">En primeiro lugar, [cree unha conexión de orixe de Azure Blob Storage](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span><span class="sxs-lookup"><span data-stu-id="23d60-155">First, [create an Azure Blob Storage source connection](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span></span>    

<span data-ttu-id="23d60-156">Despois de definir a conexión de orixe, [configure un fluxo de datos](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) para que unha conexión por lotes de almacenamento na nube importe a saída do segmento de información de audiencia a Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="23d60-156">After defining the source connection, [configure a dataflow](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) for a cloud storage batch connection to import the segment output from audience insights into Adobe Experience Platform.</span></span>

## <a name="create-an-audience-in-adobe-campaign-standard"></a><span data-ttu-id="23d60-157">Crear un público en Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="23d60-157">Create an audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="23d60-158">Para enviar o correo electrónico desta campaña, usaremos Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="23d60-158">To send the email for this campaign, we will use Adobe Campaign Standard.</span></span> <span data-ttu-id="23d60-159">Despois de importar os datos a Adobe Experience Platform, necesitamos [crear un público](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) en Adobe Campaign Standard empregando os datos da Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="23d60-159">After importing the data into Adobe Experience Platform, we need to [create an audience](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) in Adobe Campaign Standard using the data in Adobe Experience Platform.</span></span>

<span data-ttu-id="23d60-160">Aprenda a [usar o creador de segmentos](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) en Adobe Campaign Standard para definir un público baseado nos datos da Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="23d60-160">Learn how to [use segment builder](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) in Adobe Campaign Standard to define an audience based on the data in Adobe Experience Platform.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="23d60-161">Crear e enviar o correo electrónico usando Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="23d60-161">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="23d60-162">Cree o contido do correo electrónico e logo [probe e envíe](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) o seu correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="23d60-162">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Mostra de correo electrónico con oferta de renovación de Adobe Campaign Standard.":::