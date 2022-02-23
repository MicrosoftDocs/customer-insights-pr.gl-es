---
title: Análise de sentimentos para comentarios dos clientes
description: Aprende a usar un modelo de análise de sentimentos nos comentarios dos clientes en Dynamics 365 Customer Insights.
ms.date: 12/23/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: 8a4473c1c395bbcf8efa2bfa24cddb82e1784279
ms.sourcegitcommit: 15ec8c5f54242feda9489e7665726ec5e0983dc9
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 01/19/2022
ms.locfileid: "8008763"
---
# <a name="analyze-sentiment-in-customer-feedback-preview"></a>Analiza o sentimento nos comentarios dos clientes (vista previa)

Os clientes esperan produtos, servizos e experiencias de alta calidade nestes días. Especialmente os clientes que comparten os seus comentarios. É moi difícil para as organizacións analizar un volume crecente de datos sen reducir a precisión e un custo laboral máis elevado. Dynamics 365 Customer Insights ofrece un modelo de análise de sentimentos para os comentarios dos clientes que permite ás organizacións analizar os seus datos con máis precisión e a un custo menor.

A análise de sentimentos permítelle sintetizar o sentimento dos clientes e identificar os aspectos comerciais como oportunidades de mellora. Esta función de Customer Insights axúdache a comprender o que funciona ben e o que tes que abordar. Céntrate nas áreas de negocio máis relevantes e impactantes para mellorar a experiencia dos teus clientes. En definitiva, pode axudarche a impulsar accións empresariais que permitan experiencias que resulten nunha alta satisfacción e fidelidade do cliente.

## <a name="overview"></a>Visión xeral

A función de análise de sentimentos xera dúas informacións derivadas por ID de cliente. Unha puntuación de sentimento (de -5 a 5) e unha lista de aspectos comerciais aplicables (áreas de negocio) axúdanche a comprender mellor os comentarios dos clientes. 

Esta información pode axudarche a conseguir os seguintes resultados: 
- Obter unha visión xeral dos sentimentos dos clientes cara a unha marca ou organización
- Identifica os clientes con sentimentos negativos para centrar as túas campañas e compromisos e optimizalos para obter unha maior rendibilidade  
- Identificar aspectos comerciais con problemas sinalados polos clientes  
- Segmenta os clientes en función do seu sentimento para realizar campañas personalizadas con vendas, mercadotecnia e esforzos de apoio dirixidos
- Optimice as operacións comerciais abordando áreas de preocupación ou oportunidades que foron mencionadas polos clientes
- Recoñece os aspectos comerciais que lles vai ben e premia aos clientes satisfeitos mediante programas de fidelización e promoción

Para garantir que pode confiar nos resultados dos modelos, fornecemos información transparente sobre como toman decisións os modelos. Recibirás unha lista de palabras que afectaron á decisión dos modelos de asignar unha puntuación de sentimento ou un aspecto empresarial particular aos comentarios de comentarios.  

Usamos dous **Modelos de procesamento da linguaxe natural (PNL).** : A primeira asigna a cada comentario de comentarios unha puntuación de sentimento. O segundo modelo asocia cada feedback con todos os aspectos comerciais aplicables. Os modelos están adestrados en datos públicos de fontes en redes sociais, venda polo miúdo, restaurantes, produtos de consumo e industrias do automóbil.    
  
Os aspectos comerciais predefinidos para que o modelo se asocie cos datos de comentarios inclúen:
-   Xestión de contas
-   Finalización da compra e pagamento
-   Asistencia técnica
-   Recollida na tenda
-   Recuperación e envío de paquetes
-   Pedido anticipado
-   Prezo
-   Privacidade e seguranza
-   Promocións e recompensas
-   Factura e garantía
-   Cancelación e cambio de devolucións
-   Precisión do cumprimento
-   Calidade da aplicación ou sitio web

> [!NOTE]
> Actualmente, só admitimos análise de sentimentos sobre comentarios de clientes en inglés. No futuro admitiranse máis idiomas. Se se cargan comentarios noutros idiomas, o modelo aínda devolverá resultados. Non obstante, estes resultados non serán precisos. 

## <a name="prerequisites"></a>Requisitos previos

A análise de sentimentos baséase nos datos de comentarios de texto que pasaron por [proceso de unificación de datos](data-unification.md). Recomendámosche encarecidamente [configure as súas entidades de datos de comentarios como entidades de actividade de tipo semántico](map-entities.md#select-primary-key-and-semantic-type-for-attributes) (Tipo de feedback) previamente. 

Para configurar un modelo de análise de sentimentos, necesitas polo menos [Permisos de colaborador](permissions.md).

Customer Insights pode procesar ata 10 millóns de rexistros de comentarios para un único modelo. O modelo pode analizar comentarios de comentarios de ata 128 palabras. Se un comentario de comentarios é máis longo, a análise considera só as primeiras 128 palabras.

### <a name="data-requirements"></a>Requirimentos de datos
  
Os seguintes atributos de datos son necesarios:
- Unified Customer ID (UCID) para relacionar os rexistros de datos de comentarios de texto cun cliente individual. Esta identificación é o resultado de [proceso de unificación de datos](data-unification.md).
- ID do comentario
- Marca de tempo de comentarios
- Texto do comentario   

> [!TIP]
> A análise de sentimentos require os comentarios de texto dos teus clientes. Actualmente só se pode configurar unha entidade de comentarios. Se hai varias entidades de comentarios, podes unila Power Query antes de que comece a inxestión de datos.

## <a name="configure-a-sentiment-analysis"></a>Configura unha análise de sentimentos 

1. En Customer Insights, diríxase a **Intelixencia** > **Predicións**.

1. No **Análise do sentimento dos clientes** tella, selecciona **Usa modelo**.

1. No **Análise do sentimento dos clientes (vista previa)** panel, seleccione **Comezar**.

1. No **Nome do modelo** paso, proporcionar a **Nome** para a súa análise. 

1. Proporcionar o **Nome da entidade de saída do aspecto empresarial** e o **Nome da entidade de saída da puntuación do sentimento** e, a continuación, seleccione **A continuación**.

1. No **Datos obrigatorios** paso, seleccione **Engadir datos**.

   :::image type="content" source="media/sentiment-add-data.png" alt-text="Engade fluxo de datos no modelo de análise de sentimentos.":::

1. No **Engadir datos** panel, escolla o tipo semántico **Comentarios** da lista.

   :::image type="content" source="media/sentiment-add-feedback-activities.png" alt-text="Paso de configuración para seleccionar actividades de comentarios para a análise de sentimentos.":::

1. Seleccione as actividades que quere utilizar para esta análise de sentimentos e, a continuación, seleccione **A continuación**.
 
1. Asigne os atributos dos seus datos aos atributos do modelo. Seleccione **Gardar** para aplicar as súas seleccións. 

1. Podes ver o estado da asignación de datos. Seleccione **Seguinte** para continuar. 

1. No **Revisa os detalles do teu modelo** paso, valida a configuración da túa análise de sentimentos. Podes volver a calquera parte da configuración predición. Seleccione **Garda e executa** para comezar a análise. 

   :::image type="content" source="media/sentiment-model-review-config.png" alt-text="Revisa o paso para o modelo de sentimento que mostra todos os elementos configurados.":::

1. Seleccione **Feito** para deixar a experiencia de configuración. O proceso pode tardar varias horas en completarse dependendo da cantidade de datos empregados. 

## <a name="review-analysis-status"></a>Revisar o estado da análise

1.  Vaia a **Intelixencia** > **Predicións** e seleccione o separador **As miñas predicións**.
2.  Seleccione a predición que desexa revisar.
- **Nome da predición**: Nome da predición proporcionado ao creala.
- **Tipo predición** : Tipo de modelo utilizado para o predición.
- **Entidade de saída**: nome da entidade para almacenar os resultados da predición. Vaia a **Datos** > **Entidades** para atopar a entidade con este nome.
- **Campo previsto**: Este campo só se completa con algúns tipos de predicións e non se usa na predición do valor de duración do cliente.
- **Estado**: Estado da execución da predición.
  - **En cola**: a predición está á espera de que finalicen outros procesos.
  - **Actualizando**: a predición está executándose actualmente para crear resultados que fluirán cara á entidade de saída.
  - **Fallou**: Fallou a execución da predición. Para obter máis detalles, revise os rexistros.
  - **Con éxito**: a predición tivo éxito. Seleccione Ver nos tres puntos verticais para revisar os resultados da predición.
- **Editado**: a data na que se modificou a configuración da predición.
- **Última actualización** : A data en que o predición actualizou resulta na entidade de saída.

## <a name="manage-sentiment-analysis"></a>Xestionar a análise de sentimentos

Podes optimizar, solucionar problemas, actualizar ou eliminar predicións. Revise un informe de usabilidade dos datos de entrada para saber como facer unha predición máis rápido e máis fiable. Para obter máis información, consulte [Xestionar predicións](manage-predictions.md).

## <a name="review-analysis-results"></a>Revisar os resultados da análise
 
1. Vaia a **Intelixencia** > **Predicións** e seleccione o separador **As miñas predicións**. 
1. Selecciona o nome do predición para o que queres revisar os resultados. Neste caso, selecciona a análise de sentimentos que queres revisar. 

### <a name="summary-tab"></a>Separador de resumo

Hai catro seccións principais de datos dentro da páxina de resultados. 

- **Puntuación media de sentimento** : Axúdache a comprender o sentimento xeral de todos os clientes. As puntuacións dos sentimentos agrúpanse en tres categorías: 
  1.    Negativo (-5 > 2)
  2.    Neutro (-1 > 1)
  3.    Positivo (2 > 5) 
  
  :::image type="content" source="media/overall-customer-sentiment.png" alt-text="Representación visual do sentimento global do cliente.":::

- **Distribución dos clientes por puntuación de sentimento** : os clientes clasifícanse en grupos negativos, neutros e positivos en función das súas puntuacións de sentimento. Pasa o rato sobre as barras do histograma para ver o número de clientes e a puntuación media de sentimento en cada grupo. Estes datos poden axudarche [crear segmentos de clientes](segments.md) en función das súas puntuacións de sentimentos.  

  :::image type="content" source="media/distribution-customer-sentiment.png" alt-text="Gráfico de barras que mostra o sentimento do cliente nos tres grupos de sentimentos.":::

- **Puntuación media do sentimento ao longo do tempo** : O sentimento do cliente pode cambiar co paso do tempo. Ofrecemos tendencias nos sentimentos dos seus clientes para o intervalo de tempo dos seus datos. Esta vista pode axudarche a valorar o efecto das promocións estacionais, os lanzamentos de produtos ou outras intervencións con límite de tempo no sentimento dos clientes. Consulta o gráfico seleccionando o ano de interese no menú despregable. 

  :::image type="content" source="media/sentiment-score-over-time.png" alt-text="Gráfico histórico coa puntuación do sentimento ao longo do tempo representada como unha liña.":::
 
- **Sentimento a través dos aspectos comerciais** : Esta táboa enumera o sentimento medio entre os aspectos comerciais. Pode axudarche a valorar que aspectos da túa empresa xa satisfacen aos clientes ou os que requiren máis atención. Os rexistros de comentarios que non se aliñan a ningún dos aspectos comerciais admitidos clasifícanse en **Outra**. A táboa está ordenada alfabeticamente por defecto. Pode modificar a ordenación seleccionando unha cabeceira de táboa.

  :::image type="content" source="media/sentiment-across-business-aspects.png" alt-text="Lista de aspectos comerciais co valor de sentimento asociado e o número de clientes que o mencionan.":::
 
  Seleccione o nome dun aspecto empresarial para ver información adicional sobre como o modelo identifica un aspecto empresarial. Neste panel hai dúas partes: 

  - **Palabras influentes** : Mostra as palabras principais que influíron na identificación do modelo de IA dun aspecto comercial nos comentarios dos clientes. 
    **Mostra palabras ofensivas** : Permíteche incluír palabras ofensivas na lista dos datos orixinais dos comentarios dos clientes. Por defecto, está desactivado.  O enmascaramento de palabras ofensivas está impulsado por un modelo de IA e é posible que non detecte todas as palabras ofensivas. Seguimos iterando e adestrando o clasificador para un rendemento óptimo. Se detectas unha palabra ofensiva que non se filtrou como esperaba, avísanos. 
    
    :::image type="content" source="media/offensive-words-sentiment.png" alt-text="Lista de palabras influentes co selector para mostrar ou ocultar palabras ofensivas.":::
 
  - **Mostras de comentarios** : mostra os rexistros de comentarios reais nos teus datos. As palabras están codificadas por cores segundo a súa influencia na identificación dun aspecto empresarial. 


### <a name="influential-words-analysis-tab"></a>Pestana de análise de palabras influentes

Hai tres seccións de información adicional que explican como funciona o modelo de sentimento.
  
1. **Palabras principais que contribúen ao sentimento positivo** : Mostra as palabras principais que influíron na identificación do modelo de IA do sentimento positivo nos comentarios dos clientes.  
2. **Palabras principais que contribúen ao sentimento negativo** : Mostra as palabras principais que influíron na identificación do modelo de IA dos sentimentos negativos nos comentarios dos clientes.  
3. **Mostras de comentarios** : mostra os rexistros de comentarios reais, un con sentimento negativo e outro con sentimento positivo. As palabras dos rexistros de comentarios realízanse segundo a súa contribución á puntuación de sentimento asignada. As palabras que contribúen a unha puntuación de sentimento positivo están resaltadas en verde. As palabras que contribúen a unha puntuación negativa están resaltadas en vermello.
   Seleccione **Ver máis** para cargar máis mostras de comentarios que proporcionen máis información e contexto sobre como funciona o modelo de sentimento.
   
   :::image type="content" source="media/sentiment-feedback-samples.png" alt-text="Exemplos de análise de sentimentos sobre comentarios dos clientes.":::
 
**Mostra palabras ofensivas** : Permíteche incluír palabras ofensivas na lista dos datos orixinais dos comentarios dos clientes. Por defecto, está desactivado.  O enmascaramento de palabras ofensivas está impulsado por un modelo de IA e é posible que non detecte todas as palabras ofensivas. Seguimos iterando e adestrando o clasificador para un rendemento óptimo. Se detectas unha palabra ofensiva que non se filtrou como esperaba, avísanos. 

## <a name="act-on-analysis-results"></a>Actuar sobre os resultados da análise

Podes comezar facilmente a crear novos segmentos de clientes desde a páxina de resultados da análise de sentimentos seleccionando **Crear segmentos** na parte superior da páxina de resultados do modelo.

:::image type="content" source="media/create-segment-model.png" alt-text="Barra de comandos con opcións nos modelos predición.":::
 
## <a name="potential-bias"></a>Sesgo potencial

Do mesmo xeito que con calquera función que utilice intelixencia artificial preditiva, debes ter en conta o posible sesgo nos datos que utilizas para predecir o sentimento dos clientes. Por exemplo, se só recolles comentarios dixitalmente, podes perderte os comentarios dos clientes que realizan negocios contigo en persoa, o que pode afectar a saída da función.

Dado que esta función utiliza medios automatizados para avaliar datos e facer predicións baseándose neses datos, ten, polo tanto, a capacidade de utilizarse como método de elaboración de perfiles, tal e como o define o Regulamento Xeral de Protección de Datos ("GDPR"). O uso desta función para procesar datos pode estar suxeito ao RXPD ou a outras leis ou regulamentos. Vostede é responsable de garantir que o seu uso Dynamics 365 Customer Insights, incluída a análise de sentimentos, cumpre todas as leis e regulamentos aplicables, incluídas as leis relacionadas coa privacidade, os datos persoais, os datos biométricos, a protección de datos e a confidencialidade das comunicacións.

[!INCLUDE[footer-include](../includes/footer-banner.md)]

