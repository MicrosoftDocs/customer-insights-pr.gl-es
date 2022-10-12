---
title: Crea un segmento baseado nun modelo predición
description: Cree segmentos baseados na entidade de saída dun modelo predición.
ms.date: 09/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: ed9c6247a1f9148628dc9b5217484e98a576224e
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610418"
---
# <a name="create-a-segment-based-on-a-prediction-model-preview"></a>Crear un segmento baseado nun modelo predición (versión preliminar)

Os resultados das predicións ás veces só se aplican a un subconxunto dos seus clientes. Aumente a personalización das recomendacións creando segmentos a partir dos resultados dos modelos de predición. Por exemplo, pode que queira dar recomendacións específicas aos clientes que prefiran un determinado tipo de servizo.

## <a name="prerequisites"></a>Requisitos previos

- Polo menos [Permisos de colaborador](permissions.md) en Customer Insights.

- Un modelo de recomendación de produtos, abandono transaccional, abandono da subscrición ou valor de duración do cliente configurado en Customer Insights. Revise os requisitos para configurar os diferentes modelos:

  - [Modelo de recomendación do produto](predict-product-recommendation.md)
  - [Modelo de abandono da subscrición](predict-subscription-churn.md)
  - [Modelo de abandono transaccional](predict-transactional-churn.md)
  - [Modelo de valor de duración do cliente](predict-customer-lifetime-value.md)

## <a name="create-a-customer-segment-based-on-predictions"></a>Crear un segmento de clientes baseado nas predicións

1. Vaia a **Intelixencia** > **Predicións** e seleccione o separador **As miñas predicións**.

1. Selecciona o modelo que queres revisar e selecciona **Ver**.

1. Na páxina de resultados, seleccione **Crear segmento**. Para obter máis información sobre a páxina de resultados, revise o artigo sobre o modelo.

   :::image type="content" source="media/prediction-create-segment.png" alt-text="Captura de pantalla da páxina de resultados da predición con énfase na acción Crear segmento.":::

1. Crea un novo segmento utilizando atributos da entidade de saída do modelo seleccionado. Para ver máis información, consulte: [Creación e xestión de segmentos](segments.md).

> [!TIP]
> Tamén podes crear un segmento para un modelo predición a partir de **Segmentos** páxina seleccionando **Novo** e escollendo **Crear dende** > **Intelixencia**. Para obter máis información, consulte [Crea un novo segmento con segmentos rápidos](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
