---
title: Exportar datos de Customer Insights a Azure Data Lake Storage Gen2
description: Aprenda a configurar a conexión a Azure Data Lake Storage Gen2.
ms.date: 02/04/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 7c0eef575f745efa6312d7141a6dd96607f9797e
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596635"
---
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a><span data-ttu-id="9c289-103">Conector para Azure Data Lake Storage Gen2 (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="9c289-103">Connector for Azure Data Lake Storage Gen2 (preview)</span></span>

<span data-ttu-id="9c289-104">Almacene os datos de Customer Insights en Azure Data Lake Storage Gen2 ou úseo para transferir os datos a outras aplicacións.</span><span class="sxs-lookup"><span data-stu-id="9c289-104">Store your Customer Insights data in Azure Data Lake Storage Gen2 or use it to transfer your data to other applications.</span></span>

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a><span data-ttu-id="9c289-105">Configurar o conector para Azure Data Lake Storage Gen2</span><span class="sxs-lookup"><span data-stu-id="9c289-105">Configure the connector for Azure Data Lake Storage Gen2</span></span>

1. <span data-ttu-id="9c289-106">Na información do público, vaia a **Administrar** > **Destinos de exportación**.</span><span class="sxs-lookup"><span data-stu-id="9c289-106">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="9c289-107">En **Azure Data Lake Storage Gen2**, seleccione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="9c289-107">Under **Azure Data Lake Storage Gen2**, select **Set up**.</span></span>

1. <span data-ttu-id="9c289-108">Déalle ao seu destino un nome recoñecible no campo **Nome para mostrar**.</span><span class="sxs-lookup"><span data-stu-id="9c289-108">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="9c289-109">Insira o **Nome da conta**, a **Clave da conta** e o **Contedor** para o seu Azure Data Lake Storage Gen2.</span><span class="sxs-lookup"><span data-stu-id="9c289-109">Enter **Account name**, **Account key**, and **Container** for your Azure Data Lake Storage Gen2.</span></span>
    - <span data-ttu-id="9c289-110">Para aprender a crear unha conta de almacenamento coa que usar Azure Data Lake Storage Gen2, vexa [Crear unha conta de almacenamento](/azure/storage/blobs/create-data-lake-storage-account).</span><span class="sxs-lookup"><span data-stu-id="9c289-110">To learn how to create a storage account to use with Azure Data Lake Storage Gen2, see [Create storage account](/azure/storage/blobs/create-data-lake-storage-account).</span></span> 
    - <span data-ttu-id="9c289-111">Para obter máis información sobre como atopar o nome e a clave da conta de almacenamento de Azure Data Lake Gen2, consulte [Xestionar a configuración da conta de almacenamento no portal de Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="9c289-111">To learn more about how to find the Azure Data Lake Gen2 storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

1. <span data-ttu-id="9c289-112">Seleccione **Seguinte**.</span><span class="sxs-lookup"><span data-stu-id="9c289-112">Select **Next**.</span></span>

1. <span data-ttu-id="9c289-113">Seleccione a caixa xunto a cada unha das entidades que desexa exportar a este destino.</span><span class="sxs-lookup"><span data-stu-id="9c289-113">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="9c289-114">Seleccione **Gardar**.</span><span class="sxs-lookup"><span data-stu-id="9c289-114">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="9c289-115">Exportar os datos</span><span class="sxs-lookup"><span data-stu-id="9c289-115">Export the data</span></span>

<span data-ttu-id="9c289-116">Pode [exportar datos baixo demanda](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="9c289-116">You can [export data on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="9c289-117">A exportación tamén se executará con todas as [actualizacións programadas](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="9c289-117">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>