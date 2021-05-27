---
title: Enriquecemento de mellora dos enderezos
description: Enriqueza e normalice a información dos enderezos dos perfís de clientes cos modelos de Microsoft.
ms.date: 04/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 07271d491460764f2c738e760e41c3492f2b6de9
ms.sourcegitcommit: 27f9dd837304ef9fc00f055a6e900fbf6fce1429
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 04/30/2021
ms.locfileid: "5965576"
---
# <a name="enrichment-of-customer-profiles-with-enhanced-addresses"></a><span data-ttu-id="2819d-103">Enriquecemento dos perfís de clientes con enderezos mellorados</span><span class="sxs-lookup"><span data-stu-id="2819d-103">Enrichment of customer profiles with enhanced addresses</span></span>

<span data-ttu-id="2819d-104">Os enderezos dos seus datos poden estar sen estruturar, incompletos ou ser incorrectos.</span><span class="sxs-lookup"><span data-stu-id="2819d-104">Addresses in your data can be unstructured, incomplete, or incorrect.</span></span> <span data-ttu-id="2819d-105">Use os modelos de Microsoft para normalizar e enriquecer os seus enderezos en [formato Common Data Model](/common-data-model/schema/core/applicationcommon/address) para unha mellor precisión e información.</span><span class="sxs-lookup"><span data-stu-id="2819d-105">Use Microsoft's models to normalize and enrich your addresses into the [Common Data Model format](/common-data-model/schema/core/applicationcommon/address) for better accuracy and insights.</span></span>

## <a name="how-we-enhance-addresses"></a><span data-ttu-id="2819d-106">Como melloramos os enderezos</span><span class="sxs-lookup"><span data-stu-id="2819d-106">How we enhance addresses</span></span>

<span data-ttu-id="2819d-107">O noso modelo pasa por un proceso de dous pasos para mellorar un enderezo.</span><span class="sxs-lookup"><span data-stu-id="2819d-107">Our model goes through a two-step process to enhance an address.</span></span> <span data-ttu-id="2819d-108">En primeiro lugar, analiza o enderezo para identificar os seus compoñentes e colócaos nun formato estruturado.</span><span class="sxs-lookup"><span data-stu-id="2819d-108">First, it parses the address to identify its components and puts them into a structured format.</span></span> <span data-ttu-id="2819d-109">Despois, empregamos a intelixencia artificial para corrixir, completar e estandarizar os valores do enderezo.</span><span class="sxs-lookup"><span data-stu-id="2819d-109">Then, we use artificial intelligence to correct, complete, and standardize the values in the address.</span></span>

### <a name="example"></a><span data-ttu-id="2819d-110">Exemplo</span><span class="sxs-lookup"><span data-stu-id="2819d-110">Example</span></span>

<span data-ttu-id="2819d-111">A información dos enderezos pode ter un formato non estándar e conter erros de ortografía.</span><span class="sxs-lookup"><span data-stu-id="2819d-111">Address information might be in a non-standard format and contain spelling errors.</span></span> <span data-ttu-id="2819d-112">O modelo pode solucionar estes problemas e crear enderezos coherentes en perfís de clientes unificados.</span><span class="sxs-lookup"><span data-stu-id="2819d-112">The model can fix these issues and create consistent addresses in unified customer profiles.</span></span>

```Input
4567 w main stret californa missouri 54321 us
```

```Output
- Street1: 4567 W Main St
- City: California
- StateOrProvince: MO
- ZipOrPostalCode: 54321
- CountryOrRegion: United States of America

- Address: 4567 W Main St, California, MO, 54321, United States of America
```

### <a name="limitations"></a><span data-ttu-id="2819d-113">Limitacións</span><span class="sxs-lookup"><span data-stu-id="2819d-113">Limitations</span></span>

<span data-ttu-id="2819d-114">Os enderezos mellorados só funcionan cos valores que xa existen nos seus datos de enderezos inxeridos.</span><span class="sxs-lookup"><span data-stu-id="2819d-114">Enhanced addresses only works with the values that already exist in your ingested address data.</span></span> <span data-ttu-id="2819d-115">O modelo non:</span><span class="sxs-lookup"><span data-stu-id="2819d-115">The model doesn't:</span></span> 

1. <span data-ttu-id="2819d-116">Comproba se o enderezo é válido.</span><span class="sxs-lookup"><span data-stu-id="2819d-116">Verify if the address is a valid address.</span></span>
2. <span data-ttu-id="2819d-117">Comproba se os valores, como os códigos postais ou os nomes de rúas, son válidos.</span><span class="sxs-lookup"><span data-stu-id="2819d-117">Verify if any of the values, such as ZIP codes or street names, are valid.</span></span>
3. <span data-ttu-id="2819d-118">Modifica os valores que non recoñece.</span><span class="sxs-lookup"><span data-stu-id="2819d-118">Change values it doesn't recognize.</span></span>

<span data-ttu-id="2819d-119">O modelo utiliza técnicas baseadas na aprendizaxe automática para mellorar os enderezos.</span><span class="sxs-lookup"><span data-stu-id="2819d-119">The model uses machine learning-based techniques to enhance addresses.</span></span> <span data-ttu-id="2819d-120">Aínda que aplicamos un limiar de confianza elevado para cando o modelo modifica un valor de entrada, como con calquera modelo baseado en aprendizaxe automática, non se garante unha precisión do 100 %.</span><span class="sxs-lookup"><span data-stu-id="2819d-120">While we apply a high confidence threshold for when the model changes an input value, as with any ML-based model, 100% accuracy is not guaranteed.</span></span>

## <a name="supported-countries-or-regions"></a><span data-ttu-id="2819d-121">Países ou rexións admitidos</span><span class="sxs-lookup"><span data-stu-id="2819d-121">Supported countries or regions</span></span>

<span data-ttu-id="2819d-122">Actualmente admitimos enderezos enriquecidos nestes países ou rexións:</span><span class="sxs-lookup"><span data-stu-id="2819d-122">We currently support enriching addresses in these countries or regions:</span></span> 

- <span data-ttu-id="2819d-123">Australia</span><span class="sxs-lookup"><span data-stu-id="2819d-123">Australia</span></span>
- <span data-ttu-id="2819d-124">O Canadá</span><span class="sxs-lookup"><span data-stu-id="2819d-124">Canada</span></span>
- <span data-ttu-id="2819d-125">O Reino Unido</span><span class="sxs-lookup"><span data-stu-id="2819d-125">United Kingdom</span></span>
- <span data-ttu-id="2819d-126">Os Estados Unidos</span><span class="sxs-lookup"><span data-stu-id="2819d-126">United States</span></span>

<span data-ttu-id="2819d-127">Os enderezos deben conter un valor de país ou rexión.</span><span class="sxs-lookup"><span data-stu-id="2819d-127">Addresses must contain a country/region value.</span></span> <span data-ttu-id="2819d-128">Non procesamos enderezos de países ou rexións que non se admitan nin enderezos nos que non se proporcione ningún país ou rexión.</span><span class="sxs-lookup"><span data-stu-id="2819d-128">We don't process addresses for countries or regions that aren't supported and addresses that have no country or region provided.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="2819d-129">Configurar o enriquecemento</span><span class="sxs-lookup"><span data-stu-id="2819d-129">Configure the enrichment</span></span>

1. <span data-ttu-id="2819d-130">Vaia a **Datos** > **Enriquecemento**.</span><span class="sxs-lookup"><span data-stu-id="2819d-130">Go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="2819d-131">Seleccione **Enriquecer os meus datos** no mosaico **Enderezos mellorados**.</span><span class="sxs-lookup"><span data-stu-id="2819d-131">Select **Enrich my data** on the **Enhanced addresses** tile.</span></span>

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="Captura de pantalla do mosaico Enderezos mellorados.":::

1. <span data-ttu-id="2819d-133">Seleccione o **Conxunto de datos do cliente** e escolla a entidade que conteña os enderezos que quere enriquecer.</span><span class="sxs-lookup"><span data-stu-id="2819d-133">Select the **Customer data set** and choose the entity containing the addresses you want to enrich.</span></span> <span data-ttu-id="2819d-134">Pode seleccionar a entidade *Cliente* para enriquecer enderezos en todos os seus perfís de clientes ou seleccionar unha entidade de segmento para enriquecer enderezos só nos perfís de clientes contidos nese segmento.</span><span class="sxs-lookup"><span data-stu-id="2819d-134">You can select the *Customer* entity to enrich addresses in all your customer profiles or select a segment entity to enrich addresses only in customer profiles contained in that segment.</span></span>

1. <span data-ttu-id="2819d-135">Escolla como se formatan os enderezos nos conxuntos de datos.</span><span class="sxs-lookup"><span data-stu-id="2819d-135">Select how addresses are formatted in your data set.</span></span> <span data-ttu-id="2819d-136">Escolla **Enderezo cun único atributo** se os enderezos dos seus datos usan só un campo.</span><span class="sxs-lookup"><span data-stu-id="2819d-136">Choose **Single-attribute address** if addresses in your data use a single field.</span></span> <span data-ttu-id="2819d-137">Escolla **Enderezo con varios atributos** se os enderezos dos seus datos usan máis dun campo de datos.</span><span class="sxs-lookup"><span data-stu-id="2819d-137">Choose **Multiple-attribute address** if addresses in your data use more than one data field.</span></span>

   > [!NOTE]
   > <span data-ttu-id="2819d-138">O país ou rexión é obrigatorio tanto no enderezo cun único atributo como no que ten varios.</span><span class="sxs-lookup"><span data-stu-id="2819d-138">Country/Region is mandatory in both single-attribute and multiple-attribute address.</span></span> <span data-ttu-id="2819d-139">Os enderezos que non conteñan valores de país ou rexión válidos ou admitidos non se enriquecerán</span><span class="sxs-lookup"><span data-stu-id="2819d-139">Addresses that don't contain valid or supported country/region values won't be enriched</span></span>

1.  <span data-ttu-id="2819d-140">Asigne os campos de enderezo da súa entidade de cliente unificada.</span><span class="sxs-lookup"><span data-stu-id="2819d-140">Map the address fields from your unified customer entity.</span></span>

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="Páxina de asignación de campos de enderezos mellorados.":::

1. <span data-ttu-id="2819d-142">Seleccione **Seguinte** para concluír a asignación do campo.</span><span class="sxs-lookup"><span data-stu-id="2819d-142">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="2819d-143">Proporcione un nome para o enriquecemento e a entidade de saída.</span><span class="sxs-lookup"><span data-stu-id="2819d-143">Provide a name for the enrichment and the output entity.</span></span>

1. <span data-ttu-id="2819d-144">Seleccione **Gardar enriquecemento** despois de revisar as súas opcións.</span><span class="sxs-lookup"><span data-stu-id="2819d-144">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="2819d-145">Resultados de enriquecemento</span><span class="sxs-lookup"><span data-stu-id="2819d-145">Enrichment results</span></span>

<span data-ttu-id="2819d-146">Para iniciar o proceso de enriquecemento, seleccione **Executar** na barra de comandos.</span><span class="sxs-lookup"><span data-stu-id="2819d-146">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="2819d-147">Tamén pode deixar que o sistema execute o enriquecemento automaticamente como parte dunha [actualización programada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="2819d-147">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="2819d-148">O tempo de procesamento depende do tamaño dos datos dos clientes.</span><span class="sxs-lookup"><span data-stu-id="2819d-148">The processing time depends on the size of your customer data.</span></span>

<span data-ttu-id="2819d-149">Despois de completar o proceso de enriquecemento, pode consultar os datos dos perfís de clientes recentemente enriquecidos en **Os meus enriquecementos**.</span><span class="sxs-lookup"><span data-stu-id="2819d-149">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="2819d-150">Ademais, atopará a hora da última actualización e o número de perfís enriquecidos.</span><span class="sxs-lookup"><span data-stu-id="2819d-150">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="2819d-151">Pode acceder a unha vista detallada de cada perfil enriquecido seleccionando **Ver datos enriquecidos**.</span><span class="sxs-lookup"><span data-stu-id="2819d-151">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="2819d-152">Pasos seguintes</span><span class="sxs-lookup"><span data-stu-id="2819d-152">Next steps</span></span>

<span data-ttu-id="2819d-153">Crear sobre os seus datos enriquecidos de clientes.</span><span class="sxs-lookup"><span data-stu-id="2819d-153">Build on top of your enriched customer data.</span></span> <span data-ttu-id="2819d-154">Cree [segmentos](segments.md), [medidas](measures.md) e incluso [exporte os datos](export-destinations.md) para ofrecer experiencias personalizadas aos seus clientes.</span><span class="sxs-lookup"><span data-stu-id="2819d-154">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
