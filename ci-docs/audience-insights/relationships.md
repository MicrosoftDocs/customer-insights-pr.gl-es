---
title: Relacións entre entidades e camiños das entidades
description: Cree e xestione relacións entre entidades a partir de varias fontes de datos.
ms.date: 04/14/2020
ms.reviewer: mukeshpo
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 295c372bb452e7c40aa950506dc494d4a2de1108
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405739"
---
# <a name="relationships-between-entities"></a><span data-ttu-id="8fb53-103">Relacións entre entidades</span><span class="sxs-lookup"><span data-stu-id="8fb53-103">Relationships between entities</span></span>

<span data-ttu-id="8fb53-104">As relacións axúdanlle a conectar entidades e a xerar un gráfico dos seus datos cando as entidades comparten un identificador común (clave estranxeira) ao que se pode facer referencia dunha entidade a outra.</span><span class="sxs-lookup"><span data-stu-id="8fb53-104">Relationships help you connect entities and generate a graph of your data when entities share a common identifier (foreign key) that can be referenced from one entity to another.</span></span> <span data-ttu-id="8fb53-105">As entidades conectadas permiten definir segmentos e medidas en función de varias orixes de datos.</span><span class="sxs-lookup"><span data-stu-id="8fb53-105">Connected entities enable you to define segments and measures based on multiple data sources.</span></span>

<span data-ttu-id="8fb53-106">Hai dous tipos de relacións.</span><span class="sxs-lookup"><span data-stu-id="8fb53-106">There are two types of relationships.</span></span> <span data-ttu-id="8fb53-107">As relacións do sistema non editables, que se crean automaticamente, e as relacións personalizadas creadas e configuradas polos usuarios.</span><span class="sxs-lookup"><span data-stu-id="8fb53-107">Non-editable system relationships, which are created automatically, and custom relationships created and configured by users.</span></span>

<span data-ttu-id="8fb53-108">Durante os procesos de combinación e localización de coincidencias, as relacións do sistema créanse entre bastidores baseándose nunha correspondencia intelixente.</span><span class="sxs-lookup"><span data-stu-id="8fb53-108">During the match and merge processes, system relationships are created behind the scenes based on intelligent matching.</span></span> <span data-ttu-id="8fb53-109">Estas relacións axudan a relacionar os rexistros do perfil de cliente con rexistros doutras entidades correspondentes.</span><span class="sxs-lookup"><span data-stu-id="8fb53-109">These relationships help relate the Customer Profile records with other corresponding entities' records.</span></span> <span data-ttu-id="8fb53-110">O seguinte diagrama ilustra a creación de tres relacións do sistema cando a entidade de cliente se emparella con entidades adicionais para producir a entidade de perfil de cliente final.</span><span class="sxs-lookup"><span data-stu-id="8fb53-110">The following diagram illustrates the creation of three system relationships when the customer entity is matched with additional entities to produce the final Customer Profile entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="8fb53-111">![Creación de relacións](media/relationships-entities-merge.png "Creación de relacións")</span><span class="sxs-lookup"><span data-stu-id="8fb53-111">![Relationship creation](media/relationships-entities-merge.png "Relationship creation")</span></span>

- <span data-ttu-id="8fb53-112">A **relación *CustomerToContact*** creouse entre a entidade cliente e a entidade de contacto.</span><span class="sxs-lookup"><span data-stu-id="8fb53-112">***CustomerToContact* relationship** was created between the Customer entity and the Contact entity.</span></span> <span data-ttu-id="8fb53-113">A entidade de cliente recibe o campo clave **Contact_contactId** para relacionarse co campo clave da entidade de contacto **contactId**.</span><span class="sxs-lookup"><span data-stu-id="8fb53-113">The Customer entity gets the key field **Contact_contactId** to relate to the Contact entity key field **contactId**.</span></span>
- <span data-ttu-id="8fb53-114">A **relación _CustomerToAccount_** creouse entre a entidade cliente e a entidade da conta.</span><span class="sxs-lookup"><span data-stu-id="8fb53-114">**_CustomerToAccount_ relationship** was created between the Customer entity and the Account entity.</span></span> <span data-ttu-id="8fb53-115">A entidade de cliente recibe o campo clave **Account_accountId** para relacionarse co campo clave da entidade da conta **accountId**.</span><span class="sxs-lookup"><span data-stu-id="8fb53-115">The Customer entity gets the key field **Account_accountId** to relate to the Account entity key field **accountId**.</span></span>
- <span data-ttu-id="8fb53-116">A **relación _CustomerToWebAccount_** creouse entre a entidade cliente e a entidade WebAccount.</span><span class="sxs-lookup"><span data-stu-id="8fb53-116">**_CustomerToWebAccount_ relationship** was created between the Customer entity and the WebAccount entity.</span></span> <span data-ttu-id="8fb53-117">A entidade de cliente recibe o campo clave **WebAccount_webaccountId** para relacionarse co campo clave da entidade WebAccount **webaccountId**.</span><span class="sxs-lookup"><span data-stu-id="8fb53-117">The Customer entity gets the key field **WebAccount_webaccountId** to relate to the WebAccount entity key field **webaccountId**.</span></span>

## <a name="create-a-relationship"></a><span data-ttu-id="8fb53-118">Crear unha relación</span><span class="sxs-lookup"><span data-stu-id="8fb53-118">Create a relationship</span></span>

<span data-ttu-id="8fb53-119">Defina relacións personalizadas na páxina **Relacións**.</span><span class="sxs-lookup"><span data-stu-id="8fb53-119">Define custom relationships on the **Relationships** page.</span></span> <span data-ttu-id="8fb53-120">Cada relación está formada por unha entidade de Orixe (a entidade que ten a clave estranxeira) e unha entidade de Destino (a entidade á que apunta a clave estranxeira da entidade de orixe).</span><span class="sxs-lookup"><span data-stu-id="8fb53-120">Each relationship consists of a Source entity (the entity that holds the foreign key) and a Target entity (the entity that the source entity's foreign key points to).</span></span>

1. <span data-ttu-id="8fb53-121">Na información do público, vaia a **Datos** > **Relacións**.</span><span class="sxs-lookup"><span data-stu-id="8fb53-121">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="8fb53-122">Seleccione **Nova relación**.</span><span class="sxs-lookup"><span data-stu-id="8fb53-122">Select **New relationship**.</span></span>

3. <span data-ttu-id="8fb53-123">No panel **Engadir relación**, forneza a seguinte información:</span><span class="sxs-lookup"><span data-stu-id="8fb53-123">In the **Add relationship** pane, provide the following information:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="8fb53-124">![Insira os detalles da relación](media/relationships-add.png "Insira os detalles da relación")</span><span class="sxs-lookup"><span data-stu-id="8fb53-124">![Enter relationship details](media/relationships-add.png "Enter relationship details")</span></span>

   - <span data-ttu-id="8fb53-125">**Nome da relación**: nome que reflicte o propósito da relación (por exemplo, **AccountWebLogs**).</span><span class="sxs-lookup"><span data-stu-id="8fb53-125">**Relationship name**: Name that reflects the purpose of the relationship (for example, **AccountWebLogs**).</span></span>
   - <span data-ttu-id="8fb53-126">**Descrición**: descrición da relación.</span><span class="sxs-lookup"><span data-stu-id="8fb53-126">**Description**: Description of the relationship.</span></span>
   - <span data-ttu-id="8fb53-127">**Entidade de orixe**: seleccione a entidade que se emprega como orixe na relación (por exemplo, WebLog).</span><span class="sxs-lookup"><span data-stu-id="8fb53-127">**Source entity**: Select the entity that is used as a source in the relationship (for example, WebLog).</span></span>
   - <span data-ttu-id="8fb53-128">**Cardinalidade**: selecciona a cardinalidade dos rexistros de entidades de orixe.</span><span class="sxs-lookup"><span data-stu-id="8fb53-128">**Cardinality**: Select the cardinality of the source entity records.</span></span> <span data-ttu-id="8fb53-129">Por exemplo, "moitos" significa que varios rexistros de Weblog están relacionados cunha WebAccount.</span><span class="sxs-lookup"><span data-stu-id="8fb53-129">For example, "many" means that multiple Weblog records are related to one WebAccount.</span></span>
   - <span data-ttu-id="8fb53-130">**Campo clave de orixe**: representa o campo de clave estranxeiro na entidade de orixe.</span><span class="sxs-lookup"><span data-stu-id="8fb53-130">**Source key field**: This represents the foreign key field in the source entity.</span></span> <span data-ttu-id="8fb53-131">Por exemplo, WebLog ten o campo de clave estranxeiro **accountId**.</span><span class="sxs-lookup"><span data-stu-id="8fb53-131">For example, WebLog has the **accountId** foreign key field.</span></span>
   - <span data-ttu-id="8fb53-132">**Entidade de destino**: seleccione a entidade que se emprega como destino na relación (por exemplo, WebAccount).</span><span class="sxs-lookup"><span data-stu-id="8fb53-132">**Target entity**: Select the entity that is used as a target in the relationship (for example, WebAccount).</span></span>
   - <span data-ttu-id="8fb53-133">**Cardinalidade obxectivo**: seleccione a cardinalidade dos rexistros de entidades de destino.</span><span class="sxs-lookup"><span data-stu-id="8fb53-133">**Target cardinality**: Select the cardinality of the target entity records.</span></span> <span data-ttu-id="8fb53-134">Por exemplo, "un" significa que varios rexistros de Weblog están relacionados cunha WebAccount.</span><span class="sxs-lookup"><span data-stu-id="8fb53-134">For example, "one" means that multiple Weblog records are related to one WebAccount.</span></span>
   - <span data-ttu-id="8fb53-135">**Campo clave obxectivo**: este campo representa o campo clave da entidade de destino.</span><span class="sxs-lookup"><span data-stu-id="8fb53-135">**Target key field**: This field represents the key field of target entity.</span></span> <span data-ttu-id="8fb53-136">Por exemplo, WebAccount ten o campo de clave **accountId**.</span><span class="sxs-lookup"><span data-stu-id="8fb53-136">For example, WebAccount has the **accountId** key field.</span></span>

> [!NOTE]
> <span data-ttu-id="8fb53-137">Só se admiten relacións de moitos a un e dun a un.</span><span class="sxs-lookup"><span data-stu-id="8fb53-137">Only many-to-one and one-to-one relationships are supported.</span></span> <span data-ttu-id="8fb53-138">Pódense crear relacións de moitos a moitos empregando dúas relacións de moitos a un e unha entidade de ligazón (unha entidade que se usa para conectar a entidade de orixe e a entidade de destino).</span><span class="sxs-lookup"><span data-stu-id="8fb53-138">Many-to-many relationships can be created using two many-to-one relationships and a link entity (an entity that is used to connect the source entity and the target entity).</span></span>

## <a name="delete-a-relationship"></a><span data-ttu-id="8fb53-139">Eliminar unha relación</span><span class="sxs-lookup"><span data-stu-id="8fb53-139">Delete a relationship</span></span>

1. <span data-ttu-id="8fb53-140">Na información do público, vaia a **Datos** > **Relacións**.</span><span class="sxs-lookup"><span data-stu-id="8fb53-140">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="8fb53-141">Marque as caixas de verificación das relacións que desexe eliminar.</span><span class="sxs-lookup"><span data-stu-id="8fb53-141">Select check boxes for the relationships you want to delete.</span></span>

3. <span data-ttu-id="8fb53-142">Seleccione **Eliminar** na parte superior da táboa **Relacións**.</span><span class="sxs-lookup"><span data-stu-id="8fb53-142">Select **Delete** at the top of the **Relationships** table.</span></span>

4. <span data-ttu-id="8fb53-143">Confirme a eliminación.</span><span class="sxs-lookup"><span data-stu-id="8fb53-143">Confirm your deletion.</span></span>

## <a name="next-step"></a><span data-ttu-id="8fb53-144">Seguinte paso</span><span class="sxs-lookup"><span data-stu-id="8fb53-144">Next step</span></span>

<span data-ttu-id="8fb53-145">As relacións do sistema e personalizadas úsanse para crear segmentos baseados en varias orixes de datos que xa non están gardadas en silos.</span><span class="sxs-lookup"><span data-stu-id="8fb53-145">System and custom relationships are used to create segments based on multiple data sources that are no longer siloed.</span></span> <span data-ttu-id="8fb53-146">Para obter máis información, consulte [Segmentos](segments.md).</span><span class="sxs-lookup"><span data-stu-id="8fb53-146">For more information, see [Segments](segments.md).</span></span>
