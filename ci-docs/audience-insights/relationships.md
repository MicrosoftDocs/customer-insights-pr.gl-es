---
title: Relacións entre entidades e camiños das entidades
description: Cree e xestione relacións entre entidades a partir de varias fontes de datos.
ms.date: 06/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: d5b9566ec88096fec31d8e164a51598159ec26d4
ms.sourcegitcommit: ece48f80a7b470fb33cd36e3096b4f1e9190433a
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 06/03/2021
ms.locfileid: "6171162"
---
# <a name="relationships-between-entities"></a><span data-ttu-id="c5ddc-103">Relacións entre entidades</span><span class="sxs-lookup"><span data-stu-id="c5ddc-103">Relationships between entities</span></span>

<span data-ttu-id="c5ddc-104">As relacións conectan entidades e definen un gráfico dos seus datos cando as entidades comparten un identificador común, unha clave externa.</span><span class="sxs-lookup"><span data-stu-id="c5ddc-104">Relationships connect entities and define a graph of your data when entities share a common identifier, a foreign key.</span></span> <span data-ttu-id="c5ddc-105">A esta clave externa pódese facer referencia desde unha entidade a outra.</span><span class="sxs-lookup"><span data-stu-id="c5ddc-105">This foreign key can be referenced from one entity to another.</span></span> <span data-ttu-id="c5ddc-106">As entidades conectadas permiten a definición de segmentos e medidas en función de varias orixes de datos.</span><span class="sxs-lookup"><span data-stu-id="c5ddc-106">Connected entities enable the definition of segments and measures based on multiple data sources.</span></span>

<span data-ttu-id="c5ddc-107">Hai tres tipos de relacións:</span><span class="sxs-lookup"><span data-stu-id="c5ddc-107">There are three types of relationships:</span></span> 
- <span data-ttu-id="c5ddc-108">Relacións do sistema non editables, creadas polo sistema como parte do proceso de unificación de datos</span><span class="sxs-lookup"><span data-stu-id="c5ddc-108">Non-editable system relationships, created by the system as part of the data unification process</span></span>
- <span data-ttu-id="c5ddc-109">Relacións herdadas non editables, que se crean automaticamente a partir da inxestión de orixes de datos</span><span class="sxs-lookup"><span data-stu-id="c5ddc-109">Non-editable inherited relationships, which are created automatically from ingesting data sources</span></span> 
- <span data-ttu-id="c5ddc-110">Relacións personalizadas editables, creadas e configuradas polos usuarios</span><span class="sxs-lookup"><span data-stu-id="c5ddc-110">Editable custom relationships, created and configured by users</span></span>

## <a name="non-editable-system-relationships"></a><span data-ttu-id="c5ddc-111">Relacións do sistema non editables</span><span class="sxs-lookup"><span data-stu-id="c5ddc-111">Non-editable system relationships</span></span>

<span data-ttu-id="c5ddc-112">Durante a unificación de datos, as relacións do sistema créanse automaticamente baseándose en coincidencias intelixentes.</span><span class="sxs-lookup"><span data-stu-id="c5ddc-112">During data unification, system relationships are created automatically based on intelligent matching.</span></span> <span data-ttu-id="c5ddc-113">Estas relacións axudan a relacionar os rexistros do perfil de cliente cos correspondentes rexistros.</span><span class="sxs-lookup"><span data-stu-id="c5ddc-113">These relationships help relate the customer profile records with corresponding records.</span></span> <span data-ttu-id="c5ddc-114">O seguinte diagrama ilustra a creación de tres relacións baseadas no sistema.</span><span class="sxs-lookup"><span data-stu-id="c5ddc-114">The following diagram illustrates the creation of three system-based relationships.</span></span> <span data-ttu-id="c5ddc-115">A entidade de cliente coincide con outras entidades para producir a entidade *Cliente* unificada.</span><span class="sxs-lookup"><span data-stu-id="c5ddc-115">The customer entity is matched with other entities to produce the unified *Customer* entity.</span></span>

:::image type="content" source="media/relationships-entities-merge.png" alt-text="Diagrama con camiños de relacións para a entidade de cliente con tres relacións 1-N.":::

- <span data-ttu-id="c5ddc-117">**A relación *CustomerToContact*** creouse entre a entidade *Cliente* e a entidade de *contacto*.</span><span class="sxs-lookup"><span data-stu-id="c5ddc-117">***CustomerToContact* relationship** was created between the *Customer* entity and the *Contact* entity.</span></span> <span data-ttu-id="c5ddc-118">A entidade *Cliente* recibe o campo clave **Contact_contactID** para relacionarse co campo clave da entidade de *contacto* **contactID**.</span><span class="sxs-lookup"><span data-stu-id="c5ddc-118">The *Customer* entity gets the key field **Contact_contactID** to relate to the *Contact* entity key field **contactID**.</span></span>
- <span data-ttu-id="c5ddc-119">**A relación *CustomerToAccount*** creouse entre a entidade *Cliente* e a entidade da *conta*.</span><span class="sxs-lookup"><span data-stu-id="c5ddc-119">***CustomerToAccount* relationship** was created between the *Customer* entity and the *Account* entity.</span></span> <span data-ttu-id="c5ddc-120">A entidade *Cliente* recibe o campo clave **Account_accountID** para relacionarse co campo clave da entidade da *conta* **accountID**.</span><span class="sxs-lookup"><span data-stu-id="c5ddc-120">The *Customer* entity gets the key field **Account_accountID** to relate to the *Account* entity key field **accountID**.</span></span>
- <span data-ttu-id="c5ddc-121">**A relación *CustomerToWebAccount*** creouse entre a entidade *Cliente* e a entidade *WebAccount*.</span><span class="sxs-lookup"><span data-stu-id="c5ddc-121">***CustomerToWebAccount* relationship** was created between the *Customer* entity and the *WebAccount* entity.</span></span> <span data-ttu-id="c5ddc-122">A entidade *Cliente* recibe o campo clave **WebAccount_webaccountID** para relacionarse co campo clave da entidade *WebAccount* **webaccountID**.</span><span class="sxs-lookup"><span data-stu-id="c5ddc-122">The *Customer* entity gets the key field **WebAccount_webaccountID** to relate to the *WebAccount* entity key field **webaccountID**.</span></span>

## <a name="non-editable-inherited-relationships"></a><span data-ttu-id="c5ddc-123">Relacións herdadas non editables</span><span class="sxs-lookup"><span data-stu-id="c5ddc-123">Non-editable inherited relationships</span></span>

<span data-ttu-id="c5ddc-124">Durante o proceso de inxestión de datos, o sistema comproba as orixes de datos para as relacións existentes.</span><span class="sxs-lookup"><span data-stu-id="c5ddc-124">During the data ingestion process, the system checks data sources for existing relationships.</span></span> <span data-ttu-id="c5ddc-125">Se non existe ningunha relación, o sistema créaas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="c5ddc-125">If no relationship exists, the system automatically creates them.</span></span> <span data-ttu-id="c5ddc-126">Estas relacións úsanse tamén en procesos descendentes.</span><span class="sxs-lookup"><span data-stu-id="c5ddc-126">These relationships are also used in downstream processes.</span></span>

## <a name="create-a-custom-relationship"></a><span data-ttu-id="c5ddc-127">Crear unha relación personalizada</span><span class="sxs-lookup"><span data-stu-id="c5ddc-127">Create a custom relationship</span></span>

<span data-ttu-id="c5ddc-128">Unha relación consiste nunha *entidade de orixe* que contén a clave externa e a *entidade de destino* á que apunta a clave externa da entidade de orixe.</span><span class="sxs-lookup"><span data-stu-id="c5ddc-128">Relationship consists of a *source entity* containing the foreign key and a *target entity* that the source entity's foreign key points to.</span></span> 

1. <span data-ttu-id="c5ddc-129">Na información do público, vaia a **Datos** > **Relacións**.</span><span class="sxs-lookup"><span data-stu-id="c5ddc-129">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="c5ddc-130">Seleccione **Nova relación**.</span><span class="sxs-lookup"><span data-stu-id="c5ddc-130">Select **New relationship**.</span></span>

3. <span data-ttu-id="c5ddc-131">No panel **Nova relación**, forneza a seguinte información:</span><span class="sxs-lookup"><span data-stu-id="c5ddc-131">In the **New relationship** pane, provide the following information:</span></span>

   :::image type="content" source="media/relationship-add.png" alt-text="Panel lateral Nova relación con campos de entrada baleiros.":::

   - <span data-ttu-id="c5ddc-133">**Nome da relación**: nome que reflicte o propósito da relación.</span><span class="sxs-lookup"><span data-stu-id="c5ddc-133">**Relationship name**: Name that reflects the purpose of the relationship.</span></span> <span data-ttu-id="c5ddc-134">Exemplo: CustomerToSupportCase.</span><span class="sxs-lookup"><span data-stu-id="c5ddc-134">Example: CustomerToSupportCase.</span></span>
   - <span data-ttu-id="c5ddc-135">**Descrición**: descrición da relación.</span><span class="sxs-lookup"><span data-stu-id="c5ddc-135">**Description**: Description of the relationship.</span></span>
   - <span data-ttu-id="c5ddc-136">**Entidade de orixe**: entidade que se usa como orixe na relación.</span><span class="sxs-lookup"><span data-stu-id="c5ddc-136">**Source entity**: Entity that is used as a source in the relationship.</span></span> <span data-ttu-id="c5ddc-137">Exemplo: SupportCase.</span><span class="sxs-lookup"><span data-stu-id="c5ddc-137">Example: SupportCase.</span></span>
   - <span data-ttu-id="c5ddc-138">**Entidade de destino**: entidade que se usa como destino na relación.</span><span class="sxs-lookup"><span data-stu-id="c5ddc-138">**Target entity**: Entity that is used as a target in the relationship.</span></span> <span data-ttu-id="c5ddc-139">Exemplo: Cliente.</span><span class="sxs-lookup"><span data-stu-id="c5ddc-139">Example: Customer.</span></span>
   - <span data-ttu-id="c5ddc-140">**Cardinalidade de orixe**: especifique a cardinalidade da entidade de orixe.</span><span class="sxs-lookup"><span data-stu-id="c5ddc-140">**Source cardinality**: Specify the cardinality of the source entity.</span></span> <span data-ttu-id="c5ddc-141">A cardinalidade describe o número de elementos posibles nun conxunto.</span><span class="sxs-lookup"><span data-stu-id="c5ddc-141">Cardinality describes the number of possible elements in a set.</span></span> <span data-ttu-id="c5ddc-142">Sempre se relaciona coa cardinalidade de destino.</span><span class="sxs-lookup"><span data-stu-id="c5ddc-142">It always relates to the target cardinality.</span></span> <span data-ttu-id="c5ddc-143">Pode escoller entre **Un** e **Moitos**.</span><span class="sxs-lookup"><span data-stu-id="c5ddc-143">You can choose between **One** and **Many**.</span></span> <span data-ttu-id="c5ddc-144">Só se admiten relacións de moitos a un e dun a un.</span><span class="sxs-lookup"><span data-stu-id="c5ddc-144">Only many-to-one and one-to-one relationships are supported.</span></span>  
     - <span data-ttu-id="c5ddc-145">Moitos a un: varios rexistros de orixe poden relacionarse cun rexistro de destino.</span><span class="sxs-lookup"><span data-stu-id="c5ddc-145">Many-to-one: Multiple source records can relate to one target record.</span></span> <span data-ttu-id="c5ddc-146">Exemplo: varios casos de asistencia técnica dun único cliente.</span><span class="sxs-lookup"><span data-stu-id="c5ddc-146">Example: Multiple support cases from a single customer.</span></span>
     - <span data-ttu-id="c5ddc-147">Un a un: un único rexistro de orixe relaciónase cun rexistro de destino.</span><span class="sxs-lookup"><span data-stu-id="c5ddc-147">One-to-one: A single source record relates to a one target record.</span></span> <span data-ttu-id="c5ddc-148">Exemplo: un ID de fidelidade para un único cliente.</span><span class="sxs-lookup"><span data-stu-id="c5ddc-148">Example: One loyalty ID for a single customer.</span></span>

     > [!NOTE]
     > <span data-ttu-id="c5ddc-149">Pódense crear relacións de moitos a moitos usando dúas relacións de moitos a un e unha entidade de ligazón, que conecta a entidade de orixe e a entidade de destino.</span><span class="sxs-lookup"><span data-stu-id="c5ddc-149">Many-to-many relationships can be created using two many-to-one relationships and a linking entity, which connects the source entity and the target entity.</span></span>

   - <span data-ttu-id="c5ddc-150">**Cardinalidade obxectivo**: seleccione a cardinalidade dos rexistros de entidades de destino.</span><span class="sxs-lookup"><span data-stu-id="c5ddc-150">**Target cardinality**: Select the cardinality of the target entity records.</span></span> 
   - <span data-ttu-id="c5ddc-151">**Campo da clave de orixe**: o campo de clave externa na entidade de orixe.</span><span class="sxs-lookup"><span data-stu-id="c5ddc-151">**Source key field**: The foreign key field in the source entity.</span></span> <span data-ttu-id="c5ddc-152">Exemplo: SupportCase podería usar CaseID como campo de clave externa.</span><span class="sxs-lookup"><span data-stu-id="c5ddc-152">Example: SupportCase could use CaseID as a foreign key field.</span></span>
   - <span data-ttu-id="c5ddc-153">**Campo da clave obxectivo**: o campo da clave da entidade de destino.</span><span class="sxs-lookup"><span data-stu-id="c5ddc-153">**Target key field**: The key field of the target entity.</span></span> <span data-ttu-id="c5ddc-154">Exemplo: o cliente podería usar o campo da clave **CustomerID**.</span><span class="sxs-lookup"><span data-stu-id="c5ddc-154">Example Customer could use the **CustomerID** key field.</span></span>

4. <span data-ttu-id="c5ddc-155">Seleccione **Gardar** para crear a relación personalizada.</span><span class="sxs-lookup"><span data-stu-id="c5ddc-155">Select **Save** to create the custom relationship.</span></span>

## <a name="view-relationships"></a><span data-ttu-id="c5ddc-156">Ver relacións</span><span class="sxs-lookup"><span data-stu-id="c5ddc-156">View relationships</span></span>

<span data-ttu-id="c5ddc-157">A páxina Relacións enumera todas as relacións que se crearon.</span><span class="sxs-lookup"><span data-stu-id="c5ddc-157">The Relationships page lists all the relationships that have been created.</span></span> <span data-ttu-id="c5ddc-158">Cada fila representa unha relación, que tamén inclúe detalles sobre a entidade de orixe, a entidade de destino e a cardinalidade.</span><span class="sxs-lookup"><span data-stu-id="c5ddc-158">Each row represents a relationship, which also includes details about the source entity, the target entity, and the cardinality.</span></span> 

:::image type="content" source="media/relationships-list.png" alt-text="Lista de relacións e opcións na barra de acción da páxina Relacións.":::

<span data-ttu-id="c5ddc-160">Esta páxina ofrece un conxunto de opcións para as relacións novas e existentes:</span><span class="sxs-lookup"><span data-stu-id="c5ddc-160">This page offers a set of options for existing and new relationships:</span></span> 
- <span data-ttu-id="c5ddc-161">**Nova relación**: [cree unha relación personalizada](#create-a-custom-relationship).</span><span class="sxs-lookup"><span data-stu-id="c5ddc-161">**New Relationship**: [Create a custom relationship](#create-a-custom-relationship).</span></span>
- <span data-ttu-id="c5ddc-162">**Visualizador**: [explore o visualizador de relacións](#explore-the-relationship-visualizer) para ver un diagrama de rede das relacións existentes e a súa cardinalidade.</span><span class="sxs-lookup"><span data-stu-id="c5ddc-162">**Visualizer**: [Explore the relationship visualizer](#explore-the-relationship-visualizer) to see a network diagram of the existing relationships and their cardinality.</span></span>
- <span data-ttu-id="c5ddc-163">**Filtrar por**: elixa o tipo de relacións que se amosarán na lista.</span><span class="sxs-lookup"><span data-stu-id="c5ddc-163">**Filter by**: Choose the type of relationships to show in the list.</span></span>
- <span data-ttu-id="c5ddc-164">**Buscar relacións**: use unha busca baseada en texto sobre as propiedades das relacións.</span><span class="sxs-lookup"><span data-stu-id="c5ddc-164">**Search relationships**: Use a text-based search on properties of the relationships.</span></span>

### <a name="explore-the-relationship-visualizer"></a><span data-ttu-id="c5ddc-165">Explorar o visualizador de relacións</span><span class="sxs-lookup"><span data-stu-id="c5ddc-165">Explore the relationship visualizer</span></span>

<span data-ttu-id="c5ddc-166">O visualizador de relacións mostra un diagrama de rede das relacións existentes entre as entidades conectadas e a súa cardinalidade.</span><span class="sxs-lookup"><span data-stu-id="c5ddc-166">The relationship visualizer shows a network diagram of the existing relationships between connected entities and their cardinality.</span></span>

<span data-ttu-id="c5ddc-167">Para personalizar a vista, pode cambiar a posición das caixas arrastrándoas sobre o lenzo.</span><span class="sxs-lookup"><span data-stu-id="c5ddc-167">To customize the view, you can change the position of the boxes by dragging them on the canvas.</span></span>

:::image type="content" source="media/relationship-visualizer.png" alt-text="Captura de pantalla do diagrama de rede do visualizador de relacións con conexións entre entidades relacionadas.":::

<span data-ttu-id="c5ddc-169">Opcións dispoñibles:</span><span class="sxs-lookup"><span data-stu-id="c5ddc-169">Available options:</span></span> 
- <span data-ttu-id="c5ddc-170">**Exportar como imaxe**: garde a vista actual como un ficheiro de imaxe.</span><span class="sxs-lookup"><span data-stu-id="c5ddc-170">**Export as image**: Save the current view as an image file.</span></span>
- <span data-ttu-id="c5ddc-171">**Cambiar a deseño horizontal ou vertical**: cambie o aliñamento das entidades e das relacións.</span><span class="sxs-lookup"><span data-stu-id="c5ddc-171">**Change to horizontal/vertical layout**: Change the alignment of the entities and relationships.</span></span>
- <span data-ttu-id="c5ddc-172">**Editar**: actualice as propiedades das relacións personalizadas no panel de edición e garde os cambios.</span><span class="sxs-lookup"><span data-stu-id="c5ddc-172">**Edit**: Update properties of custom relationships in the edit pane and save changes.</span></span>

## <a name="manage-existing-relationships"></a><span data-ttu-id="c5ddc-173">Xestionar relacións existentes</span><span class="sxs-lookup"><span data-stu-id="c5ddc-173">Manage existing relationships</span></span> 

<span data-ttu-id="c5ddc-174">Na páxina Relacións, cada relación está representada por unha fila.</span><span class="sxs-lookup"><span data-stu-id="c5ddc-174">On the Relationships page, each relationship is represented by a row.</span></span> 

<span data-ttu-id="c5ddc-175">Seleccione unha relación e elixa unha das seguintes opcións:</span><span class="sxs-lookup"><span data-stu-id="c5ddc-175">Select a relationship and choose one of the following options:</span></span> 
 
- <span data-ttu-id="c5ddc-176">**Editar**: actualice as propiedades das relacións personalizadas no panel de edición e garde os cambios.</span><span class="sxs-lookup"><span data-stu-id="c5ddc-176">**Edit**: Update properties of custom relationships in the edit pane and save changes.</span></span>
- <span data-ttu-id="c5ddc-177">**Eliminar**: elimine relacións personalizadas.</span><span class="sxs-lookup"><span data-stu-id="c5ddc-177">**Delete**: Delete custom relationships.</span></span>
- <span data-ttu-id="c5ddc-178">**Ver**: vexa as relacións creadas polo sistema e herdadas.</span><span class="sxs-lookup"><span data-stu-id="c5ddc-178">**View**: View system-created and inherited relationships.</span></span> 

## <a name="next-step"></a><span data-ttu-id="c5ddc-179">Seguinte paso</span><span class="sxs-lookup"><span data-stu-id="c5ddc-179">Next step</span></span>

<span data-ttu-id="c5ddc-180">As relacións do sistema e personalizadas úsanse para [crear segmentos](segments.md) baseados en varias orixes de datos que xa non están gardadas en silos.</span><span class="sxs-lookup"><span data-stu-id="c5ddc-180">System and custom relationships are used to [create segments](segments.md) based on multiple data sources that are no longer siloed.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
