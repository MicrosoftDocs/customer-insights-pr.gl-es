---
title: Conector de Power Automate | Microsoft Docs
description: Crear fluxos en Microsoft Power Automate a partir de Dynamics 365 Customer Insights.
ms.date: 06/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 57be0a204ef920b7a4bb31cf9a5b3a77f96eca0d
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305062"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="266d1-103">Conector de Power Automate (vista previa)</span><span class="sxs-lookup"><span data-stu-id="266d1-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="266d1-104">Desencadee eventos específicos para que se produzan automaticamente cando se modifiquen os datos e xestione fluxos máis complexos directamente en [Power Automate](https://flow.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="266d1-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="266d1-105">Desencadeadores de Power Automate</span><span class="sxs-lookup"><span data-stu-id="266d1-105">Power Automate triggers</span></span>

<span data-ttu-id="266d1-106">Use desencadeadores para crear fluxos na nube e automatizar tarefas repetitivas, como notificacións ou accións máis avanzadas.</span><span class="sxs-lookup"><span data-stu-id="266d1-106">Use triggers to create cloud flows and automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="266d1-107">Desencadeador cando falla unha actualización dunha orixe de datos.</span><span class="sxs-lookup"><span data-stu-id="266d1-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="266d1-108">Desencadeador cando se fai unha actualización dunha orixe de datos correctamente.</span><span class="sxs-lookup"><span data-stu-id="266d1-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="266d1-109">Desencadear cando se cruza un limiar nun segmento.</span><span class="sxs-lookup"><span data-stu-id="266d1-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="266d1-110">O desencadeador está limitado a cruzar por enriba do limiar.</span><span class="sxs-lookup"><span data-stu-id="266d1-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="266d1-111">Desencadear cando se cruza un limiar nunha medición de empresa.</span><span class="sxs-lookup"><span data-stu-id="266d1-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="266d1-112">Só se admiten as medicións de empresa sen ningunha dimensión.</span><span class="sxs-lookup"><span data-stu-id="266d1-112">Only business measures without a dimension are supported.</span></span> <span data-ttu-id="266d1-113">O desencadeador está limitado a cruzar por enriba do limiar.</span><span class="sxs-lookup"><span data-stu-id="266d1-113">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="266d1-114">Activar cando se complete unha actualización completa de (fontes de datos, segmentos, medidas...).</span><span class="sxs-lookup"><span data-stu-id="266d1-114">Trigger when a full refresh of (data sources, segments, measures, ...) is completed.</span></span>
- <span data-ttu-id="266d1-115">Activar cando se completa unha actualización do proceso de unificación (mapa, coincidencia, combinación).</span><span class="sxs-lookup"><span data-stu-id="266d1-115">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

[<span data-ttu-id="266d1-116">Configure os desencadeadores en Power Automate.</span><span class="sxs-lookup"><span data-stu-id="266d1-116">Configure your triggers in Power Automate.</span></span>](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

## <a name="power-automate-actions"></a><span data-ttu-id="266d1-117">Accións de Power Automate</span><span class="sxs-lookup"><span data-stu-id="266d1-117">Power Automate actions</span></span>

<span data-ttu-id="266d1-118">O conector de Power Automate ofrece outras accións que os desencadeadores dispoñibles.</span><span class="sxs-lookup"><span data-stu-id="266d1-118">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="266d1-119">Para obter máis información, consulte o [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span><span class="sxs-lookup"><span data-stu-id="266d1-119">For more information, see the [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow"></a><span data-ttu-id="266d1-120">Crear un fluxo de Power Automate</span><span class="sxs-lookup"><span data-stu-id="266d1-120">Create a Power Automate flow</span></span>

1. <span data-ttu-id="266d1-121">Na información do público, vaia a **Administrar** > **Destinos de exportación**.</span><span class="sxs-lookup"><span data-stu-id="266d1-121">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="266d1-122">No mosaico **Power Automate**, seleccione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="266d1-122">On the **Power Automate** tile, select **Set up**.</span></span>

1. <span data-ttu-id="266d1-123">Ábrese o conector de Customer Insights (versión preliminar) en Power Automate.</span><span class="sxs-lookup"><span data-stu-id="266d1-123">The Customer Insights Connector (preview) in Power Automate opens.</span></span> <span data-ttu-id="266d1-124">**Inicie sesión** en Power Automate.</span><span class="sxs-lookup"><span data-stu-id="266d1-124">**Sign in** to Power Automate.</span></span>

1. <span data-ttu-id="266d1-125">Elixa un dos desencadeadores dispoñibles e engadamáis pasos ao seu novo fluxo.</span><span class="sxs-lookup"><span data-stu-id="266d1-125">Choose one of the available triggers and add more steps to your new flow.</span></span> <span data-ttu-id="266d1-126">Para obter máis información, consulte [Crear un fluxo de nube en Power Automate](/power-automate/get-started-logic-flow).</span><span class="sxs-lookup"><span data-stu-id="266d1-126">For more information, see [Create a cloud flow in Power Automate](/power-automate/get-started-logic-flow).</span></span>

<span data-ttu-id="266d1-127">Exemplos de como usar os fluxos:</span><span class="sxs-lookup"><span data-stu-id="266d1-127">Examples of how to use flows:</span></span> 
- <span data-ttu-id="266d1-128">Enviar unha mensaxe á canle de Microsoft Teams se falla unha actualización da orixe de datos.</span><span class="sxs-lookup"><span data-stu-id="266d1-128">Post a message to a Microsoft Teams channel if a data source refresh fails.</span></span> 
- <span data-ttu-id="266d1-129">Enviar un correo electrónico aos propietarios dos datos cando se cruza un limiar nun segmento.</span><span class="sxs-lookup"><span data-stu-id="266d1-129">Send an email to the data owners when a threshold on a segment is crossed.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]
