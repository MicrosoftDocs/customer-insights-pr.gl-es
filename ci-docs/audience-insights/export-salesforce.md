---
title: Exportar datos de Customer Insights a Salesforce Marketing Cloud
description: Aprenda a configurar a conexión e exportar a Salesforce Marketing Cloud.
ms.date: 06/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 123f8b2dbb6140785dec6c1b4164d2f513f66a53
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314609"
---
# <a name="export-segments-and-other-data-to-salesforce-marketing-cloud-preview"></a><span data-ttu-id="81230-103">Exportar segmentos e outros datos a Salesforce Marketing Cloud (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="81230-103">Export segments and other data to Salesforce Marketing Cloud (preview)</span></span>

<span data-ttu-id="81230-104">Use os datos dos seus clientes en Salesforce Marketing Cloud exportándoos a través dunha localización de protocolo de transferencia de ficheiros seguro (SFTP).</span><span class="sxs-lookup"><span data-stu-id="81230-104">Use your customer data in Salesforce Marketing Cloud by exporting them through a Secure File Transfer Protocol (SFTP) location.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="81230-105">Requisitos previos para a conexión</span><span class="sxs-lookup"><span data-stu-id="81230-105">Prerequisites for connection</span></span>

- <span data-ttu-id="81230-106">Dispoñibilidade dun servidor SFTP e as correspondentes credenciais de administrador.</span><span class="sxs-lookup"><span data-stu-id="81230-106">Availability of an SFTP host and corresponding admin credentials.</span></span> [<span data-ttu-id="81230-107">Como configurar localizacións SFTP para Salesforce Marketing Cloud</span><span class="sxs-lookup"><span data-stu-id="81230-107">How to setup SFTP locations for Salesforce Marketing Cloud</span></span>](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) 

## <a name="known-limitations"></a><span data-ttu-id="81230-108">Limitacións coñecidas</span><span class="sxs-lookup"><span data-stu-id="81230-108">Known limitations</span></span>

- <span data-ttu-id="81230-109">O tempo de execución dunha exportación depende do rendemento do seu sistema.</span><span class="sxs-lookup"><span data-stu-id="81230-109">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="81230-110">Recomendamos dous núcleos de CPU e 1 Gb de memoria como configuración mínima do seu servidor.</span><span class="sxs-lookup"><span data-stu-id="81230-110">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="81230-111">As entidades exportadoras con ata 100 millóns de perfís de clientes poden levar 90 minutos cando se usa a configuración mínima recomendada.</span><span class="sxs-lookup"><span data-stu-id="81230-111">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration.</span></span> 

## <a name="set-up-the-connection-to-salesforce-marketing-cloud"></a><span data-ttu-id="81230-112">Configurar a conexión a Salesforce Marketing Cloud</span><span class="sxs-lookup"><span data-stu-id="81230-112">Set up the connection to Salesforce Marketing Cloud</span></span>

1. <span data-ttu-id="81230-113">Vaia a **Administrar** > **Conexións**.</span><span class="sxs-lookup"><span data-stu-id="81230-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="81230-114">Seleccione **Engadir conexión** e elixa **Salesforce Marketing Cloud** para configurar a conexión.</span><span class="sxs-lookup"><span data-stu-id="81230-114">Select **Add connection** and choose **Salesforce Marketing Cloud** to configure the connection.</span></span>

1. <span data-ttu-id="81230-115">Déalle á conexión un nome recoñecible no campo **Nome para mostrar**.</span><span class="sxs-lookup"><span data-stu-id="81230-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="81230-116">O nome e o tipo de conexión describen esta conexión.</span><span class="sxs-lookup"><span data-stu-id="81230-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="81230-117">Recomendamos escoller un nome que explique o propósito e o destino da conexión.</span><span class="sxs-lookup"><span data-stu-id="81230-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="81230-118">Escolla quen pode usar esta conexión.</span><span class="sxs-lookup"><span data-stu-id="81230-118">Choose who can use this connection.</span></span> <span data-ttu-id="81230-119">Se non realiza ningunha acción, o valor predeterminado será Administradores.</span><span class="sxs-lookup"><span data-stu-id="81230-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="81230-120">Para obter máis información, consulte [Permitir aos colaboradores usar unha conexión para as exportacións](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="81230-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="81230-121">Proporcione un **Nome de usuario**, **Contrasinal**, **Nome de servidor** e **Cartafol de exportación** para a súa conta de SFTP.</span><span class="sxs-lookup"><span data-stu-id="81230-121">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="81230-122">Seleccionar **Verificar** para probar a conexión.</span><span class="sxs-lookup"><span data-stu-id="81230-122">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="81230-123">Seleccione **Estou de acordo** para confirmar a **Privacidade e cumprimento dos datos**.</span><span class="sxs-lookup"><span data-stu-id="81230-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="81230-124">Seleccione **Gardar** para completar a conexión.</span><span class="sxs-lookup"><span data-stu-id="81230-124">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="81230-125">Configurar unha exportación</span><span class="sxs-lookup"><span data-stu-id="81230-125">Configure an export</span></span>

<span data-ttu-id="81230-126">Pode configurar esta exportación se ten acceso a unha conexión deste tipo.</span><span class="sxs-lookup"><span data-stu-id="81230-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="81230-127">Para obter máis información, consulte [Permisos necesarios para configurar unha exportación](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="81230-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="81230-128">Vaia a **Datos** > **Exportacións**.</span><span class="sxs-lookup"><span data-stu-id="81230-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="81230-129">Seleccione **Engadir destino** para crear unha nova exportación.</span><span class="sxs-lookup"><span data-stu-id="81230-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="81230-130">No campo **Conexión da exportación** escolla unha conexión da sección SFTP.</span><span class="sxs-lookup"><span data-stu-id="81230-130">In the **Connection for export** field, choose a connection from the SFTP section.</span></span> <span data-ttu-id="81230-131">Se non ve o nome desta sección, non hai conexións deste tipo dispoñibles para vostede.</span><span class="sxs-lookup"><span data-stu-id="81230-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="81230-132">Escolla se desexa exportar os seus datos **Comprimidos con gzip** ou **Descomprimidos** e o **delimitador de campo** dos ficheiros exportados.</span><span class="sxs-lookup"><span data-stu-id="81230-132">Choose if you want to export your data **Gzipped** or **Unzipped** and the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="81230-133">Seleccione as entidades, por exemplo, segmentos que desexa exportar.</span><span class="sxs-lookup"><span data-stu-id="81230-133">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="81230-134">Cada entidade seleccionada dividirase en ata cinco ficheiros de saída cando se exporte.</span><span class="sxs-lookup"><span data-stu-id="81230-134">Each selected entity will be split up into up to five output files when exported.</span></span> 

1. <span data-ttu-id="81230-135">Seleccione **Gardar**.</span><span class="sxs-lookup"><span data-stu-id="81230-135">Select **Save**.</span></span>

<span data-ttu-id="81230-136">Ao gardar unha exportación non se executa a exportación inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="81230-136">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="81230-137">A exportación execútase con cada [actualización programada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="81230-137">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="81230-138">Tamén pode [exportar datos baixo demanda](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="81230-138">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a><span data-ttu-id="81230-139">Importar datos de Customer Insights da localización SFTP a Salesforce Marketing Cloud</span><span class="sxs-lookup"><span data-stu-id="81230-139">Import Customer Insights data from SFTP location to Salesforce Marketing Cloud</span></span>

1. <span data-ttu-id="81230-140">Cree [extensións de datos en Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) para importar o ficheiro de datos de Customer Insights desde a localización SFTP.</span><span class="sxs-lookup"><span data-stu-id="81230-140">Create [data extensions in Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) to import the Customer Insights data file from the SFTP location.</span></span>

2. <span data-ttu-id="81230-141">[Importe os datos desde a localización SFTP](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) na extensión de datos de Salesforce Marketing Cloud.</span><span class="sxs-lookup"><span data-stu-id="81230-141">[Import the data from the SFTP location](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) into the Salesforce Marketing Cloud data extension.</span></span> 

3. <span data-ttu-id="81230-142">Configure a automatización para importar os datos ás extensións de datos.</span><span class="sxs-lookup"><span data-stu-id="81230-142">Set up the automation to import the data into the data extensions.</span></span> <span data-ttu-id="81230-143">Máis información sobre as [automatizacións ao soltar ficheiros e as automatizacións programadas](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).</span><span class="sxs-lookup"><span data-stu-id="81230-143">Learn more about [file drop automations and scheduled automations](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).</span></span>

   <span data-ttu-id="81230-144">Defina unha [automatización ao soltar ficheiros](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) ou unha [automatización programada](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).</span><span class="sxs-lookup"><span data-stu-id="81230-144">Define a [file drop automation](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) or a  [scheduled automation](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).</span></span> 

<span data-ttu-id="81230-145">Aquí ten un exemplo dunha [automatización con SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).</span><span class="sxs-lookup"><span data-stu-id="81230-145">Here's an example of [an automation with SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="81230-146">Cumprimento e privacidade dos datos</span><span class="sxs-lookup"><span data-stu-id="81230-146">Data privacy and compliance</span></span>

<span data-ttu-id="81230-147">Cando habilita Dynamics 365 Customer Insights para transmitir datos a SFTP, permite a transferencia de datos fóra do límite de cumprimento de Dynamics 365 Customer Insights, incluíndo datos potencialmente confidenciais como os datos persoais.</span><span class="sxs-lookup"><span data-stu-id="81230-147">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="81230-148">Microsoft transferirá estes datos segundo a súa instrución, pero vostede é responsable de garantir que o destino de exportación cumpra as obrigas de privacidade ou seguridade que poida ter.</span><span class="sxs-lookup"><span data-stu-id="81230-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="81230-149">Para obter máis información, consulte a [Declaración de privacidade de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="81230-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="81230-150">O administrador de Dynamics 365 Customer Insights pode eliminar este destino de exportación en calquera momento para interromper o uso desta funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="81230-150">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
