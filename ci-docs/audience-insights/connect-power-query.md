---
title: Inxerir datos a través dun conector de Power Query
description: Conectores para orixes de datos baseados en Power Query.
ms.date: 09/29/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 8a170cc5b64b4b383501021232c83948e838a0e2
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405717"
---
# <a name="connect-to-a-power-query-data-source"></a><span data-ttu-id="be6ec-103">Conéctarse a unha orixe de datos Power Query</span><span class="sxs-lookup"><span data-stu-id="be6ec-103">Connect to a Power Query data source</span></span>

<span data-ttu-id="be6ec-104">Power Query ofrece un amplo conxunto de conectores para inxerir datos.</span><span class="sxs-lookup"><span data-stu-id="be6ec-104">Power Query offers a broad set of connectors to ingest data.</span></span> <span data-ttu-id="be6ec-105">A maioría destes conectores son compatibles con Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="be6ec-105">Most of these connectors are supported by Dynamics 365 Customer Insights.</span></span> <span data-ttu-id="be6ec-106">Engadir orixes de datos baseadas nos conectores Power Query xeralmente segue os pasos descritos na seguinte sección.</span><span class="sxs-lookup"><span data-stu-id="be6ec-106">Adding data sources based on Power Query connectors generally follows the steps outlined in the next section.</span></span> <span data-ttu-id="be6ec-107">Non obstante, dependendo do conector que use, é necesaria unha información diferente.</span><span class="sxs-lookup"><span data-stu-id="be6ec-107">However, depending on the connector you use, different information is required.</span></span> <span data-ttu-id="be6ec-108">Para obter máis información, consulte a documentación sobre conectores individuais na [referencia de conectores Power Query](https://docs.microsoft.com/power-query/connectors/).</span><span class="sxs-lookup"><span data-stu-id="be6ec-108">For more information, see the documentation about individual connectors in the [Power Query connector reference](https://docs.microsoft.com/power-query/connectors/).</span></span>

## <a name="create-a-new-data-source"></a><span data-ttu-id="be6ec-109">Crear unha nova orixe de datos</span><span class="sxs-lookup"><span data-stu-id="be6ec-109">Create a new data source</span></span>

1. <span data-ttu-id="be6ec-110">Na información do público, vaia a **Datos** > **Orixes de datos**.</span><span class="sxs-lookup"><span data-stu-id="be6ec-110">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="be6ec-111">Seleccione **Engadir orixe de datos**.</span><span class="sxs-lookup"><span data-stu-id="be6ec-111">Select **Add data source**.</span></span>

1. <span data-ttu-id="be6ec-112">Escolla o método de **Importar datos** e seleccione **Seguinte**.</span><span class="sxs-lookup"><span data-stu-id="be6ec-112">Choose the **Import data** method and select **Next**.</span></span>

1. <span data-ttu-id="be6ec-113">Escriba un **Nome** para a orixe de datos e seleccione **Seguinte** para crear o orixe de datos.</span><span class="sxs-lookup"><span data-stu-id="be6ec-113">Provide a **Name** for the data source, and select **Next** to create the data source.</span></span>

1. <span data-ttu-id="be6ec-114">Escolla un dos [conectores dispoñibles](#available-power-query-data-sources).</span><span class="sxs-lookup"><span data-stu-id="be6ec-114">Choose one of the [available connectors](#available-power-query-data-sources).</span></span> <span data-ttu-id="be6ec-115">Para este exemplo, seleccionamos o conector **Texto / CSV**.</span><span class="sxs-lookup"><span data-stu-id="be6ec-115">For this example, we select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="be6ec-116">Introduza os detalles requiridos na **Configuración de conexión** para o conector seleccionado e seleccione **Seguinte** para ver unha previsualización dos datos.</span><span class="sxs-lookup"><span data-stu-id="be6ec-116">Enter the required details in the **Connection settings** for the selected connector and select **Next** to see a preview of the data.</span></span>

1. <span data-ttu-id="be6ec-117">Seleccione **Transformar datos**.</span><span class="sxs-lookup"><span data-stu-id="be6ec-117">Select **Transform data**.</span></span> <span data-ttu-id="be6ec-118">Neste paso, engadirá entidades á súa orixe de datos.</span><span class="sxs-lookup"><span data-stu-id="be6ec-118">In this step, you'll add entities to your data source.</span></span> <span data-ttu-id="be6ec-119">As entidades son conxuntos de datos.</span><span class="sxs-lookup"><span data-stu-id="be6ec-119">Entities are datasets.</span></span> <span data-ttu-id="be6ec-120">Se ten unha base de datos que inclúe varios conxuntos de datos, cada conxunto de datos é a súa propia entidade.</span><span class="sxs-lookup"><span data-stu-id="be6ec-120">If you have a database that includes multiple datasets, each dataset is its own entity.</span></span>

1. <span data-ttu-id="be6ec-121">O diálogo **Power Query - Editar consultas** permítelle revisar e refinar os datos.</span><span class="sxs-lookup"><span data-stu-id="be6ec-121">The **Power Query - Edit queries** dialog lets you review and refine the data.</span></span> <span data-ttu-id="be6ec-122">As entidades que os sistemas identificaron na orixe de datos seleccionada aparecen no panel esquerdo.</span><span class="sxs-lookup"><span data-stu-id="be6ec-122">The entities that the systems identified in your selected data source appear in the left pane.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="be6ec-123">![Editar diálogo de consultas](media/data-manager-configure-edit-queries.png "Editar diálogo de consultas")</span><span class="sxs-lookup"><span data-stu-id="be6ec-123">![Edit queries dialog](media/data-manager-configure-edit-queries.png "Edit queries dialog")</span></span>

1. <span data-ttu-id="be6ec-124">Tamén pode transformar os seus datos.</span><span class="sxs-lookup"><span data-stu-id="be6ec-124">You can also transform your data.</span></span> <span data-ttu-id="be6ec-125">Seleccione unha entidade para editar ou transformar.</span><span class="sxs-lookup"><span data-stu-id="be6ec-125">Select an entity to edit or transform.</span></span> <span data-ttu-id="be6ec-126">Use as opcións da ventá de Power Query para aplicar transformacións.</span><span class="sxs-lookup"><span data-stu-id="be6ec-126">Use the options in the Power Query window to apply transformations.</span></span> <span data-ttu-id="be6ec-127">Cada transformación aparece na lista **Pasos aplicados**.</span><span class="sxs-lookup"><span data-stu-id="be6ec-127">Each transformation gets listed under **Applied steps**.</span></span> <span data-ttu-id="be6ec-128">Power Query ofrece numerosas opcións de transformación predefinidas.</span><span class="sxs-lookup"><span data-stu-id="be6ec-128">Power Query provides numerous pre-built transformation options.</span></span> <span data-ttu-id="be6ec-129">Para obter máis información, consulte [Transformacións de Power Query](https://docs.microsoft.com/power-query/power-query-what-is-power-query#transformations).</span><span class="sxs-lookup"><span data-stu-id="be6ec-129">For more information, see [Power Query Transformations](https://docs.microsoft.com/power-query/power-query-what-is-power-query#transformations).</span></span>

1. <span data-ttu-id="be6ec-130">Pode engadir entidades adicionais á súa orixe de datos seleccionando **Obter datos** na caixa de diálogo **Editar consultas**.</span><span class="sxs-lookup"><span data-stu-id="be6ec-130">You can add additional entities to your data source by selecting **Get data** in the **Edit queries** dialog.</span></span>

   <span data-ttu-id="be6ec-131">Estas transformacións son moi recomendables:</span><span class="sxs-lookup"><span data-stu-id="be6ec-131">These transformations are highly recommended:</span></span>

   - <span data-ttu-id="be6ec-132">Se está inxerindo datos dun ficheiro CSV, a primeira fila a miúdo contén cabeceiras.</span><span class="sxs-lookup"><span data-stu-id="be6ec-132">If you're ingesting data from a CSV file, the first row often contains headers.</span></span> <span data-ttu-id="be6ec-133">Vaia a **Transformar táboa** e seleccione **Usar cabeceiras como primeira fila**.</span><span class="sxs-lookup"><span data-stu-id="be6ec-133">Go to **Transform table** and select **Use headers as first row**.</span></span>
   - <span data-ttu-id="be6ec-134">Asegúrese de que o tipo de datos está configurado correctamente.</span><span class="sxs-lookup"><span data-stu-id="be6ec-134">Ensure the data type is set appropriately.</span></span>

1. <span data-ttu-id="be6ec-135">Seleccione **Gardar** na parte inferior da ventá de Power Query para gardar as transformacións.</span><span class="sxs-lookup"><span data-stu-id="be6ec-135">Select **Save** at the bottom of the Power Query window to save the transformations.</span></span> <span data-ttu-id="be6ec-136">Despois de gardar, atopará o seu orixe de datos en **Datos** > **Orixes de datos**.</span><span class="sxs-lookup"><span data-stu-id="be6ec-136">After saving, you'll find your data source on **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="be6ec-137">Na páxina **Orixes de datos**, notarás que o novo orixe de datos está en estado **Actualizando**.</span><span class="sxs-lookup"><span data-stu-id="be6ec-137">On the **Data sources** page, you'll notice the new data source is in **Refreshing** status.</span></span>

## <a name="available-power-query-data-sources"></a><span data-ttu-id="be6ec-138">Orixes de datos de Power Query dispoñibles</span><span class="sxs-lookup"><span data-stu-id="be6ec-138">Available Power Query data sources</span></span>

<span data-ttu-id="be6ec-139">Consulte a [Referencia de conectores Power Query](https://docs.microsoft.com/power-query/connectors/) para obter unha lista actualizada de conectores que pode seleccionar para importar datos a Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="be6ec-139">See the [Power Query connector reference](https://docs.microsoft.com/power-query/connectors/) for an up-to-date list of connectors that you can select to import data to Customer Insights.</span></span> 

<span data-ttu-id="be6ec-140">Os conectores cunha marca de verificación na columna **Customer Insights (fluxos de datos)** están dispoñibles para crear novas orixes de datos baseadas en Power Query.</span><span class="sxs-lookup"><span data-stu-id="be6ec-140">Connectors with a checkmark in the **Customer Insights (Dataflows)** column are available to create new data sources based on Power Query.</span></span> <span data-ttu-id="be6ec-141">Revise a documentación dun conector específico para obter máis información sobre os seus requisitos previos, limitacións e outros detalles.</span><span class="sxs-lookup"><span data-stu-id="be6ec-141">Review the documentation of a specific connector to learn more about its prerequisites, limitations, and other details.</span></span>

## <a name="edit-power-query-data-sources"></a><span data-ttu-id="be6ec-142">Editar orixes de datos de Power Query</span><span class="sxs-lookup"><span data-stu-id="be6ec-142">Edit Power Query data sources</span></span>

> [!NOTE]
> <span data-ttu-id="be6ec-143">É posible que non se poidan facer cambios nas fontes de datos que se están empregando actualmente nun dos procesos da aplicación (*segmentación*, *coincidencia* ou *combinación*, por exemplo).</span><span class="sxs-lookup"><span data-stu-id="be6ec-143">It might not be possible to make changes to data sources that are currently being used in one of the app's processes (*segmentation*, *match*, or *merge*, for example).</span></span> 
>
> <span data-ttu-id="be6ec-144">Usando a páxina **Configuración**, pode rastrexar o progreso de cada un dos procesos activos.</span><span class="sxs-lookup"><span data-stu-id="be6ec-144">Using the **Settings** page, you can track the progress of each of the active processes.</span></span> <span data-ttu-id="be6ec-145">Cando se complete un proceso, pode volver á páxina **Orixes de datos** e facer os seus cambios.</span><span class="sxs-lookup"><span data-stu-id="be6ec-145">When a process completes, you can return to the **Data Sources** page and make your changes.</span></span>

1. <span data-ttu-id="be6ec-146">Na información do público, vaia a **Datos** > **Orixes de datos**.</span><span class="sxs-lookup"><span data-stu-id="be6ec-146">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="be6ec-147">Seleccione os tres puntos verticais xunto á orixe de datos que desexa cambiar e seleccione **Editar** no menú despregable.</span><span class="sxs-lookup"><span data-stu-id="be6ec-147">Select the vertical ellipsis next to the data source you want to change and select **Edit** from the drop-down menu.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="be6ec-148">![Editar opción](media/edit-option-data-sources.png "Editar opción")</span><span class="sxs-lookup"><span data-stu-id="be6ec-148">![Edit option](media/edit-option-data-sources.png "Edit option")</span></span>

3. <span data-ttu-id="be6ec-149">Aplique os seus cambios e transformacións no diálogo **Power Query - Editar consultas** como se describe na sección [Crea unha nova orixe de datos](#create-a-new-data-source).</span><span class="sxs-lookup"><span data-stu-id="be6ec-149">Apply your changes and transformations in the **Power Query - Edit queries** dialog as described in the [Create a new data source](#create-a-new-data-source) section.</span></span>

4. <span data-ttu-id="be6ec-150">Seleccione **Gardar** en Power Query despois de completar as edicións para gardar os cambios.</span><span class="sxs-lookup"><span data-stu-id="be6ec-150">Select **Save** in Power Query after completing your edits to save your changes.</span></span>
