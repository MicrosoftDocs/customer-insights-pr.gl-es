---
title: Exportar datos a Azure Data Lake Storage Gen2 (versión previa)
description: Aprenda a configurar a conexión a Azure Data Lake Storage Gen2.
ms.date: 10/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: c2446fba425203d2910b82134b73543a73c7ecf8
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082657"
---
# <a name="export-data-to-azure-data-lake-storage-gen2-preview"></a>Exportar datos a Azure Data Lake Storage Gen2 (versión previa)

Almacene os datos de Customer Insights nunha conta de Azure Data Lake Storage Gen2 ou úseos para transferir os datos a outras aplicacións.

## <a name="known-limitations"></a>Limitacións coñecidas

1. Para Azure Data Lake Storage Gen2 pode escoller entre [Rendemento estándar e nivel de rendemento Premium](/azure/storage/blobs/create-data-lake-storage-account) cando estea creando unha conta de almacenamento para o seu lago de datos. Se escolle o nivel de rendemento Premium, seleccione os blobs de bloque premium como tipo de conta.

## <a name="set-up-the-connection-to-azure-data-lake-storage-gen2"></a>Configurar a conexión en Azure Data Lake Storage Gen2

1. Vaia a **Administrar** > **Conexións**.

1. Seleccione **Engadir conexión** e elixa **Azure Blob Storage Gen2** para configurar a conexión.

1. Déalle á conexión un nome recoñecible no campo **Nome para mostrar**. O nome e o tipo de conexión describen esta conexión. Recomendamos escoller un nome que explique o propósito e o destino da conexión.

1. Escolla quen pode usar esta conexión. Se non realiza ningunha acción, o valor predeterminado será Administradores. Para obter máis información, consulte [Permitir aos colaboradores usar unha conexión para as exportacións](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Insira o **Nome da conta**, a **Clave da conta** e o **Contedor** para o seu Azure Data Lake Storage Gen2.
    - Para aprender a crear unha conta de almacenamento coa que usar Azure Data Lake Storage Gen2, vexa [Crear unha conta de almacenamento](/azure/storage/blobs/create-data-lake-storage-account). 
    - Para obter máis información sobre o nome e a clave da conta de almacenamento de Azure Data Lake Gen2, consulte [Xestionar a configuración da conta de almacenamento no portal de Azure](/azure/storage/common/storage-account-manage).

1. Seleccione **Gardar** para completar a conexión.

## <a name="configure-an-export"></a>Configurar unha exportación

Pode configurar esta exportación se ten acceso a unha conexión deste tipo. Para obter máis información, consulte [Permisos necesarios para configurar unha exportación](export-destinations.md#set-up-a-new-export).

1. Vaia a **Datos** > **Exportacións**.

1. Seleccione **Engadir exportación** para crear unha nova exportación.

1. No campo **Conexión da exportación** escolla unha conexión da sección **Azure Data Lake**. Se non ve o nome desta sección, non hai conexións deste tipo dispoñibles para vostede.

1. Seleccione a caixa xunto a cada unha das entidades que desexa exportar a este destino.

1. Seleccione **Gardar**.

Ao gardar unha exportación non se executa a exportación inmediatamente.

A exportación execútase con cada [actualización programada](system.md#schedule-tab).
Tamén pode [exportar datos baixo demanda](export-destinations.md#run-exports-on-demand).

Os datos exportados almacénanse no contedor de almacenamento de Azure Data Lake Gen 2 que configurou.

> [!TIP]
> A exportación de entidades que conteñen unha gran cantidade de datos pode levar a varios ficheiros CSV no mesmo cartafol para cada exportación. A división das exportacións ocorre por motivos de rendemento para minimizar o tempo que tarda en completarse unha exportación.

[!INCLUDE [footer-include](includes/footer-banner.md)]
