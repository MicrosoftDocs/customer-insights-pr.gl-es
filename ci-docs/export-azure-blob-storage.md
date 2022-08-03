---
title: Exportar datos a un Azure Blob Storage (vista previa)
description: Aprenda a configurar a conexión e exportar ao almacenamento de BLOB.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 22593ed05f403a40fe494e30f807b57658594f01
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195702"
---
# <a name="export-data-to-an-azure-blob-storage-preview"></a>Exportar datos a un Azure Blob Storage (vista previa)

Almacene os datos de Customer Insights nun almacenamento de BLOB ou úseo para transferir os datos a outras aplicacións.

## <a name="prerequisites"></a>Requisitos previos

- An [Conta de Azure Blob Storage](/azure/storage/blobs/create-data-lake-storage-account) nome e clave de conta. Para atopar o nome e a chave, consulte [Xestione a configuración da conta de almacenamento no Azure Portal](/azure/storage/common/storage-account-manage).
- An [Contedor Azure Blob Storage](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="known-limitations"></a>Limitacións coñecidas

- Para Azure Blob Storage, elixe entre [Rendemento estándar e nivel de rendemento Premium](/azure/storage/blobs/storage-blob-performance-tiers). Se escolle o nivel de rendemento Premium, seleccione os [blobs de bloque premium como tipo de conta](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-connection-to-blob-storage"></a>Configura a conexión con Blob Storage

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vaia a **Administrar** > **Conexións**.

1. Seleccione **Engadir conexión** e escolle **Azure Blob Storage**.

1. Déalle á conexión un nome recoñecible no campo **Nome para mostrar**. O nome e o tipo de conexión describen esta conexión. Recomendamos escoller un nome que explique o propósito e o destino da conexión.

1. Escolla quen pode usar esta conexión. Por defecto, só son os administradores. Para obter máis información, consulte [Permitir aos colaboradores usar unha conexión para as exportacións](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Insira o **Nome da conta**, a **Clave da conta** e o **Contedor** para a súa conta de almacenamento de BLOB.

1. Revisa o [privacidade e cumprimento dos datos](connections.md#data-privacy-and-compliance) e selecciona **Estou de acordo**.

1. Seleccione **Gardar** para completar a conexión.

## <a name="configure-an-export"></a>Configurar unha exportación

Para configurar esta exportación, debes ter [permiso](export-destinations.md#set-up-a-new-export) para este tipo de conexión.

> [!IMPORTANT]
> Se acendeches o [configuración de eliminación suave](/azure/storage/blobs/soft-delete-blob-enable) para a conta Azure Blob Storage, as exportacións fallarán. Desactive a eliminación temporal para exportar datos aos BLOB.

1. Vaia a **Datos** > **Exportacións**.

1. Seleccione **Engadir exportación**.

1. No campo **Conexión da exportación** escolla unha conexión da sección Azure Blob Storage. Póñase en contacto cun administrador se non hai conexión dispoñible.

1. Introduza un nome para a exportación.

1. Introduza o nome do cartafol para o almacenamento Blob.

1. Seleccione a caixa xunto a cada unha das entidades que desexa exportar a este destino.

1. Seleccione **Gardar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Os datos exportados almacénanse no contedor de almacenamento de BLOB que configurou. As seguintes rutas de cartafol créanse automaticamente no seu contedor:

- Para entidades de orixe e entidades xeradas polo sistema:   
  *%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*  

  Exemplo: Dynamics365CustomerInsights/CustomerInsights_ abcd1234-4312-11f4-93dc-24f72f43e7d5 /BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv
  
  > [!TIP]
  > A exportación de entidades que conteñen unha gran cantidade de datos pode levar a varios ficheiros CSV no mesmo cartafol para cada exportación. A división das exportacións ocorre por motivos de rendemento para minimizar o tempo que tarda en completarse unha exportación.

- O model.json para as entidades exportadas reside en *%ExportDestinationName%* nivel.  
  
  Exemplo: Dynamics365CustomerInsights/CustomerInsights_ abcd1234-4312-11f4-93dc-24f72f43e7d5 /BlobExport/model.json

[!INCLUDE [footer-include](includes/footer-banner.md)]
