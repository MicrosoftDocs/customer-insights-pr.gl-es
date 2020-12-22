---
title: Enriquecemento de perfís de empresa co enriquecemento de terceiros de Leadspace
description: Información xeral sobre o enriquecemento de terceiros de Leadspace.
ms.date: 11/24/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 1b5c6e46e8e424df83e855d81fc4dd7ecb394e3c
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668721"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a><span data-ttu-id="f6f12-103">Enriquecemento de perfís de empresa con Leadspace (vista previa)</span><span class="sxs-lookup"><span data-stu-id="f6f12-103">Enrichment of company profiles with Leadspace (preview)</span></span>

<span data-ttu-id="f6f12-104">Leadspace é unha empresa de ciencia de datos que proporciona unha plataforma de datos de clientes B2B.</span><span class="sxs-lookup"><span data-stu-id="f6f12-104">Leadspace is a data science company that provides a B2B Customer Data Platform.</span></span> <span data-ttu-id="f6f12-105">Permite aos clientes con perfís de clientes unificados para empresas enriquecer os seus datos.</span><span class="sxs-lookup"><span data-stu-id="f6f12-105">It enables customers with unified customer profiles for companies to enrich their data.</span></span> <span data-ttu-id="f6f12-106">Os enriquecementos incluíen atributos adicionais, como o tamaño da empresa, a localización o sector e moito máis.</span><span class="sxs-lookup"><span data-stu-id="f6f12-106">Enrichments include additional attributes such as company size, location, industry, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f6f12-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="f6f12-107">Prerequisites</span></span>

<span data-ttu-id="f6f12-108">Para configurar Leadspace, deben cumprirse os seguintes requisitos previos:</span><span class="sxs-lookup"><span data-stu-id="f6f12-108">To configure Leadspace, the following prerequisites must be met:</span></span>

- <span data-ttu-id="f6f12-109">Ten unha licenza de Leadspace activa e a "clave perpetua" (coñecida como **Token de Leadspace**).</span><span class="sxs-lookup"><span data-stu-id="f6f12-109">You have an active Leadspace license and the “perpetual key” (referred to as **Leadspace token**).</span></span> <span data-ttu-id="f6f12-110">Contacte directamente con [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) para obter máis detalles sobre o seu produto.</span><span class="sxs-lookup"><span data-stu-id="f6f12-110">Contact directly [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) for details about their product.</span></span>
- <span data-ttu-id="f6f12-111">Ten permisos de [administrador](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="f6f12-111">You have [Administrator](permissions.md#administrator) permissions.</span></span>
- <span data-ttu-id="f6f12-112">Ten [perfís de clientes unificados](customer-profiles.md) para empresas.</span><span class="sxs-lookup"><span data-stu-id="f6f12-112">You have [unified customer profiles](customer-profiles.md) for companies.</span></span>

## <a name="configuration"></a><span data-ttu-id="f6f12-113">Configuración</span><span class="sxs-lookup"><span data-stu-id="f6f12-113">Configuration</span></span>

1. <span data-ttu-id="f6f12-114">Na información do público, vaia a **Datos** > **Enriquecemento**.</span><span class="sxs-lookup"><span data-stu-id="f6f12-114">In audience insights, go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="f6f12-115">Seleccione **Enriquecer os meus datos** no mosaico de Leadspace.</span><span class="sxs-lookup"><span data-stu-id="f6f12-115">Select **Enrich my data** on the Leadspace tile.</span></span>

   :::image type="content" source="media/leadspace-tile.png" alt-text="Captura de pantalla do mosaico de Leadspace.":::

1. <span data-ttu-id="f6f12-117">Seleccione **Comezar** e logo introduza un **Token de Leadspace** (clave perpetua) activo.</span><span class="sxs-lookup"><span data-stu-id="f6f12-117">Select **Get Started** and then enter an active **Leadspace token** (perpetual key).</span></span> <span data-ttu-id="f6f12-118">Revise e proporcione o seu consentimento para a **Privacidade e cumprimento dos datos** seleccionando a caixa de verificación **Estou de acordo**.</span><span class="sxs-lookup"><span data-stu-id="f6f12-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> <span data-ttu-id="f6f12-119">Confirme ambas as entradas seleccionando **Conectarse a Leadspace**.</span><span class="sxs-lookup"><span data-stu-id="f6f12-119">Confirm both inputs by selecting **Connect to Leadspace**.</span></span>

1. <span data-ttu-id="f6f12-120">Seleccione **Asignar datos** e defina os campos dos perfís unificados que se deben empregar para buscar os datos da empresa coincidentes de Leadspace.</span><span class="sxs-lookup"><span data-stu-id="f6f12-120">Select **Map data** and define which fields from your unified profiles should be used to look for matching company data from Leadspace.</span></span> <span data-ttu-id="f6f12-121">O campo **Nome da empresa** é obrigatorio.</span><span class="sxs-lookup"><span data-stu-id="f6f12-121">The **Name of company** field is required.</span></span> <span data-ttu-id="f6f12-122">Para unha maior precisión de coincidencia, ata outros dous campos, **Páxina web da empresa** e **Localización da empresa**, pódense engadir.</span><span class="sxs-lookup"><span data-stu-id="f6f12-122">For a higher match accuracy, up to two other fields, **Company website** and **Company location**, can be added.</span></span>

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Panel de asignación de campos de Leadspace.":::
   
1. <span data-ttu-id="f6f12-124">Seleccione **Aplicar** para completar a asignación de campos.</span><span class="sxs-lookup"><span data-stu-id="f6f12-124">Select **Apply** to complete the field mapping.</span></span>

1. <span data-ttu-id="f6f12-125">Seleccione **Executar** para enriquecer os perfís da empresa.</span><span class="sxs-lookup"><span data-stu-id="f6f12-125">Select **Run** to enrich the company profiles.</span></span> <span data-ttu-id="f6f12-126">O tempo que leva un enriquecemento depende do número de perfís de clientes unificados.</span><span class="sxs-lookup"><span data-stu-id="f6f12-126">How long an enrichment takes depends on the number of unified customer profiles.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="f6f12-127">Resultados de enriquecemento</span><span class="sxs-lookup"><span data-stu-id="f6f12-127">Enrichment results</span></span>

<span data-ttu-id="f6f12-128">Despois de actualizar o enriquecemento, pode revisar os datos da empresa enriquecidos recentemente en [Os meus enriquecementos](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="f6f12-128">After refreshing the enrichment, you can review the newly enriched company data under [My enrichments](enrichment-hub.md).</span></span> <span data-ttu-id="f6f12-129">Pode atopar a hora da última actualización e o número de perfís enriquecidos.</span><span class="sxs-lookup"><span data-stu-id="f6f12-129">You can find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="f6f12-130">Pode acceder a unha vista detallada de cada perfil enriquecido seleccionando **Ver datos enriquecidos**.</span><span class="sxs-lookup"><span data-stu-id="f6f12-130">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

<span data-ttu-id="f6f12-131">Para obter máis información, consulte [API de Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span><span class="sxs-lookup"><span data-stu-id="f6f12-131">For more information, see [Leadspace APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span></span>

## <a name="next-steps"></a><span data-ttu-id="f6f12-132">Pasos seguintes</span><span class="sxs-lookup"><span data-stu-id="f6f12-132">Next steps</span></span>

<span data-ttu-id="f6f12-133">Crear sobre os seus datos enriquecidos de clientes.</span><span class="sxs-lookup"><span data-stu-id="f6f12-133">Build on top of your enriched customer data.</span></span> <span data-ttu-id="f6f12-134">Cree [segmentos](segments.md), [medidas](measures.md) e incluso [exporte os datos](export-destinations.md) para ofrecer experiencias personalizadas aos seus clientes.</span><span class="sxs-lookup"><span data-stu-id="f6f12-134">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="f6f12-135">Cumprimento e privacidade dos datos</span><span class="sxs-lookup"><span data-stu-id="f6f12-135">Data privacy and compliance</span></span>

<span data-ttu-id="f6f12-136">Cando habilita Dynamics 365 Customer Insights para transmitir datos a Leadspace, permite a transferencia de datos fóra do límite de cumprimento de Dynamics 365 Customer Insights, incluíndo datos potencialmente confidenciais como os datos persoais.</span><span class="sxs-lookup"><span data-stu-id="f6f12-136">When you enable Dynamics 365 Customer Insights to transmit data to Leadspace, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="f6f12-137">Microsoft transferirá estes datos segundo a súa instrución, pero vostede é responsable de garantir que Leadspace cumpra as obrigas de privacidade ou seguridade que poida ter.</span><span class="sxs-lookup"><span data-stu-id="f6f12-137">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Leadspace meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="f6f12-138">Para obter máis información, consulte a [Declaración de privacidade de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="f6f12-138">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="f6f12-139">O administrador de Dynamics 365 Customer Insights pode eliminar este enriquecemento en calquera momento para interromper o uso desta funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="f6f12-139">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>