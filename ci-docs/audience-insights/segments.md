---
title: Segmentos na información do público
description: Visión xeral dos segmentos e da forma de crealos e xestionalos.
ms.date: 11/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: overview
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 740d293b21f43b50201f23fcba109318823ef3af
ms.sourcegitcommit: bb1ca84bc38e81fb2ff2961c457384b7beb5b5fa
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 01/15/2022
ms.locfileid: "7978057"
---
# <a name="segments-overview"></a>Visión xeral dos segmentos

Os segmentos permiten agrupar aos seus clientes en función de atributos demográficos, transaccionais ou de comportamento. Pode usar segmentos para ter como obxectivo campañas promocionais, actividades de venda e accións de asistencia ao cliente para alcanzar os obxectivos da súa empresa.

Os perfís de clientes que coinciden cos filtros dunha definición de segmento denomínanse *membros* dun segmento. Algúns [límites de servizo](service-limits.md) aplican.

## <a name="create-a-new-segment"></a>Crear un segmento novo

Hai varias formas de crear un novo segmento: 

# <a name="individual-consumers-b-to-c"></a>[Consumidores individuais (B2C)](#tab/b2c)

- Segmento complexo con creador de segmentos: [Construír o noso](segment-builder.md#create-a-new-segment) 
- Segmentos simples cun operador: [segmento rápido](segment-builder.md#quick-segments) 
- Unha forma con tecnoloxía de IA para atopar clientes semellantes: [clientes semellantes](find-similar-customer-segments.md) 
- Suxestións con tecnoloxía de IA baseadas en medidas ou atributos: [segmentos suxeridos para mellorar as medidas](suggested-segments.md) 
- Suxestións baseadas en actividades: [segmentos suxeridos baseados na actividade dos clientes](suggested-segments-activity.md) 

# <a name="business-accounts-b-to-b"></a>[Contas empresariais (B2B)](#tab/b2b)

- Segmento complexo con creador de segmentos: [Construír o noso](segment-builder.md#create-a-new-segment)

---

## <a name="manage-existing-segments"></a>Xestionar os segmentos existentes

Vaia á paxina **Segmentos** para ver todos os segmentos gardados e xestionalos.

Cada segmento está representado por unha fila que inclúe información adicional sobre o segmento.

:::image type="content" source="media/segments-selected-segment.png" alt-text="Segmento seleccionado con lista despregable de opcións e opcións dispoñibles.":::

A seguinte acción está dispoñible cando selecciona un segmento:

- **Visualice** os detalles do segmento, incluída a tendencia do total de membros e unha vista previa dos membros do segmento.
- **Edite** o segmento para cambiar as súas propiedades.
- **Crear duplicado** dun segmento. Pode escoller editar as súas propiedades de inmediato ou simplemente gardar o duplicado.
- **Actualice** o segmento para incluír os últimos datos.
- **Active** ou **desactive** o segmento. Os segmentos teñen dous estados posibles: activo ou inactivo. Estes estados son útiles cando se edita un segmento. Para os segmentos inactivos, existe a definición do segmento, pero aínda non contén ningún cliente. Cando activa un segmento, o seu estado cambia de "inactivo" a "activo" e comeza a buscar clientes que coincidan coa definición do segmento. Se a [actualización programada](system.md#schedule-tab) está configurada, os segmentos inactivos teñen o **Estado** indicado como **Omitido**, o que indica que nin sequera se intentou actualizar. Cando se activa un segmento inactivo, actualizarase e incluirase nas actualizacións programadas.
  Alternativamente, pode usar a funcionalidade **Programar máis tarde** no menú despregable **Activar/Desactivar** para especificar unha data e hora futuras para a activación e desactivación dun determinado segmento.
- **Renomee** o segmento.
- **Descargue** a lista de membros como ficheiro .CSV.
- **Xestione as exportacións** para ver o segmento relacionado con elas e xestionalas. [Máis información acerca das exportacións.](export-destinations.md)
- **Elimine** o segmento.

## <a name="refresh-segments"></a>Actualizar os segmentos

Pode actualizar todos os segmentos á vez seleccionando **Actualizar todo** na páxina **Segmentos** ou pode actualizar un ou varios segmentos cando os seleccione e elixir **Actualizar** desde as opcións. Tamén pode configurar unha actualización recorrente en **Administrador** > **Sistema** > **Programar**.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="export-segments"></a>Exportar segmentos

Pode exportar un segmento desde a páxina de segmentos ou a [páxina de exportacións](export-destinations.md). 

1. Vaia á páxina **Segmentos**.

1. Seleccione **Mostrar máis [...]** para o segmento que quere exportar.

1. Seleccione **Xestionar as exportacións** da lista despregable de accións.

1. Ábrese a páxina **Exportacións (versión preliminar) para o segmento**. Pode ver todas as exportacións configuradas agrupadas por se conteñen o segmento actual ou non.

   1. Para engadir o segmento seleccionado a unha exportación, **Edite** a exportación respectiva para seleccionar o segmento correspondente e logo garde. En contornos para clientes individuais, pode seleccionar a exportación na lista e seleccionar **Engadir segmento** para acadar o mesmo resultado.

   1. Para crear unha nova exportación co segmento seleccionado, seleccione **Engadir exportación**. Para obter máis información sobre a creación de exportacións, consulte [Configurar unha nova exportación](export-destinations.md#set-up-a-new-export).

1. Seleccione **Atrás** para volver á páxina principal dos segmentos.

## <a name="view-processing-history-and-segment-members"></a>Ver o historial de procesamento e os membros do segmento

Pode ver datos consolidados sobre un segmento revisando os seus detalles.

Na páxina **Segmentos**, seleccione o segmento que desexe revisar.

A parte superior da páxina inclúe un gráfico de tendencias que mostra os cambios no total de membros. Pase o punteiro sobre os puntos de datos para ver o total de membros dunha data específica.

Pode actualizar o intervalo temporal da visualización.

> [!div class="mx-imgBorder"]
> ![Intervalo de tempo do segmento.](media/segment-time-range.png "Intervalo de tempo do segmento")

A parte inferior contén unha lista dos membros do segmento.

> [!NOTE]
> Os campos que aparecen nesta lista baséanse nos atributos das entidades do seu segmento.
>
>A lista é unha vista previa dos membros do segmento correspondentes e mostra os primeiros 100 rexistros do seu segmento para que poida avalialo rapidamente e revisar as súas definicións se é necesario. Para ver todos os rexistros coincidentes, cómpre [exportar o segmento](export-destinations.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)] 
