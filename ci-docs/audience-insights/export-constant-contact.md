---
title: Exportar datos de Customer Insights a Constant Contact
description: Aprenda a configurar a conexión e exportar a Constant Contact.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 29f4320c798db62609283e3c48f0b47a4f0b982f
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124271"
---
# <a name="export-segments-to-constant-contact-preview"></a><span data-ttu-id="c675f-103">Exportar segmentos a Constant Contact (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="c675f-103">Export segments to Constant Contact (preview)</span></span>

<span data-ttu-id="c675f-104">Exporte segmentos de perfís de clientes unificados a Constant Contact e utilíceos para actividades de mercadotecnia.</span><span class="sxs-lookup"><span data-stu-id="c675f-104">Export segments of unified customer profiles to Constant Contact and use them for marketing activities.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="c675f-105">Requisitos previos para unha conexión</span><span class="sxs-lookup"><span data-stu-id="c675f-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="c675f-106">Ten unha [conta de Constant Contact](https://www.constantcontact.com/account-home) e as correspondentes credenciais de administrador.</span><span class="sxs-lookup"><span data-stu-id="c675f-106">You have an [Constant Contact account](https://www.constantcontact.com/account-home) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="c675f-107">Ten [segmentos configurados](segments.md) na información do público.</span><span class="sxs-lookup"><span data-stu-id="c675f-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="c675f-108">Os perfís de clientes unificados nos segmentos exportados conteñen un campo que representa un enderezo de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="c675f-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="c675f-109">Limitacións coñecidas</span><span class="sxs-lookup"><span data-stu-id="c675f-109">Known limitations</span></span>

- <span data-ttu-id="c675f-110">Pode exportar ata 1 millón de perfís por exportación a Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="c675f-110">You can export up to 1 million profiles per export to Constant Contact.</span></span>
- <span data-ttu-id="c675f-111">A exportación a Constant Contact está limitada a segmentos.</span><span class="sxs-lookup"><span data-stu-id="c675f-111">Exporting to Constant Contact is limited to segments.</span></span>
- <span data-ttu-id="c675f-112">A exportación de segmentos de ata 1 millón de perfís a Constant Contact pode tardar ata 1 hora en finalizar.</span><span class="sxs-lookup"><span data-stu-id="c675f-112">Exporting up to 1 million profiles to Constant Contact can take up to 1 hour to complete.</span></span> 
- <span data-ttu-id="c675f-113">O número de perfís que pode exportar a Constant Contact depende e está limitado ao seu contrato con Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="c675f-113">The number of profiles that you can export to Constant Contact is dependent and limited on your contract with Constant Contact.</span></span>

## <a name="set-up-connection-to-constant-contact"></a><span data-ttu-id="c675f-114">Configurar a conexión a Constant Contact</span><span class="sxs-lookup"><span data-stu-id="c675f-114">Set up connection to Constant Contact</span></span>

1. <span data-ttu-id="c675f-115">Vaia a **Administrar** > **Conexións**.</span><span class="sxs-lookup"><span data-stu-id="c675f-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="c675f-116">Seleccione **Engadir conexión** e elixa **Constant Contact** para configurar a conexión.</span><span class="sxs-lookup"><span data-stu-id="c675f-116">Select **Add connection** and choose **Constant Contact** to configure the connection.</span></span>

1. <span data-ttu-id="c675f-117">Déalle á conexión un nome recoñecible no campo **Nome para mostrar**.</span><span class="sxs-lookup"><span data-stu-id="c675f-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="c675f-118">O nome e o tipo de conexión describen esta conexión.</span><span class="sxs-lookup"><span data-stu-id="c675f-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="c675f-119">Recomendamos escoller un nome que explique o propósito e o destino da conexión.</span><span class="sxs-lookup"><span data-stu-id="c675f-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="c675f-120">Escolla quen pode usar esta conexión.</span><span class="sxs-lookup"><span data-stu-id="c675f-120">Choose who can use this connection.</span></span> <span data-ttu-id="c675f-121">Se non realiza ningunha acción, o valor predeterminado será Administradores.</span><span class="sxs-lookup"><span data-stu-id="c675f-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="c675f-122">Para obter máis información, consulte [Permitir aos colaboradores usar unha conexión para as exportacións](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="c675f-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="c675f-123">Seleccione **Estou de acordo** para confirmar a **Privacidade e cumprimento dos datos**.</span><span class="sxs-lookup"><span data-stu-id="c675f-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="c675f-124">Seleccione **Conectar** para iniciar a conexión a Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="c675f-124">Select **Connect** to initialize the connection to Constant Contact.</span></span>

1. <span data-ttu-id="c675f-125">Seleccione **Autenticarse con AdRoll** e proporcione as súas credenciais de administrador de Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="c675f-125">Select **Authenticate with AdRoll** and provide your admin credentials for Constant Contact.</span></span> 

1. <span data-ttu-id="c675f-126">Seleccione **Autoengadirse como usuario de exportación** e proporcione as súas credenciais de Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="c675f-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="c675f-127">Seleccione **Gardar** para completar a conexión.</span><span class="sxs-lookup"><span data-stu-id="c675f-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="c675f-128">Configurar unha exportación</span><span class="sxs-lookup"><span data-stu-id="c675f-128">Configure an export</span></span>

<span data-ttu-id="c675f-129">Pode configurar esta exportación se ten acceso a unha conexión deste tipo.</span><span class="sxs-lookup"><span data-stu-id="c675f-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="c675f-130">Para obter máis información, consulte [Permisos necesarios para configurar unha exportación](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="c675f-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="c675f-131">Vaia a **Datos** > **Exportacións**.</span><span class="sxs-lookup"><span data-stu-id="c675f-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="c675f-132">Seleccione **Engadir destino** para crear unha nova exportación.</span><span class="sxs-lookup"><span data-stu-id="c675f-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="c675f-133">No campo **Conexión da exportación** escolla unha conexión da sección Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="c675f-133">In the **Connection for export** field, choose a connection from the Constant Contact section.</span></span> <span data-ttu-id="c675f-134">Se non ve o nome desta sección, non hai conexións deste tipo dispoñibles para vostede.</span><span class="sxs-lookup"><span data-stu-id="c675f-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="c675f-135">Insira o seu [**ID de lista Constant Contact**](https://app.constantcontact.com/pages/contacts/ui#lists).</span><span class="sxs-lookup"><span data-stu-id="c675f-135">Enter your [**Constant Contact List ID**](https://app.constantcontact.com/pages/contacts/ui#lists).</span></span> <span data-ttu-id="c675f-136">Abra unha lista en Constant Contact para atopar o ID da lista no URL.</span><span class="sxs-lookup"><span data-stu-id="c675f-136">Open a list in Constant Contact to find the list ID in the URL.</span></span>

1. <span data-ttu-id="c675f-137">Na sección **Coincidencia de datos**, no campo **Correo electrónico**, seleccione o campo do seu perfil de cliente unificado que representa o enderezo de correo electrónico dun cliente.</span><span class="sxs-lookup"><span data-stu-id="c675f-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="c675f-138">É necesario exportar segmentos a Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="c675f-138">It's required to export segments to Constant Contact.</span></span>

1. <span data-ttu-id="c675f-139">Opcionalmente, pode exportar o nome e os apelidos como campos adicionais para crear correos electrónicos máis personalizados.</span><span class="sxs-lookup"><span data-stu-id="c675f-139">Optionally, you can export First name and Last name as additional fields to create more personalized emails.</span></span> <span data-ttu-id="c675f-140">Seleccione **Engadir atributo** para asignar estes campos.</span><span class="sxs-lookup"><span data-stu-id="c675f-140">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="c675f-141">Seleccione os segmentos que desexa exportar.</span><span class="sxs-lookup"><span data-stu-id="c675f-141">Select the segments you want to export.</span></span>

1. <span data-ttu-id="c675f-142">Seleccione **Gardar**.</span><span class="sxs-lookup"><span data-stu-id="c675f-142">Select **Save**.</span></span>

<span data-ttu-id="c675f-143">Ao gardar unha exportación non se executa a exportación inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="c675f-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="c675f-144">A exportación execútase con cada [actualización programada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="c675f-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="c675f-145">Tamén pode [exportar datos baixo demanda](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="c675f-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="c675f-146">Cumprimento e privacidade dos datos</span><span class="sxs-lookup"><span data-stu-id="c675f-146">Data privacy and compliance</span></span>

<span data-ttu-id="c675f-147">Cando habilita Dynamics 365 Customer Insights para transmitir datos a Constant Contact, permite a transferencia de datos fóra do límite de cumprimento de Dynamics 365 Customer Insights, incluíndo datos potencialmente confidenciais como os datos persoais.</span><span class="sxs-lookup"><span data-stu-id="c675f-147">When you enable Dynamics 365 Customer Insights to transmit data to Constant Contact, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="c675f-148">Microsoft transferirá estes datos segundo a súa instrución, pero vostede é responsable de asegurarse de que Constant Contact cumpra as obrigas de privacidade ou seguridade que poida ter.</span><span class="sxs-lookup"><span data-stu-id="c675f-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Constant Contact meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="c675f-149">Para obter máis información, consulte a [Declaración de privacidade de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="c675f-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="c675f-150">O administrador de Dynamics 365 Customer Insights pode eliminar este destino de exportación en calquera momento para interromper o uso desta funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="c675f-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
