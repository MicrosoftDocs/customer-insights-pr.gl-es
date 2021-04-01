---
title: Predición de recomendacións de produtos
description: Prediga os produtos cos que é probable que un cliente interactúe ou adquira.
ms.date: 02/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 5ae78b6bbc51fd8a25bc408050a23479698a1414
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598061"
---
# <a name="product-recommendation-prediction-preview"></a>Predición de recomendacións de produtos (versión preliminar)

O modelo de recomendación de produtos crea conxuntos de recomendacións de produtos preditivas. As recomendacións baséanse no comportamento de compra anterior e en clientes con padróns de compra similares. Pode crear predicións de recomendacións de novos produtos na páxina **Intelixencia** > **Predicións**. Seleccione **As miñas predicións** para ver outras predicións que creou.

As recomendacións de produtos poden estar suxeitas ás leis e regulacións locais, así como ás expectativas dos clientes, que o modelo non está construído para ter en conta especificamente.  Como usuario desta capacidade predictiva, **debe revisar as recomendacións antes de entregalas aos seus clientes** para asegurarse de que está a cumprir as leis ou regulamentos aplicables, así como as expectativas dos clientes sobre o que pode recomendar. 

Ademais, os resultados deste modelo daranlle recomendacións baseadas no identificador do produto. O seu mecanismo de entrega deberá ter identificadores de produto previstos e asignalos ao contido adecuado para que os seus clientes teñan en conta a localización, o contido da imaxe e outro comportamento ou contido específico da empresa.

## <a name="sample-guide"></a>Guía de mostra

Se ten interese en probar esta función pero non ten datos para completar os seguintes requisitos, pode [crear unha implantación de mostra](sample-guide-predict-product-recommendation.md).

## <a name="prerequisites"></a>Requisitos previos

- Polo menos [Permisos de colaborador](permissions.md) en Customer Insights.
- Coñecemento empresarial para comprender os distintos tipos de produtos para o seu negocio e como interactúan os seus clientes con eles. Admitimos recomendar produtos que xa compraron os seus clientes ou recomendacións de novos produtos.
- Datos sobre as transaccións, compras e o seu historial:
    - Identificadores de transaccións para distinguir compras ou transaccións.
    - Identificadores de clientes para asignar transaccións aos seus clientes.
    - Datas de eventos de transacción que especifican as datas en que se produciu a transacción.
    - (Opcional) Información do identificador do produto para a transacción.
    - (Opcional) Se unha transacción é ou non unha devolución.
    - O esquema de datos semánticos require a seguinte información:
        - **ID de transacción:** Un identificador único dunha compra ou transacción.
        - **Data da transacción:** A data da compra ou transacción.
        - **Valor da transacción:** O valor numérico da transacción ou compra.
        - **ID de produto único:** O ID do produto ou servizo adquirido se os seus datos están a un nivel de elemento de liña.
        - (Opcional) **Compra ou devolución:** Un campo verdadeiro/falso que identifica se a transacción foi ou non unha devolución. Se o **Valor da transacción** é negativo, tamén usaremos esta información para inferir un retorno.


## <a name="create-a-product-recommendation-prediction"></a>Crear unha predición de recomendacións de produtos

1. En Customer Insights, diríxase a **Intelixencia** > **Predicións**.

1. Seleccione o mosaico **Modelo de recomendacións de produtos (versión preliminar)** e seleccione **Usar este modelo**.
   > [!div class="mx-imgBorder"]
   > ![Mosaico do modelo de recomendación de produtos co botón Usar este modelo](media/product-recommendation-usethismodel.PNG "Mosaico do modelo de recomendación de produtos co botón Usar este modelo")

1. Revise a información sobre os requisitos do modelo. Se ten os datos requiridos, seleccione **Comezar**.

### <a name="name-model"></a>Dar nome ao modelo

1. Proporcione un nome para o modelo para distinguilo doutros modelos.

1. Introduza un nome para a entidade de saída usando só letras e números, sen ningún espazo. Ese é o nome que empregará a entidade do modelo. despois, seleccione **Seguinte**.

### <a name="define-product-recommendation-configuration"></a>Definir a configuración da recomendación de produtos

1. Configure o **Número de produtos** que quere recomendar a un cliente. Este valor depende de como o método de entrega enche os datos. Se pode recomendar tres produtos, defina este valor segundo corresponda.
   
   >[!TIP]
   > Pode seleccionar **Gardar e pechar** en calquera momento para gardar a predición como borrador. Atopará o borrador da predición no separador **As miñas predicións**.

1. Escolla se quere **Suxerir produtos que os clientes comprasen recentemente**.

1. Se seleccionou *non* recomendar produtos comprados recentemente, configure a **Ventá para ver días pasados**. Esta configuración especifica o período de tempo que considera o modelo antes de recomendarlle de novo o produto ao usuario. Por exemplo, indique que un cliente compra un portátil cada 2 anos. Esta xanela verá o historial de compras dos últimos 2 anos e, se atopan algún elemento, filtrarase o elemento das recomendacións.

1. Seleccionar **Seguinte**

### <a name="add-required-data"></a>Engadir datos obrigatorios

1. Seleccione **Engadir datos** para **Historial de transaccións do cliente** e escolla a entidade que fornece a información do historial de transaccións/compras como se describe nos [requisitos previos](#prerequisites).

1. Asigne os campos semánticos aos atributos da súa entidade do historial de compras e seleccione **Seguinte**. Para obter descricións dos campos, bótelle unha ollada aos [requisitos previos](#prerequisites).
   > [!div class="mx-imgBorder"]
   > ![Definir a relación da entidade](media/product-recommendation-purchasehistorymapping.PNG "Páxina do historial de compras que mostra atributos semánticos asignados a campos da entidade do historial de compras seleccionada")

1. Se os campos non se enchen, configure a relación da súa entidade do historial de compras á entidade *Cliente*.
    1. Seleccione a **entidade do historial de compra**.
    1. Seleccione o **Campo** que identifica ao cliente na entidade do historial de compras. Debe relacionarse co identificador do cliente principal da súa entidade de *cliente*.
    1. Seleccione a **Entidade de cliente** que se corresponde coa súa entidade de cliente principal.
    1. Escriba un nome que describa a relación.
       > [!div class="mx-imgBorder"]
       > ![Páxina do historial de compras que mostra a creación dunha relación co cliente](media/model-purchase-join.png "Páxina do historial de compras que mostra a creación dunha relación co cliente")

1. Seleccione **Gardar**.

1. Seleccione **Seguinte**.

### <a name="set-schedule-and-review-configuration"></a>Establecer a programación e revisar a configuración

1. Estableza unha frecuencia para volver formar o modelo. Esta configuración é importante para actualizar a precisión das predicións a medida que se importan novos datos a Customer Insights. A maioría das empresas poden volverse formar unha vez ao mes e obter unha boa precisión para a súa predición.

1. Seleccione **Seguinte**.

1. Revise a configuración. Pode volver a calquera parte da configuración da predición seleccionando **Editar** no valor amosado. Tamén pode seleccionar un paso de configuración no indicador de progreso.

1. Se todos os valores están configurados correctamente, seleccione **Gardar e executar** para comezar o proceso de predición. No separador **As miñas predicións**, pode ver o estado das súas predicións. O proceso pode levar varias horas en función da cantidade de datos empregados na predición.

## <a name="review-a-prediction-status-and-results"></a>Revise o estado da predición e os resultados

1. Vaia ao separador **As miñas predicións** en **Intelixencia** > **Predicións**.
   > [!div class="mx-imgBorder"]
   > ![Vista da páxina As miñas predicións](media/product-recommendation-mypredictions.PNG "Vista da páxina As miñas predicións")

1. Seleccione a predición que desexa revisar.
   - **Nome da predición:** o nome da predición indicado ao creala.
   - **Tipo de predición:** o tipo de modelo empregado para a predición
   - **Entidade de saída:** nome da entidade para almacenar a saída da predición. Pode atopar unha entidade con este nome en **Datos** > **Entidades**.
   - **Campo previsto:** Este campo só se completa con algúns tipos de predicións e non se usa na predición do abandono.
   - **Estado:** o estado actual da execución da predición.
        - **En cola:** a predición está actualmente á espera de que se executen outros procesos.
        - **Actualización:** a predición está a executar a fase de "puntuación" do procesamento de para producir resultados que fluirán na entidade de saída.
        - **Fallo:** a predición fallou. Seleccione **Rexistros** para obter máis detalles.
        - **Correcto:** a predición fíxose correctamente. Seleccione **Ver** nos tres puntos verticais para revisar a predición
   - **Editado:** a data na que se modificou a configuración da predición.
   - **Última actualización:** a data na que a predición actualizou resultados na entidade de saída.

1. Seleccione os tres puntos verticais xunto á predición da que desexa revisar os resultados e seleccione **Ver**.
   > [!div class="mx-imgBorder"]
   > ![Vista de opcións no menú de tres puntos verticais para obter unha predición, incluída a edición, actualización, vista, rexistros e eliminación](media/product-recommendation-verticalellipses.PNG "Vista de opcións no menú de tres puntos verticais para obter unha predición, incluída a edición, actualización, vista, rexistros e eliminación")

1. Hai tres seccións principais de datos dentro da páxina de resultados:
    1. **Desempeño do modelo de formación:** A, B ou C son posibles puntuacións. Esta puntuación indica o rendemento da predición e pode axudalo a tomar a decisión de usar os resultados almacenados na entidade de saída.
        - As puntuacións determínanse segundo as regras seguintes:
            - **A**: Considerarase o modelo con calidade **A** se a métrica "Éxito @ K" é polo menos un 10 % máis que a liña base. 
            - **B**: Considerarase o modelo con calidade **B** se a métrica "Éxito @ K" é de 0 a 10 % máis que a liña base.
            - **C**: Considerarase o modelo con calidade **C** se a métrica "Éxito @ K" é menos que a liña base.
               
               > [!div class="mx-imgBorder"]
               > ![Vista do resultado do rendemento do modelo](media/product-recommendation-modelperformance.PNG "Vista do resultado do rendemento do modelo")
            - **Liña base**: O modelo colle os produtos máis recomendados segundo o número de compras de todos os clientes e usa as regras aprendidas identificadas polo modelo para crear un conxunto de recomendacións para os clientes. As predicións compáranse cos principais produtos, calculados polo número de clientes que compraron o produto. Se un cliente ten polo menos un produto recomendado que tamén se viu nos produtos máis vendidos, considérase unha parte da liña de base. Se houbese 10 destes clientes que mercaran un produto recomendado dun total de 100 clientes, a liña base sería do 10 %.
            - **Éxito @ K**: Usando un conxunto de validación do período de tempo das transaccións, créanse recomendacións para todos os clientes e compáranse co conxunto de validación de transaccións. Por exemplo, nun período de 12 meses, o mes 12 podería reservarse como un conxunto de datos de validación. Se o modelo predí polo menos unha cousa que mercaría no mes 12 segundo o que aprendeu nos 11 meses anteriores, o cliente aumentaría a métrica "Éxito @ K".
    
    1. **Produtos máis suxeridos (con reconto):** Os 5 principais produtos previstos para os seus clientes.
       > [!div class="mx-imgBorder"]
       > ![Gráfico que mostra os 5 principais produtos máis recomendados](media/product-recommendation-topproducts.PNG "Gráfico que mostra os 5 principais produtos máis recomendados")
    
    1. **Recomendacións de produtos de alta confianza:** Unha mostra de recomendacións proporcionadas aos seus clientes que o modelo cre que é probable que adquira o cliente.
       > [!div class="mx-imgBorder"]
       > ![Lista que mostra suxestións de alta confianza para un conxunto selecto de clientes individuais](media/product-recommendation-highconfidence.PNG "Lista que mostra suxestións de alta confianza para un conxunto selecto de clientes individuais")

## <a name="fix-a-failed-prediction"></a>Corrixir unha predición fallida

1. Vaia ao separador **As miñas predicións** en **Intelixencia** > **Predicións**.

1. Seleccione a predición para a que desexa ver os rexistros de erros e seleccione **Rexistros**.

1. Revise todos os erros. Existen varios tipos de erros que poden ocorrer e describen que problema causou o erro. Por exemplo, un erro que consiste en que non hai datos suficientes para predicir con precisión adoita resolverse cargando datos adicionais en Customer Insights.

## <a name="refresh-a-prediction"></a>Actualizar unha predición

As predicións actualízanse automaticamente na mesma [programación que as actualizacións dos datos](system.md#schedule-tab) como se configura na configuración.

1. Vaia ao separador **As miñas predicións** en **Intelixencia** > **Predicións**.

1. Seleccione os tres puntos verticais xunto á predición que quere actualizar.

1. Seleccione **Actualizar**.

## <a name="delete-a-prediction"></a>Eliminar unha predición

Eliminar unha predición tamén eliminará a súa entidade de saída.

1. Vaia ao separador **As miñas predicións** en **Intelixencia** > **Predicións**.

1. Seleccione os tres puntos verticais xunto á predición que quere eliminar.

1. Seleccione **Eliminar**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]