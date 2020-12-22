---
title: Crear e editar medidas
description: Definir medidas relacionadas co cliente para analizar e reflectir o rendemento de determinadas áreas comerciais.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 0e214a6eb66abd27f7292db3ce2c2a6e16a8ff33
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405736"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="6cd7e-103">Definir e xestionar medidas</span><span class="sxs-lookup"><span data-stu-id="6cd7e-103">Define and manage measures</span></span>

<span data-ttu-id="6cd7e-104">**Medidas** representan indicadores clave de rendemento (KPI) que reflicten o rendemento e a estado de determinadas áreas comerciais.</span><span class="sxs-lookup"><span data-stu-id="6cd7e-104">**Measures** represent key performance indicators (KPIs) that reflect the performance and health of specific business areas.</span></span> <span data-ttu-id="6cd7e-105">As estadísticas do público ofrecen unha experiencia intuitiva para crear diferentes tipos de medidas, usando un creador de consultas que non require que codifique nin valide as medidas manualmente.</span><span class="sxs-lookup"><span data-stu-id="6cd7e-105">Audience insights provides an intuitive experience for building different types of measures, using a query builder that doesn't require you to code or validate your measures manually.</span></span> <span data-ttu-id="6cd7e-106">Pode realizar un seguimento das súas medidas comerciais na páxina **Inicio**. Consulte as medidas para clientes específicos en **Tarxeta de cliente** e use medidas para definir segmentos de clientes na páxina **Segmentos**.</span><span class="sxs-lookup"><span data-stu-id="6cd7e-106">You can track your business measures on the **Home** page, see measures for specific customers on the **Customer Card**, and use measures to define customer segments on the **Segments** page.</span></span>

## <a name="create-a-measure"></a><span data-ttu-id="6cd7e-107">Crear unha medida</span><span class="sxs-lookup"><span data-stu-id="6cd7e-107">Create a measure</span></span>

<span data-ttu-id="6cd7e-108">Esta sección inclúe información detallada sobre como crear unha medida dende cero.</span><span class="sxs-lookup"><span data-stu-id="6cd7e-108">This section walks you through creating a measure from scratch.</span></span> <span data-ttu-id="6cd7e-109">Pode crear medidas con datos de varias orixes de datos conectadas a través da entidade de cliente.</span><span class="sxs-lookup"><span data-stu-id="6cd7e-109">You can build measures with data from multiple data sources that are connected through the Customer entity.</span></span> <span data-ttu-id="6cd7e-110">Algúns [límites de servizo](service-limits.md) aplican.</span><span class="sxs-lookup"><span data-stu-id="6cd7e-110">Some [service limits](service-limits.md) apply.</span></span>

1. <span data-ttu-id="6cd7e-111">Na información do público, vaia a **Medidas**.</span><span class="sxs-lookup"><span data-stu-id="6cd7e-111">In audience insights, go to **Measures**.</span></span>

2. <span data-ttu-id="6cd7e-112">Seleccione **Medida nova**.</span><span class="sxs-lookup"><span data-stu-id="6cd7e-112">Select **New measure**.</span></span>

3. <span data-ttu-id="6cd7e-113">Elixa o **Tipo** de medida:</span><span class="sxs-lookup"><span data-stu-id="6cd7e-113">Choose the measure **Type**:</span></span>

   - <span data-ttu-id="6cd7e-114">**Atributo de cliente**: un único campo por cliente que reflicte unha puntuación, valor ou estado para o cliente.</span><span class="sxs-lookup"><span data-stu-id="6cd7e-114">**Customer attribute**: A single field per customer that reflects a score, value, or state for the customer.</span></span> <span data-ttu-id="6cd7e-115">Os atributos de cliente créanse como atributos nunha nova entidade xerada polo sistema chamada **Customer_Measure**.</span><span class="sxs-lookup"><span data-stu-id="6cd7e-115">Customer attributes are created as attributes in a new system-generated entity called **Customer_Measure**.</span></span>

   - <span data-ttu-id="6cd7e-116">**Medida do cliente**: información do comportamento do cliente con desglose por dimensións seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="6cd7e-116">**Customer measure**: Insights on customer behavior with breakdown by selected dimensions.</span></span> <span data-ttu-id="6cd7e-117">Xérase unha nova entidade para cada medida, posiblemente con varios rexistros por cliente.</span><span class="sxs-lookup"><span data-stu-id="6cd7e-117">A new entity is generated for each measure, potentially with multiple records per customer.</span></span>

   - <span data-ttu-id="6cd7e-118">**Medida comercial**: realiza un seguimento do seu rendemento comercial e da saúde da súa empresa.</span><span class="sxs-lookup"><span data-stu-id="6cd7e-118">**Business measure**: Tracks your business performance and health of the business.</span></span> <span data-ttu-id="6cd7e-119">As medidas comerciais poden ter dous resultados diferentes: un resultado numérico que se mostra na páxina de **Inicio** ou unha nova entidade que atopará na páxina **Entidades**.</span><span class="sxs-lookup"><span data-stu-id="6cd7e-119">Business measures can have two different outputs: a numeric output that shows on the **Home** page or a new entity that you find on the **Entities** page.</span></span>

4. <span data-ttu-id="6cd7e-120">Proporcione un **Nome** e un **Nome para mostrar** opcional e logo seleccione **Seguinte**.</span><span class="sxs-lookup"><span data-stu-id="6cd7e-120">Provide a **Name** and an optional **Display name**, then select **Next**.</span></span>

5. <span data-ttu-id="6cd7e-121">Na sección **Entidades**, seleccione a primeira entidade da lista despregable.</span><span class="sxs-lookup"><span data-stu-id="6cd7e-121">In the **Entities** section, select the first entity from the drop-down list.</span></span> <span data-ttu-id="6cd7e-122">Neste momento, ten que decidir se son necesarias entidades adicionais como parte da súa definición de medida.</span><span class="sxs-lookup"><span data-stu-id="6cd7e-122">At this point, you should decide whether additional entities are needed as part of your measure definition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6cd7e-123">![Definición da medida](media/measure-definition.png "Definición da medida")</span><span class="sxs-lookup"><span data-stu-id="6cd7e-123">![Measure definition](media/measure-definition.png "Measure definition")</span></span>

   <span data-ttu-id="6cd7e-124">Para engadir máis entidades, seleccione **Engadir entidade** e seleccione as entidades que desexe usar para a medida.</span><span class="sxs-lookup"><span data-stu-id="6cd7e-124">To add more entities, select **Add entity** and select entities you want to use for the measure.</span></span>

   > [!NOTE]
   > <span data-ttu-id="6cd7e-125">Só pode seleccionar as entidades que teñen relacións coa entidade inicial.</span><span class="sxs-lookup"><span data-stu-id="6cd7e-125">You can select only entities that have relationships to your starting entity.</span></span> <span data-ttu-id="6cd7e-126">Para obter máis información acerca da definición de relacións, consulte [Relacións](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="6cd7e-126">For more information about defining relationships, see [Relationships](relationships.md).</span></span>

6. <span data-ttu-id="6cd7e-127">Tamén pode configurar variables.</span><span class="sxs-lookup"><span data-stu-id="6cd7e-127">Optionally, you can configure variables.</span></span> <span data-ttu-id="6cd7e-128">Na sección **Variables**, seleccione **Nova variable**.</span><span class="sxs-lookup"><span data-stu-id="6cd7e-128">In the **Variables** section, select **New variable**.</span></span>

   <span data-ttu-id="6cd7e-129">As variables son cálculos que se realizan en cada un dos rexistros seleccionados.</span><span class="sxs-lookup"><span data-stu-id="6cd7e-129">Variables are calculations that are made on each of your selected records.</span></span> <span data-ttu-id="6cd7e-130">Por exemplo, sumar o punto de venda (POS) e as vendas en liña para cada un dos rexistros dos seus clientes.</span><span class="sxs-lookup"><span data-stu-id="6cd7e-130">For example, summing point-of-sale (POS) and online sales for each of your customers' records.</span></span>

7. <span data-ttu-id="6cd7e-131">Proporcione un **Nome** para a variable.</span><span class="sxs-lookup"><span data-stu-id="6cd7e-131">Provide a **Name** for the variable.</span></span>

8. <span data-ttu-id="6cd7e-132">Na zona **Expresión**, escolla un campo co que comezar o seu cálculo.</span><span class="sxs-lookup"><span data-stu-id="6cd7e-132">In the **Expression** area, choose a field to begin your calculation with.</span></span>

9. <span data-ttu-id="6cd7e-133">Escriba unha expresión na zona **Expresión** escollendo máis campos para incluír no seu cálculo.</span><span class="sxs-lookup"><span data-stu-id="6cd7e-133">Type an expression in the **Expression** area while choosing more fields to be included in your calculation.</span></span>

   > [!NOTE]
   > <span data-ttu-id="6cd7e-134">Actualmente só se admiten expresións aritméticas.</span><span class="sxs-lookup"><span data-stu-id="6cd7e-134">Currently, only arithmetic expressions are supported.</span></span> <span data-ttu-id="6cd7e-135">Ademais, o cálculo de variables non é compatible con entidades de diferentes [camiños de entidade](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="6cd7e-135">Additionally, variable calculation isn't supported for entities from different [entity paths](relationships.md).</span></span>

10. <span data-ttu-id="6cd7e-136">Seleccione **Feito**.</span><span class="sxs-lookup"><span data-stu-id="6cd7e-136">Select **Done**.</span></span>

11. <span data-ttu-id="6cd7e-137">Na sección **Definición da medida**, definirá como se suman as súas entidades escollidas e as variables calculadas nunha nova entidade ou atributo de medida.</span><span class="sxs-lookup"><span data-stu-id="6cd7e-137">In the **Measure definition** section, you'll define how your chosen entities and calculated variables are aggregated in a new measure entity or attribute.</span></span>

12. <span data-ttu-id="6cd7e-138">Seleccione **Nova dimensión**.</span><span class="sxs-lookup"><span data-stu-id="6cd7e-138">Select **New dimension**.</span></span> <span data-ttu-id="6cd7e-139">Pode pensar nunha dimensión como unha función de *agrupar por*.</span><span class="sxs-lookup"><span data-stu-id="6cd7e-139">You can think of a dimension as a *group by* function.</span></span> <span data-ttu-id="6cd7e-140">A saída de datos da súa entidade ou atributo de medida agruparase por parte de todas as súas dimensións definidas.</span><span class="sxs-lookup"><span data-stu-id="6cd7e-140">The data output of your Measure entity or attribute will be grouped by all of your defined dimensions.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="6cd7e-141">![Elixa un ciclo agregado](media/measures-businessreport-measure-definition2.png "Elixa un ciclo agregado")</span><span class="sxs-lookup"><span data-stu-id="6cd7e-141">![Choose aggregate cycle](media/measures-businessreport-measure-definition2.png "Choose aggregate cycle")</span></span>

    <span data-ttu-id="6cd7e-142">Seleccione ou introduza a seguinte información como parte da definición da súa dimensión:</span><span class="sxs-lookup"><span data-stu-id="6cd7e-142">Select or enter the following information as part of your dimension's definition:</span></span>

    - <span data-ttu-id="6cd7e-143">**Entidade**: se define unha entidade de medida, debería incluír polo menos un atributo.</span><span class="sxs-lookup"><span data-stu-id="6cd7e-143">**Entity**: If you define a Measure entity, it should include at least one attribute.</span></span> <span data-ttu-id="6cd7e-144">Se define un atributo de medida, só incluirá un atributo por defecto.</span><span class="sxs-lookup"><span data-stu-id="6cd7e-144">If you define a Measure attribute, it will include only one attribute by default.</span></span> <span data-ttu-id="6cd7e-145">Esta selección trata de escoller a entidade que inclúe ese atributo.</span><span class="sxs-lookup"><span data-stu-id="6cd7e-145">This selection is about choosing the entity that includes that attribute.</span></span>
    - <span data-ttu-id="6cd7e-146">**Campo**: escolla o atributo específico que se vai incluír na súa entidade ou atributo de medida.</span><span class="sxs-lookup"><span data-stu-id="6cd7e-146">**Field**: Choose the specific attribute to be included either in your Measure entity or attribute.</span></span>
    - <span data-ttu-id="6cd7e-147">**Depósito**: escolla se desexa agregar datos a diario, mensualmente ou anualmente.</span><span class="sxs-lookup"><span data-stu-id="6cd7e-147">**Bucket**: Choose whether you want to aggregate data on a daily, monthly, or annual basis.</span></span> <span data-ttu-id="6cd7e-148">É unha selección necesaria só se seleccionou un atributo de tipo Data.</span><span class="sxs-lookup"><span data-stu-id="6cd7e-148">It's a required selection only if you've selected a Date type attribute.</span></span>
    - <span data-ttu-id="6cd7e-149">**Como**: define o nome do seu novo campo.</span><span class="sxs-lookup"><span data-stu-id="6cd7e-149">**As**: Defines the name of your new field.</span></span>
    - <span data-ttu-id="6cd7e-150">**Nome para mostrar**: define o nome para mostrar do campo.</span><span class="sxs-lookup"><span data-stu-id="6cd7e-150">**Display name**: Defines the display name of your field.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6cd7e-151">A súa medida comercial gardarase como unha entidade dun só número e aparecerá na páxina **Inicio** a menos que engada máis dimensións á súa medida.</span><span class="sxs-lookup"><span data-stu-id="6cd7e-151">Your business measure will be saved as a single-number entity and will appear on the **Home** page unless you add more dimensions to your measure.</span></span> <span data-ttu-id="6cd7e-152">Despois de engadir máis dimensións, a medida *non* aparecerá na páxina **Inicio**.</span><span class="sxs-lookup"><span data-stu-id="6cd7e-152">After adding more dimensions, the measure will *not* show up on the **Home** page.</span></span>

13. <span data-ttu-id="6cd7e-153">Tamén pode engadir funcións de agregación.</span><span class="sxs-lookup"><span data-stu-id="6cd7e-153">Optionally, add aggregation functions.</span></span> <span data-ttu-id="6cd7e-154">Calquera agregación que cree terá como resultado un novo valor dentro da súa entidade ou atributo de Medida.</span><span class="sxs-lookup"><span data-stu-id="6cd7e-154">Any aggregation that you create results in a new value within your Measures entity or attribute.</span></span> <span data-ttu-id="6cd7e-155">As funcións de agregación compatibles son: **Min**, **Max**, **Average**, **Median**, **Sum**, **Count Unique**, **First** (toma o primeiro rexistro dun valor de dimensión) e **Last** (toma o último rexistro engadido a un valor de dimensión).</span><span class="sxs-lookup"><span data-stu-id="6cd7e-155">Supported aggregation functions are: **Min**, **Max**, **Average**, **Median**, **Sum**, **Count Unique**, **First** (takes the first record of a dimension value), and **Last** (takes the last record added to a dimension value).</span></span>

14. <span data-ttu-id="6cd7e-156">Seleccione **Gardar** para aplicar os cambios á medida.</span><span class="sxs-lookup"><span data-stu-id="6cd7e-156">Select **Save** to apply your changes to the measure.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="6cd7e-157">Xestionar as súas medidas</span><span class="sxs-lookup"><span data-stu-id="6cd7e-157">Manage your measures</span></span>

<span data-ttu-id="6cd7e-158">Despois de crear polo menos unha medida, verá unha lista de medidas na páxina **Medidas**.</span><span class="sxs-lookup"><span data-stu-id="6cd7e-158">After creating at least one measure, you'll see a list of measures on the **Measures** page.</span></span>

<span data-ttu-id="6cd7e-159">Atopará información sobre o tipo de medida, o creador, a data e hora da creación, a data e hora da última edición, o estado (se a medida está activa, inactiva ou fallou) e a última data e hora de actualización.</span><span class="sxs-lookup"><span data-stu-id="6cd7e-159">You'll find information about the measure type, the creator, creation date and time, last edit date and time, status (whether the measure is active, inactive, or failed), and last refresh date and time.</span></span> <span data-ttu-id="6cd7e-160">Cando seleccione unha medida da lista, poderá ver unha vista previa da súa saída.</span><span class="sxs-lookup"><span data-stu-id="6cd7e-160">When you select a measure from the list, you can see a preview of its output.</span></span>

<span data-ttu-id="6cd7e-161">Para actualizar todas as túas medidas ao mesmo tempo, seleccione **Actualizar todo** sen seleccionar unha medida específica.</span><span class="sxs-lookup"><span data-stu-id="6cd7e-161">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="6cd7e-162">![Accións para xestionar medidas individuais](media/measure-actions.png "Accións para xestionar medidas individuais")</span><span class="sxs-lookup"><span data-stu-id="6cd7e-162">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="6cd7e-163">Tamén pode seleccionar unha medida da lista e realizar unha das seguintes accións:</span><span class="sxs-lookup"><span data-stu-id="6cd7e-163">Alternatively, select a measure from the list and perform one of the following actions:</span></span>

- <span data-ttu-id="6cd7e-164">Seleccione o nome da medida para ver os seus detalles.</span><span class="sxs-lookup"><span data-stu-id="6cd7e-164">Select the measure name to see its details.</span></span>
- <span data-ttu-id="6cd7e-165">**Editar** a configuración da medida.</span><span class="sxs-lookup"><span data-stu-id="6cd7e-165">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="6cd7e-166">**Cambiar o nome** da medida.</span><span class="sxs-lookup"><span data-stu-id="6cd7e-166">**Rename** the measure.</span></span>
- <span data-ttu-id="6cd7e-167">**Eliminar** a medida.</span><span class="sxs-lookup"><span data-stu-id="6cd7e-167">**Delete** the measure.</span></span>
- <span data-ttu-id="6cd7e-168">Seleccione os tres puntos (...) e logo **Actualice** para iniciar o proceso de actualización para a medida.</span><span class="sxs-lookup"><span data-stu-id="6cd7e-168">Select the ellipsis (...) and then **Refresh** to start the refresh process for the measure.</span></span>
- <span data-ttu-id="6cd7e-169">Seleccione os tres puntos (...) e logo **Descargar** para obter un ficheiro .CSV da medida.</span><span class="sxs-lookup"><span data-stu-id="6cd7e-169">Select the ellipsis (...) and then **Download** to get a .CSV file of the measure.</span></span>

> [!TIP]
> <span data-ttu-id="6cd7e-170">Existen [seis tipos de estado](system.md#status-types) para as tarefas ou os procesos.</span><span class="sxs-lookup"><span data-stu-id="6cd7e-170">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="6cd7e-171">Ademais, a maioría dos procesos [dependen doutros procesos descendentes](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="6cd7e-171">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="6cd7e-172">Pode seleccionar o estado dun proceso para ver detalles sobre o progreso de todo o traballo.</span><span class="sxs-lookup"><span data-stu-id="6cd7e-172">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="6cd7e-173">Despois de seleccionar **Ver detalles** para unha das tarefas do traballo, atopará información adicional: o tempo de procesamento, a última data de procesamento e todos os erros e avisos asociados á tarefa.</span><span class="sxs-lookup"><span data-stu-id="6cd7e-173">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="6cd7e-174">Seguinte paso</span><span class="sxs-lookup"><span data-stu-id="6cd7e-174">Next step</span></span>

<span data-ttu-id="6cd7e-175">Pode empregar as medidas existentes para crear o seu primeiro segmento de cliente na páxina **Segmentos**.</span><span class="sxs-lookup"><span data-stu-id="6cd7e-175">You cam use existing measures to create your first customer segment on the **Segments** page.</span></span> <span data-ttu-id="6cd7e-176">Para obter máis información, consulte [Segmentos](segments.md).</span><span class="sxs-lookup"><span data-stu-id="6cd7e-176">For more information, see [Segments](segments.md).</span></span>
