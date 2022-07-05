---
title: Predición do valor de duración do cliente (VDC)
description: Prediga o potencial de ingresos para os clientes activos no futuro.
ms.date: 02/05/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-predictions
- ci-create-prediction
- ci-custom-models
- customerInsights
ms.openlocfilehash: ea7acd1ddbb0eb8d66fb82018637a85b6ffb369b
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "9055212"
---
# <a name="customer-lifetime-value-clv-prediction"></a>Predición do valor de duración do cliente (VDC)

Prediga o valor potencial (ingresos) que os clientes activos individuais aportarán á súa empresa a través dun período de tempo futuro definido. Esta función pode axudarlle a acadar varios obxectivos:
- Identificar clientes de alto valor e procesar esta información
- Crear segmentos de clientes estratéxicos en función do seu valor potencial para realizar campañas personalizadas con vendas, mercadotecnia e esforzos de asistencia dirixidos
- Guiar o desenvolvemento de produtos centrándose en funcións que aumentan o valor do cliente
- Optimizar as estratexias de vendas ou mercadotecnia e asignar o orzamento con maior precisión para chegar aos clientes
- Recoñecer e premiar aos clientes de alto valor mediante programas de fidelización ou recompensas 

## <a name="prerequisites"></a>Requisitos previos

Antes de comezar, reflexione sobre o que significa o VDC para a súa empresa. Actualmente, admitimos a predición do VDC baseada en transaccións. O valor previsto dun cliente baséase no historial de transaccións comerciais. Para crear a predición, necesita polo menos permisos de [Colaborador](permissions.md).

Dado que a configuración e execución dun modelo de VDC non leva moito tempo, considere a posibilidade de crear varios modelos con diferentes preferencias de entrada e compare os resultados do modelo para ver que escenario de modelo se adapta mellor ás necesidades da súa empresa.

###  <a name="data-requirements"></a>Requirimentos de datos

Os seguintes datos son necesarios e, cando están marcados como opcionais, recoméndanse para aumentar o rendemento do modelo. Cantos máis datos poida procesar o modelo, máis precisa será a predición. Por iso, recomendámoslle inxerir máis datos de actividade do cliente, se están dispoñibles.

- Identificador de cliente: identificador único para facer coincidir as transaccións cun cliente individual

- Historial de transaccións: rexistro de transaccións históricas co esquema de datos semánticos a continuación
    - **ID de transacción**: identificador único de cada transacción
    - **Data da transacción**: data, preferiblemente unha marca de tempo de cada transacción
    - **Importe da transacción**: valor monetario (por exemplo, ingresos ou marxe de beneficio) de cada transacción
    - **Etiqueta asignada ás devolucións** (opcional): valor booleano que indica se a transacción é unha devolución 
    - **Identificador do produto** (opcional): identificador do produto involucrado na transacción

- Datos adicionais (opcional), por exemplo
    - Actividades na web: historial de visitas a sitios web, historial de correo electrónico
    - Actividades de fidelización: acumulación de puntos de fidelidade e historial de trocos
    - Historial de devolucións, reclamacións, chamadas de servizo ou rexistros do servizo de atención ao cliente
- Datos sobre actividades do cliente (opcional):
    - Identificadores de actividades para distinguir actividades do mesmo tipo
    - Identificadores de clientes para atribuír actividades aos seus clientes
    - Información da actividade que contén o nome e a data da actividade
    - O esquema de datos semánticos para actividades inclúe: 
        - **Clave principal**: un identificador único para unha actividade
        - **Marca de tempo**: a data e a hora do evento identificadas pola clave principal
        - **Evento (nome da actividade)**: o nome do evento que quere usar
        - **Detalles (importe ou valor)**: detalles sobre a actividade do cliente

- Características datos suxeridas:
    - Datos históricos suficientes: como mínimo un ano de datos transaccionais. Preferentemente entre dous e tres anos de datos transaccionais para predicir o VDC para un ano.
    - Múltiples compras por cliente: idealmente polo menos entre dúas ou tres transaccións por ID de cliente, preferentemente en varias datas.
    - Número de clientes: como mínimo 100 clientes únicos, preferentemente máis de 10.000 clientes. O modelo fallará con menos de 100 clientes e con datos históricos insuficientes
    - Integridade dos datos: menos do 20 % dos valores que faltan nos campos obrigatorios nos datos de entrada   

> [!NOTE]
> - O modelo require o historial de transaccións dos seus clientes. Actualmente só se pode configurar unha entidade do historial de transaccións. Se hai varias entidades de compra/transacción, podes unila Power Query antes da inxestión de datos.
> - Non obstante, para obter datos de actividade do cliente adicionais (opcionais), pode engadir tantas entidades de actividade do cliente como queira para que o modelo as teña en conta.

## <a name="create-a-customer-lifetime-value-prediction"></a>Crear unha predición do valor de duración do cliente

1. Ir a **Intelixencia** > **Predicións**.

1. Seleccione o mosaico **Valor de duración do cliente** e seleccione **Usar modelo**. 

1. No **Valor de vida do cliente** panel, seleccione **Comezar**.

1. **Poña nome a este modelo** e o **Nome da entidade de saída** para distinguilos doutros modelos ou entidades.

1. Seleccione **Seguinte**.

### <a name="define-model-preferences"></a>Definir preferencias do modelo

1. Estableza un **período de tempo de predición** para definir ata onde desexa predicir o VDC no futuro.    
   Por defecto, a unidade defínese como meses. Pode cambialo por anos para mirar máis adiante no futuro.

   > [!TIP]
   > Para predicir con precisión o VDC para o período de tempo que fixe, necesita un período comparable de datos históricos. Por exemplo, se quere predicir o VDC para os próximos 12 meses, recoméndase que teña polo menos 18-24 meses de datos históricos.

1. Especifique o que **Clientes activos** significa para o seu negocio. Estableza o intervalo temporal no que un cliente debe ter polo menos unha transacción para considerarse activo. O modelo só predicirá o VDC para clientes activos. 
   - **Permitir que o modelo calcule o intervalo de compra (recomendado)**: O modelo analiza os seus datos e determina un período de tempo baseado nas compras históricas.
   - **Establecer o intervalo manualmente**: Se ten unha definición empresarial específica dun cliente activo, escolla esta opción e estableza o período de tempo en consecuencia.

1. Defina o percentil de **Cliente de gran valor** para permitir que o modelo proporcione resultados que se axusten á definición da súa empresa.
    - **Cálculo do modelo (recomendado)**: O modelo analiza os seus datos e determina o que podería ser un cliente de alto valor para a súa empresa en función do historial de transaccións dos seus clientes. O modelo utiliza unha regra heurística (inspirada na regra 80/20 ou principio de Pareto) para atopar a proporción de clientes de alto valor. A porcentaxe de clientes que contribuíu ao 80 % de ingresos acumulados da súa empresa no período histórico considéranse clientes de alto valor. Normalmente, menos do 30-40 % dos clientes contribúen ao 80 % dos ingresos acumulados. Non obstante, este número pode variar dependendo da súa empresa e industria.    
    - **Porcentaxe dos principais clientes activos**: defina os clientes de alto valor da súa empresa como un percentil dos clientes máis activos que pagan. Por exemplo, pode usar esta opción para definir os clientes de alto valor como o 20 % dos futuros clientes que pagan.

    Se a súa empresa define clientes de alto valor dun xeito diferente, [avísenos, xa que nos encantaría escoitalo](https://go.microsoft.com/fwlink/?linkid=2074172).

1. Seleccione **Seguinte** para continuar co paso seguinte.

### <a name="add-required-data"></a>Engadir datos obrigatorios

1. No paso **Datos requiridos**, seleccione **Engadir datos** para **Historial de transaccións do cliente** e escolla a entidade que fornece a información do historial de transaccións como se describe nos [requisitos previos](#prerequisites).

1. Asigne os campos semánticos aos atributos da súa entidade do historial de compras e seleccione **Seguinte**.

   :::image type="content" source="media/clv-add-customer-data-mapping.png" alt-text="Imaxe do paso de configuración para asignar os atributos de datos dos datos requiridos.":::
 
1. Se os campos de abaixo non se enchen, configure a relación da súa entidade do historial de compras coa entidade *Cliente* e seleccione **Gardar**.
    1. Seleccione a entidade do historial de transaccións.
    1. Seleccione o campo que identifica un cliente na entidade do historial de compras. Debe relacionarse coa identificación de cliente principal da súa entidade de cliente.
    1. Seleccione a entidade que coincida coa súa entidade de cliente principal.
    1. Escriba un nome que describa a relación.

      :::image type="content" source="media/clv-add-customer-data-relationship.png" alt-text="Imaxe do paso de configuración para definir a relación coa entidade cliente.":::

1. Seleccione **Seguinte**.

### <a name="add-optional-data"></a>Engadir datos opcionais

Os datos que reflicten as interaccións clave dos clientes (como rexistros de webs, servizos de atención ao cliente e eventos) engaden contexto aos rexistros de transaccións. Se se atopan máis padróns nos datos de actividade dos seus clientes pode mellorar a precisión das predicións. 

1. No paso **Datos adicionais (opcional)**, seleccione **Engadir datos**. Escolla a entidade de actividade do cliente que proporciona a información da actividade do cliente como se describe nos [requisitos previos](#prerequisites).

1. Asigne os campos semánticos aos atributos da súa entidade de actividade do cliente e seleccione **Seguinte**.

   :::image type="content" source="media/clv-additional-data-mapping.png" alt-text="Imaxe do paso de configuración para asignar os campos dos datos adicionais.":::

1. Seleccione un tipo de actividade que coincida co tipo de actividade do cliente que está engadindo. Escolla entre os tipos de actividade existentes ou engada un novo tipo de actividade.

1. Configure a relación da entidade de actividade do cliente coa entidade *Cliente*.
    
    1. Seleccione o campo que identifica ao cliente na entidade de actividade do cliente. Pode estar directamente relacionada co ID de cliente principal da súa entidade *Cliente*.
    1. Seleccione a entidade de *Cliente* que se corresponde coa súa entidade de *Cliente* principal.
    1. Escriba un nome que describa a relación.

   :::image type="content" source="media/clv-additional-data.png" alt-text="Imaxe do paso do fluxo de configuración para engadir datos adicionais e configurar a actividade con exemplos completos.":::

1. Seleccione **Gardar**.    
    Engada máis datos se hai outras actividades do cliente que queira incluír.

1. Seleccione **Seguinte**.

### <a name="set-update-schedule"></a>Definir programación de actualizacións

1. No paso **Programación de actualización de datos**, elixa a frecuencia para volver adestrar o seu modelo en función dos últimos datos. Esta configuración é importante para actualizar a precisión das predicións a medida que se inxiren novos datos en Customer Insights. A maioría das empresas poden volverse formar unha vez ao mes e obter unha boa precisión para a súa predición.

1. Seleccione **Seguinte**.

### <a name="review-and-run-the-model-configuration"></a>Revisar e executar a configuración do modelo

1. No paso **Revisar os detalles do seu modelo**, valide a configuración da predición. Pode volver a calquera parte da configuración da predición seleccionando **Editar** no valor amosado. Tamén pode seleccionar un paso de configuración no indicador de progreso.

1. Se todos os valores están configurados correctamente, seleccione **Gardar e executar** para comezar a executar o modelo. No separador **As miñas predicións**, pode ver o estado do proceso de predición. O proceso pode levar varias horas en función da cantidade de datos empregados na predición.

## <a name="review-prediction-status-and-results"></a>Revisar o estado e os resultados da predición

### <a name="review-prediction-status"></a>Revisar o estado da predición

1.  Vaia a **Intelixencia** > **Predicións** e seleccione o separador **As miñas predicións**.
2.  Seleccione a predición que desexa revisar.

- **Nome da predición**: Nome da predición proporcionado ao creala.
- **Tipo de predición**: Tipo de modelo usado para a predición
- **Entidade de saída**: nome da entidade para almacenar os resultados da predición. Vaia a **Datos** > **Entidades** para atopar a entidade con este nome.
- **Campo previsto**: Este campo só se completa con algúns tipos de predicións e non se usa na predición do valor de duración do cliente.
- **Estado**: Estado da execución da predición.
    - **En cola**: a predición está á espera de que finalicen outros procesos.
    - **Actualizando**: a predición está executándose actualmente para crear resultados que fluirán cara á entidade de saída.
    - **Fallou**: Fallou a execución da predición. Para obter máis detalles, [revise os rexistros](manage-predictions.md#troubleshoot-a-failed-prediction).
    - **Con éxito**: a predición tivo éxito. Seleccione **Ver** nos tres puntos verticais para revisar os resultados da predición.
- **Editado**: a data na que se modificou a configuración da predición.
- **Última actualización**: a data na que a predición actualizou os resultados na entidade de saída.

### <a name="review-prediction-results"></a>Revisar os resultados da predición

1. Vaia a **Intelixencia** > **Predicións** e seleccione o separador **As miñas predicións**.

1. Seleccione a predición para a que quere revisar os resultados.

Hai tres seccións principais de datos dentro da páxina de resultados.

- **Rendemento do modelo de adestramento**: A, B ou C son as posibles cualificacións. Esta cualificación indica o rendemento da predición e pode axudarlle a tomar a decisión de usar os resultados almacenados na entidade de saída. Seleccione **Máis información sobre esta puntuación** para comprender mellor as métricas de rendemento do modelo subxacentes e como se derivou a cualificación do rendemento do modelo final.
  
  :::image type="content" source="media/clv-model-score.png" alt-text="Imaxe da caixa de información da puntuación do modelo coa cualificación A.":::

  Usando a definición de clientes de alto valor proporcionada ao configurar a predición, o sistema avalía o rendemento do modelo IA na predición dos clientes de alto valor en comparación cun modelo de base.    

  As cualificacións determínanse en función das seguintes regras:
  - **A**: cando o modelo predixo con precisión polo menos un 5 % máis de clientes de alto valor en comparación co modelo de referencia.
  - **B**: cando o modelo predixo con precisión entre un 0-5 % máis de clientes de alto valor en comparación co modelo de referencia.
  - **C**: cando o modelo predixo con precisión menos clientes de alto valor en comparación co modelo de referencia.

  O panel **Valoración do modelo** mostra máis detalles sobre o rendemento do modelo IA e o modelo de base. O modelo de base utiliza un enfoque non baseado na IA para calcular o valor da duración do cliente baseado principalmente nas compras históricas realizadas polos clientes.     
  A fórmula estándar empregada para calcular o VDC polo modelo de base:    

  _**VDC para cada cliente** = Compra mensual media feita polo cliente na ventá do cliente activo * Número de meses no período de predición do VDC * Taxa global de retención de todos os clientes*_

  O modelo IA compárase co modelo de base baseado en dúas métricas de rendemento do modelo.
  
  - **Taxa de éxito ao predicir os clientes valiosos**

    Vexa a diferenza na predición de clientes de alto valor mediante o modelo IA en comparación co modelo de base. Por exemplo, unha da taxa de éxito do 84 % significa que de todos os clientes de alto valor dos datos de adestramento, o modelo IA foi capaz de captar con precisión o 84 %. Despois comparamos esta taxa de éxito coa taxa de éxito do modelo de base para informar do cambio relativo. Este valor úsase para asignar unha cualificación ao modelo.

  - **Métricas de erro**
    
    Outra métrica permítelle revisar o rendemento xeral do modelo en termos de erro na predición de valores futuros. Usamos a métrica global de erro do valor cuadrático medio (RMSE) para avaliar este erro. O RMSE é un xeito estándar de medir o erro dun modelo na predición de datos cuantitativos. O RMSE do modelo AI compárase co RMSE do modelo de base e infórmase da diferenza relativa.

  O modelo IA prioriza a clasificación precisa dos clientes segundo o valor que aportan ao seu negocio. Polo tanto, só se usa a taxa de éxito de predición de clientes de alto valor para obter a nota do modelo final. A métrica do RMSE é sensible aos valores atípicos. Nos escenarios nos que teña unha pequena porcentaxe de clientes con valores de compra extraordinariamente altos, a métrica do RMSE xeral pode non dar a imaxe completa do rendemento do modelo.   

- **Valor dos clientes por percentil**: Usando a súa definición de clientes de alto valor, os clientes agrúpanse en valor baixo e alto valor, segundo as súas predicións do VDC, e móstranse nun gráfico. Ao pasar o rato sobre as barras do histograma, pode ver o número de clientes de cada grupo e o VDC medio dese grupo. Estes datos poden axudar se desexa [crear segmentos de clientes](segments.md) baseándose nas súas predicións do VDC.

- **Factores máis influentes**: Considéranse varios factores ao crear a súa predición do VDC en función dos datos de entrada proporcionados ao modelo IA. Cada un dos factores ten calculada a súa importancia para as predicións agregadas que crea un modelo. Pode usar estes factores para axudar a validar os resultados da súa predición. Estes factores tamén ofrecen máis información sobre os factores máis influentes que contribuíron á predición do VDC en todos os seus clientes.

## <a name="manage-predictions"></a>Xestionar predicións

É posible optimizar, solucionar problemas, actualizar ou eliminar predicións. Revise un informe de usabilidade dos datos de entrada para saber como facer unha predición máis rápido e máis fiable. Para obter máis información, consulte [Xestionar predicións](manage-predictions.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
