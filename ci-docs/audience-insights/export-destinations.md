---
title: Exportar datos de Customer Insights
description: Xestione as exportacións para compartir datos.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 354ce9ef30fe918975d06290430996c84f8bd3f7
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896141"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="17719-103">Visión xeral das exportacións (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="17719-103">Exports (preview) overview</span></span>

<span data-ttu-id="17719-104">A páxina **Exportacións** mostra todas as exportacións configuradas.</span><span class="sxs-lookup"><span data-stu-id="17719-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="17719-105">As exportacións comparten datos específicos con varias aplicacións.</span><span class="sxs-lookup"><span data-stu-id="17719-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="17719-106">Poden incluír perfís ou entidades de clientes, esquemas e detalles de asignación.</span><span class="sxs-lookup"><span data-stu-id="17719-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="17719-107">Cada exportación require unha [conexión, configurada por un administrador, para xestionar a autenticación e o acceso](connections.md).</span><span class="sxs-lookup"><span data-stu-id="17719-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

> [!NOTE]
> <span data-ttu-id="17719-108">Ata marzo de 2021, as exportacións creaban automaticamente unha conexión co servizo correspondente.</span><span class="sxs-lookup"><span data-stu-id="17719-108">Until March 2021, exports created a connection to the corresponding service automatically.</span></span> <span data-ttu-id="17719-109">As exportacións agora requiren unha [conexión, creada e compartida por un administrador](connections.md) antes de poder crealas.</span><span class="sxs-lookup"><span data-stu-id="17719-109">Exports now require a [connection, created and shared by an administrator](connections.md) before you can create them.</span></span>

<span data-ttu-id="17719-110">Vaia a **Datos** > **Exportacións** para ver a páxina de exportacións.</span><span class="sxs-lookup"><span data-stu-id="17719-110">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="17719-111">Todos os roles de usuario teñen acceso para ver as exportacións configuradas.</span><span class="sxs-lookup"><span data-stu-id="17719-111">All user roles have access to view configured exports.</span></span> <span data-ttu-id="17719-112">Uso do campo de busca na barra de comandos para atopar exportacións polo seu nome, nome de conexión ou tipo de conexión.</span><span class="sxs-lookup"><span data-stu-id="17719-112">Use of the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="17719-113">Configurar unha nova exportación</span><span class="sxs-lookup"><span data-stu-id="17719-113">Set up a new export</span></span>

<span data-ttu-id="17719-114">Para configurar ou editar unha exportación, necesita ter conexións dispoñibles.</span><span class="sxs-lookup"><span data-stu-id="17719-114">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="17719-115">As conexións dependen do seu [rol de usuario](permissions.md):</span><span class="sxs-lookup"><span data-stu-id="17719-115">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="17719-116">Os administradores teñen acceso a todas as conexións.</span><span class="sxs-lookup"><span data-stu-id="17719-116">Administrators have access to all connections.</span></span> <span data-ttu-id="17719-117">Tamén poden crear novas conexións cando configuren unha exportación.</span><span class="sxs-lookup"><span data-stu-id="17719-117">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="17719-118">Os colaboradores poden ter acceso a conexións específicas.</span><span class="sxs-lookup"><span data-stu-id="17719-118">Contributors can have access to specific connections.</span></span> <span data-ttu-id="17719-119">Dependen dos administradores para configurar e compartir conexións.</span><span class="sxs-lookup"><span data-stu-id="17719-119">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="17719-120">Para obter máis información, consulte [Permitir aos colaboradores usar unha conexión para as exportacións](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="17719-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="17719-121">Os espectadores só poden ver as exportacións existentes pero non crealas.</span><span class="sxs-lookup"><span data-stu-id="17719-121">Viewers can only view existing exports but not create them.</span></span>

1. <span data-ttu-id="17719-122">Vaia a **Datos** > **Exportacións**.</span><span class="sxs-lookup"><span data-stu-id="17719-122">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="17719-123">Seleccione **Engadir exportación** para crear un novo destino de exportación.</span><span class="sxs-lookup"><span data-stu-id="17719-123">Select **Add export** to create a new export destination.</span></span>

1. <span data-ttu-id="17719-124">No panel **Configurar exportación**, seleccione a conexión que desexa empregar.</span><span class="sxs-lookup"><span data-stu-id="17719-124">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="17719-125">As [conexións](connections.md) son xestionados por administradores.</span><span class="sxs-lookup"><span data-stu-id="17719-125">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="17719-126">Proporcione os detalles requiridos e seleccione **Gardar** para crear a exportación.</span><span class="sxs-lookup"><span data-stu-id="17719-126">Provide the required details and select **Save** to create the export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="17719-127">Editar unha exportación</span><span class="sxs-lookup"><span data-stu-id="17719-127">Edit an export</span></span>

1. <span data-ttu-id="17719-128">Seleccione os tres puntos verticais para o destino de exportación que desexa editar.</span><span class="sxs-lookup"><span data-stu-id="17719-128">Select the vertical ellipsis for the export destination you want to edit.</span></span>

1. <span data-ttu-id="17719-129">No menú despregable, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="17719-129">Select **Edit** from the drop-down menu.</span></span>

1. <span data-ttu-id="17719-130">Cambie os valores que desexa actualizar e seccione **Gardar**.</span><span class="sxs-lookup"><span data-stu-id="17719-130">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="17719-131">Ver Exportacións e detalles das exportacións</span><span class="sxs-lookup"><span data-stu-id="17719-131">View Exports and export details</span></span>

<span data-ttu-id="17719-132">Despois de crear destinos de exportación, aparecen en **Datos** > **Exportacións**.</span><span class="sxs-lookup"><span data-stu-id="17719-132">After creating export destinations, they are listed on **Data** > **Exports**.</span></span> <span data-ttu-id="17719-133">Todos os usuarios poden ver que datos se comparten e o seu estado máis recente.</span><span class="sxs-lookup"><span data-stu-id="17719-133">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="17719-134">Vaia a **Datos** > **Exportacións**.</span><span class="sxs-lookup"><span data-stu-id="17719-134">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="17719-135">Os usuarios sen permisos de edición seleccionan **Ver** en vez de **Editar** para ver os detalles da exportación.</span><span class="sxs-lookup"><span data-stu-id="17719-135">Users without edit permissions select **View** instead of **Edit** see the export details.</span></span>

1. <span data-ttu-id="17719-136">Este panel lateral mostra a configuración desta exportación.</span><span class="sxs-lookup"><span data-stu-id="17719-136">This side pane shows the set up of this export.</span></span> <span data-ttu-id="17719-137">Sen permisos de edición, non pode cambiar os valores.</span><span class="sxs-lookup"><span data-stu-id="17719-137">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="17719-138">Seleccione **Pechar** para volver á páxina de exportacións.</span><span class="sxs-lookup"><span data-stu-id="17719-138">Select **Close** to return to the exports page.</span></span>

## <a name="run-exports-on-demand"></a><span data-ttu-id="17719-139">Executar exportacións a petición</span><span class="sxs-lookup"><span data-stu-id="17719-139">Run exports on demand</span></span>

<span data-ttu-id="17719-140">Despois de configurar unha exportación, executarase con cada [actualización programada](system.md#schedule-tab) sempre que teña unha conexión que funcione.</span><span class="sxs-lookup"><span data-stu-id="17719-140">After configuring an export, it will run with every [scheduled refresh](system.md#schedule-tab) as long as it has a working connection.</span></span>

<span data-ttu-id="17719-141">Para exportar datos sen esperar a unha actualización programada, vaia a **Datos** > **Exportacións**.</span><span class="sxs-lookup"><span data-stu-id="17719-141">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span> <span data-ttu-id="17719-142">Ten dúas opcións:</span><span class="sxs-lookup"><span data-stu-id="17719-142">You have two options:</span></span>

- <span data-ttu-id="17719-143">Para executar todas as exportacións, seleccione **Executar todo** na barra de comandos.</span><span class="sxs-lookup"><span data-stu-id="17719-143">To run all exports, select **Run all** in the command bar.</span></span> 
- <span data-ttu-id="17719-144">Para executar unha única exportación, seleccione os puntos suspensivos (...) nun elemento da lista e logo escolla **Executar**.</span><span class="sxs-lookup"><span data-stu-id="17719-144">To run a single export, select the ellipsis (...) on a list item and then choose **Run**.</span></span>

## <a name="remove-an-export"></a><span data-ttu-id="17719-145">Eliminar unha exportación</span><span class="sxs-lookup"><span data-stu-id="17719-145">Remove an Export</span></span>

1. <span data-ttu-id="17719-146">Vaia a **Datos** > **Exportacións**.</span><span class="sxs-lookup"><span data-stu-id="17719-146">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="17719-147">Seleccione os tres puntos verticais para a exportación que desexa eliminar.</span><span class="sxs-lookup"><span data-stu-id="17719-147">Select the vertical ellipsis for the Export you want to remove.</span></span>

1. <span data-ttu-id="17719-148">Seleccione **Eliminar** do menú despregable.</span><span class="sxs-lookup"><span data-stu-id="17719-148">Select **Remove** from the dropdown menu.</span></span>

1. <span data-ttu-id="17719-149">Confirme a eliminación seleccionando **Eliminar** na pantalla de confirmación.</span><span class="sxs-lookup"><span data-stu-id="17719-149">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
