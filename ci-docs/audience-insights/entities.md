---
title: Entidades e conxuntos de datos
description: Vexa os datos na páxina de entidades.
ms.date: 04/16/2020
ms.reviewer: mukeshpo
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: e71c69a6207147d8cd65363d51a5fa6bbf896151
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269374"
---
# <a name="entities-in-audience-insights"></a><span data-ttu-id="b8475-103">Entidades na información sobre o público</span><span class="sxs-lookup"><span data-stu-id="b8475-103">Entities in audience insights</span></span>

<span data-ttu-id="b8475-104">Despois de [configurar as súas orixes de datos](data-sources.md), vaia á páxina **Entidades** para avaliar a calidade dos datos inxeridos.</span><span class="sxs-lookup"><span data-stu-id="b8475-104">After [configuring your data sources](data-sources.md), go to the **Entities** page to evaluate the quality of the ingested data.</span></span> <span data-ttu-id="b8475-105">As entidades considéranse conxuntos de datos.</span><span class="sxs-lookup"><span data-stu-id="b8475-105">Entities are considered datasets.</span></span> <span data-ttu-id="b8475-106">Múltiples capacidades de Dynamics 365 Customer Insights constrúense arredor destas entidades.</span><span class="sxs-lookup"><span data-stu-id="b8475-106">Multiple capabilities of Dynamics 365 Customer Insights are built around these entities.</span></span> <span data-ttu-id="b8475-107">Revisalas de preto pode axudarlle a validar o resultado desas capacidades.</span><span class="sxs-lookup"><span data-stu-id="b8475-107">Reviewing them closely can help you validate the output of those capabilities.</span></span>

<span data-ttu-id="b8475-108">A páxina **Entidades** enumera entidades e inclúe varias columnas:</span><span class="sxs-lookup"><span data-stu-id="b8475-108">The **Entities** page lists entities and includes several columns:</span></span>

- <span data-ttu-id="b8475-109">**Nome**: o nome da súa entidade de datos.</span><span class="sxs-lookup"><span data-stu-id="b8475-109">**Name**: The name of your data entity.</span></span> <span data-ttu-id="b8475-110">Se ve un símbolo de aviso xunto ao nome dunha entidade, significa que os datos da entidade non se cargaron correctamente.</span><span class="sxs-lookup"><span data-stu-id="b8475-110">If you see a warning symbol next to an entity name, it means that the data for that entity didn't load successfully.</span></span>
- <span data-ttu-id="b8475-111">**Orixe**: tipo de orixes de datos que inxeriron a entidade</span><span class="sxs-lookup"><span data-stu-id="b8475-111">**Source**: The type of data source that ingested the entity</span></span>
- <span data-ttu-id="b8475-112">**Creado por**: nome da persoa que creou a entidade</span><span class="sxs-lookup"><span data-stu-id="b8475-112">**Created by**: Name of the person who created the entity</span></span>
- <span data-ttu-id="b8475-113">**Data e hora de creación**: data e hora de creación da entidade</span><span class="sxs-lookup"><span data-stu-id="b8475-113">**Created**: Date and time of the entity creation</span></span>
- <span data-ttu-id="b8475-114">**Actualizado por**: nome da persoa que actualizou a entidade</span><span class="sxs-lookup"><span data-stu-id="b8475-114">**Updated by**: Name of the person who updated the entity</span></span>
- <span data-ttu-id="b8475-115">**Última actualización**: data e hora da última actualización da entidade</span><span class="sxs-lookup"><span data-stu-id="b8475-115">**Last updated**: Date and time of the last update of the entity</span></span>
- <span data-ttu-id="b8475-116">**Última actualización**: data e hora da última actualización de datos</span><span class="sxs-lookup"><span data-stu-id="b8475-116">**Last refresh**: Date and time of the last data refresh</span></span>

## <a name="exploring-a-specific-entitys-data"></a><span data-ttu-id="b8475-117">Exploración de datos dunha entidade específica</span><span class="sxs-lookup"><span data-stu-id="b8475-117">Exploring a specific entity's data</span></span>

<span data-ttu-id="b8475-118">Seleccione unha entidade para explorar os diferentes campos e rexistros incluídos nela.</span><span class="sxs-lookup"><span data-stu-id="b8475-118">Select an entity to explore the different fields and records included within that entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="b8475-119">![Seleccionar unha entidade](media/data-manager-entities-data.png "Seleccionar unha entidade")</span><span class="sxs-lookup"><span data-stu-id="b8475-119">![Select an entity](media/data-manager-entities-data.png "Select an entity")</span></span>

- <span data-ttu-id="b8475-120">O separador **Datos** está seleccionado de xeito predeterminado e amosa unha táboa que mostra os detalles sobre os rexistros individuais da entidade.</span><span class="sxs-lookup"><span data-stu-id="b8475-120">The **Data** tab is selected by default and shows a table listing details about individual records of the entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="b8475-121">![Táboa de campos](media/data-manager-entities-fields.PNG "Táboa de campos")</span><span class="sxs-lookup"><span data-stu-id="b8475-121">![Fields table](media/data-manager-entities-fields.PNG "Fields table")</span></span>

- <span data-ttu-id="b8475-122">O separador **Campos** mostra unha táboa para revisar os detalles da entidade seleccionada, como nomes de campo, tipos de datos e tipos.</span><span class="sxs-lookup"><span data-stu-id="b8475-122">The **Fields** tab shows a table to review details for the selected entity, such as field names, data types, and types.</span></span> <span data-ttu-id="b8475-123">A columna **Tipo** mostra os tipos asociados ao Common Data Model, identificados automaticamente polo sistema ou [mapeados manualmente](map-entities.md) polos usuarios.</span><span class="sxs-lookup"><span data-stu-id="b8475-123">The **Type** column shows Common Data Model associated types, which are either auto-identified by the system or [manually mapped](map-entities.md) by users.</span></span> <span data-ttu-id="b8475-124">Trátase de tipos semánticos que poden diferir dos tipos de datos dos atributos, por exemplo, o campo *Correo electrónico* a continuación ten o tipo de datos *Texto* pero o seu tipo de Common Data Model (semántico) pode ser *Correo electrónico* ou *Enderezo de correo electrónico*.</span><span class="sxs-lookup"><span data-stu-id="b8475-124">These are semantic types that can differ from the attributes' data types—for example, the field *Email* below has a data type *Text* but its (semantic) Common Data Model type might be *Email* or *EmailAddress*.</span></span>

> [!NOTE]
> <span data-ttu-id="b8475-125">As dúas táboas inclúen só unha mostra dos datos da súa entidade.</span><span class="sxs-lookup"><span data-stu-id="b8475-125">Both tables show only a sample of your entity's data.</span></span> <span data-ttu-id="b8475-126">Para ver o conxunto de datos completo, vaia á páxina **Orixes de datos**, seleccione unha entidade, seleccione **Editar** e, a continuación, visualice os datos desta entidade co editor Power Query como se explica en [Orixes de datos](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="b8475-126">To view the full data set, go to the **Data sources** page, select an entity, select **Edit**, and then view this entity's data with the Power Query editor as explained in [Data sources](data-sources.md).</span></span>

<span data-ttu-id="b8475-127">Para saber máis sobre os datos inxeridos na entidade, a columna **Resumo** ofrécelle algunhas características importantes dos datos, como os datos nulos, valores que faltan, valores únicos, contas e distribucións, segundo corresponda aos seus datos.</span><span class="sxs-lookup"><span data-stu-id="b8475-127">To learn more about the data ingested in the entity, the **Summary** column provides you with some important characteristics of the data, such as nulls, missing values, unique values, counts, and distributions, as applicable to your data.</span></span>

<span data-ttu-id="b8475-128">Seleccione a icona de gráfico para ver o resumo dos datos.</span><span class="sxs-lookup"><span data-stu-id="b8475-128">Select the chart icon to see the summary of the data.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="b8475-129">![Símbolo de resumo](media/data-manager-entities-summary.png "Táboa de resumo de datos")</span><span class="sxs-lookup"><span data-stu-id="b8475-129">![Summary symbol](media/data-manager-entities-summary.png "Data summary table")</span></span>

### <a name="next-step"></a><span data-ttu-id="b8475-130">Seguinte paso</span><span class="sxs-lookup"><span data-stu-id="b8475-130">Next step</span></span>

<span data-ttu-id="b8475-131">Consulte o tema [Unificar](data-unification.md) para obter información acerca de como *asignar*, *atopar coincidencia* e *combinar* os datos inxeridos.</span><span class="sxs-lookup"><span data-stu-id="b8475-131">See the [Unify](data-unification.md) topic to learn how to *map*, *match*, and *merge* the ingested data.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]