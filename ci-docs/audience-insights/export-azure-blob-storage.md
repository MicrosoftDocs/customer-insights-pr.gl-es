---
title: Exportar datos de Customer Insights a un Azure Blob Storage
description: Aprenda a configurar a conexión e exportar ao almacenamento de BLOB.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3c19dc6d4956a33a5bd3cea706f8a154198d487f
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976132"
---
# <a name="export-segment-list-and-other-data-to-azure-blob-storage-preview"></a><span data-ttu-id="05393-103">Exportar lista de segmentos e outros datos a Azure Blob Storage (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="05393-103">Export segment list and other data to Azure Blob Storage (preview)</span></span>

<span data-ttu-id="05393-104">Almacene os datos de Customer Insights nun almacenamento de BLOB ou úseo para transferir os datos a outras aplicacións.</span><span class="sxs-lookup"><span data-stu-id="05393-104">Store your Customer Insights data in a Blob storage or use it to transfer your data to other applications.</span></span>

## <a name="set-up-the-connection-to-blob-storage"></a><span data-ttu-id="05393-105">Configurar a conexión ao almacenamento de BLOB</span><span class="sxs-lookup"><span data-stu-id="05393-105">Set up the connection to Blob storage</span></span>

1. <span data-ttu-id="05393-106">Vaia a **Administrar** > **Conexións**.</span><span class="sxs-lookup"><span data-stu-id="05393-106">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="05393-107">Seleccione **Engadir conexión** e elixa **Azure Blob Storage** para configurar a conexión.</span><span class="sxs-lookup"><span data-stu-id="05393-107">Select **Add connection** and choose **Azure Blob Storage** to configure the connection.</span></span>

1. <span data-ttu-id="05393-108">Déalle á conexión un nome recoñecible no campo **Nome para mostrar**.</span><span class="sxs-lookup"><span data-stu-id="05393-108">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="05393-109">O nome e o tipo de conexión describen esta conexión.</span><span class="sxs-lookup"><span data-stu-id="05393-109">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="05393-110">Recomendamos escoller un nome que explique o propósito e o destino da conexión.</span><span class="sxs-lookup"><span data-stu-id="05393-110">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="05393-111">Escolla quen pode usar esta conexión.</span><span class="sxs-lookup"><span data-stu-id="05393-111">Choose who can use this connection.</span></span> <span data-ttu-id="05393-112">Se non realiza ningunha acción, o valor predeterminado será Administradores.</span><span class="sxs-lookup"><span data-stu-id="05393-112">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="05393-113">Para obter máis información, consulte [Permitir aos colaboradores usar unha conexión para as exportacións](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="05393-113">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="05393-114">Insira o **Nome da conta**, a **Clave da conta** e o **Envase** para a súa conta de almacenamento de BLOB.</span><span class="sxs-lookup"><span data-stu-id="05393-114">Enter **Account name**, **Account key**, and **Container** for your Blob storage account.</span></span>
    - <span data-ttu-id="05393-115">Para obter máis información sobre como atopar o nome e a clave da conta de almacenamento de BLOB, consulte [Xestionar a configuración da conta de almacenamento no portal de Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="05393-115">To learn more about how to find the Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>
    - <span data-ttu-id="05393-116">Para obter máis información acerca de como crear un contedor, consulte [Crear un contedor](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="05393-116">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="05393-117">Seleccione **Gardar** para completar a conexión.</span><span class="sxs-lookup"><span data-stu-id="05393-117">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="05393-118">Configurar unha exportación</span><span class="sxs-lookup"><span data-stu-id="05393-118">Configure an export</span></span>

<span data-ttu-id="05393-119">Pode configurar esta exportación se ten acceso a unha conexión deste tipo.</span><span class="sxs-lookup"><span data-stu-id="05393-119">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="05393-120">Para obter máis información, consulte [Permisos necesarios para configurar unha exportación](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="05393-120">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="05393-121">Vaia a **Datos** > **Exportacións**.</span><span class="sxs-lookup"><span data-stu-id="05393-121">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="05393-122">Seleccione **Engadir destino** para crear unha nova exportación.</span><span class="sxs-lookup"><span data-stu-id="05393-122">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="05393-123">No campo **Conexión da exportación** escolla unha conexión da sección Azure Blob Storage.</span><span class="sxs-lookup"><span data-stu-id="05393-123">In the **Connection for export** field, choose a connection from the Azure Blob Storage section.</span></span> <span data-ttu-id="05393-124">Se non ve o nome desta sección, non hai conexións deste tipo dispoñibles para vostede.</span><span class="sxs-lookup"><span data-stu-id="05393-124">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="05393-125">Seleccione a caixa xunto a cada unha das entidades que desexa exportar a este destino.</span><span class="sxs-lookup"><span data-stu-id="05393-125">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="05393-126">Seleccione **Gardar**.</span><span class="sxs-lookup"><span data-stu-id="05393-126">Select **Save**.</span></span>

<span data-ttu-id="05393-127">Ao gardar unha exportación non se executa a exportación inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="05393-127">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="05393-128">A exportación execútase con cada [actualización programada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="05393-128">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span>     
<span data-ttu-id="05393-129">Tamén pode [exportar datos baixo demanda](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="05393-129">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

<span data-ttu-id="05393-130">Os datos exportados almacénanse no contedor de almacenamento de BLOB que configurou.</span><span class="sxs-lookup"><span data-stu-id="05393-130">Exported data is stored in the Blob storage container you configured.</span></span> <span data-ttu-id="05393-131">As seguintes rutas de cartafol créanse automaticamente no seu contedor:</span><span class="sxs-lookup"><span data-stu-id="05393-131">The following folder paths are automatically created in your container:</span></span>

- <span data-ttu-id="05393-132">Para entidades de orixe e entidades xeradas polo sistema: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`</span><span class="sxs-lookup"><span data-stu-id="05393-132">For source entities and entities generated by the system: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`</span></span>
  - <span data-ttu-id="05393-133">Exemplo: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`</span><span class="sxs-lookup"><span data-stu-id="05393-133">Example: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`</span></span>
- <span data-ttu-id="05393-134">O model.json das entidades exportadas estará no nivel %ExportDestinationName%</span><span class="sxs-lookup"><span data-stu-id="05393-134">The model.json for the exported entities will be at the %ExportDestinationName% level</span></span>
  - <span data-ttu-id="05393-135">Exemplo: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`</span><span class="sxs-lookup"><span data-stu-id="05393-135">Example: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
