---
title: Revisar a unificación de datos
description: Revisa os pasos de unificación de datos, crea perfís de clientes unificados e revisa os resultados
ms.date: 06/02/2022
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
ms.openlocfilehash: 20728ffaef9bb705410b3ac22d19868ffd5d1243
ms.sourcegitcommit: 3c5b0b40b2b45e420015bbdd228ce0e610245e6f
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 07/12/2022
ms.locfileid: "9139580"
---
# <a name="review-data-unification"></a>Revisar a unificación de datos

Este último paso do proceso de unificación mostra un resumo dos pasos do proceso e ofrece a oportunidade de facer cambios antes de crear o perfil unificado.

:::image type="content" source="media/m3_review.png" alt-text="Captura de pantalla de Revisar e crear perfís de clientes.":::

## <a name="review-the-data-unification-steps"></a>Revisa os pasos da unificación de datos

1. Seleccione **Editar** en calquera dos pasos de unificación de datos para revisar e facer calquera cambio.

1. Se estás satisfeito coas túas seleccións, selecciona **Crear perfís de clientes**. O **Unificar** móstrase a páxina mentres se crea o perfil de cliente unificado. Todas as tellas excepto **Campos de orixe** mostrar **En cola** ou **Refrescante** estado.

   :::image type="content" source="media/m3_unify_refreshing.png" alt-text="Captura de pantalla da páxina Unify con mosaicos que mostran En cola ou Actualizando.":::

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

O algoritmo de unificación tarda en completarse e non podes cambiar a configuración ata que se complete. Cando se completa o proceso de unificación, chamou a entidade unificada do perfil do cliente *Cliente*, aparece no **Entidades** páxina na **Perfís** sección. A primeira execución exitosa de unificación crea o unificado *Cliente* entidade. Todas as execucións posteriores amplían esa entidade.

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
