---
title: Exportar datos de Customer Insights a LinkedIn Ads
description: Aprenda a configurar a conexión e exportar a LinkedIn Ads.
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 1c7b0c728bc4d4cf6b5aea79396cf0779fbf298d
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124488"
---
# <a name="export-segments-to-linkedin-ads-preview"></a><span data-ttu-id="97814-103">Exportar segmentos a LinkedIn Ads (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="97814-103">Export segments to LinkedIn Ads (preview)</span></span>

<span data-ttu-id="97814-104">Exporte segmentos de perfís de clientes unificados a LinkedIn Ads para crear públicos coincidentes.</span><span class="sxs-lookup"><span data-stu-id="97814-104">Export segments of unified customer profiles to LinkedIn Ads to create matched audiences.</span></span> <span data-ttu-id="97814-105">Utilice os públicos coincidentes para dirixirse ás empresas e aos contactos.</span><span class="sxs-lookup"><span data-stu-id="97814-105">Use the matched audiences for company targeting and contact targeting.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="97814-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="97814-106">Prerequisites</span></span>

-   <span data-ttu-id="97814-107">Ten unha [conta de LinkedIn Campaign Manager](https://business.linkedin.com/marketing-solutions/ads) e as correspondentes credenciais de administrador.</span><span class="sxs-lookup"><span data-stu-id="97814-107">You have an [LinkedIn Campaign Manager account](https://business.linkedin.com/marketing-solutions/ads) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="97814-108">Ten [segmentos configurados](segments.md) na información do público.</span><span class="sxs-lookup"><span data-stu-id="97814-108">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="97814-109">Os perfís de clientes dos segmentos exportados conteñen un campo cun enderezo de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="97814-109">Customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="97814-110">Limitacións coñecidas</span><span class="sxs-lookup"><span data-stu-id="97814-110">Known limitations</span></span>

- <span data-ttu-id="97814-111">Pode exportar ata 100 000 perfís por exportación a LinkedIn Ads.</span><span class="sxs-lookup"><span data-stu-id="97814-111">You can export up to 100K profiles per export to LinkedIn Ads.</span></span>
- <span data-ttu-id="97814-112">A exportación a LinkedIn Ads está limitada a segmentos.</span><span class="sxs-lookup"><span data-stu-id="97814-112">Exporting to LinkedIn Ads is limited to segments.</span></span>
- <span data-ttu-id="97814-113">A exportación de ata 100 000 perfís a LinkedIn Ads pode tardar ata 10 minutos en finalizar.</span><span class="sxs-lookup"><span data-stu-id="97814-113">Exporting up to 100K profiles to LinkedIn Ads can take up to 10 minutes to complete.</span></span> 

## <a name="set-up-the-connection-to-linkedin-ads"></a><span data-ttu-id="97814-114">Configurar a conexión a LinkedIn Ads</span><span class="sxs-lookup"><span data-stu-id="97814-114">Set up the connection to LinkedIn Ads</span></span>

1. <span data-ttu-id="97814-115">Na información do público, vaia a **Administrar** > **Conexións**.</span><span class="sxs-lookup"><span data-stu-id="97814-115">In audience insights, go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="97814-116">Seleccione **Engadir conexión** e elixa **LinkedIn Ads** para configurar a conexión.</span><span class="sxs-lookup"><span data-stu-id="97814-116">Select **Add connection** and choose **LinkedIn Ads** to configure the connection.</span></span>

1. <span data-ttu-id="97814-117">Déalle á conexión un nome recoñecible no campo **Nome para mostrar**.</span><span class="sxs-lookup"><span data-stu-id="97814-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="97814-118">O nome e o tipo de conexión describen esta conexión.</span><span class="sxs-lookup"><span data-stu-id="97814-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="97814-119">Recomendamos escoller un nome que explique o propósito e o destino da conexión.</span><span class="sxs-lookup"><span data-stu-id="97814-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="97814-120">Escolla quen pode usar esta conexión.</span><span class="sxs-lookup"><span data-stu-id="97814-120">Choose who can use this connection.</span></span> <span data-ttu-id="97814-121">Se non realiza ningunha acción, o valor predefinido será administradores.</span><span class="sxs-lookup"><span data-stu-id="97814-121">If you take no action, the default is administrators.</span></span> <span data-ttu-id="97814-122">Para obter máis información, consulte [Permitir aos colaboradores usar unha conexión para as exportacións](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="97814-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="97814-123">Proporcione o [ID da conta de LinkedIn Campaign Manager](https://www.linkedin.com/help/lms/answer/a424270).</span><span class="sxs-lookup"><span data-stu-id="97814-123">Provide your [LinkedIn Campaign Manager Account ID](https://www.linkedin.com/help/lms/answer/a424270).</span></span>

1. <span data-ttu-id="97814-124">Seleccione **Estou de acordo** para confirmar a **Privacidade e cumprimento dos datos**.</span><span class="sxs-lookup"><span data-stu-id="97814-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="97814-125">Seleccione **Conectar** para iniciar a conexión a Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="97814-125">Select **Connect** to initialize the connection to Campaign Monitor.</span></span>

1. <span data-ttu-id="97814-126">Seleccione **Autenticarse con LinkedIn** e proporcione as súas credenciais de administrador de LinkedIn Campaign Manager.</span><span class="sxs-lookup"><span data-stu-id="97814-126">Select **Authenticate with LinkedIn** and provide your admin credentials for LinkedIn Campaign Manager.</span></span>

1. <span data-ttu-id="97814-127">Seleccione **Autoengadirse como usuario de exportación** e proporcione as súas credenciais de Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="97814-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="97814-128">Seleccione **Gardar** para completar a conexión.</span><span class="sxs-lookup"><span data-stu-id="97814-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="97814-129">Configurar unha exportación</span><span class="sxs-lookup"><span data-stu-id="97814-129">Configure an export</span></span>

<span data-ttu-id="97814-130">Pode configurar unha exportación se ten acceso a unha conexión deste tipo.</span><span class="sxs-lookup"><span data-stu-id="97814-130">You can configure an export if you have access to a connection of this type.</span></span> <span data-ttu-id="97814-131">Para obter máis información, consulte [Permisos necesarios para configurar unha exportación](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="97814-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="97814-132">Vaia a **Datos** > **Exportacións**.</span><span class="sxs-lookup"><span data-stu-id="97814-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="97814-133">Seleccione **Engadir destino** para crear unha nova exportación.</span><span class="sxs-lookup"><span data-stu-id="97814-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="97814-134">No campo **Conexión da exportación**, escolla unha conexión da sección LinkedIn Ads.</span><span class="sxs-lookup"><span data-stu-id="97814-134">In the **Connection for export** field, choose a connection from the LinkedIn Ads section.</span></span> <span data-ttu-id="97814-135">Se non ve o nome desta sección, non hai conexións deste tipo dispoñibles para vostede.</span><span class="sxs-lookup"><span data-stu-id="97814-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="97814-136">Escolla se quere exportar datos para [dirixirse aos contactos](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) ou [dirixirse ás empresas](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) en LinkedIn.</span><span class="sxs-lookup"><span data-stu-id="97814-136">Choose whether you want to export data to do [contact targeting](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) or [company targeting](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) on LinkedIn.</span></span> 

1. <span data-ttu-id="97814-137">Na sección **Coincidencia de datos**, seleccione o campo do seu perfil de cliente unificado que represente o enderezo de correo electrónico dun cliente.</span><span class="sxs-lookup"><span data-stu-id="97814-137">In the **Data matching** section, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="97814-138">É necesario exportar segmentos a LinkedIn Ads.</span><span class="sxs-lookup"><span data-stu-id="97814-138">It's required to export segments to LinkedIn Ads.</span></span>

1. <span data-ttu-id="97814-139">Seleccione os segmentos que desexa exportar.</span><span class="sxs-lookup"><span data-stu-id="97814-139">Select the segments you want to export.</span></span> <span data-ttu-id="97814-140">Os públicos coincidentes en LinkedIn Campaign Manager crearanse automaticamente co nome dos segmentos que seleccionou para exportar.</span><span class="sxs-lookup"><span data-stu-id="97814-140">The matched audiences in LinkedIn Campaign Manager will automatically be created with the name of the segments that you selected to export.</span></span> <span data-ttu-id="97814-141">Cada segmento dará lugar a un público coincidente diferente.</span><span class="sxs-lookup"><span data-stu-id="97814-141">Each segment will result in a separate matched audience.</span></span> 

1. <span data-ttu-id="97814-142">Seleccione **Gardar**.</span><span class="sxs-lookup"><span data-stu-id="97814-142">Select **Save**.</span></span>

<span data-ttu-id="97814-143">Ao gardar unha exportación non se executa a exportación inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="97814-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="97814-144">A exportación execútase con cada [actualización programada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="97814-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="97814-145">Tamén pode [exportar datos baixo demanda](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="97814-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="97814-146">Cumprimento e privacidade dos datos</span><span class="sxs-lookup"><span data-stu-id="97814-146">Data privacy and compliance</span></span>

<span data-ttu-id="97814-147">Cando habilita Dynamics 365 Customer Insights para transmitir datos a LinkedIn Ads, permite a transferencia de datos fóra do límite de cumprimento de Dynamics 365 Customer Insights, incluíndo datos potencialmente confidenciais como os datos persoais.</span><span class="sxs-lookup"><span data-stu-id="97814-147">When you enable Dynamics 365 Customer Insights to transmit data to LinkedIn Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="97814-148">Microsoft transferirá estes datos segundo a súa instrución, pero vostede é responsable de asegurarse de que LinkedIn Ads cumpra as obrigas de privacidade ou seguridade que poida ter.</span><span class="sxs-lookup"><span data-stu-id="97814-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that LinkedIn Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="97814-149">Para obter máis información, consulte a [Declaración de privacidade de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="97814-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="97814-150">O administrador de Dynamics 365 Customer Insights pode eliminar este destino de exportación en calquera momento para deter o uso desta funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="97814-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to stop the use of this functionality.</span></span>
