---
title: Personaliza as túas experiencias con datos sobre usuarios coñecidos e descoñecidos
description: Incorpora a información sobre usuarios anteriormente descoñecidos cando coñezas a súa identidade.
ms.date: 07/07/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 8e3477750d82f965dc2d62174fb35554d9447b7b
ms.sourcegitcommit: 52eca81c36e93d553140f5a37cf6013aaa42623a
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 08/03/2022
ms.locfileid: "9224293"
---
# <a name="personalize-your-experiences-with-data-about-known-and-unknown-users"></a>Personaliza as túas experiencias con datos sobre usuarios coñecidos e descoñecidos

Xestionar os datos dos clientes non é un reto novo, pero é cada vez máis difícil a medida que os usuarios navegan polas distintas canles dixitais que ofrecen as marcas. Un usuario que é coñecido (autenticado) nunha canle pasa a ser descoñecido (non autenticado) noutra se non inicia sesión. O problema a miúdo é que os usuarios non autenticados (descoñecidos) non teñen un ID común. Podería usarse para asociar atributos de perfís significativos e xerar perfís de clientes unificados. Customer Insights axuda a resolver este problema inxerindo datos dos métodos de seguimento dos teus sistemas fonte. A consolidación de perfís descoñecidos e coñecidos ofrece ás organizacións unha visión completa dos perfís actualizados e das súas transaccións, comportamentos e datos demográficos históricos. Incluso dá un paso máis alá proporcionando resolución de identidade que che permite unificar a actividade dos clientes en varias canles, incluíndo o teu sitio web, a compra en tenda, os programas de fidelización, etc.

## <a name="sample-scenario"></a>Escenario de exemplo

Pensemos nunha cadea de café, que ten unha ampla base de clientes que compra café e alimentos en tendas e encarga produtos en liña. Moitas veces, os visitantes en liña non son autenticados cando navegan polos produtos, polo que son "usuarios descoñecidos". É difícil para a cadea de café ofrecer ofertas e experiencias personalizadas se os usuarios son descoñecidos. Por outra banda, os clientes poden iniciar sesión na súa conta e converterse en "usuarios coñecidos" da empresa uníndose a un sistema de fidelización, que á súa vez permite experiencias máis personalizadas. Customer Insights pode axudar á cadea de café a obter información sobre usuarios coñecidos e previamente descoñecidos.

Con Customer Insights, a empresa pode combinar perfís de clientes con datos de actividade de sesións non autenticadas (descoñecidas) despois de que un usuario inicie sesión e sexa coñecido. A cadea de café pode traer datos doutras fontes de datos mediante conectores integrados en Customer Insights para combinar identidades para clientes de varias canles.

## <a name="prerequisites"></a>Requisitos previos

- Os datos web recóllense e conteñen "ID de visitante" para todos os visitantes.
- Os datos web conteñen "IDs de usuario autenticados" para os visitantes iniciados. Estes DNI están vinculados co sistema de fidelización.
- Os datos de eventos de alto valor, como "Vista de produto" e "Pagamento", defínense e inclúense nos datos de orixe xunto coa marca de tempo do evento e un ID de evento.

A seguinte táboa mostra un exemplo simplificado de como se poden capturar eventos web de alto valor.

|EventID|EventTimeStamp|ID do usuario|ID de fidelidade|EventName|
|--|--|--|--|--|
|1|07-23-2022 10:00:00|abc123|--|Vista do produto|
|2|07-23-2022 10:05:00|abc123|707|Inicio de sesión de fidelidade|
|3|07-23-2022 10:10:00|abc123|707|Finalizar compra|
|4|07-23-2022 10:20:00|xyz789|--|Vista do produto|

## <a name="data-ingestion"></a>Inxestión de datos

Os datos sobre os clientes poden orixinarse do teu sitio web como datos de eventos e pódense almacenar nos teus propios servizos de análise de datos internos ou de terceiros. Os datos web contén usuarios coñecidos e descoñecidos se o sitio web ten un fluxo de autenticación que se integra cun servizo de autenticación. Por exemplo, un sistema de comercio electrónico que require que os usuarios proporcionen os seus datos completos para finalizar unha transacción de compra. Ou un sistema de fidelización que require autenticación para confirmar un destinatario válido dos descontos de recompensas.

Os datos do evento do noso exemplo anterior contén os distintos ID de perfil dos usuarios coñecidos e descoñecidos. No evento 1 e 4, os usuarios son descoñecidos mentres que no evento 2 e 3 o usuario co ID abc123 inscríbese nun programa de fidelización.

:::image type="content" source="media/website-data-source.png" alt-text="Fontes de datos, incluíndo o sitio web Contoso.":::

Para obter máis información sobre as opcións dispoñibles para a inxestión de datos, consulte [Visión xeral das fontes de datos](data-sources.md).

## <a name="data-unification"></a>Unificación de datos

A converxencia de identidades descoñecidas con identidades coñecidas axuda a habilitar a personalización en función do comportamento dos usuarios, independentemente do estado do seu perfil (coñecido ou descoñecido). O contido personalizado para todos os usuarios axuda aos clientes a acceder rapidamente aos produtos ou servizos máis relevantes que lles interesan nese momento.

Dado que algúns dos usuarios dos nosos datos son coñecidos, podemos utilizar Customer Insights para combinar eses datos co perfil do usuario. Para obter máis información sobre a unificación de perfís de clientes, consulte [Visión xeral da unificación de datos](data-unification.md).

1. Seleccione os campos de orixe da entidade de datos web. Usa os datos do perfil que se almacenan nos teus datos web e selecciona os campos que representan ID con datos demográficos.

   :::image type="content" source="media/website-source-fields.png" alt-text="Campos de orixe para a web orixe de datos.":::

1. Engade regras para combinar rexistros duplicados. Para os datos web, escolla os datos máis completos.

1. Configura regras e condicións de coincidencia. Os datos de eventos dos perfís web deste exemplo coincidirán nos ID cos perfís doutras fontes de datos que conteñan información do cliente. Configura regras de coincidencia exacta sobre ID como regras separadas con cada unha das outras entidades de perfil que teñen a correspondente chave principal ou coincidencia de ID. No exemplo, os datos do perfil do evento web utilízanse como a última entidade coincidente para que primeiro se combinen outros datos do perfil.
   1. Non comprobando **Inclúe todos os rexistros** crea perfís unificados para usuarios coñecidos e inclúe os seus ID de usuario descoñecidos correspondentes. É útil nos escenarios nos que estás interesado en ver as actividades de comportamento pasadas de usuarios coñecidos cando aínda eran descoñecidos.
   1. Comprobación **Incluír todos os rexistros** crea rexistros de perfil separados para usuarios descoñecidos. Os usuarios descoñecidos reciben un ID de cliente único. No futuro, cando se asocie un perfil coñecido nos datos do perfil de eventos web, a viaxe do usuario recentemente coñecido tamén se poderá ver e utilizar para personalizarse en función de datos de comportamento descoñecidos no pasado.

:::image type="content" source="media/website-match-rule.png" alt-text="Regra de coincidencia para a entidade do sitio web orixe de datos.":::

## <a name="get-insights"></a>Obter a información

Se se crean perfís de clientes para usuarios descoñecidos e coñecidos, pódense utilizar os datos de eventos web de alto valor [actividades](activities.md). Estas actividades pódense usar para crear máis información. Por exemplo, os clientes que visitaron un sitio web hai seis meses (cando aínda eran descoñecidos) ou os clientes que non teñen unha identificación de fidelidade nunca completaron a compra.

:::image type="content" source="media/website-known-unknown.png" alt-text="Captura de pantalla da páxina do cliente con clientes coñecidos e descoñecidos.":::

[Enriquecer](enrichment-hub.md) os teus datos, constrúe [medidas](measures.md), e crea [segmentos](segments.md) para unha activación posterior.

Por exemplo, podes crear segmentos de usuarios coñecidos que miraron algúns produtos pero que nunca completaron a compra.

Para obter máis información, consulte [Visión xeral dos segmentos](segments.md).

## <a name="activate-insights"></a>Activar insights

Existen varias formas de exportar os teus datos e de tomar medidas en función das informacións subxacentes.

Para obter máis información, consulte [Visión xeral das exportacións](export-destinations.md).
