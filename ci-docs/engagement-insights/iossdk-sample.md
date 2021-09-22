---
title: Executar o exemplo de SDK de iOS
description: Proxecto de mostra para coñecer o SDK de iOS
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 053e626d06d3e17b39b448987410058e45e8ae0385f3ecdef40314cb46ae4bf4
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036826"
---
# <a name="run-the-ios-sdk-sample"></a>Executar o exemplo de SDK de iOS

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Este exemplo de proxecto de iOS axúdalle a comprender como funciona o SDK nunha aplicación. Non ten que escribir código. Só ten que engadir a súa clave de inxestión e verá is eventos no seu espazo de traballo de inmediato.

## <a name="prerequisites"></a>Requisitos previos

- [Xcode versión 9+](https://developer.apple.com/xcode/downloads/)
- [Clave de inxestión](get-started-ios.md)

## <a name="download-the-ios-sdk-sample"></a>Descargar a mostra de SDK de iOS

1. [Descargue a mostra de SDK de iOS de información de interacción](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-ios-sample.zip).
1. Descomprima o ficheiro comprimido `ei-ios-sample.zip`.
1. Abra o proxecto de aplicación de mostra en Xcode.
1. No ficheiro `EIConfig.plist`, substitúa a cadea `“YOUR-INGESTION-KEY”` no campo `ingestionKey` coa clave de inxestión do espazo de traballo da información de intaracción en **Administrar** > **Espazo de traballo** > **Guía de instalación**.
1. Seleccione **Executar** para iniciar o proxecto de exemplo.
1. Consulte os eventos no seu espazo de traballo.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
