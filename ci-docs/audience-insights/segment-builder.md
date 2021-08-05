---
title: Crear e xestionar segmentos
description: Cree segmentos de clientes para agrupalos en función de varios atributos.
ms.date: 07/18/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 4a19661abea42618ef1848110c05d635a925c68f
ms.sourcegitcommit: c45b094072cbe3fbf61d1e9e7d220e1f29ffebd0
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 07/29/2021
ms.locfileid: "6685460"
---
# <a name="create-and-manage-segments"></a>Crear e xestionar segmentos

> [!IMPORTANT]
> Hai varios cambios que se aplican na experiencia de creación de segmentos en setembro de 2021: 
> - O creador de segmentos terá un aspecto lixeiramente diferente con elementos redeseñados e un fluxo de usuario mellorado.
> - No creador de segmentos habilítanse novos operadores dataHora e un selector de datas mellorado.
> - Poderá engadir ou eliminar condicións e regras de segmentos. 
> - As regras aniñadas que comezan cunha condición OR estarán dispoñibles. Xa non precisa unha condición AND na capa máis externa.
> - Un panel lateral para seleccionar atributos estará dispoñible constantemente.
> - Unha opción para seleccionar camiños de relación de entidade.
> Para probar o novo creador de segmentos, envíe un correo electrónico co asunto "Solicitude para activar o novo creador de segmentos" a cihelp [arroba] microsoft.com. Inclúa o nome da súa organización e o ID do ambiente de illamento de procesos.

Defina filtros complexos arredor da entidade de cliente unificada e as entidades relacionadas. Cada segmento, despois do procesamento, crea un conxunto de rexistros de clientes que pode exportar e nos que pode tomar medidas. Os segmentos xestionanse na páxina **Segmentos**. 

O seguinte exemplo ilustra a capacidade de segmentación. Definimos un segmento para clientes que solicitaron polo menos 500 $ de mercadorías nos últimos 90 días *e* que estiveron involucrados nunha chamada de servizo de atención ao cliente que se escalou.

:::image type="content" source="media/segmentation-group1-2.png" alt-text="Captura de pantalla da interface de usuario do creador de segmentos con dous grupos que especifican un segmento de cliente.":::

## <a name="create-a-new-segment"></a>Crear un segmento novo

Hai varias formas de crear un novo segmento. Esta sección describe como crear un *segmento en branco* a partir de cero. Tamén pode crear un *segmento rápido* baseado en entidades existentes ou usar os modelos de aprendizaxe automática para obter *segmentos suxeridos*. Máis información: [Visión xeral dos segmentos](segments.md).

Ao crear un segmento, pode gardar un borrador. Gardarase como un segmento inactivo e non se pode activar até que se remate cunha configuración válida.

1. Vaia á páxina **Segmentos**.

1. Seleccione **Novo** > **Segmento en branco**.

1. No panel **Novo segmento**, escolla un tipo de segmento:

   - Os **segmentos dinámicos** [actualízanse](segments.md#refresh-segments) nunha programación periódica.
   - Os **segmentos estáticos** execútanse unha vez cando se crean.

1. Proporcione un **Nome da entidade de saída** para o segmento. Tamén pode proporcionar un nome para mostrar e unha descrición que axude a identificar o segmento.

1. Seleccione **Seguinte** para chegar á páxina **Construtor de segmentos** onde pode definir un grupo. Un grupo é un conxunto de clientes.

1. Escolla a entidade que inclúe o atributo polo que desexa segmentar.

1. Escolla o atributo polo que segmentar. Este atributo pode ter un dos catro tipos de valor seguintes: numérico, cadea, data ou booleano.

1. Escolla un operador e un valor para o atributo seleccionado.

   > [!div class="mx-imgBorder"]
   > ![Filtro de grupo personalizado.](media/customer-group-numbers.png "Filtro de grupo de clientes")

   |Número |Definición  |
   |---------|---------|
   |1     |Entity          |
   |2     |Atributo          |
   |3    |Operador         |
   |4    |Valor         |

   1. Para engadir máis condicións a un grupo, pode usar dous operadores lóxicos:

      - Operador **AND**: as dúas condicións deben cumprirse como parte do proceso de segmentación. Esta opción é máis útil cando define condicións entre diferentes entidades.

      - Operador **OR**: calquera das condicións debe ser cumprida como parte do proceso de segmentación. Esta opción é máis útil cando define varias condicións para a mesma entidade.

      > [!div class="mx-imgBorder"]
      > ![Operador OR onde se debe cumprir calquera das dúas condicións.](media/segmentation-either-condition.png "Operador OR onde se debe cumprir calquera das dúas condicións")

      Actualmente é posible aniñar un operador **OR** baixo un operador **AND**, pero non ao revés.

   1. Cada grupo coincide cun conxunto de clientes. Pode combinar grupos para incluír os clientes necesarios para o seu caso de empresa.    
   Seleccione **Engadir grupo**.

      > [!div class="mx-imgBorder"]
      > ![Grupo de engadir grupo de clientes.](media/customer-group-add-group.png "Grupo de engadir grupo de clientes")

   1. Seleccione un dos operadores de definición: **Unión**, **Intersección** ou **Excepto**.

   > [!div class="mx-imgBorder"]
   > ![Unión de engadir grupo de clientes.](media/customer-group-union.png "Unión de engadir grupo de clientes")

   - **Unión** une os dous grupos.

   - **Intersección** solapa os dous grupos. Só datos que *son comúns* a ambos os grupos mantéñense no grupo unificado.

   - **Excepto** combina os dous grupos. Só datos do grupo A que *non son comúns* aos datos do grupo B mantéñense.

1. Se a entidade está conectada á entidade de cliente unificada mediante [relacións](relationships.md), necesita definir o camiño da relación para crear un segmento válido. Engada as entidades do camiño da relación ata que poida seleccionar a entidade **Cliente: CustomerInsights** no menú despregable. Despois, escolla **Todos os rexistros** para cada paso.

   > [!div class="mx-imgBorder"]
   > ![Camiño de relación durante a creación do segmento.](media/segments-multiple-relationships.png "Camiño de relación durante a creación do segmento")

1. De xeito predeterminado, os segmentos xeran unha entidade de saída que contén todos os atributos dos perfís de clientes que coinciden cos filtros definidos. Se un segmento está baseado noutras entidades que non son o *Cliente*, pode engadir máis atributos destas entidades á entidade de saída. Seleccione **Atributos do proxecto** para escoller os atributos que se engadirán á entidade de saída.  
  
   Exemplo: un segmento baséase nunha entidade que contén datos de actividade do cliente relacionados coa entidade *Cliente*. O segmento busca a todos os clientes que chamaron ao servizo de asistencia nos últimos 60 días. Pode escoller engadir a duración da chamada e o número de chamadas a todos os rexistros de clientes coincidentes da entidade de saída. Esta información pode ser útil para enviar un correo electrónico con ligazóns útiles a artigos de axuda en liña e preguntas frecuentes aos clientes que chamaron con frecuencia.

   > [!NOTE]
   > - Os atributos proxectados só funcionan para entidades que teñen unha relación de un a varios coa entidade do cliente. Por exemplo, un cliente pode ter varias subscricións.
   > - Só pode proxectar atributos dunha entidade que se use en todos os grupos de consultas de segmento que está a compilar.
   > - Os atributos proxectados téñense en conta cando se usan operadores de definición.

1. Seleccione **Gardar** para gardar o segmento. O teu segmento gardarase e procesarase se todos os requisitos están validados. Se non, gardarase como borrador.

1. Seleccione **Volver a segmentos** para volver á páxina **Segmentos**.



## <a name="quick-segments"></a>Segmentos rápidos

Os segmentos rápidos permítenlle crear rapidamente segmentos sinxelos cun único operador para obter información máis rápido.

1. Na páxina **Segmentos**, seleccione **Novo** > **Crear desde**.

   - Seleccione a opción **Perfís** para crear un segmento baseado na entidade de *cliente unificada*.
   - Seleccione a opción **Medidas** para crear un segmento arredor das medidas creadas previamente.
   - Seleccione a opción **Intelixencia** para construír un segmento arredor dunha das entidades de saída que xerou usando calquera das funcións de **Predicións** ou **Modelos personalizados**.

2. Na caixa de diálogo **Novo segmento rápido**, seleccione un atributo no menú despregable **Campo**.

3. O sistema proporcionará información adicional que lle axudará a crear mellores segmentos dos seus clientes.
   - Por campos categóricos, mostraremos as 10 contas máis importantes de clientes. Escolla un **Valor** e seleccione **Revisar**.

   - Para un atributo numérico, o sistema mostrará que valor de atributo está no percentil de cada cliente. Elixa un **Operador** e un **Valor** e logo seleccione **Revisar**.

4. O sistema forneceralle un **Tamaño de segmento estimado**. Pode escoller se quere xerar o segmento que definiu ou primeiro revisalo para obter un tamaño de segmento diferente.

    > [!div class="mx-imgBorder"]
    > ![Nome e estimación para un segmento rápido.](media/quick-segment-name.png "Nome e estimación para un segmento rápido")

5. Proporcione un **Nome** para o segmento. Tamén pode fornecer un **nome para mostrar**.

6. Seleccione **Gardar** para crear o seu segmento.

7. Despois de que o segmento remate de procesarse, pode visualizalo como calquera outro segmento que crease.

## <a name="next-steps"></a>Pasos seguintes

[Exporte un segmento](export-destinations.md) e explore a [Tarxeta de cliente](customer-card-add-in.md) e os [conectores](export-power-bi.md) para obter información sobre o nivel de cliente.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
