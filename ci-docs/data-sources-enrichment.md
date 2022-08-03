---
title: Enriquecemento das fontes de datos (vista previa)
description: Enriquece as fontes de datos antes de pasar polo proceso de unificación de datos.
ms.date: 05/20/2022
ms.subservice: audience-insights
ms.topic: how-to
author: NimrodMagen
ms.author: nimagen
ms.reviewer: v-wendysmith
manager: shellyha
ms.openlocfilehash: 98e9e330e7ef9cf085caa94a506fa788cebdd67b
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 07/28/2022
ms.locfileid: "9207181"
---
# <a name="enrichment-for-data-sources-preview"></a>Enriquecemento das fontes de datos (vista previa)

Use datos de fontes como Microsoft e outros socios para enriquecer os datos dos seus clientes antes da unificación de datos. Os enriquecementos orixe de datos axudan a producir datos máis completos e de calidade que poden axudar a conseguir mellores resultados unha vez que unifiques os teus datos. Por exemplo, usar un formato normalizado e estandarizado para os enderezos aumenta a calidade dos resultados da coincidencia. Para obter unha lista de enriquecementos admitidos, consulte [opcións de enriquecemento orixe de datos compatibles](#supported-data-source-enrichments).

## <a name="enrich-a-data-source"></a>Enriquece un orixe de datos

Debes ter Colaborador ou Administrador [permisos](permissions.md) para crear ou editar enriquecementos.  

1. Ir a **Datos** > **Unificar**. Seleccione a entidade que quere enriquecer e seleccione un atributo como a [chave primaria](map-entities.md#select-primary-key-and-semantic-type-for-attributes) para a entidade.

1. Vaia a **Datos** > **Orixes de datos**.

1. Seleccione os puntos suspensivos verticais (&vellip;) xunto ao orixe de datos que quere enriquecer e seleccionar **Enriquecer**.

   :::image type="content" source="media/data_sources_enrich.png" alt-text="Páxina de fontes de datos con Enrich resaltado":::

   O **Descubrir** pestana mostra o [opcións de enriquecemento orixe de datos compatibles](#supported-data-source-enrichments).

   :::image type="content" source="media/data_sources_enrich_discover.png" alt-text="Páxina de enriquecemento de fontes de datos.":::

1. Seleccione **Enriquece os meus datos** para configurar un enriquecemento orixe de datos. O nome da entidade de saída enchégase automaticamente.

## <a name="supported-data-source-enrichments"></a>Enriquecementos orixe de datos admitidos

Actualmente están dispoñibles os seguintes enriquecementos para as fontes de datos. Revisa os pasos detallados para o enriquecemento para saber como configuralo.

- [Enderezos mellorados](enrichment-enhanced-addresses.md)
- [Información da empresa enriquecida](enrichment-enhanced-company-data.md)
- [Datos de identidade de LiveRamp](enrichment-liveramp.md)

## <a name="manage-existing-data-source-enrichments"></a>Xestiona os enriquecementos orixe de datos existentes

Vaia a **Datos** > **Enriquecemento**. No **Os meus enriquecementos** pestana, ver os enriquecementos configurados, o seu estado, o número de clientes enriquecidos e a última vez que se actualizaron os datos. Podes ordenar a lista de enriquecementos por calquera columna ou utilizar a caixa de busca para atopar o enriquecemento que queres xestionar.

Seleccione o enriquecemento para ver as opcións dispoñibles. Tamén pode seleccionar os puntos suspensivos verticais (&vellip;) nun elemento da lista para ver as opcións.

Podes ver, editar, executar ou eliminar un enriquecemento orixe de datos. Para obter máis información, consulte [Xestionar os enriquecementos existentes](enrichment-hub.md#manage-existing-enrichments).
