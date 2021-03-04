---
title: Crear e xestionar medidas
description: Defina medidas para analizar e reflectir o rendemento da súa empresa.
ms.date: 02/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 5bcee3b4c51880740715575b18fd7a4dbf87e6d0
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269926"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="9574b-103">Definir e xestionar medidas</span><span class="sxs-lookup"><span data-stu-id="9574b-103">Define and manage measures</span></span>

<span data-ttu-id="9574b-104">As medidas axudan a comprender mellor o comportamento dos clientes e o rendemento empresarial recuperando valores relevantes de [perfís unificados](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="9574b-104">Measures help you to better understand customer behaviors and business performance by retrieving relevant values from [unified profiles](data-unification.md).</span></span> <span data-ttu-id="9574b-105">Por exemplo, unha empresa quere ver o *gasto total por cliente* para comprender o historial de compras de cada cliente.</span><span class="sxs-lookup"><span data-stu-id="9574b-105">For example, a business wants to see the *total spend per customer* to understand individual customer’s purchase history.</span></span> <span data-ttu-id="9574b-106">Ou medir as *vendas totais da empresa* para comprender os ingresos a nivel agregado en todo o negocio.</span><span class="sxs-lookup"><span data-stu-id="9574b-106">Or measure *total sales of the company* to understand the aggregate-level revenue in the whole business.</span></span>  

<span data-ttu-id="9574b-107">As medidas créanse usando o creador de medidas, unha plataforma de consulta de datos con varios operadores e sinxelas opcións de asignación.</span><span class="sxs-lookup"><span data-stu-id="9574b-107">Measures are created using the measure builder, a data query platform with various operators and simple mapping options.</span></span> <span data-ttu-id="9574b-108">Permite filtrar os datos, agrupar resultados, detectar [camiños de relación de entidade](relationships.md) e previsualizar os resultados.</span><span class="sxs-lookup"><span data-stu-id="9574b-108">It lets you filter the data, group results, detect [entity relationship paths](relationships.md), and preview the output.</span></span>

<span data-ttu-id="9574b-109">Use o creador de medidas para planificar actividades comerciais consultando datos de clientes e extraendo información.</span><span class="sxs-lookup"><span data-stu-id="9574b-109">Use the measure builder to plan business activities by querying customer data and extract insights.</span></span> <span data-ttu-id="9574b-110">Por exemplo, crear unha medida de *gasto total por cliente* e *devolución total por cliente* axuda a identificar un grupo de clientes cun gasto elevado pero cunha devolución elevada.</span><span class="sxs-lookup"><span data-stu-id="9574b-110">For example, creating a measure of *total spend per customer* and *total return per customer* helps identify a group of customers with high spend yet high return.</span></span> <span data-ttu-id="9574b-111">Pode [crear un segmento](segments.md) para impulsar as accións subseguintes máis axeitadas.</span><span class="sxs-lookup"><span data-stu-id="9574b-111">You can [create a segment](segments.md) to drive next best actions.</span></span> 

## <a name="create-a-measure"></a><span data-ttu-id="9574b-112">Crear unha medida</span><span class="sxs-lookup"><span data-stu-id="9574b-112">Create a measure</span></span>

<span data-ttu-id="9574b-113">Esta sección móstralle como crear unha nova medida desde cero.</span><span class="sxs-lookup"><span data-stu-id="9574b-113">This section walks you through creating a new measure from scratch.</span></span> <span data-ttu-id="9574b-114">Pode construír unha medida con atributos de datos de entidades de datos que teñen unha relación configurada para conectarse coa entidade Cliente.</span><span class="sxs-lookup"><span data-stu-id="9574b-114">You can build a measure with data attributes from data entities that have a relationship set up to connect with the Customer entity.</span></span> 

1. <span data-ttu-id="9574b-115">Na información do público, vaia a **Medidas**.</span><span class="sxs-lookup"><span data-stu-id="9574b-115">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="9574b-116">Seleccione **Nova**.</span><span class="sxs-lookup"><span data-stu-id="9574b-116">Select **New**.</span></span>

1. <span data-ttu-id="9574b-117">Seleccione **Editar nome** e proporcione un **Nome** para a medida.</span><span class="sxs-lookup"><span data-stu-id="9574b-117">Select **Edit name** and provide a **Name** for the measure.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="9574b-118">Se a súa nova configuración de medida ten só dous campos, por exemplo, CustomerID e un cálculo, o resultado engadirase como nova columna á entidade xerada polo sistema chamada Customer_Measure.</span><span class="sxs-lookup"><span data-stu-id="9574b-118">If your new measure configuration has only two fields, for exmample, CustomerID and one calculation, the output will be added as a new column to the system generated entity called Customer_Measure.</span></span> <span data-ttu-id="9574b-119">E poderá ver o valor da medida no perfil de cliente unificado.</span><span class="sxs-lookup"><span data-stu-id="9574b-119">And you will be able to see the measure’s value in the unified customer profile.</span></span> <span data-ttu-id="9574b-120">Outras medidas xerarán as súas propias entidades.</span><span class="sxs-lookup"><span data-stu-id="9574b-120">Other measures will generate their own entities.</span></span>

1. <span data-ttu-id="9574b-121">Na área de configuración, escolla a función de agregación no menú despregable **Seleccionar función**.</span><span class="sxs-lookup"><span data-stu-id="9574b-121">In the configuration area, choose the aggregation function from the **Select Function** drop-down menu.</span></span> <span data-ttu-id="9574b-122">As funcións de agregación inclúen:</span><span class="sxs-lookup"><span data-stu-id="9574b-122">Aggregation functions include:</span></span> 
   - <span data-ttu-id="9574b-123">**Suma**</span><span class="sxs-lookup"><span data-stu-id="9574b-123">**Sum**</span></span>
   - <span data-ttu-id="9574b-124">**Media**</span><span class="sxs-lookup"><span data-stu-id="9574b-124">**Average**</span></span>
   - <span data-ttu-id="9574b-125">**Número total**</span><span class="sxs-lookup"><span data-stu-id="9574b-125">**Count**</span></span>
   - <span data-ttu-id="9574b-126">**Número único**</span><span class="sxs-lookup"><span data-stu-id="9574b-126">**Count Unique**</span></span>
   - <span data-ttu-id="9574b-127">**Máx.**</span><span class="sxs-lookup"><span data-stu-id="9574b-127">**Max**</span></span>
   - <span data-ttu-id="9574b-128">**Min**</span><span class="sxs-lookup"><span data-stu-id="9574b-128">**Min**</span></span>
   - <span data-ttu-id="9574b-129">**Primeiro**: toma o primeiro valor do rexistro de datos</span><span class="sxs-lookup"><span data-stu-id="9574b-129">**First**: takes the first value of the data record</span></span>
   - <span data-ttu-id="9574b-130">**Último**: toma o último valor que se engadiu ao rexistro de datos</span><span class="sxs-lookup"><span data-stu-id="9574b-130">**Last**: takes the last value that was added to the data record</span></span>

   :::image type="content" source="media/measure-operators.png" alt-text="Operadores para cálculos de medidas.":::

1. <span data-ttu-id="9574b-132">Seleccione **Engadir atributo** para seleccionar os datos que precisa para crear esta medida.</span><span class="sxs-lookup"><span data-stu-id="9574b-132">Select **Add attribute** to select the data you need to create this measure.</span></span>
   
   1. <span data-ttu-id="9574b-133">Seleccione o separador **Atributos**.</span><span class="sxs-lookup"><span data-stu-id="9574b-133">Select the **Attributes** tab.</span></span> 
   1. <span data-ttu-id="9574b-134">Entidade de datos: escolla a entidade que inclúe o atributo que desexa medir.</span><span class="sxs-lookup"><span data-stu-id="9574b-134">Data entity: Choose the entity that includes the attribute you want to measure.</span></span> 
   1. <span data-ttu-id="9574b-135">Atributo de datos: escolla o atributo que desexa usar na función de agregación para calcular a medida.</span><span class="sxs-lookup"><span data-stu-id="9574b-135">Data attribute: Choose the attribute you want to use in the aggregation function to calculate the measure.</span></span> <span data-ttu-id="9574b-136">Só pode seleccionar un atributo de cada vez.</span><span class="sxs-lookup"><span data-stu-id="9574b-136">You can only select one attribute at a time.</span></span>
   1. <span data-ttu-id="9574b-137">Tamén pode seleccionar un atributo de datos dunha medida existente seleccionando o separador **Medidas**. Ou pode buscar un nome de entidade ou medida.</span><span class="sxs-lookup"><span data-stu-id="9574b-137">You can also select a data attribute from an existing measure by selecting the **Measures** tab. Or, you can search for an entity or measure name.</span></span> 
   1. <span data-ttu-id="9574b-138">Seleccione **Engadir** para engadir o atributo seleccionado á medida.</span><span class="sxs-lookup"><span data-stu-id="9574b-138">Select **Add** to add the selected attribute to the measure.</span></span>

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Seleccione un atributo para usar nos cálculos.":::

1. <span data-ttu-id="9574b-140">Para construír medidas máis complexas, pode engadir máis atributos ou usar operadores matemáticos na súa función de medida.</span><span class="sxs-lookup"><span data-stu-id="9574b-140">To build more complex measures, you can add more attributes or use math operators on your measure function.</span></span>

   :::image type="content" source="media/measure-math-operators.png" alt-text="Cree unha medida complexa con operadores matemáticos.":::

1. <span data-ttu-id="9574b-142">Para engadir filtros, seleccione o **Filtro** na área de configuración.</span><span class="sxs-lookup"><span data-stu-id="9574b-142">To add filters, select the **Filter** in the configuration area.</span></span> 
  
   1. <span data-ttu-id="9574b-143">Na sección **Engadir atributo** do panel **Filtros**, seleccione o atributo que desexa usar para crear filtros.</span><span class="sxs-lookup"><span data-stu-id="9574b-143">In **Add attribute** section of the **Filters** pane, select the attribute you want to use to create filters.</span></span>
   1. <span data-ttu-id="9574b-144">Configure os operadores de filtros para definir o filtro para cada atributo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="9574b-144">Set the filter operators to define the filter for every selected attribute.</span></span>
   1. <span data-ttu-id="9574b-145">Seleccione **Aplicar** para engadir os filtros á medida.</span><span class="sxs-lookup"><span data-stu-id="9574b-145">Select **Apply** to add the filters to the measure.</span></span>

1. <span data-ttu-id="9574b-146">Para engadir dimensións, seleccione **Dimensión** na área de configuración.</span><span class="sxs-lookup"><span data-stu-id="9574b-146">To add dimensions, select **Dimension** in the configuration area.</span></span> <span data-ttu-id="9574b-147">As dimensións mostraranse como columnas na entidade de saída de medida.</span><span class="sxs-lookup"><span data-stu-id="9574b-147">Dimensions will show as columns in the measure output entity.</span></span>
   1. <span data-ttu-id="9574b-148">Seleccione **Editar dimensións** para engadir atributos de datos polos que desexa agrupar os valores da medida.</span><span class="sxs-lookup"><span data-stu-id="9574b-148">Select **Edit dimensions** to add data attributes you want to group the measure values by.</span></span> <span data-ttu-id="9574b-149">Por exemplo, cidade ou sexo.</span><span class="sxs-lookup"><span data-stu-id="9574b-149">For example, city or gender.</span></span> <span data-ttu-id="9574b-150">Por defecto, a dimensión *CustomerID* seleccionouse para crear *medidas a nivel de cliente*.</span><span class="sxs-lookup"><span data-stu-id="9574b-150">By default, the *CustomerID* dimension is selected to create *customer-level measures*.</span></span> <span data-ttu-id="9574b-151">Pode eliminar a dimensión predeterminada se quere crear *medidas a nivel empresarial*.</span><span class="sxs-lookup"><span data-stu-id="9574b-151">You can remove the default dimension if you want to create *business-level measures*.</span></span>
   1. <span data-ttu-id="9574b-152">Seleccione **Feito** para engadir as dimensións á medida.</span><span class="sxs-lookup"><span data-stu-id="9574b-152">Select **Done** to add the dimensions to the measure.</span></span>

1. <span data-ttu-id="9574b-153">Se hai varias rutas entre a entidade de datos que asignou e a entidade Cliente, ten que escoller un dos [camiños de relación de entidade](relationships.md) identificados.</span><span class="sxs-lookup"><span data-stu-id="9574b-153">If there are multiple paths between the data entity you mapped and the Customer entity, you have to choose one of the identified [entity relationship paths](relationships.md).</span></span> <span data-ttu-id="9574b-154">Os resultados das medidas poden variar dependendo do camiño seleccionado.</span><span class="sxs-lookup"><span data-stu-id="9574b-154">Measure results can vary depending on the selected path.</span></span>
   1. <span data-ttu-id="9574b-155">Seleccione **Preferencias de datos** e elixa o camiño da entidade que se debería empregar para identificar a súa medida.</span><span class="sxs-lookup"><span data-stu-id="9574b-155">Select **Data preferences** and choose the entity path that should be used to identify your measure.</span></span>
   1. <span data-ttu-id="9574b-156">Seleccione **Feito** para aplicar a súa selección.</span><span class="sxs-lookup"><span data-stu-id="9574b-156">Select **Done** to apply your selection.</span></span> 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Seleccione o camiño da entidade para a medida.":::

1. <span data-ttu-id="9574b-158">Para engadir máis cálculos para a medida, seleccione **Novo cálculo**.</span><span class="sxs-lookup"><span data-stu-id="9574b-158">To add more calculations for the measure, select **New calculation**.</span></span> <span data-ttu-id="9574b-159">Só pode usar entidades na mesma ruta de entidade para novos cálculos.</span><span class="sxs-lookup"><span data-stu-id="9574b-159">You can only use entities on the same entity path for new calculations.</span></span> <span data-ttu-id="9574b-160">Máis cálculos mostraranse como columnas novas na entidade de saída de medida.</span><span class="sxs-lookup"><span data-stu-id="9574b-160">More calculations will show as new columns in the measure output entity.</span></span>

1. <span data-ttu-id="9574b-161">Seleccione **...** sobre o cálculo para **Duplicar**, **Cambiar o nome** ou **Quitar** un cálculo dunha medida.</span><span class="sxs-lookup"><span data-stu-id="9574b-161">Select **...** on the calculation to **Duplicate**, **Rename**, or **Remove** a calculation from a measure.</span></span>

1. <span data-ttu-id="9574b-162">Na área **Vista previa**, verá o esquema de datos da entidade de saída de medida, incluídos filtros e dimensións.</span><span class="sxs-lookup"><span data-stu-id="9574b-162">In the **Preview** area, you'll see the data schema of the measure output entity, including filters and dimensions.</span></span> <span data-ttu-id="9574b-163">A vista previa reacciona dinamicamente aos cambios na configuración.</span><span class="sxs-lookup"><span data-stu-id="9574b-163">The preview reacts dynamically to changes in the configuration.</span></span>

1. <span data-ttu-id="9574b-164">Seleccione **Executar** para calcular os resultados da medida configurada.</span><span class="sxs-lookup"><span data-stu-id="9574b-164">Select **Run** to calculate results for the configured measure.</span></span> <span data-ttu-id="9574b-165">Seleccione **Gardar e pechar** se quere manter a configuración actual e executar a medida máis tarde.</span><span class="sxs-lookup"><span data-stu-id="9574b-165">Select **Save and close** if you want to keep the current configuration and run the measure later.</span></span>

1. <span data-ttu-id="9574b-166">Vaia a **Medidas** para ver na lista a medida recentemente creada.</span><span class="sxs-lookup"><span data-stu-id="9574b-166">Go to **Measures** to see the newly created measure in the list.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="9574b-167">Xestionar as súas medidas</span><span class="sxs-lookup"><span data-stu-id="9574b-167">Manage your measures</span></span>

<span data-ttu-id="9574b-168">Despois de [crear unha medida](#create-a-measure), verá unha lista de medidas na páxina **Medidas**.</span><span class="sxs-lookup"><span data-stu-id="9574b-168">After [creating a measure](#create-a-measure), you see a list of measures on the **Measures** page.</span></span>

<span data-ttu-id="9574b-169">Atopará información sobre o tipo de medida, o creador, a data de creación, o estado e o estado.</span><span class="sxs-lookup"><span data-stu-id="9574b-169">You'll find information about the measure type, the creator, creation date, status, and state.</span></span> <span data-ttu-id="9574b-170">Cando selecciona unha medida da lista, pode previsualizar a saída e descargar un ficheiro .CSV.</span><span class="sxs-lookup"><span data-stu-id="9574b-170">When you select a measure from the list, you can preview the output and download a .CSV file.</span></span>

<span data-ttu-id="9574b-171">Para actualizar todas as túas medidas ao mesmo tempo, seleccione **Actualizar todo** sen seleccionar unha medida específica.</span><span class="sxs-lookup"><span data-stu-id="9574b-171">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="9574b-172">![Accións para xestionar medidas individuais](media/measure-actions.png "Accións para xestionar medidas individuais")</span><span class="sxs-lookup"><span data-stu-id="9574b-172">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="9574b-173">Seleccione unha medida da lista para as seguintes opcións:</span><span class="sxs-lookup"><span data-stu-id="9574b-173">Select a measure from the list for the following options:</span></span>

- <span data-ttu-id="9574b-174">Seleccione o nome da medida para ver os seus detalles.</span><span class="sxs-lookup"><span data-stu-id="9574b-174">Select the measure name to see its details.</span></span>
- <span data-ttu-id="9574b-175">**Editar** a configuración da medida.</span><span class="sxs-lookup"><span data-stu-id="9574b-175">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="9574b-176">**Actualizar** a medida segundo os últimos datos.</span><span class="sxs-lookup"><span data-stu-id="9574b-176">**Refresh** the measure based on the latest data.</span></span>
- <span data-ttu-id="9574b-177">**Cambiar o nome** da medida.</span><span class="sxs-lookup"><span data-stu-id="9574b-177">**Rename** the measure.</span></span>
- <span data-ttu-id="9574b-178">**Eliminar** a medida.</span><span class="sxs-lookup"><span data-stu-id="9574b-178">**Delete** the measure.</span></span>
- <span data-ttu-id="9574b-179">**Activar** ou **Desactivar**.</span><span class="sxs-lookup"><span data-stu-id="9574b-179">**Activate** or **Deactivate**.</span></span> <span data-ttu-id="9574b-180">As medidas inactivas non se actualizarán durante unha [actualización programada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="9574b-180">Inactive measures won't get refreshed during a [scheduled refresh](system.md#schedule-tab).</span></span>

> [!TIP]
> <span data-ttu-id="9574b-181">Existen [seis tipos de estado](system.md#status-types) para as tarefas ou os procesos.</span><span class="sxs-lookup"><span data-stu-id="9574b-181">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="9574b-182">Ademais, a maioría dos procesos [dependen doutros procesos descendentes](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="9574b-182">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="9574b-183">Pode seleccionar o estado dun proceso para ver detalles sobre o progreso de todo o traballo.</span><span class="sxs-lookup"><span data-stu-id="9574b-183">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="9574b-184">Despois de seleccionar **Ver detalles** para unha das tarefas do traballo, atopará información adicional: o tempo de procesamento, a última data de procesamento e todos os erros e avisos asociados á tarefa.</span><span class="sxs-lookup"><span data-stu-id="9574b-184">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="9574b-185">Seguinte paso</span><span class="sxs-lookup"><span data-stu-id="9574b-185">Next step</span></span>

<span data-ttu-id="9574b-186">Utilice as medidas existentes para crear [un segmento de clientes](segments.md).</span><span class="sxs-lookup"><span data-stu-id="9574b-186">You cam use existing measures to create [a customer segment](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]