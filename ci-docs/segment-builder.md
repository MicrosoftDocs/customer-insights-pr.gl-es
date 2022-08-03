---
title: Crea segmentos complexos co creador de segmentos
description: Use o creador de segmentos para crear segmentos complexos de clientes agrupándoos en función de varios atributos.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-segments
- ci-segment-builder
- ci-segment-details
- customerInsights
ms.openlocfilehash: cde373cd65e296675e1b3c92f3024e1093853842
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170633"
---
# <a name="create-complex-segments-with-segment-builder"></a>Crea segmentos complexos co creador de segmentos

Defina filtros complexos arredor da entidade de cliente unificada e as entidades relacionadas. Cada segmento, despois do procesamento, crea un conxunto de rexistros de clientes que pode exportar e nos que pode tomar medidas.

> [!TIP]
> Os segmentos baseados en **clientes individuais** inclúe automaticamente a información de contacto dispoñible para os membros do segmento. En ambientes para **contas comerciais**, os segmentos baséanse en contas (empresas ou filiais). Para incluír información de contacto nun segmento, use a funcionalidade **Atributos do proxecto** no creador de segmentos. Asegúrese de que as fontes de datos de contacto son [asignadas semanticamente á entidade ContactProfile](semantic-mappings.md#define-a-contactprofile-semantic-entity-mapping).

## <a name="segment-builder"></a>Xerador de segmentos

A seguinte imaxe ilustra os distintos aspectos do creador de segmentos. Mostra un segmento que se converte nun grupo de clientes. Os clientes pediron mercadorías nun período de tempo específico e xuntaron puntos de recompensa ou gastaron unha certa cantidade de diñeiro.

:::image type="content" source="media/segment-builder-overview.png" alt-text="Elementos do xerador de segmentos." lightbox="media/segment-builder-overview.png":::

1. Organice o segmento con regras e subregras. Cada regra ou subregra consta de condicións. Combina as condicións con operadores lóxicos.

1. Escolla o [camiño da relación](relationships.md) entre entidades que se aplica a unha regra. O camiño da relación determina que atributos se poden usar nunha condición.

1. Xestione regras e subregras. Cambie a posición dunha regra ou elimínea.

1. Engada condicións e cree o nivel correcto de aniñamento usando subregras.

1. Aplique operacións de conxunto ás regras conectadas.

1. Use o panel de atributos para engadir atributos de entidade dispoñibles ou crear condicións baseadas en atributos. O panel mostra a lista de entidades e atributos, en función do camiño de relación seleccionado, que están dispoñibles para a regra seleccionada.

1. Engada condicións baseadas en atributos a regras e subregras existentes ou engádaas a unha nova regra.

1. Desfaga e volva facer os cambios mentres crea o segmento.

O exemplo anterior ilustra a capacidade de segmentación. Definimos un segmento para clientes que compraron polo menos 500 dólares en mercadorías en liña *e* teñen interese no desenvolvemento de software.

## <a name="create-a-new-segment-with-segment-builder"></a>Crea un novo segmento co creador de segmentos

1. Vaia a **Segmentos**.

1. Seleccione **Novo** > **Construír o seu propio**. Na páxina do creador de segmentos, defina ou compoña regras. Unha regra está composta dunha ou máis condicións que definen un conxunto de clientes.

1. Seleccione **Editar detalles** xunto ao segmento Sen título. Indique un nome para o seu segmento e actualice o **Nome da entidade de saída** suxerido para o segmento. Opcionalmente, engade unha descrición e [etiquetas](work-with-tags-columns.md#manage-tags) ao segmento.

   :::image type="content" source="media/segments_edit_details.png" alt-text="Cadro de diálogo Editar detalles.":::

1. No **Regra 1** sección, escolla un atributo dunha entidade pola que quere filtrar os clientes. Hai dúas formas de escoller atributos:
   - Revise a lista de entidades e atributos dispoñibles no panel **Engadir á regra** e seleccione a icona **+** situada ao lado do atributo para engadir. Escolla se desexa engadir o atributo a unha regra existente ou utilizalo para crear unha nova regra.
   - Escriba o nome do atributo na sección da regra para ver as suxestións coincidentes.

1. Escolla os operadores para especificar os valores coincidentes da condición. O atributo pode ter un dos catro tipos de datos como valor: numérico, cadea, data ou booleano. Dependendo do tipo de datos do atributo, hai diferentes operadores dispoñibles para especificar a condición. Para segmentos con contas comerciais, hai dous operadores especiais dispoñibles para incluír xerarquías potenciais entre as contas inxeridas. Use os operadores *secundario de* e *principal de* para incluír contas relacionadas.

1. Seleccione **Engadir condición** para engadir máis condicións a unha regra. Para crear unha regra baixo a regra actual, seleccione **Engadir subregra**.

1. Se unha regra utiliza outras entidades distintas do *Cliente* entidade, seleccione **Establece o camiño da relación** para mapear a entidade seleccionada coa entidade cliente unificada. Se só hai un camiño de relación posible, o sistema selecciónao automaticamente. Diferente [camiños de relación](relationships.md#relationship-paths) pode dar resultados diferentes. Cada regra pode ter o seu propio camiño de relación.

   :::image type="content" source="media/relationship-path.png" alt-text="Ruta de relación potencial ao crear unha regra baseada nunha entidade asignada á entidade de cliente unificada.":::

1. Se ten varias condicións nunha regra, escolla que operador lóxico as conecta.  
   - Operador **AND**: deben cumprirse todas as condicións para incluír un rexistro no segmento. Use esta opción cando defina condicións en diferentes entidades.
   - Operador **OR**: debe cumprirse unha das condicións para incluír un rexistro no segmento. Use esta opción cando defina varias condicións para a mesma entidade.

   :::image type="content" source="media/segmentation-either-condition.png" alt-text="Regra con dúas condicións AND.":::

   Cando se usa o operador OR, todas as condicións deben basearse en entidades incluídas na ruta de relación.

1. Para crear diferentes conxuntos de rexistros de clientes, cree varias regras. Para incluír os clientes necesarios para o seu caso de negocio, combine grupos. En concreto, se non pode incluír unha entidade nunha regra debido á ruta de relación especificada, cree unha nova regra para escoller os atributos dela.

      :::image type="content" source="media/segment-rule-grouping.png" alt-text="Engada unha nova regra a un segmento e elixa o operador de conxunto.":::

   1. Seleccione **Engadir regra**.
   1. Seleccione un dos operadores de definición: **Unión**, **Intersección** ou **Excepto**.

      - **Unión** une os dous grupos.
      - **Intersección** solapa os dous grupos. Só os datos que *sexan comúns* a ambos os grupos permanecen no grupo unificado.
      - **Excepto** combina os dous grupos. Só os datos do grupo A que *non son comúns* cos datos do grupo B se manteñen.

1. Por defecto, a entidade de saída conterá automaticamente todos os atributos dos perfís de clientes que coincidan cos filtros definidos. Se un segmento está baseado noutras entidades distintas do *Cliente* entidade, seleccione **Atributos do proxecto** para engadir máis atributos destas entidades á entidade de saída.

   > [!IMPORTANT]
   > Para os segmentos baseados en contas empresariais, detalles dun ou máis contactos de cada conta do *Perfil de contacto* a entidade debe incluírse no segmento para permitir que ese segmento se active ou exporte a destinos que requiran información de contacto. Para obter máis información sobre a entidade *ContactProfile*, véxase [Asignacións semánticas](semantic-mappings.md).
   > Unha saída de mostra para un segmento baseado en contas comerciais con atributos de contactos proxectados podería verse así:
   >
   > |ID  |Nome da conta  |Ingresos  |Nome do contacto  | Rol do contacto|
   > |---------|---------|---------|---------|---|
   > |10021     | Contoso | 100.000 | [Abbie Moss, Ruth Soto]  | [Director xeral, Xerente de adquisicións]

   :::image type="content" source="media/segments-project-attributes.png" alt-text="Exemplo de atributos proxectados seleccionados no panel lateral para engadir á entidade de saída.":::
  
   Por exemplo: un segmento baséase nunha entidade que contén datos de compra, que están relacionados coa entidade *Cliente*. O segmento busca todos os clientes de España que adquiriron bens no ano en curso. Podes optar por engadir atributos como o prezo dos bens ou a data de compra a todos os rexistros de clientes coincidentes na entidade de saída. Esta información pode ser útil para analizar as correlacións estacionais co gasto total.

   > [!NOTE]
   > - **Atributos do proxecto** só funciona para entidades que teñen unha relación de un a moitos coa entidade de cliente. Por exemplo, un cliente pode ter varias subscricións.
   > - Se o atributo que desexa proxectar está a máis dun salto da entidade de *Cliente*, como a define a relación, ese atributo debería usarse en todas as regras da consulta de segmento que estea a construír.
   > - Se o atributo que desexa proxectar está a tan só un salto da entidade de *Cliente*, ese atributo non precisa estar presente en todas as regras da consulta de segmentos que estea a construír.
   > - Os **atributos proxectados** téñense en conta cando se usan operadores de definición.

1. Seleccione **Corre** para crear o segmento. Seleccione **Gardar** se quere manter a configuración actual e executar o segmento máis tarde. O **Segmentos** visualización da páxina.

### <a name="segment-builder-tips"></a>Consellos para crear segmentos

Ao crear un segmento usando o creador de segmentos, teña en conta os seguintes consellos:

- O creador de segmentos non suxerirá valores válidos das entidades cando estableza os operadores para as condicións. Pode ir a **Datos** > **Entidades** e descargar os datos da entidade para ver que valores están dispoñibles.
- As condicións baseadas en datas permítenche cambiar entre datas fixas e intervalos de datas flotantes.
- Se ten varias regras para o seu segmento, a regra que está editando ten unha liña azul vertical ao lado.
- Pode mover regras e condicións a outros lugares da definición do segmento. Seleccione os puntos suspensivos verticais (&vellip;) xunto a unha regra ou condición e escolle como e onde movela.
- Os controis **Desfacer** e **Refacer** da barra de comandos permiten restablecer os cambios.
- Despois de crear un segmento, algúns segmentos permítenche [rastrexar o uso do segmento](segments.md#track-usage-of-a-segment).

## <a name="next-steps"></a>Pasos seguintes

[Exporte un segmento](export-destinations.md) e explore a [Integración de cartóns de clientes](customer-card-add-in.md) para usar os segmentos noutras aplicacións.

[!INCLUDE [footer-include](includes/footer-banner.md)]
