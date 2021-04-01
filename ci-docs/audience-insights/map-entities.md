---
title: Asignar entidades para a unificación de datos
description: Asigne datos para crear perfís de clientes unificados.
ms.date: 09/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 36b7f7b2fac9497245cf6759506c53753972f173
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595991"
---
# <a name="map-entities-and-attributes"></a><span data-ttu-id="6db8f-103">Entidades e atributos do mapa</span><span class="sxs-lookup"><span data-stu-id="6db8f-103">Map entities and attributes</span></span>

<span data-ttu-id="6db8f-104">**Asignar** é a primeira etapa do proceso de unificación de datos da información do público.</span><span class="sxs-lookup"><span data-stu-id="6db8f-104">**Map** is the first stage in the data unification process of audience insights.</span></span> <span data-ttu-id="6db8f-105">A asignación consta de tres fases:</span><span class="sxs-lookup"><span data-stu-id="6db8f-105">Mapping consists of three phases:</span></span>

- <span data-ttu-id="6db8f-106">*Selección de entidades*: identifique as entidades combinables que conducen a un conxunto de datos con información máis completa sobre os seus clientes.</span><span class="sxs-lookup"><span data-stu-id="6db8f-106">*Entity selection*: Identify the combinable entities that lead to a dataset with more complete information about your customers.</span></span>
- <span data-ttu-id="6db8f-107">*Selección de atributos*: para cada entidade, identifique as columnas que desexa combinar e reconciliar nas fases *coincidencia* e *combinación*.</span><span class="sxs-lookup"><span data-stu-id="6db8f-107">*Attribute selection*: For each entity, identify the columns you want to combine and reconcile in the *match* and *merge* phases.</span></span> <span data-ttu-id="6db8f-108">Estas columnas chámanse *Atributos*.</span><span class="sxs-lookup"><span data-stu-id="6db8f-108">These columns are called *Attributes*.</span></span>
- <span data-ttu-id="6db8f-109">*Selección de clave primaria e tipo semántico*: para cada entidade, identifique un atributo que desexe definir como clave principal desa entidade e, para cada atributo, identifique un tipo semántico que describa mellor ese atributo.</span><span class="sxs-lookup"><span data-stu-id="6db8f-109">*Primary key and semantic type selection*: For each entity, identify an attribute you want to define as the primary key for that entity, and for each attribute, identify a semantic type that best describes that attribute.</span></span>

<span data-ttu-id="6db8f-110">Para obter máis información sobre o fluxo xeral de unificación de datos, consulte [Unificar](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="6db8f-110">For more information about the general flow of data unification, see [Unify](data-unification.md).</span></span>

## <a name="select-the-first-entities"></a><span data-ttu-id="6db8f-111">Seleccionar as primeiras entidades</span><span class="sxs-lookup"><span data-stu-id="6db8f-111">Select the first entities</span></span>

1. <span data-ttu-id="6db8f-112">Na información do público, vaia a **Datos** > **Unificar** > **Asignar**.</span><span class="sxs-lookup"><span data-stu-id="6db8f-112">In audience insights, go to **Data** > **Unify** > **Map**.</span></span>

2. <span data-ttu-id="6db8f-113">Inicie a fase de asignación seleccionando **Seleccionar entidades**.</span><span class="sxs-lookup"><span data-stu-id="6db8f-113">Start the map phase by selecting **Select entities**.</span></span>

3. <span data-ttu-id="6db8f-114">Seleccione as entidades e atributos que desexe empregar nas fases *atopar coincidencia* e *combinar*.</span><span class="sxs-lookup"><span data-stu-id="6db8f-114">Select the entities and attributes you want to use in the *match* and *merge* phases.</span></span> <span data-ttu-id="6db8f-115">Pode seleccionar os atributos requiridos individualmente dunha entidade ou incluír todos os atributos dunha entidade seleccionando a caixa de verificación **Incluír todos os campos** a nivel de entidade.</span><span class="sxs-lookup"><span data-stu-id="6db8f-115">You can select the required attributes individually from an entity or include all attributes from an entity by selecting the **Include all fields** checkbox on the entity level.</span></span> <span data-ttu-id="6db8f-116">Recomendamos seleccionar polo menos dúas entidades para beneficiarse do proceso de unificación de datos.</span><span class="sxs-lookup"><span data-stu-id="6db8f-116">We recommend selecting at least two entities to benefit from the data unification process.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6db8f-117">![Exemplo de engadir entidades](media/data-manager-configure-map-add-entities-example.png "Exemplo de engadir entidades")</span><span class="sxs-lookup"><span data-stu-id="6db8f-117">![Add entities example](media/data-manager-configure-map-add-entities-example.png "Add entities example")</span></span>

   <span data-ttu-id="6db8f-118">Neste exemplo, engadimos as entidades **eCommerceContacts** e **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="6db8f-118">In this example, we're adding the **eCommerceContacts** and **loyCustomers** entities.</span></span> <span data-ttu-id="6db8f-119">Se escolle estas entidades, pode obter información sobre cales dos clientes comerciais en liña son membros do programa de fidelización.</span><span class="sxs-lookup"><span data-stu-id="6db8f-119">By choosing these entities, you can derive insights on which of the online business customers are loyalty program members.</span></span>
   
   <span data-ttu-id="6db8f-120">Pode buscar palabras clave en todos os atributos e entidades para seleccionar os atributos requiridos que desexa asignar.</span><span class="sxs-lookup"><span data-stu-id="6db8f-120">You can search on keywords across all attributes and entities to select the required attributes you want to map.</span></span>
   
     > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6db8f-121">![Exemplo de campos de busca](media/data-manager-configure-map-search-fields-example.png "Exemplo de campos de busca")</span><span class="sxs-lookup"><span data-stu-id="6db8f-121">![Search fields example](media/data-manager-configure-map-search-fields-example.png "Search fields example")</span></span>

4. <span data-ttu-id="6db8f-122">Seleccione **Aplicar** para confirmar as súas seleccións.</span><span class="sxs-lookup"><span data-stu-id="6db8f-122">Select **Apply** to confirm your selections.</span></span>

## <a name="select-primary-key-and-semantic-type-for-attributes"></a><span data-ttu-id="6db8f-123">Seleccione a clave primaria e o tipo semántico para os atributos</span><span class="sxs-lookup"><span data-stu-id="6db8f-123">Select primary key and semantic type for attributes</span></span>

<span data-ttu-id="6db8f-124">Despois de seleccionar as súas entidades, a páxina **Mapa** enumera as entidades seleccionadas para a súa revisión.</span><span class="sxs-lookup"><span data-stu-id="6db8f-124">After selecting your entities, the **Map** page lists the selected entities for your review.</span></span> <span data-ttu-id="6db8f-125">Defina a clave principal dunha entidade e identifique o tipo semántico dun atributo na entidade.</span><span class="sxs-lookup"><span data-stu-id="6db8f-125">Define the primary key for an entity and identify the semantic type for an attribute in the entity.</span></span>

- <span data-ttu-id="6db8f-126">**Clave primaria**: seleccione un atributo como clave principal para cada unha das súas entidades.</span><span class="sxs-lookup"><span data-stu-id="6db8f-126">**Primary key**: Select one attribute as a primary key for each of your entities.</span></span> <span data-ttu-id="6db8f-127">Para que un atributo sexa unha clave primaria válida, non debe incluír valores duplicados, valores perdidos ou valores nulos.</span><span class="sxs-lookup"><span data-stu-id="6db8f-127">For an attribute to be a valid primary key, it shouldn't include duplicate values, missing values, or null values.</span></span> <span data-ttu-id="6db8f-128">Os atributos de tipo de datos de cadea, número enteiro e GUID admítense como claves primarias e amosaranse nun campo onde escoller.</span><span class="sxs-lookup"><span data-stu-id="6db8f-128">String, integer, and GUID data type attributes are supported as primary keys and will be displayed in a field for you to select from.</span></span>

- <span data-ttu-id="6db8f-129">**Tipo semántico de atributo**: categorías dos seus atributos, como o enderezo de correo electrónico ou o nome.</span><span class="sxs-lookup"><span data-stu-id="6db8f-129">**Attribute semantic type**: Categories of your attributes, such as email address or name.</span></span> <span data-ttu-id="6db8f-130">Para usar modelos de IA para a predición intelixente de semántica, aforrar tempo e mellorar a precisión, configure **Asignación intelixente** en **ACTIVADO**.</span><span class="sxs-lookup"><span data-stu-id="6db8f-130">To use AI models for smart prediction of semantics, save time and improve accuracy, set **Intelligent mapping** to **ON**.</span></span> <span data-ttu-id="6db8f-131">A asignación intelixente resalta a recomendación de semántica baseada en IA no campo **Tipo**.</span><span class="sxs-lookup"><span data-stu-id="6db8f-131">Intelligent mapping highlights AI-based semantics recommendation in the **Type** field.</span></span> <span data-ttu-id="6db8f-132">Se a configura en **DESACTIVADO**, verá as nosas recomendacións de asignación regular.</span><span class="sxs-lookup"><span data-stu-id="6db8f-132">If you set it to **OFF**, you will see our regular mapping recommendations.</span></span> <span data-ttu-id="6db8f-133">Pode seleccionar calquera tipo semántico na lista de opcións dispoñibles e anular a selección suxerida.</span><span class="sxs-lookup"><span data-stu-id="6db8f-133">You can select any semantic type from the available list of options and override the suggested selection.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="6db8f-134">![Tipo de atributo e predición semántica](media/data-manager-configure-map-add-attributes-semantic-prediction.png "Tipo de atributo e predición semántica")</span><span class="sxs-lookup"><span data-stu-id="6db8f-134">![Attribute type and semantic prediction](media/data-manager-configure-map-add-attributes-semantic-prediction.png "Attribute type and semantic prediction")</span></span>

<span data-ttu-id="6db8f-135">Tamén é posible engadir un tipo semántico personalizado.</span><span class="sxs-lookup"><span data-stu-id="6db8f-135">Adding a custom semantic type is also possible.</span></span> <span data-ttu-id="6db8f-136">Seleccione o campo de tipo dun atributo e escriba o seu nome de tipo semántico personalizado.</span><span class="sxs-lookup"><span data-stu-id="6db8f-136">Select the type field for an attribute, and type your custom semantic type name.</span></span> <span data-ttu-id="6db8f-137">Deste xeito, tamén pode cambiar os tipos de atributo que foron identificados polo sistema.</span><span class="sxs-lookup"><span data-stu-id="6db8f-137">This way, you can also change the attribute types that were identified by the system.</span></span>

<span data-ttu-id="6db8f-138">Todos os atributos para os que se identifica automaticamente un tipo semántico agrúpanse na sección **Revisa os campos asignados**.</span><span class="sxs-lookup"><span data-stu-id="6db8f-138">All attributes for which a semantic type is automatically identified are grouped in the **Review mapped fields** section.</span></span> <span data-ttu-id="6db8f-139">Revise estes atributos e os seus tipos semánticos porque se empregarán para combinar as súas entidades no paso de combinación da unificación de datos.</span><span class="sxs-lookup"><span data-stu-id="6db8f-139">Review these attributes and their semantic types because they'll be used to combine your entities in the merge step of data unification.</span></span>

<span data-ttu-id="6db8f-140">Os atributos que non se asignan automaticamente a un tipo semántico agrúpanse na sección **Definir os datos nos campos non asignados**.</span><span class="sxs-lookup"><span data-stu-id="6db8f-140">Attributes that aren't automatically mapped to a semantic type are grouped in the **Define the data in the unmapped fields** section.</span></span> <span data-ttu-id="6db8f-141">Seleccione o campo de tipo semántico para os atributos non asignados ou introduza o seu nome de tipo de atributo personalizado.</span><span class="sxs-lookup"><span data-stu-id="6db8f-141">Select the semantic type field for the unmapped attributes, or enter your custom attribute-type name.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="6db8f-142">![Clave primaria e tipo de atributo](media/data-manager-configure-map-add-attributes.png "Clave primaria e tipo de atributo")</span><span class="sxs-lookup"><span data-stu-id="6db8f-142">![Primary key and attribute type](media/data-manager-configure-map-add-attributes.png "Primary key and attribute type")</span></span>

> [!NOTE]
> <span data-ttu-id="6db8f-143">Un campo debería asignarse ao tipo semántico Person.FullName para completar o nome do cliente na tarxeta do cliente.</span><span class="sxs-lookup"><span data-stu-id="6db8f-143">One field should map to the semantic type Person.FullName to populate the customer name in customer card.</span></span> <span data-ttu-id="6db8f-144">Do contrario, os cartóns de cliente aparecerán sen nome.</span><span class="sxs-lookup"><span data-stu-id="6db8f-144">Otherwise, the customer cards will appear nameless.</span></span> 

## <a name="add-and-remove-attributes-and-entities"></a><span data-ttu-id="6db8f-145">Engadir e eliminar atributos e entidades</span><span class="sxs-lookup"><span data-stu-id="6db8f-145">Add and remove attributes and entities</span></span>

1. <span data-ttu-id="6db8f-146">En **Unificar** > **Mapa**, seleccione **Editar campos**.</span><span class="sxs-lookup"><span data-stu-id="6db8f-146">On **Unify** > **Map**, select **Edit fields**.</span></span>

2. <span data-ttu-id="6db8f-147">No panel **Editar campos**, engada ou elimine atributos e entidades.</span><span class="sxs-lookup"><span data-stu-id="6db8f-147">In the **Edit fields** pane, add or remove attributes and entities.</span></span> <span data-ttu-id="6db8f-148">Use a busca ou o desprazamento para atopar e seleccionar os seus atributos e entidades de interese.</span><span class="sxs-lookup"><span data-stu-id="6db8f-148">Use the search or scroll to find and select your attributes and entities of interest.</span></span> <span data-ttu-id="6db8f-149">Non pode eliminar un atributo ou unha entidade se xa coincidiron.</span><span class="sxs-lookup"><span data-stu-id="6db8f-149">You can't remove an attribute or an entity if they've already been matched.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6db8f-150">![Engadir ou eliminar atributos](media/configure-data-map-edit.png "Engadir ou eliminar atributos")</span><span class="sxs-lookup"><span data-stu-id="6db8f-150">![Add or remove attributes](media/configure-data-map-edit.png "Add or remove attributes")</span></span>

3. <span data-ttu-id="6db8f-151">Seleccione **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="6db8f-151">Select **Apply**.</span></span>

## <a name="add-images-to-profiles"></a><span data-ttu-id="6db8f-152">Engadir imaxes aos perfís</span><span class="sxs-lookup"><span data-stu-id="6db8f-152">Add images to profiles</span></span>

<span data-ttu-id="6db8f-153">Se unha entidade contén URL para imaxes ou logotipos de perfil dispoñibles publicamente, pode engadilos ao perfil de cliente unificado.</span><span class="sxs-lookup"><span data-stu-id="6db8f-153">If an entity contains URLs to publicly available profile images or logos, you can add them to the unified customer profile.</span></span>

<span data-ttu-id="6db8f-154">Seleccione a entidade e busque o campo que contén o URL á imaxe de perfil.</span><span class="sxs-lookup"><span data-stu-id="6db8f-154">Select the entity and find the field that contains the URL to the profile image.</span></span> <span data-ttu-id="6db8f-155">No campo de entrada **Tipo**, introduza o valor seguinte manualmente:</span><span class="sxs-lookup"><span data-stu-id="6db8f-155">In the **Type** input field, manually enter the following value:</span></span> 
- <span data-ttu-id="6db8f-156">Para unha persoa: Person.ProfileImage</span><span class="sxs-lookup"><span data-stu-id="6db8f-156">For a person: Person.ProfileImage</span></span>
- <span data-ttu-id="6db8f-157">Para unha organización: Organization.LogoImage</span><span class="sxs-lookup"><span data-stu-id="6db8f-157">For an organization: Organization.LogoImage</span></span>

<span data-ttu-id="6db8f-158">Continúe cos pasos de unificación e asegúrese de que o atributo que contén o URL da imaxe tamén se engada ao paso [Combinar](merge-entities.md).</span><span class="sxs-lookup"><span data-stu-id="6db8f-158">Continue with the unification steps and ensure the attribute that contains the image URL is also added in the [Merge](merge-entities.md) step.</span></span>

## <a name="set-attributes-for-organizations"></a><span data-ttu-id="6db8f-159">Establecer atributos para organizacións</span><span class="sxs-lookup"><span data-stu-id="6db8f-159">Set attributes for organizations</span></span>

<span data-ttu-id="6db8f-160">Para organizacións (vista previa), o tipo de atributo debería asignarse a "Organization.Name"</span><span class="sxs-lookup"><span data-stu-id="6db8f-160">For organizations (Preview), the attribute type should be mapped to "Organization.Name"</span></span>
> [!div class="mx-imgBorder"]
> <span data-ttu-id="6db8f-161">![Clave primaria e tipo de atributo B2B](media/configure-data-map-edit-b2b.png "Clave primaria e tipo de atributo B2B")</span><span class="sxs-lookup"><span data-stu-id="6db8f-161">![Primary key and attribute type B2B](media/configure-data-map-edit-b2b.png "Primary key and attribute type B2B")</span></span>

## <a name="next-step"></a><span data-ttu-id="6db8f-162">Seguinte paso</span><span class="sxs-lookup"><span data-stu-id="6db8f-162">Next step</span></span>

<span data-ttu-id="6db8f-163">Como parte do proceso de unificación de datos, diríxase á páxina **Coincidencia**.</span><span class="sxs-lookup"><span data-stu-id="6db8f-163">As part of the data unification process, go to the **Match** page.</span></span> <span data-ttu-id="6db8f-164">Visite [**Coincidencia**](match-entities.md) para obter información sobre esta fase.</span><span class="sxs-lookup"><span data-stu-id="6db8f-164">Visit [**Match**](match-entities.md) to learn about this phase.</span></span>

> [!TIP]
> <span data-ttu-id="6db8f-165">Consulte o seguinte vídeo: [Primeiros pasos: creación dun perfil de cliente unificado](https://youtu.be/oBfGEhucAxs).</span><span class="sxs-lookup"><span data-stu-id="6db8f-165">Check out the following video: [Getting Started: Creating a Unified Customer Profile](https://youtu.be/oBfGEhucAxs).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]