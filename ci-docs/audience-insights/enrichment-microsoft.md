---
title: Enriquecer os perfís de clientes con datos de Microsoft
description: Use datos propietarios de Microsoft para enriquecer os seus datos de clientes con afinidades de marcas e intereses.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 6f19033236190547f68d2b91ec6b32074bf7912a
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896600"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a><span data-ttu-id="6cbd2-103">Enriquecer os perfís de clientes con afinidades de marca e intereses (vista previa)</span><span class="sxs-lookup"><span data-stu-id="6cbd2-103">Enrich customer profiles with brand and interest affinities (preview)</span></span>

<span data-ttu-id="6cbd2-104">Use datos propietarios de Microsoft para enriquecer os seus datos de clientes con afinidades de marcas e intereses.</span><span class="sxs-lookup"><span data-stu-id="6cbd2-104">Use Microsoft's proprietary data to enrich your customer data with brand and interest affinities.</span></span> <span data-ttu-id="6cbd2-105">Estas afinidades determínanse en base a datos de persoas con datos demográficos semellantes aos seus clientes.</span><span class="sxs-lookup"><span data-stu-id="6cbd2-105">These affinities are determined based on data from people with similar demographics to your customers.</span></span> <span data-ttu-id="6cbd2-106">Esta información axúdalle a comprender e segmentar mellor os seus clientes en función das súas afinidades a marcas e intereses específicos.</span><span class="sxs-lookup"><span data-stu-id="6cbd2-106">This information helps you to better understand and segment your customers based on their affinities to specific brands and interests.</span></span>

<span data-ttu-id="6cbd2-107">Para obter información do público, vaia a **Datos** > **Enriquecemento** para [configurar e ver enriquecementos](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="6cbd2-107">In audience insights, go to **Data** > **Enrichment** to [configure and view enrichments](enrichment-hub.md).</span></span>

<span data-ttu-id="6cbd2-108">Para configurar o enriquecemento de afinidades de marca, diríxase á pestana **Descubrir** e seleccione **Enriquecer os meus datos** no mosaico **Marcas**.</span><span class="sxs-lookup"><span data-stu-id="6cbd2-108">To configure brand affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Brands** tile.</span></span>

<span data-ttu-id="6cbd2-109">Para configurar o enriquecemento de afinidades de intereses, diríxase á pestana **Descubrir** e seleccione **Enriquecer os meus datos** no mosaico **Intereses**.</span><span class="sxs-lookup"><span data-stu-id="6cbd2-109">To configure interest affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Interests** tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6cbd2-110">![Mosaicos de Marcas e intereses](media/BrandsInterest-tile-Hub.png "Mosaicos de marcas e intereses")</span><span class="sxs-lookup"><span data-stu-id="6cbd2-110">![Brands & Interests tiles](media/BrandsInterest-tile-Hub.png "Brands & Interest tiles")</span></span>

## <a name="how-we-determine-affinities"></a><span data-ttu-id="6cbd2-111">Como determinamos as afinidades</span><span class="sxs-lookup"><span data-stu-id="6cbd2-111">How we determine affinities</span></span>

<span data-ttu-id="6cbd2-112">Usamos os datos de busca en liña de Microsoft para atopar afinidades de marcas e intereses en diversos segmentos demográficos (definidos por idade, sexo ou situación).</span><span class="sxs-lookup"><span data-stu-id="6cbd2-112">We use Microsoft’s online search data to find affinities for brands and interests across various demographic segments (defined by age, gender, or location).</span></span> <span data-ttu-id="6cbd2-113">O volume de busca en liña dunha marca ou interese determina a cantidade de afinidade que ten un segmento demográfico en comparación con outros segmentos con esa marca ou interese.</span><span class="sxs-lookup"><span data-stu-id="6cbd2-113">The online search volume for a brand or interest determines how much affinity a demographic segment, compared to other segments, has to that brand or interest.</span></span> <span data-ttu-id="6cbd2-114">marca ou interese.</span><span class="sxs-lookup"><span data-stu-id="6cbd2-114">brand or interest.</span></span>

## <a name="affinity-level-and-score"></a><span data-ttu-id="6cbd2-115">Nivel e puntuación de afinidade</span><span class="sxs-lookup"><span data-stu-id="6cbd2-115">Affinity level and score</span></span>

<span data-ttu-id="6cbd2-116">En cada perfil de cliente enriquecido, fornecemos dous valores relacionados: o nivel de afinidade e a puntuación de afinidade.</span><span class="sxs-lookup"><span data-stu-id="6cbd2-116">On every enriched customer profile, we provide two related values – affinity level and affinity score.</span></span> <span data-ttu-id="6cbd2-117">Estes valores axúdanlle a determinar o forte que é a afinidade do segmento demográfico dese perfil, por unha marca ou interese, en comparación con outros segmentos demográficos.</span><span class="sxs-lookup"><span data-stu-id="6cbd2-117">These values help you determine how strong the affinity is for that profile’s demographic segment, for a brand or interest, as compared to other demographic segments.</span></span>

<span data-ttu-id="6cbd2-118">O *nivel de afinidade* consta de catro niveis e a *puntuación de afinidade* calcúlase nunha escala de 100 puntos que se asigna aos niveis de afinidade.</span><span class="sxs-lookup"><span data-stu-id="6cbd2-118">*Affinity level* consists of four levels and *affinity score* is calculated on a 100-point scale that maps to the affinity levels.</span></span>


|<span data-ttu-id="6cbd2-119">Nivel de afinidade</span><span class="sxs-lookup"><span data-stu-id="6cbd2-119">Affinity level</span></span> |<span data-ttu-id="6cbd2-120">Puntuación de afinidade</span><span class="sxs-lookup"><span data-stu-id="6cbd2-120">Affinity score</span></span>  |
|---------|---------|
|<span data-ttu-id="6cbd2-121">Moi alto</span><span class="sxs-lookup"><span data-stu-id="6cbd2-121">Very high</span></span>     | <span data-ttu-id="6cbd2-122">85-100</span><span class="sxs-lookup"><span data-stu-id="6cbd2-122">85-100</span></span>       |
|<span data-ttu-id="6cbd2-123">Alto</span><span class="sxs-lookup"><span data-stu-id="6cbd2-123">High</span></span>     | <span data-ttu-id="6cbd2-124">70-84</span><span class="sxs-lookup"><span data-stu-id="6cbd2-124">70-84</span></span>        |
|<span data-ttu-id="6cbd2-125">Mediana</span><span class="sxs-lookup"><span data-stu-id="6cbd2-125">Medium</span></span>     | <span data-ttu-id="6cbd2-126">35-69</span><span class="sxs-lookup"><span data-stu-id="6cbd2-126">35-69</span></span>        |
|<span data-ttu-id="6cbd2-127">Baixo</span><span class="sxs-lookup"><span data-stu-id="6cbd2-127">Low</span></span>     | <span data-ttu-id="6cbd2-128">1-34</span><span class="sxs-lookup"><span data-stu-id="6cbd2-128">1-34</span></span>        |

<span data-ttu-id="6cbd2-129">Dependendo da granularidade que desexe para medir a afinidade, pode usar o nivel de afinidade ou a puntuación.</span><span class="sxs-lookup"><span data-stu-id="6cbd2-129">Depending on the granularity you would like for measuring the affinity, you can use either affinity level or score.</span></span> <span data-ttu-id="6cbd2-130">A puntuación de afinidade ofrécelle un control máis preciso.</span><span class="sxs-lookup"><span data-stu-id="6cbd2-130">Affinity score gives you more precise control.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="6cbd2-131">Países ou rexións compatibles</span><span class="sxs-lookup"><span data-stu-id="6cbd2-131">Supported countries/regions</span></span>

<span data-ttu-id="6cbd2-132">Actualmente son compatibles as seguintes opcións de país ou rexión: Australia, Canadá (inglés), Francia, Alemaña, Reino Unido ou Estados Unidos (inglés).</span><span class="sxs-lookup"><span data-stu-id="6cbd2-132">We currently support the following country/region options: Australia, Canada (English), France, Germany, United Kingdom, or United States (English).</span></span>

<span data-ttu-id="6cbd2-133">Para seleccionar un país, abra **Enriquecemento de marcas** ou **Enriquecemento de intereses** e seleccione **Cambiar** xunto a **País/Rexión**.</span><span class="sxs-lookup"><span data-stu-id="6cbd2-133">To select a country, open the **Brands enrichment** or **Interest enrichment** and select **Change** next to **Country/Region**.</span></span> <span data-ttu-id="6cbd2-134">No panel **Configuración do país/rexión**, escolla unha opción e seleccione **Solicitar**.</span><span class="sxs-lookup"><span data-stu-id="6cbd2-134">In the **Country/Region settings** pane, choose an option and select **Apply**.</span></span>

### <a name="implications-related-to-country-selection"></a><span data-ttu-id="6cbd2-135">Implicacións relacionadas coa selección do país</span><span class="sxs-lookup"><span data-stu-id="6cbd2-135">Implications related to country selection</span></span>

- <span data-ttu-id="6cbd2-136">Cando [escolla as súas propias marcas](#define-your-brands-or-interests), o sistema ofrece suxestións en función do país ou rexión seleccionado.</span><span class="sxs-lookup"><span data-stu-id="6cbd2-136">When [choosing your own brands](#define-your-brands-or-interests), the system provides suggestions based on the selected country or region.</span></span>

- <span data-ttu-id="6cbd2-137">Cando [escolla unha industria](#define-your-brands-or-interests), obterá as marcas ou intereses máis relevantes en función do país ou rexión seleccionado.</span><span class="sxs-lookup"><span data-stu-id="6cbd2-137">When [choosing an industry](#define-your-brands-or-interests), you'll get the most relevant brands or interests based on the selected country or region.</span></span>

- <span data-ttu-id="6cbd2-138">Cando [enriqueza perfís](#refresh-enrichment), enriqueceremos todos os perfís de clientes dos que obtemos datos das marcas e intereses seleccionados.</span><span class="sxs-lookup"><span data-stu-id="6cbd2-138">When [enriching profiles](#refresh-enrichment), we'll enrich all customer profiles for which we get data for the selected brands and interests.</span></span> <span data-ttu-id="6cbd2-139">Incluír perfís que non están no país ou rexión seleccionados.</span><span class="sxs-lookup"><span data-stu-id="6cbd2-139">Including profiles that are not in the selected country or region.</span></span> <span data-ttu-id="6cbd2-140">Por exemplo, se seleccionou Alemaña, enriqueceremos os perfís situados nos Estados Unidos se temos datos dispoñibles para as marcas e os intereses seleccionados nos Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="6cbd2-140">For example, if you selected Germany, we'll enrich profiles located in the United States if we have data available for the selected brands and interests in the US.</span></span>

## <a name="configure-enrichment"></a><span data-ttu-id="6cbd2-141">Configurar o enriquecemento</span><span class="sxs-lookup"><span data-stu-id="6cbd2-141">Configure Enrichment</span></span>

<span data-ttu-id="6cbd2-142">Unha experiencia guiada axúdalle a configurar os enriquecementos.</span><span class="sxs-lookup"><span data-stu-id="6cbd2-142">A guided experience helps you through the configuration of the enrichments.</span></span> 

### <a name="define-your-brands-or-interests"></a><span data-ttu-id="6cbd2-143">Definir as marcas ou os intereses</span><span class="sxs-lookup"><span data-stu-id="6cbd2-143">Define your brands or interests</span></span>

<span data-ttu-id="6cbd2-144">Seleccione unha das seguintes opcións:</span><span class="sxs-lookup"><span data-stu-id="6cbd2-144">Select one of the following options:</span></span>

- <span data-ttu-id="6cbd2-145">**Sector**: o sistema identifica as principais marcas ou intereses relevantes para a súa industria e enriquece os datos dos seus clientes con elas.</span><span class="sxs-lookup"><span data-stu-id="6cbd2-145">**Industry**: The system identifies the top brands or interests relevant to your industry and enriches your customer data with them.</span></span>
- <span data-ttu-id="6cbd2-146">**Elixa o seu**: seleccione ata cinco elementos da lista de marcas ou intereses máis relevantes para a súa organización.</span><span class="sxs-lookup"><span data-stu-id="6cbd2-146">**Choose your own**: Select up to five items from the list of brands or interests that are most relevant to your organization.</span></span>

<span data-ttu-id="6cbd2-147">Para engadir unha marca ou interese, introdúzaa na área de entrada para obter suxestións baseadas nos termos correspondentes.</span><span class="sxs-lookup"><span data-stu-id="6cbd2-147">To add a brand or interest, enter it in the input area to get suggestions based on matching terms.</span></span> <span data-ttu-id="6cbd2-148">Se non enumeramos unha marca ou interese que está a buscar, envíenos comentarios usando a ligazón **Suxerir**.</span><span class="sxs-lookup"><span data-stu-id="6cbd2-148">If we don't list a brand or interest you're looking for, send us feedback using the **Suggest** link.</span></span>

### <a name="review-enrichment-preferences"></a><span data-ttu-id="6cbd2-149">Revisar preferencias de enriquecemento</span><span class="sxs-lookup"><span data-stu-id="6cbd2-149">Review enrichment preferences</span></span>

<span data-ttu-id="6cbd2-150">Revise as súas preferencias de enriquecemento predeterminadas e actualíceas segundo sexa necesario.</span><span class="sxs-lookup"><span data-stu-id="6cbd2-150">Review your default enrichment preferences and update them as needed.</span></span>

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Captura de pantalla da xanela de preferencias de enriquecemento.":::

### <a name="select-entity-to-enrich"></a><span data-ttu-id="6cbd2-152">Seleccionar entidade para enriquecer</span><span class="sxs-lookup"><span data-stu-id="6cbd2-152">Select entity to enrich</span></span>

<span data-ttu-id="6cbd2-153">Seleccione **Enriquecer entidade** e escolla o conxunto de datos que quere enriquecer cos datos da empresa de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6cbd2-153">Select **Enriched entity** and choose the data set you want to enrich with company data from the Microsoft.</span></span> <span data-ttu-id="6cbd2-154">Pode seleccionar a entidade Cliente para enriquecer todos os seus perfís de clientes ou seleccione unha entidade de segmento para enriquecer só os perfís de clientes contidos nese segmento.</span><span class="sxs-lookup"><span data-stu-id="6cbd2-154">You can select the Customer entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

### <a name="map-your-fields"></a><span data-ttu-id="6cbd2-155">Asignar os campos</span><span class="sxs-lookup"><span data-stu-id="6cbd2-155">Map your fields</span></span>

<span data-ttu-id="6cbd2-156">Asigne campos da súa entidade cliente unificada para definir o segmento demográfico que desexa que use o sistema para enriquecer os datos dos seus clientes.</span><span class="sxs-lookup"><span data-stu-id="6cbd2-156">Map fields from your unified customer entity to define the demographic segment you want the system to use for enriching your customer data.</span></span> <span data-ttu-id="6cbd2-157">Asigne o País/Rexión e polo menos os atributos Data de nacemento ou Sexo.</span><span class="sxs-lookup"><span data-stu-id="6cbd2-157">Map Country/Region and at least Date of Birth or Gender attributes.</span></span> <span data-ttu-id="6cbd2-158">Ademais, debe asignar polo menos un código de cidade (e estado/provincia) ou codigo postal.</span><span class="sxs-lookup"><span data-stu-id="6cbd2-158">Additionally, you must map at least one of City (and State/Province) or Postal code.</span></span> <span data-ttu-id="6cbd2-159">Seleccione **Editar** definir a asignación dos campos e seleccionar **Aplicar** cando remate.</span><span class="sxs-lookup"><span data-stu-id="6cbd2-159">Select **Edit** to define the mapping of the fields and select **Apply** when you're done.</span></span> <span data-ttu-id="6cbd2-160">Seleccione **Gardar** para completar a asignación de campos.</span><span class="sxs-lookup"><span data-stu-id="6cbd2-160">Select **Save** to complete the field mapping.</span></span>

<span data-ttu-id="6cbd2-161">Admítense os seguintes formatos e valores, os valores non diferencian entre maiúsculas e minúsculas:</span><span class="sxs-lookup"><span data-stu-id="6cbd2-161">The following formats and values are supported, values are not case-sensitive:</span></span>

- <span data-ttu-id="6cbd2-162">**Data de nacemento**: Recomendamos que a data de nacemento sexa convertida ao tipo DateTime durante a inxestión de datos.</span><span class="sxs-lookup"><span data-stu-id="6cbd2-162">**Date of Birth**: We recommend that date of birth is converted to DateTime type during data ingestion.</span></span> <span data-ttu-id="6cbd2-163">Alternativamente, pode ser unha cadea en formato [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) "aaaa-MM-dd" ou "aaaa-MM-ddTHH: mm:ssZ".</span><span class="sxs-lookup"><span data-stu-id="6cbd2-163">Alternatively, it can be a string in [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) format "yyyy-MM-dd" or "yyyy-MM-ddTHH:mm:ssZ".</span></span>
- <span data-ttu-id="6cbd2-164">**Sexo**: Masculino, Feminino, Descoñecido</span><span class="sxs-lookup"><span data-stu-id="6cbd2-164">**Gender**: Male, Female, Unknown</span></span>
- <span data-ttu-id="6cbd2-165">**Código postal**: Códigos de cinco díxitos para EUA, código postal estándar en calquera outro lugar</span><span class="sxs-lookup"><span data-stu-id="6cbd2-165">**Postal code**: Five-digit ZIP Codes for US, standard postal code everywhere else</span></span>
- <span data-ttu-id="6cbd2-166">**Cidade**: Nome da cidade en inglés</span><span class="sxs-lookup"><span data-stu-id="6cbd2-166">**City**: City name in English</span></span>
- <span data-ttu-id="6cbd2-167">**Estado/Provincia**: Abreviatura de dúas letras para Estados Unidos e Canadá.</span><span class="sxs-lookup"><span data-stu-id="6cbd2-167">**State/Province**: Two-letter abbreviation for the US and Canada.</span></span> <span data-ttu-id="6cbd2-168">Abreviación de dúas ou tres letras para Australia.</span><span class="sxs-lookup"><span data-stu-id="6cbd2-168">Two or three letter abbreviation for Australia.</span></span> <span data-ttu-id="6cbd2-169">Non se aplica a Francia, Alemaña ou Reino Unido.</span><span class="sxs-lookup"><span data-stu-id="6cbd2-169">Not applicable for France, Germany, or the UK.</span></span>
- <span data-ttu-id="6cbd2-170">**País/Rexión**:</span><span class="sxs-lookup"><span data-stu-id="6cbd2-170">**Country/Region**:</span></span>

  - <span data-ttu-id="6cbd2-171">EUA: Estados Unidos de América, Estados Unidos, EE. UU., EUA, EU</span><span class="sxs-lookup"><span data-stu-id="6cbd2-171">US: United States of America, United States, USA, US, America</span></span>
  - <span data-ttu-id="6cbd2-172">CA: Canadá, CA</span><span class="sxs-lookup"><span data-stu-id="6cbd2-172">CA: Canada, CA</span></span>
  - <span data-ttu-id="6cbd2-173">RU: Reino Unido, RU, Gran Bretaña, GB, Reino Unido de Gran Bretaña e Irlanda do Norte, Reino Unido de Gran Bretaña</span><span class="sxs-lookup"><span data-stu-id="6cbd2-173">GB: United Kingdom, UK, Great Britain, GB, United Kingdom of Great Britain and Northern Ireland, United Kingdom of Great Britain</span></span>
  - <span data-ttu-id="6cbd2-174">AU: Australia, AU, Mancomunidade de Australia</span><span class="sxs-lookup"><span data-stu-id="6cbd2-174">AU: Australia, AU, Common Wealth of Australia</span></span>
  - <span data-ttu-id="6cbd2-175">FR: Francia, FR, República Francesa</span><span class="sxs-lookup"><span data-stu-id="6cbd2-175">FR: France, FR, French Republic</span></span>
  - <span data-ttu-id="6cbd2-176">DE: Alemaña, Alemán, Deutschland, Allemagne, DE, República Federal de Alemaña, República de Alemaña</span><span class="sxs-lookup"><span data-stu-id="6cbd2-176">DE: Germany, German, Deutschland, Allemagne, DE, Federal Republic of Germany, Republic of Germany</span></span>

## <a name="review-and-name-the-enrichment"></a><span data-ttu-id="6cbd2-177">Revisar e nomear o enriquecemento</span><span class="sxs-lookup"><span data-stu-id="6cbd2-177">Review and name the enrichment</span></span>

<span data-ttu-id="6cbd2-178">Finalmente, pode revisar a información e proporcionar un nome para o enriquecemento.</span><span class="sxs-lookup"><span data-stu-id="6cbd2-178">Finally, you get to review the information and provide a name for the enrichment.</span></span>

:::image type="content" source="media/enrichment-interests-summary.png" alt-text="Revisión de intereses e nome de páxina.":::

## <a name="refresh-enrichment"></a><span data-ttu-id="6cbd2-180">Actualizar o enriquecemento</span><span class="sxs-lookup"><span data-stu-id="6cbd2-180">Refresh enrichment</span></span>

<span data-ttu-id="6cbd2-181">Execute o enriquecemento despois de configurar marcas, intereses e asignación de campos para os datos demográficos.</span><span class="sxs-lookup"><span data-stu-id="6cbd2-181">Run the enrichment after configuring brands, interests, and the field mapping for demographics.</span></span> <span data-ttu-id="6cbd2-182">Para iniciar o proceso, seleccione **Executar** na páxina de configuración da marca ou o interese.</span><span class="sxs-lookup"><span data-stu-id="6cbd2-182">To start the process, select **Run** on the brand or interest configuration page.</span></span> <span data-ttu-id="6cbd2-183">Ademais, pode deixar que o sistema execute o enriquecemento automaticamente como parte dunha actualización programada.</span><span class="sxs-lookup"><span data-stu-id="6cbd2-183">Additionally, you can let the system run the enrichment automatically as part of a scheduled refresh.</span></span>
<span data-ttu-id="6cbd2-184">Dependendo do tamaño dos datos dos seus clientes, a execución do enriquecemento pode levar uns minutos.</span><span class="sxs-lookup"><span data-stu-id="6cbd2-184">Depending on the size of your customer data, it may take several minutes for an enrichment run to complete.</span></span>

> [!TIP]
> <span data-ttu-id="6cbd2-185">Existen [seis tipos de estado](system.md#status-types) para as tarefas ou os procesos.</span><span class="sxs-lookup"><span data-stu-id="6cbd2-185">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="6cbd2-186">Ademais, a maioría dos procesos [dependen doutros procesos descendentes](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="6cbd2-186">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="6cbd2-187">Pode seleccionar o estado dun proceso para ver detalles sobre o progreso de todo o traballo.</span><span class="sxs-lookup"><span data-stu-id="6cbd2-187">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="6cbd2-188">Despois de seleccionar **Ver detalles** para unha das tarefas do traballo, atopará información adicional: o tempo de procesamento, a última data de procesamento e todos os erros e avisos asociados á tarefa.</span><span class="sxs-lookup"><span data-stu-id="6cbd2-188">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="6cbd2-189">Resultados de enriquecemento</span><span class="sxs-lookup"><span data-stu-id="6cbd2-189">Enrichment results</span></span>

<span data-ttu-id="6cbd2-190">Despois de executar o proceso de enriquecemento, vaia a **Os meus enriquecementos** para revisar o número total de clientes enriquecidos e unha subdivisión de marcas ou intereses nos perfís de clientes enriquecidos.</span><span class="sxs-lookup"><span data-stu-id="6cbd2-190">After running the enrichment process, go to **My enrichments** to review the total number of enriched customers and a breakdown of brands or interests in the enriched customer profiles.</span></span>

:::image type="content" source="media/my-enrichments.png" alt-text="Vista previa dos resultados despois de executar o proceso de enriquecemento":::

<span data-ttu-id="6cbd2-192">Revise os datos enriquecidos seleccionando **Ver datos enriquecidos** no gráfico.</span><span class="sxs-lookup"><span data-stu-id="6cbd2-192">Review the enriched data by selecting **View enriched data** in the chart.</span></span> <span data-ttu-id="6cbd2-193">Os datos enriquecidos para as marcas van á entidade **BrandAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="6cbd2-193">Enriched data for brands goes to the **BrandAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="6cbd2-194">Datos para intereses na entidade **InterestAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="6cbd2-194">Data for interests is in the **InterestAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="6cbd2-195">Tamén atopará estas entidades enumeradas no grupo **Enriquecemento** en **Datos** > **Entidades**.</span><span class="sxs-lookup"><span data-stu-id="6cbd2-195">You'll also find these entities listed in the **Enrichment** group in **Data** > **Entities**.</span></span>

## <a name="see-enrichment-data-on-the-customer-card"></a><span data-ttu-id="6cbd2-196">Vexa datos de enriquecemento na tarxeta de cliente</span><span class="sxs-lookup"><span data-stu-id="6cbd2-196">See enrichment data on the customer card</span></span>

<span data-ttu-id="6cbd2-197">As afinidades de marca e interese tamén se poden ver nas tarxetas de clientes individuais.</span><span class="sxs-lookup"><span data-stu-id="6cbd2-197">Brand and interest affinities can also be viewed on individual customer cards.</span></span> <span data-ttu-id="6cbd2-198">Vaia a **Clientes** e seleccione un perfil de cliente.</span><span class="sxs-lookup"><span data-stu-id="6cbd2-198">Go to **Customers** and select a customer profile.</span></span> <span data-ttu-id="6cbd2-199">Na tarxeta de cliente atopará gráficos das marcas ou intereses polos que teñen afinidade os usuarios do perfil demográfico dese cliente.</span><span class="sxs-lookup"><span data-stu-id="6cbd2-199">In the customer card, you'll find charts for the brands or interests that people in that customer's demographic profile have affinity for.</span></span>

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Tarxeta de cliente con datos enriquecidos":::

## <a name="next-steps"></a><span data-ttu-id="6cbd2-201">Seguintes pasos</span><span class="sxs-lookup"><span data-stu-id="6cbd2-201">Next steps</span></span>

<span data-ttu-id="6cbd2-202">Crear sobre os seus datos enriquecidos de clientes.</span><span class="sxs-lookup"><span data-stu-id="6cbd2-202">Build on top of your enriched customer data.</span></span> <span data-ttu-id="6cbd2-203">Cree [Segmentos](segments.md), [Medidas](measures.md) e incluso [exporte os datos](export-destinations.md) para ofrecer experiencias personalizadas aos seus clientes.</span><span class="sxs-lookup"><span data-stu-id="6cbd2-203">Create [Segments](segments.md), [Measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
