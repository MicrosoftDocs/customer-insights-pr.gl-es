---
title: Guía de mostra de predición do valor de duración do cliente (VDC)
description: Utilice esta guía de mostra para probar o modelo de predición do valor de duración do cliente.
ms.date: 09/15/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: fec43b279326daa17fb179181f5e310c99d48bb7
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609636"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a>Guía de mostra de predición do valor de duración do cliente (VDC)

Esta guía guíache por un exemplo de extremo a extremo do valor de vida útil do cliente (CLV) predición en Customer Insights utilizando datos de mostra. Recomendámosche que probes este predición [nun novo ambiente](manage-environments.md).

## <a name="scenario"></a>Escenario

Contoso é unha empresa que produce café e máquinas de café de alta calidade. Venden os produtos a través do seu sitio web Contoso Coffee. A empresa quere comprender o valor (ingresos) que poden xerar os seus clientes nos próximos 12 meses. Coñecer o valor esperado dos seus clientes nos próximos 12 meses axudaralles a dirixir os seus esforzos de márketing cara a clientes valiosos.

## <a name="prerequisites"></a>Requisitos previos

- Polo menos [Permisos de colaborador](permissions.md).

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

1. **Garde** a orixe de datos.

### <a name="ingest-online-purchase-data"></a>Inxerir datos de compra en liña

1. Engada outro conxunto de datos á mesma orixe de datos de **comercio electrónico**. Escolla o conector **Texto/CSV** de novo.

1. Introduza o URL para datos de **compras en liña** https://aka.ms/ciadclassonline.

1. Mentres editas os datos, selecciona **Transformar** e despois **Use a primeira fila como cabeceiras**.

1. Actualice o tipo de datos para as columnas listadas a continuación:
   - **PurchasedOn**: data/hora
   - **TotalPrice**: moeda

1. No **Nome** no panel lateral, cambie o nome do seu orixe de datos a **eCommerceCompras**.

1. **Garde** a orixe de datos.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Inxerir datos de clientes desde o esquema de fidelización

1. Crea un orixe de datos chamado **Esquema de fidelidade** e selecciona o **Texto/CSV** conector.

1. Introduza o URL para os clientes de fidelidade https://aka.ms/ciadclasscustomerloyalty.

1. Mentres editas os datos, selecciona **Transformar** e despois **Use a primeira fila como cabeceiras**.

1. Actualice o tipo de datos para as columnas listadas a continuación:
   - **DateOfBirth**: data
   - **RewardsPoints**: número enteiro
   - **CreatedOn**: data/hora

1. No **Nome** no panel da dereita, cambie o nome do seu orixe de datos a **Clientes loy**.

1. **Garde** a orixe de datos.

### <a name="ingest-customer-data-from-website-reviews"></a>Inxerir datos de clientes a partir de comentarios de sitios web

1. Crea un orixe de datos chamado **Sitio web** e selecciona o **Texto/CSV** conector.

1. Introduza o URL para as revisións do sitio web https://aka.ms/CI-ILT/WebReviews.

1. Mentres editas os datos, selecciona **Transformar** e despois **Use a primeira fila como cabeceiras**.

1. Actualice o tipo de datos para as columnas listadas a continuación:
   - **ReviewRating**: número decimal
   - **ReviewDate**: data

1. No **Nome** no panel da dereita, cambie o nome do seu orixe de datos a **Recensións**.

1. **Garde** a orixe de datos.

## <a name="task-2---data-unification"></a>Tarefa 2: unificación de datos

Revisa o artigo [sobre a unificación de datos](data-unification.md). A seguinte información supón que está familiarizado coa unificación de datos en xeral.

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---create-transaction-history-activity"></a>Tarefa 3: crear actividade de historial de transaccións

Revisa o artigo [sobre as actividades dos clientes](activities.md). A seguinte información supón que está familiarizado coa creación de actividades en xeral.

1. Crea unha actividade chamada **eCommerceCompras** co *eCommerceCompras: eCommerce* entidade e a súa clave primaria, **Id de compra**.

1. Crea unha relación entre *eCommercePurchases: eCommerce* e *eCommerceContactos: eCommerce* con **ContactID** como clave externa para conectar as dúas entidades.

1. Seleccione **Prezo total** para o **EventActivity** e **CompradoOn** para o **Selo de tempo**.

1. Seleccione **Liña de pedidos de vendas** para o **Tipo de actividade** e mapear semanticamente os datos da actividade.

1. Executar a actividade.

1. Engade outra actividade e asigna os nomes dos seus campos aos campos correspondentes:
   - **Entidade da actividade** : Recensións: Sitio web
   - **Chave primaria** : ReviewId
   - **Selo de tempo** : Data de revisión
   - **Actividade do evento** : ActivityTypeDisplay
   - **Detalle adicional** : Valoración da revisión
   - **Tipo de actividade** : Revisión

1. Executar a actividade.

## <a name="task-4---configure-customer-lifetime-value-prediction"></a>Tarefa 4: Configurar a predición do valor de duración do cliente

Cos perfís de clientes unificados e a actividade creada, executa o valor de vida útil do cliente (CLV) predición. Para os pasos detallados, consulte [Valor de por vida do cliente predición](predict-customer-lifetime-value.md).

1. Ir a **Intelixencia** > **Predicións**.

1. No **Crear** ficha, seleccione **Usa modelo** no **Valor de vida do cliente** tella.

1. Seleccione **Comezar**.

1. Nomee o modelo **OOB eCommerce CLV Prediction** e a entidade de saída **OOBeCommerceCLVPrediction**.

1. Definir as preferencias do modelo:
   - **Período de tempo predición** :**12 meses ou 1 ano** para definir ata onde se prevé o CLV no futuro.
   - **Clientes activos** :**Deixa que o modelo calcule o intervalo de compra** que é o período de tempo no que un cliente debe ter realizado polo menos unha transacción para ser considerado activo.
   - **Cliente de alto valor** : define manualmente clientes de alto valor como **30% dos clientes activos**.

    :::image type="content" source="media/clv-model-preferences.png" alt-text="Paso de preferencias na experiencia guiada para o modelo VDC.":::

1. Seleccione **Seguinte**.

1. No paso **Datos necesarios**, seleccione **Engadir datos** para fornecer os datos do historial de transaccións.

    :::image type="content" source="media/clv-model-required.png" alt-text="Engade o paso dos datos necesarios na experiencia guiada para o modelo CLV.":::

1. Seleccione **Liña de pedidos de vendas** e a entidade eCommercePurchases e seleccione **A continuación**. Os datos necesarios enchéranse automaticamente desde a actividade. Seleccione **Gardar** e despois **A continuación**.

1. O **Datos adicionais (opcional)** paso permítelle engadir máis datos de actividade dos clientes para obter máis información sobre as interaccións dos clientes. Para este exemplo, seleccione **Engadir datos** e engade a actividade de revisión web.

1. Seleccione **Seguinte**.

1. No **Actualizacións de datos** paso, seleccione **Mensuais** para o modelo de horario.

1. Seleccione **Seguinte**.

1. Despois de revisar todos os detalles, seleccione **Gardar e executar**.

## <a name="task-5---review-model-results-and-explanations"></a>Tarefa 5: revisar resultados e explicacións do modelo

Deixe que o modelo complete o adestramento e a puntuación dos datos. Revisa o [Resultados e explicacións do modelo CLV](predict-customer-lifetime-value.md#view-prediction-results).

## <a name="task-6---create-a-segment-of-high-value-customers"></a>Tarefa 6: Crear un segmento de clientes valiosos

Ao executar o modelo créase unha nova entidade, que aparece na lista **Datos** > **Entidades**. Pode crear un novo segmento de clientes baseado na entidade creada polo modelo.

1. Na páxina de resultados, seleccione **Crear segmento**.

1. Crea unha regra usando o **OOBeCommerceCLVPrediction** entidade e define o segmento:
   - **Campo** : CLVScore
   - **Operador** : máis grande cá
   - **Valor** : 1500

1. Seleccione **Gardar** e **Corre** o segmento.

Agora ten un segmento que identifica os clientes que se predí que xeren ingresos superiores a 1500 $ nos próximos 12 meses. Este segmento actualízase dinamicamente se se inxiren máis datos. Para ver máis información, consulte: [Creación e xestión de segmentos](segments.md).

> [!TIP]
> Tamén podes crear un segmento para un modelo predición a partir de **Segmentos** páxina seleccionando **Novo** e escollendo **Crear dende** > **Intelixencia**. Para obter máis información, consulte [Crea un novo segmento con segmentos rápidos](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
