---
title: Exportar datos de Customer Insights a AdRoll
description: Aprenda a configurar a conexión a AdRoll.
ms.date: 02/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6fedd549c2e7de362f36e3fb23d363200bb92a04
ms.sourcegitcommit: d24e52150fe5a4fab45128e12d6a03637771d9b9
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "5697072"
---
# <a name="connector-for-adroll-preview"></a><span data-ttu-id="6a880-103">Conector para AdRoll (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="6a880-103">Connector for AdRoll (preview)</span></span>

<span data-ttu-id="6a880-104">Exporte segmentos de perfís de clientes unificados a AdRoll e utilíceos para publicidade.</span><span class="sxs-lookup"><span data-stu-id="6a880-104">Export segments of unified customer profiles to AdRoll and use them for advertising.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="6a880-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="6a880-105">Prerequisites</span></span>

-   <span data-ttu-id="6a880-106">Ten unha [conta de AdRoll](https://www.adroll.com/) e as correspondentes credenciais de administrador.</span><span class="sxs-lookup"><span data-stu-id="6a880-106">You have an [AdRoll account](https://www.adroll.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="6a880-107">Ten [segmentos configurados](segments.md) na información do público.</span><span class="sxs-lookup"><span data-stu-id="6a880-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="6a880-108">Os perfís de clientes unificados nos segmentos exportados conteñen un campo que representa un enderezo de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="6a880-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-adroll"></a><span data-ttu-id="6a880-109">Conectar con AdRoll</span><span class="sxs-lookup"><span data-stu-id="6a880-109">Connect to AdRoll</span></span>

1. <span data-ttu-id="6a880-110">Vaia a **Administrador** > **Exportar destinos**.</span><span class="sxs-lookup"><span data-stu-id="6a880-110">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="6a880-111">En **AdRoll**, seleccione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="6a880-111">Under **AdRoll**, select **Set up**.</span></span>

1. <span data-ttu-id="6a880-112">Déalle ao seu destino da exploración un nome recoñecible no campo **Nome para mostrar**.</span><span class="sxs-lookup"><span data-stu-id="6a880-112">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/AdRoll_config.PNG" alt-text="Panel de configuración para a conexión de AdRoll.":::

1. <span data-ttu-id="6a880-114">Seleccione **Estou de acordo** para confirmar a **Privacidade e cumprimento dos datos**.</span><span class="sxs-lookup"><span data-stu-id="6a880-114">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="6a880-115">Seleccione **Conectar** para iniciar a conexión a AdRoll.</span><span class="sxs-lookup"><span data-stu-id="6a880-115">Select **Connect** to initialize the connection to AdRoll.</span></span>

1. <span data-ttu-id="6a880-116">Seleccione **Autenticarse con AdRoll** e proporcione as súas credenciais de administrador de AdRoll.</span><span class="sxs-lookup"><span data-stu-id="6a880-116">Select **Authenticate with AdRoll** and provide your admin credentials for AdRoll.</span></span> 

1. <span data-ttu-id="6a880-117">Seleccione **Autoengadirse como usuario de exportación** e proporcione as súas credenciais de Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="6a880-117">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="6a880-118">Introduza o seu **ID de anunciante de AdRoll** [Posible publicidade en AdRoll](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).</span><span class="sxs-lookup"><span data-stu-id="6a880-118">Enter your **AdRoll Advertiser ID** [AdRoll Advertisable](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).</span></span>

1. <span data-ttu-id="6a880-119">Seleccione **Seguinte** para configurar a exportación.</span><span class="sxs-lookup"><span data-stu-id="6a880-119">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="6a880-120">Configurar o conector</span><span class="sxs-lookup"><span data-stu-id="6a880-120">Configure the connector</span></span>

1. <span data-ttu-id="6a880-121">Na sección **Coincidencia de datos**, no campo **Correo electrónico**, seleccione o campo do seu perfil de cliente unificado que representa o enderezo de correo electrónico dun cliente.</span><span class="sxs-lookup"><span data-stu-id="6a880-121">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="6a880-122">É necesario exportar segmentos a AdRoll.</span><span class="sxs-lookup"><span data-stu-id="6a880-122">It's required to export segments to AdRoll.</span></span>

1. <span data-ttu-id="6a880-123">Seleccione os segmentos que desexa exportar.</span><span class="sxs-lookup"><span data-stu-id="6a880-123">Select the segments you want to export.</span></span> <span data-ttu-id="6a880-124">Seleccione un segmento cun mínimo de 100 membros.</span><span class="sxs-lookup"><span data-stu-id="6a880-124">Select a segment with a least 100 members.</span></span> <span data-ttu-id="6a880-125">Non pode exportar segmentos máis pequenos.</span><span class="sxs-lookup"><span data-stu-id="6a880-125">You can't export smaller segments.</span></span> <span data-ttu-id="6a880-126">Ademais, o tamaño máximo dun segmento para exportar é de 250.000 membros por exportación.</span><span class="sxs-lookup"><span data-stu-id="6a880-126">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="6a880-127">Seleccione **Gardar**.</span><span class="sxs-lookup"><span data-stu-id="6a880-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="6a880-128">Exportar os datos</span><span class="sxs-lookup"><span data-stu-id="6a880-128">Export the data</span></span>

<span data-ttu-id="6a880-129">Pode [exportar datos baixo demanda](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="6a880-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="6a880-130">A exportación tamén se executará con todas as [actualizacións programadas](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="6a880-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="6a880-131">Limitacións coñecidas</span><span class="sxs-lookup"><span data-stu-id="6a880-131">Known limitations</span></span>

- <span data-ttu-id="6a880-132">Pode exportar ata 250.000 perfís por exportación a AdRoll.</span><span class="sxs-lookup"><span data-stu-id="6a880-132">You can export up to 250'000 profiles in per export to AdRoll.</span></span>
- <span data-ttu-id="6a880-133">Non pode exportar segmentos con menos de 100 perfís a AdRoll.</span><span class="sxs-lookup"><span data-stu-id="6a880-133">You can't export segments with fewer than 100 profiles to AdRoll.</span></span> 
- <span data-ttu-id="6a880-134">A exportación a AdRoll está limitada a segmentos.</span><span class="sxs-lookup"><span data-stu-id="6a880-134">Exporting to AdRoll is limited to segments.</span></span>
- <span data-ttu-id="6a880-135">Exportar ata 250.000 perfís a AdRoll pode levar ata 10 minutos en completarse.</span><span class="sxs-lookup"><span data-stu-id="6a880-135">Exporting up to 250'000 profiles to AdRoll can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="6a880-136">O número de perfís que pode exportar a AdRoll depende e está limitado no seu contrato con AdRoll.</span><span class="sxs-lookup"><span data-stu-id="6a880-136">The number of profiles that you can export to AdRoll is dependent and limited on your contract with AdRoll.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="6a880-137">Cumprimento e privacidade dos datos</span><span class="sxs-lookup"><span data-stu-id="6a880-137">Data privacy and compliance</span></span>

<span data-ttu-id="6a880-138">Cando habilita Dynamics 365 Customer Insights para transmitir datos a AdRoll, permite a transferencia de datos fóra do límite de cumprimento de Dynamics 365 Customer Insights, incluíndo datos potencialmente confidenciais como os datos persoais.</span><span class="sxs-lookup"><span data-stu-id="6a880-138">When you enable Dynamics 365 Customer Insights to transmit data to AdRoll, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="6a880-139">Microsoft transferirá estes datos segundo a súa instrución, pero vostede é responsable de garantir que AdRoll cumpra as obrigas de privacidade ou seguridade que poida ter.</span><span class="sxs-lookup"><span data-stu-id="6a880-139">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that AdRoll meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="6a880-140">Para obter máis información, consulte a [Declaración de privacidade de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="6a880-140">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="6a880-141">O administrador de Dynamics 365 Customer Insights pode eliminar este destino de exportación en calquera momento para interromper o uso desta funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="6a880-141">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
