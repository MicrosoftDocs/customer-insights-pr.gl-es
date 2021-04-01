---
title: Conector de Power Apps
description: Conecte con Power Apps e Power Automate.
ms.date: 01/19/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 3fa91553fd50a22ab62b5a2b1e3f13b9483776a8
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598153"
---
# <a name="microsoft-power-apps-connector-preview"></a><span data-ttu-id="79f25-103">Conector de Microsoft Power Apps (vista previa)</span><span class="sxs-lookup"><span data-stu-id="79f25-103">Microsoft Power Apps connector (preview)</span></span>

<span data-ttu-id="79f25-104">Consiga perfís de clientes unificados ás súas aplicacións personalizadas con Power Apps.</span><span class="sxs-lookup"><span data-stu-id="79f25-104">Bring unified customer profiles into your personalized apps with Power Apps.</span></span>

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a><span data-ttu-id="79f25-105">Conectar Power Apps e Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="79f25-105">Connect Power Apps and Dynamics 365 Customer Insights</span></span>

<span data-ttu-id="79f25-106">Customer Insights é unha das moitas [orixes dispoñibles para datos en Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).</span><span class="sxs-lookup"><span data-stu-id="79f25-106">Customer Insights is one of the many [available sources for data in Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).</span></span>

<span data-ttu-id="79f25-107">Consulte a documentación de Power Apps para aprender a [engadir unha conexión de datos a unha aplicación](/powerapps/maker/canvas-apps/add-data-connection).</span><span class="sxs-lookup"><span data-stu-id="79f25-107">Refer to the Power Apps documentation to learn how to [add a data connection to an app](/powerapps/maker/canvas-apps/add-data-connection).</span></span> <span data-ttu-id="79f25-108">Recomendamos que revise tamén [como Power Apps usa a delegación para xestionar grandes conxuntos de datos en aplicacións de lenzo](/powerapps/maker/canvas-apps/delegation-overview).</span><span class="sxs-lookup"><span data-stu-id="79f25-108">We recommend you also review [how Power Apps uses delegation to handle large datasets in Canvas apps](/powerapps/maker/canvas-apps/delegation-overview).</span></span>

## <a name="available-entities"></a><span data-ttu-id="79f25-109">Entidades dispoñibles</span><span class="sxs-lookup"><span data-stu-id="79f25-109">Available entities</span></span>

<span data-ttu-id="79f25-110">Despois de engadir Customer Insights como conexión de datos, pode escoller as seguintes entidades en Power Apps:</span><span class="sxs-lookup"><span data-stu-id="79f25-110">After adding Customer Insights as a data connection, you can choose the following entities in Power Apps:</span></span>

- <span data-ttu-id="79f25-111">Cliente: para usar datos do [perfil de cliente unificado](customer-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="79f25-111">Customer: to use data from the [unified customer profile](customer-profiles.md).</span></span>
- <span data-ttu-id="79f25-112">UnifiedActivity: para mostrar a [liña de tempo de actividade](activities.md) na aplicación.</span><span class="sxs-lookup"><span data-stu-id="79f25-112">UnifiedActivity: to display the [activity timeline](activities.md) on the app.</span></span>

## <a name="limitations"></a><span data-ttu-id="79f25-113">Limitacións</span><span class="sxs-lookup"><span data-stu-id="79f25-113">Limitations</span></span>

### <a name="retrievable-entities"></a><span data-ttu-id="79f25-114">Entidades recuperables</span><span class="sxs-lookup"><span data-stu-id="79f25-114">Retrievable entities</span></span>

<span data-ttu-id="79f25-115">Só pode recuperar as entidades **Cliente**, **UnifiedActivity** e **Segmentos** a través do conector Power Apps.</span><span class="sxs-lookup"><span data-stu-id="79f25-115">You can only retrieve the **Customer**, **UnifiedActivity**, and **Segments** entities through the Power Apps connector.</span></span> <span data-ttu-id="79f25-116">Amósanse outras entidades porque o conector subxacente as admite a través de desencadeadores en Power Automate.</span><span class="sxs-lookup"><span data-stu-id="79f25-116">Other entities are shown because the underlying connector supports them through triggers in Power Automate.</span></span>  

### <a name="delegation"></a><span data-ttu-id="79f25-117">Delegación</span><span class="sxs-lookup"><span data-stu-id="79f25-117">Delegation</span></span>

<span data-ttu-id="79f25-118">A delegación funciona para a entidade de cliente e a entidade UnifiedActivity.</span><span class="sxs-lookup"><span data-stu-id="79f25-118">Delegation works for the Customer entity and UnifiedActivity entity.</span></span> 

- <span data-ttu-id="79f25-119">Delegación para a entidade **Cliente**: para usar a delegación para esta entidade, os campos deben indexarse en [Buscar e filtrar o índice](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="79f25-119">Delegation for **Customer** entity: To use delegation for this entity, the fields need to be indexed in [Search & filter index](search-filter-index.md).</span></span>  

- <span data-ttu-id="79f25-120">Delegación para **UnifiedActivity**: a delegación para esta entidade só funciona para os campos **ActivityId** e **ID de cliente**.</span><span class="sxs-lookup"><span data-stu-id="79f25-120">Delegation for **UnifiedActivity**: Delegation for this entity only works for the fields **ActivityId** and **CustomerId**.</span></span>  

- <span data-ttu-id="79f25-121">Para obter máis información sobre a delegación, consulte [Funcións e operacións delegables de Power Apps](/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps).</span><span class="sxs-lookup"><span data-stu-id="79f25-121">For more information about delegation, see [Power Apps delegable functions and operations](/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps).</span></span> 

## <a name="example-gallery-control"></a><span data-ttu-id="79f25-122">Exemplo de control de galería</span><span class="sxs-lookup"><span data-stu-id="79f25-122">Example gallery control</span></span>

<span data-ttu-id="79f25-123">Por exemplo, engada perfís de clientes a un [control da galería](/powerapps/maker/canvas-apps/add-gallery).</span><span class="sxs-lookup"><span data-stu-id="79f25-123">For example, you add customer profiles to a [gallery control](/powerapps/maker/canvas-apps/add-gallery).</span></span>

1. <span data-ttu-id="79f25-124">Engada un control de **Galería** a unha aplicación que estea a crear.</span><span class="sxs-lookup"><span data-stu-id="79f25-124">Add a **Gallery** control to an app you're building.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="79f25-125">![Engadir un elemento da galería](media/connector-powerapps9.png "Engadir un elemento da galería")</span><span class="sxs-lookup"><span data-stu-id="79f25-125">![Add a gallery element](media/connector-powerapps9.png "Add a gallery element")</span></span>

1. <span data-ttu-id="79f25-126">Seleccione **Cliente** como orixe de datos para os elementos.</span><span class="sxs-lookup"><span data-stu-id="79f25-126">Select **Customer** as the data source for items.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="79f25-127">![Seleccionar unha orixe de datos](media/choose-datasource-powerapps.png "Seleccionar unha orixe de datos")</span><span class="sxs-lookup"><span data-stu-id="79f25-127">![Select a data source](media/choose-datasource-powerapps.png "Select a data source")</span></span>

1. <span data-ttu-id="79f25-128">Pode cambiar o panel de datos da dereita para seleccionar que campo debe mostrar a entidade do cliente na galería.</span><span class="sxs-lookup"><span data-stu-id="79f25-128">You can change the data panel on the right to select which field for the Customer entity to show on the gallery.</span></span>

1. <span data-ttu-id="79f25-129">Se desexa mostrar algún campo do cliente seleccionado na galería, encha a propiedade Texto dunha etiqueta: **{Name_of_the_gallery}.Seleccionado.{property_name}**</span><span class="sxs-lookup"><span data-stu-id="79f25-129">If you want to show any field from the selected customer on the gallery, fill in the Text property of a label:  **{Name_of_the_gallery}.Selected.{property_name}**</span></span>

    <span data-ttu-id="79f25-130">Exemplo: Gallery1.Selected.address1_city</span><span class="sxs-lookup"><span data-stu-id="79f25-130">Example: Gallery1.Selected.address1_city</span></span>

1. <span data-ttu-id="79f25-131">Para mostrar a liña de tempo unificada para un cliente, engada un elemento de galería e a propiedade Elementos: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**</span><span class="sxs-lookup"><span data-stu-id="79f25-131">To display the unified timeline for a customer, add a Gallery element, and add the Items property: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**</span></span>

    <span data-ttu-id="79f25-132">Exemplo: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)</span><span class="sxs-lookup"><span data-stu-id="79f25-132">Example: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]