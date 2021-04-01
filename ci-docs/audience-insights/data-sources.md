---
title: Usar fontes de datos para inxerir datos
description: Aprenda a importar datos de varias orixes.
ms.date: 11/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 780dc61a82d6ed9856a37dc8f164fa946d982bbe
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595945"
---
# <a name="data-sources-overview"></a><span data-ttu-id="38bfb-103">Visión xeral de orixes de datos</span><span class="sxs-lookup"><span data-stu-id="38bfb-103">Data sources overview</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="38bfb-104">A capacidade de información do público de Dynamics 365 Customer Insights conéctase a datos dun amplo conxunto de fontes.</span><span class="sxs-lookup"><span data-stu-id="38bfb-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="38bfb-105">Conectarse a unha orixe de datos a miúdo chámase proceso de *inxestión de datos*.</span><span class="sxs-lookup"><span data-stu-id="38bfb-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="38bfb-106">Despois de inxerir os datos, pode [unificar](data-unification.md) e tomar medidas ao respecto.</span><span class="sxs-lookup"><span data-stu-id="38bfb-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="38bfb-107">Engadir unha orixe de datos</span><span class="sxs-lookup"><span data-stu-id="38bfb-107">Add a data source</span></span>

<span data-ttu-id="38bfb-108">Consulte os artigos detallados sobre como engadir unha orixe de datos, dependendo da opción que escolla.</span><span class="sxs-lookup"><span data-stu-id="38bfb-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="38bfb-109">Podes engadir unha orixe de datos de tres xeitos principais:</span><span class="sxs-lookup"><span data-stu-id="38bfb-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="38bfb-110">A través de decenas de conectores Power Query</span><span class="sxs-lookup"><span data-stu-id="38bfb-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="38bfb-111">Desde un cartafol de Common Data Model</span><span class="sxs-lookup"><span data-stu-id="38bfb-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="38bfb-112">Desde o seu propio lago de Common Data Service</span><span class="sxs-lookup"><span data-stu-id="38bfb-112">From your own Common Data Service lake</span></span>](connect-common-data-service-lake.md)

> [!NOTE]
> <span data-ttu-id="38bfb-113">Aínda non pode engadir datos das orixes de datos locais.</span><span class="sxs-lookup"><span data-stu-id="38bfb-113">You can't add data from on-premises data sources yet.</span></span>

## <a name="review-ingested-data"></a><span data-ttu-id="38bfb-114">Revisa os datos inxeridos</span><span class="sxs-lookup"><span data-stu-id="38bfb-114">Review ingested data</span></span>

<span data-ttu-id="38bfb-115">Verá o nome de cada orixe de datos inxerida, o seu estado e a última vez que se actualizaron os datos para esa orixe.</span><span class="sxs-lookup"><span data-stu-id="38bfb-115">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="38bfb-116">Pode ordenar a lista de fontes de datos por cada columna.</span><span class="sxs-lookup"><span data-stu-id="38bfb-116">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="38bfb-117">![Orixe de datos engadida](media/configure-data-datasource-added.png "Orixe de datos engadida")</span><span class="sxs-lookup"><span data-stu-id="38bfb-117">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="38bfb-118">Estado</span><span class="sxs-lookup"><span data-stu-id="38bfb-118">Status</span></span>  |<span data-ttu-id="38bfb-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="38bfb-119">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="38bfb-120">Correcto</span><span class="sxs-lookup"><span data-stu-id="38bfb-120">Successful</span></span>   |<span data-ttu-id="38bfb-121">A orixe de datos inxeriuse con éxito se se menciona unha hora na columna **Actualizado**.</span><span class="sxs-lookup"><span data-stu-id="38bfb-121">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="38bfb-122">Sen iniciar</span><span class="sxs-lookup"><span data-stu-id="38bfb-122">Not started</span></span>   |<span data-ttu-id="38bfb-123">O orixe de datos aínda non ten datos inxeridos ou aínda está en modo borrador.</span><span class="sxs-lookup"><span data-stu-id="38bfb-123">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="38bfb-124">Actualizando</span><span class="sxs-lookup"><span data-stu-id="38bfb-124">Refreshing</span></span>    |<span data-ttu-id="38bfb-125">Inxestión de datos en curso.</span><span class="sxs-lookup"><span data-stu-id="38bfb-125">Data ingestion is in progress.</span></span> <span data-ttu-id="38bfb-126">Pode cancelar esta operación seleccionando **Deixar de actualizar** na columna **Accións**.</span><span class="sxs-lookup"><span data-stu-id="38bfb-126">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="38bfb-127">Deter a actualización dunha orixe de datos provocará que se restableza o seu estado da última actualización.</span><span class="sxs-lookup"><span data-stu-id="38bfb-127">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="38bfb-128">Ero</span><span class="sxs-lookup"><span data-stu-id="38bfb-128">Failed</span></span>     |<span data-ttu-id="38bfb-129">A inxestión de datos tivo erros.</span><span class="sxs-lookup"><span data-stu-id="38bfb-129">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="38bfb-130">Seleccione o valor na columna **Estado** de calquera orixe de datos para revisar máis detalles.</span><span class="sxs-lookup"><span data-stu-id="38bfb-130">Select the value in the **Status** column of any data source to review more details.</span></span> <span data-ttu-id="38bfb-131">No panel **Detalles do progreso**, expanda as **Fontes de datos**.</span><span class="sxs-lookup"><span data-stu-id="38bfb-131">In the **Progress details** pane, expand **Data sources**.</span></span> <span data-ttu-id="38bfb-132">Seleccione **Ver detalles** para ver máis información sobre o estado de actualización, incluídos os detalles de erros e as actualizacións de procesos posteriores.</span><span class="sxs-lookup"><span data-stu-id="38bfb-132">Select **See details** for more information about the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="38bfb-133">A carga de datos pode levar un tempo.</span><span class="sxs-lookup"><span data-stu-id="38bfb-133">Loading data can take some time.</span></span> <span data-ttu-id="38bfb-134">Despois dunha actualización con éxito, os datos inxeridos poden revisarse desde a páxina **Entidades**.</span><span class="sxs-lookup"><span data-stu-id="38bfb-134">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="38bfb-135">Para obter máis información, consulte [Entidades](entities.md).</span><span class="sxs-lookup"><span data-stu-id="38bfb-135">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="38bfb-136">Actualizar unha orixe de datos</span><span class="sxs-lookup"><span data-stu-id="38bfb-136">Refresh a data source</span></span>

<span data-ttu-id="38bfb-137">As fontes de datos pódense actualizar de xeito automático ou actualizarse manualmente a demanda.</span><span class="sxs-lookup"><span data-stu-id="38bfb-137">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="38bfb-138">Vaia a **Administrar** > **Sistema** > [**Programar**](system.md#schedule-tab) para configurar actualizacións programadas de todas as fontes de datos inxeridas.</span><span class="sxs-lookup"><span data-stu-id="38bfb-138">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="38bfb-139">Para actualizar unha orixe de datos baixo demanda, siga estes pasos:</span><span class="sxs-lookup"><span data-stu-id="38bfb-139">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="38bfb-140">Na información do público, vaia a **Datos** > **Orixes de datos**</span><span class="sxs-lookup"><span data-stu-id="38bfb-140">In audience insights, go to **Data** > **Data sources**</span></span>

2. <span data-ttu-id="38bfb-141">Seleccione os puntos suspensivos verticais xunto á orixe de datos que desexa actualizar e seleccione **Actualizar** da lista despregable.</span><span class="sxs-lookup"><span data-stu-id="38bfb-141">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the drop-down list.</span></span>

3. <span data-ttu-id="38bfb-142">A orixe de datos agora está activada para unha actualización manual.</span><span class="sxs-lookup"><span data-stu-id="38bfb-142">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="38bfb-143">Se actualiza unha orixe de datos, actualizaranse tanto o esquema de entidades como os datos de todas as entidades especificadas na orixe de datos.</span><span class="sxs-lookup"><span data-stu-id="38bfb-143">Refreshing a data source will update both the entity schema as well as data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="38bfb-144">Seleccione **Deixar de actualizar** se quere cancelar unha actualización existente e a orixe de datos volverá ao seu último estado de actualización.</span><span class="sxs-lookup"><span data-stu-id="38bfb-144">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="38bfb-145">Eliminar unha orixe de datos</span><span class="sxs-lookup"><span data-stu-id="38bfb-145">Delete a data source</span></span>

1. <span data-ttu-id="38bfb-146">Na información do público, vaia a **Datos** > **Orixes de datos**.</span><span class="sxs-lookup"><span data-stu-id="38bfb-146">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="38bfb-147">Seleccione os tres puntos verticais xunto á orixe de datos que desexa eliminar e seleccione **Eliminar** no menú despregable.</span><span class="sxs-lookup"><span data-stu-id="38bfb-147">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the drop-down menu.</span></span>

3. <span data-ttu-id="38bfb-148">Confirme a eliminación.</span><span class="sxs-lookup"><span data-stu-id="38bfb-148">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]