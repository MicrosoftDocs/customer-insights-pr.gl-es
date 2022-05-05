---
title: Segmentos suxeridos baseados na actividade.
description: Permita que a aprendizaxe automática lle axude a atopar segmentos novos e interesantes baseados na actividade dos clientes.
ms.date: 05/11/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
searchScope:
- ci-segment-suggestions
- customerInsights
ms.openlocfilehash: 85c3cef3a8d531b31b64a7e5decbdc122c4383fc
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642745"
---
# <a name="suggested-segments-based-on-activity-data-preview"></a>Segmentos suxeridos baseados nos datos de actividade (visión preliminar)

Descubra segmentos interesantes dos seus clientes baseados nos datos da súa actividade que se inxiren en Customer Insights. Exemplos de datos de actividade son as transaccións, a duración das chamadas de asistencia técnica, as compras ou as devolucións. Para suxerir segmentos, os datos de actividade analízanse por actualidade, frecuencia e valor monetario (ou duración). Como alternativa, pode xerar [segmentos suxeridos para mellorar unha medida ou comprender mellor o que inflúe nun atributo](suggested-segments.md).

:::image type="content" source="media/suggested-segments-tab.png" alt-text="Separador de segmentos suxeridos que mostra suxestións de segmentos para segmentos baseados na actividade e nos atributos.":::

## <a name="categorize-customers-by-activity"></a>Categorizar os clientes por actividade

Cos [datos de actividade](activities.md) dispoñibles en Customer Insights, podemos xerar suxestións que representen grupos de clientes:

- clientes máis activos 
- clientes que máis compras fixeron 
- clientes que máis ingresos xeraron 
- clientes que non estiveron activos ultimamente 
- clientes que interactúan frecuentemente coa súa empresa  

Se ten unha empresa minorista, pode descubrir cales son os clientes que máis ingresos xeran e recompensalos cun cupón. Tamén pode identificar os clientes ocasionais e ofrecerlles unirse a un programa de recompensas para que visiten a súa empresa con máis frecuencia.
Traballa no sector sanitario, ofrece asistencia sanitaria pública e o seu obxectivo é minimizar os gastos dos pacientes individuais. Un xeito de facelo podería ser mediante a redución das visitas periódicas, proporcionando a mellor atención posible no menor número de visitas posible. Neste caso, o seu obxectivo é manter baixa a frecuencia de visita e minimizar os custos periódicos para os pacientes. Tamén pode identificar segmentos de pacientes que teñen compromisos frecuentes e elevados custos periódicos e analizar eses casos para mellorar o seu tratamento. 

## <a name="required-data"></a>Datos necesarios

As suxestións xéranse en función dos datos de entrada seleccionados. 

- Perfís de clientes: todos os clientes ou membros dun segmento específico. 

- Período de tempo: o mes pasado, o ano pasado ou calquera intervalo temporal personalizado.

- Tipo de actividade: compras, transaccións minoristas, transaccións en liña, casos de asistencia técnica, subscricións etc.  

- A entidade de Customer Insights que contén os datos da actividade: a entidade UnifiedActivity ou a entidade para unha actividade específica. 

- Dimensións que se inclúen: actualidade, frecuencia ou dimensión monetaria, dependendo das necesidades da súa empresa.

## <a name="generate-suggested-segments"></a>Xerar segmentos suxeridos

1. Vaia a **Segmentos**.

1. Seleccione o separador **Suxestións (versión preliminar)**.

1. Seleccione **Buscar novas suxestións** e elixa **Ver ou anticipar o comportamento do cliente**. Seleccione **Iniciar** para executar a experiencia guiada.

   :::image type="content" source="media/suggested-segments-activity-wizard.png" alt-text="Primeiro paso do asistente de configuración para un segmento suxerido baseado na actividade.":::

1. Proporcione os datos de entrada necesarios e seleccione **Seguinte** para continuar.

   - Elección de clientes: inclúa todos os clientes ou un segmento específico.
   - Elección de actividade: seleccione o tipo de actividade e as entidades que a describen.
   - Preferencias: defina o período de tempo que se considerará, os factores para as suxestións e asigne os atributos.

1. Revise a entrada e seleccione **Executar** para executar o modelo e xerar suxestións.

1. En función do número de perfís de clientes e das actividades seleccionadas, pode tardar uns minutos en completarse. 

Despois de xerar as suxestións, pode filtralas pola dimensión ou o valor que máis lle interese. 

## <a name="view-details-of-a-suggested-segment"></a>Ver detalles dun segmento suxerido

Unha vez que se xeran as suxestións, atoparaas na lista **Segmentos** > **Suxestións (versión preliminar)** na sección **Suxestións baseadas na actividade**.

:::image type="content" source="media/suggested-segments-details.png" alt-text="Panel lateral expandido que mostra os datos detallados dun segmento suxerido.":::

Seleccione **Visualizar suxestión** nun segmento suxerido para ver os detalles dese segmento. O panel lateral ofrece detalles como a extensión de cada dimensión en comparación co grupo de destino. Tamén destaca o número de membros potenciais no segmento e a porcentaxe correspondente do total de clientes. Se quere manter a suxestión como un segmento, seleccione **Crear segmento**.    

## <a name="save-a-suggestion-as-a-segment"></a>Gardar unha suxestión como segmento

1. Vaia a **Segmentos** > **Suxestións (versión preliminar)**.

1. Seleccione o segmento que quere gardar. 

1. No panel lateral, seleccione **Crear segmento**. 

1. Despois de gardar o segmento, mostrarase na lista de segmentos do separador **Todos os segmentos**. Agora pode [actualizarse ou eliminarse como calquera outro segmento](segments.md). Non pode editar os detalles do segmento. Non obstante, pode modificar os criterios de entrada das suxestións e xerar diferentes suxestións.

## <a name="refresh-or-edit-a-set-of-suggestions"></a>Actualizar ou editar un conxunto de suxestións

1. Vaia a **Segmentos** > **Suxestións (versión preliminar)** e busque o segmento na sección **Suxestións baseadas na actividade**.

1. Seleccione **Actualizar suxestións** para actualizar as suxestións mantendo os atributos configurados. Tamén pode seleccionar **Editar suxestións** para modificar os atributos configurados. O sistema volverá executar o proceso, xerará suxestións de segmentos baseadas nos últimos datos e substituirá as suxestións actuais.

[!INCLUDE [footer-include](includes/footer-banner.md)]
