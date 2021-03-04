---
title: Bot para Microsoft Teams
description: Busque perfís de clientes unificados en Microsoft Teams coa axuda dun bot.
ms.date: 04/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 03299610fd41a7e142e3c9723fad56ce7f90e083
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267950"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a>Bot de Teams para Dynamics 365 Customer Insights (vista previa)

Conéctese con Microsoft Teams para que un bot busque perfís de clientes unificados nas canles de Teams.

> [!div class="mx-imgBorder"]
> ![Bot de Teams que mostra un rexistro de clientes](media/teams-bot.png "Bot de Teams que mostra un rexistro de clientes")

## <a name="prerequisites"></a>Requisitos previos

Para configurar e configurar o bot, deben cumprirse os seguintes requisitos previos:

- Hai polo menos unha [orixe de datos engadida](data-sources.md).
- O [proceso de unificación](data-unification.md) completouse.
- Os campos engádense ao [índice de busca e filtro](search-filter-index.md).
- Customer Insights e Teams están na mesma organización.

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