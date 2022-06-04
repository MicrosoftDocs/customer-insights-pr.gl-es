---
title: Orixe de datos enriquecemento
description: Enriquece as fontes de datos antes de pasar polo proceso de unificación de datos.
ms.date: 03/02/2022
ms.subservice: audience-insights
ms.topic: how-to
author: NimrodMagen
ms.author: nimagen
ms.reviewer: v-wendysmith
manager: shellyha
ms.openlocfilehash: d1e14d2d4e718d71ccbd2afd259a350ad5c9e69a
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755684"
---
# <a name="enrichment-for-data-sources-preview"></a>Enriquecemento das fontes de datos (vista previa)

Use datos de fontes como Microsoft e outros socios para enriquecer os datos dos seus clientes antes da unificación de datos. Os enriquecementos orixe de datos axudan a producir datos máis completos e de calidade que poden axudar a conseguir mellores resultados unha vez que unifiques os teus datos. Por exemplo, o uso dun formato normalizado e estandarizado para os enderezos aumenta a calidade dos resultados da coincidencia. Para obter unha lista de enriquecementos admitidos, consulte [opcións de enriquecemento orixe de datos compatibles](#supported-data-source-enrichments).

## <a name="enrich-a-data-source"></a>Enriquece un orixe de datos

Debes ter permisos de Colaborador ou Administrador para crear ou editar enriquecementos. Para obter máis información, consulte [Permisos](permissions.md).  

1. Ir a **Datos** > **Unificar**. Seleccione a entidade que quere enriquecer e seleccione un atributo como clave principal para a entidade. Para obter máis información, consulte [Seleccione a chave primaria](map-entities.md#select-primary-key-and-semantic-type-for-attributes).

1. Vaia a **Datos** > **Orixes de datos**.

1. Seleccione os puntos suspensivos verticais xunto ao orixe de datos que quere enriquecer e seleccione **Enriquecer**.

   :::image type="content" source="media/data_sources_enrich_discover.png" alt-text="Páxina de enriquecemento de fontes de datos.":::

   O **Descubrir** pestana mostra o [opcións de enriquecemento orixe de datos compatibles](#supported-data-source-enrichments).

1. Seleccione **Enriquece os meus datos** para configurar un enriquecemento orixe de datos. O nome da entidade de saída enchégase automaticamente.

## <a name="supported-data-source-enrichments"></a>Enriquecementos orixe de datos admitidos

Actualmente están dispoñibles os seguintes enriquecementos para as fontes de datos. Revisa os pasos detallados para o enriquecemento para aprender a configuralo.

- [Enderezos mellorados](enrichment-enhanced-addresses.md)
- [Información da empresa enriquecida](enrichment-enhanced-company-data.md)

## <a name="manage-existing-data-source-enrichments"></a>Xestiona os enriquecementos orixe de datos existentes

Vaia ao separador **Os meus enriquecementos** para ver todos os enriquecementos configurados.

Seleccione o enriquecemento para ver as opcións dispoñibles. Tamén pode seleccionar os puntos suspensivos (...) nun elemento da lista para ver as opcións. Se configurou varios enriquecementos, pode usar a caixa de busca para atopalo rapidamente.

Podes ver, editar, executar ou eliminar un enriquecemento orixe de datos. Para obter máis información, consulte [Xestionar os enriquecementos existentes](enrichment-hub.md).