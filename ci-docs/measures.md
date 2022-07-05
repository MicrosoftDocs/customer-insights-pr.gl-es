---
title: Visión xeral das medidas
description: Aprende como as medidas axudan a analizar e reflectir o rendemento da túa empresa.
ms.date: 03/24/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.author: wameng
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-measures
- ci-measure-builder
- ci-measure-template
- ci-enrichment-details
- customerInsights
ms.openlocfilehash: 880c06bffcfa269151d96cb4c597eed4832fc61b
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "9083119"
---
# <a name="measures-overview"></a>Visión xeral das medidas

As medidas axudan a comprender mellor os comportamentos dos clientes e o rendemento empresarial. Miran valores relevantes de [perfís unificados](data-unification.md). Por exemplo, unha empresa quere ver o *gasto total por cliente* para comprender o historial de compras dun cliente individual ou medir as *vendas totais da empresa* para comprender os ingresos agregados de todo o negocio.  

Créanse medidas [usando o constructor de medidas](measure-builder.md), unha plataforma de consulta de datos con varios operadores e opcións de cartografía sinxelas. Permite filtrar os datos, agrupar resultados, detectar [camiños de relación de entidade](relationships.md) e previsualizar os resultados. Podes [utilizar modelos predefinidos](measure-templates.md) para configurar eficazmente as medidas de uso habitual.

Use o creador de medidas para planificar actividades comerciais consultando datos de clientes e extraendo información. Por exemplo, crear unha medida de *gasto total por cliente* e *devolución total por cliente* axuda a identificar un grupo de clientes cun gasto elevado pero cunha devolución elevada. Podes [crear un segmento](segments.md) en base a estas medidas para impulsar as seguintes mellores accións.

## <a name="manage-your-measures"></a>Xestionar as súas medidas

Pode atopar a lista de medidas na páxina **Medidas**.

Atopará información sobre o tipo de medida, o creador, a data de creación, o estado e o estado. Cando selecciona unha medida da lista, pode previsualizar a saída e descargar un ficheiro CSV.

:::image type="content" source="media/measures-actions.png" alt-text="Accións para xestionar medidas individuais."lightbox="media/measures-actions.png":::

As seguintes accións están dispoñibles cando selecciona unha medida:

- **Editar** a configuración da medida.
- **Duplicar** unha medida. Pode escoller editar as súas propiedades de inmediato ou simplemente gardar o duplicado.
- **Actualizar** a medida segundo os últimos datos. Para actualizar todas as súas medidas ao mesmo tempo, seleccione todas as medidas e despois **Actualizar**.
- **Cambiar o nome** da medida.
- **Activar** ou **Desactivar**. As medidas inactivas non se actualizarán durante unha [actualización programada](system.md#schedule-tab).
- **Etiquetar** a [xestionar as etiquetas](work-with-tags-columns.md#manage-tags) para o segmento.
- **Eliminar** a medida.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="next-step"></a>Seguinte paso

Pode usar as medidas existentes para crear [un segmento de clientes](segments.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
