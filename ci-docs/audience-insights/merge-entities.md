---
title: Combinar entidades na unificación de datos
description: Combine entidades para crear perfís de clientes unificados.
ms.date: 09/14/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: b038cd3f5b433fedf918d34bbfaf2261e11c5c17
ms.sourcegitcommit: fecdee73e26816c42d39d160d4d5cfb6c8a91596
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 09/15/2021
ms.locfileid: "7494317"
---
# <a name="merge-entities"></a>Combinar entidades

A fase de combinación é a última fase do proceso de unificación de datos. O seu propósito é conciliar datos conflitivos. Como exemplos de datos en conflito poden incluírse un nome de cliente que se atopa en dous dos seus conxuntos de datos pero aparece un pouco diferente en cada un ("Grant Marshall" fronte a "Grant Marshal") ou un número de teléfono que difire en formato (617-803-091X fronte a 617803091X). A fusión deses puntos de datos conflitivos realízase atributo por atributo.

:::image type="content" source="media/merge-fields-page.png" alt-text="Páxina Combinar no proceso de unificación de datos que mostra a táboa cos campos combinados que definen o perfil de cliente unificado.":::

Despois de completar a [fase de correspondencia](match-entities.md), pode iniciar a fase de combinación seleccionando o mosaico **Combinar** na páxina **Unificar**.

## <a name="review-system-recommendations"></a>Revisar recomendacións do sistema

En **Datos** > **Unificar** > **Combinar**, escolla e exclúa atributos para combinar na súa entidade de perfil de cliente unificado. O perfil de cliente unificado é o resultado do proceso de unificación de datos. Algúns atributos os combina automaticamente o sistema.

Para ver os atributos incluídos nun dos atributos combinados automaticamente, seleccione ese atributo combinado no separador **Campos do cliente** da táboa. Os atributos que compoñen este atributo combinado móstranse en dúas novas filas baixo o atributo combinado.

## <a name="separate-rename-exclude-and-edit-merged-fields"></a>Separar, renomear, excluír e editar campos combinados

Pode modificar a forma en que o sistema procesa os atributos combinados para xerar o perfil de cliente unificado. Seleccione **Mostrar máis** e elixa o que quere modificar.

:::image type="content" source="media/manage-merged-attributes.png" alt-text="Opcións do menú despregable Mostrar máis para xestionar atributos combinados.":::

Para obter máis información, consulte as seccións seguintes.

## <a name="separate-merged-fields"></a>Separar campos combinados

Para separar campos combinados, busque o atributo na táboa. Os campos separados móstranse como puntos de datos individuais no perfil de cliente unificado. 

1. Seleccione o campo combinado.
  
1. Seleccione **Mostrar máis** e elixa **Campos independentes**.
 
1. Confirme a separación.

1. Seleccione **Gardar** e **Executar** para procesar as modificacións.

## <a name="rename-merged-fields"></a>Renomear campos combinados

Modifique o nome para mostrar dos atributos combinados. Non pode modificar o nome da entidade de saída.

1. Seleccione o campo combinado.
  
1. Seleccione **Mostrar máis** e elixa **Renomear**.

1. Confirme o nome para mostrar modificado. 

1. Seleccione **Gardar** e **Executar** para procesar as modificacións.

## <a name="exclude-merged-fields"></a>Excluír campos combinados

Exclúa un atributo do perfil de cliente unificado. Se o campo se usa noutros procesos, por exemplo nun segmento, elimíneo deses procesos antes de excluílo do perfil do cliente. 

1. Seleccione un campo combinado.
  
1. Seleccione **Mostrar máis** e elixa **Excluír**.

1. Confirme a exclusión.

1. Seleccione **Gardar** e **Executar** para procesar as modificacións. 

Na páxina **Combinar**, seleccione **Campos excluídos** para ver a lista de todos os campos excluídos. Este panel permítelle volver engadir campos excluídos.

## <a name="edit-a-merged-field"></a>Editar un campo combinado

1.  Seleccione un campo combinado.

1.  Seleccione **Mostrar máis** e elixa **Editar**.

1.  Especifique como combinar ou fusionar os campos dunha das tres opcións:
    - **Importancia**: identifica o valor do gañador en función do rango de importancia especificado para os campos participantes. É a opción de combinación predefinida. Seleccione **Subir/baixar** para establecer a clasificación de importancia.
    :::image type="content" source="media/importance-merge-option.png" alt-text="Opción de importancia no diálogo de combinación de campos."::: 
    - **Máis recente**: identifica o valor do gañador en función do máis recente. Require unha data ou un campo numérico para que cada entidade participante no ámbito dos campos de combinación defina a actualidade.
    :::image type="content" source="media/recency-merge-option.png" alt-text="Opción de actualidade no diálogo de combinación de campos.":::
    - **Menos recente**: identifica o valor do gañador en función do menos recente. Require unha data ou un campo numérico para que cada entidade participante no ámbito dos campos de combinación defina a actualidade.

1.  Pode engadir campos adicionais para participar no proceso de combinación.

1.  Pode cambiar o nome do campo combinado.

1. Seleccione **Feito** para aplicar os seus cambios.

1. Seleccione **Gardar** e **Executar** para procesar as modificacións. 

## <a name="manually-combine-fields"></a>Combinar campos manualmente

Especifique un atributo combinado manualmente. 

1. Na páxina **Combinar**, seleccione **Combinar campos**.

1. Especifique a política de gañador da combinación no menú despregable **Combinar campos por**.

1. Escolla o campo que quere engadir. Seleccione **Engadir campos** para combinar máis campos.

1. Forneza un **Nome** e un **Nome do campo de saída**.

1. Seleccione **Feito** para aplicar os cambios.

1. Seleccione **Gardar** e **Executar** para procesar as modificacións. 

## <a name="change-the-order-of-fields"></a>Modificar a orde dos campos

Algunhas entidades conteñen máis detalles que outras. Se unha entidade inclúe os últimos datos sobre un campo, pode darlle prioridade sobre outras entidades ao combinar valores.

1. Seleccione o campo combinado.
  
1. Seleccione **Mostrar máis** e elixa **Editar**.

1. No panel **Combinar campos**, seleccione **Mover cara arriba ou cara abaixo** para establecer a orde ou arrastre e solte na posición desexada.

1. Confirme a modificación.

1. Seleccione **Gardar** e **Executar** para procesar as modificacións.

## <a name="configure-customer-id-generation"></a>Configurar a xeración de ID de cliente 

Despois de configurar a fusión de campos, pode definir como xerar valores de CustomerId, os identificadores únicos do perfil de cliente. O paso de combinación no proceso de unificación de datos xera o identificador único do perfil de cliente. O identificador é o CustomerId na entidade *Cliente* que resulta do proceso de unificación de datos. 

O CustomerId da entidade Customer baséase nun hash do primeiro valor das claves primarias gañadoras non nulas. Estas claves proveñen das entidades utilizadas na fase de combinación e fusión e están influenciadas pola orde de coincidencia. Así, o CustomerID xerado pode cambiar cando cambia un valor de clave primaria na entidade principal da orde de coincidencia. En consecuencia, o valor clave principal non sempre pode representar o mesmo cliente.

A configuración dunha ID de cliente estable permítelle evitar ese comportamento.

**Configurar un ID único de cliente**

1. Vaia a **Unificar** > **Combinar**.

1. Na páxina **Combinar**, seleccione o separador **Chaves**. 

1. Pase o cursor pola fila **CustomerId** e seleccione a opción **Configurar**.
   :::image type="content" source="media/customize-stable-id.png" alt-text="Control para personalizar a xeración de identificacións.":::

1. Seleccione ata cinco campos que formarán un ID de cliente único e serán máis estables. Os rexistros que non coinciden coa súa configuración utilizan un ID configurado polo sistema.  

1. Seleccione **Feito** e execute o proceso de combinación para aplicar os seus cambios.

## <a name="run-your-merge"></a>Execute a súa combinación

Tanto se combina manualmente atributos ou deixa que o sistema os combine, sempre pode executar a súa combinación. Seleccione **Executar** na páxina **Combinar** para iniciar o proceso.

> [!div class="mx-imgBorder"]
> ![Almacenamento e execución da combinación de datos.](media/configure-data-merge-save-run.png "Almacenamento e execución da combinación de datos")

Escolla **Executar só combinación** se só quere ver a saída reflectida na entidade de cliente unificada. Os procesos descendentes actualizaranse segundo [se estableza na programación de actualización](system.md#schedule-tab).

Escolla **Executar combinación e procesos descendentes** para actualizar o sistema coas súas modificacións. Todos os procesos, incluído o enriquecemento, os segmentos e as medidas, volveranse executar automaticamente. Despois de completar todos os procesos descendentes, os perfís de clientes reflicten as modificacións realizadas.

Para realizar máis modificacións e volver executar o paso, pode cancelar unha combinación en curso. Seleccione **Actualizando...** e seleccione **Cancelar traballo** no panel lateral que aparece.

> [!TIP]
> Despois de executar o proceso de combinación, seleccione o estado do proceso para abrir o panel **Detalles da tarefa**. Ofrece unha visión xeral sobre o tempo de procesamento, a última data de procesamento e todos os erros e avisos asociados á tarefa. Seleccione **Ver detalles** para ver que entidades participaron no proceso de coincidencias, se a resolución do conflito se realizou correctamente e se as actualizacións se publicaron correctamente.  
> Existen [seis tipos de estado](system.md#status-types) para as tarefas ou os procesos. Ademais, a maioría dos procesos [dependen doutros procesos descendentes](system.md#refresh-policies).  
> :::image type="content" source="media/process-detail-path.png" alt-text="Camiño detallado para chegar aos detalles do proceso desde a ligazón de estado da tarefa.":::

## <a name="next-step"></a>Seguinte paso

Configure [actividades](activities.md), [enriquecemento](enrichment-hub.md) ou [relacións](relationships.md) para obter máis información sobre os seus clientes.

Se xa configurou actividades, un enriquecemento ou segmentos, procesaranse automaticamente para utilizar os últimos datos do cliente.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
