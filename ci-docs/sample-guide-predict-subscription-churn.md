---
title: Guía de mostra da predición do abandono da subscrición
description: Utilice esta guía de mostra para probar o modelo de predición do abandono da subscrición listo para usar.
ms.date: 03/31/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-create-prediction
- customerInsights
ms.openlocfilehash: 5a8eeafecacef3d0bb4a798b698cf490423ca98d
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741409"
---
# <a name="subscription-churn-prediction-sample-guide"></a>Guía de mostra da predición do abandono da subscrición

Guiarémolo a través dun exemplo integral de predición do abandono da subscrición empregando os datos de exemplo fornecidos a continuación. 

## <a name="scenario"></a>Escenario

Contoso é unha empresa que produce cafés e máquinas de café de alta calidade, que venden a través do seu sitio web Contoso Coffee. Recentemente iniciaron un negocio de subscrición para que os seus clientes tomasen café de xeito habitual. O seu obxectivo é comprender que clientes subscritos poden cancelar a súa subscrición nos próximos meses. Sabendo cal dos seus clientes é **susceptible de abandonar**, pode axudalos a aforrar esforzos de marketing centrándose en mantelos.

## <a name="prerequisites"></a>Requisitos previos

- Polo menos [Permisos de colaborador](permissions.md) en Customer Insights.
- Recomendámoslle que implemente os seguintes pasos [nun novo ambiente](manage-environments.md).

## <a name="task-1---ingest-data"></a>Tarefa 1: inxerir datos

Revisa os artigos [sobre a inxestión de datos](data-sources.md) e [importando fontes de datos usando Power Query conectores](connect-power-query.md) concretamente. A seguinte información supón que está familiarizado coa inxestión de datos en xeral. 

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Inxerir datos de clientes desde a plataforma de comercio electrónico

1. Cree unha orixe de datos denominada **eCommerce**, escolla a opción de importación e seleccione o conector **Texto/CSV**.

1. Insira o URL dos contactos de comercio electrónico https://aka.ms/ciadclasscontacts.

1. Mentres edita os datos, seleccione **Transformar** e logo **Usar a primeira fila como cabeceiras**.

1. Actualice o tipo de datos para as columnas listadas a continuación:

   - **DateOfBirth**: data
   - **CreatedOn**: data/hora/fuso

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transforme a data de nacemento en data.":::

1. No campo **Nome** no panel da dereita, cambie o nome da súa orixe de datos de **Consulta** a **eCommerceContacts**

1. Garde a orixe de datos.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Inxerir datos de clientes desde o esquema de fidelización

1. Cree unha orixe de datos denominada **LoyaltyScheme**, escolla a opción de importación e seleccione o conector **Texto/CSV**.

1. Insira o URL dos contactos de comercio electrónico https://aka.ms/ciadclasscustomerloyalty.

1. Mentres edita os datos, seleccione **Transformar** e logo **Usar a primeira fila como cabeceiras**.

1. Actualice o tipo de datos para as columnas listadas a continuación:

   - **DateOfBirth**: data
   - **RewardsPoints**: número enteiro
   - **CreatedOn**: data/hora

1. No campo **Nome** no panel da dereita, cambie o nome da súa orixe de datos de **Consulta** a **loyCustomers**.

1. Garde a orixe de datos.

### <a name="ingest-subscription-information"></a>Inxerir información da subscrición

1. Cree unha orixe de datos denominada **SubscriptionHistory**, escolla a opción de importación e seleccione o conector **Texto/CSV**.

1. Insira o URL dos contactos de comercio electrónico https://aka.ms/ciadchurnsubscriptionhistory.

1. Mentres edita os datos, seleccione **Transformar** e logo **Usar a primeira fila como cabeceiras**.

1. Actualice o tipo de datos para as columnas listadas a continuación:

   - **SubscriptioID**: número enteiro
   - **SubscriptionAmount**: moeda
   - **SubscriptionEndDate**: data/hora
   - **SubscriptionStartDate**: data/hora
   - **TransactionDate**: data/hora
   - **SubscriptionHistory**: verdadeiro/falso
   - **Is_auto_renew**: verdadeiro/falso
   - **RecurringFrequencyInMonths**: número enteiro

1. No campo **Nome** no panel da dereita, cambie o nome da súa orixe de datos de **Consulta** a **SubscriptionHistory**.

1. Garde a orixe de datos.

### <a name="ingest-customer-data-from-website-reviews"></a>Inxerir datos de clientes a partir de comentarios de sitios web

1. Cree unha orixe de datos denominada **Website**, escolla a opción de importación e seleccione o conector **Texto/CSV**.

1. Insira o URL dos contactos de comercio electrónico https://aka.ms/ciadclasswebsite.

1. Mentres edita os datos, seleccione **Transformar** e logo **Usar a primeira fila como cabeceiras**.

1. Actualice o tipo de datos para as columnas listadas a continuación:

   - **ReviewRating**: número enteiro
   - **ReviewDate**: data

1. No campo "Nome" no panel da dereita, cambie o nome da súa orixe de datos de **Consulta** a **webReviews**.

## <a name="task-2---data-unification"></a>Tarefa 2: unificación de datos

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---configure-the-subscription-churn-prediction"></a>Tarefa 3: configurar a predición de abandono da subscrición

Cos perfís de clientes unificados no seu lugar, agora podemos executar a predición de abandono de subscricións. Para ver os pasos detallados, consulte [Churn de subscricións predición](predict-subscription-churn.md) artigo. 

1. Vaia a **Intelixencia** > **Descubrir** e seleccione para usar o **Modelo de abandono do cliente**.

1. Seleccione a opción **Subscrición** e seleccione **Comezar**.

1. Nomee o modelo **Predición do abandono da subscrición de OOB** e a entidade de saída **OOBSubscriptionChurnPrediction**.

1. Defina dúas condicións para o modelo de abandono:

   * **Días desde que finalizou a subscrición**: **polo menos 60** días. Se un cliente non renova a subscrición neste período despois de que finalizase a súa subscrición, considérase perdido. 

   * **Definición de abandono**: **polo menos 93** días. A duración do modelo predí que clientes poderían abandonar. Canto máis se mira no futuro, menos precisos serán os resultados.

     :::image type="content" source="media/model-subs-levers.PNG" alt-text="Seleccione as opcións do modelo Ventá de predición e Definición de abandono.":::

1. Seleccione **Engadir datos requiridos** e seleccione **Engadir datos** para o historial de subscricións.

1. Engada a entidade **Subscription : SubscriptionHistory** e asigne os campos de comercio electrónico aos campos correspondentes requiridos polo modelo.

1. Una a entidade **Subscription : SubscriptionHistory** con **eCommerceContacts : eCommerce**, nomee a relación **eCommerceSubscription**.

   :::image type="content" source="media/model-subscription-join.PNG" alt-text="Unir entidades de comercio electrónico.":::

1. En Actividades do cliente, engada a entidade **webReviews : Website** e asigne os campos de webReviews aos campos correspondentes requiridos polo modelo. 
   - Clave principal: ReviewId
   - Marca de tempo: ReviewDate
   - Evento: ReviewRating

1. Configure unha actividade para as opinións de sitios web. Seleccione a actividade **Opinión** e una a entidade **webReviews : Website** con **eCommerceContacts : eCommerce**.

1. Seleccione **Seguinte** para establecer a programación do modelo.

   O modelo necesita adestrarse regularmente para aprender novos padróns cando se inxiren novos datos. Para este exemplo, seleccione **Mensual**.

1. Despois de revisar todos os detalles, seleccione **Gardar e executar**.

## <a name="task-4---review-model-results-and-explanations"></a>Tarefa 4: revisar resultados e explicacións do modelo

Deixe que o modelo complete o adestramento e a puntuación dos datos. Agora pode revisar as explicacións do modelo de abandono de subscricións. Para obter máis información, consulte [Revisar o estado e os resultados dunha predición](predict-subscription-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a>Tarefa 5: crear un segmento de clientes con alto risco de abandono

Executar o modelo de produción crea unha nova entidade na que pode ver en **Datos** > **Entidades**.   

Pode crear un novo segmento baseado na entidade creada polo modelo.

1.  Vaia a **Segmentos**. Seleccione **Novo** e elixa **Crear a partir de** > **Intelixencia**. 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Creación dun segmento coa saída do modelo.":::

1. Seleccione o extremo **OOBSubscriptionChurnPrediction** e defina o segmento: 
   - Campo: ChurnScore
   - Operador: maior que
   - Valor: 0,6
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Configurar o segmento de abandono de subscricións.":::

Agora ten un segmento que se actualiza dinámicamente para identificar clientes con alto risco de abandono para este negocio da subscrición.

Para ver máis información, consulte: [Creación e xestión de segmentos](segments.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]