---
title: Exportar datos de Customer Insights a Adobe Campaign Standard
description: Coñeza como usar segmentos de información de público en Adobe Campaign Standard.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: b6c010d84119c2fa8b3ef99017c65f9939bf28c4
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760279"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a><span data-ttu-id="05011-103">Utilice segmentos de Customer Insights en Adobe Campaign Standard (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="05011-103">Use Customer Insights segments in Adobe Campaign Standard (preview)</span></span>

<span data-ttu-id="05011-104">Como usuario Insights for Dynamics 365 Customer Insights de audiencia é posible que crease segmentos para facer máis eficientes as súas campañas de márketing dirixíndose a públicos relevantes.</span><span class="sxs-lookup"><span data-stu-id="05011-104">As a user of audience insights for Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="05011-105">Para usar un segmento de información de audiencia en Adobe Experience Platform e aplicacións como Adobe Campaign Standard, cómpre seguir algúns pasos descritos neste artigo.</span><span class="sxs-lookup"><span data-stu-id="05011-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/ACS-flow.png" alt-text="Diagrama de proceso dos pasos descritos neste artigo.":::

## <a name="prerequisites"></a><span data-ttu-id="05011-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="05011-107">Prerequisites</span></span>

-   <span data-ttu-id="05011-108">LIcenza de Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="05011-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="05011-109">Licenza de Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="05011-109">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="05011-110">Conta de Azure Blob Storage</span><span class="sxs-lookup"><span data-stu-id="05011-110">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="05011-111">Visión xeral da campaña</span><span class="sxs-lookup"><span data-stu-id="05011-111">Campaign Overview</span></span>

<span data-ttu-id="05011-112">Para comprender mellor como pode usar segmentos de información do público en Adobe Experience Platform, vexamos unha mostra de campaña ficticia.</span><span class="sxs-lookup"><span data-stu-id="05011-112">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="05011-113">Supoñamos que a súa empresa ofrece un servizo mensual baseado na subscrición aos seus clientes nos Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="05011-113">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="05011-114">Identifique os clientes cuxas subscricións deben renovarse nos próximos oito días pero aínda non renovaron a súa subscrición.</span><span class="sxs-lookup"><span data-stu-id="05011-114">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="05011-115">Para manter estes clientes, pode enviarlles unha oferta promocional por correo electrónico mediante Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="05011-115">To keep these customers, you want to send them a promotional offer via email, using Adobe Campaign Standard.</span></span>

<span data-ttu-id="05011-116">Neste exemplo, debemos executar a campaña de correo electrónico promocional unha vez.</span><span class="sxs-lookup"><span data-stu-id="05011-116">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="05011-117">Este artigo non cubre o caso de uso de realizar a campaña máis dunha vez.</span><span class="sxs-lookup"><span data-stu-id="05011-117">This article doesn’t cover the use-case of running the campaign more than once.</span></span> <span data-ttu-id="05011-118">Non obstante, a información do público e Adobe Campaign Standard pódense configurar para que funcionen tamén nun escenario de campaña periódica.</span><span class="sxs-lookup"><span data-stu-id="05011-118">However, audience insights and Adobe Campaign Standard can be configured to work for a recurring campaign scenario too.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="05011-119">Identificar o seu público obxectivo</span><span class="sxs-lookup"><span data-stu-id="05011-119">Identify your target audience</span></span>

<span data-ttu-id="05011-120">No noso escenario, supoñemos que os enderezos de correo electrónico dos clientes están dispoñibles en información de audiencia e as súas preferencias promocionais analizáronse para identificar os membros do segmento.</span><span class="sxs-lookup"><span data-stu-id="05011-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="05011-121">O [segmento que definiu nas estatísticas do público](segments.md) chámase **ChurnProneCustomers** e planea enviar a estes clientes a promoción por correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="05011-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Captura de pantalla da páxina de segmentos co segmento ChurnProneCustomers creado.":::

<span data-ttu-id="05011-123">O correo electrónico de oferta que desexa enviar conterá o nome, apelidos e a data de finalización da subscrición do cliente.</span><span class="sxs-lookup"><span data-stu-id="05011-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="05011-124">Informa aos clientes sobre o desconto que obterán se renovan a subscrición antes de que remate.</span><span class="sxs-lookup"><span data-stu-id="05011-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="05011-125">Exportar o seu público obxectivo</span><span class="sxs-lookup"><span data-stu-id="05011-125">Export your target audience</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="05011-126">Configurar unha conexión</span><span class="sxs-lookup"><span data-stu-id="05011-126">Configure a connection</span></span>

<span data-ttu-id="05011-127">Co noso público obxectivo identificado, podemos configurar a exportación desde a información de audiencia a unha conta de Azure Blob Storage.</span><span class="sxs-lookup"><span data-stu-id="05011-127">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

1. <span data-ttu-id="05011-128">Na información do público, vaia a **Administrar** > **Conexións**.</span><span class="sxs-lookup"><span data-stu-id="05011-128">In audience insights, go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="05011-129">Seleccione **Engadir conexión** e elixa **Adobe Campaign** para configurar a conexión ou seleccione **Configurar** no mosaico **Adobe Campaign**</span><span class="sxs-lookup"><span data-stu-id="05011-129">Select **Add connection** and choose **Adobe Campaign** to configure the connection or select **Set up** in the **Adobe Campaign** tile</span></span>

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Mosaico de configuración para Adobe Campaign Standard.":::

1. <span data-ttu-id="05011-131">Déalle á conexión un nome recoñecible no campo **Nome para mostrar**.</span><span class="sxs-lookup"><span data-stu-id="05011-131">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="05011-132">O nome e o tipo de conexión describen esta conexión.</span><span class="sxs-lookup"><span data-stu-id="05011-132">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="05011-133">Recomendamos escoller un nome que explique o propósito e o destino da conexión.</span><span class="sxs-lookup"><span data-stu-id="05011-133">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="05011-134">Escolla quen pode usar esta conexión.</span><span class="sxs-lookup"><span data-stu-id="05011-134">Choose who can use this connection.</span></span> <span data-ttu-id="05011-135">Se non realiza ningunha acción, o valor predeterminado será Administradores.</span><span class="sxs-lookup"><span data-stu-id="05011-135">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="05011-136">Para obter máis información, consulte [Permisos necesarios para configurar unha exportación](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="05011-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="05011-137">Insira o **Nome da conta**, a **Clave da conta** e o **Envase** da conta de Azure Blob Storage a onde desexa exportar o segmento.</span><span class="sxs-lookup"><span data-stu-id="05011-137">Enter the **Account name**, **Account key**, and **Container** of the Azure Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Captura de pantalla da configuración da conta de almacenamento. "::: 

   - <span data-ttu-id="05011-139">Para obter máis información sobre como atopar o nome da conta de almacenamento BLOB de Azure e a clave da conta, consulte [Xestionar a configuración da conta de almacenamento no portal de Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="05011-139">To learn more about how to find the Azure Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

   - <span data-ttu-id="05011-140">Para obter máis información acerca de como crear un contedor, consulte [Crear un contedor](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="05011-140">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="05011-141">Seleccione **Gardar** para completar a conexión.</span><span class="sxs-lookup"><span data-stu-id="05011-141">Select **Save** to complete the connection.</span></span>

### <a name="configure-an-export"></a><span data-ttu-id="05011-142">Configurar unha exportación</span><span class="sxs-lookup"><span data-stu-id="05011-142">Configure an export</span></span>

<span data-ttu-id="05011-143">Pode configurar esta exportación se ten acceso a unha conexión deste tipo.</span><span class="sxs-lookup"><span data-stu-id="05011-143">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="05011-144">Para obter máis información, consulte [Permisos necesarios para configurar unha exportación](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="05011-144">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="05011-145">Vaia a **Datos** > **Exportacións**.</span><span class="sxs-lookup"><span data-stu-id="05011-145">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="05011-146">Seleccione **Engadir exportación** para crear unha nova exportación.</span><span class="sxs-lookup"><span data-stu-id="05011-146">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="05011-147">No campo **Conexión da exportación** escolla unha conexión da sección Adobe Campaign.</span><span class="sxs-lookup"><span data-stu-id="05011-147">In the **Connection for export** field, choose a connection from the Adobe Campaign section.</span></span> <span data-ttu-id="05011-148">Se non ve o nome desta sección, non hai conexións deste tipo dispoñibles para vostede.</span><span class="sxs-lookup"><span data-stu-id="05011-148">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="05011-149">Escolla o segmento que quere exportar.</span><span class="sxs-lookup"><span data-stu-id="05011-149">Choose the segment that you want to export.</span></span> <span data-ttu-id="05011-150">Neste exemplo, é **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="05011-150">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Captura de pantalla da interface de usuario de selección de segmento co segmento ChurnProneCustomers seleccionado.":::

1. <span data-ttu-id="05011-152">Seleccione **Seguinte**.</span><span class="sxs-lookup"><span data-stu-id="05011-152">Select **Next**.</span></span>

1. <span data-ttu-id="05011-153">Agora asignamos os campos **Orixe** do segmento de información do público aos nomes do campo **Obxectivo** no esquema de perfil Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="05011-153">Now we map the **Source** fields from the audience insights segment to the **Target** field names in the Adobe Campaign Standard profile schema.</span></span>

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Asignación de campo para o conector Adobe Campaign Standard.":::

   <span data-ttu-id="05011-155">Se desexa engadir máis atributos, seleccione **Engadir atributo**.</span><span class="sxs-lookup"><span data-stu-id="05011-155">If you want to add more attributes, select **Add attribute**.</span></span> <span data-ttu-id="05011-156">O nome de destino pode ser diferente do nome do campo de orixe, de xeito que aínda pode asignar a saída de segmentos de información de audiencia a Adobe Campaign Standard se os campos non teñen o mesmo nome nos dous sistemas.</span><span class="sxs-lookup"><span data-stu-id="05011-156">The target name can be different from the source field name so you can still map segment output from audience insights to Adobe Campaign Standard if the fields don’t have the same name in the two systems.</span></span>

   > [!NOTE]
   > <span data-ttu-id="05011-157">O enderezo de correo electrónico úsase como campo de identidade, pero pode usar calquera outro identificador do perfil de cliente de información de público para asignar datos a Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="05011-157">Email address is used as an identity field but you can use any other identifier from your audience insights customer profile to map data to Adobe Campaign Standard.</span></span>

1. <span data-ttu-id="05011-158">Seleccione **Gardar**.</span><span class="sxs-lookup"><span data-stu-id="05011-158">Select **Save**.</span></span>

<span data-ttu-id="05011-159">Despois de gardar o destino de exportación, atoparao en **Datos** > **Exportacións**.</span><span class="sxs-lookup"><span data-stu-id="05011-159">After saving the export destination, you find it on **Data** > **Exports**.</span></span>

<span data-ttu-id="05011-160">Xa pode [exportar o segmento baixo demanda](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="05011-160">You can now [export the segment on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="05011-161">A exportación tamén se executará con todas as [actualizacións programadas](system.md).</span><span class="sxs-lookup"><span data-stu-id="05011-161">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="05011-162">Asegúrese de que o número de rexistros do segmento exportado estea dentro do límite permitido da súa licenza de Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="05011-162">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="05011-163">Os datos exportados almacénanse no contedor de almacenamento de Azure Blob que configurou anteriormente.</span><span class="sxs-lookup"><span data-stu-id="05011-163">Exported data is stored in the Azure Blob storage container you configured above.</span></span> <span data-ttu-id="05011-164">A seguinte ruta de cartafol créase automaticamente no seu contedor:</span><span class="sxs-lookup"><span data-stu-id="05011-164">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="05011-165">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span><span class="sxs-lookup"><span data-stu-id="05011-165">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span></span>

<span data-ttu-id="05011-166">Exemplo: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span><span class="sxs-lookup"><span data-stu-id="05011-166">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span></span>

## <a name="configure-adobe-campaign-standard"></a><span data-ttu-id="05011-167">Configurar Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="05011-167">Configure Adobe Campaign Standard</span></span>

<span data-ttu-id="05011-168">Cando se exporta un segmento de información de audiencia, contén as columnas que seleccionou ao definir o destino da exportación no paso anterior.</span><span class="sxs-lookup"><span data-stu-id="05011-168">When a segment from audience insights is exported, it contains the columns you selected while defining the export destination in the previous step.</span></span> <span data-ttu-id="05011-169">Estes datos pódense empregar para [crear perfís en Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span><span class="sxs-lookup"><span data-stu-id="05011-169">This data can be used to [create profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span></span>

<span data-ttu-id="05011-170">Para usar o segmento en Adobe Campaign Standard, necesitamos ampliar o esquema de perfís en Adobe Campaign Standard para incluír dous campos adicionais.</span><span class="sxs-lookup"><span data-stu-id="05011-170">To use the segment in Adobe Campaign Standard, we need to extend the profile schema in Adobe Campaign Standard to include two additional fields.</span></span> <span data-ttu-id="05011-171">Aprenda a [ampliar o recurso do perfil](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) con novos campos en Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="05011-171">Learn how to [extend the profile resource](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) with new fields in Adobe Campaign Standard.</span></span>

<span data-ttu-id="05011-172">No noso exemplo, estes campos son *Nome do segmento e data do segmento (opcional).*</span><span class="sxs-lookup"><span data-stu-id="05011-172">In our example, these fields are *Segment Name and Segment Date (optional).*</span></span>

<span data-ttu-id="05011-173">Usaremos estes campos para identificar os perfís de Adobe Campaign Standard aos que queremos orientar esta campaña.</span><span class="sxs-lookup"><span data-stu-id="05011-173">We will use these fields to identify the profiles in Adobe Campaign Standard we want to target for this campaign.</span></span>

<span data-ttu-id="05011-174">Se non hai outros rexistros en Adobe Campaign Standard, ademais do que vai importar, pode omitir este paso.</span><span class="sxs-lookup"><span data-stu-id="05011-174">If there are no other records in Adobe Campaign Standard, other than what you are going to import, you can skip this step.</span></span>

## <a name="import-data-into-adobe-campaign-standard"></a><span data-ttu-id="05011-175">Importar datos a Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="05011-175">Import data into Adobe Campaign Standard</span></span>

<span data-ttu-id="05011-176">Agora que todo está no seu lugar, necesitamos importar os datos de audiencia preparados da información da audiencia a Adobe Campaign Standard para crear perfís.</span><span class="sxs-lookup"><span data-stu-id="05011-176">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Campaign Standard to create profiles.</span></span> <span data-ttu-id="05011-177">Aprenda [como importar perfís en Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) usando un fluxo de traballo.</span><span class="sxs-lookup"><span data-stu-id="05011-177">Learn [how to import profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) using a workflow.</span></span>

<span data-ttu-id="05011-178">O fluxo de traballo de importación da seguinte imaxe configurouse para executarse cada 8 horas e busca segmentos de información de audiencia exportados (ficheiro .csv en Azure Blob Storage).</span><span class="sxs-lookup"><span data-stu-id="05011-178">The import workflow in the image below has been configured to run every 8 hours and looks for exported audience insights segments (.csv file in Azure Blob Storage).</span></span> <span data-ttu-id="05011-179">O fluxo de traballo extrae o contido do ficheiro .csv nunha orde de columna especificada.</span><span class="sxs-lookup"><span data-stu-id="05011-179">The workflow extracts the .csv file content in a specified column order.</span></span> <span data-ttu-id="05011-180">Este fluxo de traballo creouse para realizar un tratamento básico de erros e garantir que cada rexistro teña un enderezo de correo electrónico antes de hidratar os datos en Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="05011-180">This workflow has been built to perform basic error handling and ensure that each record has an email address before hydrating the data in Adobe Campaign Standard.</span></span> <span data-ttu-id="05011-181">O fluxo de traballo tamén extrae o nome do segmento do nome do ficheiro antes de introducilo nos datos do perfil de ACS.</span><span class="sxs-lookup"><span data-stu-id="05011-181">The workflow also extracts the segment name from the filename before upserting into ACS Profile data.</span></span>

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Captura de pantalla dun fluxo de traballo de importación na interface de usuario de Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a><span data-ttu-id="05011-183">Recuperar o público en Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="05011-183">Retrieve the audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="05011-184">Unha vez importados os datos a Adobe Campaign Standard, [pode crear un fluxo de traballo](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) e [consultar](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) os clientes en función do *Nome do segmento* e a *Data do segmento* para seleccionar os perfís identificados para a nosa campaña de mostra.</span><span class="sxs-lookup"><span data-stu-id="05011-184">Once the data is imported into Adobe Campaign Standard, you [can create a workflow](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) and [query](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) the customers based on the *Segment Name* and *Segment Date* to select profiles that were identified for our sample campaign.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="05011-185">Crear e enviar o correo electrónico usando Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="05011-185">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="05011-186">Cree o contido do correo electrónico e logo [probe e envíe](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) o seu correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="05011-186">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Mostra de correo electrónico con oferta de renovación de Adobe Campaign Standard.":::
