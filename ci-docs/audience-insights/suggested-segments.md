---
title: Segmentos suxeridos con tecnoloxía de aprendizaxe automática
description: Permita que a aprendizaxe automática lle axude a atopar segmentos novos e interesantes baseados nos atributos do cliente.
ms.date: 02/01/2021
ms.reviewer: jimsonc
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 54655d57f4f0f723b497fe47891fd397ccb9dbf4
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268224"
---
# <a name="suggested-segments-preview"></a>Segmentos suxeridos (versión preliminar)

Descubra segmentos interesantes dos seus clientes coa axuda dun modelo IA. Esta función baseada na aprendizaxe automática suxire segmentos baseados en medidas ou atributos do cliente. Pode axudar a mellorar os seus KPI ou comprender mellor a influencia dos atributos no contexto doutros atributos. 

> [!NOTE]
> A función de segmentos suxeridos emprega medios automatizados para avaliar datos e facer predicións en función deses datos e, polo tanto, ten a capacidade de usarse como método de creación de perfís, tal e como ese termo está definido polo Regulamento xeral de protección de datos ("RXPD"). O uso desta función para procesar datos pode estar suxeito ao RXPD ou a outras leis ou regulamentos. Vostede é responsable de garantir que o seu uso de Dynamics 365 Customer Insights, incluída esta función, cumpre con todas as leis e regulamentos aplicables, incluídas as leis relacionadas coa privacidade, os datos persoais, os datos biométricos, a protección de datos e a confidencialidade das comunicacións.

:::image type="content" source="media/suggested-segments-details.png" alt-text="Páxina de segmentos suxeridos en Customer Insights que amosa detalles dunha suxestión nun panel lateral.":::

## <a name="suggested-segments-to-improve-your-kpis"></a>Segmentos suxeridos para mellorar os seus KPI

Como usuario da información sobre o público, é probable que teña unha serie de [medidas creadas](measures.md) que axudan a rastrexar os seus indicadores clave de rendemento (KPI). É importante comprender como determinados atributos inflúen neste KPI para crear segmentos e realizar unha campaña altamente orientada.   
Por exemplo, fai un seguimento dunha medida chamada *TotalSpendPerCustomer*. Como empresa, gustaríalle ver medrar este número. Se escolle unha medida como atributo principal, permítelle seleccionar os atributos que desexa avaliar por influencia. Digamos *nivel de adhesión*, *período de adhesión* e *ocupación*. Customer Insights pode suxerir un segmento que lle indique cal é a maior influencia desa medida. Por exemplo, os *contables* quen son membros *Gold* e que estiveron coa súa empresa durante *polo menos cinco anos* son a maior influencia de *TotalSpendPerCustomer*. Obterá un tamaño estimado de segmento por cada suxestión. Pode usar esta información para crear campañas para o público orientado.

## <a name="understand-what-influences-a-customer-attribute"></a>Comprender que inflúe nun atributo de cliente

Pode escoller un atributo de cliente en lugar dunha medida como atributo principal. En función da súa elección de atributos de influencia, o modelo IA crea unha serie de suxestións que mostran como inflúen os atributos seleccionados no atributo principal.   
Por exemplo, vostede escolle *Membro de Rewards (Si/Non)* como atributo principal. *Antigüidade*, *Ocupación* e *Número de tíckets de asistencia* establécense como outros atributos de influencia. O modelo IA podería suxerir que os segmentos que indican que son membros de Rewards son principalmente profesionais de TI cunha antigüidade superior a dous anos. Outra suxestión podería resaltar que os contables con antigüidade superior a un ano e menos de tres tíckets de asistencia son membros de Rewards. 

## <a name="artificial-intelligence-usage"></a>Uso de intelixencia artificial

Usando o atributo principal e os atributos de influencia, un algoritmo de árbore de decisión suxire segmentos interesantes. As suxestións baséanse en regras ou padróns recollidos polo algoritmo de IA. Só se mostran como suxestións os segmentos que difiren significativamente da poboación media. A comparación coa poboación media baséase na medida ou atributo primario seleccionado.

### <a name="responsible-ai"></a>IA responsable

Os segmentos suxeridos permítenlle seleccionar atributos para crear novos segmentos e procesar os datos que seleccione. Ao elixir atributos, incluídos atributos confidenciais como a raza, a orientación sexual ou o sexo, debe asegurarse de que pode e debe procesar eses datos. Vostede é responsable de cumprir as leis aplicables á súa organización e cumprir os principios e políticas de privacidade da súa organización.

### <a name="different-results-for-primary-attributes-with-categorical-and-numeric-values"></a>Diferentes resultados para atributos primarios con valores numéricos e categóricos

As suxestións de segmentos son diferentes se escolle un atributo numérico ou un atributo categórico como atributo principal. Os valores dun atributo categórico conteñen dúas ou máis categorías ou tipos. Un atributo numérico contén datos cuantitativos e ten asociado un sentido da medida.

Cun atributo numérico como *ingresos anuais* ou *período de adhesión* como atributo principal, o sistema suxire segmentos que teñen un valor medio maior ou menor do atributo numérico cando se compara con todos os clientes.

Un atributo categórico como a *satisfacción do cliente* como o atributo principal resulta en segmentos suxeridos que teñen unha porcentaxe maior ou menor de clientes pertencentes a unha categoría determinada cando se compara coa porcentaxe de todos os clientes pertencentes a esa mesma categoría. Por exemplo, a *satisfacción do cliente* escóllese como atributo principal e consta de tres categorías (*Baixa*, *Media* e *Alta*). Para cada categoría, suxeriranse segmentos que teñan unha porcentaxe significativamente maior ou menor de clientes pertencentes a esa categoría en comparación coa proporción de todos os clientes da mesma categoría. Se o 22 % de todos os clientes teñen unha satisfacción *Alta*, entón, só os segmentos que teñen unha proporción significativamente maior ou menor de clientes cunha satisfacción *Alta* suxeriranse fronte ao 22 % para esa categoría. Do mesmo xeito, suxeriranse segmentos para cada unha das outras categorías (*Baixa* e *Media*) se son estatisticamente significativos.

> [!NOTE]
> Actualmente, só admitimos atributos categóricos primarios que teñen ata 10 categorías. Se desexa ver suxestións de segmentos baseadas nun atributo principal con máis de 10 categorías, recomendamos agrupar algunhas das categorías para reducir o número de categorías a 10 ou menos. Esta limitación só se aplica aos atributos primarios. Para influír nos atributos categóricos, actualmente admitimos un máximo de 100 categorías.

## <a name="generate-suggested-segments"></a>Xerar segmentos suxeridos

1. Vaia a **Segmentos**.

1. Seleccione o separador **Suxestións (versión preliminar)**.

1. Seleccione **Recibir novas suxestións** para comezar a experiencia guiada.

1. Escolla unha medida ou un atributo de cliente como atributo principal e seleccione **Seguinte**.

   :::image type="content" source="media/suggested-segments-primary-attribute.png" alt-text="Escolla o atributo principal para suxestións sobre os segmentos suxeridos.":::

1. Seleccione os atributos de influencia e seleccione **Gardar**.
   
   > [!TIP]
   > Seleccionar múltiples atributos de influencia mellora as posibilidades de avaliar como inflúen no atributo principal. Non inclúa atributos que non inflúan no atributo principal. Por exemplo, se todos os seus clientes son dun país específico, non inclúa o atributo *país* porque non terá ningún impacto nos resultados.

1. Dependendo do número de perfís de clientes e dos atributos seleccionados, pode levar uns minutos procesar os atributos seleccionados. 

## <a name="view-details-of-a-suggested-segment"></a>Ver detalles dun segmento suxerido

Unha vez que o modelo IA xerou as suxestións, atoparaas enumeradas en **Segmentos** > **Suxestións (versión preliminar)**.
 
Seleccione un segmento suxerido para revisar os detalles desa suxestión, incluíndo unha comparación do valor medio e do número de membros do segmento. Tamén pode revisar os valores ou as regras dos atributos que o modelo IA aprendeu para suxerir o segmento seleccionado.

## <a name="save-a-suggestion-as-a-segment"></a>Gardar unha suxestión como segmento

1. Vaia a **Segmentos** > **Suxestións (versión preliminar)**.

1. Seleccione o segmento que quere gardar. 

1. No panel lateral, seleccione **Gardar como segmento**. 

1. Despois de gardar o segmento, mostrarase na lista de segmentos do separador **Todos os segmentos**. Agora pode ser [actualizado, editado ou eliminado como calquera outro segmento](segments.md).

## <a name="refresh-or-edit-a-set-of-suggestions"></a>Actualizar ou editar un conxunto de suxestións

1. Vaia a **Segmentos** > **Suxestións (versión preliminar)**.

1. Seleccione **Actualizar suxestións** para actualizar as suxestións mantendo os atributos configurados. Ou seleccione **Editar atributos** para modificar os atributos configurados. O sistema volverá executar o modelo IA, xerará suxestións de segmentos baseadas nos últimos datos e substituirá as suxestións actuais.

## <a name="limitations"></a>Limitacións

1. Non coincide o tamaño do segmento estimado: se escolle un atributo principal que conteña valores baleiros, pode afectar o tamaño do segmento estimado nas suxestións de segmento. Ao gardar tal segmento, o tamaño real do segmento pode ser diferente á estimación orixinal.
 
2. Os atributos primarios de tipo booleano non funcionan: actualmente só admitimos tipos de datos de cadeas e numéricos como atributo principal.

3. Os segmentos suxeridos non son o suficientemente distintos: teña en conta que os atributos seleccionados e a distribución de valores deses atributos inflúen nos resultados. Pode cambiar os seus atributos de influencia ou incluso o seu atributo principal para obter resultados diferentes.



[!INCLUDE[footer-include](../includes/footer-banner.md)]