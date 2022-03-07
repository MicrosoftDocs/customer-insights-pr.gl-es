---
title: Límites do servizo en Dynamics 365 Customer Insights
description: Comprender os límites e restricións.
ms.date: 09/03/2021
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 9bf8f03b785fb3035e3fc979a3304d4e98fd8d28
ms.sourcegitcommit: 1946d7af0bd2ca216885bec3c5c95009996d9a28
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 02/25/2022
ms.locfileid: "8350405"
---
# <a name="service-limits-in-customer-insights-capabilities"></a>Límites de servizo en capacidades de Customer Insights

Este artigo describe os límites internos para o servizo de Customer Insights, que están deseñados para garantir a fiabilidade e estabilidade do servizo. Calquera solicitude de cambios pódese facer a través do [Foro de ideas](https://go.microsoft.com/fwlink/?linkid=2074172). 

## <a name="audience-insights"></a>Información do público

| De áreas  | Límites  | Notas |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmentos, medidas e predicións | 300  | O número total de [segmentos](audience-insights/segments.md),[medidas](audience-insights/measures.md), e [predicións](audience-insights/predictions.md) combinados non poden superar os 300.  |
| Relacións | 20 niveis de profundidade nas relacións nos camiños da entidade. | Ao crear [segmentos](audience-insights/segments.md) ou [medidas](audience-insights/measures.md) usando a interface do creador, os camiños de entidades poden ter ata 20 saltos de relación entre a entidade de inicio e a entidade de destino.  |

<!--
## Engagement insights

### Workspace and event quotas

Engagement insights is a highly scalable application that can support millions of events per second. During public preview, events have a volume threshold. There's also a limit to the number of workspaces in an organization.

### Engagement insights limits

- Maximum event volume per workspace  = 100 events per second

- Maximum number of workspaces per organization = 100

When events exceed the threshold, it can lead to loss of data in reports based on those events. You can [contact support](https://go.microsoft.com/fwlink/?linkid=2145734) to request a volume increase before you exceed limits. We'll work with you to determine your need for a volume increase and support your request.
-->

[!INCLUDE[footer-include](includes/footer-banner.md)]
