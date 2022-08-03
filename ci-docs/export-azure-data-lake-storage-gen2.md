---
title: Exportar datos a Azure Data Lake Storage Gen2 (versión previa)
description: Aprenda a configurar a conexión a Azure Data Lake Storage Gen2.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 55a61e4d9166df7809a64aeb1168a730402aaed6
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196438"
---
# <a name="export-data-to-azure-data-lake-storage-gen2-preview"></a>Exportar datos a Azure Data Lake Storage Gen2 (versión previa)

Almacene os datos de Customer Insights nunha conta de Azure Data Lake Storage Gen2 ou úseos para transferir os datos a outras aplicacións.

## <a name="prerequisites"></a>Requisitos previos

- A [conta de almacenamento para usar con Azure Data Lake Gen2](/azure/storage/blobs/create-data-lake-storage-account). Para atopar o nome e a chave da conta de almacenamento, consulte [Xestione a configuración da conta de almacenamento no Azure Portal](/azure/storage/common/storage-account-manage).
- An [Contedor Azure Blob Storage](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="known-limitations"></a>Limitacións coñecidas

- Para Azure Data Lake Storage Gen2, escolle entre [Rendemento estándar e nivel de rendemento Premium](/azure/storage/blobs/create-data-lake-storage-account). Se escolle o nivel de rendemento Premium, seleccione os [blobs de bloque premium como tipo de conta](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-connection-to-azure-data-lake-storage-gen2"></a>Configura a conexión a Azure Data Lake Storage Xeración 2

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vaia a **Administrar** > **Conexións**.

1. Seleccione **Engadir conexión** e escolle **Azure Data Lake Gen 2**.

1. Déalle á conexión un nome recoñecible no campo **Nome para mostrar**. O nome e o tipo de conexión describen esta conexión. Recomendamos escoller un nome que explique o propósito e o destino da conexión.

1. Escolla quen pode usar esta conexión. Por defecto, só son os administradores. Para obter máis información, consulte [Permitir aos colaboradores usar unha conexión para as exportacións](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Insira o **Nome da conta**, a **Clave da conta** e o **Contedor** para o seu Azure Data Lake Storage Gen2.

1. Revisa o [privacidade e cumprimento dos datos](connections.md#data-privacy-and-compliance) e selecciona **Estou de acordo**.

1. Seleccione **Gardar** para completar a conexión.

## <a name="configure-an-export"></a>Configurar unha exportación

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vaia a **Datos** > **Exportacións**.

1. Seleccione **Engadir exportación**.

1. No **Conexión para exportación** campo, seleccione unha conexión na sección Azure Data Lake. Póñase en contacto cun administrador se non hai conexión dispoñible.

1. Introduza un nome para a exportación.

1. Introduza o nome do cartafol Azure Data Lake Storage Almacenamento Gen2.

1. Seleccione a caixa xunto a cada unha das entidades que desexa exportar a este destino.

1. Seleccione **Gardar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Os datos exportados almacénanse no contedor de almacenamento de Azure Data Lake Gen 2 que configurou.

> [!TIP]
> A exportación de entidades que conteñen unha gran cantidade de datos pode levar a varios ficheiros CSV no mesmo cartafol para cada exportación. A división das exportacións ocorre por motivos de rendemento para minimizar o tempo que tarda en completarse unha exportación.

[!INCLUDE [footer-include](includes/footer-banner.md)]
