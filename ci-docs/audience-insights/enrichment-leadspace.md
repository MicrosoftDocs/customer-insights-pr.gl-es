---
title: Enriquecemento de perfís de empresa co enriquecemento de terceiros de Leadspace
description: Información xeral sobre o enriquecemento de terceiros de Leadspace.
ms.date: 11/24/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 41c56aece043c2d7658fd2655713e1e98775edec
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597647"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a><span data-ttu-id="021a4-103">Enriquecemento de perfís de empresa con Leadspace (vista previa)</span><span class="sxs-lookup"><span data-stu-id="021a4-103">Enrichment of company profiles with Leadspace (preview)</span></span>

<span data-ttu-id="021a4-104">Leadspace é unha empresa de ciencia de datos que proporciona unha plataforma de datos de clientes B2B.</span><span class="sxs-lookup"><span data-stu-id="021a4-104">Leadspace is a data science company that provides a B2B Customer Data Platform.</span></span> <span data-ttu-id="021a4-105">Permite aos clientes con perfís de clientes unificados para empresas enriquecer os seus datos.</span><span class="sxs-lookup"><span data-stu-id="021a4-105">It enables customers with unified customer profiles for companies to enrich their data.</span></span> <span data-ttu-id="021a4-106">Os enriquecementos incluíen atributos adicionais, como o tamaño da empresa, a localización o sector e moito máis.</span><span class="sxs-lookup"><span data-stu-id="021a4-106">Enrichments include additional attributes such as company size, location, industry, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="021a4-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="021a4-107">Prerequisites</span></span>

<span data-ttu-id="021a4-108">Para configurar Leadspace, deben cumprirse os seguintes requisitos previos:</span><span class="sxs-lookup"><span data-stu-id="021a4-108">To configure Leadspace, the following prerequisites must be met:</span></span>

- <span data-ttu-id="021a4-109">Ten unha licenza de Leadspace activa e a "clave perpetua" (coñecida como **Token de Leadspace**).</span><span class="sxs-lookup"><span data-stu-id="021a4-109">You have an active Leadspace license and the “perpetual key” (referred to as **Leadspace token**).</span></span> <span data-ttu-id="021a4-110">Contacte directamente con [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) para obter máis detalles sobre o seu produto.</span><span class="sxs-lookup"><span data-stu-id="021a4-110">Contact directly [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) for details about their product.</span></span>
- <span data-ttu-id="021a4-111">Ten permisos de [administrador](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="021a4-111">You have [Administrator](permissions.md#administrator) permissions.</span></span>
- <span data-ttu-id="021a4-112">Ten [perfís de clientes unificados](customer-profiles.md) para empresas.</span><span class="sxs-lookup"><span data-stu-id="021a4-112">You have [unified customer profiles](customer-profiles.md) for companies.</span></span>

## <a name="configuration"></a><span data-ttu-id="021a4-113">Configuración</span><span class="sxs-lookup"><span data-stu-id="021a4-113">Configuration</span></span>

1. <span data-ttu-id="021a4-114">Na información do público, vaia a **Datos** > **Enriquecemento**.</span><span class="sxs-lookup"><span data-stu-id="021a4-114">In audience insights, go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="021a4-115">Seleccione **Enriquecer os meus datos** no mosaico de Leadspace.</span><span class="sxs-lookup"><span data-stu-id="021a4-115">Select **Enrich my data** on the Leadspace tile.</span></span>

   :::image type="content" source="media/leadspace-tile.png" alt-text="Captura de pantalla do mosaico de Leadspace.":::

1. <span data-ttu-id="021a4-117">Seleccione **Comezar** e logo introduza un **Token de Leadspace** (clave perpetua) activo.</span><span class="sxs-lookup"><span data-stu-id="021a4-117">Select **Get Started** and then enter an active **Leadspace token** (perpetual key).</span></span> <span data-ttu-id="021a4-118">Revise e proporcione o seu consentimento para a **Privacidade e cumprimento dos datos** seleccionando a caixa de verificación **Estou de acordo**.</span><span class="sxs-lookup"><span data-stu-id="021a4-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> <span data-ttu-id="021a4-119">Confirme ambas as entradas seleccionando **Conectarse a Leadspace**.</span><span class="sxs-lookup"><span data-stu-id="021a4-119">Confirm both inputs by selecting **Connect to Leadspace**.</span></span>

1. <span data-ttu-id="021a4-120">Seleccione **Asignar datos** e escolla o conxunto de datos que desexa enriquecer cos datos da empresa de Leadspace.</span><span class="sxs-lookup"><span data-stu-id="021a4-120">Select **Map data** and choose the data set you want to enrich with company data from Leadspace.</span></span> <span data-ttu-id="021a4-121">Pode seleccionar a entidade *Cliente* para enriquecer todos os seus perfís de clientes ou seleccione unha entidade de segmento para enriquecer só os perfís de clientes contidos nese segmento.</span><span class="sxs-lookup"><span data-stu-id="021a4-121">You can select the *Customer* entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

   :::image type="content" source="media/enrichment-leadspace-select-segment.png" alt-text="Elixa entre o perfil do cliente e o enriquecemento do segmento.":::

1. <span data-ttu-id="021a4-123">Seleccione **Seguinte** e defina os campos dos perfís unificados que se deben empregar para buscar os datos da empresa coincidentes de Leadspace.</span><span class="sxs-lookup"><span data-stu-id="021a4-123">Click **Next** and define which fields from your unified profiles should be used to look for matching company data from Leadspace.</span></span> <span data-ttu-id="021a4-124">O campo **Nome da empresa** é obrigatorio.</span><span class="sxs-lookup"><span data-stu-id="021a4-124">The **Name of company** field is required.</span></span> <span data-ttu-id="021a4-125">Para unha maior precisión de coincidencia, ata outros dous campos, **Páxina web da empresa** e **Localización da empresa**, pódense engadir.</span><span class="sxs-lookup"><span data-stu-id="021a4-125">For a higher match accuracy, up to two other fields, **Company website** and **Company location**, can be added.</span></span>

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Panel de asignación de campos de Leadspace.":::
   
1. <span data-ttu-id="021a4-127">Seleccione **Aplicar** para completar a asignación de campos.</span><span class="sxs-lookup"><span data-stu-id="021a4-127">Select **Apply** to complete the field mapping.</span></span>

1. <span data-ttu-id="021a4-128">Seleccione **Executar** para enriquecer os perfís da empresa.</span><span class="sxs-lookup"><span data-stu-id="021a4-128">Select **Run** to enrich the company profiles.</span></span> <span data-ttu-id="021a4-129">O tempo que leva un enriquecemento depende do número de perfís de clientes unificados.</span><span class="sxs-lookup"><span data-stu-id="021a4-129">How long an enrichment takes depends on the number of unified customer profiles.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="021a4-130">Resultados de enriquecemento</span><span class="sxs-lookup"><span data-stu-id="021a4-130">Enrichment results</span></span>

<span data-ttu-id="021a4-131">Despois de actualizar o enriquecemento, pode revisar os datos da empresa enriquecidos recentemente en [Os meus enriquecementos](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="021a4-131">After refreshing the enrichment, you can review the newly enriched company data under [My enrichments](enrichment-hub.md).</span></span> <span data-ttu-id="021a4-132">Pode atopar a hora da última actualización e o número de perfís enriquecidos.</span><span class="sxs-lookup"><span data-stu-id="021a4-132">You can find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="021a4-133">Pode acceder a unha vista detallada de cada perfil enriquecido seleccionando **Ver datos enriquecidos**.</span><span class="sxs-lookup"><span data-stu-id="021a4-133">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

<span data-ttu-id="021a4-134">Para obter máis información, consulte [API de Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span><span class="sxs-lookup"><span data-stu-id="021a4-134">For more information, see [Leadspace APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span></span>

## <a name="next-steps"></a><span data-ttu-id="021a4-135">Pasos seguintes</span><span class="sxs-lookup"><span data-stu-id="021a4-135">Next steps</span></span>

<span data-ttu-id="021a4-136">Crear sobre os seus datos enriquecidos de clientes.</span><span class="sxs-lookup"><span data-stu-id="021a4-136">Build on top of your enriched customer data.</span></span> <span data-ttu-id="021a4-137">Cree [segmentos](segments.md), [medidas](measures.md) e incluso [exporte os datos](export-destinations.md) para ofrecer experiencias personalizadas aos seus clientes.</span><span class="sxs-lookup"><span data-stu-id="021a4-137">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="021a4-138">Cumprimento e privacidade dos datos</span><span class="sxs-lookup"><span data-stu-id="021a4-138">Data privacy and compliance</span></span>

<span data-ttu-id="021a4-139">Cando habilita Dynamics 365 Customer Insights para transmitir datos a Leadspace, permite a transferencia de datos fóra do límite de cumprimento de Dynamics 365 Customer Insights, incluíndo datos potencialmente confidenciais como os datos persoais.</span><span class="sxs-lookup"><span data-stu-id="021a4-139">When you enable Dynamics 365 Customer Insights to transmit data to Leadspace, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="021a4-140">Microsoft transferirá estes datos segundo a súa instrución, pero vostede é responsable de garantir que Leadspace cumpra as obrigas de privacidade ou seguridade que poida ter.</span><span class="sxs-lookup"><span data-stu-id="021a4-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Leadspace meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="021a4-141">Para obter máis información, consulte a [Declaración de privacidade de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="021a4-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="021a4-142">O administrador de Dynamics 365 Customer Insights pode eliminar este enriquecemento en calquera momento para interromper o uso desta funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="021a4-142">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]