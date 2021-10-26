---
title: Executar un exemplo de SDK web
description: Obteña información acerca da personalización e execución dun exemplo de SDK web.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 545f4a7e9660e339dee1070ad727d5d398eb6254
ms.sourcegitcommit: 693458e13e4b4d94b6205093559912f6a4dc4a1c
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 10/06/2021
ms.locfileid: "7606207"
---
# <a name="run-the-web-sdk-sample-for-dynamics-365-customer-insights-engagement-insights-capability"></a>Executar o exemplo de SDK web para a capacidade de información de interacción de Dynamics 365 Customer Insights

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

A biblioteca do SDK web da capacidade de información de interacción é unha biblioteca de JavaScript cun código de exemplo que pode usar no seu sitio web.

## <a name="prerequisites"></a>Requisitos previos

- Instale [Visual Studio Code](https://code.visualstudio.com/).
- [Instale a extensión Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) en Visual Studio Code e familiarícese coa forma de executar Live Server.
- Debe ter un [espazo de traballo de información de compromiso](create-workspace.md).

## <a name="run-sample"></a>Executar o exemplo

1. [Descargue o exemplo de SDK web](https://download.pi.dynamics.com/sdk/EngagementInsightsSamples/ei_websdk_sample.zip).

1. Descomprima o ficheiro comprimido `ei_websdk_sample.zip`.

1. Abra o cartafol descomprimido en Visual Studio Code.

1. Vaia ao portal de información de compromiso do seu espazo de traballo. Seleccione **Administrador** > **Espazo de traballo** e logo **Guía de instalación**. Siga a primeira opción e seleccione **Copiar código** para copiar o fragmento de código de JavaScript.

1. No ficheiro `ei_websdk_sample.html`, pegue o fragmento de código que acaba de copiar nesta liña:

   - <-- PEGUE O FRAGMENTO DE CÓDIGO DE JAVASCRIPT DO PORTAL DE INFORMACIÓN DE COMPROMISO AQUÍ DEBAIXO DESTA LIÑA -->

1. Abra o ficheiro `ei_websdk_sample.html` con Live Server en Visual Studio Code seleccionando **Publicar** na barra de estado.

1. Ao abrir a páxina, debería enviarse automaticamente un evento de visualización. Ao facer clic en calquera dos botóns da páxina enviaranse eventos de acción. O botón **Rastrexar eventos** tamén enviará eventos personalizados. Ao seleccionar o botón **Ir a Bing** enviarase un evento de acción antes de navegar ao sitio web de Bing.

1. Mire os eventos fluír cando navegue á súa área de traballo. Esta área de traballo está asociada á clave de inxestión introducida no paso 4.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
