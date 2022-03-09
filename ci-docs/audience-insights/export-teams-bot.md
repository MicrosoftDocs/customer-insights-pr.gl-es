---
title: Bot para Microsoft Teams
description: Busque perfís de clientes unificados en Microsoft Teams coa axuda dun bot.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: d6b016c1ec35e26ce6449333234edfd218bc9354
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 02/16/2022
ms.locfileid: "8232100"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a>Bot de Teams para Dynamics 365 Customer Insights (vista previa)

Conéctese con Microsoft Teams para que un bot busque perfís de clientes unificados nas canles de Teams.

> [!div class="mx-imgBorder"]
> ![Bot de Teams que mostra un rexistro de clientes.](media/teams-bot.png "Bot de Teams que mostra un rexistro de clientes")

## <a name="prerequisites"></a>Requisitos previos

Para configurar e configurar o bot, deben cumprirse os seguintes requisitos previos:

- Hai polo menos unha [orixe de datos engadida](data-sources.md).
- O [proceso de unificación](data-unification.md) completouse.
- Os campos engádense ao [índice de busca e filtro](search-filter-index.md).
- Customer Insights e Teams están na mesma organización.
- O seu contorno ten o público obxectivo principal establecido para clientes individuais. Non se admiten as contas empresariais.


> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElj]
## <a name="configure-the-bot"></a>Configurar o bot

1. Na información do público, vaia a **Administrar** > **Destinos de exportación**.
1. No mosaico Microsoft Teams, seleccione **Configurar**.
1. Será dirixido á sección **Aplicacións** de Teams. Tamén pode abrir Teams e seleccionar **Aplicacións** na esquina inferior esquerda ou [obtelo de AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) directamente.
1. Busque **Customer Insights** e seleccione a aplicación.
1. Seleccione **Engadir**.
1. Despois de iniciar sesión en Customer Insights en Teams, verá unha mensaxe de benvida e poderá comezar.

## <a name="things-you-can-do-with-the-bot"></a>Accións que pode levar a cabo co bot

O bot ofrece capacidades de busca para perfís de clientes unificados.

- Introduza **buscar** seguido dun nome, enderezo de correo electrónico ou calquera outro campo do perfil de cliente unificado que se engada ao índice de busca e filtro.

  Obterá unha tarxeta con ata 15 campos do perfil de cliente resultante. As coincidencias múltiples devolven unha lista de resultados onde pode seleccionar un perfil. Pode engadir o termo de busca entre comiñas dobres para buscar unha coincidencia exacta.

- Se a súa organización mantén varios contornos de Customer Insights na mesma organización, pode introducir **switchinstance** para escoller a que contorno desexa conectar o bot.

- Introduza **axuda** para ver unha lista de comandos dispoñibles para o bot.  


[!INCLUDE[footer-include](../includes/footer-banner.md)]