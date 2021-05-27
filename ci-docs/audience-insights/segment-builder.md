---
title: Crear e xestionar segmentos
description: Cree segmentos de clientes para agrupalos en función de varios atributos.
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 550e509a24701fe5fcdeb9d54311872dc954156c
ms.sourcegitcommit: 72603fb39c4d5dbca71128815a2e1692542ea4dc
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 05/19/2021
ms.locfileid: "6064935"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="7358f-103">Crear e xestionar segmentos</span><span class="sxs-lookup"><span data-stu-id="7358f-103">Create and manage segments</span></span>

<span data-ttu-id="7358f-104">Defina filtros complexos arredor da entidade de cliente unificada e as entidades relacionadas.</span><span class="sxs-lookup"><span data-stu-id="7358f-104">Define complex filters around the unified customer entity and its related entities.</span></span> <span data-ttu-id="7358f-105">Cada segmento, despois do procesamento, crea un conxunto de rexistros de clientes que pode exportar e nos que pode tomar medidas.</span><span class="sxs-lookup"><span data-stu-id="7358f-105">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="7358f-106">Os segmentos xestionanse na páxina **Segmentos**.</span><span class="sxs-lookup"><span data-stu-id="7358f-106">Segments are managed on the **Segments** page.</span></span> 

<span data-ttu-id="7358f-107">O seguinte exemplo ilustra a capacidade de segmentación.</span><span class="sxs-lookup"><span data-stu-id="7358f-107">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="7358f-108">Definimos un segmento para clientes que solicitaron polo menos 500 $ de mercadorías nos últimos 90 días *e* que estiveron involucrados nunha chamada de servizo de atención ao cliente que se escalou.</span><span class="sxs-lookup"><span data-stu-id="7358f-108">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

:::image type="content" source="media/segmentation-group1-2.png" alt-text="Captura de pantalla da interface de usuario do creador de segmentos con dous grupos que especifican un segmento de cliente.":::

## <a name="create-a-new-segment"></a><span data-ttu-id="7358f-110">Crear un segmento novo</span><span class="sxs-lookup"><span data-stu-id="7358f-110">Create a new segment</span></span>

<span data-ttu-id="7358f-111">Hai varias formas de crear un novo segmento.</span><span class="sxs-lookup"><span data-stu-id="7358f-111">There are multiple ways to create a new segment.</span></span> <span data-ttu-id="7358f-112">Esta sección describe como crear un *segmento en branco* a partir de cero.</span><span class="sxs-lookup"><span data-stu-id="7358f-112">This section describes how to create a *blank segment* from scratch.</span></span> <span data-ttu-id="7358f-113">Tamén pode crear un *segmento rápido* baseado en entidades existentes ou usar os modelos de aprendizaxe automática para obter *segmentos suxeridos*.</span><span class="sxs-lookup"><span data-stu-id="7358f-113">You can also create a *quick segment* based on existing entities or make use of machine learning models to get *suggested segments*.</span></span> <span data-ttu-id="7358f-114">Máis información: [Visión xeral dos segmentos](segments.md).</span><span class="sxs-lookup"><span data-stu-id="7358f-114">More information: [Segments overview](segments.md).</span></span>

<span data-ttu-id="7358f-115">Ao crear un segmento, pode gardar un borrador.</span><span class="sxs-lookup"><span data-stu-id="7358f-115">While creating a segment, you can save a draft.</span></span> <span data-ttu-id="7358f-116">Gardarase como un segmento inactivo e non se pode activar até que se remate cunha configuración válida.</span><span class="sxs-lookup"><span data-stu-id="7358f-116">It will be saved as an inactive segment, and can't be activated it finished with a valid configuration.</span></span>

1. <span data-ttu-id="7358f-117">Vaia á páxina **Segmentos**.</span><span class="sxs-lookup"><span data-stu-id="7358f-117">Go to the **Segments** page.</span></span>

1. <span data-ttu-id="7358f-118">Seleccione **Novo** > **Segmento en branco**.</span><span class="sxs-lookup"><span data-stu-id="7358f-118">Select **New** > **Blank segment**.</span></span>

1. <span data-ttu-id="7358f-119">No panel **Novo segmento**, escolla un tipo de segmento:</span><span class="sxs-lookup"><span data-stu-id="7358f-119">In the **New segment** pane, choose a segment type:</span></span>

   - <span data-ttu-id="7358f-120">Os **segmentos dinámicos** [actualízanse](segments.md#refresh-segments) nunha programación periódica.</span><span class="sxs-lookup"><span data-stu-id="7358f-120">**Dynamic segments** [refresh](segments.md#refresh-segments) on a recurring schedule.</span></span>
   - <span data-ttu-id="7358f-121">Os **segmentos estáticos** execútanse unha vez cando se crean.</span><span class="sxs-lookup"><span data-stu-id="7358f-121">**Static segments** run once when you create it.</span></span>

1. <span data-ttu-id="7358f-122">Proporcione un **Nome da entidade de saída** para o segmento.</span><span class="sxs-lookup"><span data-stu-id="7358f-122">Provide an **Output entity name** for the segment.</span></span> <span data-ttu-id="7358f-123">Tamén pode proporcionar un nome para mostrar e unha descrición que axude a identificar o segmento.</span><span class="sxs-lookup"><span data-stu-id="7358f-123">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

1. <span data-ttu-id="7358f-124">Seleccione **Seguinte** para chegar á páxina **Construtor de segmentos** onde pode definir un grupo.</span><span class="sxs-lookup"><span data-stu-id="7358f-124">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="7358f-125">Un grupo é un conxunto de clientes.</span><span class="sxs-lookup"><span data-stu-id="7358f-125">A group is a set of customers.</span></span>

1. <span data-ttu-id="7358f-126">Escolla a entidade que inclúe o atributo polo que desexa segmentar.</span><span class="sxs-lookup"><span data-stu-id="7358f-126">Choose the entity that includes the attribute you want to segment by.</span></span>

1. <span data-ttu-id="7358f-127">Escolla o atributo polo que segmentar.</span><span class="sxs-lookup"><span data-stu-id="7358f-127">Choose the attribute to segment by.</span></span> <span data-ttu-id="7358f-128">Este atributo pode ter un dos catro tipos de valor seguintes: numérico, cadea, data ou booleano.</span><span class="sxs-lookup"><span data-stu-id="7358f-128">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

1. <span data-ttu-id="7358f-129">Escolla un operador e un valor para o atributo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="7358f-129">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="7358f-130">![Filtro de grupo personalizado](media/customer-group-numbers.png "Filtro de grupo de clientes")</span><span class="sxs-lookup"><span data-stu-id="7358f-130">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="7358f-131">Número</span><span class="sxs-lookup"><span data-stu-id="7358f-131">Number</span></span> |<span data-ttu-id="7358f-132">Definición</span><span class="sxs-lookup"><span data-stu-id="7358f-132">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="7358f-133">1</span><span class="sxs-lookup"><span data-stu-id="7358f-133">1</span></span>     |<span data-ttu-id="7358f-134">Entity</span><span class="sxs-lookup"><span data-stu-id="7358f-134">Entity</span></span>          |
   |<span data-ttu-id="7358f-135">2</span><span class="sxs-lookup"><span data-stu-id="7358f-135">2</span></span>     |<span data-ttu-id="7358f-136">Atributo</span><span class="sxs-lookup"><span data-stu-id="7358f-136">Attribute</span></span>          |
   |<span data-ttu-id="7358f-137">3</span><span class="sxs-lookup"><span data-stu-id="7358f-137">3</span></span>    |<span data-ttu-id="7358f-138">Operador</span><span class="sxs-lookup"><span data-stu-id="7358f-138">Operator</span></span>         |
   |<span data-ttu-id="7358f-139">4</span><span class="sxs-lookup"><span data-stu-id="7358f-139">4</span></span>    |<span data-ttu-id="7358f-140">Valor</span><span class="sxs-lookup"><span data-stu-id="7358f-140">Value</span></span>         |

   1. <span data-ttu-id="7358f-141">Para engadir máis condicións a un grupo, pode usar dous operadores lóxicos:</span><span class="sxs-lookup"><span data-stu-id="7358f-141">To add more conditions to a group, you can use two logical operators:</span></span>

      - <span data-ttu-id="7358f-142">Operador **AND**: as dúas condicións deben cumprirse como parte do proceso de segmentación.</span><span class="sxs-lookup"><span data-stu-id="7358f-142">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="7358f-143">Esta opción é máis útil cando define condicións entre diferentes entidades.</span><span class="sxs-lookup"><span data-stu-id="7358f-143">This option is most useful when you define conditions across different entities.</span></span>

      - <span data-ttu-id="7358f-144">Operador **OR**: calquera das condicións debe ser cumprida como parte do proceso de segmentación.</span><span class="sxs-lookup"><span data-stu-id="7358f-144">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="7358f-145">Esta opción é máis útil cando define varias condicións para a mesma entidade.</span><span class="sxs-lookup"><span data-stu-id="7358f-145">This option is most useful when you define multiple conditions for the same entity.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="7358f-146">![Operador OR onde se debe cumprir calquera das dúas condicións](media/segmentation-either-condition.png "Operador OR onde se debe cumprir calquera das dúas condicións")</span><span class="sxs-lookup"><span data-stu-id="7358f-146">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

      <span data-ttu-id="7358f-147">Actualmente é posible aniñar un operador **OR** baixo un operador **AND**, pero non ao revés.</span><span class="sxs-lookup"><span data-stu-id="7358f-147">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

   1. <span data-ttu-id="7358f-148">Cada grupo coincide cun conxunto de clientes.</span><span class="sxs-lookup"><span data-stu-id="7358f-148">Each group matches set of customers.</span></span> <span data-ttu-id="7358f-149">Pode combinar grupos para incluír os clientes necesarios para o seu caso de empresa.</span><span class="sxs-lookup"><span data-stu-id="7358f-149">You can combine groups to include the customers required for your business case.</span></span>    
   <span data-ttu-id="7358f-150">Seleccione **Engadir grupo**.</span><span class="sxs-lookup"><span data-stu-id="7358f-150">Select **Add Group**.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="7358f-151">![Grupo de engadir grupo de clientes](media/customer-group-add-group.png "Grupo de engadir grupo de clientes")</span><span class="sxs-lookup"><span data-stu-id="7358f-151">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

   1. <span data-ttu-id="7358f-152">Seleccione un dos operadores de definición: **Unión**, **Intersección** ou **Excepto**.</span><span class="sxs-lookup"><span data-stu-id="7358f-152">Select one of the set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="7358f-153">![Unión de engadir grupo de clientes](media/customer-group-union.png "Unión de engadir grupo de clientes")</span><span class="sxs-lookup"><span data-stu-id="7358f-153">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   - <span data-ttu-id="7358f-154">**Unión** une os dous grupos.</span><span class="sxs-lookup"><span data-stu-id="7358f-154">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="7358f-155">**Intersección** solapa os dous grupos.</span><span class="sxs-lookup"><span data-stu-id="7358f-155">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="7358f-156">Só datos que *son comúns* a ambos os grupos mantéñense no grupo unificado.</span><span class="sxs-lookup"><span data-stu-id="7358f-156">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="7358f-157">**Excepto** combina os dous grupos.</span><span class="sxs-lookup"><span data-stu-id="7358f-157">**Except** combines the two groups.</span></span> <span data-ttu-id="7358f-158">Só datos do grupo A que *non son comúns* aos datos do grupo B mantéñense.</span><span class="sxs-lookup"><span data-stu-id="7358f-158">Only data in group A that *is not common* to data in group B is retained.</span></span>

1. <span data-ttu-id="7358f-159">Se a entidade está conectada á entidade de cliente unificada mediante [relacións](relationships.md), necesita definir o camiño da relación para crear un segmento válido.</span><span class="sxs-lookup"><span data-stu-id="7358f-159">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="7358f-160">Engada as entidades do camiño da relación ata que poida seleccionar a entidade **Cliente: CustomerInsights** no menú despregable.</span><span class="sxs-lookup"><span data-stu-id="7358f-160">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="7358f-161">Despois, escolla **Todos os rexistros** para cada paso.</span><span class="sxs-lookup"><span data-stu-id="7358f-161">Then, choose **All records** for each step.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="7358f-162">![Camiño de relación durante a creación do segmento](media/segments-multiple-relationships.png "Camiño de relación durante a creación do segmento")</span><span class="sxs-lookup"><span data-stu-id="7358f-162">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

1. <span data-ttu-id="7358f-163">De xeito predeterminado, os segmentos xeran unha entidade de saída que contén todos os atributos dos perfís de clientes que coinciden cos filtros definidos.</span><span class="sxs-lookup"><span data-stu-id="7358f-163">By default, segments generate an output entity that contains all attributes of customer profiles which match the defined filters.</span></span> <span data-ttu-id="7358f-164">Se un segmento está baseado noutras entidades que non son o *Cliente*, pode engadir máis atributos destas entidades á entidade de saída.</span><span class="sxs-lookup"><span data-stu-id="7358f-164">If a segment is based on other entities than the *Customer* entity, you can add more attributes from these entities to the output entity.</span></span> <span data-ttu-id="7358f-165">Seleccione **Atributos do proxecto** para escoller os atributos que se engadirán á entidade de saída.</span><span class="sxs-lookup"><span data-stu-id="7358f-165">Select **Project attributes** to choose the attributes that will be appended to the output entity.</span></span>  
  
   <span data-ttu-id="7358f-166">Exemplo: un segmento baséase nunha entidade que contén datos de actividade do cliente relacionados coa entidade *Cliente*.</span><span class="sxs-lookup"><span data-stu-id="7358f-166">Example: A segment is based on an entity that contains customer activity data which is related to the *Customer* entity.</span></span> <span data-ttu-id="7358f-167">O segmento busca a todos os clientes que chamaron ao servizo de asistencia nos últimos 60 días.</span><span class="sxs-lookup"><span data-stu-id="7358f-167">The segment looks for all customers that called the help desk in the last 60 days.</span></span> <span data-ttu-id="7358f-168">Pode escoller engadir a duración da chamada e o número de chamadas a todos os rexistros de clientes coincidentes da entidade de saída.</span><span class="sxs-lookup"><span data-stu-id="7358f-168">You can choose to append the call duration and the number of calls to all matching customer records in the output entity.</span></span> <span data-ttu-id="7358f-169">Esta información pode ser útil para enviar un correo electrónico con ligazóns útiles a artigos de axuda en liña e preguntas frecuentes aos clientes que chamaron con frecuencia.</span><span class="sxs-lookup"><span data-stu-id="7358f-169">This information might be useful to send an email with helpful links to online help articles and FAQs to customers who called frequently.</span></span>

   > [!NOTE]
   > - <span data-ttu-id="7358f-170">Os atributos proxectados só funcionan para entidades que teñen unha relación de un a varios coa entidade do cliente.</span><span class="sxs-lookup"><span data-stu-id="7358f-170">Projected attributes only work for entities that have a one-to-many relationship with the customer entity.</span></span> <span data-ttu-id="7358f-171">Por exemplo, un cliente pode ter varias subscricións.</span><span class="sxs-lookup"><span data-stu-id="7358f-171">For example, one customer can have multiple subscriptions.</span></span>
   > - <span data-ttu-id="7358f-172">Só pode proxectar atributos dunha entidade que se use en todos os grupos de consultas de segmento que está a compilar.</span><span class="sxs-lookup"><span data-stu-id="7358f-172">You can only project attributes from an entity that is used in every group of segment query you are building.</span></span>
   > - <span data-ttu-id="7358f-173">Os atributos proxectados téñense en conta cando se usan operadores de definición.</span><span class="sxs-lookup"><span data-stu-id="7358f-173">Projected attributes are factored in when using set operators.</span></span>

1. <span data-ttu-id="7358f-174">Seleccione **Gardar** para gardar o segmento.</span><span class="sxs-lookup"><span data-stu-id="7358f-174">Select **Save** to save your segment.</span></span> <span data-ttu-id="7358f-175">O teu segmento gardarase e procesarase se todos os requisitos están validados.</span><span class="sxs-lookup"><span data-stu-id="7358f-175">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="7358f-176">Se non, gardarase como borrador.</span><span class="sxs-lookup"><span data-stu-id="7358f-176">Otherwise, it will be saved as a draft.</span></span>

1. <span data-ttu-id="7358f-177">Seleccione **Volver a segmentos** para volver á páxina **Segmentos**.</span><span class="sxs-lookup"><span data-stu-id="7358f-177">Select **Back to segments** to go back to the **Segments** page.</span></span>



## <a name="quick-segments"></a><span data-ttu-id="7358f-178">Segmentos rápidos</span><span class="sxs-lookup"><span data-stu-id="7358f-178">Quick segments</span></span>

<span data-ttu-id="7358f-179">Os segmentos rápidos permítenlle crear rapidamente segmentos sinxelos cun único operador para obter información máis rápido.</span><span class="sxs-lookup"><span data-stu-id="7358f-179">Quick segments let you build simple segments with a single operator quickly for faster insights.</span></span>

1. <span data-ttu-id="7358f-180">Na páxina **Segmentos**, seleccione **Novo** > **Crear desde**.</span><span class="sxs-lookup"><span data-stu-id="7358f-180">On the **Segments** page, select **New** > **Create from**.</span></span>

   - <span data-ttu-id="7358f-181">Seleccione a opción **Perfís** para crear un segmento baseado na entidade de *cliente unificada*.</span><span class="sxs-lookup"><span data-stu-id="7358f-181">Select the **Profiles** option to build a segment that is based on the *unified customer* entity.</span></span>
   - <span data-ttu-id="7358f-182">Seleccione a opción **Medidas** para crear un segmento arredor das medidas creadas previamente.</span><span class="sxs-lookup"><span data-stu-id="7358f-182">Select the **Measures** option to build a segment around  measures you have previously created.</span></span>
   - <span data-ttu-id="7358f-183">Seleccione a opción **Intelixencia** para construír un segmento arredor dunha das entidades de saída que xerou usando calquera das funcións de **Predicións** ou **Modelos personalizados**.</span><span class="sxs-lookup"><span data-stu-id="7358f-183">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="7358f-184">Na caixa de diálogo **Novo segmento rápido**, seleccione un atributo no menú despregable **Campo**.</span><span class="sxs-lookup"><span data-stu-id="7358f-184">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="7358f-185">O sistema proporcionará información adicional que lle axudará a crear mellores segmentos dos seus clientes.</span><span class="sxs-lookup"><span data-stu-id="7358f-185">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="7358f-186">Por campos categóricos, mostraremos as 10 contas máis importantes de clientes.</span><span class="sxs-lookup"><span data-stu-id="7358f-186">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="7358f-187">Escolla un **Valor** e seleccione **Revisar**.</span><span class="sxs-lookup"><span data-stu-id="7358f-187">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="7358f-188">Para un atributo numérico, o sistema mostrará que valor de atributo está no percentil de cada cliente.</span><span class="sxs-lookup"><span data-stu-id="7358f-188">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="7358f-189">Elixa un **Operador** e un **Valor** e logo seleccione **Revisar**.</span><span class="sxs-lookup"><span data-stu-id="7358f-189">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="7358f-190">O sistema forneceralle un **Tamaño de segmento estimado**.</span><span class="sxs-lookup"><span data-stu-id="7358f-190">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="7358f-191">Pode escoller se quere xerar o segmento que definiu ou primeiro revisalo para obter un tamaño de segmento diferente.</span><span class="sxs-lookup"><span data-stu-id="7358f-191">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="7358f-192">![Nome e estimación para un segmento rápido](media/quick-segment-name.png "Nome e estimación para un segmento rápido")</span><span class="sxs-lookup"><span data-stu-id="7358f-192">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="7358f-193">Proporcione un **Nome** para o segmento.</span><span class="sxs-lookup"><span data-stu-id="7358f-193">Provide a **Name** for your segment.</span></span> <span data-ttu-id="7358f-194">Tamén pode fornecer un **nome para mostrar**.</span><span class="sxs-lookup"><span data-stu-id="7358f-194">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="7358f-195">Seleccione **Gardar** para crear o seu segmento.</span><span class="sxs-lookup"><span data-stu-id="7358f-195">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="7358f-196">Despois de que o segmento remate de procesarse, pode visualizalo como calquera outro segmento que crease.</span><span class="sxs-lookup"><span data-stu-id="7358f-196">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

## <a name="next-steps"></a><span data-ttu-id="7358f-197">Pasos seguintes</span><span class="sxs-lookup"><span data-stu-id="7358f-197">Next steps</span></span>

<span data-ttu-id="7358f-198">[Exporte un segmento](export-destinations.md) e explore a [Tarxeta de cliente](customer-card-add-in.md) e os [conectores](export-power-bi.md) para obter información sobre o nivel de cliente.</span><span class="sxs-lookup"><span data-stu-id="7358f-198">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
