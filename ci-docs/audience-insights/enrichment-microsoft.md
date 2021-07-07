---
title: Enriquecer os perfís de clientes con datos de Microsoft
description: Use datos propietarios de Microsoft para enriquecer os seus datos de clientes con afinidades de marcas e intereses.
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 1b11c325649b91ebb47cde924227eacedae64b7a
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305154"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a><span data-ttu-id="e3a20-103">Enriquecer os perfís de clientes con afinidades de marca e intereses (vista previa)</span><span class="sxs-lookup"><span data-stu-id="e3a20-103">Enrich customer profiles with brand and interest affinities (preview)</span></span>

<span data-ttu-id="e3a20-104">Use datos propietarios de Microsoft para enriquecer os seus datos de clientes con afinidades de marcas e intereses.</span><span class="sxs-lookup"><span data-stu-id="e3a20-104">Use Microsoft's proprietary data to enrich your customer data with brand and interest affinities.</span></span> <span data-ttu-id="e3a20-105">Estas afinidades baséanse nos datos de persoas con factores demográficos similares ao dos clientes.</span><span class="sxs-lookup"><span data-stu-id="e3a20-105">These affinities are based on data from people with demographics similar to your customers.</span></span> <span data-ttu-id="e3a20-106">Esta información axúdalle a comprender e segmentar mellor os seus clientes en función das súas afinidades a marcas e intereses específicos.</span><span class="sxs-lookup"><span data-stu-id="e3a20-106">This information helps you to better understand and segment your customers based on their affinities to specific brands and interests.</span></span>

<span data-ttu-id="e3a20-107">Para obter información do público, vaia a **Datos** > **Enriquecemento** para [configurar e ver enriquecementos](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="e3a20-107">In audience insights, go to **Data** > **Enrichment** to [configure and view enrichments](enrichment-hub.md).</span></span>

<span data-ttu-id="e3a20-108">Para configurar o enriquecemento de afinidades de marca, diríxase á pestana **Descubrir** e seleccione **Enriquecer os meus datos** no mosaico **Marcas**.</span><span class="sxs-lookup"><span data-stu-id="e3a20-108">To configure brand affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Brands** tile.</span></span>

<span data-ttu-id="e3a20-109">Para configurar o enriquecemento de afinidades de intereses, diríxase á pestana **Descubrir** e seleccione **Enriquecer os meus datos** no mosaico **Intereses**.</span><span class="sxs-lookup"><span data-stu-id="e3a20-109">To configure interest affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Interests** tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e3a20-110">![Mosaicos de marcas e intereses](media/BrandsInterest-tile-Hub.png "Mosaicos de marcas e intereses")</span><span class="sxs-lookup"><span data-stu-id="e3a20-110">![Brands and Interests tiles](media/BrandsInterest-tile-Hub.png "Brands and Interest tiles")</span></span>

## <a name="how-we-determine-affinities"></a><span data-ttu-id="e3a20-111">Como determinamos as afinidades</span><span class="sxs-lookup"><span data-stu-id="e3a20-111">How we determine affinities</span></span>

<span data-ttu-id="e3a20-112">Usamos os datos de busca en liña de Microsoft para atopar afinidades de marcas e intereses en diversos segmentos demográficos (definidos por idade, sexo ou situación).</span><span class="sxs-lookup"><span data-stu-id="e3a20-112">We use Microsoft’s online search data to find affinities for brands and interests across various demographic segments (defined by age, gender, or location).</span></span> <span data-ttu-id="e3a20-113">O volume de busca en liña dunha marca ou interese determina a cantidade de afinidade que ten un segmento demográfico en comparación con outros segmentos con esa marca ou interese.</span><span class="sxs-lookup"><span data-stu-id="e3a20-113">The online search volume for a brand or interest determines how much affinity a demographic segment, compared to other segments, has to that brand or interest.</span></span>

## <a name="affinity-level-and-score"></a><span data-ttu-id="e3a20-114">Nivel e puntuación de afinidade</span><span class="sxs-lookup"><span data-stu-id="e3a20-114">Affinity level and score</span></span>

<span data-ttu-id="e3a20-115">En cada perfil de cliente enriquecido, fornecemos dous valores relacionados: o nivel de afinidade e a puntuación de afinidade.</span><span class="sxs-lookup"><span data-stu-id="e3a20-115">On every enriched customer profile, we provide two related values: affinity level and affinity score.</span></span> <span data-ttu-id="e3a20-116">Estes valores axúdanlle a determinar o forte que é a afinidade do segmento demográfico dese perfil, por unha marca ou interese, en comparación con outros segmentos demográficos.</span><span class="sxs-lookup"><span data-stu-id="e3a20-116">These values help you determine how strong the affinity is for that profile’s demographic segment, for a brand or interest, as compared to other demographic segments.</span></span>

<span data-ttu-id="e3a20-117">O *nivel de afinidade* consta de catro niveis e a *puntuación de afinidade* calcúlase nunha escala de 100 puntos que se asigna aos niveis de afinidade.</span><span class="sxs-lookup"><span data-stu-id="e3a20-117">*Affinity level* consists of four levels and *affinity score* is calculated on a 100-point scale that maps to the affinity levels.</span></span>


|<span data-ttu-id="e3a20-118">Nivel de afinidade</span><span class="sxs-lookup"><span data-stu-id="e3a20-118">Affinity level</span></span> |<span data-ttu-id="e3a20-119">Puntuación de afinidade</span><span class="sxs-lookup"><span data-stu-id="e3a20-119">Affinity score</span></span>  |
|---------|---------|
|<span data-ttu-id="e3a20-120">Moi alto</span><span class="sxs-lookup"><span data-stu-id="e3a20-120">Very high</span></span>     | <span data-ttu-id="e3a20-121">85-100</span><span class="sxs-lookup"><span data-stu-id="e3a20-121">85-100</span></span>       |
|<span data-ttu-id="e3a20-122">Alto</span><span class="sxs-lookup"><span data-stu-id="e3a20-122">High</span></span>     | <span data-ttu-id="e3a20-123">70-84</span><span class="sxs-lookup"><span data-stu-id="e3a20-123">70-84</span></span>        |
|<span data-ttu-id="e3a20-124">Mediana</span><span class="sxs-lookup"><span data-stu-id="e3a20-124">Medium</span></span>     | <span data-ttu-id="e3a20-125">35-69</span><span class="sxs-lookup"><span data-stu-id="e3a20-125">35-69</span></span>        |
|<span data-ttu-id="e3a20-126">Baixo</span><span class="sxs-lookup"><span data-stu-id="e3a20-126">Low</span></span>     | <span data-ttu-id="e3a20-127">1-34</span><span class="sxs-lookup"><span data-stu-id="e3a20-127">1-34</span></span>        |

<span data-ttu-id="e3a20-128">Dependendo da granularidade que desexe para medir a afinidade, pode usar o nivel de afinidade ou a puntuación.</span><span class="sxs-lookup"><span data-stu-id="e3a20-128">Depending on the granularity you would like for measuring the affinity, you can use either affinity level or score.</span></span> <span data-ttu-id="e3a20-129">A puntuación de afinidade ofrécelle un control máis preciso.</span><span class="sxs-lookup"><span data-stu-id="e3a20-129">Affinity score gives you more precise control.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="e3a20-130">Países ou rexións compatibles</span><span class="sxs-lookup"><span data-stu-id="e3a20-130">Supported countries/regions</span></span>

<span data-ttu-id="e3a20-131">Actualmente son compatibles as seguintes opcións de país ou rexión: Australia, Canadá (inglés), Francia, Alemaña, Reino Unido ou Estados Unidos (inglés).</span><span class="sxs-lookup"><span data-stu-id="e3a20-131">We currently support the following country/region options: Australia, Canada (English), France, Germany, United Kingdom, or United States (English).</span></span>

<span data-ttu-id="e3a20-132">Para seleccionar un país ou rexión, abra **Enriquecemento de marcas** ou **Enriquecemento de intereses** e seleccione **Cambiar** preto de **País/Rexión**.</span><span class="sxs-lookup"><span data-stu-id="e3a20-132">To select a country or region, open **Brands enrichment** or **Interest enrichment** and select **Change** next to **Country/Region**.</span></span> <span data-ttu-id="e3a20-133">No panel **Configuración do país/rexión**, escolla unha opción e seleccione **Solicitar**.</span><span class="sxs-lookup"><span data-stu-id="e3a20-133">In the **Country/Region settings** pane, choose an option and select **Apply**.</span></span>

### <a name="implications-related-to-country-selection"></a><span data-ttu-id="e3a20-134">Implicacións relacionadas coa selección do país</span><span class="sxs-lookup"><span data-stu-id="e3a20-134">Implications related to country selection</span></span>

- <span data-ttu-id="e3a20-135">Cando [escolla as súas propias marcas](#define-your-brands-or-interests), o sistema ofrece suxestións en función do país ou rexión seleccionado.</span><span class="sxs-lookup"><span data-stu-id="e3a20-135">When [choosing your own brands](#define-your-brands-or-interests), the system provides suggestions based on the selected country or region.</span></span>

- <span data-ttu-id="e3a20-136">Cando [escolla unha industria](#define-your-brands-or-interests), obterá as marcas ou intereses máis relevantes en función do país ou rexión seleccionado.</span><span class="sxs-lookup"><span data-stu-id="e3a20-136">When [choosing an industry](#define-your-brands-or-interests), you'll get the most relevant brands or interests based on the selected country or region.</span></span>

- <span data-ttu-id="e3a20-137">Ao [enriquecer perfís](#refresh-enrichment), enriqueceremos todos os perfís de clientes dos que obteñamos datos das marcas e intereses seleccionados, incluídos os perfís que non están no país ou rexión seleccionados.</span><span class="sxs-lookup"><span data-stu-id="e3a20-137">When [enriching profiles](#refresh-enrichment), we'll enrich all customer profiles for which we get data for the selected brands and interests, including profiles that are not in the selected country or region.</span></span> <span data-ttu-id="e3a20-138">Por exemplo, se seleccionou Alemaña, enriqueceremos os perfís situados nos Estados Unidos se temos datos dispoñibles para as marcas e os intereses seleccionados nos Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="e3a20-138">For example, if you selected Germany, we'll enrich profiles located in the United States if we have data available for the selected brands and interests in the US.</span></span>

## <a name="configure-enrichment"></a><span data-ttu-id="e3a20-139">Configurar o enriquecemento</span><span class="sxs-lookup"><span data-stu-id="e3a20-139">Configure enrichment</span></span>

<span data-ttu-id="e3a20-140">Unha experiencia guiada axúdalle a configurar os enriquecementos.</span><span class="sxs-lookup"><span data-stu-id="e3a20-140">A guided experience helps you through the configuration of the enrichments.</span></span> 

### <a name="define-your-brands-or-interests"></a><span data-ttu-id="e3a20-141">Definir as marcas ou os intereses</span><span class="sxs-lookup"><span data-stu-id="e3a20-141">Define your brands or interests</span></span>

<span data-ttu-id="e3a20-142">Escolla ata cinco marcas ou intereses usando unha ou as dúas opcións seguintes:</span><span class="sxs-lookup"><span data-stu-id="e3a20-142">Choose up to five brands or interests using one or both of these options:</span></span>

- <span data-ttu-id="e3a20-143">**Industria**: Seleccione a súa industria na lista despregable e logo escolla entre as mellores marcas ou intereses desa industria.</span><span class="sxs-lookup"><span data-stu-id="e3a20-143">**Industry**: Select your industry from the dropdown list and then choose from the top brands or interests for that industry.</span></span>
- <span data-ttu-id="e3a20-144">**Escoller os seus propios**: insira unha marca ou interese que sexa relevante para a súa organización e logo escolla entre as suxestións coincidentes.</span><span class="sxs-lookup"><span data-stu-id="e3a20-144">**Choose your own**: Enter a brand or interest that is relevant to your organization and then choose from the matching suggestions.</span></span> <span data-ttu-id="e3a20-145">Se non enumeramos unha marca ou interese que está a buscar, envíenos comentarios usando a ligazón **Suxerir**.</span><span class="sxs-lookup"><span data-stu-id="e3a20-145">If we don't list a brand or interest you're looking for, send us feedback using the **Suggest** link.</span></span>

### <a name="review-enrichment-preferences"></a><span data-ttu-id="e3a20-146">Revisar preferencias de enriquecemento</span><span class="sxs-lookup"><span data-stu-id="e3a20-146">Review enrichment preferences</span></span>

<span data-ttu-id="e3a20-147">Revise as súas preferencias de enriquecemento predeterminadas e actualíceas segundo sexa necesario.</span><span class="sxs-lookup"><span data-stu-id="e3a20-147">Review your default enrichment preferences and update them as needed.</span></span>

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Captura de pantalla da xanela de preferencias de enriquecemento.":::

### <a name="select-entity-to-enrich"></a><span data-ttu-id="e3a20-149">Seleccionar entidade para enriquecer</span><span class="sxs-lookup"><span data-stu-id="e3a20-149">Select entity to enrich</span></span>

<span data-ttu-id="e3a20-150">Seleccione **Enriquecer entidade** e escolla o conxunto de datos que quere enriquecer cos datos da empresa de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e3a20-150">Select **Enriched entity** and choose the data set you want to enrich with company data from the Microsoft.</span></span> <span data-ttu-id="e3a20-151">Pode seleccionar a entidade Cliente para enriquecer todos os seus perfís de clientes ou seleccione unha entidade de segmento para enriquecer só os perfís de clientes contidos nese segmento.</span><span class="sxs-lookup"><span data-stu-id="e3a20-151">You can select the Customer entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

### <a name="map-your-fields"></a><span data-ttu-id="e3a20-152">Asignar os campos</span><span class="sxs-lookup"><span data-stu-id="e3a20-152">Map your fields</span></span>

<span data-ttu-id="e3a20-153">Asigne campos da súa entidade cliente unificada para definir o segmento demográfico que desexa que use o sistema para enriquecer os datos dos seus clientes.</span><span class="sxs-lookup"><span data-stu-id="e3a20-153">Map fields from your unified customer entity to define the demographic segment you want the system to use for enriching your customer data.</span></span> <span data-ttu-id="e3a20-154">Asigne o País/Rexión e polo menos os atributos Data de nacemento ou Sexo.</span><span class="sxs-lookup"><span data-stu-id="e3a20-154">Map Country/Region and at least Date of Birth or Gender attributes.</span></span> <span data-ttu-id="e3a20-155">Ademais, debe asignar polo menos un código de cidade (e estado/provincia) ou codigo postal.</span><span class="sxs-lookup"><span data-stu-id="e3a20-155">Additionally, you must map at least one of City (and State/Province) or Postal code.</span></span> <span data-ttu-id="e3a20-156">Seleccione **Editar** definir a asignación dos campos e seleccionar **Aplicar** cando remate.</span><span class="sxs-lookup"><span data-stu-id="e3a20-156">Select **Edit** to define the mapping of the fields and select **Apply** when you're done.</span></span> <span data-ttu-id="e3a20-157">Seleccione **Gardar** para completar a asignación de campos.</span><span class="sxs-lookup"><span data-stu-id="e3a20-157">Select **Save** to complete the field mapping.</span></span>

<span data-ttu-id="e3a20-158">Admítense os seguintes formatos e valores (os valores non diferencian entre maiúsculas e minúsculas):</span><span class="sxs-lookup"><span data-stu-id="e3a20-158">The following formats and values are supported (values are not case-sensitive):</span></span>

- <span data-ttu-id="e3a20-159">**Data de nacemento**: Recomendamos que a data de nacemento sexa convertida ao tipo DateTime durante a inxestión de datos.</span><span class="sxs-lookup"><span data-stu-id="e3a20-159">**Date of Birth**: We recommend that date of birth is converted to DateTime type during data ingestion.</span></span> <span data-ttu-id="e3a20-160">Alternativamente, pode ser unha cadea en [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) formato "aaaa-MM-dd" ou "aaaa-MM-ddTHH:mm:ss".</span><span class="sxs-lookup"><span data-stu-id="e3a20-160">Alternatively, it can be a string in [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) format "yyyy-MM-dd" or "yyyy-MM-ddTHH:mm:ss".</span></span>
- <span data-ttu-id="e3a20-161">**Sexo**: Masculino, Feminino, Descoñecido.</span><span class="sxs-lookup"><span data-stu-id="e3a20-161">**Gender**: Male, Female, Unknown.</span></span>
- <span data-ttu-id="e3a20-162">**Código postal**: Códigos postales de cinco díxitos para Estados Unidos, código postal estándar en calquera outro lugar.</span><span class="sxs-lookup"><span data-stu-id="e3a20-162">**Postal code**: Five-digit ZIP codes for United States, standard postal code everywhere else.</span></span>
- <span data-ttu-id="e3a20-163">**Cidade**: Nome da cidade en inglés.</span><span class="sxs-lookup"><span data-stu-id="e3a20-163">**City**: City name in English.</span></span>
- <span data-ttu-id="e3a20-164">**Estado/Provincia**: Abreviatura de dúas letras para Estados Unidos e Canadá.</span><span class="sxs-lookup"><span data-stu-id="e3a20-164">**State/Province**: Two-letter abbreviation for the US and Canada.</span></span> <span data-ttu-id="e3a20-165">Abreviación de dúas ou tres letras para Australia.</span><span class="sxs-lookup"><span data-stu-id="e3a20-165">Two- or three-letter abbreviation for Australia.</span></span> <span data-ttu-id="e3a20-166">Non se aplica a Francia, Alemaña ou Reino Unido.</span><span class="sxs-lookup"><span data-stu-id="e3a20-166">Not applicable for France, Germany, or the UK.</span></span>
- <span data-ttu-id="e3a20-167">**País/Rexión**:</span><span class="sxs-lookup"><span data-stu-id="e3a20-167">**Country/Region**:</span></span>

  - <span data-ttu-id="e3a20-168">EUA: Estados Unidos de América, Estados Unidos, EE. UU., EUA, EU</span><span class="sxs-lookup"><span data-stu-id="e3a20-168">US: United States of America, United States, USA, US, America</span></span>
  - <span data-ttu-id="e3a20-169">CA: Canadá, CA</span><span class="sxs-lookup"><span data-stu-id="e3a20-169">CA: Canada, CA</span></span>
  - <span data-ttu-id="e3a20-170">RU: Reino Unido, RU, Gran Bretaña, GB, Reino Unido de Gran Bretaña e Irlanda do Norte, Reino Unido de Gran Bretaña</span><span class="sxs-lookup"><span data-stu-id="e3a20-170">GB: United Kingdom, UK, Great Britain, GB, United Kingdom of Great Britain and Northern Ireland, United Kingdom of Great Britain</span></span>
  - <span data-ttu-id="e3a20-171">AU: Australia, AU, Mancomunidade de Australia</span><span class="sxs-lookup"><span data-stu-id="e3a20-171">AU: Australia, AU, Commonwealth of Australia</span></span>
  - <span data-ttu-id="e3a20-172">FR: Francia, FR, República Francesa</span><span class="sxs-lookup"><span data-stu-id="e3a20-172">FR: France, FR, French Republic</span></span>
  - <span data-ttu-id="e3a20-173">DE: Alemaña, Alemán, Deutschland, Allemagne, DE, República Federal de Alemaña, República de Alemaña</span><span class="sxs-lookup"><span data-stu-id="e3a20-173">DE: Germany, German, Deutschland, Allemagne, DE, Federal Republic of Germany, Republic of Germany</span></span>

## <a name="review-and-name-the-enrichment"></a><span data-ttu-id="e3a20-174">Revisar e nomear o enriquecemento</span><span class="sxs-lookup"><span data-stu-id="e3a20-174">Review and name the enrichment</span></span>

<span data-ttu-id="e3a20-175">Finalmente, pode revisar a información e proporcionar un nome para o enriquecemento.</span><span class="sxs-lookup"><span data-stu-id="e3a20-175">Finally, you get to review the information and provide a name for the enrichment.</span></span>

:::image type="content" source="media/enrichment-interests-summary.png" alt-text="Revisión de intereses e nome de páxina.":::

## <a name="refresh-enrichment"></a><span data-ttu-id="e3a20-177">Actualizar o enriquecemento</span><span class="sxs-lookup"><span data-stu-id="e3a20-177">Refresh enrichment</span></span>

<span data-ttu-id="e3a20-178">Execute o enriquecemento despois de configurar marcas, intereses e asignación de campos para os datos demográficos.</span><span class="sxs-lookup"><span data-stu-id="e3a20-178">Run the enrichment after configuring brands, interests, and the field mapping for demographics.</span></span> <span data-ttu-id="e3a20-179">Para iniciar o proceso, seleccione **Executar** na páxina de configuración da marca ou o interese.</span><span class="sxs-lookup"><span data-stu-id="e3a20-179">To start the process, select **Run** on the brand or interest configuration page.</span></span> <span data-ttu-id="e3a20-180">Ademais, pode deixar que o sistema execute o enriquecemento automaticamente como parte dunha actualización programada.</span><span class="sxs-lookup"><span data-stu-id="e3a20-180">Additionally, you can let the system run the enrichment automatically as part of a scheduled refresh.</span></span>

<span data-ttu-id="e3a20-181">Dependendo do tamaño dos datos dos seus clientes, a execución do enriquecemento pode levar uns minutos.</span><span class="sxs-lookup"><span data-stu-id="e3a20-181">Depending on the size of your customer data, it may take several minutes for an enrichment run to complete.</span></span>

> [!TIP]
> <span data-ttu-id="e3a20-182">Existen [seis tipos de estado](system.md#status-types) para as tarefas ou os procesos.</span><span class="sxs-lookup"><span data-stu-id="e3a20-182">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="e3a20-183">Ademais, a maioría dos procesos [dependen doutros procesos descendentes](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="e3a20-183">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="e3a20-184">Pode seleccionar o estado dun proceso para ver detalles sobre o progreso de todo o traballo.</span><span class="sxs-lookup"><span data-stu-id="e3a20-184">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="e3a20-185">Despois de seleccionar **Ver detalles** para unha das tarefas do traballo, atopará información adicional: tempo de procesamento, a última data de procesamento e todos os erros e avisos asociados á tarefa.</span><span class="sxs-lookup"><span data-stu-id="e3a20-185">After selecting **See details** for one of the job's tasks, you'll find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="e3a20-186">Resultados de enriquecemento</span><span class="sxs-lookup"><span data-stu-id="e3a20-186">Enrichment results</span></span>

<span data-ttu-id="e3a20-187">Despois de executar o proceso de enriquecemento, vaia a **Os meus enriquecementos** para revisar o número total de clientes enriquecidos e unha subdivisión de marcas ou intereses nos perfís de clientes enriquecidos.</span><span class="sxs-lookup"><span data-stu-id="e3a20-187">After running the enrichment process, go to **My enrichments** to review the total number of enriched customers and a breakdown of brands or interests in the enriched customer profiles.</span></span>

:::image type="content" source="media/my-enrichments.png" alt-text="Vista previa dos resultados despois de executar o proceso de enriquecemento":::

<span data-ttu-id="e3a20-189">Revise os datos enriquecidos seleccionando **Ver datos enriquecidos** no gráfico.</span><span class="sxs-lookup"><span data-stu-id="e3a20-189">Review the enriched data by selecting **View enriched data** in the chart.</span></span> <span data-ttu-id="e3a20-190">Os datos enriquecidos para as marcas van á entidade **BrandAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="e3a20-190">Enriched data for brands goes to the **BrandAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="e3a20-191">Datos para intereses na entidade **InterestAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="e3a20-191">Data for interests is in the **InterestAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="e3a20-192">Tamén atopará estas entidades enumeradas no grupo **Enriquecemento** en **Datos** > **Entidades**.</span><span class="sxs-lookup"><span data-stu-id="e3a20-192">You'll also find these entities listed in the **Enrichment** group in **Data** > **Entities**.</span></span>

## <a name="see-enrichment-data-on-the-customer-card"></a><span data-ttu-id="e3a20-193">Vexa datos de enriquecemento na tarxeta de cliente</span><span class="sxs-lookup"><span data-stu-id="e3a20-193">See enrichment data on the customer card</span></span>

<span data-ttu-id="e3a20-194">As afinidades de marca e interese tamén se poden ver nas tarxetas de clientes individuais.</span><span class="sxs-lookup"><span data-stu-id="e3a20-194">Brand and interest affinities can also be viewed on individual customer cards.</span></span> <span data-ttu-id="e3a20-195">Vaia a **Clientes** e seleccione un perfil de cliente.</span><span class="sxs-lookup"><span data-stu-id="e3a20-195">Go to **Customers** and select a customer profile.</span></span> <span data-ttu-id="e3a20-196">Na tarxeta de cliente atopará gráficos das marcas ou intereses polos que teñen afinidade os usuarios do perfil demográfico dese cliente.</span><span class="sxs-lookup"><span data-stu-id="e3a20-196">In the customer card, you'll find charts for the brands or interests that people in that customer's demographic profile have affinity for.</span></span>

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Tarxeta de cliente con datos enriquecidos":::

## <a name="next-steps"></a><span data-ttu-id="e3a20-198">Seguintes pasos</span><span class="sxs-lookup"><span data-stu-id="e3a20-198">Next steps</span></span>

<span data-ttu-id="e3a20-199">Crear sobre os seus datos enriquecidos de clientes.</span><span class="sxs-lookup"><span data-stu-id="e3a20-199">Build on top of your enriched customer data.</span></span> <span data-ttu-id="e3a20-200">Cree [Segmentos](segments.md) e [Medidas](measures.md), e incluso [exporte os datos](export-destinations.md) para ofrecer experiencias personalizadas aos seus clientes.</span><span class="sxs-lookup"><span data-stu-id="e3a20-200">Create [Segments](segments.md) and [Measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
