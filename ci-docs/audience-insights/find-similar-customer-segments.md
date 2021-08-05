---
title: Buscar clientes semellantes con IA
description: Atope segmentos de clientes similares con intelixencia artificial.
ms.date: 06/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 96fbd18a20e0df7abd4e79ff77e2c3a396e33ccc
ms.sourcegitcommit: dab2cbf818fafc9436e685376df94c5e44e4b144
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 07/13/2021
ms.locfileid: "6554203"
---
# <a name="similar-customers-preview"></a>Clientes similares (vista previa)

Esta característica permítelle atopar clientes similares na súa base de clientes mediante intelixencia artificial. Debe ter polo menos un segmento creado para usar esta función. A expansión dos criterios dun segmento existente axuda a atopar clientes similares a ese segmento.

> [!NOTE]
> *Buscar clientes similares* usa medios automatizados para avaliar datos e facer predicións a partir deses datos e, polo tanto, ten a capacidade de ser utilizado como método de avaliación de perfís, xa que ese termo é definido polo Regulamento xeral de protección de datos ("RXPD"). O uso desta función para o procesamento de datos por parte do cliente pode estar suxeito a RXPD ou a outras leis ou regulamentos. Vostede é responsable de garantir que o seu uso de Dynamics 365 Customer Insights, incluíndo as predicións, cumpre con todas as leis e regulamentos aplicables, incluídas as leis relacionadas coa privacidade, os datos persoais, os datos biométricos, a protección de datos e a confidencialidade das comunicacións.

## <a name="finding-similar-customers"></a>Busca de clientes similares

1. Na información do público, vaia a **Segmentos** e seleccione o segmento no que desexa basear o seu novo segmento. Ese é o seu *segmento de orixe*.

1. Na barra de acción, seleccione **Buscar clientes similares**.

1. Revise o nome suxerido para o seu novo segmento e cámbieo se é necesario.

1. Revise os campos que definen o seu novo segmento. Estes campos definen a base sobre a que o sistema tratará de atopar clientes similares ao seu segmento de orixe. O sistema seleccionará de xeito predeterminado os campos recomendados.
  Os campos que poden reducir significativamente o rendemento do modelo quedan automaticamente excluídos:
  
   - Campos cos seguintes tipos de datos: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType
   - Campos cunha cardinalidade (o número de elementos dun campo) de menos de 2 ou máis de 30

1. Elixa se quere incluír **Todos os clientes** ou só clientes nun **Segmento existente específico** no seu novo segmento.

1. Exclúa os clientes do seu segmento de orixe seleccionando a caixa de verificación **Excluír a todos no segmento de orixe**.

1. De xeito predeterminado, o sistema suxire incluír só o 20 % do tamaño do público obxectivo nos seus resultados. Edite este limiar segundo sexa necesario. Aumentar o limiar reducirá a precisión.

1. Seleccione **Executar** ao final da páxina para iniciar unha tarefa de clasificación binaria (un método de aprendizaxe automática) que analiza o conxunto de datos.

## <a name="view-the-similar-segment"></a>Ver o segmento similar

Despois de procesar o segmento similar, atopará o novo segmento listado na páxina **Segmentos**.

> [!div class="mx-imgBorder"]
> ![Segmento de clientes similar.](media/expanded-segment.png "Segmento de clientes similar")

Seleccione **Ver** na barra de accións para abrir o detalle do segmento. Esta vista contén información sobre a distribución dos resultados en [puntuacións de semellanza](#about-similarity-scores). Tamén atopará os valores de puntuación de semellanza na **Vista previa dos membros do segmento**.

## <a name="use-the-output-of-a-similar-segment"></a>Usar os resultados dun segmento similar

Pode [traballar cos resultados dun segmento similar](segments.md) como fai con outros segmentos. Por exemplo, exporte o segmento ou cree unha medida.

## <a name="refresh-and-edit-a-similar-segment"></a>Actualizar e editar un segmento similar

Para actualizar un segmento similar, seleccióneo na páxina **Segmentos** e seleccione **Actualizar** na barra de accións.

A edición dun segmento similar reprocesará os seus datos. O segmento creado anteriormente actualízase con datos actualizados.    
Para editar un segmento similar, seleccióneo na páxina **Segmentos** e seleccione **Editar** na barra de accións. Aplique os cambios e seleccione **Executar** para iniciar a tramitación.

## <a name="delete-a-similar-segment"></a>Eliminar un segmento similar

Seleccione o segmento na páxina **Segmentos** e seleccione **Eliminar** na barra de accións. Logo confirme a eliminación.

## <a name="about-similarity-scores"></a>Acerca das puntuacións de semellanza

O modelo de aprendizaxe automática de clasificación binaria asigna unha puntuación aos clientes do segmento similar. A puntuación baséase na semellanza con clientes do segmento de orixe.

- Os resultados de semellanza por baixo de 0,55 son os clientes que o sistema clasificou como *non semellante* aos clientes do segmento de orixe
- As puntuacións de semellanza entre 0,55 e 0,7 clasifícanse como *algo semellante*
- As puntuacións de semellanza entre 0,7 e 0,85 clasifícanse como *semellante*
- As puntuacións de semellanza entre 0,85 e 1 son clientes que o sistema clasificou como *moi semellante*

Os clientes con puntuacións de semellanza inferiores a 0,4 non se inclúen nos resultados do modelo. O sistema non os considera suficientemente semellantes ao segmento de orixe.


[!INCLUDE[footer-include](../includes/footer-banner.md)]