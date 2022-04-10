---
title: Comprender e xestionar as medidas
description: Aprende como as medidas axudan a analizar e reflectir o rendemento da túa empresa.
ms.date: 02/28/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-measures
- ci-measure-builder
- ci-measure-template
- ci-enrichment-details
- customerInsights
ms.openlocfilehash: c46fcc3baba1d6c92c2c0fe459a62277343cc0e4
ms.sourcegitcommit: cf6a0ed44915908a44c70889a2dd199a9d0d4798
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 02/28/2022
ms.locfileid: "8359776"
---
# <a name="measures-overview"></a>Visión xeral das medidas

As medidas axudan a comprender mellor os comportamentos dos clientes e o rendemento empresarial. Miran valores relevantes de [perfís unificados](data-unification.md). Por exemplo, unha empresa quere ver o *gasto total por cliente* para comprender o historial de compras dun cliente individual ou medir as *vendas totais da empresa* para comprender os ingresos agregados de todo o negocio.  

Créanse medidas [usando o constructor de medidas](measure-builder.md), unha plataforma de consulta de datos con varios operadores e opcións de cartografía sinxelas. Permite filtrar os datos, agrupar resultados, detectar [camiños de relación de entidade](relationships.md) e previsualizar os resultados. Podes [utilizar modelos predefinidos](measure-templates.md) para configurar eficazmente as medidas de uso habitual.

Use o creador de medidas para planificar actividades comerciais consultando datos de clientes e extraendo información. Por exemplo, crear unha medida de *gasto total por cliente* e *devolución total por cliente* axuda a identificar un grupo de clientes cun gasto elevado pero cunha devolución elevada. Podes [crear un segmento](segments.md) en base a estas medidas para impulsar as seguintes mellores accións. 

## <a name="manage-your-measures"></a>Xestionar as súas medidas

Pode atopar a lista de medidas na páxina **Medidas**.

Atopará información sobre o tipo de medida, o creador, a data de creación, o estado e o estado. Cando selecciona unha medida da lista, pode previsualizar a saída e descargar un ficheiro CSV.

Para actualizar todas as túas medidas ao mesmo tempo, seleccione **Actualizar todo** sen seleccionar unha medida específica.

:::image type="content" source="media/measure-actions.png" alt-text="Accións para xestionar medidas individuais.":::

Seleccione unha medida da lista para as seguintes opcións:

- Seleccione o nome da medida para ver os seus detalles.
- **Editar** a configuración da medida.
- **Actualizar** a medida segundo os últimos datos.
- **Cambiar o nome** da medida.
- **Eliminar** a medida.
- **Activar** ou **Desactivar**. As medidas inactivas non se actualizarán durante unha [actualización programada](system.md#schedule-tab).

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="next-step"></a>Seguinte paso

Pode usar as medidas existentes para crear [un segmento de clientes](segments.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
