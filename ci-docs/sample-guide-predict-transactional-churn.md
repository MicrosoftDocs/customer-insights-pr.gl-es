---
title: Guía de mostra da predición do abandono transaccional
description: Utilice esta guía de mostra para probar o modelo de predición do abandono transaccional listo para usar.
ms.date: 05/11/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 3edbf2a471313379c28db874d7f19c3265a23299
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741317"
---
# <a name="transactional-churn-prediction-sample-guide"></a>Guía de mostra da predición do abandono transaccional

Esta guía guiarao a través dun exemplo integral de predición do abandono transaccional en Customer Insights empregando os datos fornecidos a continuación. Todos os datos empregados nesta guía non son datos reais do cliente e forman parte do conxunto de datos de Contoso que se atopan no ambiente de *demostración* dentro da súa subscrición a Customer Insights.

## <a name="scenario"></a>Escenario

Contoso é unha empresa que produce cafés e máquinas de café de alta calidade, que venden a través do seu sitio web Contoso Coffee. O seu obxectivo é saber que clientes que adoitan mercar os seus produtos de xeito regular deixarán de ser clientes activos nos próximos 60 días. Sabendo cal dos seus clientes é **susceptible de abandonar**, pode axudalos a aforrar esforzos de marketing centrándose en mantelos.

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

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformar DoB en data.":::

1. No campo **Nome** no panel da dereita, cambie o nome da súa orixe de datos de **Consulta** a **eCommerceContacts**

1. Garde a orixe de datos.

### <a name="ingest-online-purchase-data"></a>Inxerir datos de compra en liña

1. Engada outro conxunto de datos á mesma orixe de datos de **comercio electrónico**. Escolla o conector **Texto/CSV** de novo.

1. Introduza o URL para datos de **compras en liña** https://aka.ms/ciadclassonline.

1. Mentres edita os datos, seleccione **Transformar** e logo **Usar a primeira fila como cabeceiras**.

1. Actualice o tipo de datos para as columnas listadas a continuación:

   - **PurchasedOn**: data/hora
   - **TotalPrice**: moeda
   
1. No campo **Nome** no panel da dereita, cambie o nome da súa orixe de datos de **Consulta** a **eCommercePurchases**.

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

## <a name="task-2---data-unification"></a>Tarefa 2: unificación de datos

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---configure-transaction-churn-prediction"></a>Tarefa 3: configurar a predición de abandono transaccional

Cos perfís de clientes unificados, agora podemos executar o churn de transaccións predición. Para ver os pasos detallados, consulte [Churn de transaccións predición](predict-transactional-churn.md) artigo. 

1. Vaia a **Intelixencia** > **Descubrir** e seleccione para usar o **Modelo de abandono do cliente**.

1. Seleccione a opción **Transaccional** e seleccione **Comezar**.

1. Nomee o modelo **Predición do abandono de transaccións de comercio electrónico de OOB** e a entidade de saída **OOBeCommerceChurnPrediction**.

1. Defina dúas condicións para o modelo de abandono:

   * **Xanela de predición**: **polo menos 60** días. Esta configuración define ata que punto do futuro queremos predicir o abandono do cliente.

   * **Definición de abandono**: **polo menos 60** días. A duración sen compra despois da cal se considera que un cliente abandonou.

     :::image type="content" source="media/model-levers.PNG" alt-text="Seleccione as opcións do modelo Ventá de predición e Definición de abandono.":::

1. Seleccione **Historial de compras (obrigatorio)** e seleccione **Engadir datos** para o historial de compras.

1. Engada a entidade **eCommercePurchases : eCommerce** e asigne os campos de comercio electrónico aos campos correspondentes requiridos polo modelo.

1. Una a entidade **eCommercePurchases : eCommerce** con **eCommerceContacts : eCommerce**.

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="Unir entidades de comercio electrónico.":::

1. Seleccione **Seguinte** para establecer a programación do modelo.

   O modelo necesita adestrarse regularmente para aprender novos padróns cando se inxiren novos datos. Para este exemplo, seleccione **Mensual**.

1. Despois de revisar todos os detalles, seleccione **Gardar e executar**.

## <a name="task-4---review-model-results-and-explanations"></a>Tarefa 4: revisar resultados e explicacións do modelo

Deixe que o modelo complete o adestramento e a puntuación dos datos. Agora podes revisar as explicacións do modelo de churn. Para obter máis información, consulte [Revisar o estado e os resultados dunha predición](predict-transactional-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a>Tarefa 5: crear un segmento de clientes con alto risco de abandono

Executar o modelo de produción crea unha nova entidade na que pode ver en **Datos** > **Entidades**.   

Pode crear un novo segmento baseado na entidade creada polo modelo.

1.  Vaia a **Segmentos**. Seleccione **Novo** e elixa **Crear a partir de** > **Intelixencia**. 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Creación dun segmento coa saída do modelo.":::

1. Seleccione o **OOBeCommerceChurnPrediction** punto final e define o segmento: 
   - Campo: ChurnScore
   - Operador: maior que
   - Valor: 0,6

Agora tes un segmento que se actualiza de forma dinámica que identifica clientes con alto risco de abandono.

Para ver máis información, consulte: [Creación e xestión de segmentos](segments.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]
