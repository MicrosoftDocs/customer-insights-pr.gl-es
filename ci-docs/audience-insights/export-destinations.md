---
title: Exportar datos de Customer Insights
description: Xestione as exportacións para compartir datos.
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6e7793fa99f8431d9d420529b39e0b5b5dbf6748
ms.sourcegitcommit: 0689e7ed4265855d1f76745d68af390f8f4af8a0
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 06/14/2021
ms.locfileid: "6253038"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="b9641-103">Visión xeral das exportacións (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="b9641-103">Exports (preview) overview</span></span>

<span data-ttu-id="b9641-104">A páxina **Exportacións** mostra todas as exportacións configuradas.</span><span class="sxs-lookup"><span data-stu-id="b9641-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="b9641-105">As exportacións comparten datos específicos con varias aplicacións.</span><span class="sxs-lookup"><span data-stu-id="b9641-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="b9641-106">Poden incluír perfís ou entidades de clientes, esquemas e detalles de asignación.</span><span class="sxs-lookup"><span data-stu-id="b9641-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="b9641-107">Cada exportación require unha [conexión, configurada por un administrador, para xestionar a autenticación e o acceso](connections.md).</span><span class="sxs-lookup"><span data-stu-id="b9641-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

<span data-ttu-id="b9641-108">Vaia a **Datos** > **Exportacións** para ver a páxina de exportacións.</span><span class="sxs-lookup"><span data-stu-id="b9641-108">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="b9641-109">Todos os roles de usuario teñen acceso para ver as exportacións configuradas.</span><span class="sxs-lookup"><span data-stu-id="b9641-109">All user roles have access to view configured exports.</span></span> <span data-ttu-id="b9641-110">Uso do campo de busca na barra de comandos para atopar exportacións polo seu nome, nome de conexión ou tipo de conexión.</span><span class="sxs-lookup"><span data-stu-id="b9641-110">Use of the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="b9641-111">Configurar unha nova exportación</span><span class="sxs-lookup"><span data-stu-id="b9641-111">Set up a new export</span></span>

<span data-ttu-id="b9641-112">Para configurar ou editar unha exportación, necesita ter conexións dispoñibles.</span><span class="sxs-lookup"><span data-stu-id="b9641-112">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="b9641-113">As conexións dependen do seu [rol de usuario](permissions.md):</span><span class="sxs-lookup"><span data-stu-id="b9641-113">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="b9641-114">Os administradores teñen acceso a todas as conexións.</span><span class="sxs-lookup"><span data-stu-id="b9641-114">Administrators have access to all connections.</span></span> <span data-ttu-id="b9641-115">Tamén poden crear novas conexións cando configuren unha exportación.</span><span class="sxs-lookup"><span data-stu-id="b9641-115">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="b9641-116">Os colaboradores poden ter acceso a conexións específicas.</span><span class="sxs-lookup"><span data-stu-id="b9641-116">Contributors can have access to specific connections.</span></span> <span data-ttu-id="b9641-117">Dependen dos administradores para configurar e compartir conexións.</span><span class="sxs-lookup"><span data-stu-id="b9641-117">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="b9641-118">A lista de exportacións móstralles aos colaboradores se poden editar ou só ver unha exportación na columna **Os seus permisos**.</span><span class="sxs-lookup"><span data-stu-id="b9641-118">The exports list shows contributors whether they can edit or only view an export in the **Your permissions** column.</span></span> <span data-ttu-id="b9641-119">Para obter máis información, consulte [Permitir aos colaboradores usar unha conexión para as exportacións](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="b9641-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="b9641-120">Os espectadores só poden ver as exportacións existentes pero non crealas.</span><span class="sxs-lookup"><span data-stu-id="b9641-120">Viewers can only view existing exports but not create them.</span></span>

### <a name="define-a-new-export"></a><span data-ttu-id="b9641-121">Definir unha nova exportación</span><span class="sxs-lookup"><span data-stu-id="b9641-121">Define a new export</span></span>

1. <span data-ttu-id="b9641-122">Vaia a **Datos** > **Exportacións**.</span><span class="sxs-lookup"><span data-stu-id="b9641-122">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="b9641-123">Seleccione **Engadir exportación** para crear unha nova exportación.</span><span class="sxs-lookup"><span data-stu-id="b9641-123">Select **Add export** to create a new export.</span></span>

1. <span data-ttu-id="b9641-124">No panel **Configurar exportación**, seleccione a conexión que desexa empregar.</span><span class="sxs-lookup"><span data-stu-id="b9641-124">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="b9641-125">As [conexións](connections.md) son xestionados por administradores.</span><span class="sxs-lookup"><span data-stu-id="b9641-125">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="b9641-126">Proporcione os detalles requiridos e seleccione **Gardar** para crear a exportación.</span><span class="sxs-lookup"><span data-stu-id="b9641-126">Provide the required details and select **Save** to create the export.</span></span>

### <a name="define-a-new-export-based-on-an-existing-export"></a><span data-ttu-id="b9641-127">Definir unha nova exportación baseada nunha exportación existente</span><span class="sxs-lookup"><span data-stu-id="b9641-127">Define a new export based on an existing export</span></span>

1. <span data-ttu-id="b9641-128">Vaia a **Datos** > **Exportacións**.</span><span class="sxs-lookup"><span data-stu-id="b9641-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="b9641-129">Na lista de exportacións, seleccione a exportación que quere duplicar.</span><span class="sxs-lookup"><span data-stu-id="b9641-129">In the list of exports, select the export you want to duplicate.</span></span>

1. <span data-ttu-id="b9641-130">Seleccione **Crear duplicado** na barra de comandos para abrir o panel **Configurar exportación** cos detalles da exportación seleccionada.</span><span class="sxs-lookup"><span data-stu-id="b9641-130">Select **Create duplicate** in the command bar to open the **Set up export** pane with the details of the selected export.</span></span>

1. <span data-ttu-id="b9641-131">Revise e adapte a exportación e seleccione **Gardar** para crear unha nova exportación.</span><span class="sxs-lookup"><span data-stu-id="b9641-131">Review and adapt the export and select **Save** to create a new export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="b9641-132">Editar unha exportación</span><span class="sxs-lookup"><span data-stu-id="b9641-132">Edit an export</span></span>

1. <span data-ttu-id="b9641-133">Vaia a **Datos** > **Exportacións**.</span><span class="sxs-lookup"><span data-stu-id="b9641-133">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="b9641-134">Na lista de exportacións, seleccione a exportación que quere editar.</span><span class="sxs-lookup"><span data-stu-id="b9641-134">In the list of exports, select the export you want to edit.</span></span>

1. <span data-ttu-id="b9641-135">Seleccione **Editar** na barra de comandos.</span><span class="sxs-lookup"><span data-stu-id="b9641-135">Select **Edit** in the command bar.</span></span>

1. <span data-ttu-id="b9641-136">Cambie os valores que desexa actualizar e seccione **Gardar**.</span><span class="sxs-lookup"><span data-stu-id="b9641-136">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="b9641-137">Ver exportacións e detalles das exportacións</span><span class="sxs-lookup"><span data-stu-id="b9641-137">View exports and export details</span></span>

<span data-ttu-id="b9641-138">Despois de crear destinos de exportación, aparecen en **Datos** > **Exportacións**.</span><span class="sxs-lookup"><span data-stu-id="b9641-138">After creating export destinations, they're listed on **Data** > **Exports**.</span></span> <span data-ttu-id="b9641-139">Todos os usuarios poden ver que datos se comparten e o seu estado máis recente.</span><span class="sxs-lookup"><span data-stu-id="b9641-139">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="b9641-140">Vaia a **Datos** > **Exportacións**.</span><span class="sxs-lookup"><span data-stu-id="b9641-140">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="b9641-141">Os usuarios sen permisos de edición seleccionan **Ver** en vez de **Editar** para ver os detalles da exportación.</span><span class="sxs-lookup"><span data-stu-id="b9641-141">Users without edit permissions select **View** instead of **Edit** see the export details.</span></span>

1. <span data-ttu-id="b9641-142">O panel lateral mostra a configuración dunha exportación.</span><span class="sxs-lookup"><span data-stu-id="b9641-142">The side pane shows the configuration of an export.</span></span> <span data-ttu-id="b9641-143">Sen permisos de edición, non pode cambiar os valores.</span><span class="sxs-lookup"><span data-stu-id="b9641-143">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="b9641-144">Seleccione **Pechar** para volver á páxina de exportacións.</span><span class="sxs-lookup"><span data-stu-id="b9641-144">Select **Close** to return to the exports page.</span></span>

## <a name="schedule-and-run-exports"></a><span data-ttu-id="b9641-145">Programar e executar exportacións</span><span class="sxs-lookup"><span data-stu-id="b9641-145">Schedule and run exports</span></span>

<span data-ttu-id="b9641-146">Cada exportación que configura ten unha programación de actualización.</span><span class="sxs-lookup"><span data-stu-id="b9641-146">Each export you configure has a refresh schedule.</span></span> <span data-ttu-id="b9641-147">Durante unha actualización, o sistema busca datos novos ou actualizados para incluír nunha exportación.</span><span class="sxs-lookup"><span data-stu-id="b9641-147">During a refresh, the system looks for new or updated data to include in an export.</span></span> <span data-ttu-id="b9641-148">Por defecto, as exportacións execútanse como parte de todas as [actualización do sistema programadas](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="b9641-148">By default, exports are run as part of every [scheduled system refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="b9641-149">Pode personalizar a programación de actualización ou desactivala para executar as exportacións manualmente.</span><span class="sxs-lookup"><span data-stu-id="b9641-149">You can customize the refresh schedule or turn it off to run exports manually.</span></span>

<span data-ttu-id="b9641-150">As programacións de exportación dependen do estado do seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="b9641-150">Export schedules depend on the state of your environment.</span></span> <span data-ttu-id="b9641-151">Se hai actualizacións en [dependencias](system.md#refresh-policies) no progreso cando debería comezar unha exportación programada, o sistema primeiro completará as dependencias e logo executará a exportación.</span><span class="sxs-lookup"><span data-stu-id="b9641-151">If there are updates on [dependencies](system.md#refresh-policies) in progress when a scheduled export should start, the system will first complete the dependencies and then run the export.</span></span> <span data-ttu-id="b9641-152">Pode ver cando se actualizou por última vez unha exportación na columna **Actualizado**.</span><span class="sxs-lookup"><span data-stu-id="b9641-152">You can see when an export was last refreshed in column **Refreshed**.</span></span>

### <a name="schedule-exports"></a><span data-ttu-id="b9641-153">Programar exportacións</span><span class="sxs-lookup"><span data-stu-id="b9641-153">Schedule exports</span></span>

<span data-ttu-id="b9641-154">Pode definir programacións de actualización personalizadas para exportacións individuais ou varias exportacións á vez.</span><span class="sxs-lookup"><span data-stu-id="b9641-154">You can define custom refresh schedules for individual exports or several exports at once.</span></span> <span data-ttu-id="b9641-155">A programación definida actualmente aparece na columna **Programación** da lista de exportacións.</span><span class="sxs-lookup"><span data-stu-id="b9641-155">The currently defined schedule is listed in the **Schedule** column of the export list.</span></span> <span data-ttu-id="b9641-156">O permiso para cambiar a programación é o mesmo que para [editar e eliminar as exportacións](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="b9641-156">The permission to change the schedule is the same as for [editing and defining exports](export-destinations.md#set-up-a-new-export).</span></span> 

1. <span data-ttu-id="b9641-157">Vaia a **Datos** > **Exportacións**.</span><span class="sxs-lookup"><span data-stu-id="b9641-157">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="b9641-158">Seleccione a exportación que quere programar.</span><span class="sxs-lookup"><span data-stu-id="b9641-158">Select the export you want to schedule.</span></span>

1. <span data-ttu-id="b9641-159">Seleccione **Programar** na barra de comandos.</span><span class="sxs-lookup"><span data-stu-id="b9641-159">Select **Schedule** in the command bar.</span></span>

1. <span data-ttu-id="b9641-160">No panel **Programar exportación**, estableza **Programar execución** en **Activado** para executar a exportación automaticamente.</span><span class="sxs-lookup"><span data-stu-id="b9641-160">In the **Schedule export** pane, set the **Schedule run** to **On** to run the export automatically.</span></span> <span data-ttu-id="b9641-161">Establézaa en **Desactivado** para actualizala manualmente.</span><span class="sxs-lookup"><span data-stu-id="b9641-161">Set it to **Off** to refresh it manually.</span></span>

1. <span data-ttu-id="b9641-162">Para exportacións actualizadas automaticamente, escolla un valor de **Periodicidade** e especifique os seus detalles.</span><span class="sxs-lookup"><span data-stu-id="b9641-162">For automatically refreshed exports, choose a **Recurrence** value and specify the details for it.</span></span> <span data-ttu-id="b9641-163">A hora definida aplícase a todas instancias dunha periodicidade.</span><span class="sxs-lookup"><span data-stu-id="b9641-163">The time defined applies to all instances of a recurrence.</span></span> <span data-ttu-id="b9641-164">É a hora na que unha exportación debería comezar a actualizarse.</span><span class="sxs-lookup"><span data-stu-id="b9641-164">It's the time when an export should start refreshing.</span></span>

1. <span data-ttu-id="b9641-165">Aplique e active os cambios seleccionando **Gardar**.</span><span class="sxs-lookup"><span data-stu-id="b9641-165">Apply and activate your changes by selecting **Save**.</span></span>

<span data-ttu-id="b9641-166">Ao editar a programación de varias exportacións, ten que facer unha selección en **Manter ou anular programacións**:</span><span class="sxs-lookup"><span data-stu-id="b9641-166">When editing the schedule for several exports, you need to make a selection under **Keep or override schedules**:</span></span>
- <span data-ttu-id="b9641-167">**Manter programacións individuais**: continuar coa programación previamente definida para as exportacións seleccionadas e só desactivalas ou activalas.</span><span class="sxs-lookup"><span data-stu-id="b9641-167">**Keep individual schedules**: Persist the previously defined schedule for the selected exports and only disable or enable them.</span></span>
- <span data-ttu-id="b9641-168">**Definir unha nova programación para todas as exportación seleccionadas**: anular as programacións existentes das exportacións seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="b9641-168">**Define new schedule for all selected exports**: Override the existing schedules of the selected exports.</span></span>

### <a name="run-exports-on-demand"></a><span data-ttu-id="b9641-169">Executar exportacións a petición</span><span class="sxs-lookup"><span data-stu-id="b9641-169">Run exports on demand</span></span>

<span data-ttu-id="b9641-170">Para exportar datos sen esperar a unha actualización programada, vaia a **Datos** > **Exportacións**.</span><span class="sxs-lookup"><span data-stu-id="b9641-170">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span>

- <span data-ttu-id="b9641-171">Para executar todas as exportacións, seleccione **Executar todo** na barra de comandos.</span><span class="sxs-lookup"><span data-stu-id="b9641-171">To run all exports, select **Run all** in the command bar.</span></span> <span data-ttu-id="b9641-172">Esta acción só executará exportacións que teñen unha programación activa.</span><span class="sxs-lookup"><span data-stu-id="b9641-172">This action will only run exports that have an active schedule.</span></span>
- <span data-ttu-id="b9641-173">Para executar unha única exportación, selecciónea na lista e seleccione **Executar** na barra de comandos.</span><span class="sxs-lookup"><span data-stu-id="b9641-173">To run a single export, select it in the list and select **Run** in the command bar.</span></span> <span data-ttu-id="b9641-174">Así é como executa as exportacións sen programación activa.</span><span class="sxs-lookup"><span data-stu-id="b9641-174">That's how you run exports with no active schedule.</span></span> 

## <a name="remove-an-export"></a><span data-ttu-id="b9641-175">Eliminar unha exportación</span><span class="sxs-lookup"><span data-stu-id="b9641-175">Remove an Export</span></span>

1. <span data-ttu-id="b9641-176">Vaia a **Datos** > **Exportacións**.</span><span class="sxs-lookup"><span data-stu-id="b9641-176">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="b9641-177">Seleccione a exportación que desexe eliminar.</span><span class="sxs-lookup"><span data-stu-id="b9641-177">Select the export you want to remove.</span></span>

1. <span data-ttu-id="b9641-178">Seleccione **Eliminar** na barra de comandos.</span><span class="sxs-lookup"><span data-stu-id="b9641-178">Select **Remove** in the command bar.</span></span>

1. <span data-ttu-id="b9641-179">Confirme a eliminación seleccionando **Eliminar** na pantalla de confirmación.</span><span class="sxs-lookup"><span data-stu-id="b9641-179">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
