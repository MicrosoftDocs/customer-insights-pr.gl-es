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
ms.openlocfilehash: 99368a7ab2e8d7b3e53c04fbf25bb23bd2e550a9
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245371"
---
# <a name="measures-overview"></a>Visión xeral das medidas

As medidas axudan a comprender mellor os comportamentos dos clientes e o rendemento empresarial. Miran valores relevantes de [perfís unificados](data-unification.md). Por exemplo, unha empresa quere ver o *gasto total por cliente* para comprender o historial de compras dun cliente individual ou medir as *vendas totais da empresa* para comprender os ingresos agregados de todo o negocio.

Crea medidas para planificar actividades empresariais consultando os datos dos clientes e extraendo información. Por exemplo, crea unha medida de *gasto total por cliente* e *retorno total por cliente* para axudar a identificar un grupo de clientes con alto gasto pero alto retorno. Entón, [crear un segmento](segments.md) en base a estas medidas para impulsar as seguintes mellores accións.

## <a name="create-a-measure"></a>Crear unha medida

Escolle como crear unha medida en función do teu público obxectivo.

# <a name="individual-consumers-b-to-c"></a>[Consumidores individuais (B2C)](#tab/b2c)

- Desde cero co constructor de medidas: [Constrúe o teu propio](measure-builder.md).
- De medidas de uso común: [Use modelos predefinidos](measure-templates.md).

# <a name="business-accounts-b-to-b"></a>[Contas empresariais (B2B)](#tab/b2b)

Desde cero co constructor de medidas: [Constrúe o teu propio](measure-builder.md).

---

## <a name="manage-existing-measures"></a>Xestionar as medidas existentes

Vaia ao **Medidas** páxina para ver as medidas que creou, o seu estado, o tipo de medida e a última vez que se actualizaron os datos. Pode ordenar a lista de medidas por calquera columna ou utilizar a caixa de busca para atopar a medida que quere xestionar.

Seleccione xunto a unha medida para ver as accións dispoñibles. Seleccione o nome da medida para ver a saída e descargar un ficheiro CSV.

:::image type="content" source="media/measures-actions.png" alt-text="Accións para xestionar medidas individuais."lightbox="media/measures-actions.png":::

- **Editar** a medida para cambiar as súas propiedades.
- **Actualizar** a medida para incluír os datos máis recentes.
- **Cambiar o nome** da medida.
- **Activar** ou **Desactivar** a medida. As medidas inactivas non se actualizarán durante a [actualización programada](schedule-refresh.md) e ter o **Estado** listado como **Omitido**, o que indica que nin sequera se intentou unha actualización.
- **Etiquetar** a [xestionar as etiquetas](work-with-tags-columns.md#manage-tags) para a medida.
- **Eliminar** a medida.
- **Columnas** a [personalizar as columnas](work-with-tags-columns.md#customize-columns) esa visualización.
- **Filtro** a [filtrar as etiquetas](work-with-tags-columns.md#filter-on-tags).
- **Buscar nome** para buscar polo nome da medida.

## <a name="refresh-measures"></a>Medidas de actualización

As medidas pódense actualizar nunha programación automática ou actualizar manualmente baixo demanda. Para actualizar manualmente unha ou máis medidas, selecciónaas e escolla **Actualizar**. Para [programar unha actualización automática](schedule-refresh.md), Ir a **Admin** > **Sistema** > **Horario**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
