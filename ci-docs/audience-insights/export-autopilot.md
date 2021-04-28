---
title: Exportar datos de Customer Insights a Autopilot
description: Aprenda a configurar a conexión e exportar a Autopilot.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e320a48d5b7c35b530e3a38567b226b804879e4e
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760141"
---
# <a name="export-segments-to-autopilot-preview"></a><span data-ttu-id="9a6c7-103">Exportar segmentos a Autopilot (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="9a6c7-103">Export segments to Autopilot (preview)</span></span>

<span data-ttu-id="9a6c7-104">Exporte segmentos de perfís de clientes unificados a Autopilot e utilíceos para campañas e mercadotecnia por correo electrónico en Autopilot.</span><span class="sxs-lookup"><span data-stu-id="9a6c7-104">Export segments of unified customer profiles to Autopilot and use them for email marketing in Autopilot.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="9a6c7-105">Requisitos previos para unha conexión</span><span class="sxs-lookup"><span data-stu-id="9a6c7-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="9a6c7-106">Ten unha [Conta de Autopilot](https://www.autopilothq.com/) e as correspondentes credenciais de administrador.</span><span class="sxs-lookup"><span data-stu-id="9a6c7-106">You have an [Autopilot account](https://www.autopilothq.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="9a6c7-107">Ten [segmentos configurados](segments.md) na información do público.</span><span class="sxs-lookup"><span data-stu-id="9a6c7-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="9a6c7-108">Os perfís de clientes unificados nos segmentos exportados conteñen un campo que representa un enderezo de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="9a6c7-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="9a6c7-109">Limitacións coñecidas</span><span class="sxs-lookup"><span data-stu-id="9a6c7-109">Known limitations</span></span>

- <span data-ttu-id="9a6c7-110">Pode exportar ata 100.000 perfís en total a Autopilot.</span><span class="sxs-lookup"><span data-stu-id="9a6c7-110">You can export up to 100'000 profiles in total to Autopilot.</span></span>
- <span data-ttu-id="9a6c7-111">A exportación a Autopilot está limitada a segmentos.</span><span class="sxs-lookup"><span data-stu-id="9a6c7-111">Exporting to Autopilot is limited to segments.</span></span>
- <span data-ttu-id="9a6c7-112">Exportar ata 100.000 perfís a Autopilot pode tardar unhas horas en completarse.</span><span class="sxs-lookup"><span data-stu-id="9a6c7-112">Exporting up to 100'000 profiles to Autopilot can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="9a6c7-113">O número de perfís que pode exportar a Autopilot depende e está limitado no seu contrato con Autopilot.</span><span class="sxs-lookup"><span data-stu-id="9a6c7-113">The number of profiles that you can export to Autopilot is dependent and limited on your contract with Autopilot.</span></span>

## <a name="set-up-connection-to-autopilot"></a><span data-ttu-id="9a6c7-114">Configurar conexión a Autopilot</span><span class="sxs-lookup"><span data-stu-id="9a6c7-114">Set up connection to Autopilot</span></span>

1. <span data-ttu-id="9a6c7-115">Vaia a **Administrar** > **Conexións**.</span><span class="sxs-lookup"><span data-stu-id="9a6c7-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="9a6c7-116">Seleccione **Engadir conexión** e elixa **Autopilot** para configurar a conexión.</span><span class="sxs-lookup"><span data-stu-id="9a6c7-116">Select **Add connection** and choose **Autopilot** to configure the connection.</span></span>

1. <span data-ttu-id="9a6c7-117">Déalle á conexión un nome recoñecible no campo **Nome para mostrar**.</span><span class="sxs-lookup"><span data-stu-id="9a6c7-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="9a6c7-118">O nome e o tipo de conexión describen esta conexión.</span><span class="sxs-lookup"><span data-stu-id="9a6c7-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="9a6c7-119">Recomendamos escoller un nome que explique o propósito e o destino da conexión.</span><span class="sxs-lookup"><span data-stu-id="9a6c7-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="9a6c7-120">Escolla quen pode usar esta conexión.</span><span class="sxs-lookup"><span data-stu-id="9a6c7-120">Choose who can use this connection.</span></span> <span data-ttu-id="9a6c7-121">Se non realiza ningunha acción, o valor predeterminado será Administradores.</span><span class="sxs-lookup"><span data-stu-id="9a6c7-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="9a6c7-122">Para obter máis información, consulte [Permitir aos colaboradores usar unha conexión para as exportacións](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="9a6c7-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

3. <span data-ttu-id="9a6c7-123">Introduza a súa [Clave da API de Autopilot](https://autopilot.docs.apiary.io/#).</span><span class="sxs-lookup"><span data-stu-id="9a6c7-123">Enter your [Autopilot API key](https://autopilot.docs.apiary.io/#).</span></span>

1. <span data-ttu-id="9a6c7-124">Seleccione **Estou de acordo** para confirmar a **Privacidade e cumprimento dos datos**.</span><span class="sxs-lookup"><span data-stu-id="9a6c7-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="9a6c7-125">Seleccione **Conectar** para inicializar a conexión a Autopilot.</span><span class="sxs-lookup"><span data-stu-id="9a6c7-125">Select **Connect** to initialize the connection to Autopilot.</span></span>

1. <span data-ttu-id="9a6c7-126">Seleccione **Autoengadirse como usuario de exportación** e proporcione as súas credenciais de Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="9a6c7-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="9a6c7-127">Seleccione **Gardar** para completar a conexión.</span><span class="sxs-lookup"><span data-stu-id="9a6c7-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="9a6c7-128">Configurar unha exportación</span><span class="sxs-lookup"><span data-stu-id="9a6c7-128">Configure an export</span></span>

<span data-ttu-id="9a6c7-129">Pode configurar esta exportación se ten acceso a unha conexión deste tipo.</span><span class="sxs-lookup"><span data-stu-id="9a6c7-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="9a6c7-130">Para obter máis información, consulte [Permisos necesarios para configurar unha exportación](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="9a6c7-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="9a6c7-131">Vaia a **Datos** > **Exportacións**.</span><span class="sxs-lookup"><span data-stu-id="9a6c7-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="9a6c7-132">Seleccione **Engadir destino** para crear unha nova exportación.</span><span class="sxs-lookup"><span data-stu-id="9a6c7-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="9a6c7-133">No campo **Conexión da exportación** escolla unha conexión da sección Autopilot.</span><span class="sxs-lookup"><span data-stu-id="9a6c7-133">In the **Connection for export** field, choose a connection from the Autopilot section.</span></span> <span data-ttu-id="9a6c7-134">Se non ve o nome desta sección, non hai conexións deste tipo dispoñibles para vostede.</span><span class="sxs-lookup"><span data-stu-id="9a6c7-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

3. <span data-ttu-id="9a6c7-135">Na sección **Coincidencia de datos**, no campo **Correo electrónico**, seleccione o campo do seu perfil de cliente unificado que representa o enderezo de correo electrónico dun cliente.</span><span class="sxs-lookup"><span data-stu-id="9a6c7-135">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="9a6c7-136">Repita os mesmos pasos para outros campos opcionais como **nome**, **apelidos**.</span><span class="sxs-lookup"><span data-stu-id="9a6c7-136">Repeat the same steps for other optional fields such as **First name**, **Last name**.</span></span>

1. <span data-ttu-id="9a6c7-137">Seleccione os segmentos que desexa exportar.</span><span class="sxs-lookup"><span data-stu-id="9a6c7-137">Select the segments you want to export.</span></span> <span data-ttu-id="9a6c7-138">Nós fortemente **recomendamos non exportar máis de 100.000 perfís de clientes en total** a Autopilot.</span><span class="sxs-lookup"><span data-stu-id="9a6c7-138">We strongly **recommend to not export more than 100'000 customer profiles in total** to Autopilot.</span></span> 

1. <span data-ttu-id="9a6c7-139">Seleccione **Gardar**.</span><span class="sxs-lookup"><span data-stu-id="9a6c7-139">Select **Save**.</span></span>

<span data-ttu-id="9a6c7-140">Ao gardar unha exportación non se executa a exportación inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="9a6c7-140">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="9a6c7-141">A exportación execútase con cada [actualización programada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="9a6c7-141">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="9a6c7-142">Tamén pode [exportar datos baixo demanda](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="9a6c7-142">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="9a6c7-143">Cumprimento e privacidade dos datos</span><span class="sxs-lookup"><span data-stu-id="9a6c7-143">Data privacy and compliance</span></span>

<span data-ttu-id="9a6c7-144">Cando habilita Dynamics 365 Customer Insights para transmitir datos a Autopilot, permite a transferencia de datos fóra do límite de cumprimento de Dynamics 365 Customer Insights, incluíndo datos potencialmente confidenciais como os datos persoais.</span><span class="sxs-lookup"><span data-stu-id="9a6c7-144">When you enable Dynamics 365 Customer Insights to transmit data to Autopilot, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="9a6c7-145">Microsoft transferirá estes datos segundo a súa instrución, pero vostede é responsable de garantir que Autopilot cumpra as obrigas de privacidade ou seguridade que poida ter.</span><span class="sxs-lookup"><span data-stu-id="9a6c7-145">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Autopilot meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="9a6c7-146">Para obter máis información, consulte a [Declaración de privacidade de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="9a6c7-146">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="9a6c7-147">O administrador de Dynamics 365 Customer Insights pode eliminar este destino de exportación en calquera momento para interromper o uso desta funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="9a6c7-147">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
