---
title: Segmentos suxeridos en función de medidas (vista previa)
description: Permita que a aprendizaxe automática lle axude a atopar segmentos novos e interesantes baseados nos atributos do cliente.
ms.date: 10/15/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
searchScope:
- ci-segment-suggestions
- customerInsights
ms.openlocfilehash: e3f504827029afa12c65ec6f065a62606aaa823f
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170955"
---
# <a name="suggested-segments-based-on-measures-preview"></a>Segmentos suxeridos en función de medidas (vista previa)

Descubra segmentos interesantes dos seus clientes coa axuda dun modelo IA. Esta función baseada na aprendizaxe automática suxire segmentos baseados en medidas ou atributos do cliente. Pode axudar a mellorar os seus indicadores clave de rendemento (KPI) ou comprender mellor a influencia dos atributos no contexto doutros atributos.

> [!NOTE]
> A función de segmentos suxeridos usa medios automatizados para avaliar os datos e facer predicións baseadas neses datos. Polo tanto, ten a capacidade de utilizarse como método de elaboración de perfiles, tal e como o define o Regulamento Xeral de Protección de Datos ("GDPR"). O uso desta función para procesar datos pode estar suxeito ao RXPD ou a outras leis ou regulamentos. Vostede é responsable de garantir que o seu uso de Dynamics 365 Customer Insights, incluída esta función, cumpre con todas as leis e regulamentos aplicables, incluídas as leis relacionadas coa privacidade, os datos persoais, os datos biométricos, a protección de datos e a confidencialidade das comunicacións.

:::image type="content" source="media/suggested-segments.png" alt-text="Páxina de segmentos suxeridos que mostra detalles dunha suxestión nun panel lateral.":::

## <a name="suggested-segments-to-improve-your-kpis"></a>Segmentos suxeridos para mellorar os seus KPI

Se usas [medidas creadas](measures.md) para axudar a rastrexar os seus KPI, cree segmentos para ver as influencias no KPI. Podes usar esta información para realizar unha campaña altamente orientada.

Por exemplo, fai un seguimento dunha medida chamada *TotalSpendPerCustomer*. Como empresa, gustaríalle ver medrar este número. Escollendo unha medida como atributo principal, selecciona os atributos que queres avaliar para a súa influencia. Digamos *nivel de adhesión*, *período de adhesión* e *ocupación*. Customer Insights pode suxerir un segmento que lle indique cal é a maior influencia desa medida. Por exemplo, os *contables* quen son membros *Gold* e que estiveron coa súa empresa durante *polo menos cinco anos* son a maior influencia de *TotalSpendPerCustomer*. Obterá un tamaño estimado de segmento por cada suxestión. Pode usar esta información para crear campañas para o público orientado.

## <a name="understand-what-influences-a-customer-attribute"></a>Comprender que inflúe nun atributo de cliente

Pode escoller un atributo de cliente en lugar dunha medida como atributo principal. En función da súa elección de atributos de influencia, o modelo IA crea unha serie de suxestións que mostran como inflúen os atributos seleccionados no atributo principal.

Por exemplo, vostede escolle *Membro de Rewards (Si/Non)* como atributo principal. *Antigüidade*, *Ocupación* e *Número de tíckets de asistencia* establécense como outros atributos de influencia. O modelo IA podería suxerir que os segmentos que indican que son membros de Rewards son principalmente profesionais de TI cunha antigüidade superior a dous anos. Outra suxestión podería resaltar que os contables con antigüidade superior a un ano e menos de tres tíckets de asistencia son membros de Rewards.

## <a name="artificial-intelligence-usage"></a>Uso de intelixencia artificial

Usando o atributo principal e os atributos de influencia, un algoritmo de árbore de decisión suxire segmentos interesantes. As suxestións baséanse en regras ou padróns recollidos polo algoritmo de IA. Só se mostran como suxestións os segmentos que difiren significativamente da poboación media. A comparación coa poboación media baséase na medida ou atributo primario seleccionado.

### <a name="responsible-ai"></a>IA responsable

Cos segmentos suxeridos, selecciona atributos para crear novos segmentos e procesar os datos que seleccione. Ao elixir atributos, incluídos atributos confidenciais como a raza, a orientación sexual ou o sexo, debe asegurarse de que pode e debe procesar eses datos. Vostede é responsable de cumprir as leis aplicables á súa organización e cumprir os principios e políticas de privacidade da súa organización.

### <a name="different-results-for-primary-attributes-with-categorical-and-numeric-values"></a>Diferentes resultados para atributos primarios con valores numéricos e categóricos

As suxestións de segmentos son diferentes se escolle un atributo numérico ou un atributo categórico como atributo principal. Os valores dun atributo categórico conteñen dúas ou máis categorías ou tipos. Un atributo numérico contén datos cuantitativos e ten asociado un sentido da medida.

Cun atributo numérico como *ingresos anuais* ou *período de adhesión* como atributo principal, o sistema suxire segmentos que teñen un valor medio maior ou menor do atributo numérico cando se compara con todos os clientes.

Un atributo categórico como a *satisfacción do cliente* como o atributo principal resulta en segmentos suxeridos que teñen unha porcentaxe maior ou menor de clientes pertencentes a unha categoría determinada cando se compara coa porcentaxe de todos os clientes pertencentes a esa mesma categoría. Por exemplo, a *satisfacción do cliente* escóllese como atributo principal e consta de tres categorías (*Baixa*, *Media* e *Alta*). Para cada categoría, suxeriranse segmentos que teñan unha porcentaxe maior ou menor de clientes pertencentes a esa categoría en comparación coa proporción de todos os clientes da mesma categoría. Se o 22 % de todos os clientes teñen unha satisfacción *alta*, pois, só os segmentos que teñan unha proporción maior ou menor de clientes cunha satisfacción *alta* en comparación co 22 % suxerirase para esa categoría. Do mesmo xeito, suxeriranse segmentos para cada unha das outras categorías (*Baixa* e *Media*) se son estatisticamente significativos.

> [!NOTE]
> Actualmente, só admitimos atributos categóricos primarios que teñen ata 10 categorías. Se queres ver suxestións de segmentos baseadas nun atributo principal con máis de 10 categorías, recomendamos agrupar algunhas das categorías para reducir o número de categorías a 10 ou menos. Esta limitación só se aplica aos atributos primarios. Para influír nos atributos categóricos, actualmente admitimos un máximo de 100 categorías.

## <a name="generate-suggested-segments"></a>Xerar segmentos suxeridos

1. Ir a **Segmentos** e selecciona o **Suxestións (vista previa)** ficha.

1. Seleccione **Busca novas suxestións** e escolle **Mellorar unha medida/métrica**. Seleccione **Comeza**.

   :::image type="content" source="media/suggested-segments-measure.png" alt-text="Elixir unha medida de mellora nos segmentos suxeridos.":::

1. Escolla un atributo ou medida do cliente como atributo principal e selecciónelo **A continuación**.

1. Seleccione os atributos de influencia e seleccione **Corre**.

   > [!TIP]
   > Seleccionar múltiples atributos de influencia mellora as posibilidades de avaliar como inflúen no atributo principal. Non inclúa atributos que non teñan influencia sobre o atributo principal. Por exemplo, se todos os seus clientes son dun país específico, non inclúa o atributo *país* porque non terá ningún impacto nos resultados.

Dependendo do número de perfís de clientes e dos atributos seleccionados, pode levar uns minutos procesar os atributos seleccionados.

## <a name="manage-suggested-segments"></a>Xestionar segmentos suxeridos

Ir a **Segmentos** e selecciona o **Suxestións (vista previa)** ficha. No **Suxestións de segmentos baseados en atributos** sección, seleccione un segmento suxerido para ver as accións dispoñibles.

- **Ver** os detalles do segmento suxeridos e os valores de atributos ou regras que aprendeu o modelo de IA.
- **Gardar como segmento** a suxestión como segmento. Aparece no **Todos os segmentos** ficha e pode ser [actualizado, editado ou eliminado](segments.md).
- **Editar atributos** e modificar os atributos configurados que substituirán as suxestións actuais.
- **Actualizar suxestións** para actualizar as suxestións mantendo os atributos configurados.

## <a name="limitations"></a>Limitacións

1. Non coincide o tamaño do segmento estimado: se escolle un atributo principal que conteña valores baleiros, pode afectar o tamaño do segmento estimado nas suxestións de segmento. Ao gardar tal segmento, o tamaño real do segmento pode ser diferente á estimación orixinal.

2. Os atributos primarios de tipo booleano non funcionan: actualmente só admitimos tipos de datos de cadeas e numéricos como atributo principal.

3. Os segmentos suxeridos non son o suficientemente distintos: teña en conta que os atributos seleccionados e a distribución de valores deses atributos inflúen nos resultados. Pode cambiar os seus atributos de influencia ou incluso o seu atributo principal para obter resultados diferentes.

[!INCLUDE [footer-include](includes/footer-banner.md)]