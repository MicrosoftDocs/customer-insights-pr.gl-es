---
title: Exportar datos de Customer Insights a Google Ads
description: Aprenda a configurar a conexión a Google Ads.
ms.date: 11/18/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 06aa0b6ff3125d8735adc8c8f9f6dad69087d9f8
ms.sourcegitcommit: ff824bbbd31fd666ab0da682bf48ea31580d242c
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "4568436"
---
# <a name="connector-for-google-ads-preview"></a><span data-ttu-id="c4a65-103">Conector para Google Ads (vista previa)</span><span class="sxs-lookup"><span data-stu-id="c4a65-103">Connector for Google Ads (preview)</span></span>

<span data-ttu-id="c4a65-104">Exporte segmentos de perfís de clientes unificados á lista de públicos de Google Ads e utilíceos para anunciarse na Busca de Google, en Gmail, YouTube e na Rede de Display de Google.</span><span class="sxs-lookup"><span data-stu-id="c4a65-104">Export segments of unified customer profiles to Google Ads audience list and use them to advertise on Google Search, Gmail, YouTube, and Google Display Network.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="c4a65-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="c4a65-105">Prerequisites</span></span>

-   <span data-ttu-id="c4a65-106">Ten unha [Conta de Google Ads](https://ads.google.com/) e as correspondentes credenciais de administrador.</span><span class="sxs-lookup"><span data-stu-id="c4a65-106">You have a [Google Ads account](https://ads.google.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="c4a65-107">Existen públicos en Google Ads e os ID correspondentes.</span><span class="sxs-lookup"><span data-stu-id="c4a65-107">There are existing audiences in Google Ads and the corresponding IDs.</span></span> <span data-ttu-id="c4a65-108">Para obter máis información, consulte [Públicos de Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span><span class="sxs-lookup"><span data-stu-id="c4a65-108">For more information, see [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span></span>
-   <span data-ttu-id="c4a65-109">Ten [segmentos configurados](segments.md)</span><span class="sxs-lookup"><span data-stu-id="c4a65-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="c4a65-110">Os perfís de clientes unificados nos segmentos exportados conteñen campos que representan un enderezo de correo electrónico, nome e apelidos</span><span class="sxs-lookup"><span data-stu-id="c4a65-110">Unified customer profiles in the exported segments contain fields representing an email address, first name, and last name</span></span>

## <a name="connect-to-google-ads"></a><span data-ttu-id="c4a65-111">Conectarse con Google Ads</span><span class="sxs-lookup"><span data-stu-id="c4a65-111">Connect to Google Ads</span></span>

1. <span data-ttu-id="c4a65-112">Vaia a **Administrador** > **Exportar destinos**.</span><span class="sxs-lookup"><span data-stu-id="c4a65-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="c4a65-113">En **Google Ads**, seleccione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="c4a65-113">Under **Google Ads**, select **Set up**.</span></span>

1. <span data-ttu-id="c4a65-114">Déalle ao seu destino da exploración un nome recoñecible no campo **Nome para mostrar**.</span><span class="sxs-lookup"><span data-stu-id="c4a65-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="c4a65-115">Insira o seu **[ID de cliente de Google Ads](https://support.google.com/google-ads/answer/1704344)**.</span><span class="sxs-lookup"><span data-stu-id="c4a65-115">Enter your **[Google Ads customer ID](https://support.google.com/google-ads/answer/1704344)**.</span></span>

1. <span data-ttu-id="c4a65-116">Introduza o seu **[Token de programador aprobado por Google Ads](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span><span class="sxs-lookup"><span data-stu-id="c4a65-116">Enter your **[Google Ads approved developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span></span>

1. <span data-ttu-id="c4a65-117">Seleccione **Estou de acordo** para confirmar a **Privacidade e cumprimento dos datos**.</span><span class="sxs-lookup"><span data-stu-id="c4a65-117">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="c4a65-118">Introduza o seu **[ID de audiencia de Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** e seleccione **Conectar** para inicializar a conexión a Google Ads.</span><span class="sxs-lookup"><span data-stu-id="c4a65-118">Enter your **[Google Ads audience ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** and select **Connect** to initialize the connection to Google Ads.</span></span>

1. <span data-ttu-id="c4a65-119">Seleccione **Autenticarse con Google Ads** e proporcione as súas credenciais de Google Ads.</span><span class="sxs-lookup"><span data-stu-id="c4a65-119">Select **Authenticate with Google Ads** and provide your Google Ads credentials.</span></span>

1. <span data-ttu-id="c4a65-120">Seleccione **Autoengadirse como usuario de exportación** e proporcione as súas credenciais de Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="c4a65-120">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-segments-googleads.PNG" alt-text="Captura de pantalla de exportación para a conexión de Google Ads":::

1. <span data-ttu-id="c4a65-122">Seleccione **Seguinte** para configurar a exportación.</span><span class="sxs-lookup"><span data-stu-id="c4a65-122">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="c4a65-123">Configurar o conector</span><span class="sxs-lookup"><span data-stu-id="c4a65-123">Configure the connector</span></span>

1. <span data-ttu-id="c4a65-124">Na sección **Coincidencia de datos**, no campo **Correo electrónico**, seleccione o campo do seu perfil de cliente unificado que representa o enderezo de correo electrónico dun cliente.</span><span class="sxs-lookup"><span data-stu-id="c4a65-124">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="c4a65-125">Repita os mesmos pasos para os campos **nome** e **apelidos**.</span><span class="sxs-lookup"><span data-stu-id="c4a65-125">Repeat the same steps for \*\*First name" and **Last name** fields.</span></span>

1. <span data-ttu-id="c4a65-126">Seleccione os segmentos que desexa exportar.</span><span class="sxs-lookup"><span data-stu-id="c4a65-126">Select the segments you want to export.</span></span> <span data-ttu-id="c4a65-127">Pode exportar ata 1 millón de perfís de clientes en total a Google Ads.</span><span class="sxs-lookup"><span data-stu-id="c4a65-127">You can export up to 1 million customer profiles in total to Google Ads.</span></span>

1. <span data-ttu-id="c4a65-128">Seleccione **Gardar**.</span><span class="sxs-lookup"><span data-stu-id="c4a65-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="c4a65-129">Exportar os datos</span><span class="sxs-lookup"><span data-stu-id="c4a65-129">Export the data</span></span>

<span data-ttu-id="c4a65-130">Pode [exportar datos baixo demanda](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="c4a65-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="c4a65-131">A exportación tamén se executará con todas as [actualizacións programadas](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="c4a65-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="c4a65-132">En Google Ads, agora pode atopar os seus segmentos en [Públicos de Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en/).</span><span class="sxs-lookup"><span data-stu-id="c4a65-132">In Google Ads, you can now find your segments under [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en/).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="c4a65-133">Limitacións coñecidas</span><span class="sxs-lookup"><span data-stu-id="c4a65-133">Known limitations</span></span>

- <span data-ttu-id="c4a65-134">Ata 1 millón de perfís por exportación a Google Ads.</span><span class="sxs-lookup"><span data-stu-id="c4a65-134">Up to 1 million profiles per export to Google Ads.</span></span>
- <span data-ttu-id="c4a65-135">A exportación a Google Ads está limitada a segmentos.</span><span class="sxs-lookup"><span data-stu-id="c4a65-135">Exporting to Google Ads is limited to segments.</span></span>
- <span data-ttu-id="c4a65-136">A exportación de segmentos cun total de 1 millón de perfís pode levar ata 5 minutos debido ás limitacións do provedor.</span><span class="sxs-lookup"><span data-stu-id="c4a65-136">Exporting segments with a total of 1 million profiles can take up to 5 minutes because of limitations on the provider side.</span></span> 
- <span data-ttu-id="c4a65-137">A busca de coincidencias en Google Ads pode levar ata 48 horas.</span><span class="sxs-lookup"><span data-stu-id="c4a65-137">The matching in Google Ads can take up to 48 hours.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="c4a65-138">Cumprimento e privacidade dos datos</span><span class="sxs-lookup"><span data-stu-id="c4a65-138">Data privacy and compliance</span></span>

<span data-ttu-id="c4a65-139">Cando habilita Dynamics 365 Customer Insights para transmitir datos a Google Ads, permite a transferencia de datos fóra do límite de cumprimento de Dynamics 365 Customer Insights, incluíndo datos potencialmente confidenciais como os datos persoais.</span><span class="sxs-lookup"><span data-stu-id="c4a65-139">When you enable Dynamics 365 Customer Insights to transmit data to Google Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="c4a65-140">Microsoft transferirá estes datos segundo a súa instrución, pero vostede é responsable de garantir que Google Ads cumpra as obrigas de privacidade ou seguridade que poida ter.</span><span class="sxs-lookup"><span data-stu-id="c4a65-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Google Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="c4a65-141">Para obter máis información, consulte a [Declaración de privacidade de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="c4a65-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="c4a65-142">O administrador de Dynamics 365 Customer Insights pode eliminar este destino de exportación en calquera momento para interromper o uso desta funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="c4a65-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
