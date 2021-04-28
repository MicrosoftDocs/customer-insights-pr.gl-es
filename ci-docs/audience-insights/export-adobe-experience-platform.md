---
title: Exportar datos de Customer Insights á plataforma Adobe Experience
description: Coñeza como usar segmentos de información de público na Adobe Experience Platform.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 884f4d30f354bed29909d57be84dce4c8e46965a
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760099"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a><span data-ttu-id="c51d7-103">Utilice segmentos de Customer Insights na Adobe Experience Platform (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="c51d7-103">Use Customer Insights segments in Adobe Experience Platform (preview)</span></span>

<span data-ttu-id="c51d7-104">Como usuario Insights for Dynamics 365 Customer Insights de audiencia é posible que crease segmentos para facer máis eficientes as súas campañas de márketing dirixíndose a públicos relevantes.</span><span class="sxs-lookup"><span data-stu-id="c51d7-104">As a user of audience insights for Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="c51d7-105">Para usar un segmento de información de audiencia en Adobe Experience Platform e aplicacións como Adobe Campaign Standard, cómpre seguir algúns pasos descritos neste artigo.</span><span class="sxs-lookup"><span data-stu-id="c51d7-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/AEP-flow.png" alt-text="Diagrama de proceso dos pasos descritos neste artigo.":::

## <a name="prerequisites"></a><span data-ttu-id="c51d7-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="c51d7-107">Prerequisites</span></span>

-   <span data-ttu-id="c51d7-108">LIcenza de Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="c51d7-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="c51d7-109">Licenza de Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="c51d7-109">Adobe Experience Platform license</span></span>
-   <span data-ttu-id="c51d7-110">Licenza de Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="c51d7-110">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="c51d7-111">Conta de Azure Blob Storage</span><span class="sxs-lookup"><span data-stu-id="c51d7-111">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="c51d7-112">Visión xeral da campaña</span><span class="sxs-lookup"><span data-stu-id="c51d7-112">Campaign Overview</span></span>

<span data-ttu-id="c51d7-113">Para comprender mellor como pode usar segmentos de información do público en Adobe Experience Platform, vexamos unha mostra de campaña ficticia.</span><span class="sxs-lookup"><span data-stu-id="c51d7-113">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="c51d7-114">Supoñamos que a súa empresa ofrece un servizo mensual baseado na subscrición aos seus clientes nos Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="c51d7-114">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="c51d7-115">Identifique os clientes cuxas subscricións deben renovarse nos próximos oito días pero aínda non renovaron a súa subscrición.</span><span class="sxs-lookup"><span data-stu-id="c51d7-115">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="c51d7-116">Para manter estes clientes, pode enviarlles unha oferta promocional por correo electrónico mediante a Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="c51d7-116">To keep these customers, you want to send them a promotional offer via email, using Adobe Experience Platform.</span></span>

<span data-ttu-id="c51d7-117">Neste exemplo, debemos executar a campaña de correo electrónico promocional unha vez.</span><span class="sxs-lookup"><span data-stu-id="c51d7-117">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="c51d7-118">Este artigo non cubre o caso de uso de realizar a campaña máis dunha vez.</span><span class="sxs-lookup"><span data-stu-id="c51d7-118">This article doesn’t cover the use-case of running the campaign more than once.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="c51d7-119">Identificar o seu público obxectivo</span><span class="sxs-lookup"><span data-stu-id="c51d7-119">Identify your target audience</span></span>

<span data-ttu-id="c51d7-120">No noso escenario, supoñemos que os enderezos de correo electrónico dos clientes están dispoñibles en información de audiencia e as súas preferencias promocionais analizáronse para identificar os membros do segmento.</span><span class="sxs-lookup"><span data-stu-id="c51d7-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="c51d7-121">O [segmento que definiu nas estatísticas do público](segments.md) chámase **ChurnProneCustomers** e planea enviar a estes clientes a promoción por correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="c51d7-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Captura de pantalla da páxina de segmentos co segmento ChurnProneCustomers creado.":::

<span data-ttu-id="c51d7-123">O correo electrónico de oferta que desexa enviar conterá o nome, apelidos e a data de finalización da subscrición do cliente.</span><span class="sxs-lookup"><span data-stu-id="c51d7-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="c51d7-124">Informa aos clientes sobre o desconto que obterán se renovan a subscrición antes de que remate.</span><span class="sxs-lookup"><span data-stu-id="c51d7-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="c51d7-125">Exportar o seu público obxectivo</span><span class="sxs-lookup"><span data-stu-id="c51d7-125">Export your target audience</span></span>

<span data-ttu-id="c51d7-126">Co noso público obxectivo identificado, podemos configurar a exportación desde a información de audiencia a unha conta de Azure Blob Storage.</span><span class="sxs-lookup"><span data-stu-id="c51d7-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="c51d7-127">Configurar unha conexión</span><span class="sxs-lookup"><span data-stu-id="c51d7-127">Configure a connection</span></span>

1. <span data-ttu-id="c51d7-128">Vaia a **Administrar** > **Conexións**.</span><span class="sxs-lookup"><span data-stu-id="c51d7-128">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="c51d7-129">Seleccione **Engadir conexión** e elixa **Azure Blob Storage** ou seleccione **Configurar** no mosaico **Azure Blob Storage**:</span><span class="sxs-lookup"><span data-stu-id="c51d7-129">Select **Add connection** and choose **Azure Blob Storage** or select **Set up** in the **Azure Blob Storage** tile:</span></span>

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Mosaico de configuración para Azure Blob Storage."::: <span data-ttu-id="c51d7-131">para configurar a conexión.</span><span class="sxs-lookup"><span data-stu-id="c51d7-131">to configure the connection.</span></span>

1. <span data-ttu-id="c51d7-132">Déalle á conexión un nome recoñecible no campo **Nome para mostrar**.</span><span class="sxs-lookup"><span data-stu-id="c51d7-132">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="c51d7-133">O nome e o tipo de conexión describen esta conexión.</span><span class="sxs-lookup"><span data-stu-id="c51d7-133">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="c51d7-134">Recomendamos escoller un nome que explique o propósito e o destino da conexión.</span><span class="sxs-lookup"><span data-stu-id="c51d7-134">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="c51d7-135">Escolla quen pode usar esta conexión.</span><span class="sxs-lookup"><span data-stu-id="c51d7-135">Choose who can use this connection.</span></span> <span data-ttu-id="c51d7-136">Se non realiza ningunha acción, o valor predeterminado será Administradores.</span><span class="sxs-lookup"><span data-stu-id="c51d7-136">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="c51d7-137">Para obter máis información, consulte [Permitir aos colaboradores usar unha conexión para as exportacións](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="c51d7-137">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="c51d7-138">Insira o **Nome da conta**, a **Clave da conta** e o **Envase** da súa conta de almacenamento de BLOB a onde desexa exportar o segmento.</span><span class="sxs-lookup"><span data-stu-id="c51d7-138">Enter **Account name**, **Account key**, and **Container** for your Blob storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Captura de pantalla da configuración da conta de almacenamento. "::: 
   
    - <span data-ttu-id="c51d7-140">Para obter máis información sobre como atopar o nome e a clave da conta de almacenamento de BLOB, consulte [Xestionar a configuración da conta de almacenamento no portal de Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="c51d7-140">To learn more about how to find the Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>
    - <span data-ttu-id="c51d7-141">Para obter máis información acerca de como crear un contedor, consulte [Crear un contedor](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="c51d7-141">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="c51d7-142">Seleccione **Gardar** para completar a conexión.</span><span class="sxs-lookup"><span data-stu-id="c51d7-142">Select **Save** to complete the connection.</span></span> 

### <a name="configure-an-export"></a><span data-ttu-id="c51d7-143">Configurar unha exportación</span><span class="sxs-lookup"><span data-stu-id="c51d7-143">Configure an export</span></span>

<span data-ttu-id="c51d7-144">Pode configurar esta exportación se ten acceso a unha conexión deste tipo.</span><span class="sxs-lookup"><span data-stu-id="c51d7-144">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="c51d7-145">Para obter máis información, consulte [Permisos necesarios para configurar unha exportación](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="c51d7-145">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="c51d7-146">Vaia a **Datos** > **Exportacións**.</span><span class="sxs-lookup"><span data-stu-id="c51d7-146">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="c51d7-147">Seleccione **Engadir exportación** para crear unha nova exportación.</span><span class="sxs-lookup"><span data-stu-id="c51d7-147">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="c51d7-148">No campo **Conexión da exportación** escolla unha conexión da sección Azure Blob Storage.</span><span class="sxs-lookup"><span data-stu-id="c51d7-148">In the **Connection for export** field, choose a connection from the Azure Blob Storage section.</span></span> <span data-ttu-id="c51d7-149">Se non ve o nome desta sección, non hai conexións deste tipo dispoñibles para vostede.</span><span class="sxs-lookup"><span data-stu-id="c51d7-149">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="c51d7-150">Escolla o segmento que quere exportar.</span><span class="sxs-lookup"><span data-stu-id="c51d7-150">Choose the segment that you want to export.</span></span> <span data-ttu-id="c51d7-151">Neste exemplo, é **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="c51d7-151">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Captura de pantalla da interface de usuario de selección de segmento co segmento ChurnProneCustomers seleccionado.":::

1. <span data-ttu-id="c51d7-153">Seleccione **Gardar**.</span><span class="sxs-lookup"><span data-stu-id="c51d7-153">Select **Save**.</span></span>

<span data-ttu-id="c51d7-154">Despois de gardar o destino de exportación, atoparao en **Datos** > **Exportacións**.</span><span class="sxs-lookup"><span data-stu-id="c51d7-154">After saving the export destination, you find it on **Data** > **Exports**.</span></span>

<span data-ttu-id="c51d7-155">Xa pode [exportar o segmento baixo demanda](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="c51d7-155">You can now [export the segment on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="c51d7-156">A exportación tamén se executará con todas as [actualizacións programadas](system.md).</span><span class="sxs-lookup"><span data-stu-id="c51d7-156">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="c51d7-157">Asegúrese de que o número de rexistros do segmento exportado estea dentro do límite permitido da súa licenza de Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="c51d7-157">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="c51d7-158">Os datos exportados almacénanse no contedor de almacenamento de Azure Blob que configurou anteriormente.</span><span class="sxs-lookup"><span data-stu-id="c51d7-158">Exported data is stored in the Azure Blob storage container you configured above.</span></span> <span data-ttu-id="c51d7-159">A seguinte ruta de cartafol créase automaticamente no seu contedor:</span><span class="sxs-lookup"><span data-stu-id="c51d7-159">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="c51d7-160">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span><span class="sxs-lookup"><span data-stu-id="c51d7-160">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span></span>

<span data-ttu-id="c51d7-161">Exemplo: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span><span class="sxs-lookup"><span data-stu-id="c51d7-161">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span></span>

<span data-ttu-id="c51d7-162">O *model.json* das entidades exportadas reside a nivel de *%ExportDestinationName%*.</span><span class="sxs-lookup"><span data-stu-id="c51d7-162">The *model.json* for the exported entities resides at the *%ExportDestinationName%* level.</span></span>

<span data-ttu-id="c51d7-163">Exemplo: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span><span class="sxs-lookup"><span data-stu-id="c51d7-163">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span></span>

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a><span data-ttu-id="c51d7-164">Definir o Experience Data Model (XDM) na Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="c51d7-164">Define Experience Data Model (XDM) in Adobe Experience Platform</span></span>

<span data-ttu-id="c51d7-165">Para poder usar os datos exportados de estatísticas de audiencia na Adobe Experience Platform, debemos definir o esquema do Experience Data Model e [configurar os datos para o perfil de cliente en tempo real](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span><span class="sxs-lookup"><span data-stu-id="c51d7-165">Before the exported data from audience insights can be used within Adobe Experience Platform, we need to define the Experience Data Model schema and [configure the data for the Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span></span>

<span data-ttu-id="c51d7-166">Aprenda [que é XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) e os [conceptos básicos da composición do esquema](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span><span class="sxs-lookup"><span data-stu-id="c51d7-166">Learn [what XDM is](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) and understand the [basics of schema composition](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span></span>

## <a name="import-data-into-adobe-experience-platform"></a><span data-ttu-id="c51d7-167">Importar datos a Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="c51d7-167">Import data into Adobe Experience Platform</span></span>

<span data-ttu-id="c51d7-168">Agora que todo está no seu lugar, necesitamos importar os datos de audiencia preparados da información da audiencia á Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="c51d7-168">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Experience Platform.</span></span>

<span data-ttu-id="c51d7-169">En primeiro lugar, [cree unha conexión de orixe de Azure Blob Storage](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span><span class="sxs-lookup"><span data-stu-id="c51d7-169">First, [create an Azure Blob Storage source connection](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span></span>    

<span data-ttu-id="c51d7-170">Despois de definir a conexión de orixe, [configure un fluxo de datos](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) para que unha conexión por lotes de almacenamento na nube importe a saída do segmento de información de audiencia a Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="c51d7-170">After defining the source connection, [configure a dataflow](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) for a cloud storage batch connection to import the segment output from audience insights into Adobe Experience Platform.</span></span>

## <a name="create-an-audience-in-adobe-campaign-standard"></a><span data-ttu-id="c51d7-171">Crear un público en Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="c51d7-171">Create an audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="c51d7-172">Para enviar o correo electrónico desta campaña, usaremos Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="c51d7-172">To send the email for this campaign, we will use Adobe Campaign Standard.</span></span> <span data-ttu-id="c51d7-173">Despois de importar os datos a Adobe Experience Platform, necesitamos [crear un público](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) en Adobe Campaign Standard empregando os datos da Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="c51d7-173">After importing the data into Adobe Experience Platform, we need to [create an audience](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) in Adobe Campaign Standard using the data in Adobe Experience Platform.</span></span>

<span data-ttu-id="c51d7-174">Aprenda a [usar o creador de segmentos](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) en Adobe Campaign Standard para definir un público baseado nos datos da Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="c51d7-174">Learn how to [use segment builder](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) in Adobe Campaign Standard to define an audience based on the data in Adobe Experience Platform.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="c51d7-175">Crear e enviar o correo electrónico usando Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="c51d7-175">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="c51d7-176">Cree o contido do correo electrónico e logo [probe e envíe](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) o seu correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="c51d7-176">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Mostra de correo electrónico con oferta de renovación de Adobe Campaign Standard.":::
