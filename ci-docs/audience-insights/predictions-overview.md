---
title: Visión xeral dos escenarios de predición compatibles
description: Os escenarios e opcións de predición cubertos pola aplicación de Dynamics 365 Customer Insights.
ms.date: 09/06/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: get-started
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: be452e4f1515f637f6edbc3ae3aaf6a3d3471489
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 10/08/2021
ms.locfileid: "7618841"
---
# <a name="predictions-overview"></a>Visión xeral de predicións

Dynamics 365 Customer Insights inclúe unha variedade de opcións que aproveitan a IA e a aprendizaxe automática para predicir datos. 

## <a name="out-of-box-models"></a>Modelos listos para utilizar

O xeito máis sinxelo de comezar coa predición de datos é cos modelos predefinidos, a miúdo denominados modelos listos para usar. Só requiren determinados datos e unha determinada estrutura para xerar información rapidamente. Actualmente están dispoñibles os seguintes modelos: 

# <a name="individual-customers-b2c"></a>[Consumidores individuais (B2C)](#tab/b2c)

- [Valor de duración do cliente](predict-customer-lifetime-value.md): predí os ingresos potenciais dun cliente ao longo de toda a interacción cunha empresa.
- [Recomendación de produtos](predict-product-recommendation.md): suxire conxuntos de recomendacións preditivas de produtos baseadas no comportamento de compra e en clientes con padróns de compra similares.
- [Renovación da subscrición](predict-subscription-churn.md): predí se un cliente está en risco de deixar de usar os servizos ou produtos da subscrición da empresa.
- [Abandono transaccional](predict-transactional-churn.md): predí se un cliente deixará de mercar os seus produtos ou servizos nun determinado intervalo temporal.

# <a name="business-accounts-b2b"></a>[Contas empresariais (B2B)](#tab/b2b)

- [Abandono transaccional](predict-transactional-churn.md): predí se un cliente deixará de mercar os seus produtos ou servizos nun determinado intervalo temporal.

---


## <a name="azure-machine-learning-integration"></a>Integración da Aprendizaxe automática de Azure

Se unha organización xa usa escenarios de aprendizaxe automática baseados en experimentos da Aprendizaxe automática de Azure, a función de modelos personalizados en Customer Insights axuda a conectar os puntos. Cree fluxos de traballo que lle axuden a escoller os datos dos que quere xerar información e asigne os resultados aos perfís de clientes unificados. Para obter máis información, consulte [Modelos de aprendizaxe automática personalizados](custom-models.md).

## <a name="ai-builder-prediction"></a>Predición de AI Builder

Ás veces, os conxuntos de datos están incompletos e faltan algúns valores. Customer Insights pode axudar a predicir os valores que faltan para os segmentos e a entidade de cliente. Para obter máis información, consulte [Completar os datos parciais con predicións](predictions.md).
