---
title: Exportar datos de Customer Insights a Mailchimp
description: Aprenda a configurar a conexión e exportar a Mailchimp.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 7922a6a69f863caae5401549ed6f88a61aa77d39
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124225"
---
# <a name="export-segments-to-mailchimp-preview"></a><span data-ttu-id="7fc96-103">Exportar segmentos a Mailchimp (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="7fc96-103">Export segments to Mailchimp (preview)</span></span>

<span data-ttu-id="7fc96-104">Exporte segmentos de perfís de clientes unificados a Mailchimp para crear boletíns e campañas de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="7fc96-104">Export segments of unified customer profiles to Mailchimp to create newsletters and email campaigns.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="7fc96-105">Requisitos previos para a conexión</span><span class="sxs-lookup"><span data-stu-id="7fc96-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="7fc96-106">Ten unha [Conta de Mailchimp](https://mailchimp.com/) e as correspondentes credenciais de administrador.</span><span class="sxs-lookup"><span data-stu-id="7fc96-106">You have a [Mailchimp account](https://mailchimp.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="7fc96-107">Existen públicos en Mailchimp e os ID correspondentes.</span><span class="sxs-lookup"><span data-stu-id="7fc96-107">There are existing audiences in Mailchimp and the corresponding IDs.</span></span> <span data-ttu-id="7fc96-108">Para obter máis información, consulte [públicos de Mailchimp](https://mailchimp.com/help/create-audience/).</span><span class="sxs-lookup"><span data-stu-id="7fc96-108">For more information, see [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>
-   <span data-ttu-id="7fc96-109">Ten [segmentos configurados](segments.md)</span><span class="sxs-lookup"><span data-stu-id="7fc96-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="7fc96-110">Os perfís de clientes unificados nos segmentos exportados conteñen un campo que representa un enderezo de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="7fc96-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="7fc96-111">Limitacións coñecidas</span><span class="sxs-lookup"><span data-stu-id="7fc96-111">Known limitations</span></span>

- <span data-ttu-id="7fc96-112">Ata 1 millón de perfís por exportación a Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="7fc96-112">Up to 1 million profiles per export to Mailchimp.</span></span>
- <span data-ttu-id="7fc96-113">A exportación a Mailchimp está limitada a segmentos.</span><span class="sxs-lookup"><span data-stu-id="7fc96-113">Exporting to Mailchimp is limited to segments.</span></span>
- <span data-ttu-id="7fc96-114">Exportar segmentos cun millón de perfís pode levar ata tres horas.</span><span class="sxs-lookup"><span data-stu-id="7fc96-114">Exporting segments with 1 million profiles can take up to three hours.</span></span> 
- <span data-ttu-id="7fc96-115">O número de perfís que pode exportar a Mailchimp depende e está limitado no seu contrato con Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="7fc96-115">The number of profiles that you can export to Mailchimp is dependent and limited on your contract with Mailchimp.</span></span>

## <a name="set-up-connection-to-mailchimp"></a><span data-ttu-id="7fc96-116">Configurar conexión a Mailchimp</span><span class="sxs-lookup"><span data-stu-id="7fc96-116">Set up connection to Mailchimp</span></span>

1. <span data-ttu-id="7fc96-117">Vaia a **Administrar** > **Conexións**.</span><span class="sxs-lookup"><span data-stu-id="7fc96-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="7fc96-118">Seleccione **Engadir conexión** e elixa **Autopilot** para configurar a conexión.</span><span class="sxs-lookup"><span data-stu-id="7fc96-118">Select **Add connection** and choose **Autopilot** to configure the connection.</span></span>

1. <span data-ttu-id="7fc96-119">Déalle á conexión un nome recoñecible no campo **Nome para mostrar**.</span><span class="sxs-lookup"><span data-stu-id="7fc96-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="7fc96-120">O nome e o tipo de conexión describen esta conexión.</span><span class="sxs-lookup"><span data-stu-id="7fc96-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="7fc96-121">Recomendamos escoller un nome que explique o propósito e o destino da conexión.</span><span class="sxs-lookup"><span data-stu-id="7fc96-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="7fc96-122">Escolla quen pode usar esta conexión.</span><span class="sxs-lookup"><span data-stu-id="7fc96-122">Choose who can use this connection.</span></span> <span data-ttu-id="7fc96-123">Se non realiza ningunha acción, o valor predeterminado será Administradores.</span><span class="sxs-lookup"><span data-stu-id="7fc96-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="7fc96-124">Para obter máis información, consulte [Permitir aos colaboradores usar unha conexión para as exportacións](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="7fc96-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="7fc96-125">Seleccione **Estou de acordo** para confirmar a **Privacidade e cumprimento dos datos**.</span><span class="sxs-lookup"><span data-stu-id="7fc96-125">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="7fc96-126">Seleccione **Conectar** para iniciar a conexión a Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="7fc96-126">Select **Connect** to initialize the connection to Mailchimp.</span></span>

1. <span data-ttu-id="7fc96-127">Seleccione **Autenticarse con Mailchimp** e proporcione as súas credenciais de Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="7fc96-127">Select **Authenticate with Mailchimp** and provide your Mailchimp credentials.</span></span>

1. <span data-ttu-id="7fc96-128">Seleccione **Autoengadirse como usuario de exportación** e proporcione as súas credenciais de Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="7fc96-128">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="7fc96-129">Seleccione **Gardar** para completar a conexión.</span><span class="sxs-lookup"><span data-stu-id="7fc96-129">Select **Save** to complete the connection.</span></span> 

## <a name="configure-the-connector"></a><span data-ttu-id="7fc96-130">Configurar o conector</span><span class="sxs-lookup"><span data-stu-id="7fc96-130">Configure the connector</span></span>

<span data-ttu-id="7fc96-131">Pode configurar esta exportación se ten acceso a unha conexión deste tipo.</span><span class="sxs-lookup"><span data-stu-id="7fc96-131">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="7fc96-132">Para obter máis información, consulte [Permisos necesarios para configurar unha exportación](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="7fc96-132">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="7fc96-133">Vaia a **Datos**> **Exportacións**.</span><span class="sxs-lookup"><span data-stu-id="7fc96-133">Go to **Data**> **Exports**.</span></span>

1. <span data-ttu-id="7fc96-134">Seleccione **Engadir destino** para crear unha nova exportación.</span><span class="sxs-lookup"><span data-stu-id="7fc96-134">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="7fc96-135">No campo **Conexión da exportación** escolla unha conexión da sección Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="7fc96-135">In the **Connection for export** field, choose a connection from the Mailchimp section.</span></span> <span data-ttu-id="7fc96-136">Se non ve o nome desta sección, non hai conexións deste tipo dispoñibles para vostede.</span><span class="sxs-lookup"><span data-stu-id="7fc96-136">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="7fc96-137">Insira o seu **[ID de público de MailChimp](https://mailchimp.com/help/find-audience-id/)**</span><span class="sxs-lookup"><span data-stu-id="7fc96-137">Enter your **[Mailchimp audience ID](https://mailchimp.com/help/find-audience-id/)**</span></span>

3. <span data-ttu-id="7fc96-138">Na sección **Coincidencia de datos**, no campo **Correo electrónico**, seleccione o campo do seu perfil de cliente unificado que representa o enderezo de correo electrónico dun cliente.</span><span class="sxs-lookup"><span data-stu-id="7fc96-138">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="7fc96-139">Opcionalmente, pode exportar o **nome** e **apelidos** para crear correos electrónicos máis personalizados.</span><span class="sxs-lookup"><span data-stu-id="7fc96-139">Optionally, you can export **First name** and **Last name** to create more personalized emails.</span></span> <span data-ttu-id="7fc96-140">Seleccione **Engadir atributo** para asignar estes campos.</span><span class="sxs-lookup"><span data-stu-id="7fc96-140">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="7fc96-141">Seleccione os segmentos que desexa exportar.</span><span class="sxs-lookup"><span data-stu-id="7fc96-141">Select the segments you want to export.</span></span> <span data-ttu-id="7fc96-142">Pode exportar ata 1 millón de perfís de clientes en total a Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="7fc96-142">You can export up to 1 million customer profiles in total to Mailchimp.</span></span>

1. <span data-ttu-id="7fc96-143">Seleccione **Gardar**.</span><span class="sxs-lookup"><span data-stu-id="7fc96-143">Select **Save**.</span></span>

<span data-ttu-id="7fc96-144">Ao gardar unha exportación non se executa a exportación inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="7fc96-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="7fc96-145">A exportación execútase con cada [actualización programada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="7fc96-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="7fc96-146">Tamén pode [exportar datos baixo demanda](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="7fc96-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="7fc96-147">Cumprimento e privacidade dos datos</span><span class="sxs-lookup"><span data-stu-id="7fc96-147">Data privacy and compliance</span></span>

<span data-ttu-id="7fc96-148">Cando habilita Dynamics 365 Customer Insights para transmitir datos a Mailchimp, permite a transferencia de datos fóra do límite de cumprimento de Dynamics 365 Customer Insights, incluíndo datos potencialmente confidenciais como os datos persoais.</span><span class="sxs-lookup"><span data-stu-id="7fc96-148">When you enable Dynamics 365 Customer Insights to transmit data to Mailchimp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="7fc96-149">Microsoft transferirá estes datos segundo a súa instrución, pero vostede é responsable de garantir que Mailchimp cumpra as obrigas de privacidade ou seguridade que poida ter.</span><span class="sxs-lookup"><span data-stu-id="7fc96-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Mailchimp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="7fc96-150">Para obter máis información, consulte a [Declaración de privacidade de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="7fc96-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="7fc96-151">O administrador de Dynamics 365 Customer Insights pode eliminar este destino de exportación en calquera momento para interromper o uso desta funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="7fc96-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
