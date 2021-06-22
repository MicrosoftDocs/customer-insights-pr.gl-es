---
title: Visión xeral dos escenarios de predición compatibles
description: Os escenarios e opcións de predición cubertos pola aplicación de Dynamics 365 Customer Insights.
ms.date: 05/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: get-started
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 69ae945b22819521db217508c6fc232876346747
ms.sourcegitcommit: 6b07c9c3102761be162e4842f3c9fbc19f948a9b
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 05/25/2021
ms.locfileid: "6095707"
---
# <a name="predictions-overview"></a><span data-ttu-id="0281f-103">Visión xeral de predicións</span><span class="sxs-lookup"><span data-stu-id="0281f-103">Predictions overview</span></span>

<span data-ttu-id="0281f-104">Dynamics 365 Customer Insights inclúe unha variedade de opcións que aproveitan a IA e a aprendizaxe automática para predicir datos.</span><span class="sxs-lookup"><span data-stu-id="0281f-104">Dynamics 365 Customer Insights comes with a variety of options that leverage AI and machine learning to predict data.</span></span> 

## <a name="out-of-box-models"></a><span data-ttu-id="0281f-105">Modelos listos para utilizar</span><span class="sxs-lookup"><span data-stu-id="0281f-105">Out-of-box models</span></span>

<span data-ttu-id="0281f-106">O xeito máis sinxelo de comezar coa predición de datos é cos modelos predefinidos, a miúdo denominados modelos listos para usar.</span><span class="sxs-lookup"><span data-stu-id="0281f-106">The easiest way to start with predicting data are predefined models, often referred to as out-of-box models.</span></span> <span data-ttu-id="0281f-107">Só requiren determinados datos e unha determinada estrutura para xerar información rapidamente.</span><span class="sxs-lookup"><span data-stu-id="0281f-107">They only require certain data and structure to generate insights quickly.</span></span> <span data-ttu-id="0281f-108">Actualmente están dispoñibles os seguintes modelos:</span><span class="sxs-lookup"><span data-stu-id="0281f-108">Currently, the following models are available:</span></span> 
- <span data-ttu-id="0281f-109">[Valor de duración do cliente](predict-customer-lifetime-value.md): predí os ingresos potenciais dun cliente ao longo de toda a interacción cunha empresa.</span><span class="sxs-lookup"><span data-stu-id="0281f-109">[Customer lifetime value](predict-customer-lifetime-value.md): Predicts the potential revenue of a customer throughout the entire interaction with a business.</span></span> 
- <span data-ttu-id="0281f-110">[Recomendación de produtos](predict-product-recommendation.md): suxire conxuntos de recomendacións preditivas de produtos baseadas no comportamento de compra e en clientes con padróns de compra similares.</span><span class="sxs-lookup"><span data-stu-id="0281f-110">[Product recommendation](predict-product-recommendation.md): Suggests sets of predictive product recommendations based on purchase behavior and customers with similar purchase patterns.</span></span>
- <span data-ttu-id="0281f-111">[Renovación da subscrición](predict-subscription-churn.md): predí se un cliente está en risco de deixar de usar os servizos ou produtos da subscrición da empresa.</span><span class="sxs-lookup"><span data-stu-id="0281f-111">[Subscription churn](predict-subscription-churn.md): Predicts whether a customer is at risk for no longer using your company’s subscription products or services.</span></span>
- <span data-ttu-id="0281f-112">[Abandono transaccional](predict-transactional-churn.md): predí se un cliente deixará de mercar os seus produtos ou servizos nun determinado intervalo temporal.</span><span class="sxs-lookup"><span data-stu-id="0281f-112">[Transactional churn](predict-transactional-churn.md): Predict if a customer will no longer purchase your products or services in a certain time frame.</span></span>

## <a name="azure-machine-learning-integration"></a><span data-ttu-id="0281f-113">Integración da Aprendizaxe automática de Azure</span><span class="sxs-lookup"><span data-stu-id="0281f-113">Azure Machine Learning integration</span></span>

<span data-ttu-id="0281f-114">Se unha organización xa usa escenarios de aprendizaxe automática baseados en experimentos da Aprendizaxe automática de Azure, a función de modelos personalizados en Customer Insights axuda a conectar os puntos.</span><span class="sxs-lookup"><span data-stu-id="0281f-114">If an organization already uses machine learning scenarios based on Azure Machine Learning experiments, the custom models feature in Customer Insights helps to connect the dots.</span></span> <span data-ttu-id="0281f-115">Cree fluxos de traballo que lle axuden a escoller os datos dos que quere xerar información e asigne os resultados aos perfís de clientes unificados.</span><span class="sxs-lookup"><span data-stu-id="0281f-115">Create workflows that help you choose the data you want to generate insights from and map the results to your unified customer profiles.</span></span> <span data-ttu-id="0281f-116">Para obter máis información, consulte [Modelos de aprendizaxe automática personalizados](custom-models.md).</span><span class="sxs-lookup"><span data-stu-id="0281f-116">For more information, see [Custom machine learning models](custom-models.md).</span></span>

## <a name="ai-builder-prediction"></a><span data-ttu-id="0281f-117">Predición de AI Builder</span><span class="sxs-lookup"><span data-stu-id="0281f-117">AI Builder prediction</span></span>

<span data-ttu-id="0281f-118">Ás veces, os conxuntos de datos están incompletos e faltan algúns valores.</span><span class="sxs-lookup"><span data-stu-id="0281f-118">Sometimes, data sets are incomplete and some values are missing.</span></span> <span data-ttu-id="0281f-119">Customer Insights pode axudar a predicir os valores que faltan para os segmentos e a entidade de cliente.</span><span class="sxs-lookup"><span data-stu-id="0281f-119">Customer Insights can help to predict missing values for the Customer entity and segments.</span></span> <span data-ttu-id="0281f-120">Para obter máis información, consulte [Completar os datos parciais con predicións](predictions.md).</span><span class="sxs-lookup"><span data-stu-id="0281f-120">For more information, see [Complete your partial data with predictions](predictions.md).</span></span>
