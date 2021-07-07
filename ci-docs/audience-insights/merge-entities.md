---
title: Combinar entidades na unificación de datos
description: Combine entidades para crear perfís de clientes unificados.
ms.date: 05/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 86ab3cefa70e5fab4bdb27cde363adee26efee4c
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305633"
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

1. Seleccione o campo combinado.
  
1. Seleccione **Mostrar máis** e elixa **Excluír**.

1. Confirme a exclusión.

1. Seleccione **Gardar** e **Executar** para procesar as modificacións. 

Na páxina **Combinar**, seleccione **Campos excluídos** para ver a lista de todos os campos excluídos. Este panel permítelle volver engadir campos excluídos.

## <a name="manually-combine-fields"></a>Combinar campos manualmente

Especifique un atributo combinado manualmente. 

1. Na páxina **Combinar**, seleccione **Combinar campos**.

1. Forneza un **Nome** e un **Nome do campo de saída**.

1. Escolla o campo que quere engadir. Seleccione **Engadir campos** para combinar máis campos.

1. Confirme a exclusión.

1. Seleccione **Gardar** e **Executar** para procesar as modificacións. 

## <a name="change-the-order-of-fields"></a>Modificar a orde dos campos

Algunhas entidades conteñen máis detalles que outras. Se unha entidade inclúe os últimos datos sobre un campo, pode darlle prioridade sobre outras entidades ao combinar valores.

1. Seleccione o campo combinado.
  
1. Seleccione **Mostrar máis** e elixa **Editar**.

1. No panel **Combinar campos**, seleccione **Mover cara arriba ou cara abaixo** para establecer a orde ou arrastre e solte na posición desexada.

1. Confirme a modificación.

1. Seleccione **Gardar** e **Executar** para procesar as modificacións.

## <a name="run-your-merge"></a>Execute a súa combinación

Tanto se combina manualmente atributos ou deixa que o sistema os combine, sempre pode executar a súa combinación. Seleccione **Executar** na páxina **Combinar** para iniciar o proceso.

> [!div class="mx-imgBorder"]
> ![Almacenamento e execución da combinación de datos](media/configure-data-merge-save-run.png "Almacenamento e execución da combinación de datos")

Escolla **Executar só combinación** se só quere ver a saída reflectida na entidade de cliente unificada. Os procesos descendentes actualizaranse segundo [se estableza na programación de actualización](system.md#schedule-tab).

Escolla **Executar combinación e procesos descendentes** para actualizar o sistema coas súas modificacións. Todos os procesos, incluído o enriquecemento, os segmentos e as medidas, volveranse executar automaticamente. Despois de completar todos os procesos descendentes, os perfís de clientes reflicten as modificacións realizadas.

Para realizar máis modificacións e volver executar o paso, pode cancelar unha combinación en curso. Seleccione **Actualizando...** e seleccione **Cancelar traballo** no panel lateral que aparece.

> [!TIP]
> Existen [seis tipos de estado](system.md#status-types) para as tarefas ou os procesos. Ademais, a maioría dos procesos [dependen doutros procesos descendentes](system.md#refresh-policies). Pode seleccionar o estado dun proceso para ver detalles sobre o progreso de todo o traballo. Despois de seleccionar **Ver detalles** para unha das tarefas do traballo, atopará información adicional: o tempo de procesamento, a última data de procesamento e todos os erros e avisos asociados á tarefa.

## <a name="next-step"></a>Seguinte paso

Configure [actividades](activities.md), [enriquecemento](enrichment-hub.md) ou [relacións](relationships.md) para obter máis información sobre os seus clientes.

Se xa configurou actividades, un enriquecemento ou segmentos, procesaranse automaticamente para utilizar os últimos datos do cliente.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
