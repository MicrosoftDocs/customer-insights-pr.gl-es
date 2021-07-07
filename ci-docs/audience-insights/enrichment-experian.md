---
title: Enriquecemento co enriquecemento de terceiros Experian
description: Información xeral sobre o enriquecemento de terceiros Experian.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 7c82fe92b3351a782a4fa6510300d870b742d042
ms.sourcegitcommit: 42b3bce1e20e7cc707d232844dacfeed3d6fc096
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 06/28/2021
ms.locfileid: "6309818"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="625d4-103">Enriqueza os perfís de clientes con datos demográficos de Experian (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="625d4-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="625d4-104">Experian é líder mundial en servizos de mercadotecnia e informes de crédito ao consumidor e ás empresas.</span><span class="sxs-lookup"><span data-stu-id="625d4-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="625d4-105">Cos servizos de enriquecemento de datos de Experian, pode construír unha comprensión máis profunda dos seus clientes enriquecendo os perfís dos seus clientes con datos demográficos como tamaño do fogar, ingresos e moito máis.</span><span class="sxs-lookup"><span data-stu-id="625d4-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="625d4-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="625d4-106">Prerequisites</span></span>

<span data-ttu-id="625d4-107">Para configurar Experian, deben cumprirse os seguintes requisitos previos:</span><span class="sxs-lookup"><span data-stu-id="625d4-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="625d4-108">Debe ter unha subscrición activa de Experian.</span><span class="sxs-lookup"><span data-stu-id="625d4-108">You have an active Experian subscription.</span></span> <span data-ttu-id="625d4-109">Para obter unha subscrición, [contacte con Experian](https://www.experian.com/marketing-services/contact) directamente.</span><span class="sxs-lookup"><span data-stu-id="625d4-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="625d4-110">[Obteña máis información acerca do enriquecementos de datos de Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="625d4-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>

- <span data-ttu-id="625d4-111">Un administrador configurou xa unha conexión de Experian *ou* ten permisos de [administrador](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="625d4-111">An Experian connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="625d4-112">Tamén precisa o ID de usuario, o ID de grupo e o número de modelo da súa conta de transporte seguro (ST) con SSH que Experian creou para vostede.</span><span class="sxs-lookup"><span data-stu-id="625d4-112">You also need the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="625d4-113">Países ou rexións compatibles</span><span class="sxs-lookup"><span data-stu-id="625d4-113">Supported countries/regions</span></span>

<span data-ttu-id="625d4-114">Actualmente admítese enriquecer perfís de clientes só nos Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="625d4-114">We currently support enriching customer profiles in the United States only.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="625d4-115">Configurar o enriquecemento</span><span class="sxs-lookup"><span data-stu-id="625d4-115">Configure the enrichment</span></span>

1. <span data-ttu-id="625d4-116">Vaia a **Datos** > **Enriquecemento** e seleccione o separador **Descubrir**.</span><span class="sxs-lookup"><span data-stu-id="625d4-116">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="625d4-117">Seleccione **Enriquecer os meus datos** no mosaico Experian.</span><span class="sxs-lookup"><span data-stu-id="625d4-117">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="625d4-118">![Experian mosaicos](media/experian-tile.png "Experian tile")</span><span class="sxs-lookup"><span data-stu-id="625d4-118">![Experian tile](media/experian-tile.png "Experian tile")</span></span>
   > 

1. <span data-ttu-id="625d4-119">Seleccione unha [conexión](connections.md) da lista despregable.</span><span class="sxs-lookup"><span data-stu-id="625d4-119">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="625d4-120">Póñase en contacto cun administrador se non hai conexión dispoñible.</span><span class="sxs-lookup"><span data-stu-id="625d4-120">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="625d4-121">Se é administrador, pode crear unha conexión seleccionando **Engadir conexión** e escollendo Experian da lista despregable.</span><span class="sxs-lookup"><span data-stu-id="625d4-121">If you are an administrator, you can create a connection by selecting **Add connection** and choosing Experian from the dropdown list.</span></span> 

1. <span data-ttu-id="625d4-122">Seleccione **Conectarse a Experian** para confirmar a selección de conexión.</span><span class="sxs-lookup"><span data-stu-id="625d4-122">Select **Connect to Experian** to confirm the connection selection.</span></span>

1.  <span data-ttu-id="625d4-123">Seleccione **Seguinte** e escolla o **Conxunto de datos do cliente** que quere enriquecer con datos demográficos de Experian.</span><span class="sxs-lookup"><span data-stu-id="625d4-123">Select **Next** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="625d4-124">Pode seleccionar a entidade **Cliente** para enriquecer todos os seus perfís de clientes ou seleccione unha entidade de segmento para enriquecer só os perfís de clientes contidos nese segmento.</span><span class="sxs-lookup"><span data-stu-id="625d4-124">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Captura de pantalla ao escoller o conxunto de datos do cliente.":::

1. <span data-ttu-id="625d4-126">Seleccione **Seguinte** e defina que tipo de campos dos seus perfís unificados se deben empregar para buscar datos demográficos coincidentes de Experian.</span><span class="sxs-lookup"><span data-stu-id="625d4-126">Select **Next** and define which type of fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="625d4-127">Polo menos un dos campos **Nome e enderezo**, **Teléfono** ou **Correo electrónico** é requerido.</span><span class="sxs-lookup"><span data-stu-id="625d4-127">At least one of the fields **Name and address**, **Phone**, or **Email** is required.</span></span> <span data-ttu-id="625d4-128">Para unha maior precisión de coincidencia, pódense engadir ata outros dous campos.</span><span class="sxs-lookup"><span data-stu-id="625d4-128">For a higher match accuracy, up to two other fields can be added.</span></span> <span data-ttu-id="625d4-129">Esta selección afectará aos campos de asignación aos que ten acceso no seguinte paso.</span><span class="sxs-lookup"><span data-stu-id="625d4-129">This selection will affect the mapping fields you have access to in the next step.</span></span>

    > [!TIP]
    > <span data-ttu-id="625d4-130">Enviar máis atributos de identificación claves a Experian é probable que produza unha maior taxa de coincidencia.</span><span class="sxs-lookup"><span data-stu-id="625d4-130">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="625d4-131">Seleccione **Seguinte** para iniciar a asignación dos campos.</span><span class="sxs-lookup"><span data-stu-id="625d4-131">Select **Next** to start the field mapping.</span></span>

1. <span data-ttu-id="625d4-132">Defina que campos dos seus perfís unificados se deben empregar para buscar datos demográficos coincidentes de Experian.</span><span class="sxs-lookup"><span data-stu-id="625d4-132">Define which fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="625d4-133">Os campos necesarios están marcados.</span><span class="sxs-lookup"><span data-stu-id="625d4-133">Required fields are marked.</span></span>

1. <span data-ttu-id="625d4-134">Proporcione un nome para o enriquecemento e un nome para a entidade de saída.</span><span class="sxs-lookup"><span data-stu-id="625d4-134">Provide a name for the enrichment and a name for the output entity.</span></span>

1. <span data-ttu-id="625d4-135">Seleccione **Gardar enriquecemento** despois de revisar as súas opcións.</span><span class="sxs-lookup"><span data-stu-id="625d4-135">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-experian"></a><span data-ttu-id="625d4-136">Configurar a conexión de Experian</span><span class="sxs-lookup"><span data-stu-id="625d4-136">Configure the connection for Experian</span></span> 

<span data-ttu-id="625d4-137">Debe ser administrador para configurar as conexións.</span><span class="sxs-lookup"><span data-stu-id="625d4-137">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="625d4-138">Seleccione **Engadir conexión** ao configurar un enriquecemento *ou* vaia a **Administrar** > **Conexións** e seleccionr **configurar** no mosaico de Experian.</span><span class="sxs-lookup"><span data-stu-id="625d4-138">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Experian tile.</span></span>

1. <span data-ttu-id="625d4-139">Seleccione **Comezar**.</span><span class="sxs-lookup"><span data-stu-id="625d4-139">Select **Get Started**.</span></span>

1. <span data-ttu-id="625d4-140">Introduza un nome para a conexión na caixa **Nome de visualización**.</span><span class="sxs-lookup"><span data-stu-id="625d4-140">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="625d4-141">Introduza un ID de usuario, ID de grupo e número de modelo válidos para a súa conta de transporte seguro de Experian.</span><span class="sxs-lookup"><span data-stu-id="625d4-141">Enter valid User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span>

1. <span data-ttu-id="625d4-142">Revise e proporcione o seu consentimento para a **Privacidade e cumprimento de datos** seleccionando **Estou de acordo**.</span><span class="sxs-lookup"><span data-stu-id="625d4-142">Review and provide your consent for **Data privacy and compliance** by selecting **I agree**.</span></span>

1. <span data-ttu-id="625d4-143">Seleccione **Verificar** para validar a configuración.</span><span class="sxs-lookup"><span data-stu-id="625d4-143">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="625d4-144">Despois de completar a verificación, seleccione **Gardar**.</span><span class="sxs-lookup"><span data-stu-id="625d4-144">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Experian panel de configuración da conexión.":::

## <a name="enrichment-results"></a><span data-ttu-id="625d4-146">Resultados de enriquecemento</span><span class="sxs-lookup"><span data-stu-id="625d4-146">Enrichment results</span></span>

<span data-ttu-id="625d4-147">Para iniciar o proceso de enriquecemento, seleccione **Executar** na barra de comandos.</span><span class="sxs-lookup"><span data-stu-id="625d4-147">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="625d4-148">Tamén pode deixar que o sistema execute o enriquecemento automaticamente como parte dunha [actualización programada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="625d4-148">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="625d4-149">O tempo de procesamento dependerá do tamaño dos datos dos seus clientes e dos procesos de enriquecemento configurados para a súa conta por Experian.</span><span class="sxs-lookup"><span data-stu-id="625d4-149">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="625d4-150">Despois de completar o proceso de enriquecemento, pode consultar os datos dos perfís de clientes recentemente enriquecidos en **Os meus enriquecementos**.</span><span class="sxs-lookup"><span data-stu-id="625d4-150">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="625d4-151">Ademais, atopará a hora da última actualización e o número de perfís enriquecidos.</span><span class="sxs-lookup"><span data-stu-id="625d4-151">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="625d4-152">Pode acceder a unha vista detallada de cada perfil enriquecido seleccionando **Ver datos enriquecidos**.</span><span class="sxs-lookup"><span data-stu-id="625d4-152">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="625d4-153">Pasos seguintes</span><span class="sxs-lookup"><span data-stu-id="625d4-153">Next steps</span></span>

<span data-ttu-id="625d4-154">Crear sobre os seus datos enriquecidos de clientes.</span><span class="sxs-lookup"><span data-stu-id="625d4-154">Build on top of your enriched customer data.</span></span> <span data-ttu-id="625d4-155">Cree [segmentos](segments.md) e [medidas](measures.md), e incluso [exporte os datos](export-destinations.md) para ofrecer experiencias personalizadas aos seus clientes.</span><span class="sxs-lookup"><span data-stu-id="625d4-155">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="625d4-156">Cumprimento e privacidade dos datos</span><span class="sxs-lookup"><span data-stu-id="625d4-156">Data privacy and compliance</span></span>

<span data-ttu-id="625d4-157">Cando permite a Dynamics 365 Customer Insights transmitir datos a Experian, permite a transferencia de datos fóra do límite de cumprimento de Dynamics 365 Customer Insights, incluíndo datos potencialmente confidenciais como os datos persoais.</span><span class="sxs-lookup"><span data-stu-id="625d4-157">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="625d4-158">Microsoft transferirá estes datos segundo a súa instrución, pero vostede é responsable de asegurarse de que Experian cumpre coas obrigacións de privacidade ou seguridade que poida ter.</span><span class="sxs-lookup"><span data-stu-id="625d4-158">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="625d4-159">Para obter máis información, consulte a [Declaración de privacidade de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="625d4-159">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="625d4-160">O administrador de Dynamics 365 Customer Insights pode eliminar este enriquecemento en calquera momento para interromper o uso desta funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="625d4-160">Your Dynamics 365 Customer Insights administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
