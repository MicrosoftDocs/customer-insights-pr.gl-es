---
title: Power Automate conector (vista previa) | Microsoft Docs
description: Crear fluxos en Microsoft Power Automate a partir de Dynamics 365 Customer Insights.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f87bd6db7143294a264813f6c5c7d7963f303628
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196116"
---
# <a name="power-automate-connector-preview"></a>Conector de Power Automate (vista previa)

Desencadee eventos específicos para que se produzan automaticamente cando se modifiquen os datos e xestione fluxos máis complexos directamente en [Microsoft Power Automate](https://flow.microsoft.com/).

## <a name="known-limitations"></a>Limitacións coñecidas

- Un máximo de 100 chamadas por 60 segundos. Usa o [$skip parámetro](/connectors/customerinsights/#get-items-from-an-entity) para chamar ao punto final da API varias veces.

## <a name="power-automate-triggers"></a>Desencadeadores de Power Automate

Use desencadeadores para crear fluxos na nube e automatizar tarefas repetitivas, como notificacións ou accións máis avanzadas. Use disparadores cando:

- Falla unha actualización de orixe de datos.
- Unha actualización de orixe de datos ten éxito.
- Crúzase un limiar nun segmento. O desencadeador está limitado a cruzar por enriba do limiar.
- Crúzase un limiar nunha medida empresarial. Só se admiten as medicións de empresa sen ningunha dimensión. O desencadeador está limitado a cruzar por enriba do limiar.
- Completouse unha actualización completa programada. Este activador non funciona para as actualizacións iniciadas manualmente.
- Completouse unha actualización do proceso de unificación.

[Configure os desencadeadores en Power Automate.](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

## <a name="power-automate-actions"></a>Accións de Power Automate

O conector de Power Automate ofrece outras accións que os desencadeadores dispoñibles. Para obter máis información, consulte o [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).

## <a name="create-a-power-automate-flow"></a>Crear un fluxo de Power Automate

1. Vaia a **Administrar** > **Conexións**.

1. No mosaico **Power Automate**, seleccione **Configurar**.

1. Ábrese o conector de Customer Insights (versión preliminar) en Power Automate. **Inicie sesión** en Power Automate.

1. Elixa un dos desencadeadores dispoñibles e engadamáis pasos ao seu novo fluxo. Para obter máis información, consulte [Crear un fluxo de nube en Power Automate](/power-automate/get-started-logic-flow).

Exemplos de como usar os fluxos: 
- Enviar unha mensaxe á canle de Microsoft Teams se falla unha actualización da orixe de datos. 
- Enviar un correo electrónico aos propietarios dos datos cando se cruza un limiar nun segmento.

[!INCLUDE [footer-include](includes/footer-banner.md)]
