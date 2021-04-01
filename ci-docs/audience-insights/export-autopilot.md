---
title: Exportar datos de Customer Insights a Autopilot
description: Aprenda a configurar a conexión a Autopilot.
ms.date: 12/08/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6d039c4afd84eaad942d214d4e6fb8ef7b1ec72a
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596128"
---
# <a name="connector-for-autopilot-preview"></a><span data-ttu-id="89174-103">Conector para Autopilot (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="89174-103">Connector for Autopilot (preview)</span></span>

<span data-ttu-id="89174-104">Exporte segmentos de perfís de clientes unificados a Autopilot e utilíceos para campañas e mercadotecnia por correo electrónico en Autopilot.</span><span class="sxs-lookup"><span data-stu-id="89174-104">Export segments of unified customer profiles to Autopilot and use them for email marketing in Autopilot.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="89174-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="89174-105">Prerequisites</span></span>

-   <span data-ttu-id="89174-106">Ten unha [Conta de Autopilot](https://www.autopilothq.com/) e as correspondentes credenciais de administrador.</span><span class="sxs-lookup"><span data-stu-id="89174-106">You have an [Autopilot account](https://www.autopilothq.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="89174-107">Ten [segmentos configurados](segments.md) na información do público.</span><span class="sxs-lookup"><span data-stu-id="89174-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="89174-108">Os perfís de clientes unificados nos segmentos exportados conteñen un campo que representa un enderezo de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="89174-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-autopilot"></a><span data-ttu-id="89174-109">Conectar con AutoPilot</span><span class="sxs-lookup"><span data-stu-id="89174-109">Connect to Autopilot</span></span>

1. <span data-ttu-id="89174-110">Vaia a **Administrador** > **Exportar destinos**.</span><span class="sxs-lookup"><span data-stu-id="89174-110">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="89174-111">En **Autopilot**, seleccione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="89174-111">Under **Autopilot**, select **Set up**.</span></span>

1. <span data-ttu-id="89174-112">Déalle ao seu destino da exploración un nome recoñecible no campo **Nome para mostrar**.</span><span class="sxs-lookup"><span data-stu-id="89174-112">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/export-autopilot.PNG" alt-text="Panel de configuración para a conexión de Autopilot.":::

1. <span data-ttu-id="89174-114">Introduza a súa **Clave da API de Autopilot** [Clave da API de Autopilot](https://autopilot.docs.apiary.io/#).</span><span class="sxs-lookup"><span data-stu-id="89174-114">Enter your **Autopilot API key** [Autopilot API key](https://autopilot.docs.apiary.io/#).</span></span>

1. <span data-ttu-id="89174-115">Seleccione **Estou de acordo** para confirmar a **Privacidade e cumprimento dos datos**.</span><span class="sxs-lookup"><span data-stu-id="89174-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="89174-116">Seleccione **Conectar** para inicializar a conexión a Autopilot.</span><span class="sxs-lookup"><span data-stu-id="89174-116">Select **Connect** to initialize the connection to Autopilot.</span></span>

1. <span data-ttu-id="89174-117">Seleccione **Autoengadirse como usuario de exportación** e proporcione as súas credenciais de Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="89174-117">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="89174-118">Seleccione **Seguinte** para configurar a exportación.</span><span class="sxs-lookup"><span data-stu-id="89174-118">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="89174-119">Configurar o conector</span><span class="sxs-lookup"><span data-stu-id="89174-119">Configure the connector</span></span>

1. <span data-ttu-id="89174-120">Na sección **Coincidencia de datos**, no campo **Correo electrónico**, seleccione o campo do seu perfil de cliente unificado que representa o enderezo de correo electrónico dun cliente.</span><span class="sxs-lookup"><span data-stu-id="89174-120">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="89174-121">Repita os mesmos pasos para outros campos opcionais como **nome**, **apelidos**.</span><span class="sxs-lookup"><span data-stu-id="89174-121">Repeat the same steps for other optional fields such as **First name**, **Last name**.</span></span>

1. <span data-ttu-id="89174-122">Seleccione os segmentos que desexa exportar.</span><span class="sxs-lookup"><span data-stu-id="89174-122">Select the segments you want to export.</span></span> <span data-ttu-id="89174-123">Nós fortemente **recomendamos non exportar máis de 100.000 perfís de clientes en total** a Autopilot.</span><span class="sxs-lookup"><span data-stu-id="89174-123">We strongly **recommend to not export more than 100'000 customer profiles in total** to Autopilot.</span></span> 

1. <span data-ttu-id="89174-124">Seleccione **Gardar**.</span><span class="sxs-lookup"><span data-stu-id="89174-124">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="89174-125">Exportar os datos</span><span class="sxs-lookup"><span data-stu-id="89174-125">Export the data</span></span>

<span data-ttu-id="89174-126">Pode [exportar datos baixo demanda](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="89174-126">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="89174-127">A exportación tamén se executará con todas as [actualizacións programadas](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="89174-127">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="89174-128">Limitacións coñecidas</span><span class="sxs-lookup"><span data-stu-id="89174-128">Known limitations</span></span>

- <span data-ttu-id="89174-129">Pode exportar ata 100.000 perfís en total a Autopilot.</span><span class="sxs-lookup"><span data-stu-id="89174-129">You can export up to 100'000 profiles in total to Autopilot.</span></span>
- <span data-ttu-id="89174-130">A exportación a Autopilot está limitada a segmentos.</span><span class="sxs-lookup"><span data-stu-id="89174-130">Exporting to Autopilot is limited to segments.</span></span>
- <span data-ttu-id="89174-131">Exportar ata 100.000 perfís a Autopilot pode tardar unhas horas en completarse.</span><span class="sxs-lookup"><span data-stu-id="89174-131">Exporting up to 100'000 profiles to Autopilot can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="89174-132">O número de perfís que pode exportar a Autopilot depende e está limitado no seu contrato con Autopilot.</span><span class="sxs-lookup"><span data-stu-id="89174-132">The number of profiles that you can export to Autopilot is dependent and limited on your contract with Autopilot.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="89174-133">Cumprimento e privacidade dos datos</span><span class="sxs-lookup"><span data-stu-id="89174-133">Data privacy and compliance</span></span>

<span data-ttu-id="89174-134">Cando habilita Dynamics 365 Customer Insights para transmitir datos a Autopilot, permite a transferencia de datos fóra do límite de cumprimento de Dynamics 365 Customer Insights, incluíndo datos potencialmente confidenciais como os datos persoais.</span><span class="sxs-lookup"><span data-stu-id="89174-134">When you enable Dynamics 365 Customer Insights to transmit data to Autopilot, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="89174-135">Microsoft transferirá estes datos segundo a súa instrución, pero vostede é responsable de garantir que Autopilot cumpra as obrigas de privacidade ou seguridade que poida ter.</span><span class="sxs-lookup"><span data-stu-id="89174-135">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Autopilot meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="89174-136">Para obter máis información, consulte a [Declaración de privacidade de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="89174-136">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="89174-137">O administrador de Dynamics 365 Customer Insights pode eliminar este destino de exportación en calquera momento para interromper o uso desta funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="89174-137">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]