---
title: Ver perfís de clientes
description: Obteña unha vista combinada dos seus datos de clientes unificados.
ms.date: 12/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: d6a9e7872a488b6d68afce35b547f93cc4a7c652
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596865"
---
# <a name="customer-profiles"></a><span data-ttu-id="3b56f-103">Perfís de clientes</span><span class="sxs-lookup"><span data-stu-id="3b56f-103">Customer profiles</span></span>

<span data-ttu-id="3b56f-104">A páxina **Clientes** mostra unha vista combinada dos seus clientes, baseada nos datos dos perfís recompilados de [todas as fontes de datos](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="3b56f-104">The **Customers** page shows a combined view of your customers, based on profile data gathered from [all data sources](data-sources.md).</span></span> <span data-ttu-id="3b56f-105">Os perfís de clientes están dispoñibles unha vez [creada a entidade de cliente unificada](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="3b56f-105">Customer profiles are available once you [create the unified Customer entity](data-unification.md).</span></span> <span data-ttu-id="3b56f-106">Asegúrese de completar o proceso de unificación de datos para obter unha visión máis rica dos seus clientes.</span><span class="sxs-lookup"><span data-stu-id="3b56f-106">Make sure you complete the data unification process to get richer views of your customers.</span></span> <span data-ttu-id="3b56f-107">A páxina tamén lle permite buscar clientes.</span><span class="sxs-lookup"><span data-stu-id="3b56f-107">The page also lets you search for customers.</span></span>

<span data-ttu-id="3b56f-108">Os clientes poden ser persoas ou organizacións (vista previa).</span><span class="sxs-lookup"><span data-stu-id="3b56f-108">Customers can be individuals or organizations (preview).</span></span> <span data-ttu-id="3b56f-109">Cada perfil de cliente ou organización está representado por un mosaico.</span><span class="sxs-lookup"><span data-stu-id="3b56f-109">Each customer or organization profile is represented by a tile.</span></span> <span data-ttu-id="3b56f-110">Seleccione un mosaico para ver información adicional sobre ese cliente ou organización específico.</span><span class="sxs-lookup"><span data-stu-id="3b56f-110">Select a tile to see additional information on that specific customer or organization.</span></span> <span data-ttu-id="3b56f-111">Use os controis de paxinación do final da páxina para ver rexistros adicionais.</span><span class="sxs-lookup"><span data-stu-id="3b56f-111">Use the pagination controls at the bottom of the page to see additional records.</span></span>

> [!div class="mx-imgBorder"] 
> <span data-ttu-id="3b56f-112">![Perfís de cliente B2C](media/profiles-customers.png "Perfís de cliente B2C")</span><span class="sxs-lookup"><span data-stu-id="3b56f-112">![B2C customer profiles](media/profiles-customers.png "B2C customer profiles")</span></span>

<span data-ttu-id="3b56f-113">Organizacións (vista previa)</span><span class="sxs-lookup"><span data-stu-id="3b56f-113">Organizations (Preview)</span></span>
> [!div class="mx-imgBorder"] 
> <span data-ttu-id="3b56f-114">![Perfís de cliente B2B](media/profile-customers-b2b.png "Perfís de cliente B2B")</span><span class="sxs-lookup"><span data-stu-id="3b56f-114">![B2B customer profiles](media/profile-customers-b2b.png "B2B customer profiles")</span></span>

> [!NOTE]
> <span data-ttu-id="3b56f-115">Se non ve os mosaicos ao seleccionar **Clientes** na navegación, o seu administrador precisará [definir polo menos un atributo que se poida buscar](search-filter-index.md) no **Índice de busca e filtro**.</span><span class="sxs-lookup"><span data-stu-id="3b56f-115">If you can't see the tiles when you select **Customers** in navigation, your administrator needs to [define at least one searchable attribute](search-filter-index.md) on the **Search & filter index**.</span></span>

## <a name="search-for-customers"></a><span data-ttu-id="3b56f-116">Buscar clientes</span><span class="sxs-lookup"><span data-stu-id="3b56f-116">Search for customers</span></span>

<span data-ttu-id="3b56f-117">Busque clientes introducindo un nome ou algún outro atributo na caixa de busca.</span><span class="sxs-lookup"><span data-stu-id="3b56f-117">Search for customers by entering a name or some other attribute in the search box.</span></span> <span data-ttu-id="3b56f-118">A busca só funciona dentro da entidade de Perfil do cliente creada durante o proceso de unificación de datos.</span><span class="sxs-lookup"><span data-stu-id="3b56f-118">The search only works within the Customer Profile entity created during the data unification process.</span></span>

<span data-ttu-id="3b56f-119">Como administrador, pode configurar os atributos que se poden buscar usando a páxina **Índice de busca e filtro**.</span><span class="sxs-lookup"><span data-stu-id="3b56f-119">As an admin, you can configure the searchable attributes using the **Search & filter index** page.</span></span> <span data-ttu-id="3b56f-120">Para obter máis información, consulte [Xestionar o índice de busca e filtro](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="3b56f-120">For more information, see [Manage search & filter index](search-filter-index.md).</span></span>

## <a name="filter-customers"></a><span data-ttu-id="3b56f-121">Filtrar clientes</span><span class="sxs-lookup"><span data-stu-id="3b56f-121">Filter customers</span></span>

<span data-ttu-id="3b56f-122">Pode filtrar clientes polos campos de entidade de perfil do cliente.</span><span class="sxs-lookup"><span data-stu-id="3b56f-122">You can filter customers by the Customer Profile entity fields.</span></span> <span data-ttu-id="3b56f-123">De xeito semellante á busca, o administrador primeiro deberá definir os campos como filtrables usando a páxina **Índice de busca e filtro**.</span><span class="sxs-lookup"><span data-stu-id="3b56f-123">Similar to search, your admin will first need to define the fields as filterable using the **Search & filter index** page.</span></span>

1. <span data-ttu-id="3b56f-124">Na páxina **Clientes**, seleccione **Filtrar**.</span><span class="sxs-lookup"><span data-stu-id="3b56f-124">Select **Filter** on the **Customers** page.</span></span>

2. <span data-ttu-id="3b56f-125">Marque as caixas situadas xunto aos atributos polos que desexa filtrar os clientes.</span><span class="sxs-lookup"><span data-stu-id="3b56f-125">Check the boxes next to the attributes you want to filter customers by.</span></span>

   > [!div class="mx-imgBorder"] 
   > <span data-ttu-id="3b56f-126">![Perfís de clientes](media/profiles-customers3.png "Perfís de clientes")</span><span class="sxs-lookup"><span data-stu-id="3b56f-126">![Customer profiles](media/profiles-customers3.png "Customer profiles")</span></span>

3. <span data-ttu-id="3b56f-127">Elimine os filtros seleccionando **Limpar filtros** na páxina **Clientes**.</span><span class="sxs-lookup"><span data-stu-id="3b56f-127">Remove your filters by selecting **Clear filters** on the **Customers** page.</span></span>

##  <a name="customer-details-page"></a><span data-ttu-id="3b56f-128">Páxina de detalles do cliente</span><span class="sxs-lookup"><span data-stu-id="3b56f-128">Customer details page</span></span>

<span data-ttu-id="3b56f-129">Seleccione calquera dos mosaicos de clientes para abrir a **Páxina de detalles do cliente**.</span><span class="sxs-lookup"><span data-stu-id="3b56f-129">Select any of the customer tiles to open the **Customer details page**.</span></span> <span data-ttu-id="3b56f-130">Esta vista contén información unificada do cliente seleccionado.</span><span class="sxs-lookup"><span data-stu-id="3b56f-130">This view contains unified information for the selected customer.</span></span>

<span data-ttu-id="3b56f-131">Os detalles do cliente inclúen:</span><span class="sxs-lookup"><span data-stu-id="3b56f-131">Customer details include:</span></span>

-   <span data-ttu-id="3b56f-132">**Ficha do perfil do cliente:** Este mosaico mostra os diferentes valores da entidade de perfil de cliente unificado.</span><span class="sxs-lookup"><span data-stu-id="3b56f-132">**Customer profile tile:** This tile shows the different values from the unified customer profile entity.</span></span> <span data-ttu-id="3b56f-133">Estes detalles poden incluír enderezo de correo electrónico, nome, cidade etc.</span><span class="sxs-lookup"><span data-stu-id="3b56f-133">These details can include email address, name, city, and so on.</span></span> 

-   <span data-ttu-id="3b56f-134">**Intereses potenciais, marcas potenciais:** Mostra se configurou un enriquecemento propio.</span><span class="sxs-lookup"><span data-stu-id="3b56f-134">**Potential interests, potential brands:** Shows if you configured a first-party enrichment.</span></span> <span data-ttu-id="3b56f-135">Representa posibles intereses e afinidades para as marcas que poida ter un cliente cun perfil similar a este.</span><span class="sxs-lookup"><span data-stu-id="3b56f-135">It represents potential interests and affinities for brands a customer with a profile similar to this customer might have.</span></span> <span data-ttu-id="3b56f-136">Para obter máis información, consulte [Enriquecer os perfís de clientes con afinidades de marca e intereses](enrichment-microsoft-graph.md).</span><span class="sxs-lookup"><span data-stu-id="3b56f-136">For more information, see [Enrich customer profiles with brand and interest affinities](enrichment-microsoft-graph.md).</span></span>

-   <span data-ttu-id="3b56f-137">**Medidas:** Mostra se configurou unha ou máis medidas dun tipo específico: medidas de atributo de cliente.</span><span class="sxs-lookup"><span data-stu-id="3b56f-137">**Measures:** Shows if you configured one or more measures of a specific type: customer attribute measures.</span></span> <span data-ttu-id="3b56f-138">Inclúen KPI calculados arredor dos seus clientes a nivel de cliente individual.</span><span class="sxs-lookup"><span data-stu-id="3b56f-138">They include calculated KPIs around your customers on the individual customer level.</span></span> <span data-ttu-id="3b56f-139">Para obter máis información, consulte [Definir e xestionar medidas](measures.md).</span><span class="sxs-lookup"><span data-stu-id="3b56f-139">For more information, see [Define and manage measures](measures.md).</span></span>

-   <span data-ttu-id="3b56f-140">**Cronoloxía da actividade:** Mostra se configurou actividades.</span><span class="sxs-lookup"><span data-stu-id="3b56f-140">**Activity timeline:** Shows if you have configured activities.</span></span> <span data-ttu-id="3b56f-141">A vista de cronoloxía contén actividades ordenadas cronoloxicamente deste cliente, comezando pola actividade máis recente.</span><span class="sxs-lookup"><span data-stu-id="3b56f-141">The timeline view contains chronologically sorted activities of this customer, starting with the most recent activity.</span></span> <span data-ttu-id="3b56f-142">Para obter máis información, consulte [Actividades do cliente](activities.md).</span><span class="sxs-lookup"><span data-stu-id="3b56f-142">For more information, see [Customer activities](activities.md).</span></span>

<span data-ttu-id="3b56f-143">Seleccione **Volver a Clientes** para volver á páxina de busca de clientes.</span><span class="sxs-lookup"><span data-stu-id="3b56f-143">Select **Back to Customers** to return to the customer search page.</span></span>

## <a name="next-steps"></a><span data-ttu-id="3b56f-144">Pasos seguintes</span><span class="sxs-lookup"><span data-stu-id="3b56f-144">Next steps</span></span>

<span data-ttu-id="3b56f-145">[Engada máis orixes de datos](data-sources.md) ou [cree segmentos de clientes](segments.md).</span><span class="sxs-lookup"><span data-stu-id="3b56f-145">[Add more data sources](data-sources.md) or [create customer segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]