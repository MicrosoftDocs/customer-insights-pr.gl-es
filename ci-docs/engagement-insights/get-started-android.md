---
title: Comezar a usar o SDK de Android
description: Aprender a personalizar e executar o SDK de Android
author: britl
ms.reviewer: mhart
ms.custom: intro-internal
ms.author: britl
ms.date: 10/19/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 71ec4841303bd17d3f605547be8d6032c58a7b21
ms.sourcegitcommit: bb1ca84bc38e81fb2ff2961c457384b7beb5b5fa
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 01/15/2022
ms.locfileid: "7977511"
---
# <a name="get-started-with-the-android-sdk"></a>Comezar a usar o SDK de Android

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Este titorial guíao a través do proceso de instrumentación da aplicación de Android cun SDK de información de interacción de Dynamics 365 Customer Insights. Comezará a ver eventos no seu portal dentro de cinco minutos ou antes.

## <a name="configuration-options"></a>Opcións de configuración
As seguintes opcións de configuración pódense pasar ao SDK:

- **inxestiónClave**: A clave de inxestión é empregada para enviar eventos ao seu espazo de traballo.

## <a name="prerequisites"></a>Requisitos previos

- Android Studio

- Nivel da API de Android mínimo: 16 (Jelly Bean)

- Unha clave de inxestión (consulte as instrucións seguintes sobre como obtela)

## <a name="integrate-the-sdk-into-your-application"></a>Integrar o SDK na súa aplicación
Comece o proceso seleccionando un espazo de traballo, seleccionando a plataforma móbil Android e descargando o SDK de Android.

- Use o conmutador do espazo de traballo no panel de navegación esquerdo para seleccionar o seu espazo de traballo.

- Se non ten un espazo de traballo existente, seleccione **Novo espazo de traballo** e siga os pasos para crear un [novo espazo de traballo](create-workspace.md).

- Despois de crear un espazo de traballo, vaia a **Administrar** > **Espazo de traballo** e logo seleccione **Guía de instalación**.

## <a name="configure-the-sdk"></a>Configurar o SDK

Unha vez que descargue o SDK, pode traballar con el en Android Studio para habilitar e definir eventos. Hai dúas formas de facelo:
### <a name="option-1-use-jitpack-recommended"></a>Opción 1: use JitPack (recomendado)
1. Engada o repositorio JitPack á súa raíz `build.gradle`:
    ```gradle
    allprojects {
        repositories {
            ...
            maven { url 'https://jitpack.io' }
        }
    }
    ```

1. Engada a dependencia:
    ```gradle
    dependencies {
        implementation 'com.github.microsoft:engagementinsights-sdk-android:v1.0.0'
        api 'com.google.code.gson:gson:2.8.1'
    }
    ```

### <a name="option-2-use-download-link"></a>Opción 2: usar a ligazón de descarga
1. Descargue o [SDK de Android de información de interacción](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-android-sdk.zip) e coloque o ficheiro `eiandroidsdk-debug.aar` no cartafol `libs`.

1. Abra o ficheiro `build.gradle` do nivel do proxecto e engada os fragmentos de código seguintes:
    ```gradle
    dependencies {
        implementation(name: 'eiandroidsdk-debug', ext: 'aar')
        api 'com.google.code.gson:gson:2.8.1'
    }

    repositories {
        flatDir {
            dirs 'libs'
        }
    }
    ```

## <a name="enable-auto-instrumentation"></a>Activar a instrumentación automática

1. Engada permiso para a rede e Internet no seu ficheiro `AndroidManifest.xml` situado baixo o cartafol `manifests`.
    ```xml
    <manifest>
        ...
        <uses-permission android:name="android.permission.INTERNET" />
        <uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
    ```

1. Configure a configuración do SDK de información de interacción a través do seu ficheiro `AndroidManifest.xml`.

1. Copie o fragmento de XML da **Guía de instalación**. `Your-Ingestion-Key` debería cubrirse automaticamente.

   > [!NOTE]
   > Non precisa substituír a sección `${applicationId}`. Cúbrese automaticamente.


   ```xml
   <application>
   ...
       <provider
           android:authorities="${applicationId}.com.microsoft.engagementinsights.AnalyticsContentProvider"
           android:name="com.microsoft.engagementinsights.AnalyticsContentProvider" />
       <meta-data
           android:name="com.microsoft.engagementinsights.ingestionKey"
           android:value="Your-Ingestion-Key" />
       <meta-data
           android:name="com.microsoft.engagementinsights.autoCapture"
           android:value="true" />
   ...
   </application>
   ```

1. Active ou desactive a captura automática de eventos `View` mediante a configuración do campo u`autoCapture` anterior en `true` ou `false`. 

   >[!NOTE]
   >`Action` os eventos deben engadirse manualmente.

1. (Opcional) Outras configuracións inclúen a configuración do URL do colector do extremo. Pódense engadir baixo os metadatos da clave de inxestión en `AndroidManifest.xml`.

   ```xml
        <meta-data
            android:name="com.microsoft.engagementinsights.endpointUrl"
            android:value="https://some-endpoint-url.com" />
   ```

## <a name="implement-custom-events"></a>Implementar eventos personalizados

Despois de iniciar o SDK, pode traballar con eventos e as súas propiedades no contorno `MainActivity`.


Java:
```java
Analytics analytics = new Analytics();
```

Kotlin:
```kotlin
var analytics = Analytics()
```

### <a name="set-property-for-all-events-optional"></a>Establecer propiedade para todos os eventos (opcional)

Java:
```java
analytics.setProperty("year", 2021);
```

Kotlin:
```kotlin
analytics.setProperty("year", 2021)
```

Admítense os seguintes tipos para as propiedades do evento de contexto:
- String
- Data
- Dobre
- Longo
- Boolean
- UUID

### <a name="track-an-event"></a>Rastrexar un evento

Java:
```java
Event event = new Event("video");
event.setProperty("duration", 320);
event.setProperty("ad_shown", true);
analytics.trackEvent(event);
```

Kotlin:
```kotlin
var event = Event("video")
event.setProperty("duration", 320)
event.setProperty("ad_shown", true)
analytics.trackEvent(event)
```

## <a name="set-user-details-for-your-event-optional"></a>Definir os detalles do usuario para o seu evento (opcional)

O SDK permítelle definir a información do usuario que se pode enviar con cada evento. Pode especificar a información do usuario chamando a API `setUser(user: User)` no nivel de `Analytics`.

Java:
```java
User user = new User();
user.setName("testuser");
user.setEmail("abc@xyz.com");
analytics.setUser(user);
```

Kotlin:
```kotlin
var user = User()
user.name = "testuser"
user.email = "abc@xyz.com"
analytics.setUser(user)
```

A clase de datos `User` contén as seguintes propiedades de cadea:

- **localId** : o ID local do usuario.
- **authId** : o ID do usuario autenticado.
- **authType**: O tipo de autenticación usado para obter o ID de usuario autenticado.
- **name**: o nome do usuario.
- **email**: o enderezo de correo electrónico do usuario.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
