---
title: Exporta datos de Customer Insights a InMobi
description: Aprende a configurar a conexión e a exportar a InMobi.
ms.date: 06/27/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8261c8adfe231792e70fc85432237cf73d5cd5a7
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "9059608"
---
# <a name="export-segment-list-and-other-data-to-inmobi-preview"></a>Exportar a lista de segmentos e outros datos a InMobi (vista previa)

Exporta listas de segmentos ou outros datos da túa instancia de Customer Insights a [InMobi](https://www.inmobi.com/).

## <a name="prerequisites"></a>Requisitos previos

1. Tes un [Conta InMobi](https://www.inmobi.com/) e credenciais de administrador.
1. Tes un nome de conta de almacenamento de Azure Blob e a clave de conta correspondente. Para obter máis información, consulte [Xestione a configuración da conta de almacenamento no Azure Portal](/azure/storage/common/storage-account-manage). Hai un contedor na conta de almacenamento para exportar os datos inMobi. Para obter máis información, consulte [Crear un recipiente](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).
1. InMobi creará unha conexión directa co teu Blob Storage e configurará unha importación automática dos teus datos a InMobi. Ponte en contacto co teu representante de InMobi para iniciar o proceso.

## <a name="known-limitations"></a>Limitacións coñecidas

1. Para Azure Blob Storage, podes escoller entre [Rendemento estándar e nivel de rendemento Premium](/azure/storage/blobs/storage-blob-performance-tiers). Se escolle o nivel de rendemento Premium, seleccione os [blobs de bloque premium como tipo de conta](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-the-connection-to-azure-blob-storage-and-configure-an-export"></a>Configure a conexión a Azure Blob Storage e configure unha exportación

1. Siga as instrucións para [configure unha conexión co seu Azure Blob Storage](export-azure-blob-storage.md).
2. Siga as instrucións para [configurar unha exportación](export-azure-blob-storage.md#configure-an-export).

[!INCLUDE [footer-include](includes/footer-banner.md)]
