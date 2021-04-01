---
title: Actualización incremental para fontes de datos baseadas en Power Query
description: Actualice datos novos e actualizados para grandes orixes de datos baseadas en Power Query.
ms.date: 09/28/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.openlocfilehash: 03f76bcfc7336d8430146e8a26ffa649c6a17db0
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596819"
---
# <a name="incremental-refresh-for-data-sources-based-on-power-query"></a><span data-ttu-id="06bb4-103">Actualización incremental para orixes de datos baseadas en Power Query</span><span class="sxs-lookup"><span data-stu-id="06bb4-103">Incremental refresh for data sources based on Power Query</span></span>

<span data-ttu-id="06bb4-104">A actualización incremental para as orixes de datos ofrece as seguintes vantaxes:</span><span class="sxs-lookup"><span data-stu-id="06bb4-104">Incremental refresh for data sources provides the following advantages:</span></span>

- <span data-ttu-id="06bb4-105">**Actualizacións máis rápidas** - Só se actualizan os datos que cambiaron.</span><span class="sxs-lookup"><span data-stu-id="06bb4-105">**Faster refreshes** - Only data that has changed gets refreshed.</span></span> <span data-ttu-id="06bb4-106">Por exemplo, pode actualizar só os últimos cinco días dun conxunto de datos histórico.</span><span class="sxs-lookup"><span data-stu-id="06bb4-106">For example, you might refresh only the past five days of a historical dataset.</span></span>
- <span data-ttu-id="06bb4-107">**Fiabilidade aumentada** - Con actualizacións máis frecuentes, non necesita manter conexións a sistemas de orixes volátiles durante tanto tempo, reducindo o risco de problemas de conexión.</span><span class="sxs-lookup"><span data-stu-id="06bb4-107">**Increased reliability** - With smaller refreshes, you don't need to maintain connections to volatile source systems for as long, reducing the risk of connection issues.</span></span>
- <span data-ttu-id="06bb4-108">**Consumo de recursos reducido** - Actualizar só un subconxunto dos seus datos totais implica un uso máis eficiente dos recursos informáticos e diminúe a pegada ambiental.</span><span class="sxs-lookup"><span data-stu-id="06bb4-108">**Reduced resource consumption** - Refreshing only a subset of your total data leads to more efficient use of computing resources and decreases the environmental footprint.</span></span>

## <a name="configure-incremental-refresh"></a><span data-ttu-id="06bb4-109">Configurar actualización incremental</span><span class="sxs-lookup"><span data-stu-id="06bb4-109">Configure incremental refresh</span></span>

<span data-ttu-id="06bb4-110">As estadísticas do público permiten actualizar incrementalmente as fontes de datos importadas a través de Power Query que admiten a inxestión incremental.</span><span class="sxs-lookup"><span data-stu-id="06bb4-110">Audience insights allows incremental refresh for data sources imported through Power Query that support incremental ingestion.</span></span> <span data-ttu-id="06bb4-111">Por exemplo, as bases de datos de Azure SQL con campos de data e hora, que indican cando se actualizaron por última vez os rexistros de datos.</span><span class="sxs-lookup"><span data-stu-id="06bb4-111">For example, Azure SQL databases with date and time fields, which indicate when data records were last updated.</span></span>

1. <span data-ttu-id="06bb4-112">[Cree unha nova orixe de datos baseada en Power Query](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="06bb4-112">[Create a new data source based on Power Query](connect-power-query.md).</span></span>

1. <span data-ttu-id="06bb4-113">Indique un nome da orixe de datos.</span><span class="sxs-lookup"><span data-stu-id="06bb4-113">Provide a name for the data source.</span></span>

1. <span data-ttu-id="06bb4-114">Seleccione unha orixe de datos que admita a actualización incremental, como a base de datos de Azure SQL.</span><span class="sxs-lookup"><span data-stu-id="06bb4-114">Select a data source that supports incremental refresh, such as Azure SQL database.</span></span>

1. <span data-ttu-id="06bb4-115">Seleccione as entidades ou táboas para inxerir.</span><span class="sxs-lookup"><span data-stu-id="06bb4-115">Select the entities or tables to ingest.</span></span>

1. <span data-ttu-id="06bb4-116">Complete os pasos de transformación e seleccione **Seguinte**.</span><span class="sxs-lookup"><span data-stu-id="06bb4-116">Complete the transformation steps and select **Next**.</span></span>

1. <span data-ttu-id="06bb4-117">Na caixa de diálogo **Configurar actualización incremental**, seleccione **Configurar** para abrir a **Configuración de actualización incremental**.</span><span class="sxs-lookup"><span data-stu-id="06bb4-117">In the **Set up incremental refresh** dialog box, select **Set up** to open the **Incremental refresh settings**.</span></span> <span data-ttu-id="06bb4-118">Se selecciona **Saltar**, a orixe de datos actualizará todo o conxunto de datos.</span><span class="sxs-lookup"><span data-stu-id="06bb4-118">If you select **Skip**, the data source will refresh the entire data set.</span></span>
   > [!TIP]
   > <span data-ttu-id="06bb4-119">Tamén pode aplicar a actualización incremental máis tarde editando un orixe de datos existente.</span><span class="sxs-lookup"><span data-stu-id="06bb4-119">You can also apply incremental refresh later by editing an existing data source.</span></span>

1. <span data-ttu-id="06bb4-120">Na **Configuración de actualización incremental**, configurará a actualización incremental para todas as entidades que seleccionou ao crear a orixe de datos.</span><span class="sxs-lookup"><span data-stu-id="06bb4-120">On **Incremental refresh settings**, you'll configure the incremental refresh for all entities that you selected when creating the data source.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="06bb4-121">![Configurar as entidades dunha orixe de datos para actualizar incrementalmente](media/incremental-refresh-settings.png "Configurar as entidades dunha orixe de datos para actualizar incrementalmente")</span><span class="sxs-lookup"><span data-stu-id="06bb4-121">![Configure entities in a data source for incremental refresh](media/incremental-refresh-settings.png "Configure entities in a data source for incremental refresh")</span></span>

1. <span data-ttu-id="06bb4-122">Seleccione unha entidade e proporcione os seguintes detalles:</span><span class="sxs-lookup"><span data-stu-id="06bb4-122">Select an entity, and provide the following details:</span></span>

   - <span data-ttu-id="06bb4-123">**Definir a clave principal**: seleccione unha clave principal para a entidade ou táboa.</span><span class="sxs-lookup"><span data-stu-id="06bb4-123">**Define the primary key**: Select a primary key for the entity or table.</span></span>
   - <span data-ttu-id="06bb4-124">**Definir o campo "última actualización"**: este campo só mostrará atributos de data ou hora.</span><span class="sxs-lookup"><span data-stu-id="06bb4-124">**Define the "last updated" field**: This field will only display attributes of type date or time.</span></span> <span data-ttu-id="06bb4-125">Seleccione un atributo que indique cando se actualizaron os rexistros por última vez.</span><span class="sxs-lookup"><span data-stu-id="06bb4-125">Select an attribute that indicates when the records were last updated.</span></span> <span data-ttu-id="06bb4-126">Utilizarase para identificar os rexistros que se atopan dentro do intervalo temporal de actualización incremental.</span><span class="sxs-lookup"><span data-stu-id="06bb4-126">It will be used to identify the records that fall within the incremental refresh time frame.</span></span>
   - <span data-ttu-id="06bb4-127">**Comprobar se hai actualizacións cada**: especifique o tempo que quere que dure o período de actualización incremental.</span><span class="sxs-lookup"><span data-stu-id="06bb4-127">**Check for updates every**: Specify how long you want the incremental refresh time frame to be.</span></span>

1. <span data-ttu-id="06bb4-128">Seleccione **Gardar** para completar a creación da orixe de datos.</span><span class="sxs-lookup"><span data-stu-id="06bb4-128">Select **Save** to complete the creation of the data source.</span></span> <span data-ttu-id="06bb4-129">A actualización de datos inicial será unha actualización completa.</span><span class="sxs-lookup"><span data-stu-id="06bb4-129">The initial data refresh will be a full refresh.</span></span> <span data-ttu-id="06bb4-130">Despois, a actualización de datos incremental producirase como se configurou no paso anterior.</span><span class="sxs-lookup"><span data-stu-id="06bb4-130">Afterwards, the incremental data refresh happens as configured in the previous step.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]