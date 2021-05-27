---
title: Usar fontes de datos para inxerir datos
description: Aprenda a importar datos de varias orixes.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 3c0b4690e18285aa37eef481b3cfac951884ead6
ms.sourcegitcommit: fcc94f55dc2dce84eae188d582801dc47696c9cc
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 05/20/2021
ms.locfileid: "6085528"
---
# <a name="data-sources-overview"></a><span data-ttu-id="64988-103">Visión xeral de orixes de datos</span><span class="sxs-lookup"><span data-stu-id="64988-103">Data sources overview</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="64988-104">A capacidade de información do público de Dynamics 365 Customer Insights conéctase a datos dun amplo conxunto de fontes.</span><span class="sxs-lookup"><span data-stu-id="64988-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="64988-105">Conectarse a unha orixe de datos a miúdo chámase proceso de *inxestión de datos*.</span><span class="sxs-lookup"><span data-stu-id="64988-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="64988-106">Despois de inxerir os datos, pode [unificar](data-unification.md) e tomar medidas ao respecto.</span><span class="sxs-lookup"><span data-stu-id="64988-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="64988-107">Engadir unha orixe de datos</span><span class="sxs-lookup"><span data-stu-id="64988-107">Add a data source</span></span>

<span data-ttu-id="64988-108">Consulte os artigos detallados sobre como engadir unha orixe de datos, dependendo da opción que escolla.</span><span class="sxs-lookup"><span data-stu-id="64988-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="64988-109">Podes engadir unha orixe de datos de tres xeitos principais:</span><span class="sxs-lookup"><span data-stu-id="64988-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="64988-110">A través de decenas de conectores Power Query</span><span class="sxs-lookup"><span data-stu-id="64988-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="64988-111">Desde un cartafol de Common Data Model</span><span class="sxs-lookup"><span data-stu-id="64988-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="64988-112">Desde o seu propio lago de Common Data Service</span><span class="sxs-lookup"><span data-stu-id="64988-112">From your own Common Data Service lake</span></span>](connect-common-data-service-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a><span data-ttu-id="64988-113">Engadir datos de fontes de datos locais</span><span class="sxs-lookup"><span data-stu-id="64988-113">Add data from on-premises data sources</span></span>

<span data-ttu-id="64988-114">Admite datos interesantes de orixes de datos locais da Información do público en función dos fluxos de datos de Power Platform.</span><span class="sxs-lookup"><span data-stu-id="64988-114">Ingesting data from on-premises data sources in Audience Insights is supported based on Power Platform dataflows.</span></span> <span data-ttu-id="64988-115">Os fluxos de datos pódense activar en Customer Insights [proporcionando o URL do contorno de Microsoft Dataverse](manage-environments.md#create-an-environment-in-an-existing-organization) ao configurar o ambiente.</span><span class="sxs-lookup"><span data-stu-id="64988-115">Dataflows can be enabled in Customer Insights by [providing the Microsoft Dataverse environment URL](manage-environments.md#create-an-environment-in-an-existing-organization) when setting up the environment.</span></span>

<span data-ttu-id="64988-116">As fontes de datos que se creen despois de asociar un contorno de Dataverse con Customer Insights usarán [fluxos de datos e Power Platform](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) por defecto.</span><span class="sxs-lookup"><span data-stu-id="64988-116">Data sources that are created after associating a Dataverse environment with Customer Insights will use [Power Platform dataflows](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) by default.</span></span> <span data-ttu-id="64988-117">Os fluxos de datos admiten conectividade local mediante a pasarela de datos.</span><span class="sxs-lookup"><span data-stu-id="64988-117">Dataflows support on-premises connectivity using the data gateway.</span></span> <span data-ttu-id="64988-118">Elimine e volva crear as orixes de datos que existían antes de que se asociase un ambiente de Dataverse para [usar as pasarelas de datos locais](/powerapps/maker/data-platform/using-dataflows-with-on-premises-data.md).</span><span class="sxs-lookup"><span data-stu-id="64988-118">Remove and recreate data sources that existed before a Dataverse environment was associated to [use the on-premises data gateways](/powerapps/maker/data-platform/using-dataflows-with-on-premises-data.md).</span></span>

<span data-ttu-id="64988-119">As pasarelas de datos dun xa existente contorno de Power BI ou Power Apps serán visibles e pode reutilizalas en Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="64988-119">Data gateways from an existing Power BI or Power Apps environment will be visible and you can reuse in Customer Insights.</span></span> <span data-ttu-id="64988-120">A páxina de fontes de datos mostra ligazóns para ir ao ambiente de Power Platform onde pode ver e configurar pasarelas de datos locais.</span><span class="sxs-lookup"><span data-stu-id="64988-120">The data sources page shows links to go the Power Platform environment where you can view and configure on-premises data gateways.</span></span>

## <a name="review-ingested-data"></a><span data-ttu-id="64988-121">Revisa os datos inxeridos</span><span class="sxs-lookup"><span data-stu-id="64988-121">Review ingested data</span></span>

<span data-ttu-id="64988-122">Verá o nome de cada orixe de datos inxerida, o seu estado e a última vez que se actualizaron os datos para esa orixe.</span><span class="sxs-lookup"><span data-stu-id="64988-122">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="64988-123">Pode ordenar a lista de fontes de datos por cada columna.</span><span class="sxs-lookup"><span data-stu-id="64988-123">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="64988-124">![Orixe de datos engadida](media/configure-data-datasource-added.png "Orixe de datos engadida")</span><span class="sxs-lookup"><span data-stu-id="64988-124">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="64988-125">Estado</span><span class="sxs-lookup"><span data-stu-id="64988-125">Status</span></span>  |<span data-ttu-id="64988-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="64988-126">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="64988-127">Correcto</span><span class="sxs-lookup"><span data-stu-id="64988-127">Successful</span></span>   |<span data-ttu-id="64988-128">A orixe de datos inxeriuse con éxito se se menciona unha hora na columna **Actualizado**.</span><span class="sxs-lookup"><span data-stu-id="64988-128">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="64988-129">Sen iniciar</span><span class="sxs-lookup"><span data-stu-id="64988-129">Not started</span></span>   |<span data-ttu-id="64988-130">O orixe de datos aínda non ten datos inxeridos ou aínda está en modo borrador.</span><span class="sxs-lookup"><span data-stu-id="64988-130">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="64988-131">Actualizando</span><span class="sxs-lookup"><span data-stu-id="64988-131">Refreshing</span></span>    |<span data-ttu-id="64988-132">Inxestión de datos en curso.</span><span class="sxs-lookup"><span data-stu-id="64988-132">Data ingestion is in progress.</span></span> <span data-ttu-id="64988-133">Pode cancelar esta operación seleccionando **Deixar de actualizar** na columna **Accións**.</span><span class="sxs-lookup"><span data-stu-id="64988-133">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="64988-134">Deter a actualización dunha orixe de datos provocará que se restableza o seu estado da última actualización.</span><span class="sxs-lookup"><span data-stu-id="64988-134">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="64988-135">Ero</span><span class="sxs-lookup"><span data-stu-id="64988-135">Failed</span></span>     |<span data-ttu-id="64988-136">A inxestión de datos tivo erros.</span><span class="sxs-lookup"><span data-stu-id="64988-136">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="64988-137">Seleccione o valor na columna **Estado** de calquera orixe de datos para revisar máis detalles.</span><span class="sxs-lookup"><span data-stu-id="64988-137">Select the value in the **Status** column of any data source to review more details.</span></span> <span data-ttu-id="64988-138">No panel **Detalles do progreso**, expanda as **Fontes de datos**.</span><span class="sxs-lookup"><span data-stu-id="64988-138">In the **Progress details** pane, expand **Data sources**.</span></span> <span data-ttu-id="64988-139">Seleccione **Ver detalles** para ver máis información sobre o estado de actualización, incluídos os detalles de erros e as actualizacións de procesos posteriores.</span><span class="sxs-lookup"><span data-stu-id="64988-139">Select **See details** for more information about the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="64988-140">A carga de datos pode levar un tempo.</span><span class="sxs-lookup"><span data-stu-id="64988-140">Loading data can take some time.</span></span> <span data-ttu-id="64988-141">Despois dunha actualización con éxito, os datos inxeridos poden revisarse desde a páxina **Entidades**.</span><span class="sxs-lookup"><span data-stu-id="64988-141">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="64988-142">Para obter máis información, consulte [Entidades](entities.md).</span><span class="sxs-lookup"><span data-stu-id="64988-142">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="64988-143">Actualizar unha orixe de datos</span><span class="sxs-lookup"><span data-stu-id="64988-143">Refresh a data source</span></span>

<span data-ttu-id="64988-144">As fontes de datos pódense actualizar de xeito automático ou actualizarse manualmente a demanda.</span><span class="sxs-lookup"><span data-stu-id="64988-144">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="64988-145">Vaia a **Administrar** > **Sistema** > [**Programar**](system.md#schedule-tab) para configurar actualizacións programadas de todas as fontes de datos inxeridas.</span><span class="sxs-lookup"><span data-stu-id="64988-145">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="64988-146">Para actualizar unha orixe de datos baixo demanda, siga estes pasos:</span><span class="sxs-lookup"><span data-stu-id="64988-146">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="64988-147">Na información do público, vaia a **Datos** > **Orixes de datos**</span><span class="sxs-lookup"><span data-stu-id="64988-147">In audience insights, go to **Data** > **Data sources**</span></span>

2. <span data-ttu-id="64988-148">Seleccione os puntos suspensivos verticais xunto á orixe de datos que desexa actualizar e seleccione **Actualizar** da lista despregable.</span><span class="sxs-lookup"><span data-stu-id="64988-148">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the drop-down list.</span></span>

3. <span data-ttu-id="64988-149">A orixe de datos agora está activada para unha actualización manual.</span><span class="sxs-lookup"><span data-stu-id="64988-149">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="64988-150">Actualizar unha orixe de datos actualizá tanto o esquema de entidade como os datos de todas as entidades especificadas na orixe de datos.</span><span class="sxs-lookup"><span data-stu-id="64988-150">Refreshing a data source will update both the entity schema and data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="64988-151">Seleccione **Deixar de actualizar** se quere cancelar unha actualización existente e a orixe de datos volverá ao seu último estado de actualización.</span><span class="sxs-lookup"><span data-stu-id="64988-151">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="64988-152">Eliminar unha orixe de datos</span><span class="sxs-lookup"><span data-stu-id="64988-152">Delete a data source</span></span>

1. <span data-ttu-id="64988-153">Na información do público, vaia a **Datos** > **Orixes de datos**.</span><span class="sxs-lookup"><span data-stu-id="64988-153">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="64988-154">Seleccione os tres puntos verticais xunto á orixe de datos que desexa eliminar e seleccione **Eliminar** no menú despregable.</span><span class="sxs-lookup"><span data-stu-id="64988-154">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the drop-down menu.</span></span>

3. <span data-ttu-id="64988-155">Confirme a eliminación.</span><span class="sxs-lookup"><span data-stu-id="64988-155">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
