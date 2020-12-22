---
title: Conector de Power Automate | Microsoft Docs
description: Cree fluxos en Microsoft Power Automate dende Dynamics 365 Customer Insights.
ms.date: 08/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: ffe92414365b0b777691a4a2d585100e4fbea591
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405693"
---
# <a name="power-automate-connector-preview"></a>Conector de Power Automate (vista previa)

Desencadee eventos específicos para que se produzan automaticamente cando se modifiquen os datos e xestione fluxos máis complexos directamente en [Power Automate](https://flow.microsoft.com/).

## <a name="power-automate-triggers"></a>Desencadeadores de Power Automate

Pode usar unha variedade de desencadeadores que lle permiten crear fluxos para automatizar tarefas repetitivas, como notificacións ou accións máis avanzadas. 

- Desencadeador cando falla unha actualización dunha orixe de datos. 
- Desencadeador cando se fai unha actualización dunha orixe de datos correctamente.
- Desencadear cando se cruza un limiar nun segmento. O desencadeador está limitado a cruzar por enriba do limiar.
- Desencadear cando se cruza un limiar nunha medición de empresa. O desencadeador está limitado a cruzar por enriba do limiar.
- Activar cando se complete unha actualización completa de (fontes de datos, segmentos, medidas...).
- Activar cando se completa unha actualización do proceso de unificación (mapa, coincidencia, combinación).

[Configure os desencadeadores en Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).

## <a name="power-automate-actions"></a>Accións de Power Automate
O conector de Power Automate ofrece outras accións que os desencadeadores dispoñibles. Para obter máis información, consulte o [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).

## <a name="create-a-power-automate-flow-in-audience-insights"></a>Crear un fluxo de Power Automate na información do público

1. Na información do público, vaia a **Administrar** > **Sistema**.

1. Na páxina **Sistema**, seleccione o separador **Estado**.

1. Na sección **Orixes de datos**, seleccione **Fluxos** e **Crear un fluxo** na lista despregable.
   > [!div class="mx-imgBorder"]
   > ![Conector de Power Automate que mostra a acción Crear un fluxo](media/power-automate-connector-create-flow.png "Conector de Power Automate que mostra a acción Crear un fluxo")

1. En Power Automate, seleccione un dos desencadeadores para crear o fluxo preferido. Se está a crear o primeiro fluxo, ten que autenticarse co conector de Power Automate primeiro.
