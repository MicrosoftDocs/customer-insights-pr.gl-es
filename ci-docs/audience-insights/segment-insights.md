---
title: Información de segmentos para segmentos existentes
description: Obteña información sobre os segmentos existentes para ver diferenzas e aspectos comúns.
ms.date: 06/10/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: jimsonc
manager: shellyha
ms.openlocfilehash: d731d21462b5a31aba0653f87e299d98373bbf49
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270018"
---
# <a name="segment-insights-preview"></a><span data-ttu-id="8a041-103">Información do segmento (previsualización)</span><span class="sxs-lookup"><span data-stu-id="8a041-103">Segment insights (preview)</span></span>

<span data-ttu-id="8a041-104">Descubra información e ideas adicionais sobre os seus segmentos existentes.</span><span class="sxs-lookup"><span data-stu-id="8a041-104">Discover additional information and insights around your existing segments.</span></span> <span data-ttu-id="8a041-105">Descubra o que diferencia dous segmentos ou o que teñen en común.</span><span class="sxs-lookup"><span data-stu-id="8a041-105">Find out what differentiates two segments or what they have in common.</span></span>

## <a name="segment-overlap"></a><span data-ttu-id="8a041-106">Superposición de segmentos</span><span class="sxs-lookup"><span data-stu-id="8a041-106">Segment overlap</span></span>

<span data-ttu-id="8a041-107">A análise do solapamento dos segmentos mostra cantos e que clientes son comúns a dous ou máis segmentos.</span><span class="sxs-lookup"><span data-stu-id="8a041-107">Segment overlap analysis shows how many and which customers are common to two or more segments.</span></span> <span data-ttu-id="8a041-108">Por exemplo, como un segmento de clientes frecuentes se solapa cun segmento que contén clientes satisfeitos co seu servizo ou produto.</span><span class="sxs-lookup"><span data-stu-id="8a041-108">For example, how a segment of frequent customers overlaps with a segment that contains customers that are satisfied with your service or product.</span></span>
<span data-ttu-id="8a041-109">Tamén pode analizar como cambia a superposición para atributos específicos.</span><span class="sxs-lookup"><span data-stu-id="8a041-109">You can also analyze how the overlap changes for specific attributes.</span></span>

### <a name="run-an-overlap-analysis"></a><span data-ttu-id="8a041-110">Realizar unha análise de solapamentos</span><span class="sxs-lookup"><span data-stu-id="8a041-110">Run an overlap analysis</span></span>

1. <span data-ttu-id="8a041-111">Vaia a **Segmentos** e seleccione o separadpr **Información (vista previa)**.</span><span class="sxs-lookup"><span data-stu-id="8a041-111">Go to **Segments** and select the **Insights (preview)** tab.</span></span>

1. <span data-ttu-id="8a041-112">Seleccione **Novo** e escolla a opción **Superposición** no panel **Escoller tipo de información**.</span><span class="sxs-lookup"><span data-stu-id="8a041-112">Select **New** and choose the **Overlap** option in the **Choose Insight Type** pane.</span></span>

1. <span data-ttu-id="8a041-113">Escolla os segmentos de interese e seleccione **Seguinte**.</span><span class="sxs-lookup"><span data-stu-id="8a041-113">Choose the segments of interest and select **Next**.</span></span>

1. <span data-ttu-id="8a041-114">Opcionalmente, escolla un ou varios campos de interese para analizar solapamentos para cada valor do campo posible e seleccione **Seguinte**.</span><span class="sxs-lookup"><span data-stu-id="8a041-114">Optionally, choose one or more fields of interest to analyze overlaps for every possible field value and select **Next**.</span></span>

1. <span data-ttu-id="8a041-115">Proporcione un nome para a análise de solapamentos, un nome de visualización opcional e unha descrición.</span><span class="sxs-lookup"><span data-stu-id="8a041-115">Provide a name for you overlap analysis, an optional display name, and a description.</span></span>

1. <span data-ttu-id="8a041-116">Seleccione **Gardar** para iniciar a análise.</span><span class="sxs-lookup"><span data-stu-id="8a041-116">Select **Save** to start the analysis.</span></span> <span data-ttu-id="8a041-117">A análise de solapamentos está lista cando o estado cambia de Actualizar a Exitoso.</span><span class="sxs-lookup"><span data-stu-id="8a041-117">The overlap analysis is ready when the status changes from Refreshing to Successful.</span></span>

### <a name="view-and-optimize-an-overlap-analysis"></a><span data-ttu-id="8a041-118">Ver e optimizar unha análise de solapamento</span><span class="sxs-lookup"><span data-stu-id="8a041-118">View and optimize an overlap analysis</span></span>

<span data-ttu-id="8a041-119">Despois de completar a análise, busque detalles sobre esta información en **Segmentos** > **Información (vista previa)**.</span><span class="sxs-lookup"><span data-stu-id="8a041-119">After completing the analysis, find details on this insight on **Segments** > **Insights (preview)**.</span></span>

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-overlap.png" alt-text="Detalles da información do solapamento do segmento":::

<span data-ttu-id="8a041-121">Seleccione unha información para ver os resultados da análise:</span><span class="sxs-lookup"><span data-stu-id="8a041-121">Select an insight to see the analysis results:</span></span>

- <span data-ttu-id="8a041-122">Número de membros que se solapan nos segmentos seleccionados para a súa análise.</span><span class="sxs-lookup"><span data-stu-id="8a041-122">The number of members overlapping the segments selected for analysis.</span></span>
- <span data-ttu-id="8a041-123">Número de membros incluídos nun dos segmentos pero non no resto dos segmentos.</span><span class="sxs-lookup"><span data-stu-id="8a041-123">The number of members included in one of the segments but not in the rest of the segments.</span></span>
- <span data-ttu-id="8a041-124">Se seleccionou campos mentres configura a análise de solapamento, atoparáos nas pestañas correspondentes.</span><span class="sxs-lookup"><span data-stu-id="8a041-124">If you selected fields while configuring the overlap analysis, you'll find them in the corresponding tabs.</span></span> <span data-ttu-id="8a041-125">Pode usar o menú desplegable do filtro para seleccionar calquera nivel de interese do atributo e a táboa na parte inferior mostrará os datos correspondentes.</span><span class="sxs-lookup"><span data-stu-id="8a041-125">You can use the filter drop-down to select any attribute level of interest and the table at the bottom will show the corresponding data.</span></span>

## <a name="segment-differentiators"></a><span data-ttu-id="8a041-126">Diferenciadores de segmentos</span><span class="sxs-lookup"><span data-stu-id="8a041-126">Segment differentiators</span></span>

<span data-ttu-id="8a041-127">Os diferenciadores de segmentos axúdanlle a descubrir que diferencia un segmento do resto dos seus clientes ou doutro segmento.</span><span class="sxs-lookup"><span data-stu-id="8a041-127">Segment differentiators help you find out what differentiates a segment from the rest of your customers or from another segment.</span></span> <span data-ttu-id="8a041-128">Só ten que seleccionar un segmento e o sistema identificará atributos e medidas do perfil que distinguen o segmento seleccionado.</span><span class="sxs-lookup"><span data-stu-id="8a041-128">You just have to select a segment and the system will identify profile attributes and measures that distinguish the selected segment.</span></span>

### <a name="run-a-differentiator-analysis"></a><span data-ttu-id="8a041-129">Realizar unha análise de diferenciadores</span><span class="sxs-lookup"><span data-stu-id="8a041-129">Run a differentiator analysis</span></span>

1. <span data-ttu-id="8a041-130">Vaia a **Segmentos** e seleccione o separadpr **Información (vista previa)**.</span><span class="sxs-lookup"><span data-stu-id="8a041-130">Go to **Segments** and select the **Insights (preview)** tab.</span></span>

1. <span data-ttu-id="8a041-131">Seleccione **Novo** e escolla a opción **Superposición** no panel **Escoller tipo de información**.</span><span class="sxs-lookup"><span data-stu-id="8a041-131">Select **New** and choose the **Overlap** option in the **Choose Insight Type** pane.</span></span>

1. <span data-ttu-id="8a041-132">Escolla o segmento que desexa analizar como **Segmento primario** e seleccione **Seguinte**.</span><span class="sxs-lookup"><span data-stu-id="8a041-132">Choose the segment you want to analyze as **Primary segment** and select **Next**.</span></span>

1. <span data-ttu-id="8a041-133">Escolla **Todos os clientes** ou a **Segmento secundario** para comparar o seu segmento principal e seleccione **Seguinte**.</span><span class="sxs-lookup"><span data-stu-id="8a041-133">Choose **All customers** or a **Secondary segment** to compare your primary segment with and select **Next**.</span></span>

1. <span data-ttu-id="8a041-134">Opcionalmente, elixa un ou varios campos de interese para centrar a análise en atributos específicos e seleccione **Seguinte**.</span><span class="sxs-lookup"><span data-stu-id="8a041-134">Optionally, choose one or more fields of interest to focus the analysis on specific attributes and select **Next**.</span></span>

1. <span data-ttu-id="8a041-135">Proporcione un nome para a análise de solapamentos, un nome de visualización opcional e unha descrición.</span><span class="sxs-lookup"><span data-stu-id="8a041-135">Provide a name for you overlap analysis, an optional display name, and a description.</span></span>

1. <span data-ttu-id="8a041-136">Seleccione **Gardar** para iniciar a análise.</span><span class="sxs-lookup"><span data-stu-id="8a041-136">Select **Save** to start the analysis.</span></span> <span data-ttu-id="8a041-137">A análise de solapamentos está lista cando o estado cambia de Actualizar a Exitoso.</span><span class="sxs-lookup"><span data-stu-id="8a041-137">The overlap analysis is ready when the status changes from Refreshing to Successful.</span></span>

### <a name="view-and-optimize-a-differentiators-analysis"></a><span data-ttu-id="8a041-138">Ver e optimizar unha análise de diferenciadores</span><span class="sxs-lookup"><span data-stu-id="8a041-138">View and optimize a differentiators analysis</span></span>

<span data-ttu-id="8a041-139">Despois de completar a análise, busque detalles sobre esta información en **Segmentos** > **Información (vista previa)**.</span><span class="sxs-lookup"><span data-stu-id="8a041-139">After completing the analysis, find details on this insight on **Segments** > **Insights (preview)**.</span></span>

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-differentiators.png" alt-text="Detalles da información de diferenciadores do segmento":::

<span data-ttu-id="8a041-141">Seleccione unha información para ver os resultados da análise.</span><span class="sxs-lookup"><span data-stu-id="8a041-141">Select an insight to see the analysis results.</span></span> <span data-ttu-id="8a041-142">Unha análise diferenciadora inclúe dúas lapelas.</span><span class="sxs-lookup"><span data-stu-id="8a041-142">A differentiator analysis includes two tabs.</span></span> <span data-ttu-id="8a041-143">A lapela **Atributos** enumera os atributos de perfil considerados como diferenciadores.</span><span class="sxs-lookup"><span data-stu-id="8a041-143">The **Attributes** tab lists profile attributes considered as differentiators.</span></span> <span data-ttu-id="8a041-144">A lapela **Medidas** enumera os diferenciadores.</span><span class="sxs-lookup"><span data-stu-id="8a041-144">The **Measures** tab lists differentiators.</span></span> <span data-ttu-id="8a041-145">Cada lapela inclúe os seguintes detalles:</span><span class="sxs-lookup"><span data-stu-id="8a041-145">Each tab includes the following details:</span></span>

- <span data-ttu-id="8a041-146">Lista clasificada de diferenciadores, ordenada por puntuación de diferenza.</span><span class="sxs-lookup"><span data-stu-id="8a041-146">Ranked list of differentiators, sorted by difference score.</span></span>
- <span data-ttu-id="8a041-147">A **Puntuación de diferenza** para cada diferenciador.</span><span class="sxs-lookup"><span data-stu-id="8a041-147">The **Difference score** for each differentiator.</span></span> <span data-ttu-id="8a041-148">A puntuación de diferenza representa o grao de diferenza dun atributo entre dous segmentos.</span><span class="sxs-lookup"><span data-stu-id="8a041-148">The difference score represents the degree of difference of an attribute between two segments.</span></span> <span data-ttu-id="8a041-149">Canto maior sexa a puntuación de diferenza, máis os atributos difiren entre os dous segmentos.</span><span class="sxs-lookup"><span data-stu-id="8a041-149">The higher the difference score, the more the attributes differ between the two segments.</span></span> <span data-ttu-id="8a041-150">Seleccione unha puntuación para abrir o panel **Puntuación de diferenza** coas distribucións de valores para ese atributo.</span><span class="sxs-lookup"><span data-stu-id="8a041-150">Select a score to open the **Difference score** pane with the distributions of values for that attribute.</span></span>

## <a name="manage-segment-insights"></a><span data-ttu-id="8a041-151">Xestionar a información do segmento</span><span class="sxs-lookup"><span data-stu-id="8a041-151">Manage segment insights</span></span>

<span data-ttu-id="8a041-152">Pode empregar as seguintes opcións nos seus datos desde a barra de comandos:</span><span class="sxs-lookup"><span data-stu-id="8a041-152">You can use the following options on your insights from the command bar:</span></span>

- <span data-ttu-id="8a041-153">**Volver** para volver á lista de informacións</span><span class="sxs-lookup"><span data-stu-id="8a041-153">**Back** to return the list of insights</span></span>
- <span data-ttu-id="8a041-154">**Actualizar** para volver executar a análise</span><span class="sxs-lookup"><span data-stu-id="8a041-154">**Refresh** to run the analysis again</span></span>
- <span data-ttu-id="8a041-155">**Eliminar** para eliminar esta información</span><span class="sxs-lookup"><span data-stu-id="8a041-155">**Delete** to remove this insight</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]