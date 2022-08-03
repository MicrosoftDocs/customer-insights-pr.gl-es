---
title: Segmentos suxeridos en función da actividade (vista previa)
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
ms.openlocfilehash: df4f5f4b5c9a3ad66d57a6b349e18a0d714aff62
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170587"
---
# <a name="suggested-segments-based-on-activity-preview"></a>Segmentos suxeridos en función da actividade (vista previa)

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
Se prestas asistencia sanitaria pública e o teu obxectivo é minimizar os gastos dos pacientes individuais, podes intentar reducir as visitas recorrentes proporcionando a mellor atención posible no menor número de visitas posible. Neste caso, o seu obxectivo é manter baixa a frecuencia de visita e minimizar os custos periódicos para os pacientes. Tamén pode identificar segmentos de pacientes que teñen compromisos frecuentes e elevados custos periódicos e analizar eses casos para mellorar o seu tratamento.

## <a name="required-data"></a>Datos necesarios

As suxestións xéranse en función dos datos de entrada seleccionados.

- Perfís de clientes: todos os clientes ou membros dun segmento específico.

- Período de tempo: o mes pasado, o ano pasado ou calquera intervalo temporal personalizado.

- Tipo de actividade: compras, transaccións minoristas, transaccións en liña, casos de asistencia técnica, subscricións etc.  

- A entidade de Customer Insights que contén os datos da actividade: a entidade UnifiedActivity ou a entidade para unha actividade específica.

- Dimensións que se inclúen: actualidade, frecuencia ou dimensión monetaria, dependendo das necesidades da súa empresa.

## <a name="generate-suggested-segments"></a>Xerar segmentos suxeridos

1. Ir a **Segmentos** e selecciona o **Suxestións (vista previa)** ficha.

1. Seleccione **Buscar novas suxestións** e elixa **Ver ou anticipar o comportamento do cliente**. Seleccione **Comeza**.

   :::image type="content" source="media/suggested-segments-activity-wizard.png" alt-text="Primeiro paso do asistente de configuración para un segmento suxerido baseado na actividade.":::

1. Proporcione os datos de entrada necesarios e seleccione **A continuación**.

   - Elección de clientes: inclúa todos os clientes ou un segmento específico.
   - Elección de actividade: seleccione o tipo de actividade e as entidades que a describen.
   - Preferencias: defina o período de tempo que se considerará, os factores para as suxestións e asigne os atributos.

1. Revise a entrada e seleccione **Executar** para executar o modelo e xerar suxestións.

En función do número de perfís de clientes e das actividades seleccionadas, pode tardar uns minutos en completarse.

Despois de xerar as suxestións, pode filtralas pola dimensión ou o valor que máis lle interese.

## <a name="manage-suggested-segments"></a>Xestionar segmentos suxeridos

Ir a **Segmentos** e selecciona o **Suxestións (vista previa)** ficha. No **Suxestións baseadas en actividades** sección, seleccione un segmento suxerido para ver as accións dispoñibles.

- **Ver suxestión** para ver os detalles dese segmento como a extensión de cada dimensión en comparación co grupo obxectivo. Tamén destaca o número de membros potenciais no segmento e a porcentaxe correspondente do total de clientes.
- **Crear segmento** para gardar o suxerido como un segmento. Aparece no **Todos os segmentos** ficha e pode ser [actualizado ou eliminado](segments.md). Non pode editar os detalles do segmento. Non obstante, pode modificar os criterios de entrada das suxestións e xerar diferentes suxestións.
- **Editar suxestións** para modificar os atributos configurados que substituirán as suxestións actuais.
- **Actualizar suxestións** para actualizar as suxestións mantendo os atributos configurados.

[!INCLUDE [footer-include](includes/footer-banner.md)]
