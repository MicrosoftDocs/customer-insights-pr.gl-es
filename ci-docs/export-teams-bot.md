---
title: Bot de Teams para Dynamics 365 Customer Insights (vista previa)
description: Busque perfís de clientes unificados en Microsoft Teams coa axuda dun bot.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: d140ae72578b48091a41005c4acafe03bac540da
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195840"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a>Bot de Teams para Dynamics 365 Customer Insights (vista previa)

Conéctese con Microsoft Teams para que un bot busque perfís de clientes unificados nas canles de Teams.

:::image type="content" source="media/teams-bot.png" alt-text="Bot de Teams que mostra un rexistro de clientes":::

## <a name="prerequisites"></a>Requisitos previos

- Polo menos un [orixe de datos engadido](data-sources.md).
- O [proceso de unificación](data-unification.md) completouse.
- Engádense campos ao [índice de busca e filtro](search-filter-index.md).
- Customer Insights e Teams están na mesma organización.
- O seu contorno ten o público obxectivo principal establecido para clientes individuais. Non se admiten as contas empresariais.


> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElj]

## <a name="configure-the-bot"></a>Configurar o bot

1. Vaia a **Administrar** > **Conexións**.
1. No mosaico Microsoft Teams, seleccione **Configurar**.
1. Será dirixido á sección **Aplicacións** de Teams. Tamén pode abrir Teams e seleccionar **Aplicacións** na esquina inferior esquerda ou [obtelo de AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) directamente.
1. Busque **Customer Insights** e seleccione a aplicación.
1. Seleccione **Engadir**.
1. Inicia sesión en Customer Insights en Teams. Aparece unha mensaxe de benvida.

## <a name="things-you-can-do-with-the-bot"></a>Accións que pode levar a cabo co bot

O bot ofrece capacidades de busca para perfís de clientes unificados.

- Entra **buscar** seguido dun nome, enderezo de correo electrónico ou calquera outro campo do perfil de cliente unificado que se engade ao índice de busca e filtro.

  Obterá unha tarxeta con ata 15 campos do perfil de cliente resultante. As coincidencias múltiples devolven unha lista de resultados onde pode seleccionar un perfil. Para buscar unha coincidencia exacta, engade o termo de busca entre comiñas dobres.

- Se a súa organización mantén varios ambientes de Customer Insights na mesma organización, introduza **instancia de conmutación** para escoller a que ambiente desexa conectar o bot.

- Introduza **axuda** para ver unha lista de comandos dispoñibles para o bot.  

[!INCLUDE [footer-include](includes/footer-banner.md)]