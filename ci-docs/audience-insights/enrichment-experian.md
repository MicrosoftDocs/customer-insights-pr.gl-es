---
title: Enriquecemento co enriquecemento de terceiros de Experian
description: Información xeral sobre o enriquecemento de terceiros de Experian.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 9cf2a7fa18ecc022ea67f6829f52381ad59f3172
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896371"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="19edc-103">Enriquecer os perfís de clientes con datos demográficos de Experian (previsualización)</span><span class="sxs-lookup"><span data-stu-id="19edc-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="19edc-104">Experian é líder mundial en servizos de márketing e informes de crédito para consumidores e empresas.</span><span class="sxs-lookup"><span data-stu-id="19edc-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="19edc-105">Cos servizos de enriquecemento de datos de Experian, pode adquirir unha comprensión máis profunda dos seus clientes enriquecendo os perfís dos seus clientes con datos demográficos como o tamaño do fogar, os ingresos e moito máis.</span><span class="sxs-lookup"><span data-stu-id="19edc-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="19edc-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="19edc-106">Prerequisites</span></span>

<span data-ttu-id="19edc-107">Para configurar Experian, deben cumprirse os seguintes requisitos previos:</span><span class="sxs-lookup"><span data-stu-id="19edc-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="19edc-108">Vostede ten unha subscrición a Experian activa.</span><span class="sxs-lookup"><span data-stu-id="19edc-108">You have an active Experian subscription.</span></span> <span data-ttu-id="19edc-109">Para obter unha subscrición, [contacte con Experian](https://www.experian.com/marketing-services/contact) directamente.</span><span class="sxs-lookup"><span data-stu-id="19edc-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="19edc-110">[Máis información sobre o enriquecemento de información de Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="19edc-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>

- <span data-ttu-id="19edc-111">Un administrador configurou xa unha conexión de Experian *ou* ten permisos de [administrador](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="19edc-111">An Experian connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="19edc-112">Tamén precisa o ID de usuario, o ID de grupo e o número de modelo da súa conta de transporte seguro (ST) habilitada para SSH que Experian creou para vostede.</span><span class="sxs-lookup"><span data-stu-id="19edc-112">You also need the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="19edc-113">Configurar o enriquecemento</span><span class="sxs-lookup"><span data-stu-id="19edc-113">Configure the enrichment</span></span>

1. <span data-ttu-id="19edc-114">Vaia a **Datos** > **Enriquecemento** e seleccione o separador **Descubrir**.</span><span class="sxs-lookup"><span data-stu-id="19edc-114">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="19edc-115">Seleccione **Enriquece os meus datos** no mosaico de Experian.</span><span class="sxs-lookup"><span data-stu-id="19edc-115">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="19edc-116">![Mosaico de Experian](media/experian-tile.png "Mosaico de Experian")</span><span class="sxs-lookup"><span data-stu-id="19edc-116">![Experian tile](media/experian-tile.png "Experian tile")</span></span>
   > 

1. <span data-ttu-id="19edc-117">Seleccione unha [conexión](connections.md) da lista despregable.</span><span class="sxs-lookup"><span data-stu-id="19edc-117">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="19edc-118">Póñase en contacto cun administrador se non hai conexión dispoñible.</span><span class="sxs-lookup"><span data-stu-id="19edc-118">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="19edc-119">Se é administrador, pode crear unha conexión seleccionando **Engadir conexión** e escollendo Experian desde o menú despregable.</span><span class="sxs-lookup"><span data-stu-id="19edc-119">If you are an administrator, you can create a connection by selecting **Add connection** and choosing Experian from the drop-down.</span></span> 

1. <span data-ttu-id="19edc-120">Seleccione **Conectar con Experian** para confirmar a selección da conexión.</span><span class="sxs-lookup"><span data-stu-id="19edc-120">Select **Connect to Experian** to confirm the connection selection.</span></span>

1.  <span data-ttu-id="19edc-121">Seleccione **Seguinte** e escolla o **Conxunto de datos do cliente** que quere enriquecer cos datos demográficos de Experian.</span><span class="sxs-lookup"><span data-stu-id="19edc-121">Select **Next** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="19edc-122">Pode seleccionar a entidade **Cliente** para enriquecer todos os seus perfís de clientes ou seleccione unha entidade de segmento para enriquecer só os perfís de clientes contidos nese segmento.</span><span class="sxs-lookup"><span data-stu-id="19edc-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Captura de pantalla ao escoller o conxunto de datos do cliente.":::

1. <span data-ttu-id="19edc-124">Seleccione **Seguinte** e defina o tipo de campos dos perfís unificados que se debe usar para buscar os datos demográficos coincidentes de Experian.</span><span class="sxs-lookup"><span data-stu-id="19edc-124">Select **Next** and define which type of fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="19edc-125">Polo menos un dos campos **Nome e enderezo**, **Teléfono** ou **Correo electrónico** é requerido.</span><span class="sxs-lookup"><span data-stu-id="19edc-125">At least one of the fields **Name and address**, **Phone**, or **Email** is required.</span></span> <span data-ttu-id="19edc-126">Para unha maior precisión de coincidencia, pódense engadir ata outros dous campos.</span><span class="sxs-lookup"><span data-stu-id="19edc-126">For a higher match accuracy, up to two other fields can be added.</span></span> <span data-ttu-id="19edc-127">Esta selección afectará aos campos de asignación aos que ten acceso no seguinte paso.</span><span class="sxs-lookup"><span data-stu-id="19edc-127">This selection will affect the mapping fields you have access to in the next step.</span></span>

    > [!TIP]
    > <span data-ttu-id="19edc-128">É probable que máis atributos de identificadores clave enviados a Experian produzan unha maior taxa de coincidencia.</span><span class="sxs-lookup"><span data-stu-id="19edc-128">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="19edc-129">Seleccione **Seguinte** para iniciar a asignación dos campos.</span><span class="sxs-lookup"><span data-stu-id="19edc-129">Select **Next** to start the field mapping.</span></span>

1. <span data-ttu-id="19edc-130">Defina que campos dos perfís unificados se deben usar para buscar os datos demográficos coincidentes de Experian.</span><span class="sxs-lookup"><span data-stu-id="19edc-130">Define which fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="19edc-131">Os campos necesarios están marcados.</span><span class="sxs-lookup"><span data-stu-id="19edc-131">Required fields are marked.</span></span>

1. <span data-ttu-id="19edc-132">Proporcione un nome para o enriquecemento e un nome para a entidade de saída.</span><span class="sxs-lookup"><span data-stu-id="19edc-132">Provide a name for the enrichment and a name for the output entity.</span></span>

1. <span data-ttu-id="19edc-133">Seleccione **Gardar enriquecemento** despois de revisar as súas opcións.</span><span class="sxs-lookup"><span data-stu-id="19edc-133">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-experian"></a><span data-ttu-id="19edc-134">Configurar a conexión de Experian</span><span class="sxs-lookup"><span data-stu-id="19edc-134">Configure the connection for Experian</span></span> 

<span data-ttu-id="19edc-135">Debe ser administrador para configurar as conexións.</span><span class="sxs-lookup"><span data-stu-id="19edc-135">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="19edc-136">Seleccione **Engadir conexión** ao configurar un enriquecemento *ou* vaia a **Administrar** > **Conexións** e seleccione **Configurar** no mosaico de Experian.</span><span class="sxs-lookup"><span data-stu-id="19edc-136">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Experian tile.</span></span>

1. <span data-ttu-id="19edc-137">Seleccione **Comezar**.</span><span class="sxs-lookup"><span data-stu-id="19edc-137">Select **Get Started**.</span></span>

1. <span data-ttu-id="19edc-138">Introduza un nome para a conexión na caixa **Nome de visualización**.</span><span class="sxs-lookup"><span data-stu-id="19edc-138">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="19edc-139">Introduza un ID de usuario, un ID de grupo e un número de modelo válidos para a súa conta de Transporte seguro de Experian.</span><span class="sxs-lookup"><span data-stu-id="19edc-139">Enter valid User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span>

1. <span data-ttu-id="19edc-140">Revise e proporcione o seu consentimento para a **Privacidade de datos e cumprimento** seleccionando a caixa de verificación **Estou de acordo**</span><span class="sxs-lookup"><span data-stu-id="19edc-140">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox</span></span>

1. <span data-ttu-id="19edc-141">Seleccione **Verificar** para validar a configuración.</span><span class="sxs-lookup"><span data-stu-id="19edc-141">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="19edc-142">Despois de completar a verificación, seleccione **Gardar**.</span><span class="sxs-lookup"><span data-stu-id="19edc-142">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Panel de configuración da conexión de Experian.":::

## <a name="enrichment-results"></a><span data-ttu-id="19edc-144">Resultados de enriquecemento</span><span class="sxs-lookup"><span data-stu-id="19edc-144">Enrichment results</span></span>

<span data-ttu-id="19edc-145">Para iniciar o proceso de enriquecemento, seleccione **Executar** na barra de comandos.</span><span class="sxs-lookup"><span data-stu-id="19edc-145">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="19edc-146">Tamén pode deixar que o sistema execute o enriquecemento automaticamente como parte dunha [actualización programada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="19edc-146">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="19edc-147">O tempo de procesamento dependerá do tamaño dos datos dos seus clientes e dos procesos de enriquecemento configurados para Experian na súa conta.</span><span class="sxs-lookup"><span data-stu-id="19edc-147">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="19edc-148">Despois de completar o proceso de enriquecemento, pode consultar os datos dos perfís de clientes recentemente enriquecidos en **Os meus enriquecementos**.</span><span class="sxs-lookup"><span data-stu-id="19edc-148">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="19edc-149">Ademais, atopará a hora da última actualización e o número de perfís enriquecidos.</span><span class="sxs-lookup"><span data-stu-id="19edc-149">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="19edc-150">Pode acceder a unha vista detallada de cada perfil enriquecido seleccionando **Ver datos enriquecidos**.</span><span class="sxs-lookup"><span data-stu-id="19edc-150">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="19edc-151">Pasos seguintes</span><span class="sxs-lookup"><span data-stu-id="19edc-151">Next steps</span></span>

<span data-ttu-id="19edc-152">Crear sobre os seus datos enriquecidos de clientes.</span><span class="sxs-lookup"><span data-stu-id="19edc-152">Build on top of your enriched customer data.</span></span> <span data-ttu-id="19edc-153">Cree [segmentos](segments.md), [medidas](measures.md) e incluso [exporte os datos](export-destinations.md) para ofrecer experiencias personalizadas aos seus clientes.</span><span class="sxs-lookup"><span data-stu-id="19edc-153">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="19edc-154">Cumprimento e privacidade dos datos</span><span class="sxs-lookup"><span data-stu-id="19edc-154">Data privacy and compliance</span></span>

<span data-ttu-id="19edc-155">Cando habilita Dynamics 365 Customer Insights para transmitir datos a Experian, permite a transferencia de datos fóra do límite de cumprimento de Dynamics 365 Customer Insights, incluíndo datos potencialmente confidenciais como os datos persoais.</span><span class="sxs-lookup"><span data-stu-id="19edc-155">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="19edc-156">Microsoft transferirá estes datos segundo a súa instrución, pero vostede é responsable de garantir que Experian cumpra as obrigas de privacidade ou seguridade que poida ter.</span><span class="sxs-lookup"><span data-stu-id="19edc-156">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="19edc-157">Para obter máis información, consulte a [Declaración de privacidade de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="19edc-157">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="19edc-158">O administrador de Dynamics 365 Customer Insights pode eliminar este enriquecemento en calquera momento para interromper o uso desta funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="19edc-158">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
