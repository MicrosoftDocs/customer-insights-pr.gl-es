---
title: Ver e crear métricas
description: Como crear, editar e eliminar métricas.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 7e8c96f38af74f25080a40fd92e73f05c71320a8
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 02/16/2022
ms.locfileid: "8229814"
---
# <a name="view-and-create-metrics"></a>Ver e crear métricas

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

As métricas axudan a comprender o comportamento dos visitantes. Engaden propiedades de eventos e miden as estatísticas e o desempeño das propiedades da súa web.  

Supoña que está a realizar unha promoción de márketing no seu sitio web. Pode usar as métricas para rastrexar o número de visitantes ou usuarios únicos que chegaron ao sitio web durante a promoción. A análise de métricas axuda a comprender mellor o público do seu sitio web. A combinación de métricas con [dimensións](dimensions.md) nun [informe personalizado](custom-reports.md) permítelle medir o comportamento para comprender os seus usuarios. Por exemplo, pode separar os visitantes en categorías novas e recorrentes para identificar as diferenzas de intereses e intencións entre os grupos.

## <a name="view-metrics"></a>Ver métricas

A información de interacción inclúe agregacións de propiedades de eventos de uso habitual, como as métricas do sistema: 

- Visitantes
- Visitas
- Visualizacións da páxina
- Clics

Estas métricas do sistema baséanse en propiedades de eventos existentes en eventos base.

1. Vaia a **Datos** no panel de navegación esquerdo. 
1. Seleccione o separador **Métricas** para ver unha lista de todas as métricas na área de traballo. 
   > [!NOTE]
   > As métricas xeradas polo sistema son só de lectura. Non pode editalas nin eliminalas. Só pode crear e editar métricas personalizadas.

## <a name="create-a-metric"></a>Crear unha métrica

Os administradores de ambientes e áreas de traballo poden crear métricas. As propiedades dos eventos deben enviarse á área de traballo antes de crear unha métrica. Pode crear métricas baseadas nas propiedades dos eventos que envían os eventos base ou usar o SDK web para [enviar propiedades de eventos personalizadas](advanced-SDK-implementation.md).

1. Vaia a **Datos** > **Métricas**.
1. Seleccione **Nova métrica** para abrir o diálogo **Biblioteca de recursos** e **Nova métrica sen título**.

   :::image type="content" source="media/new-metric.png" alt-text="Engadir unha métrica a un evento.":::

1. No diálogo **Nova métrica sen título**, seleccione a lista despregable **Formato** e escolla o tipo de datos **Enteiro** ou **Dobre**. Enteiro é un número enteiro. En Dobre, pode escoller un e tres decimais.

   :::image type="content" source="media/create-new-metric.png" alt-text="Crear unha nova métrica.":::
   
5. No panel **Biblioteca de recursos**, busque a propiedade do evento na que se baseará a métrica.
6. Seleccione o **signo máis (+)** xunto á propiedade para usala na fórmula. Só pode crear unha fórmula baseada nunha propiedade. 
7. Seleccione unha das seguintes funcións de agregado. 

   - Suma: o total aritmético de todos os valores 
   - Media: a media de todos os valores
   - Reconto: o número total de valores
   - Número total de valores únicos: o número total de valores únicos

   Despois de definir a métrica, verá unha versión preliminar da actividade da métrica durante a última hora.

1. Seleccione **Gardar**. 
1. Escriba un nome para a métrica e seleccione **Gardar**.

Pode pasar ata un minuto antes de poder usar a métrica para [crear informes personalizados](custom-reports.md).

## <a name="edit-a-metric"></a>Editar unha métrica

Só pode editar métricas personalizadas.

1. Vaia a **Datos** > **Métricas**.
1. Seleccione a métrica na lista.
1. Cambiar a definición da métrica
1. Seleccione **Gardar**.

## <a name="change-the-name-of-a-metric"></a>Cambiar o nome dunha métrica

Só pode cambiar o nome das métricas personalizadas.

1. Vaia a **Datos** > **Métricas**.
1. Seleccione **Máis [...]** para unha métrica e escolla **Editar nome**.
1. Modifique o nome. 
1. Seleccione **Renomear**.

## <a name="delete-a-metric"></a>Eliminar unha métrica

Só pode eliminar métricas personalizadas.

1. Vaia a **Datos** > **Métricas**.
1. Seleccione **Máis [...]** para unha métrica e escolla **Eliminar**.

   :::image type="content" source="media/delete-metric.png" alt-text="Eliminar unha métrica dun evento.":::

1. Para confirmar a eliminación, seleccione **Eliminar**.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
