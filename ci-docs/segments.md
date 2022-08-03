---
title: Visión xeral dos segmentos
description: Visión xeral dos segmentos e da forma de crealos e xestionalos.
ms.date: 05/20/2022
ms.subservice: audience-insights
ms.topic: overview
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-customers-page
- ci-enrichment-details
- ci-segments
- ci-segment-details
- customerInsights
ms.openlocfilehash: 4bcfbb50b893ca7e6ec4607d3c156a3c6979f775
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170679"
---
# <a name="segments-overview"></a>Visión xeral dos segmentos

Os segmentos permiten agrupar aos seus clientes en función de atributos demográficos, transaccionais ou de comportamento. Pode usar segmentos para ter como obxectivo campañas promocionais, actividades de venda e accións de asistencia ao cliente para alcanzar os obxectivos da súa empresa.

Denomínase perfís de cliente que coinciden cos filtros dunha definición de segmento *membros* dun segmento. Algúns [límites de servizo](/dynamics365/customer-insights/service-limits) aplican.

## <a name="create-a-segment"></a>Crear un segmento

Escolle como crear un segmento en función do teu público obxectivo.

# <a name="individual-consumers-b-to-c"></a>[Consumidores individuais (B2C)](#tab/b2c)

- Segmentos complexos con creador de segmentos: [Constrúe o teu propio](segment-builder.md)
- Segmentos simples cun operador: [segmento rápido](segment-quick.md)
- Forma impulsada por IA de atopar clientes similares: [Clientes semellantes](find-similar-customer-segments.md)
- Suxestións con IA baseadas en medidas ou atributos: [Segmentos suxeridos en función de medidas](suggested-segments.md)
- Suxestións baseadas en actividades: [segmentos suxeridos baseados na actividade dos clientes](suggested-segments-activity.md)

# <a name="business-accounts-b-to-b"></a>[Contas empresariais (B2B)](#tab/b2b)

- Segmentos simples ou complexos co creador de segmentos: [Constrúe o teu propio](segment-builder.md)

---

## <a name="manage-existing-segments"></a>Xestionar os segmentos existentes

Vaia ao **Segmentos** páxina para ver os segmentos que creou, o seu estado e estado, o número de membros e a última vez que se actualizaron os datos. Podes ordenar a lista de segmentos por calquera columna ou utilizar a caixa de busca para atopar o segmento que queres xestionar.

Seleccione un segmento para ver as accións dispoñibles.

:::image type="content" source="media/segments-selected-segment.png" alt-text="Segmento seleccionado con lista despregable de opcións e opcións dispoñibles." lightbox="media/segments-selected-segment.png":::

- [**Ver**](#view-segment-details) os detalles do segmento, incluíndo a tendencia do reconto de membros e unha vista previa dos membros do segmento.
- **Descargue** a lista de membros como ficheiro .CSV.
- **Edite** o segmento para cambiar as súas propiedades.
- **Crear duplicado** dun segmento. Podes optar por editar as súas propiedades de inmediato ou gardar o duplicado.
- [**Actualizar**](#refresh-segments) o segmento para incluír os datos máis recentes.
- **Active** ou **desactive** o segmento. Os segmentos inactivos non se actualizarán durante a [actualización programada](system.md#schedule-tab) e ter o **Estado** listado como **Omitido**, o que indica que nin sequera se intentou unha actualización. Os segmentos activos actualízanse segundo o seu tipo: estático ou dinámico.
- **Fai estática** ou **Dinámico** o tipo de segmento. Os segmentos estáticos deben actualizarse manualmente. Os segmentos dinámicos actualízanse automaticamente durante a actualización do sistema.
- [**Atopar clientes similares**](find-similar-customer-segments.md) do segmento.
- **Renomee** o segmento.
- **Etiquetar** a [xestionar as etiquetas](work-with-tags-columns.md#manage-tags) para o segmento.
- [**Xestionar as exportacións**](#export-segments) para ver segmentos relacionados coa exportación e xestionalos. [Máis información acerca das exportacións.](export-destinations.md)
- **Elimine** o segmento.
- **Columnas** a [personalizar as columnas](work-with-tags-columns.md#customize-columns) esa visualización.
- **Filtro** a [filtrar as etiquetas](work-with-tags-columns.md#filter-on-tags).
- **Buscar nome** para buscar polo nome do segmento.

## <a name="view-segment-details"></a>Ver detalles do segmento

No **Segmentos** páxina, seleccione un segmento para ver o historial de procesamento e os membros do segmento.

A parte superior da páxina inclúe un gráfico de tendencias que mostra os cambios no total de membros. Pase o punteiro sobre os puntos de datos para ver o total de membros dunha data específica. Cambia o marco de tempo da visualización.

:::image type="content" source="media/segment-time-range.png" alt-text="Intervalo de tempo do segmento.":::

A parte inferior contén unha lista dos membros do segmento.

> [!NOTE]
> Os campos que aparecen nesta lista baséanse nos atributos das entidades do seu segmento.
>
>A lista é unha vista previa dos membros do segmento correspondentes e mostra os primeiros 100 rexistros do seu segmento para que poida avalialo rapidamente e revisar as súas definicións se é necesario. Para ver todos os rexistros coincidentes, [exportar o segmento](export-destinations.md).

## <a name="refresh-segments"></a>Actualizar os segmentos

Os segmentos pódense actualizar nunha programación automática ou manualmente baixo demanda. Para actualizar manualmente un ou máis segmentos, selecciónaos e escolla **Actualizar**.

Para [programar unha actualización automática](system.md#schedule-tab), Ir a **Admin** > **Sistema** > **Horario**. Aplícanse as seguintes regras:

- Todos os segmentos co tipo **Dinámico** ou **Expansión** actualizarase automaticamente na cadencia establecida. Unha vez completada a actualización, o **Estado** indica se houbo algún problema ao actualizar o segmento. O **Última actualización** mostra unha marca de tempo da última actualización exitosa. Se se produce un erro, seleccione o erro para ver detalles sobre o que pasou.
- Segmentos co tipo **Estática** *non* actualizarse automaticamente. O **Última actualización** mostra unha marca de tempo da última vez que o segmento estático foi executado ou actualizado manualmente.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="export-segments"></a>Exportar segmentos

Exporta segmentos a outras aplicacións para seguir utilizando os datos. Exportar un segmento desde a páxina de segmentos ou a [páxina de exportacións](export-destinations.md).

1. Vaia ao **Segmentos** páxina e seleccione o segmento que quere exportar.

1. Seleccione **Xestionar as exportacións**. Ábrese a páxina **Exportacións (versión preliminar) para o segmento**. Consulta todas as exportacións configuradas agrupadas segundo se conteñen o segmento actual ou non.

   1. Para engadir o segmento seleccionado a unha exportación, **Edite** a exportación respectiva para seleccionar o segmento correspondente e logo garde. En ambientes para clientes individuais, seleccione a exportación na lista e seleccione **Engadir segmento** para conseguir o mesmo resultado.

   1. Para crear unha nova exportación co segmento seleccionado, seleccione **Engadir exportación**. Para obter máis información sobre a creación de exportacións, consulte [Configurar unha nova exportación](export-destinations.md#set-up-a-new-export).

1. Seleccione **Atrás** para volver á páxina principal dos segmentos.

## <a name="track-usage-of-a-segment"></a>Rastrexa o uso dun segmento

Se usas segmentos en aplicacións que se basean no mesmo Microsoft Dataverse organización que está conectada con Customer Insights, pode rastrexar o uso dun segmento. Para [Segmentos de Customer Insights utilizados nas viaxes dos clientes de Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile), o sistema infórmache sobre o uso dese segmento.

Ao editar un segmento que se está a utilizar no contorno de Customer Insights ou nun viaxe do cliente en Marketing, aparecerá un banner no [constructor de segmentos](segment-builder.md) infórmache sobre as dependencias. Inspecciona os detalles da dependencia directamente desde o banner ou seleccionando **Uso** no constructor de segmentos.

O **Uso de segmentos** o panel mostra os detalles sobre o uso deste segmento en Dataverse aplicacións baseadas en -. Para os segmentos utilizados nas viaxes dos clientes, atoparás unha ligazón para inspeccionar a viaxe en Marketing onde se utiliza este segmento. Se tes permisos para acceder á aplicación Marketing, consulta máis detalles alí.

:::image type="content" source="media/segment-usage-pane.png" alt-text="Panel lateral con detalles do uso do segmento no creador de segmentos.":::

O sistema infórmache sobre o uso dun segmento rastrexado cando intentas eliminalo. Se o segmento que está a piques de eliminar se usa nun viaxe do cliente en Marketing, esa viaxe deterase para todos os usuarios do segmento. Se a viaxe forma parte dunha campaña de mercadotecnia, a eliminación afectará a esa campaña en si. Non obstante, aínda podes eliminar o segmento a pesar das advertencias.

:::image type="content" source="media/segment-usage-delete.png" alt-text="Cadro de diálogo para confirmar a eliminación do segmento cando se usa un segmento nun Dataverse aplicación.":::

### <a name="supported-apps"></a>Aplicacións compatibles

O uso actualízase a continuación Dataverse aplicacións baseadas en:

- [Viaxes dos clientes en Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile)

[!INCLUDE [footer-include](includes/footer-banner.md)]
