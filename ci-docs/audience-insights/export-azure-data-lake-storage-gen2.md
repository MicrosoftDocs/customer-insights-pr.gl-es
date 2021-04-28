---
title: Exportar datos de Customer Insights a Azure Data Lake Storage Gen2
description: Aprenda a configurar a conexión a Azure Data Lake Storage Gen2.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: f431b707e1d65ffe47f8b3aa1c52abaa964e871a
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760049"
---
# <a name="set-up-the-connection-to-azure-data-lake-storage-gen2-preview"></a><span data-ttu-id="321cf-103">Configurar a conexión a Azure Data Lake Storage Gen2 (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="321cf-103">Set up the connection to Azure Data Lake Storage Gen2 (preview)</span></span>

1. <span data-ttu-id="321cf-104">Vaia a **Administrar** > **Conexións**.</span><span class="sxs-lookup"><span data-stu-id="321cf-104">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="321cf-105">Seleccione **Engadir conexión** e elixa **Azure Blob Storage Gen2** para configurar a conexión.</span><span class="sxs-lookup"><span data-stu-id="321cf-105">Select **Add connection** and choose **Azure Data Lake Gen 2** to configure the connection.</span></span>

1. <span data-ttu-id="321cf-106">Déalle á conexión un nome recoñecible no campo **Nome para mostrar**.</span><span class="sxs-lookup"><span data-stu-id="321cf-106">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="321cf-107">O nome e o tipo de conexión describen esta conexión.</span><span class="sxs-lookup"><span data-stu-id="321cf-107">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="321cf-108">Recomendamos escoller un nome que explique o propósito e o destino da conexión.</span><span class="sxs-lookup"><span data-stu-id="321cf-108">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="321cf-109">Escolla quen pode usar esta conexión.</span><span class="sxs-lookup"><span data-stu-id="321cf-109">Choose who can use this connection.</span></span> <span data-ttu-id="321cf-110">Se non realiza ningunha acción, o valor predeterminado será Administradores.</span><span class="sxs-lookup"><span data-stu-id="321cf-110">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="321cf-111">Para obter máis información, consulte [Permitir aos colaboradores usar unha conexión para as exportacións](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="321cf-111">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="321cf-112">Insira o **Nome da conta**, a **Clave da conta** e o **Contedor** para o seu Azure Data Lake Storage Gen2.</span><span class="sxs-lookup"><span data-stu-id="321cf-112">Enter **Account name**, **Account key**, and **Container** for your Azure Data Lake Storage Gen2.</span></span>
    - <span data-ttu-id="321cf-113">Para aprender a crear unha conta de almacenamento coa que usar Azure Data Lake Storage Gen2, vexa [Crear unha conta de almacenamento](/azure/storage/blobs/create-data-lake-storage-account).</span><span class="sxs-lookup"><span data-stu-id="321cf-113">To learn how to create a storage account to use with Azure Data Lake Storage Gen2, see [Create storage account](/azure/storage/blobs/create-data-lake-storage-account).</span></span> 
    - <span data-ttu-id="321cf-114">Para obter máis información sobre o nome e a clave da conta de almacenamento de Azure Data Lake Gen2, consulte [Xestionar a configuración da conta de almacenamento no portal de Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="321cf-114">To learn more about Azure Data Lake Gen2 storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

1. <span data-ttu-id="321cf-115">Seleccione **Gardar** para completar a conexión.</span><span class="sxs-lookup"><span data-stu-id="321cf-115">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="321cf-116">Configurar unha exportación</span><span class="sxs-lookup"><span data-stu-id="321cf-116">Configure an export</span></span>

<span data-ttu-id="321cf-117">Pode configurar esta exportación se ten acceso a unha conexión deste tipo.</span><span class="sxs-lookup"><span data-stu-id="321cf-117">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="321cf-118">Para obter máis información, consulte [Permisos necesarios para configurar unha exportación](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="321cf-118">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="321cf-119">Vaia a **Datos** > **Exportacións**.</span><span class="sxs-lookup"><span data-stu-id="321cf-119">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="321cf-120">Seleccione **Engadir exportación** para crear unha nova exportación.</span><span class="sxs-lookup"><span data-stu-id="321cf-120">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="321cf-121">No campo **Conexión da exportación** escolla unha conexión da sección **Azure Data Lake**.</span><span class="sxs-lookup"><span data-stu-id="321cf-121">In the **Connection for export** field, choose a connection from the **Azure Data Lake** section.</span></span> <span data-ttu-id="321cf-122">Se non ve o nome desta sección, non hai conexións deste tipo dispoñibles para vostede.</span><span class="sxs-lookup"><span data-stu-id="321cf-122">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="321cf-123">Seleccione a caixa xunto a cada unha das entidades que desexa exportar a este destino.</span><span class="sxs-lookup"><span data-stu-id="321cf-123">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="321cf-124">Seleccione **Gardar**.</span><span class="sxs-lookup"><span data-stu-id="321cf-124">Select **Save**.</span></span>

<span data-ttu-id="321cf-125">Ao gardar unha exportación non se executa a exportación inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="321cf-125">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="321cf-126">A exportación execútase con cada [actualización programada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="321cf-126">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="321cf-127">Tamén pode [exportar datos baixo demanda](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="321cf-127">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

<span data-ttu-id="321cf-128">Os datos exportados almacénanse no contedor de almacenamento de Azure Data Lake Gen 2 que configurou.</span><span class="sxs-lookup"><span data-stu-id="321cf-128">Exported data is stored in the Azure Data Lake Gen 2 storage container you configured.</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
