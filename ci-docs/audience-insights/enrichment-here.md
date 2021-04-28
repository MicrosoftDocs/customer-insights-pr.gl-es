---
title: Enriquecemento co enriquecemento de terceiros de HERE Technologies
description: Información xeral sobre o enriquecemento de terceiros de HERE Technologies.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 5d1f037377010153045c9255d2d01f98ebf1fdfd
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896049"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a><span data-ttu-id="ea24d-103">Enriquecemento de perfís de clientes con HERE Technologies (vista previa)</span><span class="sxs-lookup"><span data-stu-id="ea24d-103">Enrichment of customer profiles with HERE Technologies (preview)</span></span>

<span data-ttu-id="ea24d-104">HERE Technologies é unha empresa de plataformas de localización que ofrece servizos e datos centrados na situación.</span><span class="sxs-lookup"><span data-stu-id="ea24d-104">HERE Technologies is a location platform company that provides location-centric data and services.</span></span> <span data-ttu-id="ea24d-105">Cos servizos de enriquecemento de datos de HERE Technologies, pode construír unha comprensión máis precisa da situación dos seus clientes coa normalización de enderezos, a extracción de latitude e lonxitude e moito máis.</span><span class="sxs-lookup"><span data-stu-id="ea24d-105">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ea24d-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="ea24d-106">Prerequisites</span></span>

<span data-ttu-id="ea24d-107">Para configurar os enriquecementos de HERE Technologies, deben cumprirse os seguintes requisitos previos:</span><span class="sxs-lookup"><span data-stu-id="ea24d-107">To configure HERE Technologies enrichments, the following prerequisites must be met:</span></span>

- <span data-ttu-id="ea24d-108">Ten unha subscrición activa de HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="ea24d-108">You have an active HERE Technologies subscription.</span></span> <span data-ttu-id="ea24d-109">Para obter unha subscrición, pode [inscribirse aquí](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) ou [poñerse en contacto con HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directamente.</span><span class="sxs-lookup"><span data-stu-id="ea24d-109">To get a subscription, you can [sign-up here](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) or [contact HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directly.</span></span> [<span data-ttu-id="ea24d-110">Obteña máis información sobre o enriquecemento de localización de HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="ea24d-110">Learn more about HERE Technologies Location Enrichment.</span></span>](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- <span data-ttu-id="ea24d-111">Hai unha [conexión](connections.md) de HERE dispoñible *ou* ten permisos de [administrador](permissions.md#administrator) e a clave da API de HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="ea24d-111">There is a HERE [connection](connections.md) available *or* you have [administrator](permissions.md#administrator) permissions and the HERE Technologies API key.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="ea24d-112">Configurar o enriquecemento</span><span class="sxs-lookup"><span data-stu-id="ea24d-112">Configure the enrichment</span></span>

1. <span data-ttu-id="ea24d-113">Vaia a **Datos** > **Enriquecemento**.</span><span class="sxs-lookup"><span data-stu-id="ea24d-113">Go to **Data** > **Enrichment**.</span></span> 

1. <span data-ttu-id="ea24d-114">No mosaico de HERE Technologies, seleccione **Enriquecer os meus datos** e logo seleccione **Comezar**.</span><span class="sxs-lookup"><span data-stu-id="ea24d-114">Select **Enrich my data** on the HERE Technologies tile and select **Get started**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ea24d-115">![Mosaico de HERE Technologies](media/HERE-tile.png "Mosaico de HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="ea24d-115">![HERE Technologies tile](media/HERE-tile.png "HERE Technologies tile")</span></span>

1. <span data-ttu-id="ea24d-116">Seleccione unha [conexión](connections.md) da lista despregable.</span><span class="sxs-lookup"><span data-stu-id="ea24d-116">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="ea24d-117">Póñase en contacto cun administrador se non hai conexión dispoñible.</span><span class="sxs-lookup"><span data-stu-id="ea24d-117">Contact  an administrator if no connection is available.</span></span> <span data-ttu-id="ea24d-118">Se é administrador, pode crear unha conexión seleccionando **Engadir conexión**.</span><span class="sxs-lookup"><span data-stu-id="ea24d-118">If you are an administrator, you can create a connection by selecting **Add connection**.</span></span> <span data-ttu-id="ea24d-119">Escolla **HERE Technologies** desde o menú despregable.</span><span class="sxs-lookup"><span data-stu-id="ea24d-119">Choose **HERE Technologies** from the drop-down.</span></span> 

1. <span data-ttu-id="ea24d-120">Seleccione **Conectar con HERE Technologies** para confirmar a selección.</span><span class="sxs-lookup"><span data-stu-id="ea24d-120">Select **Connect to HERE Technologies** to confirm the selection.</span></span>

1.  <span data-ttu-id="ea24d-121">Seleccione **Seguinte** e escolla o **Conxunto de datos do cliente** que quere enriquecer cos datos de localización de HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="ea24d-121">Select **Next** and choose the **Customer data set** you want to enrich with location data from HERE Technologies.</span></span> <span data-ttu-id="ea24d-122">Pode seleccionar a entidade **Cliente** para enriquecer todos os seus perfís de clientes ou seleccione unha entidade de segmento para enriquecer só os perfís de clientes contidos nese segmento.</span><span class="sxs-lookup"><span data-stu-id="ea24d-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="Captura de pantalla ao escoller o conxunto de datos do cliente.":::

1. <span data-ttu-id="ea24d-124">Escolla se desexa asignar campos ao enderezo principal e/ou secundario.</span><span class="sxs-lookup"><span data-stu-id="ea24d-124">Choose if you want to map fields to the primary and/or secondary address.</span></span> <span data-ttu-id="ea24d-125">Pode especificar unha asignación de campos para ambos os enderezos e enriquecer os perfís de ambos os enderezos por separado.</span><span class="sxs-lookup"><span data-stu-id="ea24d-125">You can specify a field mapping for both addresses and enrich the profiles for both addresses separately.</span></span> <span data-ttu-id="ea24d-126">Por exemplo, se hai un domicilio e un enderezo comercial.</span><span class="sxs-lookup"><span data-stu-id="ea24d-126">For example, if there's a home and a business address.</span></span> <span data-ttu-id="ea24d-127">Seleccione **Seguinte**.</span><span class="sxs-lookup"><span data-stu-id="ea24d-127">Select **Next**.</span></span>

1. <span data-ttu-id="ea24d-128">Defina os campos dos perfís unificados que se deben empregar para buscar datos de localización coincidentes de HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="ea24d-128">Define which fields from your unified profiles should be used to look for matching location data from HERE Technologies.</span></span> <span data-ttu-id="ea24d-129">Os campos **Rúa 1** e **Código postal** son obrigatorios para o enderezo primario e/ou secundario seleccionado.</span><span class="sxs-lookup"><span data-stu-id="ea24d-129">The **Street 1** and **Zip/Postal Code** fields are required for the selected primary and/or secondary address.</span></span> <span data-ttu-id="ea24d-130">Para unha maior precisión de coincidencia, pódense engadir máis campos.</span><span class="sxs-lookup"><span data-stu-id="ea24d-130">For a higher match accuracy, more fields can be added.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ea24d-131">![Páxina de configuración de enriquecemento de HERE Technologies](media/enrichment-HERE-configuration.png "Páxina de configuración de enriquecemento de HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="ea24d-131">![HERE Technologies enrichment configuration page](media/enrichment-HERE-configuration.png "HERE Technologies enrichment configuration page")</span></span>

1. <span data-ttu-id="ea24d-132">Seleccione **Seguinte** para concluír a asignación do campo.</span><span class="sxs-lookup"><span data-stu-id="ea24d-132">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="ea24d-133">Proporcione un nome para o enriquecemento.</span><span class="sxs-lookup"><span data-stu-id="ea24d-133">Provide a name for the enrichment.</span></span> 

<span data-ttu-id="ea24d-134">1. Seleccione **Gardar enriquecemento** despois de revisar as súas opcións.</span><span class="sxs-lookup"><span data-stu-id="ea24d-134">1.Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-here-technologies"></a><span data-ttu-id="ea24d-135">Configurar a conexión para HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="ea24d-135">Configure the connection for HERE technologies</span></span> 

<span data-ttu-id="ea24d-136">Debe ser administrador para configurar as conexións.</span><span class="sxs-lookup"><span data-stu-id="ea24d-136">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="ea24d-137">Seleccione **Engadir conexión** ao configurar un enriquecemento *ou* vaia a **Administrar** > **Conexións** e seleccione **Configurar** no mosaico de HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="ea24d-137">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the HERE Technologies tile.</span></span>

1. <span data-ttu-id="ea24d-138">Introduza un nome para a conexión na caixa **Nome de visualización**.</span><span class="sxs-lookup"><span data-stu-id="ea24d-138">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="ea24d-139">Proporcione unha clave de API de HERE Technologies válida.</span><span class="sxs-lookup"><span data-stu-id="ea24d-139">Provide a valid HERE Technologies API key.</span></span>

1. <span data-ttu-id="ea24d-140">Revise e proporcione o seu consentimento para a **Privacidade de datos e cumprimento** seleccionando a caixa de verificación **Estou de acordo**</span><span class="sxs-lookup"><span data-stu-id="ea24d-140">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox</span></span>

1. <span data-ttu-id="ea24d-141">Seleccione **Verificar** para validar a configuración.</span><span class="sxs-lookup"><span data-stu-id="ea24d-141">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="ea24d-142">Despois de completar a verificación, seleccione **Gardar**.</span><span class="sxs-lookup"><span data-stu-id="ea24d-142">After completing the verification, select **Save**.</span></span>

> [!div class="mx-imgBorder"]
   > <span data-ttu-id="ea24d-143">![Páxina de configuración da conexión de HERE Technologies](media/enrichment-HERE-connection.png "Páxina de configuración da conexión de HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="ea24d-143">![HERE Technologies connection configuration page](media/enrichment-HERE-connection.png "HERE Technologies connection configuration page")</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="ea24d-144">Resultados de enriquecemento</span><span class="sxs-lookup"><span data-stu-id="ea24d-144">Enrichment results</span></span>

<span data-ttu-id="ea24d-145">Para iniciar o proceso de enriquecemento, seleccione **Executar** na barra de comandos.</span><span class="sxs-lookup"><span data-stu-id="ea24d-145">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="ea24d-146">Tamén pode deixar que o sistema execute o enriquecemento automaticamente como parte dunha [actualización programada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="ea24d-146">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="ea24d-147">O tempo de procesamento dependerá do tamaño dos datos dos seus clientes e dos tempos de resposta da API de HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="ea24d-147">The processing time will depend on the size of your customer data and the API response times from HERE Technologies.</span></span>

<span data-ttu-id="ea24d-148">Despois de completar o proceso de enriquecemento, pode consultar os datos dos perfís de clientes recentemente enriquecidos en **Os meus enriquecementos**.</span><span class="sxs-lookup"><span data-stu-id="ea24d-148">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="ea24d-149">Ademais, atopará a hora da última actualización e o número de perfís enriquecidos.</span><span class="sxs-lookup"><span data-stu-id="ea24d-149">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="ea24d-150">Pode acceder a unha vista detallada de cada perfil enriquecido seleccionando **Ver datos enriquecidos**.</span><span class="sxs-lookup"><span data-stu-id="ea24d-150">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="ea24d-151">Pasos seguintes</span><span class="sxs-lookup"><span data-stu-id="ea24d-151">Next steps</span></span>

<span data-ttu-id="ea24d-152">Crear sobre os seus datos enriquecidos de clientes.</span><span class="sxs-lookup"><span data-stu-id="ea24d-152">Build on top of your enriched customer data.</span></span> <span data-ttu-id="ea24d-153">Cree [segmentos](segments.md), [medidas](measures.md) e incluso [exporte os datos](export-destinations.md) para ofrecer experiencias personalizadas aos seus clientes.</span><span class="sxs-lookup"><span data-stu-id="ea24d-153">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="ea24d-154">Cumprimento e privacidade dos datos</span><span class="sxs-lookup"><span data-stu-id="ea24d-154">Data privacy and compliance</span></span>

<span data-ttu-id="ea24d-155">Cando habilita Dynamics 365 Customer Insights para transmitir datos a HERE Technologies, permite a transferencia de datos fóra do límite de cumprimento de Dynamics 365 Customer Insights, incluíndo datos potencialmente confidenciais como os datos persoais.</span><span class="sxs-lookup"><span data-stu-id="ea24d-155">When you enable Dynamics 365 Customer Insights to transmit data to HERE Technologies, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="ea24d-156">Microsoft transferirá estes datos segundo a súa instrución, pero vostede é responsable de garantir que HERE Technologies cumpra as obrigas de privacidade ou seguridade que poida ter.</span><span class="sxs-lookup"><span data-stu-id="ea24d-156">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that HERE Technologies meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="ea24d-157">Para obter máis información, consulte a [Declaración de privacidade de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="ea24d-157">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="ea24d-158">O administrador de Dynamics 365 Customer Insights pode eliminar este enriquecemento en calquera momento para interromper o uso desta funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="ea24d-158">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
