---
title: Exportar datos de Customer Insights a Dynamics 365 Marketing
description: Aprenda a configurar a conexión e exportar a Dynamics 365 Marketing.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: a13f6f81f5e2570d3302d88c02755f1d86321a01
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759635"
---
# <a name="use-segments-in-dynamics-365-marketing-preview"></a><span data-ttu-id="9ce84-103">Usar segmentos en Dynamics 365 Marketing (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="9ce84-103">Use segments in Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="9ce84-104">Use os [segmentos](segments.md) para xerar campañas e contactar con grupos específicos de clientes con Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="9ce84-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="9ce84-105">Para obter máis información, consulte [Usar segmentos de Dynamics 365 Customer Insights con Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="9ce84-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite-for-a-connection"></a><span data-ttu-id="9ce84-106">Requisito previo para unha conexión</span><span class="sxs-lookup"><span data-stu-id="9ce84-106">Prerequisite for a connection</span></span>

- <span data-ttu-id="9ce84-107">Os rexistros de contacto deben estar presentes en Dynamics 365 Marketing antes de poder exportar un segmento de Customer Insights a Marketing.</span><span class="sxs-lookup"><span data-stu-id="9ce84-107">Contact records must be present in Dynamics 365 Marketing before you can export a segment from Customer Insights to Marketing.</span></span> <span data-ttu-id="9ce84-108">Lea máis sobre como inxerir contactos en [Dynamics 365 Marketing usando Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="9ce84-108">Read more on how to ingest contacts in [Dynamics 365 Marketing using Common Data Services](connect-power-query.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="9ce84-109">A exportación de segmentos de información de audiencia a Marketing non creará novos rexistros de contacto nas instancias de Marketing.</span><span class="sxs-lookup"><span data-stu-id="9ce84-109">Exporting segments from audience insights to Marketing will not create new contact records in the Marketing instances.</span></span> <span data-ttu-id="9ce84-110">Os rexistros de contacto de Marketing deben ser inxeridos na información do público e utilizados como orixe de datos.</span><span class="sxs-lookup"><span data-stu-id="9ce84-110">The contact records from Marketing must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="9ce84-111">Tamén deben incluírse na entidade de cliente unificada para asignar os ID de clientes a ID de contacto antes de que os segmentos poidan ser exportados.</span><span class="sxs-lookup"><span data-stu-id="9ce84-111">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="set-up-connection-to-marketing"></a><span data-ttu-id="9ce84-112">Configurar conexión a Marketing</span><span class="sxs-lookup"><span data-stu-id="9ce84-112">Set up connection to Marketing</span></span>

1. <span data-ttu-id="9ce84-113">Vaia a **Administrar** > **Conexións**.</span><span class="sxs-lookup"><span data-stu-id="9ce84-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="9ce84-114">Seleccione **Engadir conexión** e elixa **Dynamics 365 Marketing** para configurar a conexión.</span><span class="sxs-lookup"><span data-stu-id="9ce84-114">Select **Add connection** and choose **Dynamics 365 Marketing** to configure the connection.</span></span>

1. <span data-ttu-id="9ce84-115">Déalle á conexión un nome recoñecible no campo **Nome para mostrar**.</span><span class="sxs-lookup"><span data-stu-id="9ce84-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="9ce84-116">O nome e o tipo de conexión describen esta conexión.</span><span class="sxs-lookup"><span data-stu-id="9ce84-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="9ce84-117">Recomendamos escoller un nome que explique o propósito e o destino da conexión.</span><span class="sxs-lookup"><span data-stu-id="9ce84-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="9ce84-118">Escolla quen pode usar esta conexión.</span><span class="sxs-lookup"><span data-stu-id="9ce84-118">Choose who can use this connection.</span></span> <span data-ttu-id="9ce84-119">Se non realiza ningunha acción, o valor predeterminado será Administradores.</span><span class="sxs-lookup"><span data-stu-id="9ce84-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="9ce84-120">Para obter máis información, consulte [Permitir aos colaboradores usar unha conexión para as exportacións](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="9ce84-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="9ce84-121">Insira o URL de mercadotecnia da súa organización no campo **Enderezo do servidor**.</span><span class="sxs-lookup"><span data-stu-id="9ce84-121">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="9ce84-122">Na sección **Conta de administrador do servidor**, seleccione **Iniciar sesión** e escolla unha conta de Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="9ce84-122">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="9ce84-123">Asigne un campo de ID de cliente ao ID de contacto de Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="9ce84-123">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="9ce84-124">Seleccione **Gardar** para completar a conexión.</span><span class="sxs-lookup"><span data-stu-id="9ce84-124">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="9ce84-125">Configurar unha exportación</span><span class="sxs-lookup"><span data-stu-id="9ce84-125">Configure an export</span></span>

<span data-ttu-id="9ce84-126">Pode configurar esta exportación se ten acceso a unha conexión deste tipo.</span><span class="sxs-lookup"><span data-stu-id="9ce84-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="9ce84-127">Para obter máis información, consulte [Permisos necesarios para configurar unha exportación](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="9ce84-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="9ce84-128">Vaia a **Datos** > **Exportacións**.</span><span class="sxs-lookup"><span data-stu-id="9ce84-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="9ce84-129">Seleccione **Engadir destino** para crear unha nova exportación.</span><span class="sxs-lookup"><span data-stu-id="9ce84-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="9ce84-130">No campo **Conexión da exportación** escolla unha conexión da sección Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="9ce84-130">In the **Connection for export** field, choose a connection from the Dynamics 365 Marketing section.</span></span> <span data-ttu-id="9ce84-131">Se non ve o nome desta sección, non hai conexións deste tipo dispoñibles para vostede.</span><span class="sxs-lookup"><span data-stu-id="9ce84-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="9ce84-132">Escolla un ou máis segmentos.</span><span class="sxs-lookup"><span data-stu-id="9ce84-132">Choose one or more segments.</span></span>

1. <span data-ttu-id="9ce84-133">Seleccione **Gardar**.</span><span class="sxs-lookup"><span data-stu-id="9ce84-133">Select **Save**.</span></span>

<span data-ttu-id="9ce84-134">Ao gardar unha exportación non se executa a exportación inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="9ce84-134">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="9ce84-135">A exportación execútase con cada [actualización programada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="9ce84-135">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="9ce84-136">Tamén pode [exportar datos baixo demanda](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="9ce84-136">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
