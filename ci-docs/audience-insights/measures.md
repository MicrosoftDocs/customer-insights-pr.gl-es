---
title: Crear e xestionar medidas
description: Defina medidas para analizar e reflectir o rendemento da súa empresa.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 9a94a32a04f2a8beb661c27271fe96f23d998722
ms.sourcegitcommit: d89b19b2a3497722b78362aeee688ae7e94915d9
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "5887938"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="3a8ec-103">Definir e xestionar medidas</span><span class="sxs-lookup"><span data-stu-id="3a8ec-103">Define and manage measures</span></span>

<span data-ttu-id="3a8ec-104">As medidas axudan a comprender mellor os comportamentos dos clientes e o rendemento empresarial.</span><span class="sxs-lookup"><span data-stu-id="3a8ec-104">Measures help you to better understand customer behaviors and business performance.</span></span> <span data-ttu-id="3a8ec-105">Miran valores relevantes de [perfís unificados](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="3a8ec-105">They look at relevant values from [unified profiles](data-unification.md).</span></span> <span data-ttu-id="3a8ec-106">Por exemplo, unha empresa quere ver o *gasto total por cliente* para comprender o historial de compras de cada cliente ou medir as *vendas totais da empresa* para comprender os ingresos agregados de todo o negocio.</span><span class="sxs-lookup"><span data-stu-id="3a8ec-106">For example, a business wants to see the *total spend per customer* to understand individual customer’s purchase history or measure *total sales of the company* to understand the aggregate-level revenue in the whole business.</span></span>  

<span data-ttu-id="3a8ec-107">As medidas créanse usando o creador de medidas, unha plataforma de consulta de datos con varios operadores e sinxelas opcións de asignación.</span><span class="sxs-lookup"><span data-stu-id="3a8ec-107">Measures are created using the measure builder, a data query platform with various operators and simple mapping options.</span></span> <span data-ttu-id="3a8ec-108">Permite filtrar os datos, agrupar resultados, detectar [camiños de relación de entidade](relationships.md) e previsualizar os resultados.</span><span class="sxs-lookup"><span data-stu-id="3a8ec-108">It lets you filter the data, group results, detect [entity relationship paths](relationships.md), and preview the output.</span></span>

<span data-ttu-id="3a8ec-109">Use o creador de medidas para planificar actividades comerciais consultando datos de clientes e extraendo información.</span><span class="sxs-lookup"><span data-stu-id="3a8ec-109">Use the measure builder to plan business activities by querying customer data and extract insights.</span></span> <span data-ttu-id="3a8ec-110">Por exemplo, crear unha medida de *gasto total por cliente* e *devolución total por cliente* axuda a identificar un grupo de clientes cun gasto elevado pero cunha devolución elevada.</span><span class="sxs-lookup"><span data-stu-id="3a8ec-110">For example, creating a measure of *total spend per customer* and *total return per customer* helps identify a group of customers with high spend yet high return.</span></span> <span data-ttu-id="3a8ec-111">Pode [crear un segmento](segments.md) para impulsar as accións subseguintes máis axeitadas.</span><span class="sxs-lookup"><span data-stu-id="3a8ec-111">You can [create a segment](segments.md) to drive next best actions.</span></span> 

## <a name="build-your-own-measure-from-scratch"></a><span data-ttu-id="3a8ec-112">Compilar a súa propia medida desde cero</span><span class="sxs-lookup"><span data-stu-id="3a8ec-112">Build your own measure from scratch</span></span>

<span data-ttu-id="3a8ec-113">Esta sección móstralle como crear unha nova medida desde cero.</span><span class="sxs-lookup"><span data-stu-id="3a8ec-113">This section walks you through creating a new measure from scratch.</span></span> <span data-ttu-id="3a8ec-114">Pode construír unha medida con atributos de datos de entidades de datos que teñen unha relación configurada para conectarse coa entidade Cliente.</span><span class="sxs-lookup"><span data-stu-id="3a8ec-114">You can build a measure with data attributes from data entities that have a relationship set up to connect with the Customer entity.</span></span> 

1. <span data-ttu-id="3a8ec-115">Na información do público, vaia a **Medidas**.</span><span class="sxs-lookup"><span data-stu-id="3a8ec-115">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="3a8ec-116">Seleccione **Nova** e elixa **Construír unha propia**.</span><span class="sxs-lookup"><span data-stu-id="3a8ec-116">Select **New** and choose **Build your own**.</span></span>

1. <span data-ttu-id="3a8ec-117">Seleccione **Editar nome** e proporcione un **Nome** para a medida.</span><span class="sxs-lookup"><span data-stu-id="3a8ec-117">Select **Edit name** and provide a **Name** for the measure.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="3a8ec-118">Se a súa nova configuración de medida ten só dous campos, por exemplo, CustomerID e un cálculo, o resultado engadirase como nova columna á entidade xerada polo sistema chamada Customer_Measure.</span><span class="sxs-lookup"><span data-stu-id="3a8ec-118">If your new measure configuration has only two fields, for exmample, CustomerID and one calculation, the output will be added as a new column to the system generated entity called Customer_Measure.</span></span> <span data-ttu-id="3a8ec-119">E poderá ver o valor da medida no perfil de cliente unificado.</span><span class="sxs-lookup"><span data-stu-id="3a8ec-119">And you will be able to see the measure’s value in the unified customer profile.</span></span> <span data-ttu-id="3a8ec-120">Outras medidas xerarán as súas propias entidades.</span><span class="sxs-lookup"><span data-stu-id="3a8ec-120">Other measures will generate their own entities.</span></span>

1. <span data-ttu-id="3a8ec-121">Na área de configuración, escolla a función de agregación no menú despregable **Seleccionar función**.</span><span class="sxs-lookup"><span data-stu-id="3a8ec-121">In the configuration area, choose the aggregation function from the **Select Function** drop-down menu.</span></span> <span data-ttu-id="3a8ec-122">As funcións de agregación inclúen:</span><span class="sxs-lookup"><span data-stu-id="3a8ec-122">Aggregation functions include:</span></span> 
   - <span data-ttu-id="3a8ec-123">**Suma**</span><span class="sxs-lookup"><span data-stu-id="3a8ec-123">**Sum**</span></span>
   - <span data-ttu-id="3a8ec-124">**Media**</span><span class="sxs-lookup"><span data-stu-id="3a8ec-124">**Average**</span></span>
   - <span data-ttu-id="3a8ec-125">**Número total**</span><span class="sxs-lookup"><span data-stu-id="3a8ec-125">**Count**</span></span>
   - <span data-ttu-id="3a8ec-126">**Número único**</span><span class="sxs-lookup"><span data-stu-id="3a8ec-126">**Count Unique**</span></span>
   - <span data-ttu-id="3a8ec-127">**Máx.**</span><span class="sxs-lookup"><span data-stu-id="3a8ec-127">**Max**</span></span>
   - <span data-ttu-id="3a8ec-128">**Min**</span><span class="sxs-lookup"><span data-stu-id="3a8ec-128">**Min**</span></span>
   - <span data-ttu-id="3a8ec-129">**Primeiro**: toma o primeiro valor do rexistro de datos</span><span class="sxs-lookup"><span data-stu-id="3a8ec-129">**First**: takes the first value of the data record</span></span>
   - <span data-ttu-id="3a8ec-130">**Último**: toma o último valor que se engadiu ao rexistro de datos</span><span class="sxs-lookup"><span data-stu-id="3a8ec-130">**Last**: takes the last value that was added to the data record</span></span>

   :::image type="content" source="media/measure-operators.png" alt-text="Operadores para cálculos de medidas.":::

1. <span data-ttu-id="3a8ec-132">Seleccione **Engadir atributo** para seleccionar os datos que precisa para crear esta medida.</span><span class="sxs-lookup"><span data-stu-id="3a8ec-132">Select **Add attribute** to select the data you need to create this measure.</span></span>
   
   1. <span data-ttu-id="3a8ec-133">Seleccione o separador **Atributos**.</span><span class="sxs-lookup"><span data-stu-id="3a8ec-133">Select the **Attributes** tab.</span></span> 
   1. <span data-ttu-id="3a8ec-134">Entidade de datos: escolla a entidade que inclúe o atributo que desexa medir.</span><span class="sxs-lookup"><span data-stu-id="3a8ec-134">Data entity: Choose the entity that includes the attribute you want to measure.</span></span> 
   1. <span data-ttu-id="3a8ec-135">Atributo de datos: escolla o atributo que desexa usar na función de agregación para calcular a medida.</span><span class="sxs-lookup"><span data-stu-id="3a8ec-135">Data attribute: Choose the attribute you want to use in the aggregation function to calculate the measure.</span></span> <span data-ttu-id="3a8ec-136">Só pode seleccionar un atributo de cada vez.</span><span class="sxs-lookup"><span data-stu-id="3a8ec-136">You can only select one attribute at a time.</span></span>
   1. <span data-ttu-id="3a8ec-137">Tamén pode seleccionar un atributo de datos dunha medida existente seleccionando o separador **Medidas**. Ou pode buscar un nome de entidade ou medida.</span><span class="sxs-lookup"><span data-stu-id="3a8ec-137">You can also select a data attribute from an existing measure by selecting the **Measures** tab. Or, you can search for an entity or measure name.</span></span> 
   1. <span data-ttu-id="3a8ec-138">Seleccione **Engadir** para engadir o atributo seleccionado á medida.</span><span class="sxs-lookup"><span data-stu-id="3a8ec-138">Select **Add** to add the selected attribute to the measure.</span></span>

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Seleccione un atributo para usar nos cálculos.":::

1. <span data-ttu-id="3a8ec-140">Para construír medidas máis complexas, pode engadir máis atributos ou usar operadores matemáticos na súa función de medida.</span><span class="sxs-lookup"><span data-stu-id="3a8ec-140">To build more complex measures, you can add more attributes or use math operators on your measure function.</span></span>

   :::image type="content" source="media/measure-math-operators.png" alt-text="Cree unha medida complexa con operadores matemáticos.":::

1. <span data-ttu-id="3a8ec-142">Para engadir filtros, seleccione o **Filtro** na área de configuración.</span><span class="sxs-lookup"><span data-stu-id="3a8ec-142">To add filters, select the **Filter** in the configuration area.</span></span> 
  
   1. <span data-ttu-id="3a8ec-143">Na sección **Engadir atributo** do panel **Filtros**, seleccione o atributo que desexa usar para crear filtros.</span><span class="sxs-lookup"><span data-stu-id="3a8ec-143">In **Add attribute** section of the **Filters** pane, select the attribute you want to use to create filters.</span></span>
   1. <span data-ttu-id="3a8ec-144">Configure os operadores de filtros para definir o filtro para cada atributo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="3a8ec-144">Set the filter operators to define the filter for every selected attribute.</span></span>
   1. <span data-ttu-id="3a8ec-145">Seleccione **Aplicar** para engadir os filtros á medida.</span><span class="sxs-lookup"><span data-stu-id="3a8ec-145">Select **Apply** to add the filters to the measure.</span></span>

1. <span data-ttu-id="3a8ec-146">Para engadir dimensións, seleccione **Dimensión** na área de configuración.</span><span class="sxs-lookup"><span data-stu-id="3a8ec-146">To add dimensions, select **Dimension** in the configuration area.</span></span> <span data-ttu-id="3a8ec-147">As dimensións mostraranse como columnas na entidade de saída de medida.</span><span class="sxs-lookup"><span data-stu-id="3a8ec-147">Dimensions will show as columns in the measure output entity.</span></span>
   1. <span data-ttu-id="3a8ec-148">Seleccione **Editar dimensións** para engadir atributos de datos polos que desexa agrupar os valores da medida.</span><span class="sxs-lookup"><span data-stu-id="3a8ec-148">Select **Edit dimensions** to add data attributes you want to group the measure values by.</span></span> <span data-ttu-id="3a8ec-149">Por exemplo, cidade ou sexo.</span><span class="sxs-lookup"><span data-stu-id="3a8ec-149">For example, city or gender.</span></span> <span data-ttu-id="3a8ec-150">Por defecto, a dimensión *CustomerID* seleccionouse para crear *medidas a nivel de cliente*.</span><span class="sxs-lookup"><span data-stu-id="3a8ec-150">By default, the *CustomerID* dimension is selected to create *customer-level measures*.</span></span> <span data-ttu-id="3a8ec-151">Pode eliminar a dimensión predeterminada se quere crear *medidas a nivel empresarial*.</span><span class="sxs-lookup"><span data-stu-id="3a8ec-151">You can remove the default dimension if you want to create *business-level measures*.</span></span>
   1. <span data-ttu-id="3a8ec-152">Seleccione **Feito** para engadir as dimensións á medida.</span><span class="sxs-lookup"><span data-stu-id="3a8ec-152">Select **Done** to add the dimensions to the measure.</span></span>

1. <span data-ttu-id="3a8ec-153">Se hai valores nos seus datos que debe substituír por un número enteiro, por exemplo, substituír *cero* por *0*, seleccione **Regras**.</span><span class="sxs-lookup"><span data-stu-id="3a8ec-153">If there are values in your data that you need to replace with an integer, for example, replace *null* with *0*, select **Rules**.</span></span> <span data-ttu-id="3a8ec-154">Configure a regra e asegúrese de que escolle só números enteiros como substitutos.</span><span class="sxs-lookup"><span data-stu-id="3a8ec-154">Configure the rule and make sure that you choose only whole numbers as replacements.</span></span>

1. <span data-ttu-id="3a8ec-155">Se hai varias rutas entre a entidade de datos que asignou e a entidade *Cliente*, ten que escoller un dos [camiños de relación de entidade](relationships.md) identificados.</span><span class="sxs-lookup"><span data-stu-id="3a8ec-155">If there are multiple paths between the data entity you mapped and the *Customer* entity, you have to choose one of the identified [entity relationship paths](relationships.md).</span></span> <span data-ttu-id="3a8ec-156">Os resultados das medidas poden variar dependendo do camiño seleccionado.</span><span class="sxs-lookup"><span data-stu-id="3a8ec-156">Measure results can vary depending on the selected path.</span></span> 
   1. <span data-ttu-id="3a8ec-157">Seleccione **Preferencias de datos** e elixa o camiño da entidade que se debería empregar para identificar a súa medida.</span><span class="sxs-lookup"><span data-stu-id="3a8ec-157">Select **Data preferences** and choose the entity path that should be used to identify your measure.</span></span> <span data-ttu-id="3a8ec-158">Se só hai un único camiño cara á entidade *Cliente*, este control non se amosará.</span><span class="sxs-lookup"><span data-stu-id="3a8ec-158">If there's only a single path to the *Customer* entity, this control won't show.</span></span>
   1. <span data-ttu-id="3a8ec-159">Seleccione **Feito** para aplicar a súa selección.</span><span class="sxs-lookup"><span data-stu-id="3a8ec-159">Select **Done** to apply your selection.</span></span> 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Seleccione o camiño da entidade para a medida.":::

1. <span data-ttu-id="3a8ec-161">Para engadir máis cálculos para a medida, seleccione **Novo cálculo**.</span><span class="sxs-lookup"><span data-stu-id="3a8ec-161">To add more calculations for the measure, select **New calculation**.</span></span> <span data-ttu-id="3a8ec-162">Só pode usar entidades na mesma ruta de entidade para novos cálculos.</span><span class="sxs-lookup"><span data-stu-id="3a8ec-162">You can only use entities on the same entity path for new calculations.</span></span> <span data-ttu-id="3a8ec-163">Máis cálculos mostraranse como columnas novas na entidade de saída de medida.</span><span class="sxs-lookup"><span data-stu-id="3a8ec-163">More calculations will show as new columns in the measure output entity.</span></span>

1. <span data-ttu-id="3a8ec-164">Seleccione **...** sobre o cálculo para **Duplicar**, **Cambiar o nome** ou **Quitar** un cálculo dunha medida.</span><span class="sxs-lookup"><span data-stu-id="3a8ec-164">Select **...** on the calculation to **Duplicate**, **Rename**, or **Remove** a calculation from a measure.</span></span>

1. <span data-ttu-id="3a8ec-165">Na área **Vista previa**, verá o esquema de datos da entidade de saída de medida, incluídos filtros e dimensións.</span><span class="sxs-lookup"><span data-stu-id="3a8ec-165">In the **Preview** area, you'll see the data schema of the measure output entity, including filters and dimensions.</span></span> <span data-ttu-id="3a8ec-166">A vista previa reacciona dinamicamente aos cambios na configuración.</span><span class="sxs-lookup"><span data-stu-id="3a8ec-166">The preview reacts dynamically to changes in the configuration.</span></span>

1. <span data-ttu-id="3a8ec-167">Seleccione **Executar** para calcular os resultados da medida configurada.</span><span class="sxs-lookup"><span data-stu-id="3a8ec-167">Select **Run** to calculate results for the configured measure.</span></span> <span data-ttu-id="3a8ec-168">Seleccione **Gardar e pechar** se quere manter a configuración actual e executar a medida máis tarde.</span><span class="sxs-lookup"><span data-stu-id="3a8ec-168">Select **Save and close** if you want to keep the current configuration and run the measure later.</span></span>

1. <span data-ttu-id="3a8ec-169">Vaia a **Medidas** para ver na lista a medida recentemente creada.</span><span class="sxs-lookup"><span data-stu-id="3a8ec-169">Go to **Measures** to see the newly created measure in the list.</span></span>

## <a name="use-a-template-to-build-a-measure"></a><span data-ttu-id="3a8ec-170">Usar un modelo para construír unha medida</span><span class="sxs-lookup"><span data-stu-id="3a8ec-170">Use a template to build a measure</span></span>

<span data-ttu-id="3a8ec-171">Pode usar modelos predefinidos de medidas de uso común para crealas.</span><span class="sxs-lookup"><span data-stu-id="3a8ec-171">You can use predefined templates of commonly used measures to create them.</span></span> <span data-ttu-id="3a8ec-172">As descricións detalladas dos modelos e unha experiencia guiada axúdanlle a crear medidas eficientes.</span><span class="sxs-lookup"><span data-stu-id="3a8ec-172">Detailed descriptions of the templates and a guided experience help you with efficient measure creation.</span></span> <span data-ttu-id="3a8ec-173">Os modelos baséanse en datos asignados da entidade *Actividade unificada*.</span><span class="sxs-lookup"><span data-stu-id="3a8ec-173">Templates build on mapped data from the *Unified Activity* entity.</span></span> <span data-ttu-id="3a8ec-174">Asegúrese de que configurou [actividades do cliente](activities.md) antes de crear unha medida a partir dun modelo.</span><span class="sxs-lookup"><span data-stu-id="3a8ec-174">So make sure you have configured [customer activities](activities.md) before you create a measure from a template.</span></span>

<span data-ttu-id="3a8ec-175">Modelos de medidas dispoñibles:</span><span class="sxs-lookup"><span data-stu-id="3a8ec-175">Available measure templates:</span></span> 
- <span data-ttu-id="3a8ec-176">Valor medio da transacción</span><span class="sxs-lookup"><span data-stu-id="3a8ec-176">Average transaction value (ATV)</span></span>
- <span data-ttu-id="3a8ec-177">Valor total das transaccións</span><span class="sxs-lookup"><span data-stu-id="3a8ec-177">Total transaction value</span></span>
- <span data-ttu-id="3a8ec-178">Ingresos medios diarios</span><span class="sxs-lookup"><span data-stu-id="3a8ec-178">Average daily revenue</span></span>
- <span data-ttu-id="3a8ec-179">Ingresos medios anuais</span><span class="sxs-lookup"><span data-stu-id="3a8ec-179">Average yearly revenue</span></span>
- <span data-ttu-id="3a8ec-180">Número de transaccións</span><span class="sxs-lookup"><span data-stu-id="3a8ec-180">Transaction count</span></span>
- <span data-ttu-id="3a8ec-181">Puntos de fidelidade obtidos</span><span class="sxs-lookup"><span data-stu-id="3a8ec-181">Loyalty points earned</span></span>
- <span data-ttu-id="3a8ec-182">Puntos de fidelidade trocados</span><span class="sxs-lookup"><span data-stu-id="3a8ec-182">Loyalty points redeemed</span></span>
- <span data-ttu-id="3a8ec-183">Saldo de puntos de fidelidade</span><span class="sxs-lookup"><span data-stu-id="3a8ec-183">Loyalty points balance</span></span>
- <span data-ttu-id="3a8ec-184">Período activo do cliente</span><span class="sxs-lookup"><span data-stu-id="3a8ec-184">Active customer lifespan</span></span>
- <span data-ttu-id="3a8ec-185">Duración da afiliación de fidelidade</span><span class="sxs-lookup"><span data-stu-id="3a8ec-185">Loyalty membership duration</span></span>
- <span data-ttu-id="3a8ec-186">Tempo desde a última compra</span><span class="sxs-lookup"><span data-stu-id="3a8ec-186">Time since last purchase</span></span>

<span data-ttu-id="3a8ec-187">O seguinte procedemento describe os pasos para construír unha nova medida mediante un modelo.</span><span class="sxs-lookup"><span data-stu-id="3a8ec-187">The following procedure outlines the steps to build a new measure using a template.</span></span>

1. <span data-ttu-id="3a8ec-188">Na información do público, vaia a **Medidas**.</span><span class="sxs-lookup"><span data-stu-id="3a8ec-188">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="3a8ec-189">Seleccione **Novo** e logo seleccione **Escoller un modelo**.</span><span class="sxs-lookup"><span data-stu-id="3a8ec-189">Select **New** and select **Choose a template**.</span></span>

   :::image type="content" source="media/measure-use-template.png" alt-text="Captura de pantalla do menú despregable cando se crea unha nova medida con fincapé no modelo.":::

1. <span data-ttu-id="3a8ec-191">Busque o modelo que se adapte ás súas necesidades e seleccione **Escoller modelo**.</span><span class="sxs-lookup"><span data-stu-id="3a8ec-191">Find the template that fits your need and select **Choose template**.</span></span>

1. <span data-ttu-id="3a8ec-192">Revise os datos requiridos e seleccione **Comezar** se ten todos os datos no seu lugar.</span><span class="sxs-lookup"><span data-stu-id="3a8ec-192">Review the required data and select **Get started** if you have all the data in place.</span></span>

1. <span data-ttu-id="3a8ec-193">No panel **Editar nome**, estableza o nome da medida e a entidade de saída.</span><span class="sxs-lookup"><span data-stu-id="3a8ec-193">In the **Edit name** pane, set the name for your measure and the output entity.</span></span> 

1. <span data-ttu-id="3a8ec-194">Seleccione **Feito**.</span><span class="sxs-lookup"><span data-stu-id="3a8ec-194">Select **Done**.</span></span>

1. <span data-ttu-id="3a8ec-195">Na sección **Establecer o período de tempo**, defina o período de tempo dos datos que se van usar.</span><span class="sxs-lookup"><span data-stu-id="3a8ec-195">In the **Set time period** section, define the time frame of the data to use.</span></span> <span data-ttu-id="3a8ec-196">Escolla se desexa que a nova medida abranga todo o conxunto de datos seleccionando **Todo o tempo**.</span><span class="sxs-lookup"><span data-stu-id="3a8ec-196">Choose if you want the new measure to cover the entire data set by selecting **All time**.</span></span> <span data-ttu-id="3a8ec-197">Ou se quere que a medida se centre nun **Período de tempo específico**.</span><span class="sxs-lookup"><span data-stu-id="3a8ec-197">Or if you want the measure to focus on a **Specific time period**.</span></span>

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Captura de pantalla que mostra a sección do período de tempo ao configurar unha medida a partir dun modelo.":::

1. <span data-ttu-id="3a8ec-199">Na seguinte sección, seleccione **Engadir datos** para escoller as actividades e asignar os datos correspondentes da súa entidade *Actividade unificada*.</span><span class="sxs-lookup"><span data-stu-id="3a8ec-199">In the next section, select **Add data** to choose the activities and map the corresponding data from your *Unified Activity* entity.</span></span>

    1. <span data-ttu-id="3a8ec-200">Paso 1 de 2: en **Tipo de actividade**, escolla o tipo de entidade que desexa empregar.</span><span class="sxs-lookup"><span data-stu-id="3a8ec-200">Step 1 of 2: Under **Activity type**, choose the type of the entity you want to use.</span></span> <span data-ttu-id="3a8ec-201">Para **Actividades**, seleccione as entidades que desexa asignar.</span><span class="sxs-lookup"><span data-stu-id="3a8ec-201">For **Activities**, select the entities you want to map.</span></span>
    1. <span data-ttu-id="3a8ec-202">Paso 2 de 2: escolla o atributo da entidade *Actividade unificada* para o compoñente requirido pola fórmula.</span><span class="sxs-lookup"><span data-stu-id="3a8ec-202">Step 2 of 2: Choose the attribute from the *Unified Activity* entity for the component required by the formula.</span></span> <span data-ttu-id="3a8ec-203">Por exemplo, para o valor medio da transacción, é o atributo que representa o valor da transacción.</span><span class="sxs-lookup"><span data-stu-id="3a8ec-203">For example, for Average transaction value, it's the attribute representing the Transaction value.</span></span> <span data-ttu-id="3a8ec-204">Para **Marca de tempo da actividade**, escolla o atributo da entidade de actividade unificada que representa a data e hora da actividade.</span><span class="sxs-lookup"><span data-stu-id="3a8ec-204">For **Activity timestamp**, choose the attribute from the Unified Activity entity that represents the date and time of the activity.</span></span>
   
1. <span data-ttu-id="3a8ec-205">Unha vez que a asignación de datos teña éxito, pode ver o estado como **Completo** e o nome das actividades e atributos asignados.</span><span class="sxs-lookup"><span data-stu-id="3a8ec-205">Once the data mapping is successful, you can see the status as **Complete** and the name of the mapped activities and attributes.</span></span>

   :::image type="content" source="media/measure-template-configured.png" alt-text="Captura de pantalla dunha configuración do modelo de medida completa.":::

1. <span data-ttu-id="3a8ec-207">Agora pode seleccionar **Executar** para calcular os resultados da medida.</span><span class="sxs-lookup"><span data-stu-id="3a8ec-207">You can now select **Run** to calculate the results of the measure.</span></span> <span data-ttu-id="3a8ec-208">Para refinalo máis tarde, selecciona **Gardar borrador**.</span><span class="sxs-lookup"><span data-stu-id="3a8ec-208">To refine it later, select **Save draft**.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="3a8ec-209">Xestionar as súas medidas</span><span class="sxs-lookup"><span data-stu-id="3a8ec-209">Manage your measures</span></span>

<span data-ttu-id="3a8ec-210">Pode atopar a lista de medidas na páxina **Medidas**.</span><span class="sxs-lookup"><span data-stu-id="3a8ec-210">You can find the list of measures on the **Measures** page.</span></span>

<span data-ttu-id="3a8ec-211">Atopará información sobre o tipo de medida, o creador, a data de creación, o estado e o estado.</span><span class="sxs-lookup"><span data-stu-id="3a8ec-211">You'll find information about the measure type, the creator, creation date, status, and state.</span></span> <span data-ttu-id="3a8ec-212">Cando selecciona unha medida da lista, pode previsualizar a saída e descargar un ficheiro .CSV.</span><span class="sxs-lookup"><span data-stu-id="3a8ec-212">When you select a measure from the list, you can preview the output and download a .CSV file.</span></span>

<span data-ttu-id="3a8ec-213">Para actualizar todas as túas medidas ao mesmo tempo, seleccione **Actualizar todo** sen seleccionar unha medida específica.</span><span class="sxs-lookup"><span data-stu-id="3a8ec-213">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="3a8ec-214">![Accións para xestionar medidas individuais](media/measure-actions.png "Accións para xestionar medidas individuais")</span><span class="sxs-lookup"><span data-stu-id="3a8ec-214">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="3a8ec-215">Seleccione unha medida da lista para as seguintes opcións:</span><span class="sxs-lookup"><span data-stu-id="3a8ec-215">Select a measure from the list for the following options:</span></span>

- <span data-ttu-id="3a8ec-216">Seleccione o nome da medida para ver os seus detalles.</span><span class="sxs-lookup"><span data-stu-id="3a8ec-216">Select the measure name to see its details.</span></span>
- <span data-ttu-id="3a8ec-217">**Editar** a configuración da medida.</span><span class="sxs-lookup"><span data-stu-id="3a8ec-217">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="3a8ec-218">**Actualizar** a medida segundo os últimos datos.</span><span class="sxs-lookup"><span data-stu-id="3a8ec-218">**Refresh** the measure based on the latest data.</span></span>
- <span data-ttu-id="3a8ec-219">**Cambiar o nome** da medida.</span><span class="sxs-lookup"><span data-stu-id="3a8ec-219">**Rename** the measure.</span></span>
- <span data-ttu-id="3a8ec-220">**Eliminar** a medida.</span><span class="sxs-lookup"><span data-stu-id="3a8ec-220">**Delete** the measure.</span></span>
- <span data-ttu-id="3a8ec-221">**Activar** ou **Desactivar**.</span><span class="sxs-lookup"><span data-stu-id="3a8ec-221">**Activate** or **Deactivate**.</span></span> <span data-ttu-id="3a8ec-222">As medidas inactivas non se actualizarán durante unha [actualización programada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="3a8ec-222">Inactive measures won't get refreshed during a [scheduled refresh](system.md#schedule-tab).</span></span>

> [!TIP]
> <span data-ttu-id="3a8ec-223">Existen [seis tipos de estado](system.md#status-types) para as tarefas ou os procesos.</span><span class="sxs-lookup"><span data-stu-id="3a8ec-223">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="3a8ec-224">Ademais, a maioría dos procesos [dependen doutros procesos descendentes](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="3a8ec-224">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="3a8ec-225">Pode seleccionar o estado dun proceso para ver detalles sobre o progreso de todo o traballo.</span><span class="sxs-lookup"><span data-stu-id="3a8ec-225">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="3a8ec-226">Despois de seleccionar **Ver detalles** para unha das tarefas do traballo, atopará información adicional: o tempo de procesamento, a última data de procesamento e todos os erros e avisos asociados á tarefa.</span><span class="sxs-lookup"><span data-stu-id="3a8ec-226">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="3a8ec-227">Seguinte paso</span><span class="sxs-lookup"><span data-stu-id="3a8ec-227">Next step</span></span>

<span data-ttu-id="3a8ec-228">Utilice as medidas existentes para crear [un segmento de clientes](segments.md).</span><span class="sxs-lookup"><span data-stu-id="3a8ec-228">You cam use existing measures to create [a customer segment](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]