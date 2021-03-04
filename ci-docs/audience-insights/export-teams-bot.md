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
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a><span data-ttu-id="6b727-103">Bot de Teams para Dynamics 365 Customer Insights (vista previa)</span><span class="sxs-lookup"><span data-stu-id="6b727-103">Teams bot for Dynamics 365 Customer Insights (preview)</span></span>

<span data-ttu-id="6b727-104">Conéctese con Microsoft Teams para que un bot busque perfís de clientes unificados nas canles de Teams.</span><span class="sxs-lookup"><span data-stu-id="6b727-104">Connect with Microsoft Teams to let a bot look up unified customer profiles in Teams channels.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="6b727-105">![Bot de Teams que mostra un rexistro de clientes](media/teams-bot.png "Bot de Teams que mostra un rexistro de clientes")</span><span class="sxs-lookup"><span data-stu-id="6b727-105">![Teams bot showing a customer record](media/teams-bot.png "Teams bot showing a customer record")</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6b727-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="6b727-106">Prerequisites</span></span>

<span data-ttu-id="6b727-107">Para configurar e configurar o bot, deben cumprirse os seguintes requisitos previos:</span><span class="sxs-lookup"><span data-stu-id="6b727-107">To set up and configure the bot, the following prerequisites must be met:</span></span>

- <span data-ttu-id="6b727-108">Hai polo menos unha [orixe de datos engadida](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="6b727-108">There's at least one [data source added](data-sources.md).</span></span>
- <span data-ttu-id="6b727-109">O [proceso de unificación](data-unification.md) completouse.</span><span class="sxs-lookup"><span data-stu-id="6b727-109">The [unification process](data-unification.md) is complete.</span></span>
- <span data-ttu-id="6b727-110">Os campos engádense ao [índice de busca e filtro](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="6b727-110">Fields are added to the [search and filter index](search-filter-index.md).</span></span>
- <span data-ttu-id="6b727-111">Customer Insights e Teams están na mesma organización.</span><span class="sxs-lookup"><span data-stu-id="6b727-111">Customer Insights and Teams are in the same organization.</span></span>

## <a name="configure-the-bot"></a><span data-ttu-id="6b727-112">Configurar o bot</span><span class="sxs-lookup"><span data-stu-id="6b727-112">Configure the bot</span></span>

1. <span data-ttu-id="6b727-113">Na información do público, vaia a **Administrar** > **Destinos de exportación**.</span><span class="sxs-lookup"><span data-stu-id="6b727-113">In audience insights, go to **Admin** > **Export Destinations**.</span></span>
1. <span data-ttu-id="6b727-114">No mosaico Microsoft Teams, seleccione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="6b727-114">On the Microsoft Teams tile, select **Set up**.</span></span>
1. <span data-ttu-id="6b727-115">Será dirixido á sección **Aplicacións** de Teams.</span><span class="sxs-lookup"><span data-stu-id="6b727-115">You're redirected to the **Apps** area in Teams.</span></span> <span data-ttu-id="6b727-116">Tamén pode abrir Teams e seleccionar **Aplicacións** na esquina inferior esquerda ou [obtelo de AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) directamente.</span><span class="sxs-lookup"><span data-stu-id="6b727-116">You can also open Teams and select **Apps** in the bottom-left corner or [get it from AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) directly.</span></span>
1. <span data-ttu-id="6b727-117">Busque **Customer Insights** e seleccione a aplicación.</span><span class="sxs-lookup"><span data-stu-id="6b727-117">Search for **Customer Insights** and select the app.</span></span>
1. <span data-ttu-id="6b727-118">Seleccione **Engadir**.</span><span class="sxs-lookup"><span data-stu-id="6b727-118">Select **Add**.</span></span>
1. <span data-ttu-id="6b727-119">Despois de iniciar sesión en Customer Insights en Teams, verá unha mensaxe de benvida e poderá comezar.</span><span class="sxs-lookup"><span data-stu-id="6b727-119">After signing in to Customer Insights in Teams, you'll see a welcome message and can get started.</span></span>

## <a name="things-you-can-do-with-the-bot"></a><span data-ttu-id="6b727-120">Accións que pode levar a cabo co bot</span><span class="sxs-lookup"><span data-stu-id="6b727-120">Things you can do with the bot</span></span>

<span data-ttu-id="6b727-121">O bot ofrece capacidades de busca para perfís de clientes unificados.</span><span class="sxs-lookup"><span data-stu-id="6b727-121">The bot provides lookup capabilities for unified customer profiles.</span></span>

- <span data-ttu-id="6b727-122">Introduza **buscar** seguido dun nome, enderezo de correo electrónico ou calquera outro campo do perfil de cliente unificado que se engada ao índice de busca e filtro.</span><span class="sxs-lookup"><span data-stu-id="6b727-122">Enter **search** followed by a name, email address, or any other field on the unified customer profile that is added to the search and filter index.</span></span>

  <span data-ttu-id="6b727-123">Obterá unha tarxeta con ata 15 campos do perfil de cliente resultante.</span><span class="sxs-lookup"><span data-stu-id="6b727-123">You'll get a card with up to 15 fields from the resulting customer profile.</span></span> <span data-ttu-id="6b727-124">As coincidencias múltiples devolven unha lista de resultados onde pode seleccionar un perfil.</span><span class="sxs-lookup"><span data-stu-id="6b727-124">Multiple matches return a list of results where you can select a profile.</span></span> <span data-ttu-id="6b727-125">Pode engadir o termo de busca entre comiñas dobres para buscar unha coincidencia exacta.</span><span class="sxs-lookup"><span data-stu-id="6b727-125">You can add the search term in double quotes to look up an exact match.</span></span>

- <span data-ttu-id="6b727-126">Se a súa organización mantén varios contornos de Customer Insights na mesma organización, pode introducir **switchinstance** para escoller a que contorno desexa conectar o bot.</span><span class="sxs-lookup"><span data-stu-id="6b727-126">If your organization maintains multiple Customer Insights environments in the same organization, you can enter **switchinstance** to choose which environment you want to connect the bot to.</span></span>

- <span data-ttu-id="6b727-127">Introduza **axuda** para ver unha lista de comandos dispoñibles para o bot.</span><span class="sxs-lookup"><span data-stu-id="6b727-127">Enter **help** to see a list of available commands for the bot.</span></span>  


[!INCLUDE[footer-include](../includes/footer-banner.md)]