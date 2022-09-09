---
title: Programar a actualización do sistema
description: Programe a hora na que se debe actualizar o sistema
ms.date: 08/09/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-system-schedule
- customerInsights
ms.openlocfilehash: 949ea071ca41127b0c45488d5d7af3f6aa4e1c35
ms.sourcegitcommit: d7054a900f8c316804b6751e855e0fba4364914b
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 09/02/2022
ms.locfileid: "9395954"
---
# <a name="schedule-system-refresh"></a>Programar a actualización do sistema

Programe actualizacións automáticas de todos os seus [fontes de datos inxeridas](data-sources.md). As actualizacións automáticas axudan a asegurar que as actualizacións das súas orixes de datos se reflictan nos seus perfís de clientes unificados.

> [!NOTE]
> Power Query as fontes de datos xestionadas por ti actualízanse segundo as súas propias programacións. Para programar a actualización destes Power Query fontes de datos, configure a configuración de actualización nese orixe de datos específico desde o **Fontes de datos** páxina.
> :::image type="content" source="media/PPDF-edit-refresh.png" alt-text="Power Platform Configuración de actualización do fluxo de datos.":::

## <a name="set-system-refresh-schedule"></a>Establece o programa de actualización do sistema

1. Ir a **Admin** > **Sistema** e selecciona o **Horario** ficha.

   :::image type="content" source="media/schedule_refresh.png" alt-text="Programar a pestana de actualización desde a páxina do sistema.":::

1. O estado predeterminado para a actualización programada é **Desactivado**. Para activar as actualizacións programadas, cambie o axuste na parte superior da pantalla a **Activado**.

1. Elixa entre actualizacións **Semanalmente** (predeterminado) e **Diariamente**. Se pretende programar actualizacións semanais, seleccione un ou varios días nos que desexa realizalas.

1. Estableza a súa **Zona horaria**, use o menú despregable **Tempo** para configurar o tempo de actualización. Se desexa programar varias actualizacións nun só día, seleccione **Engadir outra hora**. Podes engadir ata catro actualizacións.

1. Seleccione **Gardar** para aplicar as modificacións.

[!INCLUDE [footer-include](includes/footer-banner.md)]
