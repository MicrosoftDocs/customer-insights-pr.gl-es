---
title: Buscar e filtrar perfís de clientes
description: Busque rapidamente información sobre perfís de clientes unificados e filtre por atributos especificados.
ms.date: 01/19/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: b6cc0ad1a47a6c00e3bf220271f42870fc53621b
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597141"
---
# <a name="customer-profiles-search--filter-index"></a><span data-ttu-id="dd6f5-103">Perfís de clientes: índice de busca e filtro</span><span class="sxs-lookup"><span data-stu-id="dd6f5-103">Customer profiles: Search & filter index</span></span>

<span data-ttu-id="dd6f5-104">O resultado de unificar os seus datos de clientes é unha entidade de perfil de cliente que fornece unha vista unificada na súa base de clientes total.</span><span class="sxs-lookup"><span data-stu-id="dd6f5-104">The result of unifying your customer data is a Customer Profile entity that provides a unified view into your total customer base.</span></span> <span data-ttu-id="dd6f5-105">Para [buscar información rapidamente sobre un cliente ou grupo de clientes específicos](customer-profiles.md), pode configurar as capacidades **Buscar** e **Filtrar** na páxina **Clientes**.</span><span class="sxs-lookup"><span data-stu-id="dd6f5-105">To quickly [find information on a specific customer or group of customers](customer-profiles.md), you can configure the **Search** and **Filter** capabilities on the **Customers** page.</span></span> <span data-ttu-id="dd6f5-106">Continúe lendo para aprender como poden os administradores editar os atributos na páxina **Índice de busca e filtro**, que están dispoñibles para os usuarios para buscar e filtrar.</span><span class="sxs-lookup"><span data-stu-id="dd6f5-106">Read on to learn how admins can edit the attributes on the **Search & filter index** page, which are available to users for searching and filtering.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="dd6f5-107">![Buscar filtro](media/search-filter.png "Buscar filtro")</span><span class="sxs-lookup"><span data-stu-id="dd6f5-107">![Search filter](media/search-filter.png "Search filter")</span></span>

## <a name="add-fields-and-specify-attributes"></a><span data-ttu-id="dd6f5-108">Engadir campos e especificar atributos</span><span class="sxs-lookup"><span data-stu-id="dd6f5-108">Add fields and specify attributes</span></span>

<span data-ttu-id="dd6f5-109">Se é a primeira vez que define atributos que se poden buscar como administrador, primeiro deberá definir os campos indexados.</span><span class="sxs-lookup"><span data-stu-id="dd6f5-109">If it's the first time you define searchable attributes as an administrator, you need to define indexed fields first.</span></span> <span data-ttu-id="dd6f5-110">Suxerímoslle que escolla todos os atributos cos que os usuarios poidan buscar e filtrar clientes na páxina **Clientes**.</span><span class="sxs-lookup"><span data-stu-id="dd6f5-110">We suggest you choose all the attributes by which users can search and filter customers on the **Customers** page.</span></span> <span data-ttu-id="dd6f5-111">Só pode especificar atributos que existen na entidade de Perfil de cliente que creou durante o proceso de unificación de datos.</span><span class="sxs-lookup"><span data-stu-id="dd6f5-111">You can only specify attributes that exist in the Customer Profile entity that you created during the data unification process.</span></span>

1. <span data-ttu-id="dd6f5-112">Abra a páxina **Clientes** e seleccione **Índice de busca e filtro**.</span><span class="sxs-lookup"><span data-stu-id="dd6f5-112">Open the **Customers** page and select **Search & filter index**.</span></span>

2. <span data-ttu-id="dd6f5-113">Seleccione **+ Engadir** para especificar os campos indexados.</span><span class="sxs-lookup"><span data-stu-id="dd6f5-113">Select **+ Add** to specify the indexed fields.</span></span>

3. <span data-ttu-id="dd6f5-114">Seleccione os atributos da lista que desexa engadir como campos indexados.</span><span class="sxs-lookup"><span data-stu-id="dd6f5-114">Select the attributes in the list you want to add as indexed fields.</span></span> <span data-ttu-id="dd6f5-115">Sempre pode engadir máis atributos seleccionando **Engadir**.</span><span class="sxs-lookup"><span data-stu-id="dd6f5-115">You can always add more attributes by selecting **Add**.</span></span> <span data-ttu-id="dd6f5-116">Tamén pode eliminar todos os atributos seleccionados seleccionando o símbolo **Quitar**.</span><span class="sxs-lookup"><span data-stu-id="dd6f5-116">You can also remove any selected attributes by selecting the **Remove** symbol.</span></span>

## <a name="explore-the-indexed-customer-fields-table"></a><span data-ttu-id="dd6f5-117">Explorar a táboa de campos de clientes indexados</span><span class="sxs-lookup"><span data-stu-id="dd6f5-117">Explore the Indexed customer fields table</span></span>

<span data-ttu-id="dd6f5-118">A seguinte información preséntase na táboa.</span><span class="sxs-lookup"><span data-stu-id="dd6f5-118">The following information is presented in the table.</span></span>

- <span data-ttu-id="dd6f5-119">**Nome**: representa o nome do atributo tal e como aparece na entidade de Perfil do cliente.</span><span class="sxs-lookup"><span data-stu-id="dd6f5-119">**Name**: Represents the attribute's name as it appears in the Customer Profile entity.</span></span>
- <span data-ttu-id="dd6f5-120">**Tipo de datos**: especifica se o tipo de datos é unha cadea, un número ou unha data.</span><span class="sxs-lookup"><span data-stu-id="dd6f5-120">**Data type**: Specifies whether the data type is a string, a number, or a date.</span></span>
- <span data-ttu-id="dd6f5-121">**Incluído na busca**: especifica se este atributo se pode usar para buscar clientes na páxina **Clientes** usando o campo **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="dd6f5-121">**Included in search**: Specifies whether this attribute can be used for searching customers on the **Customers** page using the **Search** field.</span></span>
- <span data-ttu-id="dd6f5-122">**Engadir filtro**: controle a definición de como se pode usar este atributo para filtrar na páxina **Clientes**.</span><span class="sxs-lookup"><span data-stu-id="dd6f5-122">**Add Filter**: Control to define how this attribute can be used for filtering on the **Customers** page.</span></span>

## <a name="editing-filtering-options-for-a-given-attribute"></a><span data-ttu-id="dd6f5-123">Edición de opcións de filtrado dun atributo dado</span><span class="sxs-lookup"><span data-stu-id="dd6f5-123">Editing filtering options for a given attribute</span></span>

<span data-ttu-id="dd6f5-124">O menú **Filtro** da páxina **Clientes** pode incluír un número variable de niveis de atributos (por exemplo, diferentes grupos de idade polos que filtrar os clientes).</span><span class="sxs-lookup"><span data-stu-id="dd6f5-124">The **Filter** menu on the **Customers** page can include a varying number of attribute levels (for example, different age groups to filter customers by).</span></span>

1. <span data-ttu-id="dd6f5-125">Seleccione **Engadir filtro** para un atributo determinado na páxina **Índice de busca e filtro**.</span><span class="sxs-lookup"><span data-stu-id="dd6f5-125">Select **Add Filter** for a given attribute on the **Search & filter index** page.</span></span> <span data-ttu-id="dd6f5-126">Pode definir o número de resultados e a orde en que se organizarán.</span><span class="sxs-lookup"><span data-stu-id="dd6f5-126">You can define the number of results and the order in which they'll be organized.</span></span> <span data-ttu-id="dd6f5-127">Dependendo do tipo de datos do atributo, aparecerá un dos seguintes paneis.</span><span class="sxs-lookup"><span data-stu-id="dd6f5-127">Depending on the attribute's data type, one of the following panes appears.</span></span>

- <span data-ttu-id="dd6f5-128">Atributos do tipo de cadea: especifique o número de resultados desexados no panel **Opcións de filtro de cadeas** e a política de pedidos pola que se organizarán.</span><span class="sxs-lookup"><span data-stu-id="dd6f5-128">String-type attributes: Specify the number of desired results on the **String filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="dd6f5-129">Atributos do tipo numérico: especifique os intervalos incluídos no panel **Opcións de filtro de números** e a política de pedidos pola que se organizarán.</span><span class="sxs-lookup"><span data-stu-id="dd6f5-129">Numerical-type attributes: Specify the intervals included on the **Number filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="dd6f5-130">Atributos do tipo de data: especifique os intervalos incluídos no panel **Opcións de filtro de datas** e a política de pedidos pola que se organizarán.</span><span class="sxs-lookup"><span data-stu-id="dd6f5-130">Date-type attributes:  Specify the intervals included on the **Date filter options** pane and the order policy by which they'll be organized.</span></span>

2. <span data-ttu-id="dd6f5-131">Seleccione **Gardar** para aplicar as modificacións.</span><span class="sxs-lookup"><span data-stu-id="dd6f5-131">Select **Save** to apply your changes.</span></span>

3. <span data-ttu-id="dd6f5-132">Seleccione **Executar** unha vez estea listo para aplicar a súa configuración.</span><span class="sxs-lookup"><span data-stu-id="dd6f5-132">Select **Run** once you're ready to apply your settings.</span></span>

## <a name="next-steps"></a><span data-ttu-id="dd6f5-133">Pasos seguintes</span><span class="sxs-lookup"><span data-stu-id="dd6f5-133">Next steps</span></span>

<span data-ttu-id="dd6f5-134">Vaia á páxina **Clientes** para buscar perfís de clientes ou use os campos indexados para ver un subconxunto de todos os perfís de clientes.</span><span class="sxs-lookup"><span data-stu-id="dd6f5-134">Go to the **Customers** page to search for customer profiles or use the indexed fields to see a subset of all customer profiles.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]