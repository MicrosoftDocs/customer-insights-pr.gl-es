---
title: Guía de mostra da predición do abandono transaccional
description: Utilice esta guía de mostra para probar o modelo de predición do abandono transaccional listo para usar.
ms.date: 11/19/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: 49dad45c951f3c00d77ddd99faec48bfccada8b0
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306118"
---
# <a name="transactional-churn-prediction-preview-sample-guide"></a>Guía de mostra (previsualización) da predición do abandono transaccional

Esta guía guiarao a través dun exemplo integral de predición do abandono transaccional en Customer Insights empregando os datos fornecidos a continuación. Os datos empregados nesta guía non son datos reais de clientes, senón que forman parte do conxunto de datos de Contoso que se atopa no ambiente de *Demostración* dentro da súa subscrición a Customer Insights.

## <a name="scenario"></a>Escenario

Contoso é unha empresa que produce café e máquinas de café de alta calidade, que se venden a través do sitio web Contoso Coffee. O seu obxectivo é saber que clientes que adoitan mercar os seus produtos de xeito regular deixarán de ser clientes activos nos próximos 60 días. Sabendo cal dos seus clientes é **susceptible de abandonar**, pode axudalos a aforrar esforzos de marketing centrándose en mantelos.

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

   [!div class="mx-imgBorder"]
   ![Transformar DoB en data](media/ecommerce-dob-date.PNG "transformar data de nacemento en data")

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

Despois de inxerir os datos agora comezamos o proceso de **Asignación, busca de coincidencias e combinación** para crear un perfil de cliente unificado. Para obter máis información, consulte [Unificación de datos](data-unification.md).

### <a name="map"></a>Asignar

1. Despois de inxerir os datos, asigne os contactos desde os datos de comercio electrónico e de fidelización a tipos de datos comúns. Vaia a **Datos** > **Unificar** > **Asignar**.

1. Seleccione as entidades que representan o perfil do cliente: **eCommerceContacts** e **loyCustomers**. 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="unificar fontes de datos de comercio electrónico e fidelización.":::

1. Seleccione **ContactId** como clave primaria para **eCommerceContacts** e **LoyaltyID** como clave primaria para **loyCustomers**.

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="Unificar LoyaltyId como clave principal.":::

### <a name="match"></a>Buscar coincidencias

1. Vaia ao separador **Buscar coincidencias** e seleccione **Definir orde**.

1. Na lista despregable **Principal**, escolla **eCommerceContacts : eCommerce** como fonte principal e inclúa todos os rexistros.

1. Na lista despregable **Entidade 2**, escolla **loyCustomers: LoyaltyScheme** e inclúa todos os rexistros.

   :::image type="content" source="media/unify-match-order.PNG" alt-text="unificar coincidencias de comercio electrónico e fidelización.":::

1. Seleccione **Crear unha nova regra**

1. Engada a súa primeira condición usando FullName.

   * Para eCommerceContacts, seleccione **FullName** no menú despregable.
   * Para loyCustomers, seleccione **FullName** no menú despregable.
   * Seleccione o menús despregable **Normalizar** e escolla **Tipo (teléfono, nome, enderezo...)**.
   * Defina o **Nivel de precisión**: **Básico** e **Valor**: **Alto**.

1. Introduza o nome **FullName, Email** para a nova regra.

   * Engada unha segunda condición para o enderezo de correo electrónico seleccionando **Engadir condición**
   * Para os eCommerceContacts da entidade, escolla **Correo electrónico** no menú despregable.
   * Para os loyCustomers da entidade, escolla **Correo electrónico** no menú despregable. 
   * Deixe Normalizar en branco. 
   * Defina o **Nivel de precisión**: **Básico** e **Valor**: **Alto**.

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="Unificar a regra de coincidencia para o nome e o correo electrónico.":::

7. Seleccione **Gardar** e **Executar**.

### <a name="merge"></a>Combinación

1. Vaia ao separador **Combinar**.

1. No **ContactId** da entidade **loyCustomers**, cambie o nome de visualización a **ContactIdLOYALTY** para diferencialo dos outros identificadores inxeridos.

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="renomear contactid do identificador de fidelidade.":::

1. Seleccione **Gardar** e **Executar** para iniciar o proceso de unión.



## <a name="task-3---configure-transaction-churn-prediction"></a>Tarefa 3: configurar a predición de abandono transaccional

Cos perfís de clientes unificados no seu lugar, agora podemos executar a predición de abandono de subscricións. Para os pasos detallados, consulte o artigo [Predición de abandono de subscricións (vista previa)](predict-subscription-churn.md). 

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


[!INCLUDE[footer-include](../includes/footer-banner.md)]