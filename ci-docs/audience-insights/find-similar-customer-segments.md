---
title: Buscar clientes semellantes con IA
description: Atope segmentos de clientes similares con intelixencia artificial.
ms.date: 06/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: f588f45ed11efffbb335003642a4b92810153017
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596773"
---
# <a name="similar-customers-preview"></a><span data-ttu-id="6be75-103">Clientes similares (vista previa)</span><span class="sxs-lookup"><span data-stu-id="6be75-103">Similar Customers (preview)</span></span>

<span data-ttu-id="6be75-104">Esta característica permítelle atopar clientes similares na súa base de clientes mediante intelixencia artificial.</span><span class="sxs-lookup"><span data-stu-id="6be75-104">This feature lets you find similar customers in your customer base using artificial intelligence.</span></span> <span data-ttu-id="6be75-105">Debe ter polo menos un segmento creado para usar esta función.</span><span class="sxs-lookup"><span data-stu-id="6be75-105">You need to have at least one segment created to use this feature.</span></span> <span data-ttu-id="6be75-106">A expansión dos criterios dun segmento existente axuda a atopar clientes similares a ese segmento.</span><span class="sxs-lookup"><span data-stu-id="6be75-106">Expanding the criteria of an existing segment help find customers that are similar to that segment.</span></span>

> [!NOTE]
> <span data-ttu-id="6be75-107">*Buscar clientes similares* usa medios automatizados para avaliar datos e facer predicións a partir deses datos e, polo tanto, ten a capacidade de ser utilizado como método de avaliación de perfís, xa que ese termo é definido polo Regulamento xeral de protección de datos ("RXPD").</span><span class="sxs-lookup"><span data-stu-id="6be75-107">*Find similar customers* uses automated means to evaluate data and make predictions based on that data, and therefore has the capability to be used as a method of profiling, as that term is defined by the General Data Protection Regulation (“GDPR”).</span></span> <span data-ttu-id="6be75-108">O uso desta función para o procesamento de datos por parte do cliente pode estar suxeito a RXPD ou a outras leis ou regulamentos.</span><span class="sxs-lookup"><span data-stu-id="6be75-108">Customer’s use of this feature to process data may be subject to GDPR or other laws or regulations.</span></span> <span data-ttu-id="6be75-109">Vostede é responsable de garantir que o seu uso de Dynamics 365 Customer Insights, incluíndo as predicións, cumpre con todas as leis e regulamentos aplicables, incluídas as leis relacionadas coa privacidade, os datos persoais, os datos biométricos, a protección de datos e a confidencialidade das comunicacións.</span><span class="sxs-lookup"><span data-stu-id="6be75-109">You are responsible for ensuring that your use of Dynamics 365 Customer Insights, including predictions, complies with all applicable laws and regulations, including laws related to privacy, personal data, biometric data, data protection, and confidentiality of communications.</span></span>

## <a name="finding-similar-customers"></a><span data-ttu-id="6be75-110">Busca de clientes similares</span><span class="sxs-lookup"><span data-stu-id="6be75-110">Finding similar customers</span></span>

1. <span data-ttu-id="6be75-111">Na información do público, vaia a **Segmentos** e seleccione o segmento no que desexa basear o seu novo segmento.</span><span class="sxs-lookup"><span data-stu-id="6be75-111">In audience insights, go to **Segments** and select the segment you want to base your new segment on.</span></span> <span data-ttu-id="6be75-112">Ese é o seu *segmento de orixe*.</span><span class="sxs-lookup"><span data-stu-id="6be75-112">That's your *source segment*.</span></span>

1. <span data-ttu-id="6be75-113">Na barra de acción, seleccione **Buscar clientes similares**.</span><span class="sxs-lookup"><span data-stu-id="6be75-113">In the action bar, select **Find similar customers**.</span></span>

1. <span data-ttu-id="6be75-114">Revise o nome suxerido para o seu novo segmento e cámbieo se é necesario.</span><span class="sxs-lookup"><span data-stu-id="6be75-114">Review the suggested name for your new segment and change it if necessary.</span></span>

1. <span data-ttu-id="6be75-115">Revise os campos que definen o seu novo segmento.</span><span class="sxs-lookup"><span data-stu-id="6be75-115">Review the fields that define your new segment.</span></span> <span data-ttu-id="6be75-116">Estes campos definen a base sobre a que o sistema tratará de atopar clientes similares ao seu segmento de orixe.</span><span class="sxs-lookup"><span data-stu-id="6be75-116">These fields define the basis on which the system will try to find similar customers to your source segment.</span></span> <span data-ttu-id="6be75-117">O sistema seleccionará de xeito predeterminado os campos recomendados.</span><span class="sxs-lookup"><span data-stu-id="6be75-117">The system will select recommended fields by default.</span></span>
  <span data-ttu-id="6be75-118">Os campos que poden reducir significativamente o rendemento do modelo quedan automaticamente excluídos:</span><span class="sxs-lookup"><span data-stu-id="6be75-118">Fields that can significantly reduce the model performance are automatically excluded:</span></span>
  
   - <span data-ttu-id="6be75-119">Campos cos seguintes tipos de datos: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType</span><span class="sxs-lookup"><span data-stu-id="6be75-119">Fields with the following data types: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType</span></span>
   - <span data-ttu-id="6be75-120">Campos cunha cardinalidade (o número de elementos dun campo) de menos de 2 ou máis de 30</span><span class="sxs-lookup"><span data-stu-id="6be75-120">Fields with a cardinality (the number of elements in a field) of less than 2 or more than 30</span></span>

1. <span data-ttu-id="6be75-121">Elixa se quere incluír **Todos os clientes** ou só clientes nun **Segmento existente específico** no seu novo segmento.</span><span class="sxs-lookup"><span data-stu-id="6be75-121">Choose if you want to include **All customers** or only customers in a **Specific existing segment** in your new segment.</span></span>

1. <span data-ttu-id="6be75-122">Exclúa os clientes do seu segmento de orixe seleccionando a caixa de verificación **Excluír a todos no segmento de orixe**.</span><span class="sxs-lookup"><span data-stu-id="6be75-122">Exclude customers in your source segment by selecting the **Exclude everyone in source segment** checkbox.</span></span>

1. <span data-ttu-id="6be75-123">De xeito predeterminado, o sistema suxire incluír só o 20 % do tamaño do público obxectivo nos seus resultados.</span><span class="sxs-lookup"><span data-stu-id="6be75-123">By default, the system suggests including only 20% of the target audience size in your output.</span></span> <span data-ttu-id="6be75-124">Edite este limiar segundo sexa necesario.</span><span class="sxs-lookup"><span data-stu-id="6be75-124">Edit this threshold as needed.</span></span> <span data-ttu-id="6be75-125">Aumentar o limiar reducirá a precisión.</span><span class="sxs-lookup"><span data-stu-id="6be75-125">Increasing the threshold will reduce the precision.</span></span>

1. <span data-ttu-id="6be75-126">Seleccione **Executar** ao final da páxina para iniciar unha tarefa de clasificación binaria (un método de aprendizaxe automática) que analiza o conxunto de datos.</span><span class="sxs-lookup"><span data-stu-id="6be75-126">Select **Run** at the bottom of the page to start a binary classification task (a method of machine learning) which analyzes the dataset.</span></span>

## <a name="view-the-similar-segment"></a><span data-ttu-id="6be75-127">Ver o segmento similar</span><span class="sxs-lookup"><span data-stu-id="6be75-127">View the similar segment</span></span>

<span data-ttu-id="6be75-128">Despois de procesar o segmento similar, atopará o novo segmento listado na páxina **Segmentos**.</span><span class="sxs-lookup"><span data-stu-id="6be75-128">After processing the similar segment, you'll find the new segment listed on the **Segments** page.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="6be75-129">![Segmento de clientes similar](media/expanded-segment.png "Segmento de clientes similar")</span><span class="sxs-lookup"><span data-stu-id="6be75-129">![Similar customers segment](media/expanded-segment.png "Similar customers segment")</span></span>

<span data-ttu-id="6be75-130">Seleccione **Ver** na barra de accións para abrir o detalle do segmento.</span><span class="sxs-lookup"><span data-stu-id="6be75-130">Select **View** in the action bar to open the segment detail.</span></span> <span data-ttu-id="6be75-131">Esta vista contén información sobre a distribución dos resultados en [puntuacións de semellanza](#about-similarity-scores).</span><span class="sxs-lookup"><span data-stu-id="6be75-131">This view contains information about the result distribution across [similarity scores](#about-similarity-scores).</span></span> <span data-ttu-id="6be75-132">Tamén atopará os valores de puntuación de semellanza na **Vista previa dos membros do segmento**.</span><span class="sxs-lookup"><span data-stu-id="6be75-132">You'll also find the similarity score values in the **Segment members preview**.</span></span>

## <a name="use-the-output-of-a-similar-segment"></a><span data-ttu-id="6be75-133">Usar os resultados dun segmento similar</span><span class="sxs-lookup"><span data-stu-id="6be75-133">Use the output of a similar segment</span></span>

<span data-ttu-id="6be75-134">Pode [traballar cos resultados dun segmento similar](segments.md) como fai con outros segmentos.</span><span class="sxs-lookup"><span data-stu-id="6be75-134">You can [work with the output of a similar segment](segments.md) as you do with other segments.</span></span> <span data-ttu-id="6be75-135">Por exemplo, exporte o segmento ou cree unha medida.</span><span class="sxs-lookup"><span data-stu-id="6be75-135">For example, export the segment or build a measure.</span></span>

## <a name="refresh-and-edit-a-similar-segment"></a><span data-ttu-id="6be75-136">Actualizar e editar un segmento similar</span><span class="sxs-lookup"><span data-stu-id="6be75-136">Refresh and edit a similar segment</span></span>

<span data-ttu-id="6be75-137">Para actualizar un segmento similar, seleccióneo na páxina **Segmentos** e seleccione **Actualizar** na barra de accións.</span><span class="sxs-lookup"><span data-stu-id="6be75-137">To refresh a similar segment, select it on the **Segments** page and select **Refresh** in the action bar.</span></span>

<span data-ttu-id="6be75-138">A edición dun segmento similar reprocesará os seus datos.</span><span class="sxs-lookup"><span data-stu-id="6be75-138">Editing a similar segment will reprocess your data.</span></span> <span data-ttu-id="6be75-139">O segmento creado anteriormente actualízase con datos actualizados.</span><span class="sxs-lookup"><span data-stu-id="6be75-139">The previously created segment gets updated with refreshed data.</span></span>    
<span data-ttu-id="6be75-140">Para editar un segmento similar, seleccióneo na páxina **Segmentos** e seleccione **Editar** na barra de accións.</span><span class="sxs-lookup"><span data-stu-id="6be75-140">To edit a similar segment, select it on the **Segments** page and select **Edit** in the action bar.</span></span> <span data-ttu-id="6be75-141">Aplique os cambios e seleccione **Executar** para iniciar a tramitación.</span><span class="sxs-lookup"><span data-stu-id="6be75-141">Apply your changes and select **Run** to start the processing.</span></span>

## <a name="delete-a-similar-segment"></a><span data-ttu-id="6be75-142">Eliminar un segmento similar</span><span class="sxs-lookup"><span data-stu-id="6be75-142">Delete a similar segment</span></span>

<span data-ttu-id="6be75-143">Seleccione o segmento na páxina **Segmentos** e seleccione **Eliminar** na barra de accións.</span><span class="sxs-lookup"><span data-stu-id="6be75-143">Select the segment on the **Segments** page and select **Delete** in the action bar.</span></span> <span data-ttu-id="6be75-144">Logo confirme a eliminación.</span><span class="sxs-lookup"><span data-stu-id="6be75-144">Then, confirm your deletion.</span></span>

## <a name="about-similarity-scores"></a><span data-ttu-id="6be75-145">Acerca das puntuacións de semellanza</span><span class="sxs-lookup"><span data-stu-id="6be75-145">About similarity scores</span></span>

<span data-ttu-id="6be75-146">O modelo de aprendizaxe automática de clasificación binaria asigna unha puntuación aos clientes do segmento similar.</span><span class="sxs-lookup"><span data-stu-id="6be75-146">The binary classification machine learning model assigns a score to customers in the similar segment.</span></span> <span data-ttu-id="6be75-147">A puntuación baséase na semellanza con clientes do segmento de orixe.</span><span class="sxs-lookup"><span data-stu-id="6be75-147">The score is based on the similarity to customers in the source segment.</span></span>

- <span data-ttu-id="6be75-148">Os resultados de semellanza por baixo de 0,55 son os clientes que o sistema clasificou como *non semellante* aos clientes do segmento de orixe</span><span class="sxs-lookup"><span data-stu-id="6be75-148">Similarity scores below 0.55 are customers the system classified as *not similar* to customers in the source segment</span></span>
- <span data-ttu-id="6be75-149">As puntuacións de semellanza entre 0,55 e 0,7 clasifícanse como *algo semellante*</span><span class="sxs-lookup"><span data-stu-id="6be75-149">Similarity scores between 0.55 – 0.7 are classified as *somewhat similar*</span></span>
- <span data-ttu-id="6be75-150">As puntuacións de semellanza entre 0,7 e 0,85 clasifícanse como *semellante*</span><span class="sxs-lookup"><span data-stu-id="6be75-150">Similarity scores between 0.7 – 0.85 are classified as *similar*</span></span>
- <span data-ttu-id="6be75-151">As puntuacións de semellanza entre 0,85 e 1 son clientes que o sistema clasificou como *moi semellante*</span><span class="sxs-lookup"><span data-stu-id="6be75-151">Similarity scores between 0.85 – 1 are customers the system classified as *very similar*</span></span>

<span data-ttu-id="6be75-152">Os clientes con puntuacións de semellanza inferiores a 0,4 non se inclúen nos resultados do modelo.</span><span class="sxs-lookup"><span data-stu-id="6be75-152">Customers with similarity scores below 0.4 aren't included in the model output.</span></span> <span data-ttu-id="6be75-153">O sistema non os considera suficientemente semellantes ao segmento de orixe.</span><span class="sxs-lookup"><span data-stu-id="6be75-153">The system doesn't consider them similar enough to the source segment.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]