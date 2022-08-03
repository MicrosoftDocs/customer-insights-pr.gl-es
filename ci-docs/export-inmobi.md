---
title: Exporta datos de Customer Insights a InMobi
description: Aprende como configurar a conexión e exportar a InMobi.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ef486ad6786ef01be977f3d6bda69ce8a2b081c7
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195886"
---
# <a name="export-customer-insights-data-to-inmobi-preview"></a>Exportar datos de Customer Insights a InMobi (vista previa)

Exporta listas de segmentos ou outros datos da túa instancia de Customer Insights a [InMobi](https://www.inmobi.com/).

## <a name="prerequisites"></a>Requisitos previos

- An [Conta InMobi](https://www.inmobi.com/) e credenciais de administrador.
- An [Conta de Azure Blob Storage](/azure/storage/blobs/create-data-lake-storage-account) nome e clave de conta. Para atopar o nome e a chave, consulte [Xestione a configuración da conta de almacenamento no Azure Portal](/azure/storage/common/storage-account-manage).
- An [Contedor Azure Blob Storage](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container) para exportar datos de InMobi.
- InMobi creará unha conexión directa co teu Blob Storage e configurará unha importación automática dos teus datos a InMobi. Ponte en contacto co teu representante de InMobi para iniciar o proceso.

## <a name="known-limitations"></a>Limitacións coñecidas

- Para Azure Blob Storage, elixe entre [Rendemento estándar e nivel de rendemento Premium](/azure/storage/blobs/storage-blob-performance-tiers). Se escolle o nivel de rendemento Premium, seleccione os [blobs de bloque premium como tipo de conta](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-connection-to-azure-blob-storage"></a>Configura a conexión con Azure Blob Storage

[Configura unha conexión co teu Azure Blob Storage](export-azure-blob-storage.md).

## <a name="configure-an-export"></a>Configurar unha exportación

[Configurar unha exportación](export-azure-blob-storage.md#configure-an-export).

[!INCLUDE [footer-include](includes/footer-banner.md)]
