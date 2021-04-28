---
title: Actividades do cliente
description: Defina as actividades dos clientes e visualíceas na cronoloxía do cliente.
ms.date: 04/07/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: 0c728fad4ed00d1bf085fed60057211861b3a195
ms.sourcegitcommit: f0855bd7762b1f0a1d3dd5259e23c95e1b0a6a93
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 04/07/2021
ms.locfileid: "5866405"
---
# <a name="customer-activities"></a><span data-ttu-id="4da84-103">Actividades do cliente</span><span class="sxs-lookup"><span data-stu-id="4da84-103">Customer activities</span></span>

<span data-ttu-id="4da84-104">Combine as actividades dos clientes desde [varias fontes de datos](data-sources.md) en Dynamics 365 Customer Insights para crear unha liña de tempo que liste as actividades cronoloxicamente.</span><span class="sxs-lookup"><span data-stu-id="4da84-104">Combine customer activities from [various data sources](data-sources.md) in Dynamics 365 Customer Insights to create a timeline that lists the activities chronologically.</span></span> <span data-ttu-id="4da84-105">Inclúa a cronoloxía nas aplicacións de Dynamics 365 coa solución [Complemento de tarxeta de cliente](customer-card-add-in.md), ou nun panel de Power BI.</span><span class="sxs-lookup"><span data-stu-id="4da84-105">Include the timeline in Dynamics 365 apps with the [Customer Card add-in](customer-card-add-in.md) solution, or in a Power BI dashboard.</span></span>

## <a name="define-an-activity"></a><span data-ttu-id="4da84-106">Definir unha actividade</span><span class="sxs-lookup"><span data-stu-id="4da84-106">Define an activity</span></span>

<span data-ttu-id="4da84-107">As súas fontes de datos poden incluír entidades con datos de transaccións e actividades de varias fontes de datos.</span><span class="sxs-lookup"><span data-stu-id="4da84-107">Your data sources can include entities with transactional and activity data from multiple data sources.</span></span> <span data-ttu-id="4da84-108">Identifique estas entidades e seleccione as actividades que desexa ver na liña de tempo do cliente.</span><span class="sxs-lookup"><span data-stu-id="4da84-108">Identify these entities and select the activities you want to view on the customer's timeline.</span></span> <span data-ttu-id="4da84-109">Escolla a entidade que inclúe a súa actividade ou actividades de destino.</span><span class="sxs-lookup"><span data-stu-id="4da84-109">Choose the entity that includes your target activity or activities.</span></span>

> [!NOTE]
> <span data-ttu-id="4da84-110">Unha entidade debe ter polo menos un atributo de tipo **Data** para incluír nunha liña de tempo de cliente e non pode engadir entidades sen campos **Data**.</span><span class="sxs-lookup"><span data-stu-id="4da84-110">An entity must have at least one attribute of type **Date** to be included in a customer timeline and you can't add entities without **Date** fields.</span></span> <span data-ttu-id="4da84-111">O control **Engadir actividade** está desactivado se non se atopa tal entidade.</span><span class="sxs-lookup"><span data-stu-id="4da84-111">The **Add activity** control is disabled if no such entity is found.</span></span>

1. <span data-ttu-id="4da84-112">Na información do público, vaia a **Datos** > **Actividades**.</span><span class="sxs-lookup"><span data-stu-id="4da84-112">In audience insights, go to **Data** > **Activities**.</span></span>

1. <span data-ttu-id="4da84-113">Seleccione **Engadir actividade** para iniciar a experiencia guiada para o proceso de configuración da actividade.</span><span class="sxs-lookup"><span data-stu-id="4da84-113">Select **Add activity** to start the guided experience for the activity setup process.</span></span>

1. <span data-ttu-id="4da84-114">No paso **Datos de actividade**, configure os valores para os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="4da84-114">In the **Activity data** step, set the values for the following fields:</span></span>

   - <span data-ttu-id="4da84-115">**Nome da actividade**: Seleccione un nome para a súa actividade.</span><span class="sxs-lookup"><span data-stu-id="4da84-115">**Activity name**: Select a name for your activity.</span></span>
   - <span data-ttu-id="4da84-116">**Entidade**: seleccione unha entidade que inclúa datos transaccionais ou de actividade.</span><span class="sxs-lookup"><span data-stu-id="4da84-116">**Entity**: Select an entity that includes transactional or activity data.</span></span>
   - <span data-ttu-id="4da84-117">**Clave principal**: seleccione o campo que identifica un rexistro de cliente de forma única.</span><span class="sxs-lookup"><span data-stu-id="4da84-117">**Primary key**: Select the field that uniquely identifies a record.</span></span> <span data-ttu-id="4da84-118">Non debe conter ningún valor duplicado, valores baleiros ou valores non atopados.</span><span class="sxs-lookup"><span data-stu-id="4da84-118">It shouldn't contain any duplicate values, empty values, or missing values.</span></span>

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Configure os datos da actividade co nome, a entidade e a clave primaria.":::

1. <span data-ttu-id="4da84-120">Seleccione **Seguinte** para ir ao seguinte paso.</span><span class="sxs-lookup"><span data-stu-id="4da84-120">Select **Next** to go to the next step.</span></span>

1. <span data-ttu-id="4da84-121">No paso **Relación**, configure os detalles para conectar os datos da súa actividade ao cliente correspondente.</span><span class="sxs-lookup"><span data-stu-id="4da84-121">In the **Relationship** step, configure the details to connect your activity data to its corresponding customer.</span></span> <span data-ttu-id="4da84-122">Este paso visualiza a conexión entre entidades.</span><span class="sxs-lookup"><span data-stu-id="4da84-122">This step visualizes the connection between entities.</span></span>  

   - <span data-ttu-id="4da84-123">**Primeiro**: Campo estranxeiro da súa entidade de actividade que se usará para establecer unha relación con outra entidade.</span><span class="sxs-lookup"><span data-stu-id="4da84-123">**First**: Foreign field in your activity entity that will be used to establish a relationship with another entity.</span></span>
   - <span data-ttu-id="4da84-124">**Segundo**: Entidade cliente fonte correspondente coa que estará relacionada a súa entidade de actividade.</span><span class="sxs-lookup"><span data-stu-id="4da84-124">**Second**: Corresponding source customer entity with which your activity entity will be in relationship.</span></span> <span data-ttu-id="4da84-125">Só pode relacionar con entidades de cliente de orixe que se usan no proceso de unificación de datos.</span><span class="sxs-lookup"><span data-stu-id="4da84-125">You can only relate to source customer entities that are used in the data unification process.</span></span>
   - <span data-ttu-id="4da84-126">**Terceiro**: Se xa existe unha relación entre esta entidade de actividade e a entidade de cliente fonte seleccionada, o nome da relación estará en modo de só lectura.</span><span class="sxs-lookup"><span data-stu-id="4da84-126">**Third**: If a relationship between this activity entity and the selected source customer entity already exists, the relationship name will be in read-only mode.</span></span> <span data-ttu-id="4da84-127">Se non existe esa relación, crearase unha nova relación co nome que proporcione nesta caixa.</span><span class="sxs-lookup"><span data-stu-id="4da84-127">If there no such relationship exists, a new relationship will be created with the name you provide in this box.</span></span>

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="Defina a relación da entidade.":::

1. <span data-ttu-id="4da84-129">Seleccione **Seguinte** para ir ao seguinte paso.</span><span class="sxs-lookup"><span data-stu-id="4da84-129">Select **Next** to go to the next step.</span></span> 

1. <span data-ttu-id="4da84-130">No paso **Unificación da actividade**, elixa o evento da actividade e a hora de inicio da súa actividade.</span><span class="sxs-lookup"><span data-stu-id="4da84-130">In the **Activity unification** step, choose the activity event and the start time of your activity.</span></span> 
   - <span data-ttu-id="4da84-131">**Campos obrigatorios**</span><span class="sxs-lookup"><span data-stu-id="4da84-131">**Required fields**</span></span>
      1. <span data-ttu-id="4da84-132">**Actividade do evento**: Campo que é o evento desta actividade</span><span class="sxs-lookup"><span data-stu-id="4da84-132">**Event activity**: Field that is the event for this activity</span></span>
      2. <span data-ttu-id="4da84-133">**Marca de tempo**: Campo que representa a hora de inicio da súa actividade.</span><span class="sxs-lookup"><span data-stu-id="4da84-133">**Timestamp**: Field that represents the start time of your activity.</span></span>

   - <span data-ttu-id="4da84-134">**Campos opcionais**</span><span class="sxs-lookup"><span data-stu-id="4da84-134">**Optional fields**</span></span>
      1. <span data-ttu-id="4da84-135">**Detalle adicional**: Campo con información relevante para esta actividade.</span><span class="sxs-lookup"><span data-stu-id="4da84-135">**Additional detail**: Field with relevant information for this activity.</span></span>
      2. <span data-ttu-id="4da84-136">**Icona**: Icona que mellor representa este tipo de actividade.</span><span class="sxs-lookup"><span data-stu-id="4da84-136">**Icon**: Icon that best represents this activity type.</span></span>
      3. <span data-ttu-id="4da84-137">**Enderezo web**: Campo que contén un URL con información sobre esta actividade.</span><span class="sxs-lookup"><span data-stu-id="4da84-137">**Web address**: Field containing a URL with information about this activity.</span></span> <span data-ttu-id="4da84-138">Por exemplo, o sistema transaccional que fornece esta actividade.</span><span class="sxs-lookup"><span data-stu-id="4da84-138">For example, the transactional system that sources this activity.</span></span> <span data-ttu-id="4da84-139">Este URL pode ser calquera campo desde orixe de datos ou pode construírse como un campo novo usando unha transformación Power Query.</span><span class="sxs-lookup"><span data-stu-id="4da84-139">This URL can be any field from the data source, or it can be constructed as a new field using a Power Query transformation.</span></span> <span data-ttu-id="4da84-140">Os datos do URL gardaranse na entidade *Actividade unificada*, que se pode consumir de forma descendente usando as [API](apis.md).</span><span class="sxs-lookup"><span data-stu-id="4da84-140">The URL data will be stored in the *Unified Activity* entity, which can be consumed downstream using [APIs](apis.md).</span></span>
   
   :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="Especifique os datos de actividade do cliente nunha entidade de actividade unificada.":::

1. <span data-ttu-id="4da84-142">Seleccione **Seguinte** para ir ao seguinte paso.</span><span class="sxs-lookup"><span data-stu-id="4da84-142">Select **Next** to move to the next step.</span></span> <span data-ttu-id="4da84-143">Pode seleccionar **Rematar e revisar** para gardar a actividade agora co tipo de actividade configurado en **Outro**.</span><span class="sxs-lookup"><span data-stu-id="4da84-143">You can select **Finish and review** to save the activity now with the activity type set to **Other**.</span></span> 

1. <span data-ttu-id="4da84-144">No paso **Tipo de actividade**, elixa o tipo de actividade e opcionalmente seleccione se quere asignar semanticamente algúns dos tipos de actividade para usalos noutras áreas de Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="4da84-144">In the **Activity Type** step, choose the activity type and optionally select if you want to semantically map some of the activity types for use in other areas of Customer Insights.</span></span> <span data-ttu-id="4da84-145">Actualmente, os tipos de actividade *Subscrición* & *SalesOrderLine* pódense asignar semanticamente despois de aceptar asignar os campos.</span><span class="sxs-lookup"><span data-stu-id="4da84-145">Currently, *Subscription* & *SalesOrderLine* activity types can be semantically mapped after agreeing to map the fields.</span></span> <span data-ttu-id="4da84-146">Se un tipo de actividade non é relevante para a nova actividade, pode escoller *Outro* ou *Crear novo* para un tipo de actividade personalizada.</span><span class="sxs-lookup"><span data-stu-id="4da84-146">If an activity type isn't relevant for the new activity, you can choose *Other* or *Create new* for a custom activity type.</span></span>

1. <span data-ttu-id="4da84-147">Seleccione **Seguinte** para ir ao seguinte paso.</span><span class="sxs-lookup"><span data-stu-id="4da84-147">Select **Next** to move to the next step.</span></span> 

1. <span data-ttu-id="4da84-148">No paso **Revisión**, verifique as súas seleccións.</span><span class="sxs-lookup"><span data-stu-id="4da84-148">In the **Review** step, verify your selections.</span></span> <span data-ttu-id="4da84-149">Volva a calquera dos pasos anteriores e actualice a información se é necesario.</span><span class="sxs-lookup"><span data-stu-id="4da84-149">You go back to any of the previous steps and update the information if necessary.</span></span>

   :::image type="content" source="media/Activity_Wizard5.PNG" alt-text="Revise os campos especificados para unha actividade.":::
   
1. <span data-ttu-id="4da84-151">Seleccione **Gardar actividade** para aplicar os seus cambios e seleccione **Feito** para volver a **Datos** > **Actividades**.</span><span class="sxs-lookup"><span data-stu-id="4da84-151">Select **Save activity** to apply your changes and select **Done** to go back to **Data** > **Activities**.</span></span> <span data-ttu-id="4da84-152">Aquí verá que actividades están configuradas para mostrarse na liña do tempo.</span><span class="sxs-lookup"><span data-stu-id="4da84-152">Here you see which activities are set to show in the timeline.</span></span> 

1. <span data-ttu-id="4da84-153">Na páxina **Actividades**, seleccione **Executar** para procesar a actividade.</span><span class="sxs-lookup"><span data-stu-id="4da84-153">On the **Activities** page, select **Run** to process the activity.</span></span> 

> [!TIP]
> <span data-ttu-id="4da84-154">Existen [seis tipos de estado](system.md#status-types) para as tarefas ou os procesos.</span><span class="sxs-lookup"><span data-stu-id="4da84-154">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="4da84-155">Ademais, a maioría dos procesos [dependen doutros procesos descendentes](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="4da84-155">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="4da84-156">Pode seleccionar o estado dun proceso para ver detalles sobre o progreso de todo o traballo.</span><span class="sxs-lookup"><span data-stu-id="4da84-156">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="4da84-157">Despois de seleccionar **Ver detalles** para unha das tarefas do traballo, atopará información adicional: o tempo de procesamento, a última data de procesamento e todos os erros e avisos asociados á tarefa.</span><span class="sxs-lookup"><span data-stu-id="4da84-157">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>


## <a name="manage-existing-activities"></a><span data-ttu-id="4da84-158">Xestionar actividades existentes</span><span class="sxs-lookup"><span data-stu-id="4da84-158">Manage existing activities</span></span>

<span data-ttu-id="4da84-159">En **Datos** > **Actividades**, pode ver todas as actividades gardadas e xestionalas.</span><span class="sxs-lookup"><span data-stu-id="4da84-159">On **Data** > **Activities**, you can view all your saved activities, and manage them.</span></span> <span data-ttu-id="4da84-160">Cada actividade está representada por unha fila que tamén inclúe detalles sobre a fonte, a entidade e o tipo de actividade.</span><span class="sxs-lookup"><span data-stu-id="4da84-160">Each activity is represented by a row that also includes details about the source, the entity, and the activity type.</span></span>

<span data-ttu-id="4da84-161">As seguintes accións están dispoñibles cando selecciona unha actividade.</span><span class="sxs-lookup"><span data-stu-id="4da84-161">The following actions are available when you select an activity.</span></span> 

- <span data-ttu-id="4da84-162">**Editar**: Abre a configuración da actividade no paso de revisión.</span><span class="sxs-lookup"><span data-stu-id="4da84-162">**Edit**: Opens the activity setup on the review step.</span></span> <span data-ttu-id="4da84-163">Pode cambiar calquera ou toda a configuración actual desde este paso.</span><span class="sxs-lookup"><span data-stu-id="4da84-163">You can change any or all of the current configuration from this step.</span></span> <span data-ttu-id="4da84-164">Despois de cambiar a configuración, seleccione **Gardar actividade** e logo seleccione **Executar** para procesar os cambios.</span><span class="sxs-lookup"><span data-stu-id="4da84-164">After changing the configuration, select **Save activity** and then select **Run** to process the changes.</span></span>

- <span data-ttu-id="4da84-165">**Cambiar o nome**: Abre un diálogo onde introducir un nome diferente para a actividade seleccionada.</span><span class="sxs-lookup"><span data-stu-id="4da84-165">**Rename**: Opens a dialog where to enter a different name for the selected activity.</span></span> <span data-ttu-id="4da84-166">Seleccione **Gardar** para aplicar as modificacións.</span><span class="sxs-lookup"><span data-stu-id="4da84-166">Select **Save** to apply your changes.</span></span>

- <span data-ttu-id="4da84-167">**Eliminar**: Abre un diálogo para confirmar a eliminación da actividade seleccionada.</span><span class="sxs-lookup"><span data-stu-id="4da84-167">**Delete**: Opens a dialog to confirm the deletion of the selected activity.</span></span> <span data-ttu-id="4da84-168">Tamén pode eliminar máis dunha actividade á vez seleccionando as actividades e logo seleccionando a icona de eliminación.</span><span class="sxs-lookup"><span data-stu-id="4da84-168">You can also delete more than one activity at once by selecting the activities and then selecting the delete icon.</span></span> <span data-ttu-id="4da84-169">Para confirmar a eliminación, seleccione **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="4da84-169">Select **Delete** to confirm the deletion.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
