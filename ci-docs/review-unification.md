---
title: Revisar a unificación de datos
description: Revisa os pasos de unificación de datos, crea perfís de clientes unificados e revisa os resultados
ms.date: 08/12/2022
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
ms.openlocfilehash: b4d77effc347e40fecde625a1a42a24900456471
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 08/16/2022
ms.locfileid: "9303965"
---
# <a name="review-data-unification"></a>Revisar a unificación de datos

Revisa o resumo dos cambios, crea o perfil unificado e revisa os resultados.

## <a name="review-and-create-customer-profiles"></a>Revisar e crear perfís de clientes

Este último paso do proceso de unificación mostra un resumo dos pasos do proceso e ofrece a oportunidade de facer cambios antes de crear o perfil unificado.

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

:::image type="content" source="media/m3_review.png" alt-text="Captura de pantalla de Revisar e crear perfís de clientes.":::

1. Seleccione **Editar** en calquera dos pasos de unificación de datos para revisar e facer calquera cambio.

1. Se estás satisfeito coas túas seleccións, selecciona **Crear perfís de clientes** (ou **Crear perfís de conta** para B-to-B). O **Unificar** móstrase a páxina mentres se crea o perfil de cliente unificado.

   :::image type="content" source="media/m3_unify_refreshing.png" alt-text="Captura de pantalla da páxina Unify con mosaicos que mostran En cola ou Actualizando.":::

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

O algoritmo de unificación tarda en completarse e non podes cambiar a configuración ata que se complete.

## <a name="view-the-results-of-data-unification"></a>Consulta os resultados da unificación de datos

Despois da unificación, o **Datos** > **Unificar** a páxina mostra o número de perfís de clientes unificados (ou perfís de conta para B-to-B). Os resultados de cada paso do proceso de unificación móstranse en cada ficha. Por exemplo, **Campos de orixe** mostra o número de atributos mapeados (campos) e **Rexistros duplicados** mostra o número de rexistros duplicados atopados.

:::image type="content" source="media/m3_unified.png" alt-text="Captura de pantalla da páxina Data Unify despois de que os datos se unifiquen.":::

> [!TIP]
> O **Condicións de coincidencia** O mosaico só se mostra se se seleccionaron varias entidades.

Recomendamos que revise os resultados, especialmente a calidade dos seus [regras de coincidencia](data-unification-update.md#manage-match-rules) e refinalos se é necesario.

Cando sexa necesario, [facer cambios na configuración de unificación](data-unification-update.md) e reexecute o perfil unificado.

### <a name="verify-output-entities-from-data-unification"></a>Verifique as entidades de saída da unificación de datos

Ir a **Datos** > **Entidades** para verificar as entidades de saída.

A entidade unificada do perfil do cliente, chamada *Cliente*, móstrase no **Perfís** sección. A primeira execución exitosa de unificación crea o unificado *Cliente* entidade. Todas as execucións posteriores amplían esa entidade.

As entidades de deduplicación e combinación créanse e móstranse no ficheiro **Sistema** sección. Co nome créase unha entidade deduplicada para cada unha das entidades fonte **Deduplication_DataSource_Entity**. O **ConflaciónMatchPairs** a entidade contén información sobre coincidencias entre entidades.

Unha entidade de saída de desduplicación contén a seguinte información:
- Identificadores ou claves
  - Campos de clave primaria e ID alternativo. O campo de ID alternativo está formado por todos os ID alternativos identificados para un rexistro.
  - O campo Deduplication_GroupId mostra o grupo ou clúster identificado dentro dunha entidade que agrupa todos os rexistros similares en función dos campos de desduplicación especificados. Úsase con fins de procesamento do sistema. Se non hai regras de desduplicación manual especificadas e se aplican regras de desduplicación definidas polo sistema, é posible que non atope este campo na entidade de saída da desduplicación.
  - Deduplication_WinnerId: este campo contén o ID gañador dos grupos ou clústeres identificados. Se o Deduplication_WinnerId é o mesmo que o valor da clave primaria para un rexistro, significa que o rexistro é o rexistro gañador.
- Campos empregados para definir as regras de desduplicación.
- Campos Regra e Puntuación para indicar cal das regras de desduplicación se aplicou e a puntuación devolta polo algoritmo de correspondencia.

## <a name="next-step"></a>Seguinte paso

- Para B-to-B, realiza opcionalmente [unificación de contactos](data-unification-contacts.md).

- Para B-to-C, configure [actividades](activities.md),[enriquecementos](enrichment-hub.md),[relacións](relationships.md), ou [medidas](measures.md) para obter máis información sobre os seus clientes.

[!INCLUDE[footer-include](includes/footer-banner.md)]
