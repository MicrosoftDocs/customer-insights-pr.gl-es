---
title: Conector de Power Automate | Microsoft Docs
description: Cree fluxos en Microsoft Power Automate dende Dynamics 365 Customer Insights.
ms.date: 01/20/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: fb1df4e9ab1f78300b8ec1f8dfdfbfbac0e71447
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268822"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="3c3ed-103">Conector de Power Automate (vista previa)</span><span class="sxs-lookup"><span data-stu-id="3c3ed-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="3c3ed-104">Desencadee eventos específicos para que se produzan automaticamente cando se modifiquen os datos e xestione fluxos máis complexos directamente en [Power Automate](https://flow.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="3c3ed-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="3c3ed-105">Desencadeadores de Power Automate</span><span class="sxs-lookup"><span data-stu-id="3c3ed-105">Power Automate triggers</span></span>

<span data-ttu-id="3c3ed-106">Use desencadeadores para crear fluxos na nube e automatizar tarefas repetitivas, como notificacións ou accións máis avanzadas.</span><span class="sxs-lookup"><span data-stu-id="3c3ed-106">Use triggers to create cloud flows and automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="3c3ed-107">Desencadeador cando falla unha actualización dunha orixe de datos.</span><span class="sxs-lookup"><span data-stu-id="3c3ed-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="3c3ed-108">Desencadeador cando se fai unha actualización dunha orixe de datos correctamente.</span><span class="sxs-lookup"><span data-stu-id="3c3ed-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="3c3ed-109">Desencadear cando se cruza un limiar nun segmento.</span><span class="sxs-lookup"><span data-stu-id="3c3ed-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="3c3ed-110">O desencadeador está limitado a cruzar por enriba do limiar.</span><span class="sxs-lookup"><span data-stu-id="3c3ed-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="3c3ed-111">Desencadear cando se cruza un limiar nunha medición de empresa.</span><span class="sxs-lookup"><span data-stu-id="3c3ed-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="3c3ed-112">O desencadeador está limitado a cruzar por enriba do limiar.</span><span class="sxs-lookup"><span data-stu-id="3c3ed-112">The trigger is limited crossing above the threshold.</span></span>
- <span data-ttu-id="3c3ed-113">Activar cando se complete unha actualización completa de (fontes de datos, segmentos, medidas...).</span><span class="sxs-lookup"><span data-stu-id="3c3ed-113">Trigger when a full refresh of (data sources, segments, measures,...) is completed.</span></span>
- <span data-ttu-id="3c3ed-114">Activar cando se completa unha actualización do proceso de unificación (mapa, coincidencia, combinación).</span><span class="sxs-lookup"><span data-stu-id="3c3ed-114">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

<span data-ttu-id="3c3ed-115">[Configure os desencadeadores en Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span><span class="sxs-lookup"><span data-stu-id="3c3ed-115">[Configure your triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span></span>

## <a name="power-automate-actions"></a><span data-ttu-id="3c3ed-116">Accións de Power Automate</span><span class="sxs-lookup"><span data-stu-id="3c3ed-116">Power Automate actions</span></span>
<span data-ttu-id="3c3ed-117">O conector de Power Automate ofrece outras accións que os desencadeadores dispoñibles.</span><span class="sxs-lookup"><span data-stu-id="3c3ed-117">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="3c3ed-118">Para obter máis información, consulte o [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span><span class="sxs-lookup"><span data-stu-id="3c3ed-118">For more information, see the [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow"></a><span data-ttu-id="3c3ed-119">Crear un fluxo de Power Automate</span><span class="sxs-lookup"><span data-stu-id="3c3ed-119">Create a Power Automate flow</span></span>

1. <span data-ttu-id="3c3ed-120">Na información do público, vaia a **Administrar** > **Destinos de exportación**.</span><span class="sxs-lookup"><span data-stu-id="3c3ed-120">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="3c3ed-121">No mosaico **Power Automate**, seleccione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="3c3ed-121">On the **Power Automate** tile, select **Set up**.</span></span>

1. <span data-ttu-id="3c3ed-122">Ábrese o conector de Customer Insights (versión preliminar) en Power Automate.</span><span class="sxs-lookup"><span data-stu-id="3c3ed-122">The Customer Insights Connector (preview) in Power Automate opens.</span></span> <span data-ttu-id="3c3ed-123">**Inicie sesión** en Power Automate.</span><span class="sxs-lookup"><span data-stu-id="3c3ed-123">**Sign in** to Power Automate.</span></span>

1. <span data-ttu-id="3c3ed-124">Elixa un dos desencadeadores dispoñibles e engadamáis pasos ao seu novo fluxo.</span><span class="sxs-lookup"><span data-stu-id="3c3ed-124">Choose one of the available triggers and add more steps to your new flow.</span></span> <span data-ttu-id="3c3ed-125">Para obter máis información, consulte [Crear un fluxo de nube en Power Automate](https://docs.microsoft.com/power-automate/get-started-logic-flow).</span><span class="sxs-lookup"><span data-stu-id="3c3ed-125">For more information, see [Create a cloud flow in Power Automate](https://docs.microsoft.com/power-automate/get-started-logic-flow).</span></span>

<span data-ttu-id="3c3ed-126">Exemplos de como usar os fluxos:</span><span class="sxs-lookup"><span data-stu-id="3c3ed-126">Examples how to use flows:</span></span> 
- <span data-ttu-id="3c3ed-127">Enviar unha mensaxe á canle de Microsoft Teams se falla unha actualización da orixe de datos.</span><span class="sxs-lookup"><span data-stu-id="3c3ed-127">Post a message to a Microsoft Teams channel if a data source refresh fails.</span></span> 
- <span data-ttu-id="3c3ed-128">Enviar un correo electrónico aos propietarios dos datos cando se cruza un limiar nun segmento.</span><span class="sxs-lookup"><span data-stu-id="3c3ed-128">Send an email to the data owners when a threshold on a segment is crossed.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]