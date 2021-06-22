---
title: Exportar datos de Customer Insights a servidores SFTP
description: Aprenda a configurar a conexión e exportar a unha localización de SFTP.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 000b44dc8e5cc419132bd17e359fbdd5879caf1b
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124317"
---
# <a name="export-segments-and-other-data-to-sftp-preview"></a><span data-ttu-id="1f20f-103">Exportar segmentos e outros datos a SFTP (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="1f20f-103">Export segments and other data to SFTP (preview)</span></span>

<span data-ttu-id="1f20f-104">Use os datos dos seus clientes en aplicacións de terceiros exportándoos a unha localización do protocolo de transferencia de ficheiros segura (SFTP).</span><span class="sxs-lookup"><span data-stu-id="1f20f-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol (SFTP) location.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="1f20f-105">Requisitos previos para a conexión</span><span class="sxs-lookup"><span data-stu-id="1f20f-105">Prerequisites for connection</span></span>

- <span data-ttu-id="1f20f-106">Dispoñibilidade dun servidor SFTP e as credenciais correspondentes.</span><span class="sxs-lookup"><span data-stu-id="1f20f-106">Availability of an SFTP host and corresponding credentials.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="1f20f-107">Limitacións coñecidas</span><span class="sxs-lookup"><span data-stu-id="1f20f-107">Known limitations</span></span>

- <span data-ttu-id="1f20f-108">O tempo de execución dunha exportación depende do rendemento do seu sistema.</span><span class="sxs-lookup"><span data-stu-id="1f20f-108">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="1f20f-109">Recomendamos dous núcleos de CPU e 1 Gb de memoria como configuración mínima do seu servidor.</span><span class="sxs-lookup"><span data-stu-id="1f20f-109">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="1f20f-110">As entidades exportadoras con ata 100 millóns de perfís de clientes poden tardar 90 minutos cando se usa a configuración mínima recomendada de dous núcleos de CPU e 1 Gb de memoria.</span><span class="sxs-lookup"><span data-stu-id="1f20f-110">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration of two CPU cores and 1 Gb of memory.</span></span> 

## <a name="set-up-connection-to-sftp"></a><span data-ttu-id="1f20f-111">Configurar conexión a SFTP</span><span class="sxs-lookup"><span data-stu-id="1f20f-111">Set up connection to SFTP</span></span>

1. <span data-ttu-id="1f20f-112">Vaia a **Administrar** > **Conexións**.</span><span class="sxs-lookup"><span data-stu-id="1f20f-112">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="1f20f-113">Seleccione **Engadir conexión** e elixa **SFTP** para configurar a conexión.</span><span class="sxs-lookup"><span data-stu-id="1f20f-113">Select **Add connection** and choose **SFTP** to configure the connection.</span></span>

1. <span data-ttu-id="1f20f-114">Déalle á conexión un nome recoñecible no campo **Nome para mostrar**.</span><span class="sxs-lookup"><span data-stu-id="1f20f-114">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="1f20f-115">O nome e o tipo de conexión describen esta conexión.</span><span class="sxs-lookup"><span data-stu-id="1f20f-115">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="1f20f-116">Recomendamos escoller un nome que explique o propósito e o destino da conexión.</span><span class="sxs-lookup"><span data-stu-id="1f20f-116">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="1f20f-117">Escolla quen pode usar esta conexión.</span><span class="sxs-lookup"><span data-stu-id="1f20f-117">Choose who can use this connection.</span></span> <span data-ttu-id="1f20f-118">Se non realiza ningunha acción, o valor predeterminado será Administradores.</span><span class="sxs-lookup"><span data-stu-id="1f20f-118">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="1f20f-119">Para obter máis información, consulte [Permitir aos colaboradores usar unha conexión para as exportacións](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="1f20f-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="1f20f-120">Proporcione un **Nome de usuario**, **Contrasinal**, **Nome de servidor** e **Cartafol de exportación** para a súa conta de SFTP.</span><span class="sxs-lookup"><span data-stu-id="1f20f-120">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="1f20f-121">Seleccionar **Verificar** para probar a conexión.</span><span class="sxs-lookup"><span data-stu-id="1f20f-121">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="1f20f-122">Escolla se desexa exportar os seus datos **Comprimidos con gzip** ou **Descomprimidos** e o **delimitador de campo** dos ficheiros exportados.</span><span class="sxs-lookup"><span data-stu-id="1f20f-122">Choose if you want to export your data **Gzipped** or **Unzipped** and the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="1f20f-123">Seleccione **Estou de acordo** para confirmar a **Privacidade e cumprimento dos datos**.</span><span class="sxs-lookup"><span data-stu-id="1f20f-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="1f20f-124">Seleccione **Gardar** para completar a conexión.</span><span class="sxs-lookup"><span data-stu-id="1f20f-124">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="1f20f-125">Configurar unha exportación</span><span class="sxs-lookup"><span data-stu-id="1f20f-125">Configure an export</span></span>

<span data-ttu-id="1f20f-126">Pode configurar esta exportación se ten acceso a unha conexión deste tipo.</span><span class="sxs-lookup"><span data-stu-id="1f20f-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="1f20f-127">Para obter máis información, consulte [Permisos necesarios para configurar unha exportación](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="1f20f-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="1f20f-128">Vaia a **Datos** > **Exportacións**.</span><span class="sxs-lookup"><span data-stu-id="1f20f-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="1f20f-129">Seleccione **Engadir destino** para crear unha nova exportación.</span><span class="sxs-lookup"><span data-stu-id="1f20f-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="1f20f-130">No campo **Conexión da exportación** escolla unha conexión da sección SFTP.</span><span class="sxs-lookup"><span data-stu-id="1f20f-130">In the **Connection for export** field, choose a connection from the SFTP section.</span></span> <span data-ttu-id="1f20f-131">Se non ve o nome desta sección, non hai conexións deste tipo dispoñibles para vostede.</span><span class="sxs-lookup"><span data-stu-id="1f20f-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="1f20f-132">Seleccione as entidades, por exemplo, segmentos que desexa exportar.</span><span class="sxs-lookup"><span data-stu-id="1f20f-132">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="1f20f-133">Cada entidade seleccionada dividirase en ata cinco ficheiros de saída cando se exporte.</span><span class="sxs-lookup"><span data-stu-id="1f20f-133">Each selected entity will be split up into up to five output files when exported.</span></span> 

1. <span data-ttu-id="1f20f-134">Seleccione **Gardar**.</span><span class="sxs-lookup"><span data-stu-id="1f20f-134">Select **Save**.</span></span>

<span data-ttu-id="1f20f-135">Ao gardar unha exportación non se executa a exportación inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="1f20f-135">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="1f20f-136">A exportación execútase con cada [actualización programada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="1f20f-136">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="1f20f-137">Tamén pode [exportar datos baixo demanda](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="1f20f-137">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="1f20f-138">Cumprimento e privacidade dos datos</span><span class="sxs-lookup"><span data-stu-id="1f20f-138">Data privacy and compliance</span></span>

<span data-ttu-id="1f20f-139">Cando habilita Dynamics 365 Customer Insights para transmitir datos a SFTP, permite a transferencia de datos fóra do límite de cumprimento de Dynamics 365 Customer Insights, incluíndo datos potencialmente confidenciais como os datos persoais.</span><span class="sxs-lookup"><span data-stu-id="1f20f-139">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="1f20f-140">Microsoft transferirá estes datos segundo a súa instrución, pero vostede é responsable de garantir que o destino de exportación cumpra as obrigas de privacidade ou seguridade que poida ter.</span><span class="sxs-lookup"><span data-stu-id="1f20f-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="1f20f-141">Para obter máis información, consulte a [Declaración de privacidade de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="1f20f-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="1f20f-142">O administrador de Dynamics 365 Customer Insights pode eliminar este destino de exportación en calquera momento para interromper o uso desta funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="1f20f-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
