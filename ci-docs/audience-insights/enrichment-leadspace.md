---
title: Enriquecemento de perfís de empresa co enriquecemento de terceiros de Leadspace
description: Información xeral sobre o enriquecemento de terceiros de Leadspace.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: ccf4f661ecffb281556a4545b1f26ee809c697cd
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 04/14/2021
ms.locfileid: "5895911"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a><span data-ttu-id="d546a-103">Enriquecemento de perfís de empresa con Leadspace (vista previa)</span><span class="sxs-lookup"><span data-stu-id="d546a-103">Enrichment of company profiles with Leadspace (preview)</span></span>

<span data-ttu-id="d546a-104">Leadspace é unha empresa de ciencia de datos que proporciona unha plataforma de datos de clientes B2B.</span><span class="sxs-lookup"><span data-stu-id="d546a-104">Leadspace is a data science company that provides a B2B Customer Data Platform.</span></span> <span data-ttu-id="d546a-105">Permite aos clientes con perfís de clientes unificados para empresas enriquecer os seus datos.</span><span class="sxs-lookup"><span data-stu-id="d546a-105">It enables customers with unified customer profiles for companies to enrich their data.</span></span> <span data-ttu-id="d546a-106">Os enriquecementos inclúen máis atributos, como o tamaño da empresa, a localización o sector e moito máis.</span><span class="sxs-lookup"><span data-stu-id="d546a-106">Enrichments include more attributes such as company size, location, industry, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d546a-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="d546a-107">Prerequisites</span></span>

<span data-ttu-id="d546a-108">Para configurar Leadspace, deben cumprirse os seguintes requisitos previos:</span><span class="sxs-lookup"><span data-stu-id="d546a-108">To configure Leadspace, the following prerequisites must be met:</span></span>

- <span data-ttu-id="d546a-109">Ten unha licenza de Leadspace activa.</span><span class="sxs-lookup"><span data-stu-id="d546a-109">You have an active Leadspace license.</span></span>
- <span data-ttu-id="d546a-110">Ten [perfís de clientes unificados](customer-profiles.md) para empresas.</span><span class="sxs-lookup"><span data-stu-id="d546a-110">You have [unified customer profiles](customer-profiles.md) for companies.</span></span>
- <span data-ttu-id="d546a-111">Un administrador xa configurou unha conexión de Leadspace ou vostede ten permisos de [administrador](permissions.md#administrator) e a "clave perpetua" (denominada **Token de Leadspace**).</span><span class="sxs-lookup"><span data-stu-id="d546a-111">A Leadspace connection has already been configured by an administrator or you have [administrator](permissions.md#administrator) permissions and the “perpetual key” (referred to as **Leadspace token**).</span></span> <span data-ttu-id="d546a-112">Contacte con [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) directamente para obter detalles sobre o seu produto.</span><span class="sxs-lookup"><span data-stu-id="d546a-112">Contact [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) directly for details about their product.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="d546a-113">Configurar o enriquecemento</span><span class="sxs-lookup"><span data-stu-id="d546a-113">Configure the enrichment</span></span>

1. <span data-ttu-id="d546a-114">Na información do público, vaia a **Datos** > **Enriquecemento**.</span><span class="sxs-lookup"><span data-stu-id="d546a-114">In audience insights, go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="d546a-115">No mosaico de Leadspace, seleccione **Enriquecer os meus datos** e logo seleccione **Comezar**.</span><span class="sxs-lookup"><span data-stu-id="d546a-115">Select **Enrich my data** on the Leadspace tile and select **Get started**.</span></span>

   :::image type="content" source="media/leadspace-tile.png" alt-text="Captura de pantalla do mosaico de Leadspace.":::

1. <span data-ttu-id="d546a-117">Seleccione unha [conexión](connections.md) da lista despregable.</span><span class="sxs-lookup"><span data-stu-id="d546a-117">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="d546a-118">Póñase en contacto cun administrador se non hai conexión dispoñible.</span><span class="sxs-lookup"><span data-stu-id="d546a-118">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="d546a-119">Se é administrador, pode crear unha conexión seleccionando **Engadir conexión** e escollendo **Leadspace**.</span><span class="sxs-lookup"><span data-stu-id="d546a-119">If you are an administrator, you can create a connection by selecting **Add connection** and choosing **Leadspace**.</span></span> 

1. <span data-ttu-id="d546a-120">Seleccione **Conectar con Leadspace** para confirmar a conexión.</span><span class="sxs-lookup"><span data-stu-id="d546a-120">Select **Connect to Leadspace** to confirm the connection.</span></span>

1. <span data-ttu-id="d546a-121">Seleccione **Seguinte** e escolla o **Conxunto de datos do cliente** que quere enriquecer cos datos da empresa de Leadspace.</span><span class="sxs-lookup"><span data-stu-id="d546a-121">Select **Next** and choose the **Customer data set** you want to enrich with company data from Leadspace.</span></span> <span data-ttu-id="d546a-122">Pode seleccionar a entidade **Cliente** para enriquecer todos os seus perfís de clientes ou seleccione unha entidade de segmento para enriquecer só os perfís de clientes contidos nese segmento.</span><span class="sxs-lookup"><span data-stu-id="d546a-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Captura de pantalla ao escoller o conxunto de datos do cliente.":::

1. <span data-ttu-id="d546a-124">Seleccione **Seguinte** e defina os campos dos perfís unificados que se usan para buscar os datos da empresa coincidentes de Leadspace.</span><span class="sxs-lookup"><span data-stu-id="d546a-124">Select **Next** and define which fields from your unified profiles are used to look for matching company data from Leadspace.</span></span> <span data-ttu-id="d546a-125">O campo **Nome da empresa** é obrigatorio.</span><span class="sxs-lookup"><span data-stu-id="d546a-125">The **Name of company** field is required.</span></span> <span data-ttu-id="d546a-126">Para unha maior precisión de coincidencia, ata outros dous campos, **Páxina web da empresa** e **Localización da empresa**, pódense engadir.</span><span class="sxs-lookup"><span data-stu-id="d546a-126">For a higher match accuracy, up to two other fields, **Company website** and **Company location**, can be added.</span></span>

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Panel de asignación de campos de Leadspace.":::

1. <span data-ttu-id="d546a-128">Seleccione **Seguinte** para concluír a asignación do campo.</span><span class="sxs-lookup"><span data-stu-id="d546a-128">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="d546a-129">Indique un nome para o enriquecemento e seleccione **Gardar enriquecemento** despois de revisar as súas opcións.</span><span class="sxs-lookup"><span data-stu-id="d546a-129">Provide a name for the enrichment and select **Save enrichment** after reviewing your choices.</span></span>


## <a name="configure-the-connection-for-leadspace"></a><span data-ttu-id="d546a-130">Configurar a conexión para Leadspace</span><span class="sxs-lookup"><span data-stu-id="d546a-130">Configure the connection for Leadspace</span></span> 

<span data-ttu-id="d546a-131">Debe ser administrador para configurar as conexións.</span><span class="sxs-lookup"><span data-stu-id="d546a-131">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="d546a-132">Seleccione **Engadir conexión** ao configurar un enriquecemento *ou* vaia a **Administrar** > **Conexións** e seleccione **Configurar** no mosaico de Leadspace.</span><span class="sxs-lookup"><span data-stu-id="d546a-132">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Leadspace tile.</span></span>

1. <span data-ttu-id="d546a-133">Seleccione **Comezar**</span><span class="sxs-lookup"><span data-stu-id="d546a-133">Select **Get Started**</span></span> 

1. <span data-ttu-id="d546a-134">Introduza un nome para a conexión na caixa **Nome de visualización**.</span><span class="sxs-lookup"><span data-stu-id="d546a-134">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="d546a-135">Forneza un token de Leadspace válido.</span><span class="sxs-lookup"><span data-stu-id="d546a-135">Provide a valid Leadspace token.</span></span>

1. <span data-ttu-id="d546a-136">Revise e proporcione o seu consentimento para a **Privacidade de datos e cumprimento** seleccionando a caixa de verificación **Estou de acordo**</span><span class="sxs-lookup"><span data-stu-id="d546a-136">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox</span></span>

1. <span data-ttu-id="d546a-137">Seleccione **Verificar** para validar a configuración.</span><span class="sxs-lookup"><span data-stu-id="d546a-137">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="d546a-138">Despois de completar a verificación, seleccione **Gardar**.</span><span class="sxs-lookup"><span data-stu-id="d546a-138">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Páxina de configuración da conexión de Leadspace.":::

## <a name="enrichment-results"></a><span data-ttu-id="d546a-140">Resultados de enriquecemento</span><span class="sxs-lookup"><span data-stu-id="d546a-140">Enrichment results</span></span>

<span data-ttu-id="d546a-141">Despois de actualizar o enriquecemento, pode revisar os datos da empresa enriquecidos recentemente en [Os meus enriquecementos](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="d546a-141">After refreshing the enrichment, you can review the newly enriched company data under [My enrichments](enrichment-hub.md).</span></span> <span data-ttu-id="d546a-142">Pode atopar a hora da última actualización e o número de perfís enriquecidos.</span><span class="sxs-lookup"><span data-stu-id="d546a-142">You can find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="d546a-143">Pode acceder a unha vista detallada de cada perfil enriquecido seleccionando **Ver datos enriquecidos**.</span><span class="sxs-lookup"><span data-stu-id="d546a-143">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

<span data-ttu-id="d546a-144">Para obter máis información, consulte [API de Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span><span class="sxs-lookup"><span data-stu-id="d546a-144">For more information, see [Leadspace APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span></span>

## <a name="next-steps"></a><span data-ttu-id="d546a-145">Pasos seguintes</span><span class="sxs-lookup"><span data-stu-id="d546a-145">Next steps</span></span>

<span data-ttu-id="d546a-146">Crear sobre os seus datos enriquecidos de clientes.</span><span class="sxs-lookup"><span data-stu-id="d546a-146">Build on top of your enriched customer data.</span></span> <span data-ttu-id="d546a-147">Cree [segmentos](segments.md), [medidas](measures.md) e incluso [exporte os datos](export-destinations.md) para ofrecer experiencias personalizadas aos seus clientes.</span><span class="sxs-lookup"><span data-stu-id="d546a-147">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="d546a-148">Cumprimento e privacidade dos datos</span><span class="sxs-lookup"><span data-stu-id="d546a-148">Data privacy and compliance</span></span>

<span data-ttu-id="d546a-149">Cando habilita Dynamics 365 Customer Insights para transmitir datos a Leadspace, permite a transferencia de datos fóra do límite de cumprimento de Dynamics 365 Customer Insights, incluíndo datos potencialmente confidenciais como os datos persoais.</span><span class="sxs-lookup"><span data-stu-id="d546a-149">When you enable Dynamics 365 Customer Insights to transmit data to Leadspace, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="d546a-150">Microsoft transferirá estes datos segundo a súa instrución, pero vostede é responsable de garantir que Leadspace cumpra as obrigas de privacidade ou seguridade que poida ter.</span><span class="sxs-lookup"><span data-stu-id="d546a-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Leadspace meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="d546a-151">Para obter máis información, consulte a [Declaración de privacidade de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="d546a-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="d546a-152">O administrador de Dynamics 365 Customer Insights pode eliminar este enriquecemento en calquera momento para interromper o uso desta funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="d546a-152">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
