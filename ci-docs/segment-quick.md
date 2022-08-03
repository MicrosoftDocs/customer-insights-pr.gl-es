---
title: Crea segmentos sinxelos con segmentos rápidos
description: Crea segmentos sinxelos de clientes para agrupalos en función de varios atributos.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-segments
- ci-segment-builder
- ci-segment-details
- customerInsights
ms.openlocfilehash: 98260371a17ff8a05912cc1bc08c67fbe9755727
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 07/18/2022
ms.locfileid: "9171155"
---
# <a name="create-simple-segments-with-quick-segments"></a>Crea segmentos sinxelos con segmentos rápidos

Os segmentos rápidos permítenlle crear rapidamente segmentos sinxelos cun único operador para obter información máis rápido. Os segmentos rápidos só se admiten en ambientes para **clientes individuais**.

## <a name="create-a-new-segment-with-quick-segments"></a>Crea un novo segmento con segmentos rápidos

1. Vaia a **Segmentos**.

1. Seleccione **Novo** > **Crear dende**.
   - Seleccione a opción **Perfís** para crear un segmento baseado na entidade de *cliente unificada*.
   - Seleccione a opción **Medidas** para crear un segmento arredor das medidas creadas previamente.
   - Seleccione a opción **Intelixencia** para construír un segmento arredor dunha das entidades de saída que xerou usando calquera das funcións de **Predicións** ou **Modelos personalizados**.

1. Na caixa de diálogo **Novo segmento rápido**, seleccione un atributo no menú despregable **Campo**. En función da súa selección, o sistema proporciona diferentes valores.
   - Para os campos categóricos, móstranse os 10 principais recontos de clientes. Escolla un **Valor** e seleccione **Revisar**.
   - Para un atributo numérico, o sistema mostra o valor do atributo que se atopa baixo o percentil de cada cliente. Elixa un **Operador** e un **Valor** e logo seleccione **Revisar**.

1. O sistema proporciona un **Tamaño estimado do segmento**. Escolla se quere xerar o segmento que definiu ou volver para escoller un campo diferente.

   :::image type="content" source="media/quick-segment-name.png" alt-text="Nome e estimación para un segmento rápido.":::

1. Proporcionar a **Nome** e **Nome da entidade de saída** para o seu segmento. Opcionalmente, engadir [etiquetas](work-with-tags-columns.md#manage-tags).

1. Seleccione **Gardar** para crear o seu segmento. O **Segmentos** visualización da páxina.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="next-steps"></a>Pasos seguintes

[Exporte un segmento](export-destinations.md) e explore a [Integración de cartóns de clientes](customer-card-add-in.md) para usar os segmentos noutras aplicacións.

[!INCLUDE [footer-include](includes/footer-banner.md)]
