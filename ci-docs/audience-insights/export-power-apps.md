---
title: Conector de Power Apps
description: Conecte con Power Apps e Power Automate.
ms.date: 08/21/2020
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b6ec103e29e218b2f27bfc1193300ea793a6b30b
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405695"
---
# <a name="microsoft-power-apps-connector-preview"></a><span data-ttu-id="78bbc-103">Conector de Microsoft Power Apps (vista previa)</span><span class="sxs-lookup"><span data-stu-id="78bbc-103">Microsoft Power Apps connector (preview)</span></span>

<span data-ttu-id="78bbc-104">Consiga perfís de clientes unificados ás súas aplicacións personalizadas con Power Apps.</span><span class="sxs-lookup"><span data-stu-id="78bbc-104">Bring unified customer profiles into your personalized apps with Power Apps.</span></span>

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a><span data-ttu-id="78bbc-105">Conectar Power Apps e Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="78bbc-105">Connect Power Apps and Dynamics 365 Customer Insights</span></span>

<span data-ttu-id="78bbc-106">Customer Insights é unha das moitas [orixes dispoñibles para datos en Power Apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/working-with-data-sources).</span><span class="sxs-lookup"><span data-stu-id="78bbc-106">Customer Insights is one of the many [available sources for data in Power Apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/working-with-data-sources).</span></span>

<span data-ttu-id="78bbc-107">Consulte a documentación de Power Apps para aprender a [engadir unha conexión de datos a unha aplicación](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-data-connection).</span><span class="sxs-lookup"><span data-stu-id="78bbc-107">Refer to the Power Apps documentation to learn how to [add a data connection to an app](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-data-connection).</span></span> <span data-ttu-id="78bbc-108">Recomendamos que revise tamén [como Power Apps usa a delegación para xestionar grandes conxuntos de datos en aplicacións de lenzo](https://docs.microsoft.com/powerapps/maker/canvas-apps/delegation-overview).</span><span class="sxs-lookup"><span data-stu-id="78bbc-108">We recommend you also review [how Power Apps uses delegation to handle large datasets in Canvas apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/delegation-overview).</span></span>

## <a name="available-entities"></a><span data-ttu-id="78bbc-109">Entidades dispoñibles</span><span class="sxs-lookup"><span data-stu-id="78bbc-109">Available entities</span></span>

<span data-ttu-id="78bbc-110">Despois de engadir Customer Insights como conexión de datos, pode escoller as seguintes entidades en Power Apps:</span><span class="sxs-lookup"><span data-stu-id="78bbc-110">After adding Customer Insights as a data connection, you can choose the following entities in Power Apps:</span></span>

- <span data-ttu-id="78bbc-111">Cliente: para usar datos do [perfil de cliente unificado](customer-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="78bbc-111">Customer: to use data from the [unified customer profile](customer-profiles.md).</span></span>
- <span data-ttu-id="78bbc-112">Actividade de clientes unificada: para mostrar a [liña de tempo da actividade](activities.md) na aplicación.</span><span class="sxs-lookup"><span data-stu-id="78bbc-112">Unified Customer Activity: to display the [activity timeline](activities.md) on the app.</span></span>

## <a name="limitations"></a><span data-ttu-id="78bbc-113">Limitacións</span><span class="sxs-lookup"><span data-stu-id="78bbc-113">Limitations</span></span>

### <a name="retrievable-entities"></a><span data-ttu-id="78bbc-114">Entidades recuperables</span><span class="sxs-lookup"><span data-stu-id="78bbc-114">Retrievable entities</span></span>

<span data-ttu-id="78bbc-115">Só pode recuperar as entidades **Cliente**, **UnifiedActivity** e **Segmentos** a través do conector Power Apps.</span><span class="sxs-lookup"><span data-stu-id="78bbc-115">You can only retrieve the **Customer**, **UnifiedActivity**, and **Segments** entities through the Power Apps connector.</span></span> <span data-ttu-id="78bbc-116">Amósanse outras entidades porque o conector subxacente as admite a través de desencadeadores en Power Automate.</span><span class="sxs-lookup"><span data-stu-id="78bbc-116">Other entities are shown because the underlying connector supports them through triggers in Power Automate.</span></span>  

### <a name="delegation"></a><span data-ttu-id="78bbc-117">Delegación</span><span class="sxs-lookup"><span data-stu-id="78bbc-117">Delegation</span></span>

<span data-ttu-id="78bbc-118">A delegación funciona para a entidade de cliente e a entidade UnifiedActivity.</span><span class="sxs-lookup"><span data-stu-id="78bbc-118">Delegation works for the Customer entity and UnifiedActivity entity.</span></span> 

- <span data-ttu-id="78bbc-119">Delegación para a entidade **Cliente**: para usar a delegación para esta entidade, os campos deben indexarse en [Buscar e filtrar o índice](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="78bbc-119">Delegation for **Customer** entity: To use delegation for this entity, the fields need to be indexed in [Search & filter index](search-filter-index.md).</span></span>  

- <span data-ttu-id="78bbc-120">Delegación para **UnifiedActivity**: a delegación para esta entidade só funciona para os campos **ActivityId** e **ID de cliente**.</span><span class="sxs-lookup"><span data-stu-id="78bbc-120">Delegation for **UnifiedActivity**: Delegation for this entity only works for the fields **ActivityId** and **CustomerId**.</span></span>  

- <span data-ttu-id="78bbc-121">Para obter máis información sobre a delegación, consulte [Funcións e operacións delegables de Power Apps](https://docs.microsoft.com/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps).</span><span class="sxs-lookup"><span data-stu-id="78bbc-121">For more information about delegation, see [Power Apps delegable functions and operations](https://docs.microsoft.com/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps).</span></span> 

## <a name="example-gallery-control"></a><span data-ttu-id="78bbc-122">Exemplo de control de galería</span><span class="sxs-lookup"><span data-stu-id="78bbc-122">Example gallery control</span></span>

<span data-ttu-id="78bbc-123">Por exemplo, engada perfís de clientes a un [control da galería](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-gallery).</span><span class="sxs-lookup"><span data-stu-id="78bbc-123">For example, you add customer profiles to a [gallery control](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-gallery).</span></span>

1. <span data-ttu-id="78bbc-124">Engada un control de **Galería** a unha aplicación que estea a crear.</span><span class="sxs-lookup"><span data-stu-id="78bbc-124">Add a **Gallery** control to an app you're building.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="78bbc-125">![Engadir un elemento da galería](media/connector-powerapps9.png "Engadir un elemento da galería")</span><span class="sxs-lookup"><span data-stu-id="78bbc-125">![Add a gallery element](media/connector-powerapps9.png "Add a gallery element")</span></span>

1. <span data-ttu-id="78bbc-126">Seleccione **Cliente** como orixe de datos para os elementos.</span><span class="sxs-lookup"><span data-stu-id="78bbc-126">Select **Customer** as the data source for items.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="78bbc-127">![Seleccionar unha orixe de datos](media/choose-datasource-powerapps.png "Seleccionar unha orixe de datos")</span><span class="sxs-lookup"><span data-stu-id="78bbc-127">![Select a data source](media/choose-datasource-powerapps.png "Select a data source")</span></span>

1. <span data-ttu-id="78bbc-128">Pode cambiar o panel de datos da dereita para seleccionar que campo debe mostrar a entidade do cliente na galería.</span><span class="sxs-lookup"><span data-stu-id="78bbc-128">You can change the data panel on the right to select which field for the Customer entity to show on the gallery.</span></span>

1. <span data-ttu-id="78bbc-129">Se desexa mostrar algún campo do cliente seleccionado na galería, encha a propiedade Texto dunha etiqueta: **{Name_of_the_gallery}.Seleccionado.{property_name}**</span><span class="sxs-lookup"><span data-stu-id="78bbc-129">If you want to show any field from the selected customer on the gallery, fill in the Text property of a label:  **{Name_of_the_gallery}.Selected.{property_name}**</span></span>

    <span data-ttu-id="78bbc-130">Exemplo: Gallery1.Selected.address1_city</span><span class="sxs-lookup"><span data-stu-id="78bbc-130">Example: Gallery1.Selected.address1_city</span></span>

1. <span data-ttu-id="78bbc-131">Para mostrar a liña de tempo unificada para un cliente, engada un elemento de galería e a propiedade Elementos: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**</span><span class="sxs-lookup"><span data-stu-id="78bbc-131">To display the unified timeline for a customer, add a Gallery element, and add the Items property: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**</span></span>

    <span data-ttu-id="78bbc-132">Exemplo: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)</span><span class="sxs-lookup"><span data-stu-id="78bbc-132">Example: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)</span></span>
