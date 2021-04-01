---
title: Exportar datos de Customer Insights a un Azure Blob Storage
description: Aprenda a configurar a conexión co Azure Blob Storage.
ms.date: 09/18/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 0986ee5caf5fa079994ca584fb2c4d9294ddb80b
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596175"
---
# <a name="connector-for-azure-blob-storage-preview"></a>Conector para Azure Blob Storage (vista previa)

Almacene os datos de Customer Insights nun Azure Blob Storage ou úseo para transferir os datos a outras aplicacións.

## <a name="configure-the-connector-for-azure-blob-storage"></a>Configurar o conector para Azure Blob Storage

1. Na información do público, vaia a **Administrar** > **Destinos de exportación**.

1. En **Azure Blob Storage**, seleccione **Configurar**.

1. Introduza **Nome da conta**, **Clave da conta** e **Contedor** para a súa conta de Azure Blob Storage.
    - Para obter máis información sobre como atopar o nome da conta de almacenamento BLOB de Azure e a clave da conta, consulte [Xestionar a configuración da conta de almacenamento no portal de Azure](/azure/storage/common/storage-account-manage).
    - Para obter máis información acerca de como crear un contedor, consulte [Crear un contedor](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Déalle ao seu destino un nome recoñecible no campo **Nome para mostrar**.

1. Seleccione **Seguinte**.

1. Seleccione a caixa xunto a cada unha das entidades que desexa exportar a este destino.

1. Seleccione **Gardar**.

Os datos exportados almacénanse no contedor de Azure Blob Storage que configurou. As seguintes rutas de cartafol créanse automaticamente no seu contedor:

- Para entidades de orixe e entidades xeradas polo sistema: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`
  - Exemplo: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`
- O model.json das entidades exportadas residirá a nivel de %ExportDestinationName%
  - Exemplo: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`

## <a name="export-the-data"></a>Exportar os datos

Pode [exportar datos baixo demanda](export-destinations.md#export-data-on-demand). A exportación tamén se executará con todas as [actualizacións programadas](system.md#schedule-tab).


[!INCLUDE[footer-include](../includes/footer-banner.md)]