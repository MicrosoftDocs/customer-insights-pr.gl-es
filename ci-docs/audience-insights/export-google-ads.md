---
title: Exportar datos de Customer Insights a Google Ads
description: Aprenda a configurar a conexión e exportar a Google Ads.
ms.date: 03/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: c23c8b4e6758df08e04bf1e3ae0cba4dee06fe2b
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305338"
---
# <a name="export-segments-to-google-ads-preview"></a><span data-ttu-id="6ebd6-103">Exportar segmentos a Google Ads (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="6ebd6-103">Export segments to Google Ads (preview)</span></span>

<span data-ttu-id="6ebd6-104">Exporte segmentos de perfís de clientes unificados a unha lista de público de Google Ads e utilíceos para anunciarse na Busca de Google, Gmail, YouTube e a Rede de visualización de Google.</span><span class="sxs-lookup"><span data-stu-id="6ebd6-104">Export segments of unified customer profiles to a Google Ads audience list and use them to advertise on Google Search, Gmail, YouTube, and Google Display Network.</span></span> 

## <a name="prerequisites-for-connection"></a><span data-ttu-id="6ebd6-105">Requisitos previos para a conexión</span><span class="sxs-lookup"><span data-stu-id="6ebd6-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="6ebd6-106">Ten unha [Conta de Google Ads](https://ads.google.com/) e as correspondentes credenciais de administrador.</span><span class="sxs-lookup"><span data-stu-id="6ebd6-106">You have a [Google Ads account](https://ads.google.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="6ebd6-107">Ten un [token de programador de Google Ads aprobado](https://developers.google.com/google-ads/api/docs/first-call/dev-token).</span><span class="sxs-lookup"><span data-stu-id="6ebd6-107">You have an [approved Google Ads Developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token).</span></span> 
-   <span data-ttu-id="6ebd6-108">Cumpre os requisitos da [Política de coincidencia de clientes](https://support.google.com/adspolicy/answer/6299717).</span><span class="sxs-lookup"><span data-stu-id="6ebd6-108">You fulfill the requirements of the [Customer Match Policy](https://support.google.com/adspolicy/answer/6299717).</span></span>
-   <span data-ttu-id="6ebd6-109">Cumpre os requisitos dos [tamaños de lista de remárketing](https://support.google.com/google-ads/answer/7558048).</span><span class="sxs-lookup"><span data-stu-id="6ebd6-109">You fulfill the requirements of the [remarketing list sizes](https://support.google.com/google-ads/answer/7558048).</span></span>
-   <span data-ttu-id="6ebd6-110">Existen públicos en Google Ads e os ID correspondentes.</span><span class="sxs-lookup"><span data-stu-id="6ebd6-110">There are existing audiences in Google Ads and the corresponding IDs.</span></span> <span data-ttu-id="6ebd6-111">Para obter máis información, consulte [Públicos de Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span><span class="sxs-lookup"><span data-stu-id="6ebd6-111">For more information, see [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span></span>
-   <span data-ttu-id="6ebd6-112">Ten [segmentos configurados](segments.md).</span><span class="sxs-lookup"><span data-stu-id="6ebd6-112">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="6ebd6-113">Os perfís de clientes unificados nos segmentos exportados conteñen campos que representan un enderezo de correo electrónico, nome e apelidos.</span><span class="sxs-lookup"><span data-stu-id="6ebd6-113">Unified customer profiles in the exported segments contain fields representing an email address, first name, and last name.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="6ebd6-114">Limitacións coñecidas</span><span class="sxs-lookup"><span data-stu-id="6ebd6-114">Known limitations</span></span>

- <span data-ttu-id="6ebd6-115">Ata 1 millón de perfís por exportación a Google Ads.</span><span class="sxs-lookup"><span data-stu-id="6ebd6-115">Up to 1 million profiles per export to Google Ads.</span></span>
- <span data-ttu-id="6ebd6-116">A exportación a Google Ads está limitada a segmentos.</span><span class="sxs-lookup"><span data-stu-id="6ebd6-116">Exporting to Google Ads is limited to segments.</span></span>
- <span data-ttu-id="6ebd6-117">A exportación de segmentos cun total de 1 millón de perfís pode levar ata 5 minutos debido ás limitacións do provedor.</span><span class="sxs-lookup"><span data-stu-id="6ebd6-117">Exporting segments with a total of 1 million profiles can take up to 5 minutes because of limitations on the provider side.</span></span> 
- <span data-ttu-id="6ebd6-118">A busca de coincidencias en Google Ads pode levar ata 48 horas.</span><span class="sxs-lookup"><span data-stu-id="6ebd6-118">The matching in Google Ads can take up to 48 hours.</span></span>

## <a name="set-up-connection-to-google-ads"></a><span data-ttu-id="6ebd6-119">Configurar conexión a Google Ads</span><span class="sxs-lookup"><span data-stu-id="6ebd6-119">Set up connection to Google Ads</span></span>

1. <span data-ttu-id="6ebd6-120">Vaia a **Administrar** > **Conexións**.</span><span class="sxs-lookup"><span data-stu-id="6ebd6-120">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="6ebd6-121">Seleccione **Engadir conexión** e elixa **Google Ads** para configurar a conexión.</span><span class="sxs-lookup"><span data-stu-id="6ebd6-121">Select **Add connection** and choose **Google Ads** to configure the connection.</span></span>

1. <span data-ttu-id="6ebd6-122">Déalle á conexión un nome recoñecible no campo **Nome para mostrar**.</span><span class="sxs-lookup"><span data-stu-id="6ebd6-122">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="6ebd6-123">O nome e o tipo de conexión describen esta conexión.</span><span class="sxs-lookup"><span data-stu-id="6ebd6-123">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="6ebd6-124">Recomendamos escoller un nome que explique o propósito e o destino da conexión.</span><span class="sxs-lookup"><span data-stu-id="6ebd6-124">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="6ebd6-125">Escolla quen pode usar esta conexión.</span><span class="sxs-lookup"><span data-stu-id="6ebd6-125">Choose who can use this connection.</span></span> <span data-ttu-id="6ebd6-126">Se non realiza ningunha acción, o valor predeterminado será Administradores.</span><span class="sxs-lookup"><span data-stu-id="6ebd6-126">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="6ebd6-127">Para obter máis información, consulte [Permitir aos colaboradores usar unha conexión para as exportacións](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="6ebd6-127">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="6ebd6-128">Insira o seu **[ID de cliente de Google Ads](https://support.google.com/google-ads/answer/1704344)**.</span><span class="sxs-lookup"><span data-stu-id="6ebd6-128">Enter your **[Google Ads customer ID](https://support.google.com/google-ads/answer/1704344)**.</span></span>

1. <span data-ttu-id="6ebd6-129">Introduza o seu **[Token de programador aprobado por Google Ads](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span><span class="sxs-lookup"><span data-stu-id="6ebd6-129">Enter your **[Google Ads approved developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span></span>

1. <span data-ttu-id="6ebd6-130">Seleccione **Estou de acordo** para confirmar a **Privacidade e cumprimento dos datos**.</span><span class="sxs-lookup"><span data-stu-id="6ebd6-130">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="6ebd6-131">Seleccione **Autenticarse con Google Ads** e proporcione as súas credenciais de Google Ads.</span><span class="sxs-lookup"><span data-stu-id="6ebd6-131">Select **Authenticate with Google Ads** and provide your Google Ads credentials.</span></span>

1. <span data-ttu-id="6ebd6-132">Seleccione **Autoengadirse como usuario de exportación** e proporcione as súas credenciais de Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="6ebd6-132">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="6ebd6-133">Seleccione **Gardar** para completar a conexión.</span><span class="sxs-lookup"><span data-stu-id="6ebd6-133">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="6ebd6-134">Configurar unha exportación</span><span class="sxs-lookup"><span data-stu-id="6ebd6-134">Configure an export</span></span>

<span data-ttu-id="6ebd6-135">Pode configurar esta exportación se ten acceso a unha conexión deste tipo.</span><span class="sxs-lookup"><span data-stu-id="6ebd6-135">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="6ebd6-136">Para obter máis información, consulte [Permisos necesarios para configurar unha exportación](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="6ebd6-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="6ebd6-137">Vaia a **Datos** > **Exportacións**.</span><span class="sxs-lookup"><span data-stu-id="6ebd6-137">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="6ebd6-138">Seleccione **Engadir destino** para crear unha nova exportación.</span><span class="sxs-lookup"><span data-stu-id="6ebd6-138">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="6ebd6-139">No campo **Conexión da exportación** escolla unha conexión da sección Google Ads.</span><span class="sxs-lookup"><span data-stu-id="6ebd6-139">In the **Connection for export** field, choose a connection from the Google Ads section.</span></span> <span data-ttu-id="6ebd6-140">Se non ve o nome desta sección, non ten ningunha conexión deste tipo dispoñible.</span><span class="sxs-lookup"><span data-stu-id="6ebd6-140">If you don't see this section name, then no connections of this type are available to you.</span></span>

1. <span data-ttu-id="6ebd6-141">Introduza o seu **[ID de audiencia de Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** e seleccione **Conectar** para inicializar a conexión a Google Ads.</span><span class="sxs-lookup"><span data-stu-id="6ebd6-141">Enter your **[Google Ads audience ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** and select **Connect** to initialize the connection to Google Ads.</span></span>

1. <span data-ttu-id="6ebd6-142">Na sección **Coincidencia de datos**, no campo **Correo electrónico**, seleccione o campo do seu perfil de cliente unificado que representa o enderezo de correo electrónico dun cliente.</span><span class="sxs-lookup"><span data-stu-id="6ebd6-142">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="6ebd6-143">Repita os mesmos pasos para os campos **nome** e **apelidos**.</span><span class="sxs-lookup"><span data-stu-id="6ebd6-143">Repeat the same steps for **First name** and **Last name** fields.</span></span>

1. <span data-ttu-id="6ebd6-144">Seleccione os segmentos que desexa exportar.</span><span class="sxs-lookup"><span data-stu-id="6ebd6-144">Select the segments you want to export.</span></span> <span data-ttu-id="6ebd6-145">Pode exportar ata 1 millón de perfís de clientes en total a Google Ads.</span><span class="sxs-lookup"><span data-stu-id="6ebd6-145">You can export up to 1 million customer profiles in total to Google Ads.</span></span>

<span data-ttu-id="6ebd6-146">Ao gardar unha exportación non se executa a exportación inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="6ebd6-146">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="6ebd6-147">A exportación execútase con cada [actualización programada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="6ebd6-147">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> 

<span data-ttu-id="6ebd6-148">Tamén pode [exportar datos baixo demanda](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="6ebd6-148">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="6ebd6-149">Cumprimento e privacidade dos datos</span><span class="sxs-lookup"><span data-stu-id="6ebd6-149">Data privacy and compliance</span></span>

<span data-ttu-id="6ebd6-150">Cando habilita Dynamics 365 Customer Insights para transmitir datos a Google Ads, permite a transferencia de datos fóra do límite de cumprimento de Dynamics 365 Customer Insights, incluíndo datos potencialmente confidenciais como os datos persoais.</span><span class="sxs-lookup"><span data-stu-id="6ebd6-150">When you enable Dynamics 365 Customer Insights to transmit data to Google Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="6ebd6-151">Microsoft transferirá estes datos segundo a súa instrución, pero vostede é responsable de garantir que Google Ads cumpra as obrigas de privacidade ou seguridade que poida ter.</span><span class="sxs-lookup"><span data-stu-id="6ebd6-151">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Google Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="6ebd6-152">Para obter máis información, consulte a [Declaración de privacidade de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="6ebd6-152">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="6ebd6-153">O administrador de Dynamics 365 Customer Insights pode eliminar este destino de exportación en calquera momento para interromper o uso desta funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="6ebd6-153">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
