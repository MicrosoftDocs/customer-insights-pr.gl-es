---
title: Predicir recomendacións de produtos
description: Prediga os produtos cos que é probable que un cliente interactúe ou adquira.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: 0057d6796bb60db44d08b58d9e0daaf6e7c90fde
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610280"
---
# <a name="predict-product-recommendations"></a>Predicir recomendacións de produtos

O modelo de recomendación de produtos crea conxuntos de recomendacións de produtos preditivas. As recomendacións baséanse no comportamento de compra anterior e en clientes con padróns de compra similares. Este modelo é para consumidores individuais (B-to-C).

Debes ter coñecementos comerciais sobre os diferentes tipos de produtos para a túa empresa e como interactúan os teus clientes con eles. Admitimos recomendar produtos que xa compraron os seus clientes ou recomendacións de novos produtos.

As recomendacións de produtos poden estar suxeitas ás leis e regulacións locais e ás expectativas dos clientes, que o modelo non está construído para ter en conta especificamente. Polo tanto, **debe revisar as recomendacións antes de entregalas aos seus clientes** para asegurarse de que cumpre as leis ou regulamentos aplicables e as expectativas dos clientes sobre o que pode recomendar.

A saída deste modelo ofrece recomendacións baseadas no ID do produto. O teu mecanismo de entrega debe asignar os ID de produto previstos ao contido axeitado para que os teus clientes teñan en conta a localización, o contido de imaxe e outro contido ou comportamento específicos da empresa.

> [!TIP]
> Proba a recomendación de produto predición usando datos de mostra: [Guía de exemplo de recomendación de produtos predición](sample-guide-predict-product-recommendation.md).

## <a name="prerequisites"></a>Requisitos previos

- Polo menos [Permisos de colaborador](permissions.md)
- Polo menos 100 clientes, preferiblemente máis de 10.000 clientes.
- Identificador de cliente, un identificador único para relacionar transaccións cun cliente individual
- Polo menos un ano de datos transaccionais, preferiblemente de dous a tres anos para incluír algunha estacionalidade. Idealmente, polo menos tres ou máis transaccións por ID de cliente. O historial de transaccións debe incluír:
  - **ID de transacción** : identificador único dunha compra ou transacción.
  - **Data da transacción** : Data da compra ou transacción.
  - **Valor da transacción** : Valor numérico da compra ou transacción.
  - **ID de produto único** : ID do produto ou servizo adquirido se os seus datos están nun nivel de liña.
  - **Compra ou devolución** : un valor booleano verdadeiro/falso onde *verdade* identifica que unha transacción foi unha devolución. Se os datos de Compra ou Devolución non se fornecen no modelo e no **Valor da transacción** é negativo, inferimos un retorno.
- Unha entidade de datos do catálogo de produtos para usar como filtro de produto.

> [!NOTE]
> - O modelo require o historial de transaccións dos teus clientes, onde a transacción é calquera dato que describa unha interacción usuario-produto. Por exemplo, mercar un produto, tomar unha clase ou asistir a un evento.
> - Só se pode configurar unha entidade do historial de transaccións. Se hai varias entidades de compra, combínaas Power Query antes da inxestión de datos.
> - Se os detalles da orde e dos pedidos son entidades diferentes, únaas antes de empregalas no modelo. O modelo non funciona só cun ID de pedido ou ID de recibo nunha entidade.

## <a name="create-a-product-recommendation-prediction"></a>Crear unha predición de recomendacións de produtos

Seleccione **Garda o borrador** en calquera momento para gardar o predición como borrador. O borrador predición móstrase no **As miñas predicións** ficha.

1. Ir a **Intelixencia** > **Predicións**.

1. No **Crear** ficha, seleccione **Usa modelo** no **Recomendacións de produtos (vista previa)** tella.

1. Seleccione **Comezar**.

1. **Poña nome a este modelo** e o **Nome da entidade de saída** para distinguilos doutros modelos ou entidades.

1. Seleccione **Seguinte**.

### <a name="define-product-recommendation-preferences"></a>Definir as preferencias de recomendación de produtos

1. Establece o **Número de produtos** para recomendar a un cliente. Este valor depende de como o método de entrega enche os datos.

1. Escolla se quere incluír produtos que os clientes compraron anteriormente na páxina **Se esperan compras repetidas** campo.

1. Establece o **Mira cara atrás fiestra** co período de tempo que o modelo considera antes de recomendar de novo o produto ao usuario. Por exemplo, indica que un cliente compra un portátil cada dous anos. O modelo analiza o historial de compras dos últimos dous anos e, se atopa un artigo, fíltrase a partir das recomendacións.

1. Seleccionar **Seguinte**

### <a name="add-purchase-history"></a>Engadir historial de compra

1. Seleccione **Engadir datos** para **Historial de transaccións do cliente**.

1. Seleccione o tipo de actividade semántica **Liña de pedidos de vendas** que conteña a información necesaria sobre o historial de transaccións ou compras. Se a actividade non está configurada, seleccione **aquí** e crealo.

1. Baixo **Actividades**, se os atributos da actividade foron mapeados semanticamente cando se creou a actividade, escolla os atributos ou a entidade específicos nos que desexa que se centre o cálculo. Se non se produciu a asignación semántica, seleccione **Editar** e mapea os teus datos.

   :::image type="content" source="media/product-recommendation-select-semantic-activity.PNG" alt-text="Panel lateral que mostra a elección de actividades específicas baixo o tipo semántico.":::

1. Seleccione **A continuación** e revise os atributos necesarios para este modelo.

1. Seleccione **Gardar**.

1. Seleccione **Seguinte**.

### <a name="add-product-information-and-filters"></a>Engade información sobre produtos e filtros

Ás veces, só certos produtos son beneficiosos ou apropiados para o tipo de predición que constrúe. Use filtros de produtos para identificar un subconxunto de produtos con características específicas para recomendar aos seus clientes. O modelo empregará todos os produtos dispoñibles para aprender padróns, pero só empregará os produtos que coincidan co filtro de produto na súa saída.

1. Engade a túa entidade de catálogo de produtos que conteña información de cada produto. Mapea a información requirida e selecciona **Gardar**.

1. Seleccione **Seguinte**.

1. Seleccione **Filtros de produtos**:

   - **Sen filtros**: Use todos os produtos na predición de recomendacións de produtos.

   - **Definir filtros de produtos específicos**: Use produtos específicos na predición de recomendacións de produtos. No **Atributos do catálogo de produtos** panel, seleccione os atributos da entidade do catálogo de produtos que quere incluír no filtro.

     :::image type="content" source="media/product-filters-sidepane.png" alt-text="Panel lateral que mostra os atributos na entidade do catálogo de produtos para seleccionar os filtros de produtos.":::

1. Escolle se queres que use o filtro do produto **e** ou **ou** para combinar loxicamente a súa selección de atributos do catálogo de produtos.

   :::image type="content" source="media/product-filters-sample.png" alt-text="Configuración de mostra de filtros de produtos combinados con conectores AND lóxicos.":::

1. Seleccione **Seguinte**.

### <a name="set-update-schedule"></a>Definir programación de actualizacións

1. Escolle unha frecuencia para reciclar o teu modelo. Esta opción de configuración é importante para actualizar a precisión das predicións a medida que se inxiren novos datos en Customer Insights. A maioría das empresas poden volverse formar unha vez ao mes e obter unha boa precisión para a súa predición.

1. Seleccione **Seguinte**.

### <a name="review-and-run-the-model-configuration"></a>Revisar e executar a configuración do modelo

O **Revisa e corre** O paso mostra un resumo da configuración e ofrece a oportunidade de facer cambios antes de crear o predición.

1. Seleccione **Editar** en calquera dos pasos para revisar e facer calquera cambio.

1. Se estás satisfeito coas túas seleccións, selecciona **Garda e executa** para comezar a executar o modelo. Seleccione **Feito**. O **As miñas predicións** aparece a pestana mentres se crea o predición. O proceso pode levar varias horas en función da cantidade de datos empregados na predición.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Ver os resultados de predición

1. Ir a **Intelixencia** > **Predicións**.

1. No **As miñas predicións** pestana, seleccione o predición que quere ver.

Hai cinco seccións principais de datos dentro da páxina de resultados.

- **Rendemento do modelo:** As notas A, B ou C indican o rendemento do predición e poden axudarche a tomar a decisión de usar os resultados almacenados na entidade de saída.
  
  :::image type="content" source="media/product-recommendation-modelperformance.PNG" alt-text="Imaxe do resultado do rendemento do modelo coa nota A.":::

  As cualificacións determínanse en función das seguintes regras:
  - **A** cando a métrica "Éxito @ K" é polo menos un 10 % máis que a liña base.
  - **B** cando a métrica "Éxito @ K" é do 0% ao 10% máis que a liña de base.
  - **C** cando a métrica "Éxito @ K" é menor que a liña base.
  - **Liña base** : Os produtos máis recomendados por compra recóllense en todos os clientes + regras aprendidas identificadas polo modelo = un conxunto de recomendacións para os clientes. As predicións compáranse cos principais produtos, calculados polo número de clientes que compraron o produto. Se un cliente ten polo menos un produto recomendado que tamén se viu nos produtos máis vendidos, considérase unha parte da liña de base. Por exemplo, se 10 destes clientes compraron un produto recomendado dun total de 100 clientes, a liña de referencia é do 10%.
  - **Éxito @K** : créanse recomendacións para todos os clientes e compáranse co conxunto de validación do período de tempo das transaccións. Por exemplo, nun período de 12 meses, o mes 12 está reservado como un conxunto de datos de validación. Se o modelo predí polo menos unha cousa que mercaría no mes 12 segundo o que aprendeu nos 11 meses anteriores, o cliente aumentaría a métrica "Éxito @ K".

- **Produtos máis suxeridos (con reconto):** Os cinco produtos principais previstos para os seus clientes.
  
  :::image type="content" source="media/product-recommendation-topproducts.PNG" alt-text="Gráfico que mostra os 5 principais produtos máis recomendados.":::

- **Factores clave de recomendación:** O modelo utiliza o historial de transaccións dos clientes para facer recomendacións de produtos. Aprende padróns baseados en compras pasadas e atopa similitudes entre clientes e produtos. Estas similitudes utilízanse entón para xerar recomendacións de produtos.
  Os seguintes factores poden influír nunha recomendación de produto xerada polo modelo.
  - **Transaccións pasadas** : Un produto recomendado baseouse en patróns de compra anteriores. Por exemplo, o modelo pode recomendar un *Rato en arco para Surface* se alguén mercou recentemente un *Surface Book 3* e un *Lapis Surface Pen*. O modelo aprendeu que historicamente moitos clientes compraran un *Rato de arco para Surface* despois de mercar un *Surface Book 3* e un *Surface Pen*.
  - **Semellanza de clientes**: Un produto recomendado foi adquirido históricamente por outros clientes que mostran padróns de compra similares. Por exemplo, a John foille recomendado *Surface Headphones 2* porque Jennifer e Brad compraron recentemente *Surface Headphones 2*. O modelo cre que John é similar a Jennifer e Brad porque historicamente tiveron padróns de compra similares.
  - **Semellanza de produtos**: Un produto recomendado é similar a outros produtos que o cliente comprou anteriormente. O modelo considera que dous produtos son similares se foron comprados xuntos ou por clientes similares. Por exemplo, alguén recibe unha recomendación para unha *unidade de almacenamento USB* porque previamente comprou un *Adaptador USB-C a USB* e o modelo cre que esa *unidade de almacenamento USB* é semellante ao *Adaptador USB-C a USB* baseándose en padróns de compra históricos.

  Cada recomendación de produto está influenciada por un ou máis destes factores. A porcentaxe de recomendacións onde cada factor influente xogou un papel visualízase nun gráfico. No seguinte exemplo, o 100 % das recomendacións estiveron influenciadas por transaccións pasadas, o 60 % pola similitude dos clientes e o 22 % pola similitude do produto. Pase o rato por enriba das barras do gráfico para ver a porcentaxe exacta na que contribuíron os factores influentes.
  
  :::image type="content" source="media/product-recommendation-keyrecommendationfactors.png" alt-text="Factores clave de recomendación aprendidos polo modelo para xerar recomendacións de produtos.":::

- **Estatísticas de datos** : Unha visión xeral do número de transaccións, clientes e produtos que o modelo considerou. Baséase nos datos de entrada que se empregaron para aprender padróns e xerar recomendacións de produtos.

  :::image type="content" source="media/product-recommendation-datastatistics.png" alt-text="Estatísticas de datos sobre os datos de entrada utilizados polo modelo para aprender patróns.":::
  
  O modelo utiliza todos os datos dispoñibles para aprender patróns. Polo tanto, se usa o filtrado de produtos na configuración do modelo, esta sección mostra o número total de produtos que o modelo analizou para coñecer patróns, que poden diferir do número de produtos que coinciden cos criterios de filtrado definidos. O filtrado aplícase á saída xerada polo modelo.

- **Recomendacións de produtos de mostra:** Unha mostra de recomendacións que o modelo considera susceptibles de ser adquiridas polo cliente. Se se engade un catálogo de produtos, os ID de produtos substitúense por nomes de produtos.

  :::image type="content" source="media/product-recommendation-highconfidence.PNG" alt-text="Lista que mostra suxestións de alta confianza para un conxunto selecto de clientes individuais.":::

> [!NOTE]
> Na entidade de saída para este modelo, *Puntuación* mostra a medida cuantitativa da recomendación. O modelo recomenda produtos cunha puntuación máis alta antes que os produtos cunha puntuación máis baixa. Para ver a puntuación, vai a **Datos** > **Entidades** e ver a pestana de datos para a entidade de saída que definiu para este modelo.

[!INCLUDE [footer-include](includes/footer-banner.md)]
