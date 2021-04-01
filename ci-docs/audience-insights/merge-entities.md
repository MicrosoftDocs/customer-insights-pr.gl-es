---
title: Combinar entidades na unificación de datos
description: Combine entidades para crear perfís de clientes unificados.
ms.date: 04/16/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 737c593353878a5e322488d00de5dc5db5befda9
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597831"
---
# <a name="merge-entities"></a>Combinar entidades

A fase de combinación é a última fase do proceso de unificación de datos. O seu propósito é conciliar datos conflitivos. Como exemplos de datos en conflito poden incluírse un nome de cliente que se atopa en dous dos seus conxuntos de datos pero aparece un pouco diferente en cada un ("Grant Marshall" fronte a "Grant Marshal") ou un número de teléfono que difire en formato (617-803-091X fronte a 617803091X). A fusión deses puntos de datos conflitivos realízase atributo por atributo.

Despois de completar a [fase de correspondencia](match-entities.md), pode iniciar a fase de combinación seleccionando o mosaico **Combinar** na páxina **Unificar**.

## <a name="review-system-recommendations"></a>Revisar recomendacións do sistema

Na páxina **Combinar**, pode escoller e excluír os atributos que desexa fusionar na súa entidade de perfil de cliente unificada (o resultado do proceso de configuración). Algúns atributos os combina automaticamente o sistema.

### <a name="view-merged-attributes"></a>Ver atributos combinados

Para ver os atributos que están incluídos nun dos seus atributos combinados automaticamente, seleccione ese atributo combinado. Os dous atributos que compoñen este atributo combinado aparecerán en dúas novas filas baixo o atributo combinado.

> [!div class="mx-imgBorder"]
> ![Seleccionar atributo combinado](media/configure-data-merge-profile-attributes.png "Seleccionar atributo combinado")

### <a name="separate-merged-attributes"></a>Separar atributos combinados

Para separar ou desfacer a combinación de calquera dos atributos combinados automaticamente, busque o atributo na táboa **Atributos do perfil**.

1. Seleccione o botón de tres puntos (...).
  
2. Na lista despregable, seleccione **Campos separados**.

### <a name="remove-merged-attributes"></a>Elimine os atributos combinados

Para excluír un atributo da entidade de perfil de cliente final, búsqueo na táboa **Atributos do perfil**.

1. Seleccione o botón de tres puntos (...).
  
2. Na lista despregable, seleccione **Non combinar**.

   O atributo móvese á sección **Eliminado do rexistro do cliente**.

## <a name="manually-add-a-merged-attribute"></a>Engadir manualmente un atributo combinado

Para engadir un atributo combinado, diríxase á páxina **Combinar**.

1. Seleccione **Engadir atributo combinado**.

2. Proporcione un **Nome** para identificalo na páxina **Combinar** despois.

3. Tamén pode fornecer un **Nome para mostrar** que apareza na entidade de perfil de cliente unificada.

4. Configure **Seleccionar atributos duplicados** para seleccionar os atributos que desexe combinar entre as entidades correspondentes. Tamén pode buscar atributos.

5. Estableza **Clasificar por importancia** para priorizar un atributo por enriba dos outros. Por exemplo, se a entidade *WebAccountCSV* inclúe os datos máis precisos sobre o atributo *Nomes completos*, pode priorizar esta entidade sobre *ContactCSV* seleccionando *WebAccountCSV*. Como resultado, *WebAccountCSV* pasa á primeira prioridade mentres que *ContactCSV* desprázase á segunda prioridade ao obter valores para o atributo *Nome completo*.

## <a name="run-your-merge"></a>Execute a súa combinación

Tanto se combina manualmente atributos ou deixa que o sistema os combine, sempre pode executar a súa combinación. Seleccione **Executar** na páxina **Combinar** para iniciar o proceso.

> [!div class="mx-imgBorder"]
> ![Almacenamento e execución da combinación de datos](media/configure-data-merge-save-run.png "Almacenamento e execución da combinación de datos")

Para facer cambios adicionais e volver executar o paso, pode cancelar unha combinación en curso. Seleccione **Actualizando...** e seleccione **Cancelar traballo** no panel lateral que aparece.

Unha vez que cambie o texto **Actualizando...** a **Correcto**, a combinación completouse e resolveu as contradicións dos seus datos de acordo coas políticas que definiu. Os atributos combinados e non combinados inclúense na entidade de perfil unificado. Os atributos excluídos non se inclúen na entidade de perfil unificado.

Se non foi a primeira vez que executou unha combinación con éxito, todos os procesos descendentes, incluído o enriquecemento, a segmentación e as medidas, volveranse executar automaticamente. Despois de repetirse todos os procesos descendentes, os perfís de clientes reflicten os cambios que fixo.

> [!TIP]
> Existen [seis tipos de estado](system.md#status-types) para as tarefas ou os procesos. Ademais, a maioría dos procesos [dependen doutros procesos descendentes](system.md#refresh-policies). Pode seleccionar o estado dun proceso para ver detalles sobre o progreso de todo o traballo. Despois de seleccionar **Ver detalles** para unha das tarefas do traballo, atopará información adicional: o tempo de procesamento, a última data de procesamento e todos os erros e avisos asociados á tarefa.

## <a name="next-step"></a>Seguinte paso

Configure [actividades](activities.md), [enriquecemento](enrichment-microsoft-graph.md) ou [relacións](relationships.md) para obter máis información sobre os seus clientes.

Se xa configurou actividades, enriquecemento ou relacións ou se definiu segmentos, procesaranse automaticamente para usar os datos máis recentes do cliente.




[!INCLUDE[footer-include](../includes/footer-banner.md)]