---
title: Guía de mostra de predición de recomendacións de produtos
description: Utilice esta guía de mostra para probar o modelo de predición de recomendacións de produtos.
ms.date: 05/16/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-predictions
- ci-create-prediction
- customerInsights
ms.openlocfilehash: cc72cce15fa0c9e92dbf202c803e99514c9ce2b1
ms.sourcegitcommit: 82f417cfb0a16600e9f552d7a21d598cc8f5a267
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 05/16/2022
ms.locfileid: "8762684"
---
# <a name="product-recommendation-prediction-sample-guide"></a>Guía de mostra de predición de recomendacións de produtos

Guiarémolo a través dun exemplo integral de predición de recomendacións de produtos empregando os datos de exemplo fornecidos a continuación.

## <a name="scenario"></a>Escenario

Contoso é unha empresa que produce cafés e máquinas de café de alta calidade, que venden a través do seu sitio web Contoso Coffee. O seu obxectivo é comprender que produtos deben recomendar aos seus clientes recorrentes. Sabendo que clientes son máis **susceptibles a comprar**, pode axudalos a aforrar esforzos de marketing centrándose en elementos específicos.

## <a name="prerequisites"></a>Requisitos previos

- Polo menos [Permisos de colaborador](permissions.md) en Customer Insights.
- Recomendámoslle que implemente os seguintes pasos [nun novo ambiente](manage-environments.md).

## <a name="task-1---ingest-data"></a>Tarefa 1: inxerir datos

Revisa os artigos [sobre a inxestión de datos](data-sources.md) e [importando fontes de datos usando Power Query conectores](connect-power-query.md) concretamente. A seguinte información supón que está familiarizado coa inxestión de datos en xeral.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Inxerir datos de clientes desde a plataforma de comercio electrónico

1. Cree unha orixe de datos denominada **eCommerce**, escolla a opción de importación e seleccione o conector **Texto/CSV**.

1. Introduza o URL dos contactos de comercio electrónico: [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).

1. Mentres edita os datos, seleccione **Transformar** e logo **Usar a primeira fila como cabeceiras**.

1. Actualice o tipo de datos para as columnas listadas a continuación:
   - **DateOfBirth**: data
   - **CreatedOn**: data/hora/fuso

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transforme a data de nacemento en data.":::

1. No campo "Nome" no panel da dereita, cambie o nome da súa orixe de datos de **Consulta** a **eCommerceContacts**

1. **Garde** a orixe de datos.

### <a name="ingest-online-purchase-data"></a>Inxerir datos de compra en liña

1. Engada outro conxunto de datos á mesma orixe de datos de **comercio electrónico**. Escolla o conector **Texto/CSV** de novo.

1. Introduza o URL para **Compras en liña** datos [https://aka.ms/ciadclassonline](https://aka.ms/ciadclassonline).

1. Mentres edita os datos, seleccione **Transformar** e logo **Usar a primeira fila como cabeceiras**.

1. Actualice o tipo de datos para as columnas listadas a continuación:
   - **PurchasedOn**: data/hora
   - **TotalPrice**: moeda

1. No campo **Nome** do panel lateral, cambie o nome da súa orixe de datos de **Consulta** a **eCommercePurchases**.

1. **Garde** a orixe de datos.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Inxerir datos de clientes desde o esquema de fidelización

1. Cree unha orixe de datos denominada **LoyaltyScheme**, escolla a opción de importación e seleccione o conector **Texto/CSV**.

1. Introduza o URL dos contactos de comercio electrónico [https://aka.ms/ciadclasscustomerloyalty](https://aka.ms/ciadclasscustomerloyalty).

1. Mentres edita os datos, seleccione **Transformar** e logo **Usar a primeira fila como cabeceiras**.

1. Actualice o tipo de datos para as columnas listadas a continuación:
   - **DateOfBirth**: data
   - **RewardsPoints**: número enteiro
   - **CreatedOn**: data/hora

1. No campo **Nome** no panel da dereita, cambie o nome da súa orixe de datos de **Consulta** a **loyCustomers**.

1. **Garde** a orixe de datos.

## <a name="task-2---data-unification"></a>Tarefa 2: unificación de datos

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---configure-product-recommendation-prediction"></a>Tarefa 3: configurar a predición de recomendacións de produtos

Cos perfís de clientes unificados, agora podemos executar a recomendación de produtos predición.

1. Vaia a **Intelixencia** > **Predición** e escolla **Recomendación de produtos**.

1. Seleccione **Comezar**.

1. Dea nome ao modelo **Predición do modelo de recomendación de produtos de OOB** e a entidade de saída **OOBProductRecommendationModelPrediction**.

1. Defina tres condicións para o modelo:

   - **Número de produtos**: Configure este valor en **5**. Esta configuración define cantos produtos desexa recomendar aos seus clientes.

   - **Compras repetidas esperadas**: seleccione **Si** para indicar que quere incluír produtos na recomendación que os seus clientes compraron con anterioridade.

   - **Ventá para ver días pasados:** Seleccione polo menos **365 días**. Esta configuración define o número de días pasados que o modelo mira na actividade do cliente que se van usar como entrada para as súas recomendacións.

   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Preferencias do modelo de recomendación de produtos.":::

1. No **Engade os datos necesarios** paso, seleccione **Engadir datos**.

1. No **Engadir datos** panel, escolla o **Liña de pedido de vendas** como a entidade do historial de compras. Neste momento, é probable que aínda non estea configurado. Abre a ligazón no panel para crear a actividade cos seguintes pasos:
   1. Introduza un **Nome da actividade** e escolle *eCommerceCompras: eCommerce* como **Entidade actividade**. O **Chave primaria** é *Id de compra*.
   1. Define e nomea a relación co *eCommerceContacts: entidade de comercio electrónico* e escolle **ContactId** como clave externa.
   1. Para a unificación de actividade, establece **Actividade do evento** como *Prezo total* e marca de tempo para *CompradoOn*. Podes especificar máis campos como se indica en [Actividades do cliente](activities.md).
   1. Para **Tipo de actividade**, escolle *Liña de pedido de vendas*. Mapea os seguintes campos de actividade:
      - ID da liña de pedido: PurchaseId
      - ID do pedido: PurchaseId
      - Datos do pedido: PurchasedOn
      - ID do produto: ID do produto
      - Importe: Prezo total
   1. Revisa e remata a actividade antes de volver á configuración do modelo.

1. De volta no **Selecciona actividades** paso, escolla a actividade recentemente creada no **Actividades** sección. Seleccione **A continuación** e a asignación de atributos xa está cuberta. Seleccione **Gardar**.

1. Nesta guía de exemplo, omitimos o **Engade información do produto** e **Filtros de produtos** definido porque non temos datos de información do produto.

1. No **Actualizacións de datos** paso, configure o horario do modelo.

   O modelo necesita adestrarse regularmente para aprender novos padróns cando se inxiren novos datos. Para este exemplo, seleccione **Mensual**.

1. Despois de revisar todos os detalles, seleccione **Gardar e executar**. Levará uns minutos executar o modelo a primeira vez.

## <a name="task-4---review-model-results-and-explanations"></a>Tarefa 4: revisar resultados e explicacións do modelo

Deixe que o modelo complete o adestramento e a puntuación dos datos. Agora pode revisar as explicacións do modelo de recomendación de produtos. Para obter máis información, consulte [Revisar o estado e os resultados dunha predición](predict-transactional-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-purchased-products"></a>Tarefa 5: crear un segmento de produtos moi comprados

Executar o modelo de produción crea unha nova entidade na que pode ver en **Datos** > **Entidades**.

Pode crear un novo segmento baseado na entidade creada polo modelo.

1. Vaia a **Segmentos**. Seleccione **Novo** e escolle **Crear a partir da intelixencia**.

   ![Creación dun segmento coa saída do modelo.](media/segment-intelligence.png)

1. Seleccione o extremo **OOBProductRecommendationModelPrediction** e defina o segmento:

   - Campo: ProductID
   - Valor: seleccione os tres identificadores de produto principais

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="Cree un segmento a partir dos resultados do modelo.":::

Agora tes un segmento que se actualiza de forma dinámica que identifica os clientes que poden estar interesados en comprar os tres produtos máis recomendados.

Para ver máis información, consulte: [Creación e xestión de segmentos](segments.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
