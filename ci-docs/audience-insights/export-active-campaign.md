---
title: Exportar datos de Customer Insights a ActiveCampaign
description: Aprenda a configurar a conexión e exportar a ActiveCampaign.
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6d85fa9836618e27f7f3da6ce17c07b4bc89e187
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314611"
---
# <a name="export-segments-to-activecampaign-preview"></a><span data-ttu-id="a3b9d-103">Exportar segmentos a ActiveCampaign (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="a3b9d-103">Export segments to ActiveCampaign (preview)</span></span>

<span data-ttu-id="a3b9d-104">Exporte segmentos de perfís de clientes unificados a ActiveCampaign e utilíceos para actividades de mercadotecnia.</span><span class="sxs-lookup"><span data-stu-id="a3b9d-104">Export segments of unified customer profiles to ActiveCampaign and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a3b9d-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="a3b9d-105">Prerequisites</span></span>

-   <span data-ttu-id="a3b9d-106">Ten unha [conta de ActiveCampaign](https://www.activecampaign.com/) e as correspondentes credenciais de administrador.</span><span class="sxs-lookup"><span data-stu-id="a3b9d-106">You have an [ActiveCampaign account](https://www.activecampaign.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="a3b9d-107">Ten [segmentos configurados](segments.md) na información do público.</span><span class="sxs-lookup"><span data-stu-id="a3b9d-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="a3b9d-108">Os perfís de clientes unificados nos segmentos exportados conteñen un campo cun enderezo de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="a3b9d-108">Unified customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="a3b9d-109">Limitacións coñecidas</span><span class="sxs-lookup"><span data-stu-id="a3b9d-109">Known limitations</span></span>

- <span data-ttu-id="a3b9d-110">Pode exportar ata 1 millón de perfís por exportación a ActiveCampaign e pode levar ata 90 minutos en completarse.</span><span class="sxs-lookup"><span data-stu-id="a3b9d-110">You can export up to 1 million profiles per export to ActiveCampaign and it can take up to 90 minutes to complete.</span></span>
- <span data-ttu-id="a3b9d-111">A exportación a ActiveCampaign está limitada a segmentos.</span><span class="sxs-lookup"><span data-stu-id="a3b9d-111">Exporting to ActiveCampaign is limited to segments.</span></span>
- <span data-ttu-id="a3b9d-112">O número de perfís que pode exportar a ActiveCampaign depende do seu contrato con ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="a3b9d-112">The number of profiles that you can export to ActiveCampaign depends on your contract with ActiveCampaign.</span></span>

## <a name="set-up-connection-to-activecampaign"></a><span data-ttu-id="a3b9d-113">Configurar conexión a ActiveCampaign</span><span class="sxs-lookup"><span data-stu-id="a3b9d-113">Set up connection to ActiveCampaign</span></span>

1. <span data-ttu-id="a3b9d-114">Vaia a **Administrar** > **Conexións**.</span><span class="sxs-lookup"><span data-stu-id="a3b9d-114">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="a3b9d-115">Seleccione **Engadir conexión** e elixa **ActiveCampaign** para configurar a conexión.</span><span class="sxs-lookup"><span data-stu-id="a3b9d-115">Select **Add connection** and choose **ActiveCampaign** to configure the connection.</span></span>

1. <span data-ttu-id="a3b9d-116">Déalle á conexión un nome recoñecible no campo **Nome para mostrar**.</span><span class="sxs-lookup"><span data-stu-id="a3b9d-116">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="a3b9d-117">O nome e o tipo de conexión describen esta conexión.</span><span class="sxs-lookup"><span data-stu-id="a3b9d-117">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="a3b9d-118">Recomendamos escoller un nome que explique o propósito e o destino da conexión.</span><span class="sxs-lookup"><span data-stu-id="a3b9d-118">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="a3b9d-119">Escolla quen pode usar esta conexión.</span><span class="sxs-lookup"><span data-stu-id="a3b9d-119">Choose who can use this connection.</span></span> <span data-ttu-id="a3b9d-120">Por defecto, só son os administradores.</span><span class="sxs-lookup"><span data-stu-id="a3b9d-120">By default, it's only administrators.</span></span> <span data-ttu-id="a3b9d-121">Para obter máis información, consulte [Permitir aos colaboradores usar unha conexión para as exportacións](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="a3b9d-121">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="a3b9d-122">Introduza a súa [Clave da API de ActiveCampaign e o nome de servidor do extremo de REST](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key).</span><span class="sxs-lookup"><span data-stu-id="a3b9d-122">Enter your [ActiveCampaign API Key and REST Endpoint Hostname](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key).</span></span> <span data-ttu-id="a3b9d-123">O nome do servidor do extremo de REST é só o nome do servidor, sen https://.</span><span class="sxs-lookup"><span data-stu-id="a3b9d-123">The REST Endpoint Hostname is the hostname only, without https://.</span></span> 

1. <span data-ttu-id="a3b9d-124">Seleccione **Estou de acordo** para confirmar a **Privacidade e cumprimento dos datos**.</span><span class="sxs-lookup"><span data-stu-id="a3b9d-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="a3b9d-125">Seleccione **Conectar** para iniciar a conexión a ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="a3b9d-125">Select **Connect** to initialize the connection to ActiveCampaign.</span></span>

1. <span data-ttu-id="a3b9d-126">Seleccione **Autoengadirse como usuario de exportación** e proporcione as súas credenciais de Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="a3b9d-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="a3b9d-127">Seleccione **Gardar** para completar a conexión.</span><span class="sxs-lookup"><span data-stu-id="a3b9d-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="a3b9d-128">Configurar unha exportación</span><span class="sxs-lookup"><span data-stu-id="a3b9d-128">Configure an export</span></span>

<span data-ttu-id="a3b9d-129">Pode configurar unha exportación se ten acceso a unha conexión deste tipo.</span><span class="sxs-lookup"><span data-stu-id="a3b9d-129">You can configure an export if you have access to a connection of this type.</span></span> <span data-ttu-id="a3b9d-130">Para obter máis información, consulte [Permisos necesarios para configurar unha exportación](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="a3b9d-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="a3b9d-131">Vaia a **Datos** > **Exportacións**.</span><span class="sxs-lookup"><span data-stu-id="a3b9d-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="a3b9d-132">Seleccione **Engadir destino** para crear unha nova exportación.</span><span class="sxs-lookup"><span data-stu-id="a3b9d-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="a3b9d-133">No campo **Conexión para a exportación**, escolla unha conexión na sección ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="a3b9d-133">In the **Connection for export** field, choose a connection from the ActiveCampaign section.</span></span> <span data-ttu-id="a3b9d-134">Se non ve o nome desta sección, non hai conexións deste tipo dispoñibles para vostede.</span><span class="sxs-lookup"><span data-stu-id="a3b9d-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="a3b9d-135">Introduza o seu [**ID de lista de ActiveCampaign**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).</span><span class="sxs-lookup"><span data-stu-id="a3b9d-135">Enter your [**ActiveCampaign List ID**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).</span></span>    

3. <span data-ttu-id="a3b9d-136">Na sección **Coincidencia de datos**, no campo **Correo electrónico**, seleccione o campo do seu perfil de cliente unificado que representa o enderezo de correo electrónico dun cliente.</span><span class="sxs-lookup"><span data-stu-id="a3b9d-136">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="a3b9d-137">É necesario exportar segmentos a ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="a3b9d-137">It's required to export segments to ActiveCampaign.</span></span> <span data-ttu-id="a3b9d-138">Opcionalmente, pode exportar nome, apelidos e Teléfono para crear correos electrónicos máis personalizados.</span><span class="sxs-lookup"><span data-stu-id="a3b9d-138">Optionally, you can export First name, Last name, and Phone to create more personalized emails.</span></span> <span data-ttu-id="a3b9d-139">Seleccione Engadir atributo para asignar estes campos.</span><span class="sxs-lookup"><span data-stu-id="a3b9d-139">Select Add attribute to map these fields.</span></span>

1. <span data-ttu-id="a3b9d-140">Seleccione **Gardar**.</span><span class="sxs-lookup"><span data-stu-id="a3b9d-140">Select **Save**.</span></span>

<span data-ttu-id="a3b9d-141">Ao gardar unha exportación non se executa a exportación inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="a3b9d-141">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="a3b9d-142">A exportación execútase con cada [actualización programada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="a3b9d-142">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="a3b9d-143">Tamén pode [exportar datos baixo demanda](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="a3b9d-143">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="a3b9d-144">Cumprimento e privacidade dos datos</span><span class="sxs-lookup"><span data-stu-id="a3b9d-144">Data privacy and compliance</span></span>

<span data-ttu-id="a3b9d-145">Cando permite a Dynamics 365 Customer Insights transmitir datos a ActiveCampaign, permite a transferencia de datos fóra do límite de cumprimento de Dynamics 365 Customer Insights, incluíndo datos potencialmente confidenciais como os datos persoais.</span><span class="sxs-lookup"><span data-stu-id="a3b9d-145">When you enable Dynamics 365 Customer Insights to transmit data to ActiveCampaign, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="a3b9d-146">Microsoft transferirá estes datos segundo a súa instrución, pero vostede é responsable de asegurarse de que ActiveCampaign cumpre coas obrigacións de privacidade ou seguridade que poida ter.</span><span class="sxs-lookup"><span data-stu-id="a3b9d-146">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that ActiveCampaign meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="a3b9d-147">Para obter máis información, consulte a [Declaración de privacidade de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="a3b9d-147">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="a3b9d-148">O administrador de Dynamics 365 Customer Insights pode eliminar este destino de exportación en calquera momento para interromper o uso desta funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="a3b9d-148">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
