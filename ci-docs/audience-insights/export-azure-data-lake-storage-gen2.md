---
title: Exportar datos de Customer Insights a Azure Data Lake Storage Gen2
description: Aprenda a configurar a conexión a Azure Data Lake Storage Gen2.
ms.date: 02/04/2021
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b00c3d6178150cbc93fe800779f094809d4dc67b
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477177"
---
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a>Conector para Azure Data Lake Storage Gen2 (versión preliminar)

Almacene os datos de Customer Insights en Azure Data Lake Storage Gen2 ou úseo para transferir os datos a outras aplicacións.

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a>Configurar o conector para Azure Data Lake Storage Gen2

1. Na información do público, vaia a **Administrar** > **Destinos de exportación**.

1. En **Azure Data Lake Storage Gen2**, seleccione **Configurar**.

1. Déalle ao seu destino un nome recoñecible no campo **Nome para mostrar**.

1. Insira o **Nome da conta**, a **Clave da conta** e o **Contedor** para o seu Azure Data Lake Storage Gen2.
    - Para aprender a crear unha conta de almacenamento coa que usar Azure Data Lake Storage Gen2, vexa [Crear unha conta de almacenamento](https://docs.microsoft.com/azure/storage/blobs/create-data-lake-storage-account). 
    - Para obter máis información sobre como atopar o nome e a clave da conta de almacenamento de Azure Data Lake Gen2, consulte [Xestionar a configuración da conta de almacenamento no portal de Azure](https://docs.microsoft.com/azure/storage/common/storage-account-manage).

1. Seleccione **Seguinte**.

1. Seleccione a caixa xunto a cada unha das entidades que desexa exportar a este destino.

1. Seleccione **Gardar**.

## <a name="export-the-data"></a>Exportar os datos

Pode [exportar datos baixo demanda](export-destinations.md#export-data-on-demand). A exportación tamén se executará con todas as [actualizacións programadas](system.md#schedule-tab).
