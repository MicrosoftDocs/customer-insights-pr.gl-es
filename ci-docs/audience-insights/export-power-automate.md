---
title: Conector de Power Automate | Microsoft Docs
description: Cree fluxos en Microsoft Power Automate dende Dynamics 365 Customer Insights.
ms.date: 08/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: ffe92414365b0b777691a4a2d585100e4fbea591
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405693"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="c85e7-103">Conector de Power Automate (vista previa)</span><span class="sxs-lookup"><span data-stu-id="c85e7-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="c85e7-104">Desencadee eventos específicos para que se produzan automaticamente cando se modifiquen os datos e xestione fluxos máis complexos directamente en [Power Automate](https://flow.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="c85e7-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="c85e7-105">Desencadeadores de Power Automate</span><span class="sxs-lookup"><span data-stu-id="c85e7-105">Power Automate triggers</span></span>

<span data-ttu-id="c85e7-106">Pode usar unha variedade de desencadeadores que lle permiten crear fluxos para automatizar tarefas repetitivas, como notificacións ou accións máis avanzadas.</span><span class="sxs-lookup"><span data-stu-id="c85e7-106">You can use a variety of triggers that allow you to create flows to automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="c85e7-107">Desencadeador cando falla unha actualización dunha orixe de datos.</span><span class="sxs-lookup"><span data-stu-id="c85e7-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="c85e7-108">Desencadeador cando se fai unha actualización dunha orixe de datos correctamente.</span><span class="sxs-lookup"><span data-stu-id="c85e7-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="c85e7-109">Desencadear cando se cruza un limiar nun segmento.</span><span class="sxs-lookup"><span data-stu-id="c85e7-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="c85e7-110">O desencadeador está limitado a cruzar por enriba do limiar.</span><span class="sxs-lookup"><span data-stu-id="c85e7-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="c85e7-111">Desencadear cando se cruza un limiar nunha medición de empresa.</span><span class="sxs-lookup"><span data-stu-id="c85e7-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="c85e7-112">O desencadeador está limitado a cruzar por enriba do limiar.</span><span class="sxs-lookup"><span data-stu-id="c85e7-112">The trigger is limited crossing above the threshold.</span></span>
- <span data-ttu-id="c85e7-113">Activar cando se complete unha actualización completa de (fontes de datos, segmentos, medidas...).</span><span class="sxs-lookup"><span data-stu-id="c85e7-113">Trigger when a full refresh of (data sources, segments, measures,...) is completed.</span></span>
- <span data-ttu-id="c85e7-114">Activar cando se completa unha actualización do proceso de unificación (mapa, coincidencia, combinación).</span><span class="sxs-lookup"><span data-stu-id="c85e7-114">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

<span data-ttu-id="c85e7-115">[Configure os desencadeadores en Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span><span class="sxs-lookup"><span data-stu-id="c85e7-115">[Configure your triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span></span>

## <a name="power-automate-actions"></a><span data-ttu-id="c85e7-116">Accións de Power Automate</span><span class="sxs-lookup"><span data-stu-id="c85e7-116">Power Automate actions</span></span>
<span data-ttu-id="c85e7-117">O conector de Power Automate ofrece outras accións que os desencadeadores dispoñibles.</span><span class="sxs-lookup"><span data-stu-id="c85e7-117">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="c85e7-118">Para obter máis información, consulte o [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span><span class="sxs-lookup"><span data-stu-id="c85e7-118">For more information, see the [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow-in-audience-insights"></a><span data-ttu-id="c85e7-119">Crear un fluxo de Power Automate na información do público</span><span class="sxs-lookup"><span data-stu-id="c85e7-119">Create a Power Automate flow in audience insights</span></span>

1. <span data-ttu-id="c85e7-120">Na información do público, vaia a **Administrar** > **Sistema**.</span><span class="sxs-lookup"><span data-stu-id="c85e7-120">In audience insights, go to **Admin** > **System**.</span></span>

1. <span data-ttu-id="c85e7-121">Na páxina **Sistema**, seleccione o separador **Estado**.</span><span class="sxs-lookup"><span data-stu-id="c85e7-121">On the **System** page, select the **Status** tab.</span></span>

1. <span data-ttu-id="c85e7-122">Na sección **Orixes de datos**, seleccione **Fluxos** e **Crear un fluxo** na lista despregable.</span><span class="sxs-lookup"><span data-stu-id="c85e7-122">In the **Data Sources** section, select **Flows** and select **Create a flow** from the dropdown list.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c85e7-123">![Conector de Power Automate que mostra a acción Crear un fluxo](media/power-automate-connector-create-flow.png "Conector de Power Automate que mostra a acción Crear un fluxo")</span><span class="sxs-lookup"><span data-stu-id="c85e7-123">![Power Automate connector showing Create a Flow action](media/power-automate-connector-create-flow.png "Power Automate connector showing Create a Flow action")</span></span>

1. <span data-ttu-id="c85e7-124">En Power Automate, seleccione un dos desencadeadores para crear o fluxo preferido.</span><span class="sxs-lookup"><span data-stu-id="c85e7-124">In Power Automate, select one of the available triggers to create your preferred flow.</span></span> <span data-ttu-id="c85e7-125">Se está a crear o primeiro fluxo, ten que autenticarse co conector de Power Automate primeiro.</span><span class="sxs-lookup"><span data-stu-id="c85e7-125">If you're creating your first flow, you'll need to authenticate with the Power Automate connector first.</span></span>
