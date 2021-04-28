---
title: Conexións a outros servizos de Customer Insights.
description: Comparta datos con outros servizos.
ms.date: 04/09/2021
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 106dbc26f95b309821d738e1484b1eaa79dd225b
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896095"
---
# <a name="connections-preview-overview"></a><span data-ttu-id="8d0ec-103">Visión xeral de conexións (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="8d0ec-103">Connections (preview) overview</span></span>

<span data-ttu-id="8d0ec-104">As conexións son a clave para permitir o intercambio de datos desde e ata Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="8d0ec-104">Connections are the key to enable data sharing to and from Customer Insights.</span></span> <span data-ttu-id="8d0ec-105">Cada conexión establece o uso compartido de datos cun servizo específico.</span><span class="sxs-lookup"><span data-stu-id="8d0ec-105">Each connection establishes data sharing with a specific service.</span></span> <span data-ttu-id="8d0ec-106">As conexións son a base para [configurar enriquecementos de terceiros](enrichment-hub.md) e [configurar as exportacións](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="8d0ec-106">Connections are the foundation to [configure third-party enrichments](enrichment-hub.md) and [configure exports](export-destinations.md).</span></span> <span data-ttu-id="8d0ec-107">A mesma conexión pódese usar varias veces.</span><span class="sxs-lookup"><span data-stu-id="8d0ec-107">The same connection can be used multiple times.</span></span> <span data-ttu-id="8d0ec-108">Por exemplo, unha conexión a Dynamics 365 Marketing funciona para exportacións múltiples e unha conexión de Leadspace pode usarse para varios enriquecementos.</span><span class="sxs-lookup"><span data-stu-id="8d0ec-108">For example, one connection to Dynamics 365 Marketing works for multiple exports and one Leadspace connection can be used for several enrichments.</span></span>

<span data-ttu-id="8d0ec-109">Vaia a **Administrar** > **Conexións** para crear e ver conexións.</span><span class="sxs-lookup"><span data-stu-id="8d0ec-109">Go to **Admin** > **Connections** to create and view connections.</span></span>

<span data-ttu-id="8d0ec-110">O separador **Conexións** mostra todas as conexións activas.</span><span class="sxs-lookup"><span data-stu-id="8d0ec-110">The **Connections** tab shows you all active connections.</span></span> <span data-ttu-id="8d0ec-111">A lista mostra unha fila para cada conexión.</span><span class="sxs-lookup"><span data-stu-id="8d0ec-111">The list shows a row for each connection.</span></span> 

<span data-ttu-id="8d0ec-112">Obteña unha visión xeral rápida, descrición e descubra o que pode facer con cada opción de extensibilidade no separador **Descubrir**.</span><span class="sxs-lookup"><span data-stu-id="8d0ec-112">Get a quick overview, description, and find out what you can do with each extensibility option on the **Discover** tab.</span></span>

### <a name="exports"></a><span data-ttu-id="8d0ec-113">Exportacións</span><span class="sxs-lookup"><span data-stu-id="8d0ec-113">Exports</span></span>

<span data-ttu-id="8d0ec-114">Só os administradores poden configurar novas conexións, pero poden conceder acceso aos colaboradores para que empreguen as conexións existentes.</span><span class="sxs-lookup"><span data-stu-id="8d0ec-114">Only administrators can configure new connections but they can grant access to contributors to use existing connections.</span></span> <span data-ttu-id="8d0ec-115">Os administradores controlan onde poden ir os datos, os colaboradores definen a carga útil e a frecuencia que se axustan ás súas necesidades.</span><span class="sxs-lookup"><span data-stu-id="8d0ec-115">Administrators control where data can go, contributors define the payload and frequency fitting their needs.</span></span> <span data-ttu-id="8d0ec-116">Para obter máis información, consulte [Permitir aos colaboradores usar unha conexión para as exportacións](#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="8d0ec-116">For more information, see [Allow contributors to use a connection for exports](#allow-contributors-to-use-a-connection-for-exports).</span></span>

### <a name="enrichments"></a><span data-ttu-id="8d0ec-117">Enriquecementos</span><span class="sxs-lookup"><span data-stu-id="8d0ec-117">Enrichments</span></span>

<span data-ttu-id="8d0ec-118">Só os administradores poden configurar novas conexións, pero as conexións creadas están sempre dispoñibles tanto para administradores como para colaboradores.</span><span class="sxs-lookup"><span data-stu-id="8d0ec-118">Only administrators can configure new connections but the created connections are always available to both administrators and contributors.</span></span> <span data-ttu-id="8d0ec-119">Os administradores xestionan as credenciais e consenten as transferencias de datos.</span><span class="sxs-lookup"><span data-stu-id="8d0ec-119">Administrators manage credentials and give consent to data transfers.</span></span> <span data-ttu-id="8d0ec-120">As conexións poden ser usadas para enriquecementos por administradores e colaboradores.</span><span class="sxs-lookup"><span data-stu-id="8d0ec-120">The connections can then be used for enrichments by both administrators and contributors.</span></span>

## <a name="add-a-new-connection"></a><span data-ttu-id="8d0ec-121">Engadir unha nova conexión</span><span class="sxs-lookup"><span data-stu-id="8d0ec-121">Add a new connection</span></span>

<span data-ttu-id="8d0ec-122">Para engadir conexións, cómpre ter [permisos de administrador](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="8d0ec-122">To add connections, you need to have [administrator permissions](permissions.md).</span></span> <span data-ttu-id="8d0ec-123">Se se conecta a outros servizos de Microsoft, supoñemos que ambos os servizos están na mesma organización.</span><span class="sxs-lookup"><span data-stu-id="8d0ec-123">If you connect to other Microsoft services, we assume both services are in the same organization.</span></span>

1. <span data-ttu-id="8d0ec-124">Vaia a **Administrar** > **Conexións (versión preliminar)**.</span><span class="sxs-lookup"><span data-stu-id="8d0ec-124">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="8d0ec-125">Vaia ao separador **Conexións**.</span><span class="sxs-lookup"><span data-stu-id="8d0ec-125">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="8d0ec-126">Seleccione **Engadir conexión** para crear unha nova conexión.</span><span class="sxs-lookup"><span data-stu-id="8d0ec-126">Select **Add connection** to create a new connection.</span></span> <span data-ttu-id="8d0ec-127">Escolla no menú despregable que tipo de conexión quere crear.</span><span class="sxs-lookup"><span data-stu-id="8d0ec-127">Choose from the drop-down menu what type of connection you want to create.</span></span>

1. <span data-ttu-id="8d0ec-128">No panel **Configurar a conexión**, proporcione os detalles requiridos.</span><span class="sxs-lookup"><span data-stu-id="8d0ec-128">In the **Set up connection** pane, provide the required details.</span></span> 
   1. <span data-ttu-id="8d0ec-129">O **Nome de visualización** e o tipo de conexión describen unha conexión.</span><span class="sxs-lookup"><span data-stu-id="8d0ec-129">The **Display name** and the type of the connection describe a connection.</span></span> <span data-ttu-id="8d0ec-130">Recomendamos escoller un nome que explique o propósito e o destino desta conexión.</span><span class="sxs-lookup"><span data-stu-id="8d0ec-130">We recommend choosing a name that explains the purpose and target of this connection.</span></span>
   1. <span data-ttu-id="8d0ec-131">Os campos exactos dependen do servizo ao que se conecte.</span><span class="sxs-lookup"><span data-stu-id="8d0ec-131">The exact fields depend on what service you are connecting to.</span></span> <span data-ttu-id="8d0ec-132">Pode coñecer os detalles dun tipo de conexión específico no artigo sobre o servizo de destino.</span><span class="sxs-lookup"><span data-stu-id="8d0ec-132">You can learn about details of a specific connection type in the article about the target service.</span></span>

1. <span data-ttu-id="8d0ec-133">Seleccione **Gardar** para crear a conexión.</span><span class="sxs-lookup"><span data-stu-id="8d0ec-133">To create the connection, select **Save**.</span></span>

<span data-ttu-id="8d0ec-134">Tamén pode seleccionar **Configurar** nun mosaico do separador **Descubrir**.</span><span class="sxs-lookup"><span data-stu-id="8d0ec-134">You can also select **Set up** on a tile on the **Discover** tab.</span></span>

### <a name="allow-contributors-to-use-a-connection-for-exports"></a><span data-ttu-id="8d0ec-135">Permitir aos colaboradores usar unha conexión para exportacións</span><span class="sxs-lookup"><span data-stu-id="8d0ec-135">Allow contributors to use a connection for exports</span></span>

<span data-ttu-id="8d0ec-136">Ao configurar ou editar unha conexión de exportación, elixa aos usuarios que poden usar esta conexión específica para definir [exportacións](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="8d0ec-136">When setting up or editing an export connection, you choose which users are allowed to use this specific connection to define [exports](export-destinations.md).</span></span> <span data-ttu-id="8d0ec-137">De xeito predeterminado, hai unha conexión dispoñible para usuarios con función de administrador.</span><span class="sxs-lookup"><span data-stu-id="8d0ec-137">By default a connection is available to users with an administrator role.</span></span> <span data-ttu-id="8d0ec-138">Pode cambiar esta configuración en **Escoller quen pode usar esta conexión** e permitir aos usuarios con función de colaborador usar esta conexión.</span><span class="sxs-lookup"><span data-stu-id="8d0ec-138">You can change this setting under **Choose who can use this connection** and allow users with contributor role to use this connection.</span></span>

- <span data-ttu-id="8d0ec-139">Os colaboradores non poderán ver nin editar a conexión.</span><span class="sxs-lookup"><span data-stu-id="8d0ec-139">Contributors won't be able to view or edit the connection.</span></span> <span data-ttu-id="8d0ec-140">Só verán o nome de visualización e o seu tipo ao crear unha exportación.</span><span class="sxs-lookup"><span data-stu-id="8d0ec-140">They will only see the display name and its type when creating an export.</span></span>
- <span data-ttu-id="8d0ec-141">Ao compartir unha conexión, permítelle aos colaboradores usar unha conexión.</span><span class="sxs-lookup"><span data-stu-id="8d0ec-141">By sharing a connection, you allow contributors to use a connection.</span></span> <span data-ttu-id="8d0ec-142">Os colaboradores verán as conexións compartidas cando configuren as exportacións.</span><span class="sxs-lookup"><span data-stu-id="8d0ec-142">Contributors will see shared connections when they set up exports.</span></span> <span data-ttu-id="8d0ec-143">Poden xestionar todas as exportacións que utilizan esta conexión específica.</span><span class="sxs-lookup"><span data-stu-id="8d0ec-143">They can manage every export that uses this specific connection.</span></span>
- <span data-ttu-id="8d0ec-144">Pode cambiar esta configuración mantendo as exportacións que xa foron definidas polos colaboradores.</span><span class="sxs-lookup"><span data-stu-id="8d0ec-144">You can change this setting while keeping the exports that have already been defined by contributors.</span></span>

## <a name="edit-a-connection"></a><span data-ttu-id="8d0ec-145">Editar unha conexión</span><span class="sxs-lookup"><span data-stu-id="8d0ec-145">Edit a connection</span></span>

1. <span data-ttu-id="8d0ec-146">Vaia a **Administrar** > **Conexións (versión preliminar)**.</span><span class="sxs-lookup"><span data-stu-id="8d0ec-146">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="8d0ec-147">Vaia ao separador **Conexións**.</span><span class="sxs-lookup"><span data-stu-id="8d0ec-147">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="8d0ec-148">Seleccione os tres puntos verticais para a conexión que desexa editar.</span><span class="sxs-lookup"><span data-stu-id="8d0ec-148">Select the vertical ellipsis for the connection you want to edit.</span></span>

1. <span data-ttu-id="8d0ec-149">Seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="8d0ec-149">Select **Edit**.</span></span>

1. <span data-ttu-id="8d0ec-150">Cambie os valores que desexa actualizar e seccione **Gardar**.</span><span class="sxs-lookup"><span data-stu-id="8d0ec-150">Change the values you want to update and select **Save**.</span></span>

## <a name="remove-a-connection"></a><span data-ttu-id="8d0ec-151">Eliminar unha conexión</span><span class="sxs-lookup"><span data-stu-id="8d0ec-151">Remove a connection</span></span>

<span data-ttu-id="8d0ec-152">Se a conexión que vai eliminar é utilizada por enriquecementos ou exportacións, primeiro cómpre desprendela ou eliminala.</span><span class="sxs-lookup"><span data-stu-id="8d0ec-152">If the connection you are removing is used by enrichments or exports, you first need to detach or remove them.</span></span> <span data-ttu-id="8d0ec-153">O diálogo de eliminación guiarao aos enriquecementos ou exportacións relevantes.</span><span class="sxs-lookup"><span data-stu-id="8d0ec-153">The remove dialog will guide you to the relevant enrichments or exports.</span></span> <span data-ttu-id="8d0ec-154">Os enriquecementos e exportacións desconectados quedan inactivos.</span><span class="sxs-lookup"><span data-stu-id="8d0ec-154">Detached enrichments and exports become inactive.</span></span> <span data-ttu-id="8d0ec-155">Reactíveos engadíndolles outra conexión na páxina [Enriquecementos](enrichment-hub.md) ou [Exportacións](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="8d0ec-155">You reactivate them by adding another connection to them on the [Enrichments](enrichment-hub.md) or [Exports](export-destinations.md) page.</span></span>

1. <span data-ttu-id="8d0ec-156">Vaia a **Administrar** > **Conexións (versión preliminar)**.</span><span class="sxs-lookup"><span data-stu-id="8d0ec-156">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="8d0ec-157">Vaia ao separador **Conexións**.</span><span class="sxs-lookup"><span data-stu-id="8d0ec-157">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="8d0ec-158">Seleccione os tres puntos verticais para a conexión que desexa eliminar.</span><span class="sxs-lookup"><span data-stu-id="8d0ec-158">Select the vertical ellipsis for the connection you want to remove.</span></span>

1. <span data-ttu-id="8d0ec-159">Seleccione **Eliminar** do menú despregable.</span><span class="sxs-lookup"><span data-stu-id="8d0ec-159">Select **Remove** from the dropdown menu.</span></span> <span data-ttu-id="8d0ec-160">Aparecerá un diálogo de confirmación.</span><span class="sxs-lookup"><span data-stu-id="8d0ec-160">A confirmation dialog appears.</span></span>

   1. <span data-ttu-id="8d0ec-161">Se hai enriquecementos ou exportacións usando esta conexión, seleccione o botón para ver que está a usar a conexión.</span><span class="sxs-lookup"><span data-stu-id="8d0ec-161">If there are enrichments or exports using this connection, select the button to see what's using the connection.</span></span>
      - <span data-ttu-id="8d0ec-162">**Exportacións:** Pode eliminar ou desconectar as exportacións para poder eliminar a conexión.</span><span class="sxs-lookup"><span data-stu-id="8d0ec-162">**Exports:** You can choose to either remove or disconnect the exports to be able to remove the connection.</span></span> <span data-ttu-id="8d0ec-163">Para desconectar unha exportación, os administradores poden usar a acción **Desconectar**.</span><span class="sxs-lookup"><span data-stu-id="8d0ec-163">To disconnect an export, administrators can use the **Disconnect** action.</span></span> <span data-ttu-id="8d0ec-164">Esta acción está dispoñible para exportacións individuais e múltiples seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="8d0ec-164">This action is available for individual and multiple selected exports.</span></span> <span data-ttu-id="8d0ec-165">Ao desconectar manterá a configuración de exportación, pero non se executará ata que se lle engada outra conexión.</span><span class="sxs-lookup"><span data-stu-id="8d0ec-165">By disconnecting you keep the export config, but it won't be run until another connection is added to it.</span></span>
      - <span data-ttu-id="8d0ec-166">**Enriquecementos:** Pode eliminar ou desactivar os enriquecementos para poder eliminar a conexión.</span><span class="sxs-lookup"><span data-stu-id="8d0ec-166">**Enrichments:** You can choose to either remove or deactivate the enrichments to be able to remove the connection.</span></span> 
   1. <span data-ttu-id="8d0ec-167">Unha vez que a conexión non teña máis dependencias, volva a **Administrar** > **Conexións** e tente eliminar de novo a conexión.</span><span class="sxs-lookup"><span data-stu-id="8d0ec-167">Once the connection has no more dependencies, go back to **Admin** > **Connections** and try removing the connection again.</span></span>

1. <span data-ttu-id="8d0ec-168">Para confirmar a eliminación seleccione **Quitar**.</span><span class="sxs-lookup"><span data-stu-id="8d0ec-168">To confirm the deletion select **Remove**.</span></span>

