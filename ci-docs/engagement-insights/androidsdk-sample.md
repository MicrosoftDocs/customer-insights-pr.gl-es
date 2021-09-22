---
title: Exemplo de SDK de Android
description: Proxecto de mostra para coñecer o SDK de Android
author: britl
ms.reviewer: m-hartmann
ms.author: britl
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: ba51961bc7f9555d7dba5b6a21c8636011438d75cba87bc132b896841c467a33
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035824"
---
# <a name="run-the-android-sdk-sample"></a>Executar o exemplo de SDK de Android

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Este exemplo de proxecto de Android axúdalle a comprender como funciona o SDK nunha aplicación. Non ten que escribir código. Só ten que engadir a súa clave de inxestión e verá is eventos no seu espazo de traballo de inmediato.

## <a name="prerequisites"></a>Requisitos previos

- [Android Studio](https://developer.android.com/studio)
- [Clave de inxestión](get-started-android.md)

## <a name="download-the-android-sdk-sample"></a>Descargar a mostra de SDK de Android

1. [Descargue a mostra de SDK de Android de información de interacción](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-android-sample.zip).
1. Descomprima o ficheiro comprimido `ei-android-sample.zip`.
1. Abra o cartafol descomprimido en Android Studio.
1. No ficheiro `AndroidManifest.xml`, substitúa a cadea `"Your-Ingestion-Key"` coa clave de inxestión do espazo de traballo da información de intaracción en **Administrar** > **Espazo de traballo** > **Guía de instalación**. 

   > [!NOTE]
   > Non precisa substituír a sección `${applicationId}`. Cúbrese automaticamente.

   ```xml
   <application>
   ...
       <provider
           android:authorities="${applicationId}.com.microsoft.engagementinsights.eiandroidsdk.AnalyticsContentProvider"
           android:name="microsoft.dynamics.engagementinsights.eiandroidsdk.AnalyticsContentProvider" />
       <meta-data
           android:name="com.microsoft.engagementinsights.ingestionKey"
           android:value="Your-Ingestion-Key" />
       <meta-data
           android:name="com.microsoft.engagementinsights.autoCapture"
           android:value="true" />
   ...
   </application>
   ```

1. Seleccione **Executar** para iniciar o proxecto de exemplo.
1. Consulte os eventos no seu espazo de traballo.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
