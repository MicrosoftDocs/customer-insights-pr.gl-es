---
title: Límites do servizo en Customer Insights
description: Comprenda os límites e restricións do servizo SaaS de Customer Insights.
ms.date: 08/30/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 7f38b7d9985368fc38107f1f360f0603a7fcc8e6
ms.sourcegitcommit: 3c7cdfc8bd83ca236e4777240e08a541dc955d34
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 09/07/2022
ms.locfileid: "9411738"
---
# <a name="service-limits-in-customer-insights"></a>Límites do servizo en Customer Insights

 Customer Insights ten límites incorporados deseñados para garantir a fiabilidade e estabilidade do servizo. Calquera solicitude de cambios pódese facer a través do [Foro de ideas](https://go.microsoft.com/fwlink/?linkid=2074172).

## <a name="customer-insights"></a>Customer Insights

| De áreas  | Límites  | Notas |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmentos, medidas e predicións | 300  | O número total de [segmentos](segments.md),[medidas](measures.md), e [predicións](predictions-overview.md) combinados non poden superar os 300.  |
| Relacións | 20 niveis de profundidade nas relacións nos camiños da entidade. | Ao crear [segmentos](segments.md) ou [medidas](measures.md) usando a interface do creador, os camiños de entidades poden ter ata 20 saltos de relación entre a entidade de inicio e a entidade de destino.  |

## <a name="fair-scheduling-of-jobs"></a>Programación xusta de postos de traballo

Customer Insights é un servizo SaaS que usa recursos compartidos de Azure. Os clientes adoitan ter cargas de traballo de intensidade variable e en horarios diferentes. Para garantir o acceso xusto aos recursos subxacentes, asegurámonos de que os procesos do sistema se executen en orde xusta. Exemplos de procesos do sistema son traballos relacionados coa unificación de datos, actualizacións de segmentos ou cálculo de medidas. A programación xusta protéxeche de facer cola para obter recursos se hai un aumento dos traballos solicitados. Ao mesmo tempo, Customer Insights non garante que todos os traballos que fas se procesen en paralelo.

[!INCLUDE [footer-include](includes/footer-banner.md)]
