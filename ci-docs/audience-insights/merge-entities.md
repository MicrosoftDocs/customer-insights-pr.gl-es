---
title: Combinar entidades na unificación de datos
description: Combine entidades para crear perfís de clientes unificados.
ms.date: 04/16/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 045fd8d8f65161b91caabed2ac52494dc4fb3910
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405733"
---
# <a name="merge-entities"></a><span data-ttu-id="5f49e-103">Combinar entidades</span><span class="sxs-lookup"><span data-stu-id="5f49e-103">Merge entities</span></span>

<span data-ttu-id="5f49e-104">A fase de combinación é a última fase do proceso de unificación de datos.</span><span class="sxs-lookup"><span data-stu-id="5f49e-104">The merge phase is the last phase in the data unification process.</span></span> <span data-ttu-id="5f49e-105">O seu propósito é conciliar datos conflitivos.</span><span class="sxs-lookup"><span data-stu-id="5f49e-105">Its purpose is reconciling conflicting data.</span></span> <span data-ttu-id="5f49e-106">Como exemplos de datos en conflito poden incluírse un nome de cliente que se atopa en dous dos seus conxuntos de datos pero aparece un pouco diferente en cada un ("Grant Marshall" fronte a "Grant Marshal") ou un número de teléfono que difire en formato (617-803-091X fronte a 617803091X).</span><span class="sxs-lookup"><span data-stu-id="5f49e-106">Examples of conflicting data could include a customer name found in two of your datasets but that shows up a little differently in each ("Grant Marshall" versus "Grant Marshal"), or a phone number that differs in format (617-803-091X versus 617803091X).</span></span> <span data-ttu-id="5f49e-107">A fusión deses puntos de datos conflitivos realízase atributo por atributo.</span><span class="sxs-lookup"><span data-stu-id="5f49e-107">Merging those conflicting data points is done on an attribute-by-attribute basis.</span></span>

<span data-ttu-id="5f49e-108">Despois de completar a [fase de correspondencia](match-entities.md), pode iniciar a fase de combinación seleccionando o mosaico **Combinar** na páxina **Unificar**.</span><span class="sxs-lookup"><span data-stu-id="5f49e-108">After completing the [match phase](match-entities.md), you start the merge phase by selecting the **Merge** tile on the **Unify** page.</span></span>

## <a name="review-system-recommendations"></a><span data-ttu-id="5f49e-109">Revisar recomendacións do sistema</span><span class="sxs-lookup"><span data-stu-id="5f49e-109">Review system recommendations</span></span>

<span data-ttu-id="5f49e-110">Na páxina **Combinar**, pode escoller e excluír os atributos que desexa fusionar na súa entidade de perfil de cliente unificada (o resultado do proceso de configuración).</span><span class="sxs-lookup"><span data-stu-id="5f49e-110">On the **Merge** page, you choose and exclude attributes to merge within your unified customer profile entity (the result of the configuration process).</span></span> <span data-ttu-id="5f49e-111">Algúns atributos os combina automaticamente o sistema.</span><span class="sxs-lookup"><span data-stu-id="5f49e-111">Some attributes are automatically merged by the system.</span></span>

### <a name="view-merged-attributes"></a><span data-ttu-id="5f49e-112">Ver atributos combinados</span><span class="sxs-lookup"><span data-stu-id="5f49e-112">View merged attributes</span></span>

<span data-ttu-id="5f49e-113">Para ver os atributos que están incluídos nun dos seus atributos combinados automaticamente, seleccione ese atributo combinado.</span><span class="sxs-lookup"><span data-stu-id="5f49e-113">To view the attributes that are included in one of your automatically merged attributes, select that merged attribute.</span></span> <span data-ttu-id="5f49e-114">Os dous atributos que compoñen este atributo combinado aparecerán en dúas novas filas baixo o atributo combinado.</span><span class="sxs-lookup"><span data-stu-id="5f49e-114">The two attributes that compose that merged attribute display in two new rows beneath the merged attribute.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="5f49e-115">![Seleccionar atributo combinado](media/configure-data-merge-profile-attributes.png "Seleccionar atributo combinado")</span><span class="sxs-lookup"><span data-stu-id="5f49e-115">![Select merged attribute](media/configure-data-merge-profile-attributes.png "Select merged attribute")</span></span>

### <a name="separate-merged-attributes"></a><span data-ttu-id="5f49e-116">Separar atributos combinados</span><span class="sxs-lookup"><span data-stu-id="5f49e-116">Separate merged attributes</span></span>

<span data-ttu-id="5f49e-117">Para separar ou desfacer a combinación de calquera dos atributos combinados automaticamente, busque o atributo na táboa **Atributos do perfil**.</span><span class="sxs-lookup"><span data-stu-id="5f49e-117">To separate or unmerge any of the automatically merged attributes, find the attribute in the **Profile attributes** table.</span></span>

1. <span data-ttu-id="5f49e-118">Seleccione o botón de tres puntos (...).</span><span class="sxs-lookup"><span data-stu-id="5f49e-118">Select the ellipsis (...) button.</span></span>
  
2. <span data-ttu-id="5f49e-119">Na lista despregable, seleccione **Campos separados**.</span><span class="sxs-lookup"><span data-stu-id="5f49e-119">In the dropdown list, select **Separate fields**.</span></span>

### <a name="remove-merged-attributes"></a><span data-ttu-id="5f49e-120">Elimine os atributos combinados</span><span class="sxs-lookup"><span data-stu-id="5f49e-120">Remove merged attributes</span></span>

<span data-ttu-id="5f49e-121">Para excluír un atributo da entidade de perfil de cliente final, búsqueo na táboa **Atributos do perfil**.</span><span class="sxs-lookup"><span data-stu-id="5f49e-121">To exclude an attribute from the final customer profile entity, find it in the **Profile attributes** table.</span></span>

1. <span data-ttu-id="5f49e-122">Seleccione o botón de tres puntos (...).</span><span class="sxs-lookup"><span data-stu-id="5f49e-122">Select the ellipsis (...) button.</span></span>
  
2. <span data-ttu-id="5f49e-123">Na lista despregable, seleccione **Non combinar**.</span><span class="sxs-lookup"><span data-stu-id="5f49e-123">In the dropdown list, select **Don't merge**.</span></span>

   <span data-ttu-id="5f49e-124">O atributo móvese á sección **Eliminado do rexistro do cliente**.</span><span class="sxs-lookup"><span data-stu-id="5f49e-124">The attribute is moved to the **Removed from customer record** section.</span></span>

## <a name="manually-add-a-merged-attribute"></a><span data-ttu-id="5f49e-125">Engadir manualmente un atributo combinado</span><span class="sxs-lookup"><span data-stu-id="5f49e-125">Manually add a merged attribute</span></span>

<span data-ttu-id="5f49e-126">Para engadir un atributo combinado, diríxase á páxina **Combinar**.</span><span class="sxs-lookup"><span data-stu-id="5f49e-126">To add a merged attribute, go to the **Merge** page.</span></span>

1. <span data-ttu-id="5f49e-127">Seleccione **Engadir atributo combinado**.</span><span class="sxs-lookup"><span data-stu-id="5f49e-127">Select **Add merged attribute**.</span></span>

2. <span data-ttu-id="5f49e-128">Proporcione un **Nome** para identificalo na páxina **Combinar** despois.</span><span class="sxs-lookup"><span data-stu-id="5f49e-128">Provide a **Name** to identify it on the **Merge** page later.</span></span>

3. <span data-ttu-id="5f49e-129">Tamén pode fornecer un **Nome para mostrar** que apareza na entidade de perfil de cliente unificada.</span><span class="sxs-lookup"><span data-stu-id="5f49e-129">Optionally, provide a **Display name** to appear in the unified Customer Profile entity.</span></span>

4. <span data-ttu-id="5f49e-130">Configure **Seleccionar atributos duplicados** para seleccionar os atributos que desexe combinar entre as entidades correspondentes.</span><span class="sxs-lookup"><span data-stu-id="5f49e-130">Configure **Select duplicate attributes** to select the attributes that you want to merge from the matched entities.</span></span> <span data-ttu-id="5f49e-131">Tamén pode buscar atributos.</span><span class="sxs-lookup"><span data-stu-id="5f49e-131">You can also search for attributes.</span></span>

5. <span data-ttu-id="5f49e-132">Estableza **Clasificar por importancia** para priorizar un atributo por enriba dos outros.</span><span class="sxs-lookup"><span data-stu-id="5f49e-132">Set the **Rank by importance** to prioritize one attribute above the others.</span></span> <span data-ttu-id="5f49e-133">Por exemplo, se a entidade *WebAccountCSV* inclúe os datos máis precisos sobre o atributo *Nomes completos*, pode priorizar esta entidade sobre *ContactCSV* seleccionando *WebAccountCSV*.</span><span class="sxs-lookup"><span data-stu-id="5f49e-133">For example, if the *WebAccountCSV* entity includes the most accurate data about the *Full Names* attribute, you could prioritize this entity over *ContactCSV* by selecting *WebAccountCSV*.</span></span> <span data-ttu-id="5f49e-134">Como resultado, *WebAccountCSV* pasa á primeira prioridade mentres que *ContactCSV* desprázase á segunda prioridade ao obter valores para o atributo *Nome completo*.</span><span class="sxs-lookup"><span data-stu-id="5f49e-134">As a result, *WebAccountCSV* moves to first priority, while *ContactCSV* moves to second priority when pulling values for the *Full Name* attribute.</span></span>

## <a name="run-your-merge"></a><span data-ttu-id="5f49e-135">Execute a súa combinación</span><span class="sxs-lookup"><span data-stu-id="5f49e-135">Run your merge</span></span>

<span data-ttu-id="5f49e-136">Tanto se combina manualmente atributos ou deixa que o sistema os combine, sempre pode executar a súa combinación.</span><span class="sxs-lookup"><span data-stu-id="5f49e-136">Whether you manually merge attributes or let the system merge them, you can always run your merge.</span></span> <span data-ttu-id="5f49e-137">Seleccione **Executar** na páxina **Combinar** para iniciar o proceso.</span><span class="sxs-lookup"><span data-stu-id="5f49e-137">Select **Run** on the **Merge** page to start the process.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="5f49e-138">![Almacenamento e execución da combinación de datos](media/configure-data-merge-save-run.png "Almacenamento e execución da combinación de datos")</span><span class="sxs-lookup"><span data-stu-id="5f49e-138">![Data merge Save and Run](media/configure-data-merge-save-run.png "Data merge Save and Run")</span></span>

<span data-ttu-id="5f49e-139">Para facer cambios adicionais e volver executar o paso, pode cancelar unha combinación en curso.</span><span class="sxs-lookup"><span data-stu-id="5f49e-139">To make additional changes and rerun the step, you can cancel an in-progress merge.</span></span> <span data-ttu-id="5f49e-140">Seleccione **Actualizando...** e seleccione **Cancelar traballo** no panel lateral que aparece.</span><span class="sxs-lookup"><span data-stu-id="5f49e-140">Select **Refreshing ...** and select **Cancel job**  in the side pane that appears.</span></span>

<span data-ttu-id="5f49e-141">Unha vez que cambie o texto **Actualizando...** a **Correcto**, a combinación completouse e resolveu as contradicións dos seus datos de acordo coas políticas que definiu.</span><span class="sxs-lookup"><span data-stu-id="5f49e-141">After the **Refreshing ...** text changes to **Successful**, merge has completed and resolved contradictions in your data according to the policies you defined.</span></span> <span data-ttu-id="5f49e-142">Os atributos combinados e non combinados inclúense na entidade de perfil unificado.</span><span class="sxs-lookup"><span data-stu-id="5f49e-142">Merged and unmerged attributes are included in the unified profile entity.</span></span> <span data-ttu-id="5f49e-143">Os atributos excluídos non se inclúen na entidade de perfil unificado.</span><span class="sxs-lookup"><span data-stu-id="5f49e-143">Excluded attributes aren't included in the unified profile entity.</span></span>

<span data-ttu-id="5f49e-144">Se non foi a primeira vez que executou unha combinación con éxito, todos os procesos descendentes, incluído o enriquecemento, a segmentación e as medidas, volveranse executar automaticamente.</span><span class="sxs-lookup"><span data-stu-id="5f49e-144">If it wasn't the first time you ran a merge successfully, all downstream processes, including enrichment, segmentation, and measures will rerun automatically.</span></span> <span data-ttu-id="5f49e-145">Despois de repetirse todos os procesos descendentes, os perfís de clientes reflicten os cambios que fixo.</span><span class="sxs-lookup"><span data-stu-id="5f49e-145">After all downstream processes have been rerun, the customer profiles reflect any changes you made.</span></span>

> [!TIP]
> <span data-ttu-id="5f49e-146">Existen [seis tipos de estado](system.md#status-types) para as tarefas ou os procesos.</span><span class="sxs-lookup"><span data-stu-id="5f49e-146">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="5f49e-147">Ademais, a maioría dos procesos [dependen doutros procesos descendentes](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="5f49e-147">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="5f49e-148">Pode seleccionar o estado dun proceso para ver detalles sobre o progreso de todo o traballo.</span><span class="sxs-lookup"><span data-stu-id="5f49e-148">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="5f49e-149">Despois de seleccionar **Ver detalles** para unha das tarefas do traballo, atopará información adicional: o tempo de procesamento, a última data de procesamento e todos os erros e avisos asociados á tarefa.</span><span class="sxs-lookup"><span data-stu-id="5f49e-149">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="5f49e-150">Seguinte paso</span><span class="sxs-lookup"><span data-stu-id="5f49e-150">Next Step</span></span>

<span data-ttu-id="5f49e-151">Configure [actividades](activities.md), [enriquecemento](enrichment-microsoft-graph.md) ou [relacións](relationships.md) para obter máis información sobre os seus clientes.</span><span class="sxs-lookup"><span data-stu-id="5f49e-151">Configure [activities](activities.md), [enrichment](enrichment-microsoft-graph.md), or [relationships](relationships.md) to gain more insights about your customers.</span></span>

<span data-ttu-id="5f49e-152">Se xa configurou actividades, enriquecemento ou relacións ou se definiu segmentos, procesaranse automaticamente para usar os datos máis recentes do cliente.</span><span class="sxs-lookup"><span data-stu-id="5f49e-152">If you already configured activities, enrichment, or relationships, or if you defined segments, they'll be processed automatically to use the latest customer data.</span></span>


