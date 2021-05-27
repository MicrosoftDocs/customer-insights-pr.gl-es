---
title: Exportar datos de Customer Insights
description: Xestione as exportacións para compartir datos.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c1078ed0ba259a6e9cde3c7ede3570890ae48e67
ms.sourcegitcommit: 33a8e21b3bf6521bdb8346f81f79fce88091ddfd
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 05/10/2021
ms.locfileid: "6016612"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="aa4ba-103">Visión xeral das exportacións (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="aa4ba-103">Exports (preview) overview</span></span>

<span data-ttu-id="aa4ba-104">A páxina **Exportacións** mostra todas as exportacións configuradas.</span><span class="sxs-lookup"><span data-stu-id="aa4ba-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="aa4ba-105">As exportacións comparten datos específicos con varias aplicacións.</span><span class="sxs-lookup"><span data-stu-id="aa4ba-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="aa4ba-106">Poden incluír perfís ou entidades de clientes, esquemas e detalles de asignación.</span><span class="sxs-lookup"><span data-stu-id="aa4ba-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="aa4ba-107">Cada exportación require unha [conexión, configurada por un administrador, para xestionar a autenticación e o acceso](connections.md).</span><span class="sxs-lookup"><span data-stu-id="aa4ba-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

<span data-ttu-id="aa4ba-108">Vaia a **Datos** > **Exportacións** para ver a páxina de exportacións.</span><span class="sxs-lookup"><span data-stu-id="aa4ba-108">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="aa4ba-109">Todos os roles de usuario teñen acceso para ver as exportacións configuradas.</span><span class="sxs-lookup"><span data-stu-id="aa4ba-109">All user roles have access to view configured exports.</span></span> <span data-ttu-id="aa4ba-110">Uso do campo de busca na barra de comandos para atopar exportacións polo seu nome, nome de conexión ou tipo de conexión.</span><span class="sxs-lookup"><span data-stu-id="aa4ba-110">Use of the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="aa4ba-111">Configurar unha nova exportación</span><span class="sxs-lookup"><span data-stu-id="aa4ba-111">Set up a new export</span></span>

<span data-ttu-id="aa4ba-112">Para configurar ou editar unha exportación, necesita ter conexións dispoñibles.</span><span class="sxs-lookup"><span data-stu-id="aa4ba-112">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="aa4ba-113">As conexións dependen do seu [rol de usuario](permissions.md):</span><span class="sxs-lookup"><span data-stu-id="aa4ba-113">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="aa4ba-114">Os administradores teñen acceso a todas as conexións.</span><span class="sxs-lookup"><span data-stu-id="aa4ba-114">Administrators have access to all connections.</span></span> <span data-ttu-id="aa4ba-115">Tamén poden crear novas conexións cando configuren unha exportación.</span><span class="sxs-lookup"><span data-stu-id="aa4ba-115">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="aa4ba-116">Os colaboradores poden ter acceso a conexións específicas.</span><span class="sxs-lookup"><span data-stu-id="aa4ba-116">Contributors can have access to specific connections.</span></span> <span data-ttu-id="aa4ba-117">Dependen dos administradores para configurar e compartir conexións.</span><span class="sxs-lookup"><span data-stu-id="aa4ba-117">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="aa4ba-118">Para obter máis información, consulte [Permitir aos colaboradores usar unha conexión para as exportacións](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="aa4ba-118">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="aa4ba-119">Os espectadores só poden ver as exportacións existentes pero non crealas.</span><span class="sxs-lookup"><span data-stu-id="aa4ba-119">Viewers can only view existing exports but not create them.</span></span>

1. <span data-ttu-id="aa4ba-120">Vaia a **Datos** > **Exportacións**.</span><span class="sxs-lookup"><span data-stu-id="aa4ba-120">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="aa4ba-121">Seleccione **Engadir exportación** para crear un novo destino de exportación.</span><span class="sxs-lookup"><span data-stu-id="aa4ba-121">Select **Add export** to create a new export destination.</span></span>

1. <span data-ttu-id="aa4ba-122">No panel **Configurar exportación**, seleccione a conexión que desexa empregar.</span><span class="sxs-lookup"><span data-stu-id="aa4ba-122">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="aa4ba-123">As [conexións](connections.md) son xestionados por administradores.</span><span class="sxs-lookup"><span data-stu-id="aa4ba-123">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="aa4ba-124">Proporcione os detalles requiridos e seleccione **Gardar** para crear a exportación.</span><span class="sxs-lookup"><span data-stu-id="aa4ba-124">Provide the required details and select **Save** to create the export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="aa4ba-125">Editar unha exportación</span><span class="sxs-lookup"><span data-stu-id="aa4ba-125">Edit an export</span></span>

1. <span data-ttu-id="aa4ba-126">Seleccione os tres puntos verticais para o destino de exportación que desexa editar.</span><span class="sxs-lookup"><span data-stu-id="aa4ba-126">Select the vertical ellipsis for the export destination you want to edit.</span></span>

1. <span data-ttu-id="aa4ba-127">No menú despregable, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="aa4ba-127">Select **Edit** from the drop-down menu.</span></span>

1. <span data-ttu-id="aa4ba-128">Cambie os valores que desexa actualizar e seccione **Gardar**.</span><span class="sxs-lookup"><span data-stu-id="aa4ba-128">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="aa4ba-129">Ver Exportacións e detalles das exportacións</span><span class="sxs-lookup"><span data-stu-id="aa4ba-129">View Exports and export details</span></span>

<span data-ttu-id="aa4ba-130">Despois de crear destinos de exportación, aparecen en **Datos** > **Exportacións**.</span><span class="sxs-lookup"><span data-stu-id="aa4ba-130">After creating export destinations, they are listed on **Data** > **Exports**.</span></span> <span data-ttu-id="aa4ba-131">Todos os usuarios poden ver que datos se comparten e o seu estado máis recente.</span><span class="sxs-lookup"><span data-stu-id="aa4ba-131">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="aa4ba-132">Vaia a **Datos** > **Exportacións**.</span><span class="sxs-lookup"><span data-stu-id="aa4ba-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="aa4ba-133">Os usuarios sen permisos de edición seleccionan **Ver** en vez de **Editar** para ver os detalles da exportación.</span><span class="sxs-lookup"><span data-stu-id="aa4ba-133">Users without edit permissions select **View** instead of **Edit** see the export details.</span></span>

1. <span data-ttu-id="aa4ba-134">Este panel lateral mostra a configuración desta exportación.</span><span class="sxs-lookup"><span data-stu-id="aa4ba-134">This side pane shows the set up of this export.</span></span> <span data-ttu-id="aa4ba-135">Sen permisos de edición, non pode cambiar os valores.</span><span class="sxs-lookup"><span data-stu-id="aa4ba-135">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="aa4ba-136">Seleccione **Pechar** para volver á páxina de exportacións.</span><span class="sxs-lookup"><span data-stu-id="aa4ba-136">Select **Close** to return to the exports page.</span></span>

## <a name="run-exports-on-demand"></a><span data-ttu-id="aa4ba-137">Executar exportacións a petición</span><span class="sxs-lookup"><span data-stu-id="aa4ba-137">Run exports on demand</span></span>

<span data-ttu-id="aa4ba-138">Despois de configurar unha exportación, executarase con cada [actualización programada](system.md#schedule-tab) sempre que teña unha conexión que funcione.</span><span class="sxs-lookup"><span data-stu-id="aa4ba-138">After configuring an export, it will run with every [scheduled refresh](system.md#schedule-tab) as long as it has a working connection.</span></span>

<span data-ttu-id="aa4ba-139">Para exportar datos sen esperar a unha actualización programada, vaia a **Datos** > **Exportacións**.</span><span class="sxs-lookup"><span data-stu-id="aa4ba-139">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span> <span data-ttu-id="aa4ba-140">Ten dúas opcións:</span><span class="sxs-lookup"><span data-stu-id="aa4ba-140">You have two options:</span></span>

- <span data-ttu-id="aa4ba-141">Para executar todas as exportacións, seleccione **Executar todo** na barra de comandos.</span><span class="sxs-lookup"><span data-stu-id="aa4ba-141">To run all exports, select **Run all** in the command bar.</span></span> 
- <span data-ttu-id="aa4ba-142">Para executar unha única exportación, seleccione os puntos suspensivos (...) nun elemento da lista e logo escolla **Executar**.</span><span class="sxs-lookup"><span data-stu-id="aa4ba-142">To run a single export, select the ellipsis (...) on a list item and then choose **Run**.</span></span>

## <a name="remove-an-export"></a><span data-ttu-id="aa4ba-143">Eliminar unha exportación</span><span class="sxs-lookup"><span data-stu-id="aa4ba-143">Remove an Export</span></span>

1. <span data-ttu-id="aa4ba-144">Vaia a **Datos** > **Exportacións**.</span><span class="sxs-lookup"><span data-stu-id="aa4ba-144">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="aa4ba-145">Seleccione os tres puntos verticais para a exportación que desexa eliminar.</span><span class="sxs-lookup"><span data-stu-id="aa4ba-145">Select the vertical ellipsis for the Export you want to remove.</span></span>

1. <span data-ttu-id="aa4ba-146">Seleccione **Eliminar** do menú despregable.</span><span class="sxs-lookup"><span data-stu-id="aa4ba-146">Select **Remove** from the dropdown menu.</span></span>

1. <span data-ttu-id="aa4ba-147">Confirme a eliminación seleccionando **Eliminar** na pantalla de confirmación.</span><span class="sxs-lookup"><span data-stu-id="aa4ba-147">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
