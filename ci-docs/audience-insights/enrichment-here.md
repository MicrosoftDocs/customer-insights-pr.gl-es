---
title: Enriquecemento co enriquecemento de terceiros de HERE Technologies
description: Información xeral sobre o enriquecemento de terceiros de HERE Technologies.
ms.date: 12/10/2020
ms.reviewer: jodahl
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 258e37de9d9685d9ebc30b3c6b8d238d583431b4
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269512"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a><span data-ttu-id="7f612-103">Enriquecemento de perfís de clientes con HERE Technologies (vista previa)</span><span class="sxs-lookup"><span data-stu-id="7f612-103">Enrichment of customer profiles with HERE Technologies (preview)</span></span>

<span data-ttu-id="7f612-104">HERE Technologies é unha empresa de plataformas de localización que ofrece servizos e datos centrados na situación.</span><span class="sxs-lookup"><span data-stu-id="7f612-104">HERE Technologies is a location platform company that provides location-centric data and services.</span></span> <span data-ttu-id="7f612-105">Cos servizos de enriquecemento de datos de HERE Technologies, pode construír unha comprensión máis precisa da situación dos seus clientes coa normalización de enderezos, a extracción de latitude e lonxitude e moito máis.</span><span class="sxs-lookup"><span data-stu-id="7f612-105">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7f612-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="7f612-106">Prerequisites</span></span>

<span data-ttu-id="7f612-107">Para configurar os enriquecementos de HERE Technologies, deben cumprirse os seguintes requisitos previos:</span><span class="sxs-lookup"><span data-stu-id="7f612-107">To configure HERE Technologies enrichments, the following prerequisites must be met:</span></span>

- <span data-ttu-id="7f612-108">Ten unha subscrición activa de HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="7f612-108">You have an active HERE Technologies subscription.</span></span> <span data-ttu-id="7f612-109">Para obter unha subscrición, pode [inscribirse aquí](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) ou [poñerse en contacto con HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directamente.</span><span class="sxs-lookup"><span data-stu-id="7f612-109">To get a subscription, you can [sign-up here](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) or [contact HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directly.</span></span> [<span data-ttu-id="7f612-110">Obteña máis información sobre o enriquecemento de localización de HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="7f612-110">Learn more about HERE Technologies Location Enrichment.</span></span>](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- <span data-ttu-id="7f612-111">Ten a clave da API de HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="7f612-111">You have the HERE Technologies API key.</span></span>

- <span data-ttu-id="7f612-112">Ten permisos de [administrador](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="7f612-112">You have [Administrator](permissions.md#administrator) permissions.</span></span>

## <a name="configuration"></a><span data-ttu-id="7f612-113">Configuración</span><span class="sxs-lookup"><span data-stu-id="7f612-113">Configuration</span></span>

1. <span data-ttu-id="7f612-114">Vaia a **Datos** > **Enriquecemento**.</span><span class="sxs-lookup"><span data-stu-id="7f612-114">Go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="7f612-115">No mosaico de HERE Technologies, seleccione **Enriquecer os meus datos**.</span><span class="sxs-lookup"><span data-stu-id="7f612-115">Select **Enrich my data** on the HERE Technologies tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="7f612-116">![Mosaico de HERE Technologies](media/HERE-tile.png "Mosaico de HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="7f612-116">![HERE Technologies tile](media/HERE-tile.png "HERE Technologies tile")</span></span>

1. <span data-ttu-id="7f612-117">Insira unha **clave da API de HERE Technologies** activa.</span><span class="sxs-lookup"><span data-stu-id="7f612-117">Enter an active **HERE Technologies API key**.</span></span> <span data-ttu-id="7f612-118">Revise e proporcione o seu consentimento para a **Privacidade e cumprimento dos datos** seleccionando a caixa de verificación **Estou de acordo**.</span><span class="sxs-lookup"><span data-stu-id="7f612-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> 

1. <span data-ttu-id="7f612-119">Confirme ambas as entradas seleccionando **Conectarse a HERE**.</span><span class="sxs-lookup"><span data-stu-id="7f612-119">Confirm both inputs by selecting **Connect to HERE**.</span></span>

1.  <span data-ttu-id="7f612-120">Seleccione **Engadir datos** e escolla o **conxunto de datos de cliente** que desexa enriquecer coa localización de HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="7f612-120">Select **Add data** and choose the **Customer data set** you want to enrich with location data from HERE Technologies.</span></span> <span data-ttu-id="7f612-121">Pode seleccionar a entidade **Cliente** para enriquecer todos os seus perfís de clientes ou seleccione unha entidade de segmento para enriquecer só os perfís de clientes contidos nese segmento.</span><span class="sxs-lookup"><span data-stu-id="7f612-121">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="Captura de pantalla ao escoller o conxunto de datos do cliente.":::

1. <span data-ttu-id="7f612-123">Escolla se desexa asignar campos ao enderezo principal e/ou secundario.</span><span class="sxs-lookup"><span data-stu-id="7f612-123">Choose if you want to map fields to the primary and/or secondary address.</span></span> <span data-ttu-id="7f612-124">Pode especificar unha asignación de campo para ambos os enderezos (por exemplo, un enderezo de casa e un de empresa) e enriquecer os perfís de ambos os enderezos por separado.</span><span class="sxs-lookup"><span data-stu-id="7f612-124">You can specify a field mapping for both addresses (for example, a home and a business address) and enrich the profiles for both addresses separately.</span></span> <span data-ttu-id="7f612-125">Seleccione **Seguinte**.</span><span class="sxs-lookup"><span data-stu-id="7f612-125">Select **Next**.</span></span>

1. <span data-ttu-id="7f612-126">Defina os campos dos perfís unificados que se deben empregar para buscar datos de localización coincidentes de HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="7f612-126">Define which fields from your unified profiles should be used to look for matching location data from HERE Technologies.</span></span> <span data-ttu-id="7f612-127">Os campos **Rúa 1** e **Código postal** son obrigatorios para o enderezo primario e/ou secundario seleccionado.</span><span class="sxs-lookup"><span data-stu-id="7f612-127">The **Street 1** and **Zip/Postal Code** fields are required for the selected primary and/or secondary address.</span></span> <span data-ttu-id="7f612-128">Para unha maior precisión de coincidencia, pódense engadir máis campos.</span><span class="sxs-lookup"><span data-stu-id="7f612-128">For a higher match accuracy, more fields can be added.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="7f612-129">![Páxina de configuración de enriquecemento de HERE Technologies](media/enrichment-HERE-configuration.png "Páxina de configuración de enriquecemento de HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="7f612-129">![HERE Technologies enrichment configuration page](media/enrichment-HERE-configuration.png "HERE Technologies enrichment configuration page")</span></span>

1. <span data-ttu-id="7f612-130">Seleccione **Aplicar** para completar a asignación de campos.</span><span class="sxs-lookup"><span data-stu-id="7f612-130">Select **Apply** to complete the field mapping.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="7f612-131">Resultados de enriquecemento</span><span class="sxs-lookup"><span data-stu-id="7f612-131">Enrichment results</span></span>

<span data-ttu-id="7f612-132">Para iniciar o proceso de enriquecemento, seleccione **Executar** na barra de comandos.</span><span class="sxs-lookup"><span data-stu-id="7f612-132">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="7f612-133">Tamén pode deixar que o sistema execute o enriquecemento automaticamente como parte dunha [actualización programada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="7f612-133">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="7f612-134">O tempo de procesamento dependerá do tamaño dos datos dos seus clientes e dos tempos de resposta da API de HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="7f612-134">The processing time will depend on the size of your customer data and the API response times from HERE Technologies.</span></span>

<span data-ttu-id="7f612-135">Despois de completar o proceso de enriquecemento, pode consultar os datos dos perfís de clientes recentemente enriquecidos en **Os meus enriquecementos**.</span><span class="sxs-lookup"><span data-stu-id="7f612-135">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="7f612-136">Ademais, atopará a hora da última actualización e o número de perfís enriquecidos.</span><span class="sxs-lookup"><span data-stu-id="7f612-136">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="7f612-137">Pode acceder a unha vista detallada de cada perfil enriquecido seleccionando **Ver datos enriquecidos**.</span><span class="sxs-lookup"><span data-stu-id="7f612-137">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="7f612-138">Pasos seguintes</span><span class="sxs-lookup"><span data-stu-id="7f612-138">Next steps</span></span>

<span data-ttu-id="7f612-139">Crear sobre os seus datos enriquecidos de clientes.</span><span class="sxs-lookup"><span data-stu-id="7f612-139">Build on top of your enriched customer data.</span></span> <span data-ttu-id="7f612-140">Cree [segmentos](segments.md), [medidas](measures.md) e incluso [exporte os datos](export-destinations.md) para ofrecer experiencias personalizadas aos seus clientes.</span><span class="sxs-lookup"><span data-stu-id="7f612-140">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="7f612-141">Cumprimento e privacidade dos datos</span><span class="sxs-lookup"><span data-stu-id="7f612-141">Data privacy and compliance</span></span>

<span data-ttu-id="7f612-142">Cando habilita Dynamics 365 Customer Insights para transmitir datos a HERE Technologies, permite a transferencia de datos fóra do límite de cumprimento de Dynamics 365 Customer Insights, incluíndo datos potencialmente confidenciais como os datos persoais.</span><span class="sxs-lookup"><span data-stu-id="7f612-142">When you enable Dynamics 365 Customer Insights to transmit data to HERE Technologies, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="7f612-143">Microsoft transferirá estes datos segundo a súa instrución, pero vostede é responsable de garantir que HERE Technologies cumpra as obrigas de privacidade ou seguridade que poida ter.</span><span class="sxs-lookup"><span data-stu-id="7f612-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that HERE Technologies meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="7f612-144">Para obter máis información, consulte a [Declaración de privacidade de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="7f612-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="7f612-145">O administrador de Dynamics 365 Customer Insights pode eliminar este enriquecemento en calquera momento para interromper o uso desta funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="7f612-145">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]