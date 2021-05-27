---
title: Segmentos suxeridos baseados na actividade.
description: Permita que a aprendizaxe automática lle axude a atopar segmentos novos e interesantes baseados na actividade dos clientes.
ms.date: 05/11/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
ms.openlocfilehash: 14d9d4f0df6b5835f21fb63447d05853ee98a757
ms.sourcegitcommit: 8341fa964365c185b65bc4b71fc0c695ea127dc0
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 05/14/2021
ms.locfileid: "6034071"
---
# <a name="suggested-segments-based-on-activity-data-preview"></a><span data-ttu-id="99f5a-103">Segmentos suxeridos baseados nos datos de actividade (visión preliminar)</span><span class="sxs-lookup"><span data-stu-id="99f5a-103">Suggested segments based on activity data (preview)</span></span>

<span data-ttu-id="99f5a-104">Descubra segmentos interesantes dos seus clientes baseados nos datos da súa actividade que se inxiren en Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="99f5a-104">Discover interesting segments of your customers based on customer activity data that is ingested to Customer Insights.</span></span> <span data-ttu-id="99f5a-105">Exemplos de datos de actividade son as transaccións, a duración das chamadas de asistencia técnica, as compras ou as devolucións.</span><span class="sxs-lookup"><span data-stu-id="99f5a-105">Examples of activity data are transactions, support call duration, purchases, or returns.</span></span> <span data-ttu-id="99f5a-106">Para suxerir segmentos, os datos de actividade analízanse por actualidade, frecuencia e valor monetario (ou duración).</span><span class="sxs-lookup"><span data-stu-id="99f5a-106">To suggest segments, activity data gets analyzed for recency, frequency, and monetary value (or duration).</span></span> <span data-ttu-id="99f5a-107">Como alternativa, pode xerar [segmentos suxeridos para mellorar unha medida ou comprender mellor o que inflúe nun atributo](suggested-segments.md).</span><span class="sxs-lookup"><span data-stu-id="99f5a-107">Alternatively, you can generate [suggested segments to improve a measure or better understand what influences an attribute](suggested-segments.md).</span></span>

:::image type="content" source="media/suggested-segments-tab.png" alt-text="Separador de segmentos suxeridos que mostra suxestións de segmentos para segmentos baseados na actividade e nos atributos.":::

## <a name="categorize-customers-by-activity"></a><span data-ttu-id="99f5a-109">Categorizar os clientes por actividade</span><span class="sxs-lookup"><span data-stu-id="99f5a-109">Categorize customers by activity</span></span>

<span data-ttu-id="99f5a-110">Cos [datos de actividade](activities.md) dispoñibles en Customer Insights, podemos xerar suxestións que representen grupos de clientes:</span><span class="sxs-lookup"><span data-stu-id="99f5a-110">With [activity data](activities.md) available in Customer Insights, we can generate suggestions that represent customer groups:</span></span>

- <span data-ttu-id="99f5a-111">clientes máis activos</span><span class="sxs-lookup"><span data-stu-id="99f5a-111">most active customers</span></span> 
- <span data-ttu-id="99f5a-112">clientes que máis compras fixeron</span><span class="sxs-lookup"><span data-stu-id="99f5a-112">customers that have made the most purchases</span></span> 
- <span data-ttu-id="99f5a-113">clientes que máis ingresos xeraron</span><span class="sxs-lookup"><span data-stu-id="99f5a-113">customers that generated the most revenue</span></span> 
- <span data-ttu-id="99f5a-114">clientes que non estiveron activos ultimamente</span><span class="sxs-lookup"><span data-stu-id="99f5a-114">customers who haven’t been active lately</span></span> 
- <span data-ttu-id="99f5a-115">clientes que interactúan frecuentemente coa súa empresa</span><span class="sxs-lookup"><span data-stu-id="99f5a-115">customers who frequently interact with your business</span></span>  

<span data-ttu-id="99f5a-116">Se ten unha empresa minorista, pode descubrir cales son os clientes que máis ingresos xeran e recompensalos cun cupón.</span><span class="sxs-lookup"><span data-stu-id="99f5a-116">If you have a retail business, you could find out which customers generate the most revenue and reward them with a coupon.</span></span> <span data-ttu-id="99f5a-117">Tamén pode identificar os clientes ocasionais e ofrecerlles unirse a un programa de recompensas para que visiten a súa empresa con máis frecuencia.</span><span class="sxs-lookup"><span data-stu-id="99f5a-117">Or you can identify occasional customers and offer them to join a rewards program so they visit your business more often.</span></span>
<span data-ttu-id="99f5a-118">Traballa no sector sanitario, ofrece asistencia sanitaria pública e o seu obxectivo é minimizar os gastos dos pacientes individuais.</span><span class="sxs-lookup"><span data-stu-id="99f5a-118">If you're in the healthcare business providing public healthcare and your goal is to minimize the expenses for individual patients.</span></span> <span data-ttu-id="99f5a-119">Un xeito de facelo podería ser mediante a redución das visitas periódicas, proporcionando a mellor atención posible no menor número de visitas posible.</span><span class="sxs-lookup"><span data-stu-id="99f5a-119">A way to do so could be to reduce recurring visits by providing best possible care in as few visits as possible.</span></span> <span data-ttu-id="99f5a-120">Neste caso, o seu obxectivo é manter baixa a frecuencia de visita e minimizar os custos periódicos para os pacientes.</span><span class="sxs-lookup"><span data-stu-id="99f5a-120">In this case, your goal is to keep the visit frequency low and minimize recurring cost for the patients.</span></span> <span data-ttu-id="99f5a-121">Tamén pode identificar segmentos de pacientes que teñen compromisos frecuentes e elevados custos periódicos e analizar eses casos para mellorar o seu tratamento.</span><span class="sxs-lookup"><span data-stu-id="99f5a-121">Or you can identify segments of patients who have frequent appointments and high recurring costs and analyze these cases to improve the treatment of the individual.</span></span> 

## <a name="required-data"></a><span data-ttu-id="99f5a-122">Datos necesarios</span><span class="sxs-lookup"><span data-stu-id="99f5a-122">Required data</span></span>

<span data-ttu-id="99f5a-123">As suxestións xéranse en función dos datos de entrada seleccionados.</span><span class="sxs-lookup"><span data-stu-id="99f5a-123">Suggestions are generated based on the selected input data.</span></span> 

- <span data-ttu-id="99f5a-124">Perfís de clientes: todos os clientes ou membros dun segmento específico.</span><span class="sxs-lookup"><span data-stu-id="99f5a-124">Customer profiles: All customers or members of a specific segment.</span></span> 

- <span data-ttu-id="99f5a-125">Período de tempo: o mes pasado, o ano pasado ou calquera intervalo temporal personalizado.</span><span class="sxs-lookup"><span data-stu-id="99f5a-125">Time period: Last month, last year, or any custom time frame.</span></span>

- <span data-ttu-id="99f5a-126">Tipo de actividade: compras, transaccións minoristas, transaccións en liña, casos de asistencia técnica, subscricións etc.</span><span class="sxs-lookup"><span data-stu-id="99f5a-126">Activity type: purchases, retail transactions, online transactions, customer support cases, subscriptions, and so on.</span></span>  

- <span data-ttu-id="99f5a-127">A entidade de Customer Insights que contén os datos da actividade: a entidade UnifiedActivity ou a entidade para unha actividade específica.</span><span class="sxs-lookup"><span data-stu-id="99f5a-127">Entity in Customer Insights that contains the activity data: The UnifiedActivity entity or the entity for a specific activity.</span></span> 

- <span data-ttu-id="99f5a-128">Dimensións que se inclúen: actualidade, frecuencia ou dimensión monetaria, dependendo das necesidades da súa empresa.</span><span class="sxs-lookup"><span data-stu-id="99f5a-128">Dimensions to include: Recency, frequency, or monetary dimension, depending on your business requirements.</span></span>

## <a name="generate-suggested-segments"></a><span data-ttu-id="99f5a-129">Xerar segmentos suxeridos</span><span class="sxs-lookup"><span data-stu-id="99f5a-129">Generate suggested segments</span></span>

1. <span data-ttu-id="99f5a-130">Vaia a **Segmentos**.</span><span class="sxs-lookup"><span data-stu-id="99f5a-130">Go to **Segments**.</span></span>

1. <span data-ttu-id="99f5a-131">Seleccione o separador **Suxestións (versión preliminar)**.</span><span class="sxs-lookup"><span data-stu-id="99f5a-131">Select the **Suggestions (preview)** tab.</span></span>

1. <span data-ttu-id="99f5a-132">Seleccione **Buscar novas suxestións** e elixa **Ver ou anticipar o comportamento do cliente**.</span><span class="sxs-lookup"><span data-stu-id="99f5a-132">Select **Find new suggestions** and choose **See or anticipate customer behavior**.</span></span> <span data-ttu-id="99f5a-133">Seleccione **Iniciar** para executar a experiencia guiada.</span><span class="sxs-lookup"><span data-stu-id="99f5a-133">Select **Start** to run the guided experience.</span></span>

   :::image type="content" source="media/suggested-segments-activity-wizard.png" alt-text="Primeiro paso do asistente de configuración para un segmento suxerido baseado na actividade.":::

1. <span data-ttu-id="99f5a-135">Proporcione os datos de entrada necesarios e seleccione **Seguinte** para continuar.</span><span class="sxs-lookup"><span data-stu-id="99f5a-135">Provide the required input data and select **Next** proceed.</span></span>

   - <span data-ttu-id="99f5a-136">Elección de clientes: inclúa todos os clientes ou un segmento específico.</span><span class="sxs-lookup"><span data-stu-id="99f5a-136">Choose customers: Include all customers or a specific segment.</span></span>
   - <span data-ttu-id="99f5a-137">Elección de actividade: seleccione o tipo de actividade e as entidades que a describen.</span><span class="sxs-lookup"><span data-stu-id="99f5a-137">Choose activity: Select the activity type and the entities that describe the activity.</span></span>
   - <span data-ttu-id="99f5a-138">Preferencias: defina o período de tempo que se considerará, os factores para as suxestións e asigne os atributos.</span><span class="sxs-lookup"><span data-stu-id="99f5a-138">Preferences: Set the time period to consider, the factors for suggestions, and map the attributes.</span></span>

1. <span data-ttu-id="99f5a-139">Revise a entrada e seleccione **Executar** para executar o modelo e xerar suxestións.</span><span class="sxs-lookup"><span data-stu-id="99f5a-139">Review your input and select **Run** to run the model and generate suggestions.</span></span>

1. <span data-ttu-id="99f5a-140">En función do número de perfís de clientes e das actividades seleccionadas, pode tardar uns minutos en completarse.</span><span class="sxs-lookup"><span data-stu-id="99f5a-140">Depending on the number of customer profiles and selected activities, it can take a few minutes to complete.</span></span> 

<span data-ttu-id="99f5a-141">Despois de xerar as suxestións, pode filtralas pola dimensión ou o valor que máis lle interese.</span><span class="sxs-lookup"><span data-stu-id="99f5a-141">After generating the suggestions, you can filter them by the dimension or value you're most interested in.</span></span> 

## <a name="view-details-of-a-suggested-segment"></a><span data-ttu-id="99f5a-142">Ver detalles dun segmento suxerido</span><span class="sxs-lookup"><span data-stu-id="99f5a-142">View details of a suggested segment</span></span>

<span data-ttu-id="99f5a-143">Unha vez que se xeran as suxestións, atoparaas na lista **Segmentos** > **Suxestións (versión preliminar)** na sección **Suxestións baseadas na actividade**.</span><span class="sxs-lookup"><span data-stu-id="99f5a-143">Once the suggestions are generated, you'll find them listed on **Segments** > **Suggestions (preview)** in the **Activity-based suggestions** section.</span></span>

:::image type="content" source="media/suggested-segments-details.png" alt-text="Panel lateral expandido que mostra os datos detallados dun segmento suxerido.":::

<span data-ttu-id="99f5a-145">Seleccione **Visualizar suxestión** nun segmento suxerido para ver os detalles dese segmento.</span><span class="sxs-lookup"><span data-stu-id="99f5a-145">Select **See suggestion** on a suggested segment to view the details of that segment.</span></span> <span data-ttu-id="99f5a-146">O panel lateral ofrece detalles como a extensión de cada dimensión en comparación co grupo de destino.</span><span class="sxs-lookup"><span data-stu-id="99f5a-146">The side pane provides details like the extent of each dimension in comparison to the target group.</span></span> <span data-ttu-id="99f5a-147">Tamén destaca o número de membros potenciais no segmento e a porcentaxe correspondente do total de clientes.</span><span class="sxs-lookup"><span data-stu-id="99f5a-147">It also highlights the number of potential members in the segment and the corresponding percentage of the total customers.</span></span> <span data-ttu-id="99f5a-148">Se quere manter a suxestión como un segmento, seleccione **Crear segmento**.</span><span class="sxs-lookup"><span data-stu-id="99f5a-148">If you want to keep the suggestion as a segment, select **Create segment**.</span></span>    

## <a name="save-a-suggestion-as-a-segment"></a><span data-ttu-id="99f5a-149">Gardar unha suxestión como segmento</span><span class="sxs-lookup"><span data-stu-id="99f5a-149">Save a suggestion as a segment</span></span>

1. <span data-ttu-id="99f5a-150">Vaia a **Segmentos** > **Suxestións (versión preliminar)**.</span><span class="sxs-lookup"><span data-stu-id="99f5a-150">Go to **Segments** > **Suggestions (preview)**.</span></span>

1. <span data-ttu-id="99f5a-151">Seleccione o segmento que quere gardar.</span><span class="sxs-lookup"><span data-stu-id="99f5a-151">Select the segment you want to save.</span></span> 

1. <span data-ttu-id="99f5a-152">No panel lateral, seleccione **Crear segmento**.</span><span class="sxs-lookup"><span data-stu-id="99f5a-152">In the side pane, select **Create segment**.</span></span> 

1. <span data-ttu-id="99f5a-153">Despois de gardar o segmento, mostrarase na lista de segmentos do separador **Todos os segmentos**. Agora pode [actualizarse ou eliminarse como calquera outro segmento](segments.md).</span><span class="sxs-lookup"><span data-stu-id="99f5a-153">After saving the segment, it will show in the list of segments on the **All segments** tab. It can now be [refreshed or deleted like any other segment](segments.md).</span></span> <span data-ttu-id="99f5a-154">Non pode editar os detalles do segmento.</span><span class="sxs-lookup"><span data-stu-id="99f5a-154">You can't edit the segment details.</span></span> <span data-ttu-id="99f5a-155">Non obstante, pode modificar os criterios de entrada das suxestións e xerar diferentes suxestións.</span><span class="sxs-lookup"><span data-stu-id="99f5a-155">However, you can change the input criteria for the suggestions and generate different suggestions.</span></span>

## <a name="refresh-or-edit-a-set-of-suggestions"></a><span data-ttu-id="99f5a-156">Actualizar ou editar un conxunto de suxestións</span><span class="sxs-lookup"><span data-stu-id="99f5a-156">Refresh or edit a set of suggestions</span></span>

1. <span data-ttu-id="99f5a-157">Vaia a **Segmentos** > **Suxestións (versión preliminar)** e busque o segmento na sección **Suxestións baseadas na actividade**.</span><span class="sxs-lookup"><span data-stu-id="99f5a-157">Go to **Segments** > **Suggestions (preview)** and look for the segment in the **Activity-based suggestions** section.</span></span>

1. <span data-ttu-id="99f5a-158">Seleccione **Actualizar suxestións** para actualizar as suxestións mantendo os atributos configurados.</span><span class="sxs-lookup"><span data-stu-id="99f5a-158">Select **Refresh suggestions** to refresh the suggestions while keeping configured attributes.</span></span> <span data-ttu-id="99f5a-159">Tamén pode seleccionar **Editar suxestións** para modificar os atributos configurados.</span><span class="sxs-lookup"><span data-stu-id="99f5a-159">Or select **Edit suggestions** to modify the configured attributes.</span></span> <span data-ttu-id="99f5a-160">O sistema volverá executar o proceso, xerará suxestións de segmentos baseadas nos últimos datos e substituirá as suxestións actuais.</span><span class="sxs-lookup"><span data-stu-id="99f5a-160">The system will rerun the process, generate segment suggestions based on the latest data, and replace the current suggestions.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
