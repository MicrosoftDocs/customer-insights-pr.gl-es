---
title: Límites do servizo en Dynamics 365 Customer Insights
description: Comprender os límites e restricións.
ms.date: 09/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: eba7871faf304d5945191b5b9bc215243b4f8a05
ms.sourcegitcommit: 5704002484cdf85ebbcf4e7e4fd12470fd8e259f
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 09/08/2021
ms.locfileid: "7483665"
---
# <a name="service-limits-in-customer-insights-capabilities"></a>Límites de servizo en capacidades de Customer Insights

Este artigo describe os límites internos para o servizo de Customer Insights, que están deseñados para garantir a fiabilidade e estabilidade do servizo. Calquera solicitude de cambios pódese facer a través do [Foro de ideas](https://go.microsoft.com/fwlink/?linkid=2074172). 

## <a name="audience-insights"></a>Información do público

### <a name="service-limits-in-dynamics-365-customer-insights-audience-insights-capability"></a>Límites de servizo na capacidade de información do público de Dynamics 365 Customer Insights

| De áreas  | Límites  | Notas |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmentos e medidas | 100 segmentos ou medidas. | O número total de [segmentos](audience-insights/segments.md) e [medidas](audience-insights/measures.md) activos combinados non poden superar os 100.  |
| Relacións | 20 niveis de profundidade nas relacións nos camiños da entidade. | Ao crear [segmentos](audience-insights/segments.md) ou [medidas](audience-insights/measures.md) usando a interface do creador, os camiños de entidades poden ter ata 20 saltos de relación entre a entidade de inicio e a entidade de destino.  |


## <a name="engagement-insights"></a>Información de interacción

### <a name="workspace-and-event-quotas"></a>Cotas de espazo de traballo e eventos

A información de interacción é unha aplicación altamente dimensionable que pode admitir millóns de eventos por segundo. Durante a versión preliminar pública, os eventos teñen un limiar de volume. Tamén hai un límite no número de áreas de traballo nunha organización.

### <a name="engagement-insights-limits"></a>Límites da información de interacción

- Volume máximo de eventos por área de traballo = 100 eventos por segundo

- Número máximo de áreas de traballo por organización = 100

Cando os eventos superan o limiar, pode provocar a perda de datos nos informes que se baseen neses eventos. Pode [poñerse en contacto coa asistencia técnica](https://go.microsoft.com/fwlink/?linkid=2145734) para solicitar un aumento de volume antes de superar os límites. Traballaremos con vostede para determinar a necesidade de aumentar o volume e apoiar a súa solicitude.


[!INCLUDE[footer-include](includes/footer-banner.md)]