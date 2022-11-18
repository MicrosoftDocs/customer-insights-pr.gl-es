---
title: Xestiona perfís descoñecidos con Customer Insights
description: Traballa con perfís de clientes descoñecidos que se crean e xestionan en Dynamics 365 Customer Insights.
ms.date: 09/14/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: andtapia
ms.author: andreatapia
manager: shellyha
ms.openlocfilehash: 0e12f64a22b93d117009fb8aee76d02a7583e699
ms.sourcegitcommit: 24627d53dcdf607baaab1cc3c299a3584c386173
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 11/15/2022
ms.locfileid: "9776819"
---
# <a name="manage-unknown-profiles-with-customer-insights"></a>Xestiona perfís descoñecidos con Customer Insights

Os usuarios de Internet adoitan estar en liña non identificados ou anónimos. Incluso os clientes máis fieis poden parecer "descoñecidos" se non inician sesión en diferentes dispositivos. Para moitas marcas, os usuarios coñecidos ou autenticados son minoría a pesar das crecentes expectativas dos clientes en torno á personalización. Co futuro das cookies de terceiros en cuestión, xestionar as preferencias dos usuarios baseándose en datos de terceiros é fundamental para conseguir experiencias personalizadas.

A personalización memorable depende do ben que coñezas ao teu cliente e Customer Insights axúdache a facelo facendo un seguimento de todos os teus clientes.  Non tes que limitar nin deter o uso dos datos recollidos ao inicio do viaxe do cliente. Customer Insights permíteche traer os teus propios datos para crear un perfil de cliente para usuarios descoñecidos. Despois, podes usar ese perfil para realizar máis accións, a pesar de que falta información de contacto. Importe datos propios de fontes como sistemas web, móbiles ou CRM en Customer Insights para enriquecer os perfís de clientes continuamente. A medida que unificas máis interaccións, [xira o *descoñecido* cliente en a *coñecido* cliente](unknown-to-known.md).

## <a name="sample-scenario"></a>Exemplo de escenario

Supoña que un usuario usa o seu dispositivo móbil para navegar polo seu sitio de comercio electrónico. O sitio web asigna ao visitante "mobile_guest123" como un identificador único e comeza a recoller actividades de comportamento en función da súa actividade en liña. Por exemplo, que páxinas visitaron, canto tempo pasaron nesas páxinas ou en que ligazóns fixeron clic. Non coñeces o seu nome nin o seu enderezo de correo electrónico, pero estes datos poden axudarlle a proporcionar ás marcas información significativa sobre este usuario específico. Á súa vez, pode poñer en funcionamento esas ideas a próxima vez que o usuario visite o sitio. Consulta Customer Insights para "mobile_guest123" para recuperar a lista de segmentos do usuario, como "orgánico", "clientes de pedidos anticipados de móbiles", "clientes de gran valor", etc., ou recupera o perfil para crear experiencias web personalizadas. Tamén pode exportar os datos a calquera sistema de activación para facer o mesmo.

## <a name="prerequisites"></a>Requisitos previos

- Inxerir datos propios en Customer Insights
- Cada entidade ten un ID único que se define como clave principal
- Cada entidade cunha clave principal para a personalización está unificada
- O sistema de xestión de contidos do teu sitio web pode usar API (para a personalización web baseada na comunicación directa con Customer Insights)

A seguinte táboa mostra un exemplo simplificado de como se poden capturar eventos web de gran valor.

|EventID|EventTimeStamp|ID do usuario|Chave primaria|EventName|
|--|--|--|--|--|
|1|09-15-2022 9:00:00|abc123|CookieID1|Vista do produto|
|2|09-18-2022 10:05:00|abc123|CookieID1|Vista do produto|
|3|09-18-2022 10:10:00|abc123|CookieID1|Engadir á cesta|
|4|09-21-2022 09:05:00|abc123|CookieID1|Vista do produto|

## <a name="data-ingestion"></a>Inxestión de datos

Para obter máis información sobre as opcións dispoñibles para a inxestión de datos, consulte [Visión xeral das fontes de datos](data-sources.md).

## <a name="data-unification"></a>Unificación de datos

Para obter máis información sobre a unificación de perfís de clientes, consulte [Visión xeral da unificación de datos](data-unification.md) .

## <a name="get-insights"></a>Obter a información

[Enriquecer](enrichment-hub.md) os teus datos, constrúe [medidas](measures.md) , e crea [segmentos](segments.md) para unha activación posterior.

Por exemplo, pode crear segmentos de usuarios descoñecidos que navegaron polas mesmas páxinas de produtos pero que nunca completaron a compra.

## <a name="activation"></a>Activación

Cos teus datos en Customer Insights e listos para comezar a traballar, podes usar Customer Insights para personalizar:

1. Usa o [API OData](apis.md) para recuperar unha pertenza de segmento ou un perfil de cliente Para obter máis exemplos, consulte [Exemplos de consulta de OData para as API de Customer Insights](odata-examples.md) .

1. [Exportar](export-destinations.md) seus datos aos seus sistemas de activación.

Exemplo: un usuario descoñecido visita un sitio web varias veces e visita páxinas de produtos para varios modelos de zapatos de coiro. Con eses datos dispoñibles en Customer Insights, pode incluír o usuario descoñecido no segmento de persoas que están interesadas nos zapatos de coiro. Use este segmento para informar a personalización da creación do seu sitio web para os visitantes que regresan. Na seguinte visita, o sitio recoñece ao usuario descoñecido e podería ofrecerlle un cupón do 10% en zapatos de coiro.

[!INCLUDE [footer-include](includes/footer-banner.md)]
