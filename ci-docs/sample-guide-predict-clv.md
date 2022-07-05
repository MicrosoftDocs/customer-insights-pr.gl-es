---
title: Guía de mostra de predición do valor de duración do cliente (VDC)
description: Utilice esta guía de mostra para probar o modelo de predición do valor de duración do cliente.
ms.date: 03/31/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: 2013533ed225a396d21e51e63297d7608ce58ac6
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "9051635"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a>Guía de mostra de predición do valor de duración do cliente (VDC)

Esta guía explicaralle un exemplo integral da predición do valor de duración do cliente (VDC) en Customer Insights usando datos de exemplo.

## <a name="scenario"></a>Escenario

Contoso é unha empresa que produce café e máquinas de café de alta calidade. Venden os produtos a través do seu sitio web Contoso Coffee. A empresa quere comprender o valor (ingresos) que poden xerar os seus clientes nos próximos 12 meses. Coñecer o valor esperado dos seus clientes nos próximos 12 meses axudaralles a dirixir os seus esforzos de márketing cara a clientes valiosos.

## <a name="prerequisites"></a>Requisitos previos

- Polo menos [Permisos de colaborador](permissions.md) en Customer Insights.
- Recomendámoslle que implemente os seguintes pasos [nun novo ambiente](manage-environments.md).

## <a name="task-1---ingest-data"></a>Tarefa 1: inxerir datos

Revisa os artigos [sobre a inxestión de datos](data-sources.md) e [importando fontes de datos usando Power Query conectores](connect-power-query.md). A seguinte información supón que está familiarizado coa inxestión de datos en xeral.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Inxerir datos de clientes desde a plataforma de comercio electrónico

1. Cree unha orixe de datos denominada **eCommerce**, escolla a opción de importación e seleccione o conector **Texto/CSV**.

1. Insira o URL dos contactos de eCommerce [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).

1. Mentres edita os datos, seleccione **Transformar** e logo **Usar a primeira fila como cabeceiras**.

1. Actualice o tipo de datos para as columnas listadas a continuación:
   - **DateOfBirth**: data
   - **CreatedOn**: data/hora/fuso

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transforme a data de nacemento en data.":::

1. No campo "Nome" no panel da dereita, cambie o nome da súa orixe de datos de **Consulta** a **eCommerceContacts**

1. **Garde** a orixe de datos.

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

### <a name="ingest-customer-data-from-website-reviews"></a>Inxerir datos de clientes a partir de comentarios de sitios web

1. Cree unha orixe de datos denominada **Website**, escolla a opción de importación e seleccione o conector **Texto/CSV**.

1. Insira o URL dos contactos de comercio electrónico https://aka.ms/CI-ILT/WebReviews.

1. Mentres edita os datos, seleccione **Transformar** e logo **Usar a primeira fila como cabeceiras**.

1. Actualice o tipo de datos para as columnas listadas a continuación:

   - **ReviewRating**: número decimal
   - **ReviewDate**: data

1. No campo "Nome" no panel da dereita, cambie o nome da súa orixe de datos de **Consulta** a **Revisións**.

1. **Garde** a orixe de datos.

## <a name="task-2---data-unification"></a>Tarefa 2: unificación de datos

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---configure-customer-lifetime-value-prediction"></a>Tarefa 3: Configurar a predición do valor de duración do cliente

Cos perfís de clientes unificados no seu lugar, agora podemos executar a predición do valor de duración do cliente. Para ver os pasos detallados, consulte [Valor de por vida do cliente predición](predict-customer-lifetime-value.md).

1. Vaia a **Intelixencia**  > **Predicións** e seleccione o **Modelo de valor de duración do cliente**.

1. Consulte a información no panel lateral e seleccione **Comezar**.

1. Nomee o modelo **OOB eCommerce CLV Prediction** e a entidade de saída **OOBeCommerceCLVPrediction**.

1. Defina as preferencias do modelo para o modelo VDC:
   - **Período de tempo da predición**: **12 meses ou un ano**. Esta configuración define o período de tempo futuro para predicir o valor de duración do cliente.
   - **Clientes activos**: especifique que significan os clientes activos para a súa empresa. Estableza o intervalo temporal histórico no que un cliente debe ter polo menos unha transacción para considerarse activo. O modelo só predicirá o VDC para clientes activos. Escolla entre deixar que o modelo calcule o período de tempo en base aos datos históricos das transaccións ou proporcione un intervalo temporal específico. Nesta guía de mostra, **deixaremos que o modelo calcule o intervalo de compras**, que é a opción predefinida.
   - **Clientes valiosos**: defina os clientes valiosos como un percentil dos clientes que máis pagan. O modelo utiliza esta entrada para proporcionar resultados que se axusten á definición da súa empresa de clientes valiosos. Pode permitir que o modelo defina os clientes valiosos. Emprega unha regra heurística que deriva o percentil. Tamén pode definir os clientes valiosos como un percentil dos clientes futuros que máis pagarán. Nesta guía de exemplo, definimos manualmente os clientes valiosos como **o 30 % superior dos clientes activos que pagan** e seleccione **Seguinte**.

    :::image type="content" source="media/clv-model-preferences.png" alt-text="Paso de preferencias na experiencia guiada para o modelo VDC.":::

1. No paso **Datos necesarios**, seleccione **Engadir datos** para fornecer os datos do historial de transaccións.

1. Engada a entidade **eCommercePurchases : eCommerce** e asigne os atributos que o modelo precisa:
   - ID da transacción: eCommerce.eCommercePurchases.PurchaseId
   - Data da transacción: eCommerce.eCommercePurchases.PurchasedOn
   - Importe da transacción: eCommerce.eCommercePurchases.TotalPrice
   - ID do produto: eCommerce.eCommercePurchases.ProductId

1. Seleccione **Seguinte**.

1. Configure a relación entre a entidade **eCommercePurchases : eCommerce** e **eCommerceContacts : eCommerce**.

1. O paso **Datos adicionais (opcional)** permítelle engadir máis datos de actividade do cliente. Estes datos poden axudar a obter máis información para as interaccións dos clientes coa súa empresa, o que pode contribuír ao VDC. Engadir interaccións clave dos clientes, como rexistros web, rexistros do servizo de atención ao cliente ou historial do programa de recompensa, pode mellorar a precisión das predicións. Seleccione **Engadir datos** para incluír máis datos de actividade do cliente.

1. Engada a entidade de actividade do cliente e asigne os nomes dos seus campos aos campos correspondentes requiridos polo modelo:
   - Entidade de actividade do cliente: Reviews:Website
   - Clave principal: Website.Reviews.ReviewId
   - Marca de tempo: Website.Reviews.ReviewDate
   - Evento (nome da actividade): Website.Reviews.ActivityTypeDisplay
   - Detalles (importe ou valor): Website.Reviews.ReviewRating

1. Seleccione **Seguinte** e configure a actividade e a relación entre os datos da transacción e os datos do cliente:  
   - Tipo de actividade: escoller existente
   - Etiqueta de actividade: revisar
   - Etiqueta correspondente: Website.Reviews.UserId
   - Entidade de cliente: eCommerceContacts:eCommerce
   - Relación: WebsiteReviews

1. Seleccione **Seguinte** para establecer a programación do modelo.

   O modelo necesita adestrarse regularmente para aprender novos padróns cando se inxiren novos datos. Para este exemplo, escolla **Mensual**.

1. Despois de revisar todos os detalles, seleccione **Gardar e executar**.

## <a name="task-4---review-model-results-and-explanations"></a>Tarefa 4: revisar resultados e explicacións do modelo

Deixe que o modelo complete o adestramento e a puntuación dos datos. A continuación, pode revisar os resultados e explicacións do modelo VDC. Para obter máis información, consulte [Revisar o estado e os resultados dunha predición](predict-customer-lifetime-value.md#review-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-value-customers"></a>Tarefa 5: Crear un segmento de clientes valiosos

Ao executar o modelo créase unha nova entidade, que aparece na lista **Datos** > **Entidades**. Pode crear un novo segmento de clientes baseado na entidade creada polo modelo.

1. Vaia a **Segmentos**. 

1. Seleccione **Novo** e elixa **Crear a partir de** > **Intelixencia**.

   ![Creación dun segmento coa saída do modelo.](media/segment-intelligence.png)

1. Seleccione a entidade **OOBeCommerceCLVPrediction** e defina o segmento:
  - Campo: CLVScore
  - Operador: maior que
  - Valor: 1500

1. Seleccione **Revisar** e **Gardar** o segmento.

Agora ten un segmento que identifica os clientes que se predí que xeren ingresos superiores a 1500 $ nos próximos 12 meses. Este segmento actualízase dinamicamente se se inxiren máis datos.

Para ver máis información, consulte: [Creación e xestión de segmentos](segments.md).
