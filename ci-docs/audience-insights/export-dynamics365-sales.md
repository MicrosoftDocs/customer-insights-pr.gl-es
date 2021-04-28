---
title: Exportar datos de Customer Insights a Dynamics 365 Sales
description: Aprenda a configurar a conexión e exportar a Dynamics 365 Sales.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: fc1a05ba4d21d96aa1a9724d158687bbb86949b6
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759589"
---
# <a name="use-segments-in-dynamics-365-sales-preview"></a><span data-ttu-id="0804a-103">Usar segmentos en Dynamics 365 Sales (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="0804a-103">Use segments in Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="0804a-104">Use os datos dos clientes para crear listas de márketing, realizar o seguimento de fluxos de traballo e enviar promocións con Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="0804a-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite-for-connection"></a><span data-ttu-id="0804a-105">Requisito previo para a conexión</span><span class="sxs-lookup"><span data-stu-id="0804a-105">Prerequisite for connection</span></span>

1. <span data-ttu-id="0804a-106">Os rexistros de contacto deben estar presentes en Dynamics 365 Sales antes de poder exportar un segmento de Customer Insights a Sales.</span><span class="sxs-lookup"><span data-stu-id="0804a-106">Contact records must be present in Dynamics 365 Sales before you can export a segment from Customer Insights to Sales.</span></span> <span data-ttu-id="0804a-107">Lea máis sobre como inxerir contactos en [Dynamics 365 Sales usando Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="0804a-107">Read more on how to ingest contacts in [Dynamics 365 Sales using Common Data Services](connect-power-query.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="0804a-108">A exportación de segmentos de información de audiencia a Sales non creará novos rexistros de contacto nas instancias de Sales.</span><span class="sxs-lookup"><span data-stu-id="0804a-108">Exporting segments from audience insights to Sales will not create new contact records in the Sales instances.</span></span> <span data-ttu-id="0804a-109">Os rexistros de contacto de Sales deben ser inxeridos na información do público e utilizados como orixe de datos.</span><span class="sxs-lookup"><span data-stu-id="0804a-109">The contact records from Sales must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="0804a-110">Tamén deben incluírse na entidade de cliente unificada para asignar os ID de clientes a ID de contacto antes de que os segmentos poidan ser exportados.</span><span class="sxs-lookup"><span data-stu-id="0804a-110">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="set-up-the-connection-to-sales"></a><span data-ttu-id="0804a-111">Configurar a conexión a Sales</span><span class="sxs-lookup"><span data-stu-id="0804a-111">Set up the connection to Sales</span></span>

1. <span data-ttu-id="0804a-112">Vaia a **Administrar** > **Conexións**.</span><span class="sxs-lookup"><span data-stu-id="0804a-112">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="0804a-113">Seleccione **Engadir conexión** e elixa **Dynamics 365 Sales** para configurar a conexión.</span><span class="sxs-lookup"><span data-stu-id="0804a-113">Select **Add connection** and choose **Dynamics 365 Sales** to configure the connection.</span></span>

1. <span data-ttu-id="0804a-114">Déalle á conexión un nome recoñecible no campo **Nome para mostrar**.</span><span class="sxs-lookup"><span data-stu-id="0804a-114">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="0804a-115">O nome e o tipo de conexión describen esta conexión.</span><span class="sxs-lookup"><span data-stu-id="0804a-115">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="0804a-116">Recomendamos escoller un nome que explique o propósito e o destino da conexión.</span><span class="sxs-lookup"><span data-stu-id="0804a-116">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="0804a-117">Escolla quen pode usar esta conexión.</span><span class="sxs-lookup"><span data-stu-id="0804a-117">Choose who can use this connection.</span></span> <span data-ttu-id="0804a-118">Se non realiza ningunha acción, o valor predeterminado será Administradores.</span><span class="sxs-lookup"><span data-stu-id="0804a-118">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="0804a-119">Para obter máis información, consulte [Permitir aos colaboradores usar unha conexión para as exportacións](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="0804a-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="0804a-120">Insira o URL de Vendas da súa organización no campo **Enderezo do servidor**.</span><span class="sxs-lookup"><span data-stu-id="0804a-120">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="0804a-121">Na sección **Conta de administrador do servidor**, seleccione **Iniciar sesión** e escolla unha conta de Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="0804a-121">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="0804a-122">Asigne un campo de ID de cliente ao ID de contacto de Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="0804a-122">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="0804a-123">Seleccione **Gardar** para completar a conexión.</span><span class="sxs-lookup"><span data-stu-id="0804a-123">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="0804a-124">Configurar unha exportación</span><span class="sxs-lookup"><span data-stu-id="0804a-124">Configure an export</span></span>

<span data-ttu-id="0804a-125">Pode configurar esta exportación se ten acceso a unha conexión deste tipo.</span><span class="sxs-lookup"><span data-stu-id="0804a-125">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="0804a-126">Para obter máis información, consulte [Permisos necesarios para configurar unha exportación](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="0804a-126">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="0804a-127">Vaia a **Datos** > **Exportacións**.</span><span class="sxs-lookup"><span data-stu-id="0804a-127">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="0804a-128">Seleccione **Engadir destino** para crear unha nova exportación.</span><span class="sxs-lookup"><span data-stu-id="0804a-128">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="0804a-129">No campo **Conexión da exportación** escolla unha conexión da sección Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="0804a-129">In the **Connection for export** field, choose a connection from the Dynamics 365 Sales section.</span></span> <span data-ttu-id="0804a-130">Se non ve o nome desta sección, non hai conexións deste tipo dispoñibles para vostede.</span><span class="sxs-lookup"><span data-stu-id="0804a-130">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="0804a-131">Escolla un ou máis segmentos.</span><span class="sxs-lookup"><span data-stu-id="0804a-131">Choose one or more segments.</span></span>

1. <span data-ttu-id="0804a-132">Seleccione **Gardar**</span><span class="sxs-lookup"><span data-stu-id="0804a-132">Select **Save**</span></span>

<span data-ttu-id="0804a-133">Ao gardar unha exportación non se executa a exportación inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="0804a-133">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="0804a-134">A exportación execútase con cada [actualización programada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="0804a-134">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="0804a-135">Tamén pode [exportar datos baixo demanda](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="0804a-135">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
