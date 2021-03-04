---
title: Enriquecemento co enriquecemento de terceiros de Experian
description: Información xeral sobre o enriquecemento de terceiros de Experian.
ms.date: 12/10/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: baf3cc58a233b70c48fb94ac4a543d162f91bdd1
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269558"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="68acf-103">Enriquecer os perfís de clientes con datos demográficos de Experian (previsualización)</span><span class="sxs-lookup"><span data-stu-id="68acf-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="68acf-104">Experian é líder mundial en servizos de márketing e informes de crédito para consumidores e empresas.</span><span class="sxs-lookup"><span data-stu-id="68acf-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="68acf-105">Cos servizos de enriquecemento de datos de Experian, pode adquirir unha comprensión máis profunda dos seus clientes enriquecendo os perfís dos seus clientes con datos demográficos como o tamaño do fogar, os ingresos e moito máis.</span><span class="sxs-lookup"><span data-stu-id="68acf-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="68acf-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="68acf-106">Prerequisites</span></span>

<span data-ttu-id="68acf-107">Para configurar Experian, deben cumprirse os seguintes requisitos previos:</span><span class="sxs-lookup"><span data-stu-id="68acf-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="68acf-108">Vostede ten unha subscrición a Experian activa.</span><span class="sxs-lookup"><span data-stu-id="68acf-108">You have an active Experian subscription.</span></span> <span data-ttu-id="68acf-109">Para obter unha subscrición, [contacte con Experian](https://www.experian.com/marketing-services/contact) directamente.</span><span class="sxs-lookup"><span data-stu-id="68acf-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="68acf-110">[Máis información sobre o enriquecemento de información de Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="68acf-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>
- <span data-ttu-id="68acf-111">Vostede ten o ID de usuario, o ID de parte e o número de modelo para a súa conta de transporte seguro (ST) compatible con SSH que Experian creou para vostede.</span><span class="sxs-lookup"><span data-stu-id="68acf-111">You have the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>
- <span data-ttu-id="68acf-112">Ten permisos de [administrador](permissions.md#administrator) na información do público.</span><span class="sxs-lookup"><span data-stu-id="68acf-112">You have [Administrator](permissions.md#administrator) permissions in audience insights.</span></span>

## <a name="configuration"></a><span data-ttu-id="68acf-113">Configuración</span><span class="sxs-lookup"><span data-stu-id="68acf-113">Configuration</span></span>

1. <span data-ttu-id="68acf-114">Vaia a **Datos** > **Enriquecemento** e seleccione o separador **Descubrir**.</span><span class="sxs-lookup"><span data-stu-id="68acf-114">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="68acf-115">Seleccione **Enriquece os meus datos** no mosaico de Experian.</span><span class="sxs-lookup"><span data-stu-id="68acf-115">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="68acf-116">![Mosaico de Experian](media/experian-tile.png "Mosaico de Experian")</span><span class="sxs-lookup"><span data-stu-id="68acf-116">![Experian tile](media/experian-tile.png "Experian tile")</span></span>

1. <span data-ttu-id="68acf-117">Seleccione **Comezar** e introduza o ID de usuario, ID de parte e número de modelo para a súa conta de transporte seguro de Experian.</span><span class="sxs-lookup"><span data-stu-id="68acf-117">Select **Get started** and enter the User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span> <span data-ttu-id="68acf-118">Revise e proporcione o seu consentimento para a **Privacidade e cumprimento dos datos** seleccionando a caixa de verificación **Estou de acordo**.</span><span class="sxs-lookup"><span data-stu-id="68acf-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> <span data-ttu-id="68acf-119">Confirme todas as entradas seleccionando **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="68acf-119">Confirm all inputs by selecting **Apply**.</span></span>

## <a name="map-your-fields"></a><span data-ttu-id="68acf-120">Asignar os campos</span><span class="sxs-lookup"><span data-stu-id="68acf-120">Map your fields</span></span>

1.  <span data-ttu-id="68acf-121">Seleccione **Engadir datos** e escolla o **conxunto de datos de cliente** que desexa enriquecer cos datos demográficos de Experian.</span><span class="sxs-lookup"><span data-stu-id="68acf-121">Select **Add data** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="68acf-122">Pode seleccionar a entidade **Cliente** para enriquecer todos os seus perfís de clientes ou seleccione unha entidade de segmento para enriquecer só os perfís de clientes contidos nese segmento.</span><span class="sxs-lookup"><span data-stu-id="68acf-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

1. <span data-ttu-id="68acf-123">Seleccione os seus identificadores clave de **Nome e enderezo**, **Correo electrónico** ou **Teléfono** para enviar a Experian para a resolución de identidade.</span><span class="sxs-lookup"><span data-stu-id="68acf-123">Select your key identifiers from **Name and Address**, **E-mail**, or **Phone** to send to Experian for identity resolution.</span></span>

   > [!TIP]
   > <span data-ttu-id="68acf-124">É probable que máis atributos de identificadores clave enviados a Experian produzan unha maior taxa de coincidencia.</span><span class="sxs-lookup"><span data-stu-id="68acf-124">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="68acf-125">Seleccione **Seguinte** e asigne os atributos correspondentes da súa entidade de cliente unificada para os campos de identificador clave seleccionados.</span><span class="sxs-lookup"><span data-stu-id="68acf-125">Select **Next** and map the corresponding attributes from your unified customer entity for the selected key identifier fields.</span></span>

1. <span data-ttu-id="68acf-126">Seleccione **Engadir atributo** para asignar os atributos adicionais que lle gustaría enviar a Experian.</span><span class="sxs-lookup"><span data-stu-id="68acf-126">Select **Add attribute** to map any additional attributes you would like to send to Experian.</span></span>

1.  <span data-ttu-id="68acf-127">Seleccione **Gardar** para completar a asignación de campos.</span><span class="sxs-lookup"><span data-stu-id="68acf-127">Select **Save** to complete the field mapping.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="68acf-128">![Asignación de campos de Experian](media/experian-field-mapping.png "Asignación de campos de Experian")</span><span class="sxs-lookup"><span data-stu-id="68acf-128">![Experian field mapping](media/experian-field-mapping.png "Experian field mapping")</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="68acf-129">Resultados de enriquecemento</span><span class="sxs-lookup"><span data-stu-id="68acf-129">Enrichment results</span></span>

<span data-ttu-id="68acf-130">Para iniciar o proceso de enriquecemento, seleccione **Executar** na barra de comandos.</span><span class="sxs-lookup"><span data-stu-id="68acf-130">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="68acf-131">Tamén pode deixar que o sistema execute o enriquecemento automaticamente como parte dunha [actualización programada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="68acf-131">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="68acf-132">O tempo de procesamento dependerá do tamaño dos datos dos seus clientes e dos procesos de enriquecemento configurados para Experian na súa conta.</span><span class="sxs-lookup"><span data-stu-id="68acf-132">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="68acf-133">Despois de completar o proceso de enriquecemento, pode consultar os datos dos perfís de clientes recentemente enriquecidos en **Os meus enriquecementos**.</span><span class="sxs-lookup"><span data-stu-id="68acf-133">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="68acf-134">Ademais, atopará a hora da última actualización e o número de perfís enriquecidos.</span><span class="sxs-lookup"><span data-stu-id="68acf-134">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="68acf-135">Pode acceder a unha vista detallada de cada perfil enriquecido seleccionando **Ver datos enriquecidos**.</span><span class="sxs-lookup"><span data-stu-id="68acf-135">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="68acf-136">Pasos seguintes</span><span class="sxs-lookup"><span data-stu-id="68acf-136">Next steps</span></span>

<span data-ttu-id="68acf-137">Crear sobre os seus datos enriquecidos de clientes.</span><span class="sxs-lookup"><span data-stu-id="68acf-137">Build on top of your enriched customer data.</span></span> <span data-ttu-id="68acf-138">Cree [segmentos](segments.md), [medidas](measures.md) e incluso [exporte os datos](export-destinations.md) para ofrecer experiencias personalizadas aos seus clientes.</span><span class="sxs-lookup"><span data-stu-id="68acf-138">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="68acf-139">Cumprimento e privacidade dos datos</span><span class="sxs-lookup"><span data-stu-id="68acf-139">Data privacy and compliance</span></span>

<span data-ttu-id="68acf-140">Cando habilita Dynamics 365 Customer Insights para transmitir datos a Experian, permite a transferencia de datos fóra do límite de cumprimento de Dynamics 365 Customer Insights, incluíndo datos potencialmente confidenciais como os datos persoais.</span><span class="sxs-lookup"><span data-stu-id="68acf-140">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="68acf-141">Microsoft transferirá estes datos segundo a súa instrución, pero vostede é responsable de garantir que Experian cumpra as obrigas de privacidade ou seguridade que poida ter.</span><span class="sxs-lookup"><span data-stu-id="68acf-141">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="68acf-142">Para obter máis información, consulte a [Declaración de privacidade de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="68acf-142">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="68acf-143">O administrador de Dynamics 365 Customer Insights pode eliminar este enriquecemento en calquera momento para interromper o uso desta funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="68acf-143">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]