---
title: Xestionar as cookies e o consentimento do usuario para almacenar os seus datos
description: Comprenda como se usan as cookies e o consentimento do usuario para identificar os visitantes do sitio web.
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 10/30/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 7b3195a92c969ab36e5b43f4c2e4221ff477a0a8958838e1256528f58fe13dce
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036736"
---
# <a name="manage-cookies-and-user-consent"></a>Xestionar as cookies e o consentimento do usuario

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

A capacidade de información de interacción de Dynamics 365 Customer Insights utiliza cookies e almacenamento local (`localStorage`) para identificar os visitantes do sitio web.

As cookies son pequenos ficheiros que almacenan bits de información sobre as interaccións dun usuario co sitio web. Almacénanse nos exploradores web. Cando os usuarios visitan un sitio web no que os seus usuarios almacenaron cookies, o explorador envía esa información ao servidor, que devolve información exclusiva do usuario. Esta é a tecnoloxía que permite, por exemplo, que un carro da compra en liña garde os artigos seleccionados nel aínda que un usuario saíse do sitio web.

## <a name="user-consent"></a>Consentimento do usuario

O [Regulamento xeral de protección de datos (RXPD)](/dynamics365/get-started/gdpr/) é un regulamento da Unión Europea (UE) que impón como as organizacións deben tratar a privacidade e seguranza dos seus usuarios. As cookies adoitan almacenar ou recompilar "datos persoais", como un identificador en liña, que están amparados polo RXPD. Se a súa empresa emprega e/ou vende a titulares de datos da UE, o RXPD aféctalle. [Obteña máis información sobre como Microsoft pode axudarlle a cumprir o RXPD](https://www.microsoft.com/trust-center/privacy/gdpr-faqs).

Para permitir que o SDK de información de interacción almacene cookies ou outra información confidencial, debe especificar se os seus usuarios o consentiron. Isto ocorre durante a inicialización do SDK.

Se indica que non hai consentimento do usuario, o SDK non almacenará ningún dato e non enviará eventos que se poidan usar para rastrexar o seu comportamento. Os datos almacenados previamente eliminaranse do explorador.

Se non se especifica ningún valor de consentimento do usuario, o SDK asumirá que o usuario o consentiu. Isto significa que se vostede (como cliente noso) non especifica un valor para o consentimento do usuario no SDK, recompilaranse datos. Non obstante, se especifica que o valor do consentimento do usuario debe ser "true", os datos non se recompilarán se un usuario rexeita ou non proporciona o consentimento explícito.

## <a name="visitor-data-storage-in-engagement-insights-capability"></a>Almacenamento de datos de visitantes na capacidade de información de interacción

### <a name="cookies"></a>Cookies

- _msei
    - Almacena o ID de usuario anónimo. Esta cookie está establecida no dominio do cliente e caduca en 365 días.

### <a name="local-storage"></a>Almacenamento local

A capacidade de información de interacción tamén usa o almacenamento local (`localStorage`) para rastrexar datos non confidenciais. Estes datos almacénanse completamente no propio explorador, sen que se envíe tráfico aos ou desde os seus servidores.

- *EISession.Id* 
    - Almacena información sobre a sesión do usuario en curso, como o ID da sesión, cando comezou e cando caduca.
- *EISession.Previous*
    - Almacena o URL da páxina visitada anteriormente na sesión actual.
    
As claves do almacenamento local non caducan automaticamente. O SDK restableceraas durante a próxima sesión.

## <a name="deleting-cookies"></a>Eliminar cookies

Os seus clientes poden eliminar manualmente as cookies e as claves de almacenamento local en calquera momento a través da configuración dos seus exploradores.


[!INCLUDE[footer-include](../includes/footer-banner.md)]