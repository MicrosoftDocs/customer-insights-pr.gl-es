---
title: Revisar a unificación de datos
description: Revisa os pasos de unificación de datos, crea perfís de clientes unificados e revisa os resultados
ms.date: 05/04/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: adkuppa
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: 4c709dfb55bf079dd2fe99e41adb4c77c2bece4b
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 05/11/2022
ms.locfileid: "8742972"
---
# <a name="review-data-unification"></a>Revisar a unificación de datos

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Este último paso do proceso de unificación mostra un resumo dos pasos do proceso e ofrece a oportunidade de facer cambios antes de crear o perfil unificado.

:::image type="content" source="media/m3_review.png" alt-text="Captura de pantalla de Revisar e crear perfís de clientes.":::

## <a name="review-the-data-unification-steps"></a>Revisa os pasos da unificación de datos

1. Seleccione **Editar** en calquera dos pasos de unificación de datos para revisar e facer calquera cambio.

1. Se estás satisfeito coas túas seleccións, selecciona **Crear perfís de clientes**. O **Unificar** móstrase a páxina mentres se crea o perfil de cliente unificado. O algoritmo de unificación tarda en completarse e non podes cambiar a configuración ata que se complete.

   [!INCLUDE [m3-task-details-include](includes/m3-task-details.md)]

Cando se completa o proceso de unificación, chamou a entidade unificada do perfil do cliente *Cliente*, aparece no **Entidades** páxina na **Perfís** sección. A primeira execución exitosa de unificación crea o unificado *Cliente* entidade. Todas as execucións posteriores amplían esa entidade.

## <a name="review-the-results-of-data-unification"></a>Revisar os resultados da unificación de datos

Despois da unificación, o **Datos** > **Unificar** a páxina mostra o número de perfís de clientes unificados. Os resultados de cada paso do proceso de unificación móstranse en cada ficha. Por exemplo, **Campos de orixe** mostra o número de atributos mapeados (campos) e **Rexistros duplicados** mostra o número de rexistros duplicados atopados.

:::image type="content" source="media/m3_unified.png" alt-text="Captura de pantalla da páxina Data Unify despois de que os datos se unifiquen.":::

> [!TIP]
> O **Condicións de coincidencia** O mosaico só se mostra se se seleccionaron varias entidades.

Recomendamos que revise os resultados, especialmente a calidade dos seus [regras de coincidencia](data-unification-update.md#manage-match-rules) e refinalos se é necesario.

Cando sexa necesario, [facer cambios na configuración de unificación](data-unification-update.md) e reexecute o perfil unificado.

## <a name="next-step"></a>Seguinte paso

Configurar [actividades](activities.md),[enriquecemento](enrichment-hub.md),[relacións](relationships.md), ou [medidas](measures.md) para obter máis información sobre os seus clientes.

[!INCLUDE[footer-include](includes/footer-banner.md)]
