---
title: Destinos de exportación
description: Exportar datos e xestionar os destinos de exportación.
ms.date: 07/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 9032d99357db86e66588eda544211a5f8eb2f23b
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643861"
---
# <a name="export-destinations-preview"></a><span data-ttu-id="fee77-103">Destinos de exportación (previsualización)</span><span class="sxs-lookup"><span data-stu-id="fee77-103">Export destinations (preview)</span></span>

<span data-ttu-id="fee77-104">A páxina **Exportar destinos** móstralle todas as situacións que configurou ás que exportar datos.</span><span class="sxs-lookup"><span data-stu-id="fee77-104">The **Export destinations** page shows you all locations you've set up to export data to.</span></span> <span data-ttu-id="fee77-105">Tamén pode engadir novos destinos para a exportación.</span><span class="sxs-lookup"><span data-stu-id="fee77-105">You can also add new destinations for export.</span></span> <span data-ttu-id="fee77-106">Ademais, mostra as opcións de exportación dispoñibles actualmente.</span><span class="sxs-lookup"><span data-stu-id="fee77-106">Additionally, it shows export currently available options.</span></span> <span data-ttu-id="fee77-107">Obteña unha visión xeral rápida e descrición e descubra o que pode facer con cada opción de extensibilidade.</span><span class="sxs-lookup"><span data-stu-id="fee77-107">Get a quick overview, description, and find out what you can do with each extensibility option.</span></span> <span data-ttu-id="fee77-108">Exporte perfís, medidas e segmentos unificados a aplicacións compatibles relevantes para a súa empresa.</span><span class="sxs-lookup"><span data-stu-id="fee77-108">Export unified profiles, measures, and segments to supported apps relevant for your business.</span></span>

<span data-ttu-id="fee77-109">Vaia a **Administrador** > **Exportar destinos** para atopar as seguintes opcións de extensibilidade:</span><span class="sxs-lookup"><span data-stu-id="fee77-109">Go to **Admin** > **Export destinations** to find the following extensibility options:</span></span>

- [<span data-ttu-id="fee77-110">Complemento do cartón de Dynamics 365 Customer</span><span class="sxs-lookup"><span data-stu-id="fee77-110">Dynamics 365 Customer Card Add-in</span></span>](customer-card-add-in.md)
- [<span data-ttu-id="fee77-111">Conector do xestor de anuncios de Facebook</span><span class="sxs-lookup"><span data-stu-id="fee77-111">Facebook Ads Manager connector</span></span>](export-facebook.md)
- [<span data-ttu-id="fee77-112">Conector de Power Automate</span><span class="sxs-lookup"><span data-stu-id="fee77-112">Power Automate connector</span></span>](export-power-automate.md)
- [<span data-ttu-id="fee77-113">Conector de Power Apps</span><span class="sxs-lookup"><span data-stu-id="fee77-113">Power Apps connector</span></span>](export-power-apps.md)
- [<span data-ttu-id="fee77-114">Conector de Power BI</span><span class="sxs-lookup"><span data-stu-id="fee77-114">Power BI connector</span></span>](export-power-bi.md)
- [<span data-ttu-id="fee77-115">DotDigital</span><span class="sxs-lookup"><span data-stu-id="fee77-115">DotDigital</span></span>](export-dotdigital.md)
- [<span data-ttu-id="fee77-116">Dynamics 365 Sales</span><span class="sxs-lookup"><span data-stu-id="fee77-116">Dynamics 365 Sales</span></span>](export-dynamics365-sales.md)
- [<span data-ttu-id="fee77-117">Dynamics 365 Marketing</span><span class="sxs-lookup"><span data-stu-id="fee77-117">Dynamics 365 Marketing</span></span>](export-dynamics365-marketing.md)
- [<span data-ttu-id="fee77-118">Almacenamento de BLOB de Azure</span><span class="sxs-lookup"><span data-stu-id="fee77-118">Azure Blob Storage</span></span>](export-azure-blob-storage.md)
- [<span data-ttu-id="fee77-119">Conector de LiveRamp&reg;</span><span class="sxs-lookup"><span data-stu-id="fee77-119">LiveRamp&reg; connector</span></span>](export-liveramp.md)
- [<span data-ttu-id="fee77-120">Bot para Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fee77-120">Bot for Microsoft Teams</span></span>](export-teams-bot.md)
- [<span data-ttu-id="fee77-121">Mailchimp</span><span class="sxs-lookup"><span data-stu-id="fee77-121">Mailchimp</span></span>](export-mailchimp.md)
- [<span data-ttu-id="fee77-122">API de Customer Insights</span><span class="sxs-lookup"><span data-stu-id="fee77-122">Customer Insights API</span></span>](apis.md)

## <a name="add-a-new-export-destination"></a><span data-ttu-id="fee77-123">Engadir un novo destino de exportación</span><span class="sxs-lookup"><span data-stu-id="fee77-123">Add a new export destination</span></span>

<span data-ttu-id="fee77-124">Para engadir destinos de exportación, ten [permisos de administrador](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="fee77-124">To add export destinations, you have [administrator permissions](permissions.md).</span></span> <span data-ttu-id="fee77-125">Se exporta a servizos Microsoft, supoñemos que ambos servizos están na mesma organización.</span><span class="sxs-lookup"><span data-stu-id="fee77-125">If you export to Microsoft services, we assume both services are in the same organization.</span></span>

1. <span data-ttu-id="fee77-126">Vaia a **Administrador** > **Exportar destinos**.</span><span class="sxs-lookup"><span data-stu-id="fee77-126">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="fee77-127">Cambie ao separador **Os meus destinos de exportación**.</span><span class="sxs-lookup"><span data-stu-id="fee77-127">Switch to the **My export destinations** tab.</span></span>

1. <span data-ttu-id="fee77-128">Seleccione **Engadir destino** para crear un novo destino de exportación.</span><span class="sxs-lookup"><span data-stu-id="fee77-128">Select **Add destination** to create a new export destination.</span></span>

1. <span data-ttu-id="fee77-129">No panel **Engadir destino**, seleccione o **Tipo** de destino de exportación na lista despregable.</span><span class="sxs-lookup"><span data-stu-id="fee77-129">In the **Add destination** pane, select the **Type** of export destination in the drop-down.</span></span>

1. <span data-ttu-id="fee77-130">Proporcione os detalles necesarios e seleccione **Seguinte** para crear o destino de exportación.</span><span class="sxs-lookup"><span data-stu-id="fee77-130">Provide the required details and select **Next** to create the export destination.</span></span>

<span data-ttu-id="fee77-131">Tamén pode seleccionar **Configurar** nun mosaico do separador **Descubrir**.</span><span class="sxs-lookup"><span data-stu-id="fee77-131">You can also select **Set up** on a tile on the **Discover** tab.</span></span>

## <a name="view-export-destinations"></a><span data-ttu-id="fee77-132">Ver destinos de exportación</span><span class="sxs-lookup"><span data-stu-id="fee77-132">View Export destinations</span></span>

<span data-ttu-id="fee77-133">Despois de crear destinos de exportación, atoparalos nunha táboa do separador **Os meus destinos de exportación**. Esta táboa ten tres columnas:</span><span class="sxs-lookup"><span data-stu-id="fee77-133">After creating export destinations, you'll find them in a table on the **My export destinations** tab. This table has three columns:</span></span>

- <span data-ttu-id="fee77-134">**Nome para mostrar**: o nome que introduciu ao crear o destino.</span><span class="sxs-lookup"><span data-stu-id="fee77-134">**Display name**: The name you entered when creating the destination.</span></span>
- <span data-ttu-id="fee77-135">**Tipo**: o tipo de destino de exportación que establece ao crear o destino.</span><span class="sxs-lookup"><span data-stu-id="fee77-135">**Type**: The export destination type you set when creating the destination.</span></span>
- <span data-ttu-id="fee77-136">**Data de creación**: a data na que se creou o destino.</span><span class="sxs-lookup"><span data-stu-id="fee77-136">**Created**: The date you created the destination.</span></span>

## <a name="edit-an-export-destination"></a><span data-ttu-id="fee77-137">Editar un destino de exportación</span><span class="sxs-lookup"><span data-stu-id="fee77-137">Edit an export destination</span></span>

1. <span data-ttu-id="fee77-138">Seleccione os tres puntos verticais para o destino de exportación que desexa editar.</span><span class="sxs-lookup"><span data-stu-id="fee77-138">Select the vertical ellipsis for the Export destination you want to edit.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="fee77-139">![Tres puntos verticais](media/export-destinations-page-ellipsis.png "Tres puntos verticais")</span><span class="sxs-lookup"><span data-stu-id="fee77-139">![Vertical ellipsis](media/export-destinations-page-ellipsis.png "Vertical ellipsis")</span></span>

1. <span data-ttu-id="fee77-140">Seleccione **Editar** no menú despregable.</span><span class="sxs-lookup"><span data-stu-id="fee77-140">Select **Edit** from the dropdown menu.</span></span>

1. <span data-ttu-id="fee77-141">Cambie os valores que requiren actualización e seleccione **Gardar**.</span><span class="sxs-lookup"><span data-stu-id="fee77-141">Change the values that require update and select **Save**.</span></span>

## <a name="export-data-on-demand"></a><span data-ttu-id="fee77-142">Exportar datos baixo demanda</span><span class="sxs-lookup"><span data-stu-id="fee77-142">Export data on demand</span></span>

<span data-ttu-id="fee77-143">Despois de configurar un conector para un destino de exportación, as exportacións executaranse con todas as [actualizacións programadas](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="fee77-143">After configuring a connector for an export destination, exports will run with every [scheduled refresh](system.md#schedule-tab).</span></span>

<span data-ttu-id="fee77-144">Para exportar datos sen agardar unha actualización programada, diríxase ao separador **Os meus destinos de exportación** en **Administrador** > **Destinos de exportación**.</span><span class="sxs-lookup"><span data-stu-id="fee77-144">To export data without waiting for a scheduled refresh, go the **My export destinations** tab on **Admin** > **Export destinations**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="fee77-145">![Tres puntos verticais](media/export-destinations-page-ellipsis.png "Tres puntos verticais")</span><span class="sxs-lookup"><span data-stu-id="fee77-145">![Vertical ellipsis](media/export-destinations-page-ellipsis.png "Vertical ellipsis")</span></span>

- <span data-ttu-id="fee77-146">Seleccione **Exportar** enriba da lista para executar a exportación a todos os destinos de exportación simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="fee77-146">Select **Export** above the list to run the export to all export destinations simultaneously.</span></span>
- <span data-ttu-id="fee77-147">Seleccione os tres puntos (...) despois dun elemento da lista e logo escolla a opción **Exportar** para executar a exportación para un único destino de exportación.</span><span class="sxs-lookup"><span data-stu-id="fee77-147">Select the ellipsis (...) after a list item and then choose the **Export** option to run the export for a single export destination.</span></span>

## <a name="remove-an-export-destination"></a><span data-ttu-id="fee77-148">Eliminar un destino de exportación</span><span class="sxs-lookup"><span data-stu-id="fee77-148">Remove an Export destination</span></span>

<span data-ttu-id="fee77-149">Para eliminar un destino de exportación, comece pola páxina **Destinos de exportación** principal.</span><span class="sxs-lookup"><span data-stu-id="fee77-149">To remove an Export destination, start from the main **Export destinations** page.</span></span>

1. <span data-ttu-id="fee77-150">Seleccione os tres puntos verticais para o destino de exportación que desexa eliminar.</span><span class="sxs-lookup"><span data-stu-id="fee77-150">Select the vertical ellipsis for the Export destination you want to remove.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="fee77-151">![Tres puntos verticais](media/export-destinations-page-ellipsis.png "Tres puntos verticais")</span><span class="sxs-lookup"><span data-stu-id="fee77-151">![Vertical ellipsis](media/export-destinations-page-ellipsis.png "Vertical ellipsis")</span></span>

2. <span data-ttu-id="fee77-152">Seleccione **Eliminar** do menú despregable.</span><span class="sxs-lookup"><span data-stu-id="fee77-152">Select **Remove** from the dropdown menu.</span></span>

3. <span data-ttu-id="fee77-153">Confirme a eliminación seleccionando **Eliminar** na pantalla de confirmación.</span><span class="sxs-lookup"><span data-stu-id="fee77-153">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>
