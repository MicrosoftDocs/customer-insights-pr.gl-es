---
title: Exportar datos de Customer Insights a un Azure Blob Storage
description: Aprenda a configurar a conexión e exportar ao almacenamento de BLOB.
ms.date: 06/30/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b159f87276581f68e07bb73ffd257080eb3cb56422997b09a613bd7afa4e3980
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034726"
---
# <a name="export-segment-list-and-other-data-to-azure-blob-storage-preview"></a>Exportar lista de segmentos e outros datos a Azure Blob Storage (versión preliminar)

Almacene os datos de Customer Insights nun almacenamento de BLOB ou úseo para transferir os datos a outras aplicacións.

## <a name="set-up-the-connection-to-blob-storage"></a>Configurar a conexión ao almacenamento de BLOB

1. Vaia a **Administrar** > **Conexións**.

1. Seleccione **Engadir conexión** e elixa **Azure Blob Storage** para configurar a conexión.

1. Déalle á conexión un nome recoñecible no campo **Nome para mostrar**. O nome e o tipo de conexión describen esta conexión. Recomendamos escoller un nome que explique o propósito e o destino da conexión.

1. Escolla quen pode usar esta conexión. Se non realiza ningunha acción, o valor predeterminado será Administradores. Para obter máis información, consulte [Permitir aos colaboradores usar unha conexión para as exportacións](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Insira o **Nome da conta**, a **Clave da conta** e o **Contedor** para a súa conta de almacenamento de BLOB.
    - Para obter máis información sobre como atopar o nome e a clave da conta de Blob Storage, consulte [Xestionar a configuración da conta de almacenamento no portal de Azure](/azure/storage/common/storage-account-manage).
    - Para obter máis información acerca de como crear un contedor, consulte [Crear un contedor](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Seleccione **Gardar** para completar a conexión. 

## <a name="configure-an-export"></a>Configurar unha exportación

Pode configurar esta exportación se ten acceso a unha conexión deste tipo. Para obter máis información, consulte [Permisos necesarios para configurar unha exportación](export-destinations.md#set-up-a-new-export).

> [!IMPORTANT]
> Se activou a configuración de eliminación temporal da conta de almacenamento de BLOB de Azure, as exportacións fallarán. Desactive a eliminación temporal para exportar datos aos BLOB. Para obter máis información, consulte [Activar a eliminación temporal de BLOB](/azure/storage/blobs/soft-delete-blob-enable.md)

1. Vaia a **Datos** > **Exportacións**.

1. Seleccione **Engadir destino** para crear unha nova exportación.

1. No campo **Conexión da exportación** escolla unha conexión da sección Azure Blob Storage. Se non ve o nome desta sección, non ten ningunha conexión deste tipo dispoñible.

1. Seleccione a caixa xunto a cada unha das entidades que desexa exportar a este destino.

1. Seleccione **Gardar**.

Ao gardar unha exportación non se executa a exportación inmediatamente.

A exportación execútase con cada [actualización programada](system.md#schedule-tab).     

Tamén pode [exportar datos baixo demanda](export-destinations.md#run-exports-on-demand). 

Os datos exportados almacénanse no contedor de almacenamento de BLOB que configurou. As seguintes rutas de cartafol créanse automaticamente no seu contedor:

- Para entidades de orixe e entidades xeradas polo sistema:   
  `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`  
  - Exemplo: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`
 
- O model.json das entidades exportadas estará no nivel %ExportDestinationName%.  
  - Exemplo: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`

[!INCLUDE[footer-include](../includes/footer-banner.md)]
