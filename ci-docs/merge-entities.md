---
title: Unifica os campos de clientes para a unificación de datos
description: Combine entidades para crear perfís de clientes unificados.
recommendations: false
ms.date: 07/27/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-merge
- ci-match
- ci-relationships
- customerInsights
ms.openlocfilehash: 7ebd6ab8fa6ae141f33295a5d7723e96c8dc70ca
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304011"
---
# <a name="unify-customer-fields"></a>Unificar campos de clientes

Neste paso do proceso de unificación, escolle e exclúe os atributos para combinar na túa entidade de perfil unificado. Por exemplo, se tres entidades tiñan datos de correo electrónico, pode querer manter os tres campos de correo electrónico separados ou combinalos nun único campo de correo electrónico para o perfil unificado. Algúns atributos son combinados automaticamente polo sistema. Podes crear ID de cliente estables e únicos. Para clientes individuais, pode agrupar perfís relacionados nun clúster.

:::image type="content" source="media/m3_unify.png" alt-text="Páxina de unificación de campos de clientes no proceso de unificación de datos que mostra unha táboa con campos combinados que definen o perfil de cliente unificado.":::

## <a name="review-and-update-the-customer-fields"></a>Revisa e actualiza os campos do cliente

1. Revisa a lista de campos que se unificarán baixo a **Campos de clientes** ficha da táboa. Realice os cambios se procede.

   1. Para calquera campo combinado, pode:
      - [Editar](#edit-a-merged-field)
      - [Renomear](#rename-fields)
      - [Separar](#separate-merged-fields)
      - [Excluír](#exclude-fields)
      - [Mover arriba ou abaixo](#change-the-order-of-fields)

   1. Para calquera campo, pode:
      - [Combinar campos](#combine-fields-manually)
      - [Combina un grupo de campos](#combine-a-group-of-fields)
      - [Renomear](#rename-fields)
      - [Excluír](#exclude-fields)
      - [Mover arriba ou abaixo](#change-the-order-of-fields)

1. Opcionalmente, [xerar a configuración do ID do cliente](#configure-customer-id-generation).

1. Opcionalmente para B-to-C, [agrupar os perfís en fogares ou clusters](#group-profiles-into-households-or-clusters).

> [!div class="nextstepaction"]
> [Seguinte paso: revisar a unificación](review-unification.md)

### <a name="edit-a-merged-field"></a>Editar un campo combinado

1. Seleccione un campo combinado e escolla **Editar**. Aparece o panel Combinar campos.

1. Especifique como combinar ou fusionar os campos dunha das tres opcións:
    - **Importancia**: identifica o valor do gañador en función do rango de importancia especificado para os campos participantes. É a opción de combinación predefinida. Seleccione **Subir/baixar** para establecer a clasificación de importancia.

      > [!NOTE]
      > Customer Insights usa o primeiro valor non nulo. Por exemplo, dadas as entidades A, B e C clasificadas nesa orde, se A.Name e B.Name son nulas, entón utilízase o valor de C.Name.

      :::image type="content" source="media/importance-merge-option.png" alt-text="Opción de importancia no diálogo de combinación de campos.":::

    - **Máis recente**: identifica o valor do gañador en función do máis recente. Require unha data ou un campo numérico para que cada entidade participante no ámbito dos campos de combinación defina a actualidade.

      :::image type="content" source="media/recency-merge-option.png" alt-text="Opción de actualidade no diálogo de combinación de campos.":::

    - **Menos recente**: identifica o valor do gañador en función do menos recente. Require unha data ou un campo numérico para que cada entidade participante no ámbito dos campos de combinación defina a actualidade.

1. Pode engadir máis campos para participar no proceso de combinación.

1. Pode cambiar o nome do campo combinado.

1. Seleccione **Feito** para aplicar os seus cambios.

### <a name="rename-fields"></a>Cambiar o nome dos campos

Cambia o nome para mostrar dos campos combinados ou separados. Non pode modificar o nome da entidade de saída.

1. Seleccione o campo e escolla **Cambiar o nome**.

1. Introduza o novo nome para mostrar.

1. Seleccione **Feito**.

### <a name="separate-merged-fields"></a>Separar campos combinados

Para separar campos combinados, busque o atributo na táboa. Os campos separados móstranse como puntos de datos individuais no perfil de cliente unificado.

1. Seleccione o campo combinado e escolla **Campos separados**.

1. Confirme a separación.

### <a name="exclude-fields"></a>Excluír campos

Excluír un campo combinado ou separado do perfil de cliente unificado. Se o campo se usa noutros procesos, por exemplo nun segmento, elimíneo deses procesos antes de excluílo do perfil do cliente.

1. Seleccione un campo e escolla **Excluír**.

1. Confirme a exclusión.

Para ver a lista de todos os campos excluídos, seleccione **Campos excluídos**. Se é necesario, pode ler o campo excluído.

### <a name="change-the-order-of-fields"></a>Modificar a orde dos campos

Algunhas entidades conteñen máis detalles que outras. Se unha entidade inclúe os últimos datos sobre un campo, pode darlle prioridade sobre outras entidades ao combinar valores.

1. Seleccione o campo.
  
1. Escolle **Mover arriba/abaixo** para establecer a orde ou arrastralos e soltaos na posición desexada.

### <a name="combine-fields-manually"></a>Combina campos manualmente

Combina campos separados para crear un atributo combinado.

1. Seleccione **Combina** > **Campos**. Aparece o panel Combinar campos.

1. Especifique a política de gañador da combinación no menú despregable **Combinar campos por**.

1. Seleccione **Engadir campo** para combinar máis campos.

1. Forneza un **Nome** e un **Nome do campo de saída**.

1. Seleccione **Feito** para aplicar os cambios.

### <a name="combine-a-group-of-fields"></a>Combina un grupo de campos

Trata un grupo de campos como unha única unidade. Por exemplo, se os nosos rexistros conteñen os campos Enderezo1, Enderezo2, Cidade, Estado e Código postal, non queremos fusionar o Enderezo2 dun rexistro diferente, pensando que faría que os nosos datos sexan máis completos.

1. Seleccione **Combina** > **Grupo de campos**.

1. Especifique a política do gañador da fusión no ficheiro **Clasifica os grupos por** Despregar menú.

1. Seleccione **Engadir** e escolla se quere engadir máis campos ou grupos aos campos.

1. Proporcionar a **Nome** e un **Nome da saída** para cada campo combinado.

1. Proporcionar a **Nome** para o grupo de campos.

1. Seleccione **Feito** para aplicar os cambios.

## <a name="configure-customer-id-generation"></a>Configura a xeración de ID de cliente

Defina como xerar valores de ID de cliente, os identificadores únicos do perfil do cliente. O paso unificar campos no proceso de unificación de datos xera o identificador único do perfil do cliente. O identificador é o *ID de cliente* no *Cliente* entidade que resulta do proceso de unificación de datos.

O *ID de cliente*  baséase nun hash do primeiro valor das claves primarias gañadoras non nulas. Estas claves proveñen das entidades utilizadas na unificación de datos e están influenciadas pola orde de coincidencia.Polo tanto, o ID de cliente xerado pode cambiar cando cambia un valor de chave principal na entidade principal da orde de coincidencia. É posible que o valor da chave principal non represente sempre o mesmo cliente.

A configuración dunha ID de cliente estable permítelle evitar ese comportamento.

1. Seleccione o separador **Claves**.

1. Pasa o rato sobre **ID de cliente** fila e selecciona **Configurar**.
   :::image type="content" source="media/customize-stable-id.png" alt-text="Control para personalizar a xeración de identificacións.":::

1. Seleccione ata cinco campos que formarán un ID de cliente único e serán máis estables. Os rexistros que non coinciden coa súa configuración utilizan un ID configurado polo sistema.  

1. Seleccione **Feito**.

## <a name="group-profiles-into-households-or-clusters"></a>Agrupar perfís en fogares ou grupos

Para clientes individuais, pode definir regras para agrupar perfís relacionados nun clúster. Actualmente hai dous tipos de clústers dispoñibles: domésticos e personalizados. O sistema escolle automaticamente un fogar con regras predefinidas se a entidade *Cliente* contén os campos semánticos *Person.LastName* e *Location.Address*. Tamén pode crear un clúster coas súas propias regras e condicións, semellante a [regras de coincidencia](match-entities.md#define-rules-for-match-pairs).

1. Seleccione **Avanzado** > **Crear clúster**.

   :::image type="content" source="media/create-cluster.png" alt-text="Controlar para crear un novo clúster.":::

1. Escolla entre un clúster **Doméstico** ou **Personalizado**. Se os campos semánticos *Person.LastName* e *Location.Address* existen na entidade *Cliente*, o fogar seleccionarase automaticamente.

1. Indique un nome para o clúster e seleccione **Feito**.

1. Seleccione o separador **Clústers** para atopar o clúster que creou.

1. Especifique as regras e condicións para definir o seu clúster.

1. Seleccione **Feito**. O clúster créase cando se completa o proceso de unificación. Os identificadores do clúster engádense como novos campos ao *Cliente* entidade.

> [!div class="nextstepaction"]
> [Seguinte paso: revisar a unificación](review-unification.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
