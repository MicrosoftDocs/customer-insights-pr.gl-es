---
title: Guía de mostra de predición de recomendacións de produtos
description: Utilice esta guía de mostra para probar o modelo de predición de recomendacións de produtos.
ms.date: 09/19/2022
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
ms.openlocfilehash: 2b42a89e3f4ec8cf4f0769128b8536973365f1cb
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610142"
---
# <a name="product-recommendation-prediction-sample-guide"></a>Guía de mostra de predición de recomendacións de produtos

Esta guía guíache por un exemplo completo de recomendación de produtos predición utilizando datos de mostra. Recomendámosche que probes este predición [nun novo ambiente](manage-environments.md).

## <a name="scenario"></a>Escenario

Contoso é unha empresa que produce café e máquinas de café de alta calidade. Venden os produtos a través do seu sitio web Contoso Coffee. O seu obxectivo é comprender que produtos deben recomendar aos seus clientes recorrentes. Coñecer cales son máis os clientes **susceptible de comprar** pode axudarlles a aforrar esforzos de mercadotecnia centrándose en elementos específicos.

## <a name="prerequisites"></a>Requisitos previos

- Polo menos [Permisos de colaborador](permissions.md) en Customer Insights.

## <a name="task-1---ingest-data"></a>Tarefa 1: inxerir datos

Revisa os artigos [sobre a inxestión de datos](data-sources.md) e [conectando a a Power Query orixe de datos](connect-power-query.md). A seguinte información supón que estás familiarizado coa inxestión de datos en xeral.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Inxerir datos de clientes desde a plataforma de comercio electrónico

1. Crea un Power Query orixe de datos chamado **comercio electrónico** e selecciona o **Texto/CSV** conector.

1. Introduza o URL dos contactos de comercio electrónico:https://aka.ms/ciadclasscontacts.

1. Mentres editas os datos, selecciona **Transformar** e despois **Use a primeira fila como cabeceiras**.

1. Actualice o tipo de datos para as columnas listadas a continuación:
   - **DateOfBirth**: data
   - **CreatedOn**: data/hora/fuso

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transforme a data de nacemento en data.":::

1. No **Nome** no panel da dereita, cambie o nome do seu orixe de datos a **eCommerceContactos**.

1. **Garde** a orixe de datos.

### <a name="ingest-online-purchase-data"></a>Inxerir datos de compra en liña

1. Engada outro conxunto de datos á mesma orixe de datos de **comercio electrónico**. Escolla o conector **Texto/CSV** de novo.

1. Introduza o URL dos datos de compras en liña https://aka.ms/ciadclassonline.

1. Mentres editas os datos, selecciona **Transformar** e despois **Use a primeira fila como cabeceiras**.

1. Actualice o tipo de datos para as columnas listadas a continuación:
   - **PurchasedOn**: data/hora
   - **TotalPrice**: moeda

1. No **Nome** no panel lateral, cambie o nome do seu orixe de datos a **eCommerceCompras**.

1. **Garde** a orixe de datos.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Inxerir datos de clientes desde o esquema de fidelización

1. Crea un orixe de datos chamado **Esquema de fidelidade** e selecciona o **Texto/CSV** conector.

1. Introduza o URL dos clientes fieis https://aka.ms/ciadclasscustomerloyalty.

1. Mentres editas os datos, selecciona **Transformar** e despois **Use a primeira fila como cabeceiras**.

1. Actualice o tipo de datos para as columnas listadas a continuación:
   - **DateOfBirth**: data
   - **RewardsPoints**: número enteiro
   - **CreatedOn**: data/hora

1. No **Nome** no panel da dereita, cambie o nome do seu orixe de datos a **Clientes loy**.

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

## <a name="task-4---configure-product-recommendation-prediction"></a>Tarefa 4: configurar a predición de recomendacións de produtos

Cos perfís de clientes unificados e a actividade creada, executa a recomendación de produto predición.

1. Ir a **Intelixencia** > **Predicións**.

1. No **Crear** ficha, seleccione **Usa modelo** no **Recomendacións de produtos (vista previa)** tella.

1. Seleccione **Comezar**.

1. Dea nome ao modelo **Predición do modelo de recomendación de produtos de OOB** e a entidade de saída **OOBProductRecommendationModelPrediction**.

1. Seleccione **Seguinte**.

1. Definir as preferencias do modelo:
   - **Número de produtos** :**5** para definir cantos produtos queres recomendar aos teus clientes.
   - **Se esperan compras repetidas** :**Si** para incluír produtos adquiridos previamente na recomendación.
   - **Mirar cara atrás fiestra:** **365 días** para definir ata onde mirará o modelo antes de recomendar un produto de novo.

   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Preferencias do modelo de recomendación de produtos.":::

1. Seleccione **Seguinte**.

1. No **Engadir historial de compras** paso, seleccione **Engadir datos**.

1. Seleccione **Liña de pedidos de vendas** e a entidade eCommercePurchases e seleccione **A continuación**. Os datos necesarios enchéranse automaticamente desde a actividade. Seleccione **Gardar** e despois **A continuación**.

1. Saltar o **Engade información do produto** e **Filtros de produtos** pasos porque non temos datos de información do produto.

1. No **Actualizacións de datos** paso, seleccione **Mensuais** para o modelo de horario.

1. Seleccione **Seguinte**.

1. Despois de revisar todos os detalles, seleccione **Gardar e executar**.

## <a name="task-5---review-model-results-and-explanations"></a>Tarefa 5: revisar resultados e explicacións do modelo

Deixe que o modelo complete o adestramento e a puntuación dos datos. Revisa o [explicacións do modelo de recomendación de produtos](predict-transactional-churn.md#view-prediction-results).

## <a name="task-6---create-a-segment-of-high-purchased-products"></a>Tarefa 6: crear un segmento de produtos moi comprados

Ao executar o modelo créase unha nova entidade, que aparece na lista **Datos** > **Entidades**. Pode crear un novo segmento baseado na entidade creada polo modelo.

1. Na páxina de resultados, seleccione **Crear segmento**.

1. Crea unha regra usando o **OOBProductRecommendationModelPrediction** entidade e define o segmento:
   - **Campo** : ID de produto
   - **Valor** : selecciona os tres principais ID de produto

1. Seleccione **Gardar** e **Corre** o segmento.

Agora tes un segmento que se actualiza de forma dinámica no que se identifican os clientes que poden estar interesados en adquirir os cinco produtos máis recomendados. Para ver máis información, consulte: [Creación e xestión de segmentos](segments.md).

> [!TIP]
> Tamén podes crear un segmento para un modelo predición a partir de **Segmentos** páxina seleccionando **Novo** e escollendo **Crear dende** > **Intelixencia**. Para obter máis información, consulte [Crea un novo segmento con segmentos rápidos](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
