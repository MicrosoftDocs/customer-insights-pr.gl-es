---
title: Xestionar as cookies e o consentimento do usuario para almacenar os datos do usuario en Dynamics 365 Customer Insights
description: Comprenda como se usan as cookies e o consentimento do usuario para identificar os visitantes do sitio web.
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 09/27/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 018263220d4628690e9f0beb8453e58b0356d099
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 02/16/2022
ms.locfileid: "8228983"
---
# <a name="manage-cookies-and-user-consent"></a>Xestionar as cookies e o consentimento do usuario

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

A capacidade de información de compromiso de Dynamics 365 Customer Insights utiliza cookies e claves (`localStorage`) para identificar aos visitantes do sitio web.

As cookies son pequenos ficheiros que almacenan bits de información sobre as interaccións dun usuario co sitio web. Almacénanse nos exploradores web. Cando os usuarios visitan un sitio web no que os seus usuarios almacenaron cookies, o explorador envía esa información ao servidor, que devolve información exclusiva do usuario. Esta é a tecnoloxía que permite, por exemplo, que un carro da compra en liña garde os artigos seleccionados nel aínda que un usuario saíse do sitio web.

## <a name="user-consent"></a>Consentimento do usuario

O [Regulamento xeral de protección de datos (RXPD)](/dynamics365/get-started/gdpr/) é un regulamento da Unión Europea (UE) que impón como as organizacións deben tratar a privacidade e seguranza dos seus usuarios. As cookies adoitan almacenar ou recompilar "datos persoais", como un identificador en liña, que están amparados polo RXPD. Se a súa empresa emprega e/ou vende a titulares de datos da UE, o RXPD aféctalle. [Obteña máis información sobre como Microsoft pode axudarlle a cumprir o RXPD](https://www.microsoft.com/trust-center/privacy/gdpr-faqs).

Para permitir que o SDK de información de interacción almacene cookies ou outra información confidencial, debe especificar se os seus usuarios o consentiron. Isto ocorre no inicio do SDK configurando un campo de `userConsent` na configuración.

Se indica que non hai consentimento do usuario, o SDK non almacenará ningún dato e non enviará eventos que se poidan usar para rastrexar o seu comportamento. Os datos almacenados previamente eliminaranse do explorador.

Se non se especifica ningún valor de consentimento do usuario, o SDK asumirá que o usuario o consentiu. Isto significa que se vostede (como cliente noso) non especifica un valor para o consentimento do usuario no SDK, recompilaranse datos. Non obstante, se especifica que o valor do consentimento do usuario debe ser "true", os datos non se recompilarán se un usuario rexeita ou non proporciona o consentimento explícito.

A continuación móstrase un fragmento de código para iniciar o SDK web co consentimento do usuario:
```js
<script>
  (function(a,t,i){var e="MSEI";var s="Analytics";var o=e+"queue";a[o]=a[o]||[];var r=a[e]||function(n){var t={};t[s]={};function e(e){while(e.length){var r=e.pop();t[s][r]=function(e){return function(){a[o].push([e,n,arguments])}}(r)}}var r="track";var i="set";e([r+"Event",r+"View",r+"Action",i+"Property",i+"User","initialize","teardown"]);return t}(i.name);var n=i.name;if(!a[e]){a[n]=r[s];a[o].push(["new",n]);setTimeout(function(){var e="script";var r=t.createElement(e);r.async=1;r.src=i.src;var n=t.getElementsByTagName(e)[0];n.parentNode.insertBefore(r,n)},1)}else{a[n]=new r[s]}if(i.user){a[n].setUser(i.user)}if(i.props){for(var c in i.props){a[n].setProperty(c,i.props[c])}}a[n].initialize(i.cfg)})(window,document,{
    src:"https://download.pi.dynamics.com/sdk/web/msei-1.min.js",
    name:"EiJS",
    cfg:{
      ingestionKey:"YOUR-INGESTIONKEY",
      autoCapture:{
        view:true,
        click:true
      },
      userConsent: true
    }
  });
</script>
```

## <a name="visitor-data-storage-in-engagement-insights-capability"></a>Almacenamento de datos de visitantes na capacidade de información de interacción

### <a name="cookies"></a>Cookies

- _msei
    - Almacena o ID de usuario anónimo. Esta cookie está establecida no dominio do cliente e caduca en 365 días.

### <a name="local-storage"></a>Almacenamento local

A capacidade de información de implicación tamén fai uso de claves de (`localStorage`) para rastrexar datos non confidenciais. Estes datos almacénanse completamente no propio explorador, sen que se envíe tráfico aos ou desde os seus servidores.

- *EISession.Id*
    - Almacena información sobre a sesión do usuario en curso, como o ID da sesión, cando comezou e cando caduca.
- *EISession.Previous*
    - Almacena o URL da páxina visitada anteriormente na sesión actual.

As claves do almacenamento local non caducan automaticamente e restableceranse durante a próxima sesión do SDK.

## <a name="deleting-cookies"></a>Eliminar cookies

Os seus clientes poden eliminar manualmente as cookies e as claves de almacenamento local en calquera momento a través da configuración dos seus exploradores.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
