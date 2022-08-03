---
title: Buscar clientes similares con IA (vista previa) (contén vídeo)
description: Atope segmentos de clientes similares con intelixencia artificial.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-segment-builder
- ci-segment-insights
- customerInsights
ms.openlocfilehash: 09fe36a4da45d114cbfccf8dad1e7b80b4b7e320
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170725"
---
# <a name="find-similar-customers-with-ai-preview"></a>Buscar clientes similares con IA (vista previa)

Busque clientes similares na súa base de clientes mediante intelixencia artificial. Necesitas polo menos un segmento creado para usar esta función. Ampliar os criterios dun segmento existente axuda a atopar clientes que sexan similares a ese segmento.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWOFou]

> [!NOTE]
> *Atopar clientes similares* utiliza medios automatizados para avaliar datos e facer predicións baseándose neses datos. Polo tanto, ten a capacidade de ser utilizado como método de elaboración de perfiles, tal e como o define o Regulamento Xeral de Protección de Datos ("GDPR"). O uso desta función para o procesamento de datos por parte do cliente pode estar suxeito a RXPD ou a outras leis ou regulamentos. Vostede é responsable de garantir que o seu uso de Dynamics 365 Customer Insights, incluíndo as predicións, cumpre con todas as leis e regulamentos aplicables, incluídas as leis relacionadas coa privacidade, os datos persoais, os datos biométricos, a protección de datos e a confidencialidade das comunicacións.

## <a name="find-similar-customers"></a>Buscar clientes semellantes

1. Ir a **Segmentos** e selecciona o segmento no que queres basear o teu novo segmento. Ese é o seu *segmento de orixe*.

1. Seleccione **Atopar clientes similares**.

1. Revise o nome suxerido para o seu novo segmento e cámbieo se é necesario.

1. Opcionalmente, engadir [etiquetas](work-with-tags-columns.md#manage-tags) ao novo segmento.

1. Revise os campos que definen o seu novo segmento. Estes campos definen a base sobre a que o sistema tratará de atopar clientes similares ao seu segmento de orixe. O sistema selecciona os campos recomendados por defecto. Se é necesario, engade máis campos.
  Os campos que poden reducir significativamente o rendemento do modelo quedan automaticamente excluídos:
  
   - Campos cos seguintes tipos de datos: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType
   - Campos cunha cardinalidade (o número de elementos dun campo) de menos de 2 ou máis de 30

1. Escolle se queres incluír **Todos os clientes** excepto o segmento de orixe ou só os clientes en a **segmento diferente** no teu novo segmento.

1. De xeito predeterminado, o sistema suxire incluír só o 20 % do tamaño do público obxectivo nos seus resultados. Edite este limiar segundo sexa necesario. Aumentar o limiar reducirá a precisión.

1. Inclúa clientes no seu segmento de orixe seleccionando o **Inclúe membros do segmento de orixe ademais de clientes con atributos similares** caixa de verificación.

1. Seleccione **Corre** na parte inferior da páxina para comezar a [tarefa de clasificación binaria](#about-similarity-scores) (un método de Aprendizaxe automático) que analiza o conxunto de datos.

## <a name="view-the-similar-segment"></a>Ver o segmento similar

Despois de procesar o segmento similar, atoparás o novo segmento que aparece na lista **Segmentos** páxina co tipo **Expansión**.

Seleccione **Ver** para ver a distribución dos resultados [puntuacións de semellanza](#about-similarity-scores) e valores de puntuación de semellanza baixo **Vista previa dos membros do segmento**.

:::image type="content" source="media/expanded-segment.png" alt-text="Segmento de clientes similar.":::

## <a name="manage-a-similar-segment"></a>Xestionar un segmento similar

[Traballar e xestionar un segmento similar](segments.md#manage-existing-segments) como fai con outros segmentos. Por exemplo, exporte o segmento ou cree unha medida.

Edita, actualiza, renomea, descarga e elimina un segmento similar. Ao editar un segmento similar reprocesa os teus datos. O segmento creado anteriormente actualízase con datos actualizados.

## <a name="about-similarity-scores"></a>Acerca das puntuacións de semellanza

O modelo de aprendizaxe automática de clasificación binaria asigna unha puntuación aos clientes do segmento similar. A puntuación baséase na semellanza con clientes do segmento de orixe.

- Os resultados de semellanza por baixo de 0,55 son os clientes que o sistema clasificou como *non semellante* aos clientes do segmento de orixe
- As puntuacións de semellanza entre 0,55 e 0,7 clasifícanse como *algo semellante*
- As puntuacións de semellanza entre 0,7 e 0,85 clasifícanse como *semellante*
- As puntuacións de semellanza entre 0,85 e 1 son clientes que o sistema clasificou como *moi semellante*

Os clientes con puntuacións de semellanza inferiores a 0,4 non se inclúen nos resultados do modelo. O sistema non os considera suficientemente semellantes ao segmento de orixe.

[!INCLUDE [footer-include](includes/footer-banner.md)]
