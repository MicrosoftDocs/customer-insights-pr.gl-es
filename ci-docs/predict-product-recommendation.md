---
title: Predición de recomendacións de produtos
description: Prediga os produtos cos que é probable que un cliente interactúe ou adquira.
ms.date: 05/09/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: 9b3e60c49d294d031f43ef0594cb69707bb64019
ms.sourcegitcommit: 82f417cfb0a16600e9f552d7a21d598cc8f5a267
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 05/16/2022
ms.locfileid: "8762730"
---
# <a name="product-recommendation-prediction"></a>Predición de recomendacións de produtos

O modelo de recomendación de produtos crea conxuntos de recomendacións de produtos preditivas. As recomendacións baséanse no comportamento de compra anterior e en clientes con padróns de compra similares. Pode crear predicións de recomendacións de novos produtos na páxina **Intelixencia** > **Predicións**. Seleccione **As miñas predicións** para ver outras predicións que creou.

As recomendacións de produtos poden estar suxeitas ás leis e regulacións locais e ás expectativas dos clientes, que o modelo non está construído para ter en conta especificamente.  Como usuario desta capacidade predictiva, **debes revisar as recomendacións antes de entregalas aos seus clientes** para asegurarse de que está a cumprir as leis ou regulamentos aplicables e as expectativas dos clientes sobre o que pode recomendar.

Ademais, os resultados deste modelo daranlle recomendacións baseadas no identificador do produto. O seu mecanismo de entrega necesitará asignar os ID de produto previstos ao contido adecuado para que os seus clientes teñan en conta a localización, o contido da imaxe e outro comportamento ou contido específico da empresa.

## <a name="sample-guide"></a>Guía de mostra

Se ten interese en probar esta función pero non ten datos para completar os seguintes requisitos, pode [crear unha implantación de mostra](sample-guide-predict-product-recommendation.md).

## <a name="prerequisites"></a>Requisitos previos

- Polo menos [Permisos de colaborador](permissions.md) en Customer Insights.

- Coñecemento empresarial para comprender os distintos tipos de produtos para o seu negocio e como interactúan os seus clientes con eles. Admitimos recomendar produtos que xa compraron os seus clientes ou recomendacións de novos produtos.

- O teu ambiente ten que estar configurado para **consumidores individuais** público obxectivo principal.

- Datos sobre as transaccións, compras e o seu historial:
  - Identificadores de transaccións para distinguir compras ou transaccións.
  - Identificadores de clientes para asignar transaccións aos seus clientes.
  - Datas de eventos de transacción que especifican as datas en que se produciu a transacción.
  - Información de identificador do produto para a transacción.
  - (Opcional) Unha entidade de datos do catálogo de produtos para usar un filtro de produto.
  - (Opcional) Se unha transacción é ou non unha devolución.
  - O esquema de datos semánticos require a seguinte información:
    - **ID de transacción:** Un identificador único dunha compra ou transacción.
    - **Data da transacción:** A data da compra ou transacción.
    - **Valor da transacción:** O valor numérico da transacción ou compra.
    - **ID de produto único:** O ID do produto ou servizo adquirido se os seus datos están a un nivel de elemento de liña.
    - (Opcional) **Compra ou devolución:** Un campo booleano onde o valor *certo* identifica que unha transacción foi unha devolución. Se non se proporcionan os datos de compra ou devolución, o modelo e o **Valor da transacción** é negativo, tamén usaremos esta información para inferir unha devolución.
- Características datos suxeridas:
  - Datos históricos suficientes: polo menos un ano de datos transaccionais, preferentemente de dous a tres anos para incluír certa estacionalidade.
  - Compras múltiples por cliente: tres ou máis transaccións por identificación de cliente
  - Número de clientes: polo menos 100 clientes, preferentemente máis de 10.000 clientes. O modelo fallará con menos de 100 clientes.

> [!NOTE]
>
> - O modelo require o historial de transaccións dos seus clientes. A definición dunha transacción é bastante flexible. Calquera dato que describe unha interacción usuario-produto pode funcionar como entrada. Por exemplo, mercar un produto, tomar unha clase ou asistir a un evento.
> - Actualmente só se pode configurar unha entidade do historial de transaccións. Se hai varias entidades de compra, únaas Power Query antes da inxestión de datos.
> - Se os detalles da orde e dos pedidos son entidades diferentes, únaas antes de empregalas no modelo. O modelo non funciona só cun ID de pedido ou ID de recibo nunha entidade.

## <a name="create-a-product-recommendation-prediction"></a>Crear unha predición de recomendacións de produtos

1. En Customer Insights, diríxase a **Intelixencia** > **Predicións**.

1. Seleccione o **Modelo de recomendacións de produtos** mosaico e selecciona **Use este modelo**.
   > [!div class="mx-imgBorder"]
   > ![Mosaico do modelo de recomendación de produtos co botón Usar este modelo.](media/product-recommendation-usethismodel.PNG "Mosaico do modelo de recomendación de produtos co botón Usar este modelo")

1. Revise a información sobre os requisitos do modelo. Se ten os datos requiridos, seleccione **Comezar**.

### <a name="name-model"></a>Dar nome ao modelo

1. Proporcione un nome para o modelo para distinguilo doutros modelos.

1. Introduza un nome para a entidade de saída usando só letras e números, sen ningún espazo. Ese é o nome que empregará a entidade do modelo. despois, seleccione **Seguinte**.

### <a name="define-product-recommendation-configuration"></a>Definir a configuración da recomendación de produtos

1. Configure o **Número de produtos** que quere recomendar a un cliente. Este valor depende de como o método de entrega enche os datos. Se pode recomendar tres produtos, defina este valor segundo corresponda.

   >[!TIP]
   > Podes seleccionar **Garda o borrador** en calquera momento para gardar o predición como borrador. Atopará o borrador da predición no separador **As miñas predicións**.

1. Escolle se queres incluír produtos que os clientes compraron recentemente na páxina **Se esperan compras repetidas** campo.

1. Establece o **Mirar cara atrás fiestra**. Esta configuración especifica o período de tempo que considera o modelo antes de recomendarlle de novo o produto ao usuario. Por exemplo, indica que un cliente compra un portátil cada dous anos. Nesta xanela verá o historial de compras dos últimos dous anos e, se se atopa algún artigo, filtrarase o elemento das recomendacións.

1. Seleccionar **Seguinte**

### <a name="add-required-data"></a>Engadir datos obrigatorios

1. Seleccione **Engadir datos** e escolla o tipo de actividade no panel lateral que contén a información de transacción ou historial de compras requirida.

1. En **Elixir as actividades**, escolla as actividades específicas da actividade seleccionada na que desexa que se centre o cálculo.

   :::image type="content" source="media/product-recommendation-select-semantic-activity.PNG" alt-text="Panel lateral que mostra a elección de actividades específicas baixo o tipo semántico.":::

1. Se aínda non asignou a actividade a un tipo semántico, seleccione **Editar** facelo. Ábrese a experiencia guiada para asignar actividades semánticas. Asigne os seus datos aos campos correspondentes do tipo de actividade seleccionada.

   :::image type="content" source="media/product-recommendation-set-activity-type.PNG" alt-text="Tipo de actividade de configuración de páxina.":::

1. Despois de asignar a actividade ao tipo semántico correspondente, seleccione **A continuación** proceder.

1. Asigne os atributos semánticos aos campos necesarios para executar o modelo.

1. Seleccione **Gardar**.

1. Seleccione **Seguinte**.

### <a name="configure-product-filters"></a>Configurar os filtros de produtos

Ás veces, só certos produtos son beneficiosos ou apropiados para o tipo de predición que constrúe. Os filtros de produtos permiten identificar un subconxunto de produtos con características específicas para recomendar aos seus clientes. O modelo empregará todos os produtos dispoñibles para aprender padróns, pero só empregará os produtos que coincidan co filtro de produto na súa saída.

1. No paso **Engadir información do produto**, engada o seu catálogo de produtos con información para cada produto. Asigne a información requirida e seleccione **Seguinte**.

1. No paso **Filtros de produtos**, escolla entre as seguintes opcións.

   - **Sen filtros**: Use todos os produtos na predición de recomendacións de produtos.

   - **Definir filtros de produtos específicos**: Use produtos específicos na predición de recomendacións de produtos.

1. Seleccione **Seguinte**.

1. Se elixe definir un filtro de produto, ten que definilo agora. No panel **Atributos do catálogo de produtos**, seleccione os atributos da *Entidade do catálogo de produtos* que desexa incluír no filtro.

   :::image type="content" source="media/product-filters-sidepane.png" alt-text="Panel lateral que mostra os atributos na entidade do catálogo de produtos para seleccionar os filtros de produtos.":::

1. Escolla se desexa que o filtro de produto use conectores **e** ou **ou** para combinar loxicamente a súa selección de atributos do catálogo de produtos.

   :::image type="content" source="media/product-filters-sample.png" alt-text="Configuración de mostra de filtros de produtos combinados con conectores AND lóxicos.":::

1. Seleccione **Seguinte**.

### <a name="set-update-schedule-and-review-configuration"></a>Definir o calendario de actualización e revisar a configuración

1. Estableza unha frecuencia para volver formar o modelo. Esta configuración é importante para actualizar a precisión das predicións a medida que se importan novos datos a Customer Insights. A maioría das empresas poden volverse formar unha vez ao mes e obter unha boa precisión para a súa predición.

1. Seleccione **Seguinte**.

1. Revise a configuración. Pode volver a calquera parte da configuración da predición seleccionando **Editar** no valor amosado. Tamén pode seleccionar un paso de configuración no indicador de progreso.

1. Se todos os valores están configurados correctamente, seleccione **Gardar e executar** para comezar o proceso de predición. No separador **As miñas predicións**, pode ver o estado das súas predicións. O proceso pode levar varias horas en función da cantidade de datos empregados na predición.

## <a name="review-a-prediction-status-and-results"></a>Revise o estado da predición e os resultados

1. Vaia ao separador **As miñas predicións** en **Intelixencia** > **Predicións**.
   > [!div class="mx-imgBorder"]
   > ![Vista da páxina As miñas predicións.](media/product-recommendation-mypredictions.PNG "Vista da páxina As miñas predicións")

1. Seleccione a predición que desexa revisar.
   - **Nome da predición:** o nome da predición indicado ao creala.
   - **Tipo de predición:** o tipo de modelo empregado para a predición
   - **Entidade de saída:** nome da entidade para almacenar a saída da predición. Pode atopar unha entidade con este nome en **Datos** > **Entidades**.
      A *Puntuación* na entidade de saída é unha medida cuantitativa da recomendación. O modelo recomenda produtos cunha puntuación máis alta antes que os produtos cunha puntuación máis baixa.
   - **Campo previsto:** Este campo só se completa con algúns tipos de predicións e non se usa na Predición de recomendacións de produtos.
   - **Estado:** o estado actual da execución da predición.
        - **En cola:** a predición está actualmente á espera de que se executen outros procesos.
        - **Actualización:** a predición está a executar a fase de "puntuación" do procesamento de para producir resultados que fluirán na entidade de saída.
        - **Fallo:** a predición fallou. Seleccione **Rexistros** para obter máis detalles.
        - **Correcto:** a predición fíxose correctamente. Seleccione **Ver** nos tres puntos verticais para revisar a predición
   - **Editado:** a data na que se modificou a configuración da predición.
   - **Última actualización:** a data na que a predición actualizou resultados na entidade de saída.

1. Seleccione os tres puntos verticais xunto á predición da que desexa revisar os resultados e seleccione **Ver**.
   > [!div class="mx-imgBorder"]
   > ![Vista de opcións no menú de tres puntos verticais para obter unha predición, incluída a edición, actualización, vista, rexistros e eliminación.](media/product-recommendation-verticalellipses.PNG "Vista de opcións no menú de tres puntos verticais para obter unha predición, incluída a edición, actualización, vista, rexistros e eliminación")

1. Na páxina de resultados hai cinco seccións principais de datos:
    1. **Desempeño do modelo de formación:** A, B ou C son posibles puntuacións. Esta puntuación indica o rendemento da predición e pode axudalo a tomar a decisión de usar os resultados almacenados na entidade de saída.
        - As puntuacións determínanse segundo as regras seguintes:
            - **A**: Considerarase o modelo con calidade **A** se a métrica "Éxito @ K" é polo menos un 10 % máis que a liña base. 
            - **B**: Considerarase o modelo con calidade **B** se a métrica "Éxito @ K" é de 0 % a 10 % máis que a liña base.
            - **C**: Considerarase o modelo con calidade **C** se a métrica "Éxito @ K" é menos que a liña base.

               > [!div class="mx-imgBorder"]
               > ![Vista do resultado do rendemento do modelo.](media/product-recommendation-modelperformance.PNG "Vista do resultado do rendemento do modelo")
            - **Liña base**: O modelo colle os produtos máis recomendados segundo o número de compras de todos os clientes e usa as regras aprendidas identificadas polo modelo para crear un conxunto de recomendacións para os clientes. As predicións compáranse cos principais produtos, calculados polo número de clientes que compraron o produto. Se un cliente ten polo menos un produto recomendado que tamén se viu nos produtos máis vendidos, considérase unha parte da liña de base. Se houbese 10 destes clientes que mercaran un produto recomendado dun total de 100 clientes, a liña base sería do 10 %.
            - **Éxito @ K**: Usando un conxunto de validación do período de tempo das transaccións, créanse recomendacións para todos os clientes e compáranse co conxunto de validación de transaccións. Por exemplo, nun período de 12 meses, o mes 12 podería reservarse como un conxunto de datos de validación. Se o modelo predí polo menos unha cousa que mercaría no mes 12 segundo o que aprendeu nos 11 meses anteriores, o cliente aumentaría a métrica "Éxito @ K".

    1. **Produtos máis suxeridos (con reconto):** Os cinco produtos principais previstos para os seus clientes.
       > [!div class="mx-imgBorder"]
       > ![Gráfico que mostra os 5 principais produtos máis recomendados.](media/product-recommendation-topproducts.PNG "Gráfico que mostra os 5 principais produtos máis recomendados")

    1. **Factores clave de recomendación:** O modelo utiliza o historial de transaccións dos clientes para facer recomendacións de produtos. Aprende padróns baseados en compras pasadas e atopa similitudes entre clientes e produtos. Estas similitudes utilízanse entón para xerar recomendacións de produtos.
    Os seguintes son os factores que poden influír nunha recomendación de produto xerada polo modelo.
        - **Transaccións pasadas**: Os padróns de compra no pasado foron utilizados polo modelo para xerar recomendacións de produtos. Por exemplo, o modelo pode recomendar un *Rato en arco para Surface* se alguén mercou recentemente un *Surface Book 3* e un *Lapis Surface Pen*. O modelo aprendeu que historicamente moitos clientes compraran un *Rato de arco para Surface* despois de mercar un *Surface Book 3* e un *Surface Pen*.
        - **Semellanza de clientes**: Un produto recomendado foi adquirido históricamente por outros clientes que mostran padróns de compra similares. Por exemplo, a John foille recomendado *Surface Headphones 2* porque Jennifer e Brad compraron recentemente *Surface Headphones 2*. O modelo cre que John é similar a Jennifer e Brad porque historicamente tiveron padróns de compra similares.
        - **Semellanza de produtos**: Un produto recomendado é similar a outros produtos que o cliente comprou anteriormente. O modelo considera que dous produtos son similares se foron comprados xuntos ou por clientes similares. Por exemplo, alguén recibe unha recomendación para unha *unidade de almacenamento USB* porque previamente comprou un *Adaptador USB-C a USB* e o modelo cre que esa *unidade de almacenamento USB* é semellante ao *Adaptador USB-C a USB* baseándose en padróns de compra históricos.

        Cada recomendación de produto está influenciada por un ou máis destes factores. A porcentaxe de recomendacións onde cada factor influente xogou un papel visualízase nun gráfico. No seguinte exemplo, o 100 % das recomendacións estiveron influenciadas por transaccións pasadas, o 60 % pola similitude dos clientes e o 22 % pola similitude do produto. Pase o rato por enriba das barras do gráfico para ver a porcentaxe exacta na que contribuíron os factores influentes.

        > [!div class="mx-imgBorder"]
        > ![Principais factores de recomendación.](media/product-recommendation-keyrecommendationfactors.png "Factores clave de recomendación aprendidos polo modelo para xerar recomendacións de produtos")

   1. **Estatísticas de datos**: Ofrece unha visión xeral do número de transaccións, clientes e produtos que o modelo considerou. Baséase nos datos de entrada que se empregaron para aprender padróns e xerar recomendacións de produtos.

      > [!div class="mx-imgBorder"]
      > ![Estatísticas dos datos.](media/product-recommendation-datastatistics.png "Estatísticas de datos arredor dos datos de entrada empregados polo modelo para aprender padróns")

      Esta sección mostra as estatísticas arredor dos puntos de datos utilizados polo modelo para aprender padróns e xerar recomendacións de produtos. A filtraxe, tal e como se configura na configuración do modelo, aplicarase á saída xerada polo modelo. Non obstante, o modelo utiliza todos os datos dispoñibles para aprender padróns. Polo tanto, se usa a filtraxe de produtos na configuración do modelo, esta sección amosará o número total de produtos que o modelo analizou para aprender padróns, que poden diferir do número de produtos que coinciden cos criterios de filtraxe definidos.

   1. **Recomendacións de produtos de alta confianza:** Unha mostra de recomendacións proporcionadas aos seus clientes que o modelo cre que é probable que adquira o cliente.    
      Se se engade un catálogo de produtos, os ID de produtos substitúense por nomes de produtos. Os nomes de produtos proporcionan unha información máis intuitiva e que require accións sobre as predicións.
       > [!div class="mx-imgBorder"]
       > ![Lista que mostra suxestións de alta confianza para un conxunto selecto de clientes individuais.](media/product-recommendation-highconfidence.PNG "Lista que mostra suxestións de alta confianza para un conxunto selecto de clientes individuais")

## <a name="manage-predictions"></a>Xestionar predicións

É posible optimizar, solucionar problemas, actualizar ou eliminar predicións. Revise un informe de usabilidade dos datos de entrada para saber como facer unha predición máis rápido e máis fiable. Para obter máis información, consulte [Xestionar predicións](manage-predictions.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
