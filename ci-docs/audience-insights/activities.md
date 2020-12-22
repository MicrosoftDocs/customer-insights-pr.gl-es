---
title: Actividades do cliente
description: Defina as actividades dos clientes e visualíceas na cronoloxía do cliente.
ms.date: 10/13/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: adkuppa
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 1c95cba333266a73959de0a3afe1c8677130a3ec
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667227"
---
# <a name="customer-activities"></a><span data-ttu-id="66974-103">Actividades do cliente</span><span class="sxs-lookup"><span data-stu-id="66974-103">Customer activities</span></span>

<span data-ttu-id="66974-104">Combine as actividades dos clientes desde [varias fontes de datos](data-sources.md) dentrode Dynamics 365 Customer Insights para crear unha liña do tempo do cliente que liste as actividades por orde cronolóxica.</span><span class="sxs-lookup"><span data-stu-id="66974-104">Combine customer activities from [various data sources](data-sources.md) in Dynamics 365 Customer Insights to create a customer timeline that lists the activities in chronological order.</span></span> <span data-ttu-id="66974-105">Pode incluír a liña de tempo nas aplicacións de interacción con clientes en Dynamics 365 a través do [complemento de tarxeta de cliente](customer-card-add-in.md) ou nun panel de Power BI.</span><span class="sxs-lookup"><span data-stu-id="66974-105">You can include the timeline in customer engagement apps in Dynamics 365 via the [Customer Card add-in](customer-card-add-in.md), or in a Power BI dashboard.</span></span>

## <a name="define-an-activity"></a><span data-ttu-id="66974-106">Definir unha actividade</span><span class="sxs-lookup"><span data-stu-id="66974-106">Define an activity</span></span>

<span data-ttu-id="66974-107">As súas fontes de datos inclúen entidades con datos de transaccións e actividades de varias fontes de datos.</span><span class="sxs-lookup"><span data-stu-id="66974-107">Your data sources include entities with transactional and activity data from multiple data sources.</span></span> <span data-ttu-id="66974-108">Identifique estas entidades e seleccione as actividades que desexa ver na liña de tempo do cliente.</span><span class="sxs-lookup"><span data-stu-id="66974-108">Identify these entities and select the activities you want to view on the customer's timeline.</span></span> <span data-ttu-id="66974-109">Escolla a entidade que inclúe a súa actividade ou actividades de destino.</span><span class="sxs-lookup"><span data-stu-id="66974-109">Choose the entity that includes your target activity or activities.</span></span>

1. <span data-ttu-id="66974-110">Na información do público, vaia a **Datos** > **Actividades**.</span><span class="sxs-lookup"><span data-stu-id="66974-110">In audience insights, go to **Data** > **Activities**.</span></span>

1. <span data-ttu-id="66974-111">Seleccione **Engadir actividade**.</span><span class="sxs-lookup"><span data-stu-id="66974-111">Select **Add activity**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="66974-112">Unha entidade debe ter polo menos un atributo de tipo **Data** para incluír nunha liña de tempo de cliente e non pode engadir entidades sen campos **Data**.</span><span class="sxs-lookup"><span data-stu-id="66974-112">An entity must have at least one attribute of type **Date** to be included in a customer timeline and you can't add entities without **Date** fields.</span></span> <span data-ttu-id="66974-113">O control **Engadir actividade** está desactivado se non se atopa tal entidade.</span><span class="sxs-lookup"><span data-stu-id="66974-113">The **Add activity** control is disabled if no such entity is found.</span></span>

1. <span data-ttu-id="66974-114">No panel **Engadir actividade**, estableza os valores para os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="66974-114">In the **Add activity** pane, set the values for the following fields:</span></span>

   - <span data-ttu-id="66974-115">**Entidade**: seleccione unha entidade que inclúa datos transaccionais ou de actividade.</span><span class="sxs-lookup"><span data-stu-id="66974-115">**Entity**: Select an entity that includes transactional or activity data.</span></span>
   - <span data-ttu-id="66974-116">**Clave principal**: seleccione o campo que identifica un rexistro de cliente de forma única.</span><span class="sxs-lookup"><span data-stu-id="66974-116">**Primary key**: Select the field that uniquely identifies a record.</span></span> <span data-ttu-id="66974-117">Non debe conter ningún valor duplicado, valores baleiros ou valores non atopados.</span><span class="sxs-lookup"><span data-stu-id="66974-117">It shouldn't contain any duplicate values, empty values, or missing values.</span></span>
   - <span data-ttu-id="66974-118">**Marca de tempo**: seleccione o campo que representa a hora de inicio da súa actividade.</span><span class="sxs-lookup"><span data-stu-id="66974-118">**Timestamp**: Select the field that represents the start time of your activity.</span></span>
   - <span data-ttu-id="66974-119">**Evento**: seleccione o campo que é o evento da actividade.</span><span class="sxs-lookup"><span data-stu-id="66974-119">**Event**: Select the field that is the event for the activity.</span></span>
   - <span data-ttu-id="66974-120">**Enderezo web**: seleccione o campo que representa un URL que fornece información adicional sobre esta actividade.</span><span class="sxs-lookup"><span data-stu-id="66974-120">**Web address**: Select the field that represents a URL providing additional information about this activity.</span></span> <span data-ttu-id="66974-121">Por exemplo, o sistema transaccional que fornece esta actividade.</span><span class="sxs-lookup"><span data-stu-id="66974-121">For example, the transactional system that sources this activity.</span></span> <span data-ttu-id="66974-122">Este URL pode ser calquera campo desde orixe de datos ou pode construírse como un campo novo usando unha transformación Power Query.</span><span class="sxs-lookup"><span data-stu-id="66974-122">This URL can be any field from the data source, or it can be constructed as a new field using a Power Query transformation.</span></span> <span data-ttu-id="66974-123">Estes datos de URL almacenaranse na entidade de Actividade unificada, que se pode consumir de forma descendente mediante API.</span><span class="sxs-lookup"><span data-stu-id="66974-123">This URL data will be stored in the Unified Activity entity, which can be consumed downstream using APIs.</span></span>
   - <span data-ttu-id="66974-124">**Detalles**: tamén pode seleccionar o campo que se engade para obter máis detalles.</span><span class="sxs-lookup"><span data-stu-id="66974-124">**Details**: Optionally, select the field that is added for additional details.</span></span>
   - <span data-ttu-id="66974-125">**Icona**: tamén pode seleccionar a icona que representa esta actividade.</span><span class="sxs-lookup"><span data-stu-id="66974-125">**Icon**: Optionally, select the icon that represents this activity.</span></span>
   - <span data-ttu-id="66974-126">**Tipo de actividade**: defina a referencia do tipo de actividade no Common Data Model que describa mellor a definición semántica da actividade.</span><span class="sxs-lookup"><span data-stu-id="66974-126">**Activity Type**: Define the activity type reference to Common Data Model that best describes the semantic definition of the activity.</span></span>

1. <span data-ttu-id="66974-127">Na sección **Establecer relación**, configure os detalles para conectar os seus datos de actividade co cliente correspondente.</span><span class="sxs-lookup"><span data-stu-id="66974-127">In the **Set up relationship** section, configure the details to connect your activity data to its corresponding customer.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="66974-128">![Definir a relación da entidade](media/activities-entities-define.png "Definir a relación da entidade")</span><span class="sxs-lookup"><span data-stu-id="66974-128">![Define the entity relationship](media/activities-entities-define.png "Define the entity relationship")</span></span>

    - <span data-ttu-id="66974-129">**Campo da entidade da actividade**: seleccione o campo da súa entidade de actividade que se empregará para establecer unha relación con outra entidade.</span><span class="sxs-lookup"><span data-stu-id="66974-129">**Activity entity field**: Select the field in your activity entity that will be used to establish a relationship with another entity.</span></span>
    - <span data-ttu-id="66974-130">**Entidade de cliente**: seleccione a entidade de cliente de orixe correspondente coa que estará en relación a súa entidade de actividade.</span><span class="sxs-lookup"><span data-stu-id="66974-130">**Customer entity**: Select the corresponding source customer entity with which your activity entity will be in relationship.</span></span> <span data-ttu-id="66974-131">Pode relacionarse só con aquelas entidades de cliente de orixe que se usan no proceso de unificación de datos.</span><span class="sxs-lookup"><span data-stu-id="66974-131">You can relate to only those source customer entities that are used in the data unification process.</span></span>
    - <span data-ttu-id="66974-132">**Campo da entidade do cliente**: este campo amosa a clave principal da entidade de cliente de orixe como seleccionada no proceso de mapa.</span><span class="sxs-lookup"><span data-stu-id="66974-132">**Customer entity field**: This field shows the primary key of the source customer entity as selected in the map process.</span></span> <span data-ttu-id="66974-133">Este campo clave principal na entidade cliente de orixe úsase para establecer unha relación coa entidade da actividade.</span><span class="sxs-lookup"><span data-stu-id="66974-133">This primary key field in the source customer entity is used to establish a relationship with the activity entity.</span></span>
    - <span data-ttu-id="66974-134">**Nome**: se xa existe unha relación entre esta entidade de actividade e a entidade cliente de orixe seleccionada, o nome da relación estará en modo de só lectura.</span><span class="sxs-lookup"><span data-stu-id="66974-134">**Name**: If a relationship between this activity entity and the selected source customer entity already exists, the relationship name will be in read-only mode.</span></span> <span data-ttu-id="66974-135">Se non existe esa relación, crearase unha nova relación co nome indicado aquí.</span><span class="sxs-lookup"><span data-stu-id="66974-135">If there no such relationship exists, a new relationship will be created with the name provided here.</span></span>

1. <span data-ttu-id="66974-136">Seleccione **Gardar** para aplicar as modificacións.</span><span class="sxs-lookup"><span data-stu-id="66974-136">Select **Save** to apply your changes.</span></span>

1. <span data-ttu-id="66974-137">Na páxina **Actividades**, seleccione **Executar**.</span><span class="sxs-lookup"><span data-stu-id="66974-137">On the **Activities** page, select **Run**.</span></span>

> [!TIP]
> <span data-ttu-id="66974-138">Existen [seis tipos de estado](system.md#status-types) para as tarefas ou os procesos.</span><span class="sxs-lookup"><span data-stu-id="66974-138">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="66974-139">Ademais, a maioría dos procesos [dependen doutros procesos descendentes](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="66974-139">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="66974-140">Pode seleccionar o estado dun proceso para ver detalles sobre o progreso de todo o traballo.</span><span class="sxs-lookup"><span data-stu-id="66974-140">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="66974-141">Despois de seleccionar **Ver detalles** para unha das tarefas do traballo, atopará información adicional: o tempo de procesamento, a última data de procesamento e todos os erros e avisos asociados á tarefa.</span><span class="sxs-lookup"><span data-stu-id="66974-141">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="edit-an-activity"></a><span data-ttu-id="66974-142">Editar unha actividade</span><span class="sxs-lookup"><span data-stu-id="66974-142">Edit an activity</span></span>

1. <span data-ttu-id="66974-143">Na información do público, vaia a **Datos** > **Actividades**.</span><span class="sxs-lookup"><span data-stu-id="66974-143">In audience insights, go to **Data** > **Activities**.</span></span>

2. <span data-ttu-id="66974-144">Seleccione a entidade da actividade que desexe editar e seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="66974-144">Select the activity entity you want to edit and select **Edit**.</span></span> <span data-ttu-id="66974-145">Tamén pode pasar o rato sobre a fila de entidade e seleccionar a icona **Editar**.</span><span class="sxs-lookup"><span data-stu-id="66974-145">Or, you can hover over the entity row and select the **Edit** icon.</span></span>

3. <span data-ttu-id="66974-146">Prema na icona **Editar**.</span><span class="sxs-lookup"><span data-stu-id="66974-146">Click on the **Edit** icon.</span></span>

4. <span data-ttu-id="66974-147">No panel **Editar actividade**, actualice os valores e seleccione **Gardar**.</span><span class="sxs-lookup"><span data-stu-id="66974-147">In the **Edit activity** pane, update the values and select **Save**.</span></span>

5. <span data-ttu-id="66974-148">Na páxina **Actividades**, seleccione **Executar**.</span><span class="sxs-lookup"><span data-stu-id="66974-148">On the **Activities** page, select **Run**.</span></span>

## <a name="delete-an-activity"></a><span data-ttu-id="66974-149">Eliminar unha actividade</span><span class="sxs-lookup"><span data-stu-id="66974-149">Delete an activity</span></span>

1. <span data-ttu-id="66974-150">Na información do público, vaia a **Datos** > **Actividades**.</span><span class="sxs-lookup"><span data-stu-id="66974-150">In audience insights, go to **Data** > **Activities**.</span></span>

2. <span data-ttu-id="66974-151">Seleccione a entidade da actividade que desexe eliminar e seleccione **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="66974-151">Select the activity entity you want to remove and select **Delete**.</span></span> <span data-ttu-id="66974-152">Tamén pode pasar o rato sobre a fila de entidade e seleccionar a icona **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="66974-152">Or, you can hover over the entity row and select the **Delete** icon.</span></span> <span data-ttu-id="66974-153">Tamén pode seleccionar varias entidades de actividade para eliminar dunha vez.</span><span class="sxs-lookup"><span data-stu-id="66974-153">Additionally, you can select multiple activity entities to be deleted at once.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="66974-154">![Editar ou eliminar a relación da entidade](media/activities-entities-edit-delete.png "Editar ou eliminar a relación da entidade")</span><span class="sxs-lookup"><span data-stu-id="66974-154">![Edit or delete the entity relationship](media/activities-entities-edit-delete.png "Edit or delete the entity relationship")</span></span>

3. <span data-ttu-id="66974-155">Seleccione a icona **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="66974-155">Select on the **Delete** icon.</span></span>

4. <span data-ttu-id="66974-156">Confirme a eliminación.</span><span class="sxs-lookup"><span data-stu-id="66974-156">Confirm your deletion.</span></span>
