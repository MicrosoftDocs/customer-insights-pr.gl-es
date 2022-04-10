---
title: Crear segmentos usando o xerador de segmentos
description: Cree segmentos de clientes para agrupalos en función de varios atributos.
ms.date: 10/18/2021
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-segments
- ci-segment-builder
- ci-segment-details
- customerInsights
ms.openlocfilehash: 6fa6f0738bf7fba94b2fb84a70ea17483aae8dac
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 02/25/2022
ms.locfileid: "8354553"
---
# <a name="create-segments"></a>Crear segmentos

Defina filtros complexos arredor da entidade de cliente unificada e as entidades relacionadas. Cada segmento, despois do procesamento, crea un conxunto de rexistros de clientes que pode exportar e nos que pode tomar medidas. Os segmentos xestionanse na páxina **Segmentos**. Pode [crear novos segmentos](#create-a-new-segment) usando o xerador de segmentos ou [crear segmentos rápidos](#quick-segments) desde outras áreas da aplicación. 

> [!TIP]
> - Os segmentos rápidos só se admiten en ambientes para **clientes individuais**.    
> - Os segmentos baseados en **clientes individuais** inclúe automaticamente a información de contacto dispoñible para os membros do segmento. En ambientes para **contas comerciais**, os segmentos baséanse en contas (empresas ou filiais). Para incluír información de contacto nun segmento, use a funcionalidade **Atributos do proxecto** no creador de segmentos.
>    - Asegúrese de que as fontes de datos de contacto son [asignadas semanticamente á entidade ContactProfile](semantic-mappings.md#define-a-contactprofile-semantic-entity-mapping).

## <a name="segment-builder"></a>Xerador de segmentos

A seguinte imaxe ilustra os distintos aspectos do creador de segmentos. Mostra un segmento que se converte nun grupo de clientes. Os clientes pediron mercadorías nun período de tempo específico e xuntaron puntos de recompensa ou gastaron unha certa cantidade de diñeiro. 

:::image type="content" source="media/segment-builder-overview.png" alt-text="Elementos do xerador de segmentos." lightbox="media/segment-builder-overview.png":::

1. Organice o segmento con regras e subregras. Cada regra ou subregra consta de condicións. Combine as condicións con operadores lóxicos.

1. Escolla o [camiño da relación](relationships.md) entre entidades que se aplica a unha regra. O camiño da relación determina que atributos se poden usar nunha condición.

1. Xestione regras e subregras. Cambie a posición dunha regra ou elimínea.

1. Engada condicións e cree o nivel correcto de aniñamento usando subregras.

1. Aplique operacións de conxunto ás regras conectadas.

1. Use o panel de atributos para engadir atributos de entidade dispoñibles ou crear condicións baseadas en atributos. O panel mostra a lista de entidades e atributos, en función do camiño de relación seleccionado, que están dispoñibles para a regra seleccionada.

1. Engada condicións baseadas en atributos a regras e subregras existentes ou engádaas a unha nova regra.

1. Desfaga e volva facer os cambios mentres crea o segmento.

O exemplo anterior ilustra a capacidade de segmentación. Definimos un segmento para clientes que compraron polo menos 500 dólares en mercadorías en liña *e* teñen interese no desenvolvemento de software.

## <a name="create-a-new-segment"></a>Crear un segmento novo

Hai varias formas de crear un novo segmento. Esta sección describe como construír o seu propio segmento desde cero. Tamén pode crear un *segmento rápido* baseado en entidades existentes ou usar os modelos de aprendizaxe automática para obter *segmentos suxeridos*. Para obter máis información, vaia a [Visión xeral dos segmentos](segments.md).

Ao crear un segmento, pode gardar un borrador. Na fase de borrador, un segmento gárdase como un segmento inactivo. Cando complete a configuración do segmento, execútea para activalo. Tamén pode **Activar** un segmento da páxina **Todos os segmentos**.

1. Vaia á páxina **Segmentos**.

1. Seleccione **Novo** > **Construír o seu propio**.

1. Na páxina do creador de segmentos, defina ou compoña regras. Unha regra está composta dunha ou máis condicións que definen un conxunto de clientes.

1. Na sección **Regra1**, escolla un atributo dunha entidade pola que desexa filtrar os clientes. Hai dúas formas de escoller atributos: 
   - Revise a lista de entidades e atributos dispoñibles no panel **Engadir á regra** e seleccione a icona **+** situada ao lado do atributo para engadir. Escolla se desexa engadir o atributo a unha regra existente ou utilizalo para crear unha nova regra.
   - Escriba o nome do atributo na sección da regra para ver as suxestións coincidentes.

1. Escolla os operadores para especificar os valores coincidentes da condición. O atributo pode ter un dos catro tipos de datos como valor: numérico, cadea, data ou booleano. Dependendo do tipo de datos do atributo, hai diferentes operadores dispoñibles para especificar a condición. Para segmentos con contas comerciais, hai dous operadores especiais dispoñibles para incluír xerarquías potenciais entre as contas inxeridas. Use os operadores *secundario de* e *principal de* para incluír contas relacionadas. 

1. Seleccione **Engadir condición** para engadir máis condicións a unha regra. Para crear unha regra baixo a regra actual, seleccione **Engadir subregra**.

1. Se unha regra usa outras entidades que a entidade *Cliente*, ten que establecer o camiño da relación. O camiño da relación debe informar ao sistema sobre cales son as relacións ás que desexa que acceda a entidade do cliente unificada. Seleccione **Establecer o camiño da relación** para asignar a entidade seleccionada á entidade de cliente unificada. Se só hai un camiño de relación posible, o sistema seleccionarao automaticamente. Diferentes camiños de relación poden dar resultados diferentes. Cada regra pode ter o seu propio camiño de relación.

   :::image type="content" source="media/relationship-path.png" alt-text="Ruta de relación potencial ao crear unha regra baseada nunha entidade asignada á entidade de cliente unificada.":::

   Por exemplo, a entidade *eCommerce_eCommercePurchases* da captura de pantalla ten catro opcións para asignar á entidade *Cliente*: 
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > Cliente
   - eCommerce_eCommercePurchases > Cliente
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > Cliente
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > loyaltyScheme_loyCustomers > Cliente Ao elixir a última opción, podemos incluír atributos de todas as entidades enumeradas nas condicións da regra. É probable que obteñamos menos resultados porque os rexistros de clientes coincidentes deben formar parte de todas as entidades. Neste exemplo, teñen que mercar mercadorías a través do comercio electrónico (*eCommerce_eCommercePurchases*) nun punto de venda (*POS_posPurchases*) e participar no noso programa de fidelidade (*loyaltyScheme_loyCustomers*). Ao escoller a segunda opción, só podemos escoller atributos da entidade *eCommerce_eCommercePurchases* e *Cliente*. É probable que se produzan máis perfís de clientes.

1. Se ten varias condicións nunha regra, pode escoller que operador lóxico as conecta.  
   - Operador **AND**: deben cumprirse todas as condicións para incluír un rexistro no segmento. Esta opción é máis útil cando define condicións entre diferentes entidades.
   - Operador **OR**: debe cumprirse unha das condicións para incluír un rexistro no segmento. Esta opción é máis útil cando define varias condicións para a mesma entidade.

   :::image type="content" source="media/segmentation-either-condition.png" alt-text="Regra con dúas condicións AND.":::

   Cando se usa o operador OR, todas as condicións deben basearse en entidades incluídas na ruta de relación.

   - Pode crear varias regras para crear diferentes conxuntos de rexistros de clientes. Pode combinar grupos para incluír os clientes necesarios para o seu caso de empresa. Para crear unha nova regra, seleccione **Engadir regra**. En concreto, se non pode incluír unha entidade nunha regra debido á ruta da relación especificada, ten que crear unha nova regra para escoller os atributos da mesma.

      :::image type="content" source="media/segment-rule-grouping.png" alt-text="Engada unha nova regra a un segmento e elixa o operador de conxunto.":::

   - Seleccione un dos operadores de definición: **Unión**, **Intersección** ou **Excepto**.

      - **Unión** une os dous grupos.
      - **Intersección** solapa os dous grupos. Só os datos que *sexan comúns* a ambos os grupos permanecen no grupo unificado.
      - **Excepto** combina os dous grupos. Só os datos do grupo A que *non son comúns* cos datos do grupo B se manteñen.

1. De xeito predeterminado, os segmentos xeran a entidade de saída que contén todos os atributos dos perfís de clientes que coinciden cos filtros definidos. Se un segmento está baseado noutras entidades que non son o *Cliente*, pode engadir máis atributos destas entidades á entidade de saída. Seleccione **Atributos do proxecto** para escoller os atributos que se engadirán á entidade de saída. 

   > [!IMPORTANT]
   > Para os segmentos baseados en contas empresariais, hai que incluír no segmento os detalles dun ou máis contactos de cada conta da entidade *ContactProfile* para permitir que se active ou exporte ese segmento nos destinos que requiren información de contacto. Para obter máis información sobre a entidade *ContactProfile*, véxase [Asignacións semánticas](semantic-mappings.md).
   > Unha saída de mostra para un segmento baseado en contas comerciais con atributos de contactos proxectados podería verse así: 
   >
   > |ID  |Nome da conta  |Ingresos  |Nome do contacto  | Rol do contacto|
   > |---------|---------|---------|---------|---|
   > |10021     | Contoso | 100.000 | [Abbie Moss, Ruth Soto]  | [Director xeral, Xerente de adquisicións]

   :::image type="content" source="media/segments-project-attributes.png" alt-text="Exemplo de atributos proxectados seleccionados no panel lateral para engadir á entidade de saída.":::
  
   Por exemplo: un segmento baséase nunha entidade que contén datos de compra, que están relacionados coa entidade *Cliente*. O segmento busca todos os clientes de España que adquiriron bens no ano en curso. Pode escoller engadir atributos como o prezo dos produtos ou a data de compra a todos os rexistros de clientes coincidentes na entidade de saída. Esta información pode ser útil para analizar as correlacións estacionais co gasto total.

   > [!NOTE]
   > - **Atributos do proxecto** só funciona para entidades que teñen unha relación de un a moitos coa entidade de cliente. Por exemplo, un cliente pode ter varias subscricións.
   > - Se o atributo que desexa proxectar está a máis dun salto da entidade de *Cliente*, como a define a relación, ese atributo debería usarse en todas as regras da consulta de segmento que estea a construír. 
   > - Se o atributo que desexa proxectar está a tan só un salto da entidade de *Cliente*, ese atributo non precisa estar presente en todas as regras da consulta de segmentos que estea a construír. 
   > - Os **atributos proxectados** téñense en conta cando se usan operadores de definición.

1. Antes de gardar e executar o segmento, seleccione **Editar detalles** xunto ao nome do segmento. Indique un nome para o seu segmento e actualice o **Nome da entidade de saída** suxerido para o segmento. Tamén pode engadir unha descrición ao segmento.

1. Seleccione **Executar** para gardar o segmento, activalo e comezar a procesar o seu segmento en base a todas as regras e condicións. Se non, gardarase como un segmento inactivo.
   
1. Seleccione **Volver a segmentos** para volver á páxina **Segmentos**.

1. Por defecto, o segmento créase como segmento dinámico. Significa que o segmento se actualiza durante as actualizacións do sistema. Para [deter a actualización automática](segments.md#manage-existing-segments), seleccione o segmento e escolla a opción **Facer estático**. Os segmentos estáticos pódense [actualizar manualmente](segments.md#refresh-segments) en calquera momento.

> [!TIP]
> - O creador de segmentos non suxerirá valores válidos das entidades cando estableza os operadores para as condicións. Pode ir a **Datos** > **Entidades** e descargar os datos da entidade para ver que valores están dispoñibles.
> - As condicións baseadas nas datas permiten cambiar entre datas fixas e un intervalo de datas flotante.
> - Se ten varias regras para o seu segmento, a regra que está editando ten unha liña azul vertical ao lado. 
> - Pode mover regras e condicións a outros lugares da definición do segmento. Seleccione [...] xunto a unha regra ou condición e elixa como e a onde movela.
> - Os controis **Desfacer** e **Refacer** da barra de comandos permiten restablecer os cambios.

## <a name="quick-segments"></a>Segmentos rápidos

Os segmentos rápidos permítenlle crear rapidamente segmentos sinxelos cun único operador para obter información máis rápido.

1. Na páxina **Segmentos**, seleccione **Novo** > **Crear desde**.
   - Seleccione a opción **Perfís** para crear un segmento baseado na entidade de *cliente unificada*.
   - Seleccione a opción **Medidas** para crear un segmento arredor das medidas creadas previamente.
   - Seleccione a opción **Intelixencia** para construír un segmento arredor dunha das entidades de saída que xerou usando calquera das funcións de **Predicións** ou **Modelos personalizados**.

2. Na caixa de diálogo **Novo segmento rápido**, seleccione un atributo no menú despregable **Campo**.

3. O sistema proporcionará máis información que o axudará a crear mellores segmentos dos seus clientes.
   - Por campos categóricos, mostraremos as 10 contas máis importantes de clientes. Escolla un **Valor** e seleccione **Revisar**.
   - Para un atributo numérico, o sistema mostrará que valor de atributo está no percentil de cada cliente. Elixa un **Operador** e un **Valor** e logo seleccione **Revisar**.

4. O sistema forneceralle un **Tamaño de segmento estimado**. Pode escoller se quere xerar o segmento que definiu ou primeiro revisalo para obter un tamaño de segmento diferente.

    > [!div class="mx-imgBorder"]
    > ![Nome e estimación para un segmento rápido.](media/quick-segment-name.png "Nome e estimación para un segmento rápido")

5. Proporcione un **Nome** para o segmento. Tamén pode fornecer un **nome para mostrar**.

6. Seleccione **Gardar** para crear o seu segmento.

7. Despois de que o segmento remate de procesarse, pode visualizalo como calquera outro segmento que crease.

## <a name="next-steps"></a>Pasos seguintes

[Exporte un segmento](export-destinations.md) e explore a [Integración de cartóns de clientes](customer-card-add-in.md) para usar os segmentos noutras aplicacións.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
