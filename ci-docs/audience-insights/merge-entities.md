---
title: Combinar entidades na unificación de datos
description: Combine entidades para crear perfís de clientes unificados.
ms.date: 05/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 86ab3cefa70e5fab4bdb27cde363adee26efee4c
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305633"
---
# <a name="merge-entities"></a><span data-ttu-id="0bafe-103">Combinar entidades</span><span class="sxs-lookup"><span data-stu-id="0bafe-103">Merge entities</span></span>

<span data-ttu-id="0bafe-104">A fase de combinación é a última fase do proceso de unificación de datos.</span><span class="sxs-lookup"><span data-stu-id="0bafe-104">The merge phase is the last phase in the data unification process.</span></span> <span data-ttu-id="0bafe-105">O seu propósito é conciliar datos conflitivos.</span><span class="sxs-lookup"><span data-stu-id="0bafe-105">Its purpose is reconciling conflicting data.</span></span> <span data-ttu-id="0bafe-106">Como exemplos de datos en conflito poden incluírse un nome de cliente que se atopa en dous dos seus conxuntos de datos pero aparece un pouco diferente en cada un ("Grant Marshall" fronte a "Grant Marshal") ou un número de teléfono que difire en formato (617-803-091X fronte a 617803091X).</span><span class="sxs-lookup"><span data-stu-id="0bafe-106">Examples of conflicting data could include a customer name found in two of your datasets but that shows up a little differently in each ("Grant Marshall" versus "Grant Marshal"), or a phone number that differs in format (617-803-091X versus 617803091X).</span></span> <span data-ttu-id="0bafe-107">A fusión deses puntos de datos conflitivos realízase atributo por atributo.</span><span class="sxs-lookup"><span data-stu-id="0bafe-107">Merging those conflicting data points is done on an attribute-by-attribute basis.</span></span>

:::image type="content" source="media/merge-fields-page.png" alt-text="Páxina Combinar no proceso de unificación de datos que mostra a táboa cos campos combinados que definen o perfil de cliente unificado.":::

<span data-ttu-id="0bafe-109">Despois de completar a [fase de correspondencia](match-entities.md), pode iniciar a fase de combinación seleccionando o mosaico **Combinar** na páxina **Unificar**.</span><span class="sxs-lookup"><span data-stu-id="0bafe-109">After completing the [match phase](match-entities.md), you start the merge phase by selecting the **Merge** tile on the **Unify** page.</span></span>

## <a name="review-system-recommendations"></a><span data-ttu-id="0bafe-110">Revisar recomendacións do sistema</span><span class="sxs-lookup"><span data-stu-id="0bafe-110">Review system recommendations</span></span>

<span data-ttu-id="0bafe-111">En **Datos** > **Unificar** > **Combinar**, escolla e exclúa atributos para combinar na súa entidade de perfil de cliente unificado.</span><span class="sxs-lookup"><span data-stu-id="0bafe-111">On **Data** > **Unify** > **Merge**, you choose and exclude attributes to merge within your unified customer profile entity.</span></span> <span data-ttu-id="0bafe-112">O perfil de cliente unificado é o resultado do proceso de unificación de datos.</span><span class="sxs-lookup"><span data-stu-id="0bafe-112">The unified customer profile is the result of the data unification process.</span></span> <span data-ttu-id="0bafe-113">Algúns atributos os combina automaticamente o sistema.</span><span class="sxs-lookup"><span data-stu-id="0bafe-113">Some attributes are automatically merged by the system.</span></span>

<span data-ttu-id="0bafe-114">Para ver os atributos incluídos nun dos atributos combinados automaticamente, seleccione ese atributo combinado no separador **Campos do cliente** da táboa.</span><span class="sxs-lookup"><span data-stu-id="0bafe-114">To view the attributes that are included in one of your automatically merged attributes, select that merged attribute in the **Customer fields** tab of the table.</span></span> <span data-ttu-id="0bafe-115">Os atributos que compoñen este atributo combinado móstranse en dúas novas filas baixo o atributo combinado.</span><span class="sxs-lookup"><span data-stu-id="0bafe-115">The attributes that compose that merged attribute display in two new rows beneath the merged attribute.</span></span>

## <a name="separate-rename-exclude-and-edit-merged-fields"></a><span data-ttu-id="0bafe-116">Separar, renomear, excluír e editar campos combinados</span><span class="sxs-lookup"><span data-stu-id="0bafe-116">Separate, rename, exclude, and edit merged fields</span></span>

<span data-ttu-id="0bafe-117">Pode modificar a forma en que o sistema procesa os atributos combinados para xerar o perfil de cliente unificado.</span><span class="sxs-lookup"><span data-stu-id="0bafe-117">You can change how the system processes merged attributes to generate the unified customer profile.</span></span> <span data-ttu-id="0bafe-118">Seleccione **Mostrar máis** e elixa o que quere modificar.</span><span class="sxs-lookup"><span data-stu-id="0bafe-118">Select **Show more** and choose what you want to change.</span></span>

:::image type="content" source="media/manage-merged-attributes.png" alt-text="Opcións do menú despregable Mostrar máis para xestionar atributos combinados.":::

<span data-ttu-id="0bafe-120">Para obter máis información, consulte as seccións seguintes.</span><span class="sxs-lookup"><span data-stu-id="0bafe-120">For more information, see the following sections.</span></span>

## <a name="separate-merged-fields"></a><span data-ttu-id="0bafe-121">Separar campos combinados</span><span class="sxs-lookup"><span data-stu-id="0bafe-121">Separate merged fields</span></span>

<span data-ttu-id="0bafe-122">Para separar campos combinados, busque o atributo na táboa.</span><span class="sxs-lookup"><span data-stu-id="0bafe-122">To separate merged fields, find the attribute in the table.</span></span> <span data-ttu-id="0bafe-123">Os campos separados móstranse como puntos de datos individuais no perfil de cliente unificado.</span><span class="sxs-lookup"><span data-stu-id="0bafe-123">Separated fields show as individual data points on the unified customer profile.</span></span> 

1. <span data-ttu-id="0bafe-124">Seleccione o campo combinado.</span><span class="sxs-lookup"><span data-stu-id="0bafe-124">Select the merged field.</span></span>
  
1. <span data-ttu-id="0bafe-125">Seleccione **Mostrar máis** e elixa **Campos independentes**.</span><span class="sxs-lookup"><span data-stu-id="0bafe-125">Select **Show more** and choose **Separate fields**.</span></span>
 
1. <span data-ttu-id="0bafe-126">Confirme a separación.</span><span class="sxs-lookup"><span data-stu-id="0bafe-126">Confirm the separation.</span></span>

1. <span data-ttu-id="0bafe-127">Seleccione **Gardar** e **Executar** para procesar as modificacións.</span><span class="sxs-lookup"><span data-stu-id="0bafe-127">Select **Save** and **Run** to process the changes.</span></span>

## <a name="rename-merged-fields"></a><span data-ttu-id="0bafe-128">Renomear campos combinados</span><span class="sxs-lookup"><span data-stu-id="0bafe-128">Rename merged fields</span></span>

<span data-ttu-id="0bafe-129">Modifique o nome para mostrar dos atributos combinados.</span><span class="sxs-lookup"><span data-stu-id="0bafe-129">Change the display name of merged attributes.</span></span> <span data-ttu-id="0bafe-130">Non pode modificar o nome da entidade de saída.</span><span class="sxs-lookup"><span data-stu-id="0bafe-130">You can't change the name of the output entity.</span></span>

1. <span data-ttu-id="0bafe-131">Seleccione o campo combinado.</span><span class="sxs-lookup"><span data-stu-id="0bafe-131">Select the merged field.</span></span>
  
1. <span data-ttu-id="0bafe-132">Seleccione **Mostrar máis** e elixa **Renomear**.</span><span class="sxs-lookup"><span data-stu-id="0bafe-132">Select **Show more** and choose **Rename**.</span></span>

1. <span data-ttu-id="0bafe-133">Confirme o nome para mostrar modificado.</span><span class="sxs-lookup"><span data-stu-id="0bafe-133">Confirm the changed display name.</span></span> 

1. <span data-ttu-id="0bafe-134">Seleccione **Gardar** e **Executar** para procesar as modificacións.</span><span class="sxs-lookup"><span data-stu-id="0bafe-134">Select **Save** and **Run** to process the changes.</span></span>

## <a name="exclude-merged-fields"></a><span data-ttu-id="0bafe-135">Excluír campos combinados</span><span class="sxs-lookup"><span data-stu-id="0bafe-135">Exclude merged fields</span></span>

<span data-ttu-id="0bafe-136">Exclúa un atributo do perfil de cliente unificado.</span><span class="sxs-lookup"><span data-stu-id="0bafe-136">Exclude an attribute from the unified customer profile.</span></span> <span data-ttu-id="0bafe-137">Se o campo se usa noutros procesos, por exemplo nun segmento, elimíneo deses procesos antes de excluílo do perfil do cliente.</span><span class="sxs-lookup"><span data-stu-id="0bafe-137">If the field is used in other processes, for example in a segment, remove it from these processes before excluding it from the customer profile.</span></span> 

1. <span data-ttu-id="0bafe-138">Seleccione o campo combinado.</span><span class="sxs-lookup"><span data-stu-id="0bafe-138">Select the merged field.</span></span>
  
1. <span data-ttu-id="0bafe-139">Seleccione **Mostrar máis** e elixa **Excluír**.</span><span class="sxs-lookup"><span data-stu-id="0bafe-139">Select **Show more** and choose **Exclude**.</span></span>

1. <span data-ttu-id="0bafe-140">Confirme a exclusión.</span><span class="sxs-lookup"><span data-stu-id="0bafe-140">Confirm the exclusion.</span></span>

1. <span data-ttu-id="0bafe-141">Seleccione **Gardar** e **Executar** para procesar as modificacións.</span><span class="sxs-lookup"><span data-stu-id="0bafe-141">Select **Save** and **Run** to process the changes.</span></span> 

<span data-ttu-id="0bafe-142">Na páxina **Combinar**, seleccione **Campos excluídos** para ver a lista de todos os campos excluídos.</span><span class="sxs-lookup"><span data-stu-id="0bafe-142">On the **Merge** page, select **Excluded fields** to see the list of all excluded fields.</span></span> <span data-ttu-id="0bafe-143">Este panel permítelle volver engadir campos excluídos.</span><span class="sxs-lookup"><span data-stu-id="0bafe-143">This pane lets you add excluded fields back.</span></span>

## <a name="manually-combine-fields"></a><span data-ttu-id="0bafe-144">Combinar campos manualmente</span><span class="sxs-lookup"><span data-stu-id="0bafe-144">Manually combine fields</span></span>

<span data-ttu-id="0bafe-145">Especifique un atributo combinado manualmente.</span><span class="sxs-lookup"><span data-stu-id="0bafe-145">Specify a merged attribute manually.</span></span> 

1. <span data-ttu-id="0bafe-146">Na páxina **Combinar**, seleccione **Combinar campos**.</span><span class="sxs-lookup"><span data-stu-id="0bafe-146">On the **Merge** page, select **Combine fields**.</span></span>

1. <span data-ttu-id="0bafe-147">Forneza un **Nome** e un **Nome do campo de saída**.</span><span class="sxs-lookup"><span data-stu-id="0bafe-147">Provide a **Name** and an **Output field name**.</span></span>

1. <span data-ttu-id="0bafe-148">Escolla o campo que quere engadir.</span><span class="sxs-lookup"><span data-stu-id="0bafe-148">Choose a field to add.</span></span> <span data-ttu-id="0bafe-149">Seleccione **Engadir campos** para combinar máis campos.</span><span class="sxs-lookup"><span data-stu-id="0bafe-149">Select **Add fields** to combine more fields.</span></span>

1. <span data-ttu-id="0bafe-150">Confirme a exclusión.</span><span class="sxs-lookup"><span data-stu-id="0bafe-150">Confirm the exclusion.</span></span>

1. <span data-ttu-id="0bafe-151">Seleccione **Gardar** e **Executar** para procesar as modificacións.</span><span class="sxs-lookup"><span data-stu-id="0bafe-151">Select **Save** and **Run** to process the changes.</span></span> 

## <a name="change-the-order-of-fields"></a><span data-ttu-id="0bafe-152">Modificar a orde dos campos</span><span class="sxs-lookup"><span data-stu-id="0bafe-152">Change the order of fields</span></span>

<span data-ttu-id="0bafe-153">Algunhas entidades conteñen máis detalles que outras.</span><span class="sxs-lookup"><span data-stu-id="0bafe-153">Some entities contain more details than others.</span></span> <span data-ttu-id="0bafe-154">Se unha entidade inclúe os últimos datos sobre un campo, pode darlle prioridade sobre outras entidades ao combinar valores.</span><span class="sxs-lookup"><span data-stu-id="0bafe-154">If an entity includes the latest data about a field, you can prioritize it over other entities when merging values.</span></span>

1. <span data-ttu-id="0bafe-155">Seleccione o campo combinado.</span><span class="sxs-lookup"><span data-stu-id="0bafe-155">Select the merged field.</span></span>
  
1. <span data-ttu-id="0bafe-156">Seleccione **Mostrar máis** e elixa **Editar**.</span><span class="sxs-lookup"><span data-stu-id="0bafe-156">Select **Show more** and choose **Edit**.</span></span>

1. <span data-ttu-id="0bafe-157">No panel **Combinar campos**, seleccione **Mover cara arriba ou cara abaixo** para establecer a orde ou arrastre e solte na posición desexada.</span><span class="sxs-lookup"><span data-stu-id="0bafe-157">In the **Combine fields** pane, select **Move up/down** to set the order or drag and drop them in the desired position.</span></span>

1. <span data-ttu-id="0bafe-158">Confirme a modificación.</span><span class="sxs-lookup"><span data-stu-id="0bafe-158">Confirm the change.</span></span>

1. <span data-ttu-id="0bafe-159">Seleccione **Gardar** e **Executar** para procesar as modificacións.</span><span class="sxs-lookup"><span data-stu-id="0bafe-159">Select **Save** and **Run** to process the changes.</span></span>

## <a name="run-your-merge"></a><span data-ttu-id="0bafe-160">Execute a súa combinación</span><span class="sxs-lookup"><span data-stu-id="0bafe-160">Run your merge</span></span>

<span data-ttu-id="0bafe-161">Tanto se combina manualmente atributos ou deixa que o sistema os combine, sempre pode executar a súa combinación.</span><span class="sxs-lookup"><span data-stu-id="0bafe-161">Whether you manually merge attributes or let the system merge them, you can always run your merge.</span></span> <span data-ttu-id="0bafe-162">Seleccione **Executar** na páxina **Combinar** para iniciar o proceso.</span><span class="sxs-lookup"><span data-stu-id="0bafe-162">Select **Run** on the **Merge** page to start the process.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="0bafe-163">![Almacenamento e execución da combinación de datos](media/configure-data-merge-save-run.png "Almacenamento e execución da combinación de datos")</span><span class="sxs-lookup"><span data-stu-id="0bafe-163">![Data merge Save and Run](media/configure-data-merge-save-run.png "Data merge Save and Run")</span></span>

<span data-ttu-id="0bafe-164">Escolla **Executar só combinación** se só quere ver a saída reflectida na entidade de cliente unificada.</span><span class="sxs-lookup"><span data-stu-id="0bafe-164">Choose **Run only Merge** if you only want to see the output reflected in the unified customer entity.</span></span> <span data-ttu-id="0bafe-165">Os procesos descendentes actualizaranse segundo [se estableza na programación de actualización](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="0bafe-165">Downstream processes will be refreshed as [defined in the refresh schedule](system.md#schedule-tab).</span></span>

<span data-ttu-id="0bafe-166">Escolla **Executar combinación e procesos descendentes** para actualizar o sistema coas súas modificacións.</span><span class="sxs-lookup"><span data-stu-id="0bafe-166">Choose **Run Merge and downstream processes** to refresh the system with your changes.</span></span> <span data-ttu-id="0bafe-167">Todos os procesos, incluído o enriquecemento, os segmentos e as medidas, volveranse executar automaticamente.</span><span class="sxs-lookup"><span data-stu-id="0bafe-167">All processes, including enrichment, segments, and measures will rerun automatically.</span></span> <span data-ttu-id="0bafe-168">Despois de completar todos os procesos descendentes, os perfís de clientes reflicten as modificacións realizadas.</span><span class="sxs-lookup"><span data-stu-id="0bafe-168">After all downstream processes have completed, the customer profiles reflect any changes you made.</span></span>

<span data-ttu-id="0bafe-169">Para realizar máis modificacións e volver executar o paso, pode cancelar unha combinación en curso.</span><span class="sxs-lookup"><span data-stu-id="0bafe-169">To make more changes and rerun the step, you can cancel an in-progress merge.</span></span> <span data-ttu-id="0bafe-170">Seleccione **Actualizando...** e seleccione **Cancelar traballo** no panel lateral que aparece.</span><span class="sxs-lookup"><span data-stu-id="0bafe-170">Select **Refreshing ...** and select **Cancel job**  in the side pane that appears.</span></span>

> [!TIP]
> <span data-ttu-id="0bafe-171">Existen [seis tipos de estado](system.md#status-types) para as tarefas ou os procesos.</span><span class="sxs-lookup"><span data-stu-id="0bafe-171">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="0bafe-172">Ademais, a maioría dos procesos [dependen doutros procesos descendentes](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="0bafe-172">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="0bafe-173">Pode seleccionar o estado dun proceso para ver detalles sobre o progreso de todo o traballo.</span><span class="sxs-lookup"><span data-stu-id="0bafe-173">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="0bafe-174">Despois de seleccionar **Ver detalles** para unha das tarefas do traballo, atopará información adicional: o tempo de procesamento, a última data de procesamento e todos os erros e avisos asociados á tarefa.</span><span class="sxs-lookup"><span data-stu-id="0bafe-174">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="0bafe-175">Seguinte paso</span><span class="sxs-lookup"><span data-stu-id="0bafe-175">Next Step</span></span>

<span data-ttu-id="0bafe-176">Configure [actividades](activities.md), [enriquecemento](enrichment-hub.md) ou [relacións](relationships.md) para obter máis información sobre os seus clientes.</span><span class="sxs-lookup"><span data-stu-id="0bafe-176">Configure [activities](activities.md), [enrichment](enrichment-hub.md), or [relationships](relationships.md) to gain more insights about your customers.</span></span>

<span data-ttu-id="0bafe-177">Se xa configurou actividades, un enriquecemento ou segmentos, procesaranse automaticamente para utilizar os últimos datos do cliente.</span><span class="sxs-lookup"><span data-stu-id="0bafe-177">If you already configured activities, enrichment, or segments, they'll be processed automatically to use the latest customer data.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
