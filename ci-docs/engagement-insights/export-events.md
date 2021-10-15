---
title: Exportar eventos refinados
description: Como exportar eventos refinados e eventos base.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 04/30/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: faa0c3afb08d1c0282b2164ed914637ce9aad88117af37ba44fdb81e7610e574
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032383"
---
# <a name="export-events"></a>Exportar eventos

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Un evento representa o comportamento dun usuario. Rexistra cando un usuario ve unha páxina (evento de visualización) ou interactúa co contido (evento de acción). Cando pode decidir que propiedades dos datos quere mostrar nun informe, esta visualización virtual dos datos chámase *evento refinado*. 

- Pode exportar eventos e eventos refinados a un almacenamento externo. 
- As exportacións son un fluxo de datos de avance. Non pode volver a encher o fluxo. 
- As exportacións teñen esquemas fixos. Se engade propiedades personalizadas a un evento, estes non se incluirán. Deberá crear unha nova exportación.

## <a name="prerequisites"></a>Requisitos previos

Antes de configurar unha exportación, ten que ter acceso e unha subscrición activa ao portal de Azure. Necesitará a información da conta de almacenamento durante o proceso de exportación. 

### <a name="create-an-azure-data-lake-storage-gen-2-accounts"></a>Crear unha conta de Azure Data Lake Storage Gen2

1. Inicie sesión no portal de Azure e [cree unha nova conta de almacenamento](/azure/storage/common/storage-account-create). 

1. Asegúrese de activar **Espazo de nomes xerárquicos** no separador **Avanzado**. 

   :::image type="content" source="media/enable-hierarchical-namespace.png" alt-text="Activación do espazo de nome xerárquico no separador avanzado.":::

1. Unha vez aplicado, vaia á conta de almacenamento creada recentemente. No panel de navegación, seleccione **Configuración** > **Claves de acceso**. 

1. Copie o **nome da conta** e a **clave** para usalos ao crear unha nova exportación.
   :::image type="content" source="media/storage-account-access-keys.png" alt-text="Claves de acceso nunha conta de almacenamento.":::

## <a name="export-events"></a>Exportar eventos

Hai dúas formas de exportar eventos: 
- Vaia a **Datos** > **Exportacións** e seleccione **Nova exportación**.
- Vaia a **Datos** > **Eventos**, seleccione **Máis [...]** xunto ao evento que desexa exportar e seleccione **Exportar** dende o menú despregable. 

Móstranselle os pasos para crear unha exportación:

1. Proporcione un **nome para a exportación**.

1. Na lista despregable **Selección de eventos**, escolla os eventos básicos e os eventos refinados para incluír na exportación. 

1. En **Estrutura do ficheiro**, seleccione a cadencia para crear novos ficheiros no almacenamento de destino. Os eventos expórtanse de forma continua a medida que chegan.

1. Seleccione o formato para a exportación. Pode escoller entre os formatos **Common Data Model**, **CSV** e **JSON**. Para usar a exportación con outras aplicacións de Dynamics 365, recoméndase empregar o formato Common Data Model.

1. No paso **Escoller un destino**, especifique a localización de Azure Data Lake Storage Gen2.
    1. **Nome da conta de ADLS Gen2** é o nome da conta de almacenamento na que desexa gardar a exportación. 
    1. **Camiño do cartafol** define onde se debe almacenar a exportación no sistema de ficheiros e na estrutura de directorios da conta de almacenamento.
    1. A **Clave compartida** está dispoñible no portal de Azure para a conta de almacenamento.

1. Revise e confirme as seleccións.

## <a name="view-and-manage-exports"></a>Ver e xestionar exportacións

Unha vez configurada unha exportación, vaia a **Datos** > **Exportacións** para vela, Seleccione **Máis [...]** para editar ou eliminar calquera exportación existente.


[!INCLUDE[footer-include](../includes/footer-banner.md)]