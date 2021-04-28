---
title: Exportar datos de Customer Insights a Campaign Monitor
description: Aprenda a configurar a conexión e exportar a Campaign Monitor.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 7fd6af37b40e21d030a1ace0cd5f8fcc7861c3fa
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760527"
---
# <a name="export-segment-lists-to-campaign-monitor-preview"></a><span data-ttu-id="ff140-103">Exportar listas de segmentos a Campaign Monitor (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="ff140-103">Export segment lists to Campaign Monitor (preview)</span></span>

<span data-ttu-id="ff140-104">Exporte segmentos de perfís de clientes unificados a Campaign Monitor e utilíceos para actividades de mercadotecnia.</span><span class="sxs-lookup"><span data-stu-id="ff140-104">Export segments of unified customer profiles to Campaign Monitor and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ff140-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="ff140-105">Prerequisites</span></span>

-   <span data-ttu-id="ff140-106">Ten unha [conta de Campaign Monitor](https://www.campaignmonitor.com/) e as correspondentes credenciais de administrador.</span><span class="sxs-lookup"><span data-stu-id="ff140-106">You have an [Campaign Monitor account](https://www.campaignmonitor.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="ff140-107">Ten [segmentos configurados](segments.md) na información do público.</span><span class="sxs-lookup"><span data-stu-id="ff140-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="ff140-108">Os perfís de clientes unificados nos segmentos exportados conteñen un campo que representa un enderezo de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="ff140-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="ff140-109">Limitacións coñecidas</span><span class="sxs-lookup"><span data-stu-id="ff140-109">Known limitations</span></span>

- <span data-ttu-id="ff140-110">Pode exportar ata 1 millón de perfís por exportación a Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="ff140-110">You can export up to 1 million profiles per export to Campaign Monitor.</span></span>
- <span data-ttu-id="ff140-111">A exportación a Campaign Monitor está limitada a segmentos.</span><span class="sxs-lookup"><span data-stu-id="ff140-111">Exporting to Campaign Monitor is limited to segments.</span></span>
- <span data-ttu-id="ff140-112">A exportación de segmentos de ata 1 millón de perfís a Campaign Monitor pode tardar ata 20 minutos en finalizar.</span><span class="sxs-lookup"><span data-stu-id="ff140-112">Exporting up to 1 million profiles to Campaign Monitor can take up to 20 minutes to complete.</span></span> 
- <span data-ttu-id="ff140-113">O número de perfís que pode exportar a Campaign Monitor depende e está limitado ao seu contrato con Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="ff140-113">The number of profiles that you can export to Campaign Monitor is dependent and limited on your contract with Campaign Monitor.</span></span>

## <a name="set-up-connection-to-campaign-monitor"></a><span data-ttu-id="ff140-114">Configurar a conexión a Campaign Monitor</span><span class="sxs-lookup"><span data-stu-id="ff140-114">Set up connection to Campaign Monitor</span></span>

1. <span data-ttu-id="ff140-115">Vaia a **Administrar** > **Conexións**.</span><span class="sxs-lookup"><span data-stu-id="ff140-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="ff140-116">Seleccione **Engadir conexión** e elixa **Campaign Monitor** para configurar a conexión.</span><span class="sxs-lookup"><span data-stu-id="ff140-116">Select **Add connection** and choose **Campaign Monitor** to configure the connection.</span></span>

1. <span data-ttu-id="ff140-117">Déalle á conexión un nome recoñecible no campo **Nome para mostrar**.</span><span class="sxs-lookup"><span data-stu-id="ff140-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="ff140-118">O nome e o tipo de conexión describen esta conexión.</span><span class="sxs-lookup"><span data-stu-id="ff140-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="ff140-119">Recomendamos escoller un nome que explique o propósito e o destino da conexión.</span><span class="sxs-lookup"><span data-stu-id="ff140-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="ff140-120">Escolla quen pode usar esta conexión.</span><span class="sxs-lookup"><span data-stu-id="ff140-120">Choose who can use this connection.</span></span> <span data-ttu-id="ff140-121">Se non realiza ningunha acción, o valor predeterminado será Administradores.</span><span class="sxs-lookup"><span data-stu-id="ff140-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="ff140-122">Para obter máis información, consulte [Permitir aos colaboradores usar unha conexión para as exportacións](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="ff140-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="ff140-123">Seleccione **Estou de acordo** para confirmar a **Privacidade e cumprimento dos datos**.</span><span class="sxs-lookup"><span data-stu-id="ff140-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="ff140-124">Seleccione **Conectar** para iniciar a conexión a Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="ff140-124">Select **Connect** to initialize the connection to Campaign Monitor.</span></span>

1. <span data-ttu-id="ff140-125">Seleccione **Autenticarse con Campaign Monitor** e proporcione as súas credenciais de administrador de Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="ff140-125">Select **Authenticate with Campaign Monitor** and provide your admin credentials for Campaign Monitor.</span></span>

1. <span data-ttu-id="ff140-126">Seleccione **Autoengadirse como usuario de exportación** e proporcione as súas credenciais de Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="ff140-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="ff140-127">Seleccione **Gardar** para completar a conexión.</span><span class="sxs-lookup"><span data-stu-id="ff140-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="ff140-128">Configurar unha exportación</span><span class="sxs-lookup"><span data-stu-id="ff140-128">Configure an export</span></span>

<span data-ttu-id="ff140-129">Pode configurar esta exportación se ten acceso a unha conexión deste tipo.</span><span class="sxs-lookup"><span data-stu-id="ff140-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="ff140-130">Para obter máis información, consulte [Permisos necesarios para configurar unha exportación](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="ff140-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="ff140-131">Vaia a **Datos** > **Exportacións**.</span><span class="sxs-lookup"><span data-stu-id="ff140-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="ff140-132">Seleccione **Engadir destino** para crear unha nova exportación.</span><span class="sxs-lookup"><span data-stu-id="ff140-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="ff140-133">No campo **Conexión da exportación** escolla unha conexión da sección Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="ff140-133">In the **Connection for export** field, choose a connection from the Campaign Monitor section.</span></span> <span data-ttu-id="ff140-134">Se non ve o nome desta sección, non hai conexións deste tipo dispoñibles para vostede.</span><span class="sxs-lookup"><span data-stu-id="ff140-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="ff140-135">Insira o seu [**ID de lista de Campaign Monitor**](https://www.campaignmonitor.com/api/getting-started/#your-list-id).</span><span class="sxs-lookup"><span data-stu-id="ff140-135">Enter your [**Campaign Monitor List ID**](https://www.campaignmonitor.com/api/getting-started/#your-list-id).</span></span>    
   <span data-ttu-id="ff140-136">[Xere a clave de API](https://www.campaignmonitor.com/api/getting-started/) desde **Axustes da conta** primeiro en Campaign Monitor para ver o ID da lista de API.</span><span class="sxs-lookup"><span data-stu-id="ff140-136">[Generate the API key](https://www.campaignmonitor.com/api/getting-started/) from **Account Settings** in Campaign Monitor first to view the API list ID.</span></span>  

3. <span data-ttu-id="ff140-137">Na sección **Coincidencia de datos**, no campo **Correo electrónico**, seleccione o campo do seu perfil de cliente unificado que representa o enderezo de correo electrónico dun cliente.</span><span class="sxs-lookup"><span data-stu-id="ff140-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="ff140-138">É necesario exportar segmentos a Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="ff140-138">It's required to export segments to Campaign Monitor.</span></span>

1. <span data-ttu-id="ff140-139">Seleccione **Gardar**.</span><span class="sxs-lookup"><span data-stu-id="ff140-139">Select **Save**.</span></span>

<span data-ttu-id="ff140-140">Ao gardar unha exportación non se executa a exportación inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="ff140-140">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="ff140-141">A exportación execútase con cada [actualización programada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="ff140-141">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="ff140-142">Tamén pode [exportar datos baixo demanda](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="ff140-142">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="ff140-143">Cumprimento e privacidade dos datos</span><span class="sxs-lookup"><span data-stu-id="ff140-143">Data privacy and compliance</span></span>

<span data-ttu-id="ff140-144">Cando habilita Dynamics 365 Customer Insights para transmitir datos a Campaign Monitor, permite a transferencia de datos fóra do límite de cumprimento de Dynamics 365 Customer Insights, incluíndo datos potencialmente confidenciais como os datos persoais.</span><span class="sxs-lookup"><span data-stu-id="ff140-144">When you enable Dynamics 365 Customer Insights to transmit data to Campaign Monitor, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="ff140-145">Microsoft transferirá estes datos segundo a súa instrución, pero vostede é responsable de asegurarse de que Campaign Monitor cumpra as obrigas de privacidade ou seguridade que poida ter.</span><span class="sxs-lookup"><span data-stu-id="ff140-145">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Campaign Monitor meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="ff140-146">Para obter máis información, consulte a [Declaración de privacidade de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="ff140-146">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="ff140-147">O administrador de Dynamics 365 Customer Insights pode eliminar este destino de exportación en calquera momento para interromper o uso desta funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="ff140-147">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
