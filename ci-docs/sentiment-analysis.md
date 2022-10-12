---
title: Analizar o sentimento dos comentarios dos clientes (vista previa)
description: Aprende a usar un modelo de análise de sentimentos nos comentarios dos clientes en Dynamics 365 Customer Insights.
ms.date: 09/14/2022
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: 61ce9fb18efa6152dddb2e31f4fd0366a31ac2c7
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610464"
---
# <a name="analyze-sentiment-in-customer-feedback-preview"></a>Analizar o sentimento nos comentarios dos clientes (vista previa)

A análise de sentimentos permítelle sintetizar o sentimento dos clientes e identificar os aspectos comerciais como oportunidades de mellora. Esta función de Customer Insights axúdache a comprender o que funciona ben e o que tes que abordar. Pode axudarche a impulsar accións empresariais que permitan experiencias que resulten nunha alta satisfacción e fidelidade do cliente.

## <a name="overview"></a>Visión xeral

A función de análise de sentimentos xera dúas informacións derivadas por ID de cliente. Unha puntuación de sentimento (de -5 a 5) e unha lista de aspectos comerciais aplicables (áreas de negocio) que en conxunto axudan a comprender mellor os comentarios dos clientes.

Esta análise axúdache a:
- Obter unha visión xeral dos sentimentos dos clientes cara a unha marca ou organización
- Identifica os clientes con sentimentos negativos para centrar as túas campañas e compromisos e optimizalos para obter unha maior rendibilidade  
- Identificar aspectos comerciais con problemas sinalados polos clientes  
- Segmenta os clientes en función do seu sentimento para realizar campañas personalizadas con vendas, mercadotecnia e esforzos de apoio dirixidos
- Optimice as operacións comerciais abordando áreas de preocupación ou oportunidades que foron mencionadas polos clientes
- Recoñece os aspectos comerciais que lles vai ben e premia aos clientes satisfeitos mediante programas de fidelización e promoción

O modelo ofrece unha lista de palabras que afectaron á decisión do modelo de asignar unha puntuación de sentimento ou un aspecto empresarial particular aos comentarios de comentarios.  

Usamos dous **Modelos de procesamento da linguaxe natural (PNL).** : O primeiro atribúe a cada comentario de comentarios unha puntuación de sentimento. O segundo modelo asocia cada feedback con todos os aspectos comerciais aplicables. Os modelos están adestrados en datos públicos de fontes en redes sociais, venda polo miúdo, restaurantes, produtos de consumo e industrias do automóbil.
  
Os aspectos comerciais predefinidos para que o modelo se asocie cos datos de comentarios inclúen:
- Xestión de contas
- Finalización da compra e pagamento
- Asistencia técnica
- Recollida na tenda
- Recuperación e envío de paquetes
- Pedido anticipado
- Prezo
- Privacidade e seguranza
- Promocións e recompensas
- Factura e garantía
- Cancelación e cambio de devolucións
- Precisión do cumprimento
- Calidade da aplicación ou sitio web

> [!NOTE]
> Actualmente, só admitimos a análise de sentimentos sobre comentarios dos clientes en inglés. No futuro admitiranse máis idiomas. Se se cargan comentarios noutros idiomas, o modelo aínda devolverá resultados. Non obstante, estes resultados non serán precisos.

## <a name="prerequisites"></a>Requisitos previos

- Polo menos [Permisos de colaborador](permissions.md)
- [Unificado](data-unification.md) datos de comentarios de texto. Recomendámosche encarecidamente [configure as súas entidades de datos de comentarios como entidades de actividade de tipo semántico](map-entities.md#select-primary-key-and-semantic-type-for-attributes) (Tipo de feedback).
- ID unificado de cliente (UCID) da unificación de datos para facer coincidir os rexistros de datos de comentarios de texto cun cliente individual.
- ID do comentario
- Marca de tempo de comentarios
- Texto do comentario

Customer Insights pode procesar ata 10 millóns de rexistros de comentarios para un único modelo. O modelo pode analizar comentarios de comentarios de ata 128 palabras. Se un comentario de comentarios é máis longo, a análise considera só as primeiras 128 palabras.

> [!NOTE]
> Só se pode configurar unha entidade de comentarios. Se hai varias entidades de comentarios, combínaas Power Query antes da inxestión de datos.

## <a name="configure-a-sentiment-analysis"></a>Configura unha análise de sentimentos

1. Ir a **Intelixencia** > **Predicións**.

1. No **Crear** ficha, seleccione **Usa modelo** no **Análise do sentimento dos clientes (vista previa)** tella.

1. Seleccione **Comezar**.

1. **Nome** a análise e proporcionar o **Nome da entidade de saída do aspecto empresarial** e o **Nome da entidade de saída da puntuación do sentimento**.

1. Seleccione **Seguinte**.

1. Seleccione **Engadir datos** para **Comentarios dos clientes**.

1. Seleccione o tipo de actividade semántica **Comentarios** que contén os datos de retroalimentación. Se a actividade non está configurada, seleccione **aquí** e crealo.

   :::image type="content" source="media/sentiment-add-feedback-activities.png" alt-text="Paso de configuración para seleccionar actividades de comentarios para a análise de sentimentos.":::

1. Seleccione as actividades que quere utilizar para esta análise de sentimentos e, a continuación, seleccione **A continuación**.

1. Asigne os atributos dos seus datos aos atributos do modelo. 

1. Seleccione **Gardar**.

1. Seleccione **Seguinte**. O **Revisa e corre** O paso mostra un resumo da configuración e ofrece a oportunidade de facer cambios antes de crear a análise.

1. Seleccione **Editar** en calquera dos pasos para revisar e facer calquera cambio.

1. Se estás satisfeito coas túas seleccións, selecciona **Garda e executa** para comezar a executar o modelo. Seleccione **Feito**. O **As miñas predicións** aparece a pestana mentres se crea o predición. O proceso pode levar varias horas en función da cantidade de datos empregados na predición.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-analysis-results"></a>Ver os resultados da análise

1. Ir a **Intelixencia** > **Predicións**.

1. No **As miñas predicións** pestana, seleccione o predición que quere ver.

Hai dúas pestanas de resultados.

### <a name="sumary-tab"></a>Ficha resumo

Hai catro seccións principais de datos dentro da páxina de resultados.

- **Puntuación media de sentimento** : as puntuacións de sentimentos axúdanche a comprender o sentimento xeral de todos os clientes.
  - **Negativa** (-5 > 2)
  - **Neutral** (-1 > 1)
  - **Positivo** (2 > 5)
  
  :::image type="content" source="media/overall-customer-sentiment.png" alt-text="Representación visual do sentimento global do cliente.":::

- **Distribución dos clientes por puntuación de sentimento** : os clientes clasifícanse en grupos negativos, neutros e positivos en función das súas puntuacións de sentimento. Pasa o rato sobre as barras do histograma para ver o número de clientes e a puntuación media de sentimento en cada grupo. Estes datos poden axudarche [crear segmentos de clientes](prediction-based-segment.md) en función das súas puntuacións de sentimentos.  

  :::image type="content" source="media/distribution-customer-sentiment.png" alt-text="Gráfico de barras que mostra o sentimento do cliente nos tres grupos de sentimentos.":::

- **Puntuación media do sentimento ao longo do tempo** : O sentimento do cliente pode cambiar co paso do tempo. Proporcionamos tendencias nos sentimentos dos teus clientes para o intervalo de tempo dos teus datos. Esta vista axúdache a valorar o efecto das promocións estacionais, os lanzamentos de produtos ou outras intervencións con límite de tempo no sentimento dos clientes. Consulta o gráfico seleccionando o ano de interese no menú despregable.

  :::image type="content" source="media/sentiment-score-over-time.png" alt-text="Gráfico histórico coa puntuación do sentimento ao longo do tempo representada como unha liña.":::

- **Sentimento a través dos aspectos comerciais** : o sentimento medio en todos os aspectos da empresa axúdache a valorar cales son os aspectos da túa empresa que xa satisfacen aos clientes ou requiren máis atención. Os rexistros de comentarios que non se aliñan a ningún dos aspectos comerciais admitidos clasifícanse en **Outra**. Ordena os datos seleccionando calquera columna.

  :::image type="content" source="media/sentiment-across-business-aspects.png" alt-text="Lista de aspectos comerciais co valor do sentimento asociado e o número de clientes que o mencionan.":::

  Seleccione o nome dun aspecto empresarial para ver como o modelo identifica un aspecto empresarial:

  - **Palabras influentes** : Palabras principais que influíron na identificación do modelo de IA dun aspecto empresarial nos comentarios dos clientes.
    **Mostra palabras ofensivas** : Permíteche incluír palabras ofensivas na lista dos datos orixinais dos comentarios dos clientes. Por defecto, está desactivado.  O enmascaramento de palabras ofensivas está impulsado por un modelo de IA e é posible que non detecte todas as palabras ofensivas. Se detectas unha palabra ofensiva que non se filtrou como esperaba, avísanos.

    :::image type="content" source="media/offensive-words-sentiment.png" alt-text="Lista de palabras influentes co selector para mostrar ou ocultar palabras ofensivas.":::

  - **Mostras de comentarios** : rexistros de comentarios reais nos teus datos. As palabras están codificadas por cores segundo a súa influencia na identificación dun aspecto empresarial.

### <a name="influential-words-analysis-tab"></a>Pestana de análise de palabras influentes

Hai tres seccións de información adicional que explican como funciona o modelo de sentimento.
  
- **Palabras principais que contribúen ao sentimento positivo** : palabras principais que influíron na identificación do modelo de IA do sentimento positivo nos comentarios dos clientes.  

- **Palabras principais que contribúen ao sentimento negativo** : Palabras principais que influíron na identificación do modelo de IA dos sentimentos negativos nos comentarios dos clientes.

- **Mostras de comentarios** : rexistros de comentarios reais, un con sentimento negativo e outro con sentimento positivo. As palabras dos rexistros de comentarios realízanse segundo a súa contribución á puntuación de sentimento asignada. As palabras que contribúen a unha puntuación de sentimento positivo están resaltadas en verde. As palabras que contribúen a unha puntuación negativa están resaltadas en vermello.
   Seleccione **Ver máis** para cargar máis mostras de comentarios.
  
   :::image type="content" source="media/sentiment-feedback-samples.png" alt-text="Exemplos de análise de sentimentos sobre comentarios dos clientes.":::

**Mostra palabras ofensivas** : Permíteche incluír palabras ofensivas na lista dos datos orixinais dos comentarios dos clientes. Por defecto, está desactivado.  O enmascaramento de palabras ofensivas está impulsado por un modelo de IA e é posible que non detecte todas as palabras ofensivas. Se detectas unha palabra ofensiva que non se filtrou como esperaba, avísanos.

## <a name="act-on-analysis-results"></a>Actuar sobre os resultados da análise

Para crear novos segmentos de clientes a partir dos resultados da análise de sentimentos, seleccione **Crear segmentos** na parte superior da páxina de resultados do modelo.

## <a name="potential-bias"></a>Sesgo potencial

Do mesmo xeito que con calquera función que utilice intelixencia artificial preditiva, pode haber un sesgo potencial nos datos que utilizas para prever o sentimento dos clientes. Por exemplo, se só recolles comentarios dixitalmente, podes perderte os comentarios dos clientes que realizan negocios contigo en persoa, o que afecta a saída da función.

Dado que esta función utiliza medios automatizados para avaliar datos e facer predicións baseándose neses datos, ten a posibilidade de utilizarse como método de elaboración de perfiles, tal e como define o Regulamento Xeral de Protección de Datos ("GDPR"). O uso desta función para procesar datos pode estar suxeito ao RXPD ou a outras leis ou regulamentos. Vostede é responsable de garantir que o seu uso Dynamics 365 Customer Insights, incluída a análise de sentimentos, cumpre todas as leis e regulamentos aplicables, incluídas as leis relacionadas coa privacidade, os datos persoais, os datos biométricos, a protección de datos e a confidencialidade das comunicacións.

[!INCLUDE [footer-include](includes/footer-banner.md)]

