---
title: Recoñecer eventos web de visitantes previamente autenticados coa función de descoñecido a coñecido
description: A función de descoñecido a coñecido permítelle asociar eventos nun sitio web con visitantes que se autenticaron previamente.
ms.reviewer: mhart
ms.author: mkisel
author: mkisel11
ms.date: 7/15/2021
ms.subservice: engagement-insights
ms.topic: overview
ms.manager: shellyha
ms.openlocfilehash: 75ce776fd5be1c426508ae6f5c239c86bdd3ec39
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 02/16/2022
ms.locfileid: "8230678"
---
# <a name="recognize-web-events-from-previously-authenticated-visitors"></a>Recoñecer eventos web de visitantes previamente autenticados

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

A función **de descoñecido a coñecido** na capacidade de información de interacción permite asociar eventos nun sitio web con visitantes que se autenticaron previamente. Se a función está desactivada, os visitantes que se autenticaron durante unha visita anterior e despois saíron, non se identifican se non se autentican de novo ao volver. 

Por exemplo, unha persoa visitou un sitio web a semana pasada, iniciou sesión na súa conta de usuario no sitio e explorou o catálogo de produtos. A persoa regresa a semana seguinte para buscar máis produtos sen iniciar sesión na súa conta. O propietario do sitio que usa a función **de descoñecido a coñecido** sabería que a mesma persoa regresou e o que fixo no sitio. Isto permite obter análises e informes máis precisos das actividades do sitio web.

## <a name="enable-unknown-to-known"></a>Activar de descoñecido a coñecido

Necesita ser [administrador de áreas de traballo](user-roles.md) para activar esta funcionalidade. 

1. Na información de interacción, vaia a **Administración** > **Área de traballo**. 
2. Seleccione o separador **Configuración**.
3. Na sección **De descoñecido a coñecido**, configure a opción en **Activado**.

![Activar de descoñecido a coñecido](media/U2Ktoggle.png "Activar de descoñecido a coñecido")

## <a name="adding-javascript-code-to-your-sites-tracking-snippet"></a>Engadir código JavaScript ao fragmento de rastrexo do sitio

Un sitio web pode capturar o **authId do usuario** coa seguinte mostra de JavaScript usando o [SDK web de información de interacción](advanced-SDK-implementation.md). Para que funcione a función **de descoñecido a coñecido**, cómpre capturar o authId *e* activar userMapping:True no fragmento de JavaScript, como no exemplo seguinte.

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
},
userMapping: true
},
user:{
authId: getLoggedInUserId()*,
email: getLoggedInUserEmail()*,
authType: "MSA",
name: "Alex Jensen"
}
[…]
```

[!INCLUDE[footer-include](../includes/footer-banner.md)]
