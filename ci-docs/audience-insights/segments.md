---
title: Crear e xestionar segmentos
description: Cree segmentos de clientes para agrupalos en función de varios atributos.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: jimsonc
manager: shellyha
ms.openlocfilehash: 6931110c2ae93cd2792d319aa5a34f0df3088552
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405745"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="79bc5-103">Crear e xestionar segmentos</span><span class="sxs-lookup"><span data-stu-id="79bc5-103">Create and manage segments</span></span>

<span data-ttu-id="79bc5-104">Os segmentos permiten agrupar aos seus clientes en función de atributos demográficos, transaccionais ou de comportamento.</span><span class="sxs-lookup"><span data-stu-id="79bc5-104">Segments let you group your customers based on demographic, transactional, or behavioral attributes.</span></span> <span data-ttu-id="79bc5-105">Pode usar segmentos para ter como obxectivo campañas promocionais, actividades de venda e accións de asistencia ao cliente para alcanzar os obxectivos da súa empresa.</span><span class="sxs-lookup"><span data-stu-id="79bc5-105">You can use segments to target promotional campaigns, sales activities, and customer support actions to achieve your business goals.</span></span>

<span data-ttu-id="79bc5-106">Pode definir filtros complexos arredor da entidade de Perfil do cliente e das entidades relacionadas.</span><span class="sxs-lookup"><span data-stu-id="79bc5-106">You can define complex filters around the Customer Profile entity and its related entities.</span></span> <span data-ttu-id="79bc5-107">Cada segmento, despois do procesamento, crea un conxunto de rexistros de clientes que pode exportar e nos que pode tomar medidas.</span><span class="sxs-lookup"><span data-stu-id="79bc5-107">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="79bc5-108">Algúns [límites de servizo](service-limits.md) aplican.</span><span class="sxs-lookup"><span data-stu-id="79bc5-108">Some [service limits](service-limits.md) apply.</span></span>

<span data-ttu-id="79bc5-109">A non ser que se indique o contrario, todos os segmentos son **Segmentos dinámicos**, que se actualizan nunha programación recorrente.</span><span class="sxs-lookup"><span data-stu-id="79bc5-109">Unless stated otherwise, all segments are **Dynamic segments**, which are refreshed on a recurring schedule.</span></span>

<span data-ttu-id="79bc5-110">O seguinte exemplo ilustra a capacidade de segmentación.</span><span class="sxs-lookup"><span data-stu-id="79bc5-110">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="79bc5-111">Definimos un segmento para clientes que solicitaron polo menos 500 $ de mercadorías nos últimos 90 días *e* que estiveron involucrados nunha chamada de servizo de atención ao cliente que se escalou.</span><span class="sxs-lookup"><span data-stu-id="79bc5-111">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="79bc5-112">![Múltiples grupos](media/segmentation-group1-2.png "Múltiples grupos")</span><span class="sxs-lookup"><span data-stu-id="79bc5-112">![Multiple groups](media/segmentation-group1-2.png "Multiple groups")</span></span>

## <a name="create-a-new-segment"></a><span data-ttu-id="79bc5-113">Crear un segmento novo</span><span class="sxs-lookup"><span data-stu-id="79bc5-113">Create a new segment</span></span>

<span data-ttu-id="79bc5-114">Os segmentos xestionanse na páxina **Segmentos**.</span><span class="sxs-lookup"><span data-stu-id="79bc5-114">Segments are managed on the **Segments** page.</span></span>

1. <span data-ttu-id="79bc5-115">Na información do público, vaia á páxina **Segmentos**.</span><span class="sxs-lookup"><span data-stu-id="79bc5-115">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="79bc5-116">Seleccione **Novo** > **Segmento en branco**.</span><span class="sxs-lookup"><span data-stu-id="79bc5-116">Select **New** > **Blank segment**.</span></span>

3. <span data-ttu-id="79bc5-117">No panel **Novo segmento**, escolla un tipo de segmento e proporcione un **Nome**.</span><span class="sxs-lookup"><span data-stu-id="79bc5-117">In the **New segment** pane, choose a segment type and provide a **Name**.</span></span>

   <span data-ttu-id="79bc5-118">Tamén pode proporcionar un nome para mostrar e unha descrición que axude a identificar o segmento.</span><span class="sxs-lookup"><span data-stu-id="79bc5-118">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

4. <span data-ttu-id="79bc5-119">Seleccione **Seguinte** para chegar á páxina **Construtor de segmentos** onde pode definir un grupo.</span><span class="sxs-lookup"><span data-stu-id="79bc5-119">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="79bc5-120">Un grupo é un conxunto de clientes.</span><span class="sxs-lookup"><span data-stu-id="79bc5-120">A group is a set of customers.</span></span>

5. <span data-ttu-id="79bc5-121">Escolla a entidade que inclúe o atributo polo que desexa segmentar.</span><span class="sxs-lookup"><span data-stu-id="79bc5-121">Choose the entity that includes the attribute you want to segment by.</span></span>

6. <span data-ttu-id="79bc5-122">Escolla o atributo polo que segmentar.</span><span class="sxs-lookup"><span data-stu-id="79bc5-122">Choose the attribute to segment by.</span></span> <span data-ttu-id="79bc5-123">Este atributo pode ter un dos catro tipos de valor seguintes: numérico, cadea, data ou booleano.</span><span class="sxs-lookup"><span data-stu-id="79bc5-123">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

7. <span data-ttu-id="79bc5-124">Escolla un operador e un valor para o atributo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="79bc5-124">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="79bc5-125">![Filtro de grupo personalizado](media/customer-group-numbers.png "Filtro de grupo de clientes")</span><span class="sxs-lookup"><span data-stu-id="79bc5-125">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="79bc5-126">Número</span><span class="sxs-lookup"><span data-stu-id="79bc5-126">Number</span></span> |<span data-ttu-id="79bc5-127">Definición</span><span class="sxs-lookup"><span data-stu-id="79bc5-127">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="79bc5-128">1</span><span class="sxs-lookup"><span data-stu-id="79bc5-128">1</span></span>     |<span data-ttu-id="79bc5-129">Entidad</span><span class="sxs-lookup"><span data-stu-id="79bc5-129">Entity</span></span>          |
   |<span data-ttu-id="79bc5-130">2</span><span class="sxs-lookup"><span data-stu-id="79bc5-130">2</span></span>     |<span data-ttu-id="79bc5-131">Atributo</span><span class="sxs-lookup"><span data-stu-id="79bc5-131">Attribute</span></span>          |
   |<span data-ttu-id="79bc5-132">3</span><span class="sxs-lookup"><span data-stu-id="79bc5-132">3</span></span>    |<span data-ttu-id="79bc5-133">Operador</span><span class="sxs-lookup"><span data-stu-id="79bc5-133">Operator</span></span>         |
   |<span data-ttu-id="79bc5-134">4</span><span class="sxs-lookup"><span data-stu-id="79bc5-134">4</span></span>    |<span data-ttu-id="79bc5-135">Valor</span><span class="sxs-lookup"><span data-stu-id="79bc5-135">Value</span></span>         |

8. <span data-ttu-id="79bc5-136">Se a entidade está conectada á entidade de cliente unificada mediante [relacións](relationships.md), necesita definir o camiño da relación para crear un segmento válido.</span><span class="sxs-lookup"><span data-stu-id="79bc5-136">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="79bc5-137">Engada as entidades do camiño da relación ata que poida seleccionar a entidade **Cliente: CustomerInsights** no menú despregable.</span><span class="sxs-lookup"><span data-stu-id="79bc5-137">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="79bc5-138">A continuación, elixa **Todos os rexistros** para cada condición.</span><span class="sxs-lookup"><span data-stu-id="79bc5-138">Then, choose **All records** for each condition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="79bc5-139">![Camiño de relación durante a creación do segmento](media/segments-multiple-relationships.png "Camiño de relación durante a creación do segmento")</span><span class="sxs-lookup"><span data-stu-id="79bc5-139">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

9. <span data-ttu-id="79bc5-140">Seleccione **Gardar** para gardar o segmento.</span><span class="sxs-lookup"><span data-stu-id="79bc5-140">Select **Save** to save your segment.</span></span> <span data-ttu-id="79bc5-141">O teu segmento gardarase e procesarase se todos os requisitos están validados.</span><span class="sxs-lookup"><span data-stu-id="79bc5-141">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="79bc5-142">Se non, gardarase como borrador.</span><span class="sxs-lookup"><span data-stu-id="79bc5-142">Otherwise, it will be saved as a draft.</span></span>

10. <span data-ttu-id="79bc5-143">Seleccione **Volver a segmentos** para volver á páxina **Segmentos**.</span><span class="sxs-lookup"><span data-stu-id="79bc5-143">Select **Back to segments** to go back to the **Segments** page.</span></span>

## <a name="manage-existing-segments"></a><span data-ttu-id="79bc5-144">Xestionar os segmentos existentes</span><span class="sxs-lookup"><span data-stu-id="79bc5-144">Manage existing segments</span></span>

<span data-ttu-id="79bc5-145">Na páxina **Segmentos**, pode ver todos os seus segmentos gardados e xestionalos.</span><span class="sxs-lookup"><span data-stu-id="79bc5-145">On the **Segments** page, you can view all your saved segments and manage them.</span></span>

<span data-ttu-id="79bc5-146">Cada segmento está representado por unha fila que inclúe información adicional sobre o segmento.</span><span class="sxs-lookup"><span data-stu-id="79bc5-146">Each segment is represented by a row that includes additional information about the segment.</span></span>

<span data-ttu-id="79bc5-147">Pode clasificar os segmentos nunha columna seleccionando a cabeceira da columna.</span><span class="sxs-lookup"><span data-stu-id="79bc5-147">You can sort the segments in a column by selecting the column heading.</span></span>

<span data-ttu-id="79bc5-148">Use a caixa **Buscar** na esquina superior dereita para filtrar os segmentos.</span><span class="sxs-lookup"><span data-stu-id="79bc5-148">Use the **Search** box in the top-right corner to filter the segments.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="79bc5-149">![Opcións para xestionar un segmento existente](media/segments-selected-segment.png "Opcións para xestionar un segmento existente")</span><span class="sxs-lookup"><span data-stu-id="79bc5-149">![Options to manage an existing segment](media/segments-selected-segment.png "Options to manage an existing segment")</span></span>

<span data-ttu-id="79bc5-150">A seguinte acción está dispoñible cando selecciona un segmento:</span><span class="sxs-lookup"><span data-stu-id="79bc5-150">The following action are available when you select a segment:</span></span>

- <span data-ttu-id="79bc5-151">**Visualice** os detalles do segmento, incluída a tendencia do total de membros e unha vista previa dos membros do segmento.</span><span class="sxs-lookup"><span data-stu-id="79bc5-151">**View** the segment details, including member count trend a preview of segment members.</span></span>
- <span data-ttu-id="79bc5-152">**Edite** o segmento para cambiar as súas propiedades.</span><span class="sxs-lookup"><span data-stu-id="79bc5-152">**Edit** the segment to change its properties.</span></span>
- <span data-ttu-id="79bc5-153">**Actualice** o segmento para incluír os últimos datos.</span><span class="sxs-lookup"><span data-stu-id="79bc5-153">**Refresh** the segment to include the latest data.</span></span>
- <span data-ttu-id="79bc5-154">**Active** ou **desactive** o segmento.</span><span class="sxs-lookup"><span data-stu-id="79bc5-154">**Activate** or **Deactivate** the segment.</span></span> <span data-ttu-id="79bc5-155">Os segmentos teñen dous estados posibles: activo ou inactivo.</span><span class="sxs-lookup"><span data-stu-id="79bc5-155">Segments have two possible states - active or inactive.</span></span> <span data-ttu-id="79bc5-156">Estes estados son útiles cando se edita un segmento.</span><span class="sxs-lookup"><span data-stu-id="79bc5-156">These states come in handy when editing a segment.</span></span> <span data-ttu-id="79bc5-157">Para os segmentos inactivos, existe a definición do segmento, pero aínda non contén ningún cliente.</span><span class="sxs-lookup"><span data-stu-id="79bc5-157">For inactive segments, the segment definition exists but it doesn't contain any customers yet.</span></span> <span data-ttu-id="79bc5-158">Cando activa un segmento, o seu estado cambia de "inactivo" a "activo" e comeza a buscar clientes que coincidan coa definición do segmento.</span><span class="sxs-lookup"><span data-stu-id="79bc5-158">When you activate a segment, its state changes from 'inactive' to 'active" and it starts looking for customers that match the segment definition.</span></span> <span data-ttu-id="79bc5-159">Se a [actualización programada](system.md#schedule-tab) está configurada, os segmentos inactivos teñen o **Estado** indicado como **Omitido**, o que indica que nin sequera se intentou actualizar.</span><span class="sxs-lookup"><span data-stu-id="79bc5-159">If a [scheduled refresh](system.md#schedule-tab) is configured, inactive segments have the **Status** listed as **Skipped**, indicating that a refresh wasn't even attempted.</span></span> <span data-ttu-id="79bc5-160">Cando se activa un segmento inactivo, actualizarase e incluirase nas actualizacións programadas.</span><span class="sxs-lookup"><span data-stu-id="79bc5-160">When an inactive segment is activated, it will refresh and will be included in scheduled refreshes.</span></span>
  <span data-ttu-id="79bc5-161">Alternativamente, pode usar a funcionalidade **Programar máis tarde** no menú despregable **Activar/Desactivar** para especificar unha data e hora futuras para a activación e desactivación dun determinado segmento.</span><span class="sxs-lookup"><span data-stu-id="79bc5-161">Alternatively, you can use the **Schedule later** functionality in the **Activate/Deactivate** dropdown to specify a future date and time for activation and deactivation of a particular segment.</span></span>
- <span data-ttu-id="79bc5-162">**Renomee** o segmento.</span><span class="sxs-lookup"><span data-stu-id="79bc5-162">**Rename** the segment.</span></span>
- <span data-ttu-id="79bc5-163">**Descargue** a lista de membros como ficheiro .CSV.</span><span class="sxs-lookup"><span data-stu-id="79bc5-163">**Download** the list of members as a .CSV file.</span></span>
- <span data-ttu-id="79bc5-164">A opción **Engadir a** envía a lista de ID de clientes no segmento para o seu procesamento noutra aplicación.</span><span class="sxs-lookup"><span data-stu-id="79bc5-164">**Add to** option sends the list of customer IDs in the segment for processing in another application.</span></span>
- <span data-ttu-id="79bc5-165">**Elimine** o segmento.</span><span class="sxs-lookup"><span data-stu-id="79bc5-165">**Delete** the segment.</span></span>

## <a name="refresh-segments"></a><span data-ttu-id="79bc5-166">Actualizar os segmentos</span><span class="sxs-lookup"><span data-stu-id="79bc5-166">Refresh segments</span></span>

<span data-ttu-id="79bc5-167">Pode actualizar todos os segmentos á vez seleccionando **Actualizar todo** na páxina **Segmentos** ou pode actualizar un ou varios segmentos cando os seleccione e elixir **Actualizar** desde as opcións.</span><span class="sxs-lookup"><span data-stu-id="79bc5-167">You can refresh all segments at once by selecting **Refresh all** on the **Segments** page or you can refresh one or multiple segments when you select them and choose **Refresh** in from the options.</span></span> <span data-ttu-id="79bc5-168">Tamén pode configurar unha actualización recorrente en **Administrador** > **Sistema** > **Programar**.</span><span class="sxs-lookup"><span data-stu-id="79bc5-168">Alternatively, you can configure a recurring refresh on **Admin** > **System** > **Schedule**.</span></span>

> [!TIP]
> <span data-ttu-id="79bc5-169">Existen [seis tipos de estado](system.md#status-types) para as tarefas ou os procesos.</span><span class="sxs-lookup"><span data-stu-id="79bc5-169">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="79bc5-170">Ademais, a maioría dos procesos [dependen doutros procesos descendentes](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="79bc5-170">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="79bc5-171">Pode seleccionar o estado dun proceso para ver detalles sobre o progreso de todo o traballo.</span><span class="sxs-lookup"><span data-stu-id="79bc5-171">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="79bc5-172">Despois de seleccionar **Ver detalles** para unha das tarefas do traballo, atopará información adicional: o tempo de procesamento, a última data de procesamento e todos os erros e avisos asociados á tarefa.</span><span class="sxs-lookup"><span data-stu-id="79bc5-172">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="download-and-export-segments"></a><span data-ttu-id="79bc5-173">Descargar e exportar segmentos</span><span class="sxs-lookup"><span data-stu-id="79bc5-173">Download and export segments</span></span>

<span data-ttu-id="79bc5-174">Pode descargar os seus segmentos a un ficheiro CSV ou exportalos a Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="79bc5-174">You can download your segments to a CSV file or export them to Dynamics 365 Sales.</span></span>

### <a name="download-segments-to-a-csv-file"></a><span data-ttu-id="79bc5-175">Descargar segmentos a un ficheiro CSV</span><span class="sxs-lookup"><span data-stu-id="79bc5-175">Download segments to a CSV file</span></span>

1. <span data-ttu-id="79bc5-176">Na información do público, vaia á páxina **Segmentos**.</span><span class="sxs-lookup"><span data-stu-id="79bc5-176">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="79bc5-177">Seleccione os tres puntos no mosaico dun segmento específico.</span><span class="sxs-lookup"><span data-stu-id="79bc5-177">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="79bc5-178">Seleccione **Descargar como CSV** da lista despregable de accións.</span><span class="sxs-lookup"><span data-stu-id="79bc5-178">Select **Download as CSV** from the actions drop-down list.</span></span>

### <a name="export-segments-to-dynamics-365-sales"></a><span data-ttu-id="79bc5-179">Exportar segmentos a Dynamics 365 Sales</span><span class="sxs-lookup"><span data-stu-id="79bc5-179">Export segments to Dynamics 365 Sales</span></span>

<span data-ttu-id="79bc5-180">Antes de exportar segmentos a Dynamics 365 Sales, un administrador precisa [crear o destino de exportación](export-destinations.md) para Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="79bc5-180">Before exporting segments to Dynamics 365 Sales, an admin needs to [create the export destination](export-destinations.md) for Dynamics 365 Sales.</span></span>

1. <span data-ttu-id="79bc5-181">Na información do público, vaia á páxina **Segmentos**.</span><span class="sxs-lookup"><span data-stu-id="79bc5-181">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="79bc5-182">Seleccione os tres puntos no mosaico dun segmento específico.</span><span class="sxs-lookup"><span data-stu-id="79bc5-182">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="79bc5-183">Seleccione **Engadir a** na lista despregable de accións e seleccione o destino de exportación ao que desexa enviar os datos.</span><span class="sxs-lookup"><span data-stu-id="79bc5-183">Select **Add to** from the actions drop-down list and select the export destination you want to send the data to.</span></span>

## <a name="draft-mode-for-segments"></a><span data-ttu-id="79bc5-184">Modo de borrador para segmentos</span><span class="sxs-lookup"><span data-stu-id="79bc5-184">Draft mode for segments</span></span>

<span data-ttu-id="79bc5-185">Se non se cumpren todos os requisitos para procesar un segmento, pode gardar o segmento como borrador e acceder a el desde a páxina **Segmentos**.</span><span class="sxs-lookup"><span data-stu-id="79bc5-185">If not all requirements to process a segment are met, you can save the segment as a draft and access it from the **Segments** page.</span></span>

<span data-ttu-id="79bc5-186">Gardarase como segmento inactivo e non se poderá activar ata que sexa válido.</span><span class="sxs-lookup"><span data-stu-id="79bc5-186">It will be saved as an inactive segment, and can't be activated it until it's valid.</span></span>

## <a name="add-more-conditions-to-a-group"></a><span data-ttu-id="79bc5-187">Engadir máis condicións a un grupo</span><span class="sxs-lookup"><span data-stu-id="79bc5-187">Add more conditions to a group</span></span>

<span data-ttu-id="79bc5-188">Para engadir máis condicións a un grupo, pode usar dous operadores lóxicos:</span><span class="sxs-lookup"><span data-stu-id="79bc5-188">To add more conditions to a group, you can use two logical operators:</span></span>

- <span data-ttu-id="79bc5-189">Operador **AND**: as dúas condicións deben cumprirse como parte do proceso de segmentación.</span><span class="sxs-lookup"><span data-stu-id="79bc5-189">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="79bc5-190">Esta opción é máis útil cando define condicións entre diferentes entidades.</span><span class="sxs-lookup"><span data-stu-id="79bc5-190">This option is most useful when you define conditions across different entities.</span></span>

- <span data-ttu-id="79bc5-191">Operador **OR**: calquera das condicións debe ser cumprida como parte do proceso de segmentación.</span><span class="sxs-lookup"><span data-stu-id="79bc5-191">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="79bc5-192">Esta opción é máis útil cando define varias condicións para a mesma entidade.</span><span class="sxs-lookup"><span data-stu-id="79bc5-192">This option is most useful when you define multiple conditions for the same entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="79bc5-193">![Operador OR onde se debe cumprir calquera das dúas condicións](media/segmentation-either-condition.png "Operador OR onde se debe cumprir calquera das dúas condicións")</span><span class="sxs-lookup"><span data-stu-id="79bc5-193">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

<span data-ttu-id="79bc5-194">Actualmente é posible aniñar un operador **OR** baixo un operador **AND**, pero non ao revés.</span><span class="sxs-lookup"><span data-stu-id="79bc5-194">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

## <a name="combine-multiple-groups"></a><span data-ttu-id="79bc5-195">Combinar varios grupos</span><span class="sxs-lookup"><span data-stu-id="79bc5-195">Combine multiple groups</span></span>

<span data-ttu-id="79bc5-196">Cada grupo produce un conxunto específico de clientes.</span><span class="sxs-lookup"><span data-stu-id="79bc5-196">Each group produces a specific set of customers.</span></span> <span data-ttu-id="79bc5-197">Pode combinar estes grupos para incluír os clientes necesarios para a súa empresa.</span><span class="sxs-lookup"><span data-stu-id="79bc5-197">You can combine these groups to include the customers required for your business case.</span></span>

1. <span data-ttu-id="79bc5-198">Na información do público, vaia á páxina **Segmentos** e seleccione un segmento.</span><span class="sxs-lookup"><span data-stu-id="79bc5-198">In audience insights, go to the **Segments** page and select a segment.</span></span>

2. <span data-ttu-id="79bc5-199">Seleccione **Engadir grupo**.</span><span class="sxs-lookup"><span data-stu-id="79bc5-199">Select **Add Group**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="79bc5-200">![Grupo de engadir grupo de clientes](media/customer-group-add-group.png "Grupo de engadir grupo de clientes")</span><span class="sxs-lookup"><span data-stu-id="79bc5-200">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

3. <span data-ttu-id="79bc5-201">Seleccione un dos seguintes operadores de conxunto: **Unión**, **Intersección** ou **Excepto**.</span><span class="sxs-lookup"><span data-stu-id="79bc5-201">Select one of the following set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="79bc5-202">![Unión de engadir grupo de clientes](media/customer-group-union.png "Unión de engadir grupo de clientes")</span><span class="sxs-lookup"><span data-stu-id="79bc5-202">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   <span data-ttu-id="79bc5-203">Seleccione un operador definido para definir un novo grupo.</span><span class="sxs-lookup"><span data-stu-id="79bc5-203">Select a set operator to define a new group.</span></span> <span data-ttu-id="79bc5-204">Garde diferentes grupos para determinar que datos se reteñen:</span><span class="sxs-lookup"><span data-stu-id="79bc5-204">Save different groups to determine what data gets retained:</span></span>

   - <span data-ttu-id="79bc5-205">**Unión** une os dous grupos.</span><span class="sxs-lookup"><span data-stu-id="79bc5-205">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="79bc5-206">**Intersección** solapa os dous grupos.</span><span class="sxs-lookup"><span data-stu-id="79bc5-206">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="79bc5-207">Só datos que *son comúns* a ambos os grupos mantéñense no grupo unificado.</span><span class="sxs-lookup"><span data-stu-id="79bc5-207">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="79bc5-208">**Excepto** combina os dous grupos.</span><span class="sxs-lookup"><span data-stu-id="79bc5-208">**Except** combines the two groups.</span></span> <span data-ttu-id="79bc5-209">Só datos do grupo A que *non son comúns* aos datos do grupo B mantéñense.</span><span class="sxs-lookup"><span data-stu-id="79bc5-209">Only data in group A that *is not common* to data in group B is retained.</span></span>

## <a name="view-processing-history-and-segment-members"></a><span data-ttu-id="79bc5-210">Ver o historial de procesamento e os membros do segmento</span><span class="sxs-lookup"><span data-stu-id="79bc5-210">View processing history and segment members</span></span>

<span data-ttu-id="79bc5-211">Pode ver datos consolidados sobre un segmento revisando os seus detalles.</span><span class="sxs-lookup"><span data-stu-id="79bc5-211">You can see consolidated data about a segment by reviewing its details.</span></span>

<span data-ttu-id="79bc5-212">Na páxina **Segmentos**, seleccione o segmento que desexe revisar.</span><span class="sxs-lookup"><span data-stu-id="79bc5-212">On the **Segments** page, select the segment you want to review.</span></span>

<span data-ttu-id="79bc5-213">A parte superior da páxina inclúe un gráfico de tendencias que mostra os cambios no total de membros.</span><span class="sxs-lookup"><span data-stu-id="79bc5-213">The upper part of the page includes a trend graph that visualizes changes in member count.</span></span> <span data-ttu-id="79bc5-214">Pase o punteiro sobre os puntos de datos para ver o total de membros dunha data específica.</span><span class="sxs-lookup"><span data-stu-id="79bc5-214">Hover over data points to see the member count on a specific date.</span></span>

<span data-ttu-id="79bc5-215">Pode actualizar o intervalo temporal da visualización.</span><span class="sxs-lookup"><span data-stu-id="79bc5-215">You can update the time frame of the visualization.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="79bc5-216">![Intervalo de tempo do segmento](media/segment-time-range.png "Intervalo de tempo do segmento")</span><span class="sxs-lookup"><span data-stu-id="79bc5-216">![Segment time range](media/segment-time-range.png "Segment time range")</span></span>

<span data-ttu-id="79bc5-217">A parte inferior contén unha lista dos membros do segmento.</span><span class="sxs-lookup"><span data-stu-id="79bc5-217">The lower part contains a list of the segment members.</span></span>

> [!NOTE]
> <span data-ttu-id="79bc5-218">Os campos que aparecen nesta lista baséanse nos atributos das entidades do seu segmento.</span><span class="sxs-lookup"><span data-stu-id="79bc5-218">Fields that appear in this list are based on the attributes of your segment's entities.</span></span>
>
><span data-ttu-id="79bc5-219">A lista é unha vista previa dos membros do segmento correspondentes e mostra os primeiros 100 rexistros do seu segmento para que poida avalialo rapidamente e revisar as súas definicións se é necesario.</span><span class="sxs-lookup"><span data-stu-id="79bc5-219">The list is a preview of the matching segment members and shows the first 100 records of your segment so that you can quickly evaluate it and review its definitions if needed.</span></span> <span data-ttu-id="79bc5-220">Para ver todos os rexistros coincidentes, cómpre [exportar o segmento](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="79bc5-220">To see all matching records, you need to [export the segment](export-destinations.md).</span></span>

## <a name="quick-segments"></a><span data-ttu-id="79bc5-221">Segmentos rápidos</span><span class="sxs-lookup"><span data-stu-id="79bc5-221">Quick segments</span></span>

<span data-ttu-id="79bc5-222">Ademais do creador de segmentos, hai outro camiño para crear segmentos.</span><span class="sxs-lookup"><span data-stu-id="79bc5-222">In addition to the segment builder, there's another path for creating segments.</span></span> <span data-ttu-id="79bc5-223">Os segmentos rápidos permítenlle construír segmentos sinxelos cun único operador de forma rápida e con información instantánea.</span><span class="sxs-lookup"><span data-stu-id="79bc5-223">Quick segments let you build simple segments with a single operator quickly and with instant insights.</span></span>

1. <span data-ttu-id="79bc5-224">Na páxina **Segmentos**, seleccione **Novo** > **Crear rapidamente desde**.</span><span class="sxs-lookup"><span data-stu-id="79bc5-224">On the **Segments** page, select **New** > **Quickly create from**.</span></span>

   - <span data-ttu-id="79bc5-225">Seleccione a opción **Perfís** para construír un segmento baseado na entidade de cliente unificada.</span><span class="sxs-lookup"><span data-stu-id="79bc5-225">Select the **Profiles** option to build a segment that is based on the unified Customer entity.</span></span>
   - <span data-ttu-id="79bc5-226">Seleccione a opción **Medicións** para crear un segmento arredor de cada un dos tipos de medidas do atributo de cliente que creou anteriormente na páxina **Medicións**.</span><span class="sxs-lookup"><span data-stu-id="79bc5-226">Select the **Measures** option to build a segment around each of the Customer Attribute type of measures you have previously created on the **Measures** page.</span></span>
   - <span data-ttu-id="79bc5-227">Seleccione a opción **Intelixencia** para construír un segmento arredor dunha das entidades de saída que xerou usando calquera das funcións de **Predicións** ou **Modelos personalizados**.</span><span class="sxs-lookup"><span data-stu-id="79bc5-227">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="79bc5-228">Na caixa de diálogo **Novo segmento rápido**, seleccione un atributo no menú despregable **Campo**.</span><span class="sxs-lookup"><span data-stu-id="79bc5-228">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="79bc5-229">O sistema proporcionará información adicional que lle axudará a crear mellores segmentos dos seus clientes.</span><span class="sxs-lookup"><span data-stu-id="79bc5-229">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="79bc5-230">Por campos categóricos, mostraremos as 10 contas máis importantes de clientes.</span><span class="sxs-lookup"><span data-stu-id="79bc5-230">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="79bc5-231">Escolla un **Valor** e seleccione **Revisar**.</span><span class="sxs-lookup"><span data-stu-id="79bc5-231">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="79bc5-232">Para un atributo numérico, o sistema mostrará que valor de atributo está no percentil de cada cliente.</span><span class="sxs-lookup"><span data-stu-id="79bc5-232">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="79bc5-233">Elixa un **Operador** e un **Valor** e logo seleccione **Revisar**.</span><span class="sxs-lookup"><span data-stu-id="79bc5-233">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="79bc5-234">O sistema forneceralle un **Tamaño de segmento estimado**.</span><span class="sxs-lookup"><span data-stu-id="79bc5-234">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="79bc5-235">Pode escoller se quere xerar o segmento que definiu ou primeiro revisalo para obter un tamaño de segmento diferente.</span><span class="sxs-lookup"><span data-stu-id="79bc5-235">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="79bc5-236">![Nome e estimación para un segmento rápido](media/quick-segment-name.png "Nome e estimación para un segmento rápido")</span><span class="sxs-lookup"><span data-stu-id="79bc5-236">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="79bc5-237">Proporcione un **Nome** para o segmento.</span><span class="sxs-lookup"><span data-stu-id="79bc5-237">Provide a **Name** for your segment.</span></span> <span data-ttu-id="79bc5-238">Tamén pode fornecer un **nome para mostrar**.</span><span class="sxs-lookup"><span data-stu-id="79bc5-238">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="79bc5-239">Seleccione **Gardar** para crear o seu segmento.</span><span class="sxs-lookup"><span data-stu-id="79bc5-239">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="79bc5-240">Despois de que o segmento remate de procesarse, pode visualizalo como calquera outro segmento que crease.</span><span class="sxs-lookup"><span data-stu-id="79bc5-240">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

<span data-ttu-id="79bc5-241">Para as seguintes situacións, aconsellamos usar o creador de segmentos en lugar da capacidade de segmentos recomendada:</span><span class="sxs-lookup"><span data-stu-id="79bc5-241">For the following scenarios, we advise using the segment builder rather than the recommended segments capability:</span></span>

- <span data-ttu-id="79bc5-242">Creación de segmentos con filtros en campos categóricos nos que o operador é diferente de **IS**</span><span class="sxs-lookup"><span data-stu-id="79bc5-242">Creating segments with filters on categorical fields where the operator is different than the **Is** operator</span></span>
- <span data-ttu-id="79bc5-243">Creación de segmentos con filtros en campos numéricos nos que o operador é diferente de **Between**, **Greater than** e **Less than**</span><span class="sxs-lookup"><span data-stu-id="79bc5-243">Creating segments with filters on numerical fields where the operator is different than the **Between**, **Greater than**, and **Less than** operators</span></span>
- <span data-ttu-id="79bc5-244">Creación de segmentos con filtros en campos de tipo de data</span><span class="sxs-lookup"><span data-stu-id="79bc5-244">Creating segments with filters on date type fields</span></span>

## <a name="next-steps"></a><span data-ttu-id="79bc5-245">Seguintes pasos</span><span class="sxs-lookup"><span data-stu-id="79bc5-245">Next steps</span></span>

<span data-ttu-id="79bc5-246">[Exporte un segmento](export-destinations.md) e explore a [Tarxeta de cliente](customer-card-add-in.md) e os [conectores](export-power-bi.md) para obter información sobre o nivel de cliente.</span><span class="sxs-lookup"><span data-stu-id="79bc5-246">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>
