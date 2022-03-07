---
title: Comezar a usar o SDK de iOS
description: Aprender a personalizar e executar o SDK de iOS
author: britl
ms.reviewer: mhart
ms.custom: intro-internal
ms.author: britl
ms.date: 09/15/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 68e4d0555d2fc377fae62ff5db64c032fcebcb04
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 02/16/2022
ms.locfileid: "8226213"
---
# <a name="get-started-with-the-ios-sdk"></a>Comezar a usar o SDK de iOS

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Este titorial guíao a través do proceso de instrumentación da aplicación de iOS cun SDK de información de interacción de Dynamics 365 Customer Insights. Comezará a ver eventos no seu portal dentro de cinco minutos ou antes.

## <a name="configuration-options"></a>Opcións de configuración

As seguintes opcións de configuración pódense pasar ao SDK mediante o ficheiro `EIConfig.plist` fornecido:

- **inxestiónClave**: A clave de inxestión empregada para enviar eventos ao seu proxecto.
- **autocollectAction**: Un valor booleano para activar ou desactivar a instrumentación automática do evento de acción.
- **autocollectView**: Un valor booleano para activar ou desactivar a instrumentación automática do evento de visualización.
- **endpointUrl**: URL do extremo cara ao que se dirixirán os eventos.

## <a name="prerequisites"></a>Requisitos previos

- Xcode versión 9+
- iOS versión 8.2+
- Unha clave de inxestión (consulte as instrucións seguintes para obter)

## <a name="integrate-the-sdk-into-your-application"></a>Integrar o SDK na súa aplicación

Comece o proceso seleccionando un espazo de traballo no que traballar, seleccionando a plataforma móbil iOS e descargando o SDK.

- Use o conmutador do espazo de traballo no panel de navegación esquerdo para seleccionar o seu espazo de traballo.

- Se non ten un espazo de traballo existente, seleccione **Novo espazo de traballo** e siga os pasos para crear un [novo espazo de traballo](create-workspace.md).

- Despois de crear un espazo de traballo, vaia a **Administrar** > **Espazo de traballo** e logo seleccione **Guía de instalación**.

## <a name="configure-the-sdk"></a>Configurar o SDK

Unha vez que descargue o SDK, pode traballar con el en Xcode para habilitar e definir eventos. Hai dúas formas de facelo

### <a name="option-1-using-cocoapods-recommended"></a>Opción 1: usar CocoaPods (recomendado)
CocoaPods é un xestor de dependencias para proxectos Swift e Objective-C Cocoa. O seu uso facilita a integración do SDK de información de interacción para iOS. CocoaPods tamén permite actualizar á última versión do SDK de información de interacción. A continuación móstrase como usar CocoaPods para integrar o SDK de información de interacción no seu proxecto Xcode. 

1. Instalar CocoaPods. 

1. Cree un novo ficheiro chamado Podfile no directorio raíz do seu proxecto e engádalle as seguintes instrucións. Substitúa YOUR_TARGET_PROJECT_NAME polo nome do seu proxecto Xcode. 
```objectivec
platform :ios, '9.0'  

 target '${YOUR_TARGET_PROJECT_NAME}' do 

     use_frameworks!   

     pod 'EIObjC.framework.debug' 

     pod 'EIObjC.framework.release' 

 end 
```
A configuración de pod anterior contén as versións de depuración e lanzamento do SDK. Elixa a que mellor se adapte ao seu proxecto.

1. Instale o pod executando o seguinte comando: `pod install --repo-update `

### <a name="option-2-using-download-link"></a>Opción 2: usar unha ligazón de descarga

1. Descargue o [SDK de iOS de información de interacción](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-ios-sdk.zip) e coloque o ficheiro `EIObjC.xcframework` no cartafol `Frameworks`.

1. Se o cartafol `Frameworks` non existe, cree un no cartafol do proxecto.

## <a name="enable-auto-instrumentation"></a>Activar a instrumentación automática
 
Pode activar facilmente a instrumentación automática sen código. Cando o proxecto se execute, fará un seguimento automático dos eventos `view` e `action` usando a clave de inxestión configurada. 

1. Actualice e inclúa o ficheiro fornecido `EIConfig.plist` no cartafol do directorio do proxecto para os seguintes campos:
    - ingestionKey = `"Your-Ingestion-Key"`
    - autocollectView = SI
    - autocollectAction = SI

2. A continuación, engada o ficheiro `EIConfig.plist` ao seu proxecto en Xcode. 



Para desactivar a instrumentación automática, actualice os campos seguintes no ficheiro `EIConfig.plist` incluído no cartafol do directorio do proxecto: 

```objectivec
'autocollectView' = NO (to disable)
'autocollectAction' = NO (to disable)
```


## <a name="implement-custom-events"></a>Implementar eventos personalizados

1. Abra o seu proxecto en Xcode e navegue á configuración **Xeral**. 
1. Engada o `EIObjC.xcframework` ao proxecto na sección "Marcos, bibliotecas e contido incrustado".

1. Importe o ficheiro da cabeceira do marco en AppDelegate.m co fragmento de código seguinte:

    ```objectivec
    #import <EIObjC/EIObjC.h>
    ```

1. Inicie o SDK da información de interacción desde a aplicación: didFinishLaunchingWithOptions.
1. Copie o fragmento de XML da **Guía de instalación**.

    ```objectivec
    NSError *error = [NSError new];
    id<EIIAnalytics> analytics = [EIAnalyticsProvider analyticsForIngestionKey:nil error:&error];
    ```

1. Rastrexar un evento:

    ```objectivec
    EIEvent *event = [EIEvent new];
    event.name = @"video.log";
    [event setLongValue:320 forKey:@"duration"];
    [event setBoolValue:YES forKey:@"ad_shown"];
    [analytics trackEvent:event];
    ```

## <a name="set-user-details-for-your-event"></a>Definir os detalles do usuario para o seu evento

O SDK permítelle definir a información do usuario que se pode enviar con cada evento. Pode especificar a información do usuario chamando a API `setUser:(nonnull EIUser *)user` no SDK.

Especificar os detalles do usuario no nivel `Analytics` significa que todas as telemetrías terán esta información. Non obstante, se especifica no nivel do evento chamando a API `setUser:(nonnull EIUser *)user` no obxecto EIEvent, só ese evento específico conterá a información.

A clase de datos `EIUser` contén as seguintes propiedades NSString:

- **localId** : o ID local do usuario.
- **authId** : o ID do usuario autenticado.
- **authType** : o tipo de autenticación usado para obter o ID do usuario autenticado.
- **name**: o nome do usuario.
- **email**: o enderezo de correo electrónico do usuario.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
