---
title: Enriquecemento co enriquecemento de terceiros de Experian
description: Información xeral sobre o enriquecemento de terceiros de Experian.
ms.date: 09/17/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 60fc49734e54740e83b47a7028be216a0eb81e49
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668810"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="f2c57-103">Enriquecer os perfís de clientes con datos demográficos de Experian (previsualización)</span><span class="sxs-lookup"><span data-stu-id="f2c57-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="f2c57-104">Experian é líder mundial en servizos de márketing e informes de crédito para consumidores e empresas.</span><span class="sxs-lookup"><span data-stu-id="f2c57-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="f2c57-105">Cos servizos de enriquecemento de datos de Experian, pode adquirir unha comprensión máis profunda dos seus clientes enriquecendo os perfís dos seus clientes con datos demográficos como o tamaño do fogar, os ingresos e moito máis.</span><span class="sxs-lookup"><span data-stu-id="f2c57-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f2c57-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="f2c57-106">Prerequisites</span></span>

<span data-ttu-id="f2c57-107">Para configurar Experian, deben cumprirse os seguintes requisitos previos:</span><span class="sxs-lookup"><span data-stu-id="f2c57-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="f2c57-108">Vostede ten unha subscrición a Experian activa.</span><span class="sxs-lookup"><span data-stu-id="f2c57-108">You have an active Experian subscription.</span></span> <span data-ttu-id="f2c57-109">Para obter unha subscrición, [contacte con Experian](https://www.experian.com/marketing-services/contact) directamente.</span><span class="sxs-lookup"><span data-stu-id="f2c57-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="f2c57-110">[Máis información sobre o enriquecemento de información de Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="f2c57-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>
- <span data-ttu-id="f2c57-111">Vostede ten o ID de usuario, o ID de parte e o número de modelo para a súa conta de transporte seguro (ST) compatible con SSH que Experian creou para vostede.</span><span class="sxs-lookup"><span data-stu-id="f2c57-111">You have the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>
- <span data-ttu-id="f2c57-112">Ten permisos de [administrador](permissions.md#administrator) na información do público.</span><span class="sxs-lookup"><span data-stu-id="f2c57-112">You have [Administrator](permissions.md#administrator) permissions in audience insights.</span></span>

## <a name="configuration"></a><span data-ttu-id="f2c57-113">Configuración</span><span class="sxs-lookup"><span data-stu-id="f2c57-113">Configuration</span></span>

1. <span data-ttu-id="f2c57-114">Vaia a **Datos** > **Enriquecemento** e seleccione o separador **Descubrir**.</span><span class="sxs-lookup"><span data-stu-id="f2c57-114">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="f2c57-115">Seleccione **Enriquece os meus datos** no mosaico de Experian.</span><span class="sxs-lookup"><span data-stu-id="f2c57-115">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f2c57-116">![Mosaico de Experian](media/experian-tile.png "Mosaico de Experian")</span><span class="sxs-lookup"><span data-stu-id="f2c57-116">![Experian tile](media/experian-tile.png "Experian tile")</span></span>

1. <span data-ttu-id="f2c57-117">Seleccione **Comezar** e introduza o ID de usuario, ID de parte e número de modelo para a súa conta de transporte seguro de Experian.</span><span class="sxs-lookup"><span data-stu-id="f2c57-117">Select **Get started** and enter the User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span> <span data-ttu-id="f2c57-118">Revise e proporcione o seu consentimento para a **Privacidade e cumprimento dos datos** seleccionando a caixa de verificación **Estou de acordo**.</span><span class="sxs-lookup"><span data-stu-id="f2c57-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> <span data-ttu-id="f2c57-119">Confirme todas as entradas seleccionando **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="f2c57-119">Confirm all inputs by selecting **Apply**.</span></span>

## <a name="map-your-fields"></a><span data-ttu-id="f2c57-120">Asignar os campos</span><span class="sxs-lookup"><span data-stu-id="f2c57-120">Map your fields</span></span>

1. <span data-ttu-id="f2c57-121">Seleccione **Engadir datos** e escolla os seus identificadores clave de **Nome e enderezo**, **Correo electrónico** ou **Teléfono** que se envían a Experian para a resolución de identidade.</span><span class="sxs-lookup"><span data-stu-id="f2c57-121">Select **Add data** and choose your key identifiers from **Name and Address**, **E-mail**, or **Phone** to send to Experian for identity resolution.</span></span>

   > [!TIP]
   > <span data-ttu-id="f2c57-122">É probable que máis atributos de identificadores clave enviados a Experian produzan unha maior taxa de coincidencia.</span><span class="sxs-lookup"><span data-stu-id="f2c57-122">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="f2c57-123">Seleccione **Seguinte** e asigne os atributos correspondentes da súa entidade de cliente unificada para os campos de identificador clave seleccionados.</span><span class="sxs-lookup"><span data-stu-id="f2c57-123">Select **Next** and map the corresponding attributes from your unified customer entity for the selected key identifier fields.</span></span>

1. <span data-ttu-id="f2c57-124">Seleccione **Engadir atributo** para asignar os atributos adicionais que lle gustaría enviar a Experian.</span><span class="sxs-lookup"><span data-stu-id="f2c57-124">Select **Add attribute** to map any additional attributes you would like to send to Experian.</span></span>

1.  <span data-ttu-id="f2c57-125">Seleccione **Gardar** para completar a asignación de campos.</span><span class="sxs-lookup"><span data-stu-id="f2c57-125">Select **Save** to complete the field mapping.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f2c57-126">![Asignación de campos de Experian](media/experian-field-mapping.png "Asignación de campos de Experian")</span><span class="sxs-lookup"><span data-stu-id="f2c57-126">![Experian field mapping](media/experian-field-mapping.png "Experian field mapping")</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="f2c57-127">Resultados de enriquecemento</span><span class="sxs-lookup"><span data-stu-id="f2c57-127">Enrichment results</span></span>

<span data-ttu-id="f2c57-128">Para iniciar o proceso de enriquecemento, seleccione **Executar** na barra de comandos.</span><span class="sxs-lookup"><span data-stu-id="f2c57-128">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="f2c57-129">Tamén pode deixar que o sistema execute o enriquecemento automaticamente como parte dunha [actualización programada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="f2c57-129">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="f2c57-130">O tempo de procesamento dependerá do tamaño dos datos dos seus clientes e dos procesos de enriquecemento configurados para Experian na súa conta.</span><span class="sxs-lookup"><span data-stu-id="f2c57-130">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="f2c57-131">Despois de completar o proceso de enriquecemento, pode consultar os datos dos perfís de clientes recentemente enriquecidos en **Os meus enriquecementos**.</span><span class="sxs-lookup"><span data-stu-id="f2c57-131">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="f2c57-132">Ademais, atopará a hora da última actualización e o número de perfís enriquecidos.</span><span class="sxs-lookup"><span data-stu-id="f2c57-132">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="f2c57-133">Pode acceder a unha vista detallada de cada perfil enriquecido seleccionando **Ver datos enriquecidos**.</span><span class="sxs-lookup"><span data-stu-id="f2c57-133">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f2c57-134">Pasos seguintes</span><span class="sxs-lookup"><span data-stu-id="f2c57-134">Next steps</span></span>

<span data-ttu-id="f2c57-135">Crear sobre os seus datos enriquecidos de clientes.</span><span class="sxs-lookup"><span data-stu-id="f2c57-135">Build on top of your enriched customer data.</span></span> <span data-ttu-id="f2c57-136">Cree [segmentos](segments.md), [medidas](measures.md) e incluso [exporte os datos](export-destinations.md) para ofrecer experiencias personalizadas aos seus clientes.</span><span class="sxs-lookup"><span data-stu-id="f2c57-136">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="f2c57-137">Cumprimento e privacidade dos datos</span><span class="sxs-lookup"><span data-stu-id="f2c57-137">Data privacy and compliance</span></span>

<span data-ttu-id="f2c57-138">Cando habilita Dynamics 365 Customer Insights para transmitir datos a Experian, permite a transferencia de datos fóra do límite de cumprimento de Dynamics 365 Customer Insights, incluíndo datos potencialmente confidenciais como os datos persoais.</span><span class="sxs-lookup"><span data-stu-id="f2c57-138">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="f2c57-139">Microsoft transferirá estes datos segundo a súa instrución, pero vostede é responsable de garantir que Experian cumpra as obrigas de privacidade ou seguridade que poida ter.</span><span class="sxs-lookup"><span data-stu-id="f2c57-139">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="f2c57-140">Para obter máis información, consulte a [Declaración de privacidade de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="f2c57-140">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="f2c57-141">O administrador de Dynamics 365 Customer Insights pode eliminar este enriquecemento en calquera momento para interromper o uso desta funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="f2c57-141">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>
