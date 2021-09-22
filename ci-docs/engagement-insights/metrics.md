---
title: Ver e crear métricas
description: Como crear, editar e eliminar métricas.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 06/09/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 97189168e0f5586aad8be8089a1f9e27893c2115c7e805ddaab1efc00e11b860
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034267"
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
   > As métricas xeradas polo sistema son só de lectura. Non podes cambialas nin eliminalas. Só pode crear e editar métricas personalizadas.

## <a name="create-a-metric"></a>Crear unha métrica

Os administradores de ambientes e áreas de traballo poden crear métricas. As propiedades dos eventos deben enviarse á área de traballo antes de crear unha métrica. Pode crear métricas baseadas nas propiedades dos eventos que envían os eventos base ou usar o SDK web para [enviar propiedades de eventos personalizadas](advanced-SDK-implementation.md).

1. Vaia a **Datos** > **Métricas**.
1. Seleccione **Nova métrica**.

   :::image type="content" source="media/new-metric.png" alt-text="Engadir unha métrica a un evento.":::

1. Para o formato, seleccione o tipo de datos **Enteiro** ou **Dobre**. Enteiro é un número enteiro. En Dobre, pode escoller entre un e tres decimais.
1. No panel **Biblioteca de recursos**, busque a propiedade do evento na que se baseará a métrica.
1. Seleccione o **signo máis (+)** xunto á propiedade para usala na fórmula. Só pode crear unha fórmula baseada nunha propiedade. 
1. Seleccione unha das seguintes funcións de agregado. 

   - Suma: o total aritmético de todos os valores 
   - Media: a media de todos os valores
   - Reconto: o número total de valores
   - Número total de valores únicos: o número total de valores únicos

   Despois de definir a métrica, verá unha versión preliminar da actividade da métrica durante a última hora.

1. Seleccione **Gardar**. 
1. Escriba un nome para a métrica e seleccione **Gardar**.

Pode pasar ata un minuto antes de poder usar a métrica para [crear informes personalizados](custom-reports.md).

## <a name="edit-a-metric"></a>Editar unha métrica

1. Vaia a **Datos** > **Métricas**.
1. Seleccione a métrica na lista.
1. Cambiar a definición da métrica
1. Seleccione **Gardar**.

## <a name="change-the-name-of-a-metric"></a>Cambiar o nome dunha métrica

1. Vaia a **Datos** > **Métricas**.
1. Seleccione **Máis [...]** para unha métrica e escolla **Editar nome**.
1. Modifique o nome. 
1. Seleccione **Renomear**.

## <a name="delete-a-metric"></a>Eliminar unha métrica

1. Vaia a **Datos** > **Métricas**.
1. Seleccione **Máis [...]** para unha métrica e escolla **Eliminar**.

   :::image type="content" source="media/delete-metric.png" alt-text="Eliminar unha métrica dun evento.":::

1. Para confirmar a eliminación, seleccione **Eliminar**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
