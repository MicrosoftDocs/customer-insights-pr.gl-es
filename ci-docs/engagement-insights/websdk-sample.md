---
title: Executar un exemplo de SDK web
description: Obteña información acerca da personalización e execución dun exemplo de SDK web.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 10/30/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 97e50a51231bcf05f3e381397f0cf41e49afc10e3c3674d7c709c8f521979e12
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036601"
---
# <a name="run-the-web-sdk-sample-for-dynamics-365-customer-insights-engagement-insights-capability"></a>Executar o exemplo de SDK web para a capacidade de información de interacción de Dynamics 365 Customer Insights

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

A biblioteca do SDK web da capacidade de información de interacción é unha biblioteca de JavaScript cun código de exemplo que pode usar no seu sitio web.

## <a name="prerequisites"></a>Requisitos previos

- Instale [Visual Studio Code](https://code.visualstudio.com/).
- [Instale a extensión Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) en Visual Studio Code e familiarícese coa forma de executar Live Server.
- Debe ter a [clave de inxestión](instrument-website.md).

## <a name="run-sample"></a>Executar o exemplo

1. [Descargue o exemplo de SDK web](https://download.pi.dynamics.com/sdk/EngagementInsightsSamples/ei_websdk_sample.zip).

1. Descomprima o ficheiro comprimido `ei_websdk_sample.zip`.

1. Abra o cartafol descomprimido en Visual Studio Code.

1. No ficheiro `ei_websdk_sample.html`, substitúa a cadea "INGESTION_KEY" pola súa clave de inxestión do portal da capacidade de información de interacción e a cadea "NAME", co nome global co que quere que se cree unha instancia para o SDK. Asegúrese de substituír todas as ocorrencias.

1. Abra o ficheiro `ei_websdk_sample.html` con Live Server en Visual Studio Code seleccionando **Publicar** na barra de estado.

1. Ao abrir a páxina, debería enviarse automaticamente un evento de visualización. Ao facer clic en calquera dos botóns da páxina enviaranse eventos de acción. O botón **Rastrexar eventos** tamén enviará eventos personalizados. Ao seleccionar o botón **Ir a Bing** enviarase un evento de acción antes de navegar ao sitio web de Bing.

1. Mire os eventos fluír cando navegue á súa área de traballo. Esta área de traballo está asociada á clave de inxestión introducida no paso 4.


[!INCLUDE[footer-include](../includes/footer-banner.md)]