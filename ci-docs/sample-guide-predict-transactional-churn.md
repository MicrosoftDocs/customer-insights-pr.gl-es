---
title: Guía de mostra da predición do abandono transaccional
description: Utilice esta guía de mostra para probar o modelo de predición do abandono transaccional listo para usar.
ms.date: 09/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0ccc32b6e5e96adf6f2fa8c6d52960a07d1513f3
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609682"
---
# <a name="transactional-churn-prediction-sample-guide"></a>Guía de mostra da predición do abandono transaccional

Esta guía explicarache un exemplo de extremo a extremo de abandono transaccional predición usando datos de mostra. Recomendámosche que probes este predición [nun novo ambiente](manage-environments.md).

## <a name="scenario"></a>Escenario

Contoso é unha empresa que produce café e máquinas de café de alta calidade. Venden os produtos a través do seu sitio web Contoso Coffee. O seu obxectivo é saber que clientes que adoitan mercar os seus produtos de xeito regular deixarán de ser clientes activos nos próximos 60 días. Sabendo cal dos seus clientes é **susceptible de abandonar**, pode axudalos a aforrar esforzos de marketing centrándose en mantelos.

## <a name="prerequisites"></a>Requisitos previos

- Polo menos [Permisos de colaborador](permissions.md).

## <a name="task-1---ingest-data"></a>Tarefa 1: inxerir datos

Revisa os artigos [sobre a inxestión de datos](data-sources.md) e [conectando a a Power Query orixe de datos](connect-power-query.md). A seguinte información supón que estás familiarizado coa inxestión de datos en xeral.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Inxerir datos de clientes desde a plataforma de comercio electrónico

1. Crea un orixe de datos chamado **comercio electrónico** e selecciona o **Texto/CSV** conector.

1. Insira o URL dos contactos de comercio electrónico https://aka.ms/ciadclasscontacts.

1. Mentres editas os datos, selecciona **Transformar** e despois **Use a primeira fila como cabeceiras**.

1. Actualice o tipo de datos para as columnas listadas a continuación:

   - **DateOfBirth**: data
   - **CreatedOn**: data/hora/fuso

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformar DoB en data.":::

1. No **Nome** no panel da dereita, cambie o nome do seu orixe de datos a **eCommerceContactos**

1. Garde a orixe de datos.

### <a name="ingest-online-purchase-data"></a>Inxerir datos de compra en liña

1. Engada outro conxunto de datos á mesma orixe de datos de **comercio electrónico**. Escolla o conector **Texto/CSV** de novo.

1. Introduza o URL dos datos de compras en liña https://aka.ms/ciadclassonline.

1. Mentres editas os datos, selecciona **Transformar** e despois **Use a primeira fila como cabeceiras**.

1. Actualice o tipo de datos para as columnas listadas a continuación:

   - **PurchasedOn**: data/hora
   - **TotalPrice**: moeda

1. No **Nome** no panel da dereita, cambie o nome do seu orixe de datos a **eCommerceCompras**.

1. Garde a orixe de datos.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Inxerir datos de clientes desde o esquema de fidelización

1. Crea un orixe de datos chamado **Esquema de fidelidade** e selecciona o **Texto/CSV** conector.

1. Insira o URL dos contactos de comercio electrónico https://aka.ms/ciadclasscustomerloyalty.

1. Mentres editas os datos, selecciona **Transformar** e despois **Use a primeira fila como cabeceiras**.

1. Actualice o tipo de datos para as columnas listadas a continuación:

   - **DateOfBirth**: data
   - **RewardsPoints**: número enteiro
   - **CreatedOn**: data/hora

1. No **Nome** no panel da dereita, cambie o nome do seu orixe de datos a **Clientes loy**.

1. Garde a orixe de datos.

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

## <a name="task-4---configure-transaction-churn-prediction"></a>Tarefa 4: configurar a predición de abandono transaccional

Cos perfís de clientes unificados existentes e coa actividade, executa o proceso de transacción predición.

1. Ir a **Intelixencia** > **Predicións**.

1. No **Crear** ficha, seleccione **Usa modelo** no **Modelo de abandono de clientes**.

1. Seleccione **Transaccional** para o tipo de churn e despois **Comezar**.

1. Nomee o modelo **Predición do abandono de transaccións de comercio electrónico de OOB** e a entidade de saída **OOBeCommerceChurnPrediction**.

1. Seleccione **Seguinte**.

1. Definir as preferencias do modelo:

   - **predición xanela** :**60** días para definir ata que punto no futuro queremos prever a rotación de clientes.

   - **Definición de churn** :**60** días para indicar a duración sen compra despois do cal un cliente se considera despedido.

     :::image type="content" source="media/model-levers.PNG" alt-text="Seleccione as preferencias do modelo predición Window and Churn Definition.":::

1. Seleccione **Seguinte**.

1. Seleccione **Historial de compras (obrigatorio)** e seleccione **Engadir datos** para o historial de compras.

1. Seleccione **Liña de pedidos de vendas** e a entidade eCommercePurchases e seleccione **A continuación**. Os datos necesarios enchéranse automaticamente desde a actividade. Seleccione **Gardar** e despois **A continuación**.

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="Unir entidades de comercio electrónico.":::

1. Saltar o **Datos adicionais (opcional)** paso.

1. No **Actualizacións de datos** paso, seleccione **Mensuais** para o modelo de horario.

1. Despois de revisar todos os detalles, seleccione **Gardar e executar**.

## <a name="task-5---review-model-results-and-explanations"></a>Tarefa 5: revisar resultados e explicacións do modelo

Deixe que o modelo complete o adestramento e a puntuación dos datos. Revisa as explicacións do modelo de churn. Para obter máis información, consulte [Ver os resultados de predición](predict-transactional-churn.md#view-prediction-results).

## <a name="task-6---create-a-segment-of-high-churn-risk-customers"></a>Tarefa 6: crear un segmento de clientes con alto risco de abandono

Ao executar o modelo de produción crea unha nova entidade, que aparece na lista **Datos** > **Entidades**. Pode crear un novo segmento baseado na entidade creada polo modelo.

1. Na páxina de resultados, seleccione **Crear segmento**.

1. Crea unha regra usando o **OOBeCommerceChurnPrediction** entidade e define o segmento:
   - **Campo** : ChurnScore
   - **Operador** : máis grande cá
   - **Valor** : 0,6

1. Seleccione **Gardar** e **Corre** o segmento.

Agora tes un segmento que se actualiza de forma dinámica que identifica clientes con alto risco de abandono. Para ver máis información, consulte: [Creación e xestión de segmentos](segments.md).

> [!TIP]
> Tamén podes crear un segmento para un modelo predición a partir de **Segmentos** páxina seleccionando **Novo** e escollendo **Crear dende** > **Intelixencia**. Para obter máis información, consulte [Crea un novo segmento con segmentos rápidos](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
