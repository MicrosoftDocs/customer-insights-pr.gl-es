---
title: Visión xeral de predicións
description: Os escenarios e opcións de predición cubertos pola aplicación de Dynamics 365 Customer Insights.
ms.date: 03/24/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: overview
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: a87af80fa713a1ac70493345c0c920e416692b0f
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "9083098"
---
# <a name="predictions-overview"></a>Visión xeral de predicións

Dynamics 365 Customer Insights inclúe unha variedade de opcións que aproveitan a IA e a aprendizaxe automática para predicir datos. 

## <a name="out-of-box-models"></a>Modelos listos para utilizar

O xeito máis sinxelo de comezar coa predición de datos é cos modelos predefinidos, a miúdo denominados modelos listos para usar. Só requiren determinados datos e unha determinada estrutura para xerar información rapidamente. Actualmente están dispoñibles os seguintes modelos: 

# <a name="individual-consumers-b-to-c"></a>[Consumidores individuais (B2C)](#tab/b2c)

- [Valor de duración do cliente](predict-customer-lifetime-value.md): predí os ingresos potenciais dun cliente ao longo de toda a interacción cunha empresa.
- [Recomendación de produtos](predict-product-recommendation.md): suxire conxuntos de recomendacións preditivas de produtos baseadas no comportamento de compra e en clientes con padróns de compra similares.
- [Renovación da subscrición](predict-subscription-churn.md): predí se un cliente está en risco de deixar de usar os servizos ou produtos da subscrición da empresa.
- [Abandono transaccional](predict-transactional-churn.md): predí se un cliente deixará de mercar os seus produtos ou servizos nun determinado intervalo temporal.
- [Análise de sentimentos](sentiment-analysis.md) : Analiza o sentimento dos comentarios dos clientes e identifica os aspectos comerciais que se mencionan con frecuencia.

# <a name="business-accounts-b-to-b"></a>[Contas empresariais (B2B)](#tab/b2b)

- [Abandono transaccional](predict-transactional-churn.md): predí se un cliente deixará de mercar os seus produtos ou servizos nun determinado intervalo temporal.

---

> [!TIP]
> Recomendamos que actualices regularmente os modelos prefabricados con datos actualizados para asegurarte de que informen con precisión o caso de uso empresarial. Os datos actualízanse ad hoc cando o sistema inxire fontes de datos novas ou actualizadas. Non obstante, os modelos só repuntarán neste caso e seguirán utilizando os datos de adestramento existentes.
> 
> Podes configurar un **Actualizar horario** configurando o programa de reciclaxe do modelo na experiencia de configuración. O modelo volverá adestrar e recalificarase nesta programación, que podes cambiar en calquera momento.


## <a name="azure-machine-learning-integration"></a>Integración da Aprendizaxe automática de Azure

Se unha organización xa usa escenarios de aprendizaxe automática baseados en experimentos da Aprendizaxe automática de Azure, a función de modelos personalizados en Customer Insights axuda a conectar os puntos. Cree fluxos de traballo que lle axuden a escoller os datos dos que quere xerar información e asigne os resultados aos perfís de clientes unificados. Para obter máis información, consulte [Modelos de aprendizaxe automática personalizados](custom-models.md).

## <a name="ai-builder-prediction"></a>AI Builder predición

Ás veces, os conxuntos de datos están incompletos e faltan algúns valores. Customer Insights pode axudar a predicir os valores que faltan para os segmentos e a entidade de cliente. Para obter máis información, consulte [Completar os datos parciais con predicións](predictions.md).
