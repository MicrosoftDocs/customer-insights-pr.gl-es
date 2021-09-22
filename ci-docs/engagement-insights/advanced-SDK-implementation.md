---
title: Escenarios de SDK web avanzados
description: Escenarios avanzados que se terán en conta ao instrumentar o seu sitio web cun SDK.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 11/12/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 7455d276035bfaf1f8a93d0e3b0b0884353a4010715c05d1d696309f7eb4b233
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036326"
---
# <a name="advanced-web-sdk-instrumentation"></a>Instrumentación de SDK web avanzada

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Este artigo guíao a través de escenarios avanzados que terá en conta cando [instrumente o seu sitio web](instrument-website.md) cun SDK da capacidade de información de interacción de Dynamics 365 Customer Insights.

## <a name="setting-user-details-for-your-event"></a>Configuración dos detalles do usuario para o evento

O SDK permítelle definir a información do usuario que se pode enviar con cada evento. Pode especificar os detalles do usuario nunha propiedade chamada `user` (a información esperada para esta propiedade é o obxecto `IUser`), semellante a `src`, `name` e `cfg` na configuración do fragmento de código.

O obxecto `IUser` contén as seguintes propiedades de cadea:

- **localId** : o ID local do usuario.
- **authId** : o ID do usuario autenticado.
- **authType** : o tipo de autenticación usado para obter o ID do usuario autenticado.
- **name**: o nome do usuario.
- **email**: o enderezo de correo electrónico do usuario.
    
O seguinte exemplo mostra un fragmento de código que envía información do usuario. Cando vexa Funcións indicadas por*, substitúao pola súa implantación da chamada a eses valores:  

```
[…]
window, document 
{
    src:"https://download.pi.dynamics.com/sdk/web/mspi-0.min.js", 
    name:"myproject",      
    cfg:{ 
      ingestionKey:<paste your ingestion key>", 
      autoCapture:{ 
        view:true, 
        click:true 
      }
    },
    user:{
      authId: getLoggedInUserId()*,
      email: getLoggedInUserEmail()*,
      authType: "MSA",
      name: "John Doe"
    }
[…]
```

Tamén pode especificar a información do usuario chamando a API de `setUser(user: IUser)` no SDK. A telemetría enviada despois da chamada a `setUser API` conterá a información do usuario.

## <a name="adding-custom-properties-for-each-event"></a>Adición de propiedades personalizadas para cada evento

O SDK permítelle especificar propiedades personalizadas que se poden enviar con cada evento. Pode especificar as propiedades personalizadas como un obxecto que conteña pares clave-valor (o valor pode ser de tipo `string | number | boolean`). O obxecto pódese engadir nunha propiedade chamada `props`, semellante a `src`, `name` e `cfg` na configuración do fragmento de código. 

O seguinte exemplo mostra un fragmento de código que envía propiedades personalizadas:

```
[…]
window, document 
{
    src:"https://download.pi.dynamics.com/sdk/web/mspi-0.min.js", 
    name:"myproject",      
    cfg:{ 
      ingestionKey:<paste your ingestion key>", 
      autoCapture:{ 
        view:true, 
        click:true 
      }
    },
    props:{
      "key_name_string": "value",
      "key_name_number": 10,
      "key_name_bool": true
    }
[…]
```

Tamén pode especificar propiedades personalizadas individualmente chamando a API de `setProperty(name: string, value: string | number | boolean)` no SDK.

## <a name="sending-custom-events"></a>Envío de eventos personalizados

Pode usar o SDK para enviar eventos personalizados. Debe especificar un nome para o evento e as propiedades que se enviarán con el.

O seguinte exemplo mostra un fragmento de código que rastrexa un evento personalizado. O valor "NAME" é o valor da clave `name` na configuración do fragmento. Tamén é o nome da variable no obxecto de ventá no que se carga o SDK.

```
window["NAME"].trackEvent({
    name: "event_name",
    properties: {
        "duration": 320,
        "name": "getting_started",
        "ad_shown": true
    }
});
```


[!INCLUDE[footer-include](../includes/footer-banner.md)]