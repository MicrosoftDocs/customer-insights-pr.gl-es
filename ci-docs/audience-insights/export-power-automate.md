---
title: Conector de Power Automate | Microsoft Docs
description: Crear fluxos en Microsoft Power Automate a partir de Dynamics 365 Customer Insights.
ms.date: 06/24/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: dc9bbe22b7f10cf92f06cae18fbece9808b87dce
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 02/16/2022
ms.locfileid: "8226712"
---
# <a name="power-automate-connector-preview"></a>Conector de Power Automate (vista previa)

Desencadee eventos específicos para que se produzan automaticamente cando se modifiquen os datos e xestione fluxos máis complexos directamente en [Power Automate](https://flow.microsoft.com/).

## <a name="power-automate-triggers"></a>Desencadeadores de Power Automate

Use desencadeadores para crear fluxos na nube e automatizar tarefas repetitivas, como notificacións ou accións máis avanzadas. 

- Desencadeador cando falla unha actualización dunha orixe de datos. 
- Desencadeador cando se fai unha actualización dunha orixe de datos correctamente.
- Desencadear cando se cruza un limiar nun segmento. O desencadeador está limitado a cruzar por enriba do limiar.
- Desencadear cando se cruza un limiar nunha medición de empresa. Só se admiten as medicións de empresa sen ningunha dimensión. O desencadeador está limitado a cruzar por enriba do limiar.
- Activar cando se complete unha actualización completa de (fontes de datos, segmentos, medidas...).
- Activar cando se completa unha actualización do proceso de unificación (mapa, coincidencia, combinación).

[Configure os desencadeadores en Power Automate.](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

## <a name="power-automate-actions"></a>Accións de Power Automate

O conector de Power Automate ofrece outras accións que os desencadeadores dispoñibles. Para obter máis información, consulte o [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).

## <a name="create-a-power-automate-flow"></a>Crear un fluxo de Power Automate

1. Na información do público, vaia a **Administrar** > **Destinos de exportación**.

1. No mosaico **Power Automate**, seleccione **Configurar**.

1. Ábrese o conector de Customer Insights (versión preliminar) en Power Automate. **Inicie sesión** en Power Automate.

1. Elixa un dos desencadeadores dispoñibles e engadamáis pasos ao seu novo fluxo. Para obter máis información, consulte [Crear un fluxo de nube en Power Automate](/power-automate/get-started-logic-flow).

Exemplos de como usar os fluxos: 
- Enviar unha mensaxe á canle de Microsoft Teams se falla unha actualización da orixe de datos. 
- Enviar un correo electrónico aos propietarios dos datos cando se cruza un limiar nun segmento.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
