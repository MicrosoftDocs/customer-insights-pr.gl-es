---
title: Segmentos baseados nos resultados da predición
description: Cree segmentos baseados na entidade de saída dun modelo predición.
ms.date: 03/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 488db1af865ce600ec012716327d053bee33aff8
ms.sourcegitcommit: a95c82f46c23f625cb34fceba021ccc70d4b1df6
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 03/30/2021
ms.locfileid: "5741427"
---
# <a name="create-a-segment-based-on-a-prediction-model-preview"></a><span data-ttu-id="72beb-103">Crear un segmento baseado nun modelo predición (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="72beb-103">Create a segment based on a prediction model (preview)</span></span>

<span data-ttu-id="72beb-104">Os resultados das predicións ás veces só se aplican a un subconxunto dos seus clientes.</span><span class="sxs-lookup"><span data-stu-id="72beb-104">The results of predictions sometimes only apply to a subset of your customers.</span></span> <span data-ttu-id="72beb-105">Aumente a personalización das recomendacións creando segmentos a partir dos resultados dos modelos de predición.</span><span class="sxs-lookup"><span data-stu-id="72beb-105">Increase the personalization of recommendations by creating segments from results of prediction models.</span></span> <span data-ttu-id="72beb-106">Por exemplo, pode que queira dar recomendacións específicas aos clientes que prefiran un determinado tipo de servizo.</span><span class="sxs-lookup"><span data-stu-id="72beb-106">For example, you may want to give specific recommendations to customers that prefer a certain type of service.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="72beb-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="72beb-107">Prerequisites</span></span>

- <span data-ttu-id="72beb-108">Polo menos [Permisos de colaborador](permissions.md) en Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="72beb-108">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>

- <span data-ttu-id="72beb-109">Un modelo de recomendación de produtos, abandono transaccional, abandono da subscrición ou valor de duración do cliente configurado en Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="72beb-109">A product recommendation, transactional churn, subscription churn, or customer lifetime value model configured in Customer Insights.</span></span> <span data-ttu-id="72beb-110">Revise os requisitos para configurar os diferentes modelos:</span><span class="sxs-lookup"><span data-stu-id="72beb-110">Review the requirements to set up the different models:</span></span>

  - [<span data-ttu-id="72beb-111">Modelo de recomendación do produto</span><span class="sxs-lookup"><span data-stu-id="72beb-111">Product recommendation model</span></span>](predict-product-recommendation.md)
  - [<span data-ttu-id="72beb-112">Modelo de abandono da subscrición</span><span class="sxs-lookup"><span data-stu-id="72beb-112">Subscription churn model</span></span>](predict-subscription-churn.md)
  - [<span data-ttu-id="72beb-113">Modelo de abandono transaccional</span><span class="sxs-lookup"><span data-stu-id="72beb-113">Transactional churn model</span></span>](predict-transactional-churn.md)
  - [<span data-ttu-id="72beb-114">Modelo de valor de duración do cliente</span><span class="sxs-lookup"><span data-stu-id="72beb-114">Customer lifetime value model</span></span>](predict-customer-lifetime-value.md)

## <a name="create-a-customer-segment-based-on-predictions"></a><span data-ttu-id="72beb-115">Crear un segmento de clientes baseado nas predicións</span><span class="sxs-lookup"><span data-stu-id="72beb-115">Create a customer segment based on predictions</span></span>

1. <span data-ttu-id="72beb-116">Vaia a **Intelixencia** > **Predicións** e seleccione o separador **As miñas predicións**.</span><span class="sxs-lookup"><span data-stu-id="72beb-116">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="72beb-117">Seleccione os tres puntos verticais xunto ao modelo que desexa revisar e seleccione **Ver**.</span><span class="sxs-lookup"><span data-stu-id="72beb-117">Select the vertical ellipses next to the model you want to review and select **View**.</span></span>

1. <span data-ttu-id="72beb-118">Na páxina de resultados, seleccione **Crear segmento**.</span><span class="sxs-lookup"><span data-stu-id="72beb-118">On the results page, select **Create segment**.</span></span> <span data-ttu-id="72beb-119">Para obter máis información sobre a páxina de resultados, revise o artigo sobre o modelo.</span><span class="sxs-lookup"><span data-stu-id="72beb-119">For more information about the results page, review the article about the model.</span></span>

   :::image type="content" source="media/prediction-create-segment.png" alt-text="Captura de pantalla da páxina de resultados da predición con énfase na acción Crear segmento.":::

1. <span data-ttu-id="72beb-121">Cree un novo segmento baseado na entidade de saída do modelo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="72beb-121">Create a new segment based on the output entity of the selected model.</span></span> <span data-ttu-id="72beb-122">Para ver máis información, consulte: [Creación e xestión de segmentos](segments.md).</span><span class="sxs-lookup"><span data-stu-id="72beb-122">For more information, see [Create and manage segments](segments.md).</span></span>