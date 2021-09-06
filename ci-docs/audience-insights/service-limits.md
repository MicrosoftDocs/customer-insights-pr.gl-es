---
title: Límites de servizo
description: Comprender os límites e restricións.
ms.date: 07/08/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 2966f2ede1ddbe0245471771365cbf5b593be608764aa10ed28d962c52bb8067
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034862"
---
# <a name="service-limits-in-dynamics-365-customer-insights-audience-insights-capability"></a>Límites de servizo na capacidade de información do público de Dynamics 365 Customer Insights

Este artigo describe os límites internos para o servizo de Customer Insights, que están deseñados para garantir a fiabilidade e estabilidade do servizo. Calquera solicitude de cambios pódese facer a través do [Foro de ideas](https://go.microsoft.com/fwlink/?linkid=2074172). 
 
| De áreas  | Límites  | Notas |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmentos e medidas | 100 segmentos ou medidas. | O número total de [segmentos](segments.md) e [medidas](measures.md) activos combinados non poden superar os 100.  |
| Relacións | 20 niveis de profundidade nas relacións nos camiños da entidade. | Ao crear [segmentos](segments.md) ou [medidas](measures.md) usando a interface do creador, os camiños de entidades poden ter ata 20 saltos de relación entre a entidade de inicio e a entidade de destino.  |


[!INCLUDE[footer-include](../includes/footer-banner.md)]