---
title: Guía de mostra de predición de recomendacións de produtos
description: Utilice esta guía de mostra para probar o modelo de predición de recomendacións de produtos.
ms.date: 02/10/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: a85ee598ec747d0594755314e83a127ce0f2af95
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306164"
---
# <a name="product-recommendation-prediction-preview-sample-guide"></a>Guía de mostra de predición de recomendacións de produtos (versión preliminar)

Guiarémolo a través dun exemplo integral de predición de recomendacións de produtos empregando os datos de exemplo fornecidos a continuación.

## <a name="scenario"></a>Escenario

Contoso é unha empresa que produce café e máquinas de café de alta calidade, que se venden a través do sitio web Contoso Coffee. O seu obxectivo é comprender que produtos deben recomendar aos seus clientes recorrentes. Sabendo que clientes son máis **susceptibles a comprar**, pode axudalos a aforrar esforzos de marketing centrándose en elementos específicos.

## <a name="prerequisites"></a>Requisitos previos

- Polo menos [Permisos de colaborador](permissions.md) en Customer Insights.
- Recomendámoslle que implemente os seguintes pasos [nun novo ambiente](manage-environments.md).

## <a name="task-1---ingest-data"></a>Tarefa 1: inxerir datos

Revise os artigos [sobre a inxestión de datos](data-sources.md) e a [importación de fontes de datos usando conectores de Power Query](connect-power-query.md) especificamente. A seguinte información supón que está familiarizado coa inxestión de datos en xeral.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Inxerir datos de clientes desde a plataforma de comercio electrónico

1. Cree unha orixe de datos denominada **eCommerce**, escolla a opción de importación e seleccione o conector **Texto/CSV**.

1. Insira o URL dos contactos de comercio electrónico https://aka.ms/ciadclasscontacts.

1. Mentres edita os datos, seleccione **Transformar** e logo **Usar a primeira fila como cabeceiras**.

1. Actualice o tipo de datos para as columnas listadas a continuación:
   - **DateOfBirth**: data
   - **CreatedOn**: data/hora/fuso

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transforme a data de nacemento en data.":::

5. No campo "Nome" no panel da dereita, cambie o nome da súa orixe de datos de **Consulta** a **eCommerceContacts**

6. **Garde** a orixe de datos.

### <a name="ingest-online-purchase-data"></a>Inxerir datos de compra en liña

1. Engada outro conxunto de datos á mesma orixe de datos de **comercio electrónico**. Escolla o conector **Texto/CSV** de novo.

1. Introduza o URL para datos de **compras en liña** https://aka.ms/ciadclassonline.

1. Mentres edita os datos, seleccione **Transformar** e logo **Usar a primeira fila como cabeceiras**.

1. Actualice o tipo de datos para as columnas listadas a continuación:
   - **PurchasedOn**: data/hora
   - **TotalPrice**: moeda

1. No campo **Nome** do panel lateral, cambie o nome da súa orixe de datos de **Consulta** a **eCommercePurchases**.

1. **Garde** a orixe de datos.


### <a name="ingest-customer-data-from-loyalty-schema"></a>Inxerir datos de clientes desde o esquema de fidelización

1. Cree unha orixe de datos denominada **LoyaltyScheme**, escolla a opción de importación e seleccione o conector **Texto/CSV**.

1. Insira o URL dos contactos de comercio electrónico https://aka.ms/ciadclasscustomerloyalty.

1. Mentres edita os datos, seleccione **Transformar** e logo **Usar a primeira fila como cabeceiras**.

1. Actualice o tipo de datos para as columnas listadas a continuación:
   - **DateOfBirth**: data
   - **RewardsPoints**: número enteiro
   - **CreatedOn**: data/hora

1. No campo **Nome** no panel da dereita, cambie o nome da súa orixe de datos de **Consulta** a **loyCustomers**.

1. **Garde** a orixe de datos.

## <a name="task-2---data-unification"></a>Tarefa 2: unificación de datos

Despois de inxerir os datos, comezamos o proceso de unificación de datos para crear un perfil de cliente unificado. Para obter máis información, consulte [Unificación de datos](data-unification.md).

### <a name="map"></a>Asignar

1. Despois de inxerir os datos, asigne os contactos desde os datos de comercio electrónico e de fidelización a tipos de datos comúns. Vaia a **Datos** > **Unificar** > **Asignar**.

2. Seleccione as entidades que representan o perfil do cliente: **eCommerceContacts** e **loyCustomers**.

   ![unificar fontes de datos de comercio electrónico e fidelización.](media/unify-ecommerce-loyalty.png)

3. Seleccione **ContactId** como clave primaria para **eCommerceContacts** e **LoyaltyID** como clave primaria para **loyCustomers**.

   ![Unificar LoyaltyId como clave principal.](media/unify-loyaltyid.png)

### <a name="match"></a>Buscar coincidencias

1. Vaia ao separador **Buscar coincidencias** e seleccione **Definir orde**.

2. Na lista despregable **Principal**, escolla **eCommerceContacts : eCommerce** como fonte principal e inclúa todos os rexistros.

3. Na lista despregable **Entidade 2**, escolla **loyCustomers: LoyaltyScheme** e inclúa todos os rexistros.

   ![unificar coincidencias de comercio electrónico e fidelización.](media/unify-match-order.png)

4. Seleccione **Crear unha nova regra**

5. Engada a súa primeira condición usando FullName.

   - Para eCommerceContacts, seleccione **FullName** no menú despregable.
   - Para loyCustomers, seleccione **FullName** no menú despregable.
   - Seleccione o menús despregable **Normalizar** e escolla **Tipo (teléfono, nome, enderezo...)**.
   - Defina o **Nivel de precisión**: **Básico** e **Valor**: **Alto**.

6. Introduza o nome **FullName, Email** para a nova regra.

   - Engada unha segunda condición para o enderezo de correo electrónico seleccionando **Engadir condición**
   - Para os eCommerceContacts da entidade, escolla **Correo electrónico** no menú despregable.
   - Para os loyCustomers da entidade, escolla **Correo electrónico** no menú despregable.
   - Deixe Normalizar en branco.
   - Defina o **Nivel de precisión**: **Básico** e **Valor**: **Alto**.

   ![Unificar a regra de coincidencia para o nome e o correo electrónico.](media/unify-match-rule.png)

7. Seleccione **Gardar** e **Executar**.

### <a name="merge"></a>Combinación

1. Vaia ao separador **Combinar**.

1. No **ContactId** da entidade **loyCustomers**, cambie o nome de visualización a **ContactIdLOYALTY** para diferencialo dos outros identificadores inxeridos.

   ![renomear contactid do identificador de fidelidade.](media/unify-merge-contactid.png)

1. Seleccione **Gardar** e **Executar** para iniciar o proceso de unión.

## <a name="task-3---configure-product-recommendation-prediction"></a>Tarefa 3: configurar a predición de recomendacións de produtos

Cos perfís de clientes unificados no seu lugar, agora podemos executar a predición de abandono de subscricións.

1. Vaia a **Intelixencia** > **Predición** e escolla **Recomendación de produtos**.

1. Seleccione **Comezar**.

1. Dea nome ao modelo **Predición do modelo de recomendación de produtos de OOB** e a entidade de saída **OOBProductRecommendationModelPrediction**.

1. Defina tres condicións para o modelo:

   - **Número de produtos**: Configure este valor en **5**. Esta configuración define cantos produtos desexa recomendar aos seus clientes.

   - **Compras repetidas esperadas**: seleccione **Si** para indicar que quere incluír produtos na recomendación que os seus clientes compraron con anterioridade.

   - **Ventá para ver días pasados:** Seleccione polo menos **365 días**. Esta configuración define o número de días pasados que o modelo mira na actividade do cliente que se van usar como entrada para as súas recomendacións.
   
   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Preferencias do modelo de recomendación de produtos.":::

1. Seleccione **Datos requiridos** e seleccione **Engadir datos** para o historial de compras.

1. Engada a entidade **eCommercePurchases : eCommerce** e asigne os campos de comercio electrónico aos campos correspondentes requiridos polo modelo.

1. Una a entidade **eCommercePurchases : eCommerce** con **eCommerceContacts : eCommerce**.

   ![Unir entidades de comercio electrónico.](media/model-purchase-join.png)

1. Seleccione **Seguinte** para establecer a programación do modelo.

   O modelo necesita adestrarse regularmente para aprender novos padróns cando se inxiren novos datos. Para este exemplo, seleccione **Mensual**.

1. Despois de revisar todos os detalles, seleccione **Gardar e executar**.


## <a name="task-4---review-model-results-and-explanations"></a>Tarefa 4: revisar resultados e explicacións do modelo

Deixe que o modelo complete o adestramento e a puntuación dos datos. Agora pode revisar as explicacións do modelo de recomendación de produtos. Para obter máis información, consulte [Revisar o estado e os resultados dunha predición](predict-subscription-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-purchased-products"></a>Tarefa 5: crear un segmento de produtos moi comprados

Executar o modelo de produción crea unha nova entidade na que pode ver en **Datos** > **Entidades**.

Pode crear un novo segmento baseado na entidade creada polo modelo.

1. Vaia a **Segmentos**. Seleccione **Novo** e elixa **Crear a partir de** > **Intelixencia**.

   ![Creación dun segmento coa saída do modelo.](media/segment-intelligence.png)

1. Seleccione o extremo **OOBProductRecommendationModelPrediction** e defina o segmento:

   - Campo: ProductID
   - Operador: Valor
   - Valor: seleccione os tres identificadores de produto principais

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="Cree un segmento a partir dos resultados do modelo.":::

Agora ten un segmento que se actualiza dinamicamente e identifica aos clientes que están máis dispostos a mercar os tres produtos máis recomendados 

Para ver máis información, consulte: [Creación e xestión de segmentos](segments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
