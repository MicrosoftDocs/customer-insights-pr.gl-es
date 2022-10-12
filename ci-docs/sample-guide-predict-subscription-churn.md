---
title: Guía de mostra da predición do abandono da subscrición
description: Utilice esta guía de mostra para probar o modelo de predición do abandono da subscrición listo para usar.
ms.date: 09/19/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-create-prediction
- customerInsights
ms.openlocfilehash: 7e754be9a2cb9450949c6b3667bbd37aa39cf0bf
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610004"
---
# <a name="subscription-churn-prediction-sample-guide"></a>Guía de mostra da predición do abandono da subscrición

Esta guía explicarache un exemplo de extremo a extremo de eliminación de subscricións predición usando datos de mostra. Recomendámosche que probes este predición [nun novo ambiente](manage-environments.md).

## <a name="scenario"></a>Escenario

Contoso é unha empresa que produce café e máquinas de café de alta calidade. Venden os produtos a través do seu sitio web Contoso Coffee. Recentemente iniciaron un negocio de subscrición para que os seus clientes tomasen café de xeito habitual. O seu obxectivo é comprender que clientes subscritos poden cancelar a súa subscrición nos próximos meses. Saber cal dos seus clientes é **susceptible de revolverse** pode axudarlles a aforrar esforzos de mercadotecnia centrándose en mantelos.

## <a name="prerequisites"></a>Requisitos previos

- Polo menos [Permisos de colaborador](permissions.md) en Customer Insights.

## <a name="task-1---ingest-data"></a>Tarefa 1: inxerir datos

Revisa os artigos [sobre a inxestión de datos](data-sources.md) e [conectando a a Power Query orixe de datos](connect-power-query.md). A seguinte información supón que estás familiarizado coa inxestión de datos en xeral.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Inxerir datos de clientes desde a plataforma de comercio electrónico

1. Crea un Power Query orixe de datos chamado **comercio electrónico** e selecciona o **Texto/CSV** conector.

1. Insira o URL dos contactos de comercio electrónico https://aka.ms/ciadclasscontacts.

1. Mentres editas os datos, selecciona **Transformar** e despois **Use a primeira fila como cabeceiras**.

1. Actualice o tipo de datos para as columnas listadas a continuación:
   - **DateOfBirth**: data
   - **CreatedOn**: data/hora/fuso

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transforme a data de nacemento en data.":::

1. No **Nome** no panel da dereita, cambie o nome do seu orixe de datos a **eCommerceContactos**

1. Garde a orixe de datos.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Inxerir datos de clientes desde o esquema de fidelización

1. Crea un orixe de datos chamado **Esquema de fidelidade** e selecciona o **Texto/CSV** conector.

1. Introduza o URL para os clientes de fidelidade https://aka.ms/ciadclasscustomerloyalty.

1. Mentres editas os datos, selecciona **Transformar** e despois **Use a primeira fila como cabeceiras**.

1. Actualice o tipo de datos para as columnas listadas a continuación:
   - **DateOfBirth**: data
   - **RewardsPoints**: número enteiro
   - **CreatedOn**: data/hora

1. No **Nome** no panel da dereita, cambie o nome do seu orixe de datos a **Clientes loy**.

1. Garde a orixe de datos.

### <a name="ingest-subscription-information"></a>Inxerir información da subscrición

1. Crea un orixe de datos chamado **Historial de subscricións** e selecciona o **Texto/CSV** conector.

1. Introduza o URL para as subscricións https://aka.ms/ciadchurnsubscriptionhistory.

1. Mentres editas os datos, selecciona **Transformar** e despois **Use a primeira fila como cabeceiras**.

1. Actualice o tipo de datos para as columnas listadas a continuación:
   - **SubscriptioID**: número enteiro
   - **SubscriptionAmount**: moeda
   - **SubscriptionEndDate**: data/hora
   - **SubscriptionStartDate**: data/hora
   - **TransactionDate**: data/hora
   - **SubscriptionHistory**: verdadeiro/falso
   - **Is_auto_renew**: verdadeiro/falso
   - **RecurringFrequencyInMonths**: número enteiro

1. No **Nome** no panel da dereita, cambie o nome do seu orixe de datos a **Historial de subscricións**.

1. Garde a orixe de datos.

### <a name="ingest-customer-data-from-website-reviews"></a>Inxerir datos de clientes a partir de comentarios de sitios web

1. Crea un orixe de datos chamado **Sitio web** e selecciona o **Texto/CSV** conector.

1. Introduza o URL para as revisións do sitio web https://aka.ms/ciadclasswebsite.

1. Mentres editas os datos, selecciona **Transformar** e despois **Use a primeira fila como cabeceiras**.

1. Actualice o tipo de datos para as columnas listadas a continuación:
   - **ReviewRating**: número enteiro
   - **ReviewDate**: data

1. No **Nome** no panel da dereita, cambie o nome do seu orixe de datos a **Reseñas web**.

## <a name="task-2---data-unification"></a>Tarefa 2: unificación de datos

Revisa o artigo [sobre a unificación de datos](data-unification.md). A seguinte información supón que está familiarizado coa unificación de datos en xeral.

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---create-transaction-history-activity"></a>Tarefa 3: crear actividade de historial de transaccións

Revisa o artigo [sobre as actividades dos clientes](activities.md). A seguinte información supón que está familiarizado coa creación de actividades en xeral.

1. Crea unha actividade chamada **Historial de subscricións** co *Subscrición* entidade e a súa clave primaria, **ID de cliente**.

1. Crea unha relación entre *Historial de subscricións:Subscrición* e *eCommerceContactos: eCommerce* con **ID de cliente** como clave externa para conectar as dúas entidades.

1. Seleccione **Tipo de subscrición** para o **EventActivity** e **SubscriciónEndDate** para o **Selo de tempo**.

1. Seleccione **Subscrición** para o **Tipo de actividade** e mapear semanticamente os datos da actividade.

1. Executar a actividade.

1. Engade outra actividade e asigna os nomes dos seus campos aos campos correspondentes:
   - Entidade de actividade do cliente: Reviews:Website
   - Clave principal: Website.Reviews.ReviewId
   - Marca de tempo: Website.Reviews.ReviewDate
   - Evento (nome da actividade): Website.Reviews.ActivityTypeDisplay
   - Detalles (importe ou valor): Website.Reviews.ReviewRating

1. Executar a actividade.

## <a name="task-4---configure-the-subscription-churn-prediction"></a>Tarefa 4: configurar a predición de abandono da subscrición

Cos perfís de clientes unificados existentes e a actividade creada, executa a eliminación de subscricións predición. Para os pasos detallados, consulte [Churn de subscricións predición](predict-subscription-churn.md).

1. Ir a **Intelixencia** > **Predicións**.

1. No **Crear** ficha, seleccione **Usa modelo** no **Modelo de abandono de clientes** tella.

1. Seleccione **Subscrición** para o tipo de churn e despois **Comezar**.

1. Nomee o modelo **Predición do abandono da subscrición de OOB** e a entidade de saída **OOBSubscriptionChurnPrediction**.

1. Definir as preferencias do modelo:
   - **Días desde que finalizou a subscrición** :**60** días para indicar que un cliente se considera despedido se non renova a subscrición neste período despois de que finalice a súa subscrición.
   - **Días para investigar o futuro para prever o abandono** :**93** días, que é a duración que o modelo prevé que clientes poden abandonar. Canto máis se mira no futuro, menos precisos serán os resultados.

   :::image type="content" source="media/model-subs-levers.PNG" alt-text="Seleccione as preferencias do modelo e a definición do churn.":::

1. Seleccione **Seguinte**.

1. No **Datos requiridos** paso, seleccione **Engadir datos** para proporcionar o historial de subscricións.

1. Seleccione **Subscrición** e a entidade SubscriptionHistory e seleccione **A continuación**. Os datos necesarios enchéranse automaticamente desde a actividade. Seleccione **Gardar**.

1. En Actividades do cliente, seleccione **Engadir datos**.

1. Para este exemplo, engade a actividade de revisión web.

1. Seleccione **Seguinte**.

1. No **Actualizacións de datos** paso, seleccione **Mensuais** para o modelo de horario.

1. Despois de revisar todos os detalles, seleccione **Gardar e executar**.

## <a name="task-5---review-model-results-and-explanations"></a>Tarefa 5: revisar resultados e explicacións do modelo

Deixe que o modelo complete o adestramento e a puntuación dos datos. Revisa as explicacións do modelo de abandono da subscrición. Para obter máis información, consulte [Ver os resultados de predición](predict-subscription-churn.md#view-prediction-results).

## <a name="task-6---create-a-segment-of-high-churn-risk-customers"></a>Tarefa 6: crear un segmento de clientes con alto risco de abandono

Ao executar o modelo créase unha nova entidade, que aparece na lista **Datos** > **Entidades**. Pode crear un novo segmento baseado na entidade creada polo modelo.

1. Na páxina de resultados, seleccione **Crear segmento**.

1. Crea unha regra usando o **OOBsubscriptionChurnPrediction** entidade e define o segmento:
   - **Campo** : ChurnScore
   - **Operador** : máis grande cá
   - **Valor** : 0,6

1. Seleccione **Gardar** e **Corre** o segmento.

Agora ten un segmento que se actualiza dinámicamente para identificar clientes con alto risco de abandono para este negocio da subscrición. Para ver máis información, consulte: [Creación e xestión de segmentos](segments.md).

> [!TIP]
> Tamén podes crear un segmento para un modelo predición a partir de **Segmentos** páxina seleccionando **Novo** e escollendo **Crear dende** > **Intelixencia**. Para obter máis información, consulte [Crea un novo segmento con segmentos rápidos](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
