---
title: Exportar datos de Customer Insights a Sendinblue
description: Aprenda a configurar a conexión e exportar a Sendinblue.
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 58ca0ae5ad4a3a291f4336984d14fefb23a58ab3
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314610"
---
# <a name="export-segments-to-sendinblue-preview"></a><span data-ttu-id="13586-103">Exportar segmentos a Sendinblue (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="13586-103">Export segments to Sendinblue (preview)</span></span>

<span data-ttu-id="13586-104">Exportar segmentos de perfís de clientes unificados para xerar campañas, proporcionar márketing por correo electrónico e usar grupos específicos de clientes con Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="13586-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Sendinblue.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="13586-105">Requisitos previos para a conexión</span><span class="sxs-lookup"><span data-stu-id="13586-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="13586-106">Ten unha [conta de Sendinblue](https://www.sendinblue.com/) e as correspondentes credenciais de administrador.</span><span class="sxs-lookup"><span data-stu-id="13586-106">You have a [Sendinblue account](https://www.sendinblue.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="13586-107">Hai listas existentes en Sendinblue e os ID correspondentes.</span><span class="sxs-lookup"><span data-stu-id="13586-107">There are existing lists in Sendinblue and the corresponding IDs.</span></span>
-   <span data-ttu-id="13586-108">Ten [segmentos configurados](segments.md).</span><span class="sxs-lookup"><span data-stu-id="13586-108">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="13586-109">Os perfís de clientes unificados nos segmentos exportados conteñen un campo que representa un enderezo de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="13586-109">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="13586-110">Limitacións coñecidas</span><span class="sxs-lookup"><span data-stu-id="13586-110">Known limitations</span></span>

- <span data-ttu-id="13586-111">Ata 1 millón de perfís por exportación a Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="13586-111">Up to 1 million profiles per export to Sendinblue.</span></span>
- <span data-ttu-id="13586-112">A exportación a Sendinblue está limitada a segmentos.</span><span class="sxs-lookup"><span data-stu-id="13586-112">Exporting to Sendinblue is limited to segments.</span></span>
- <span data-ttu-id="13586-113">A exportación de segmentos cun total de 1 millón de perfís pode levar ata 90 minutos.</span><span class="sxs-lookup"><span data-stu-id="13586-113">Exporting segments with a total of 1 million profiles can take up to 90 minutes.</span></span> 
- <span data-ttu-id="13586-114">O número de perfís que pode exportar a Sendinblue depende e está limitado ao seu contrato con Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="13586-114">The number of profiles that you can export to Sendinblue is dependent and limited on your contract with Sendinblue.</span></span>

## <a name="set-up-connection-to-sendinblue"></a><span data-ttu-id="13586-115">Configurar conexión a Sendinblue</span><span class="sxs-lookup"><span data-stu-id="13586-115">Set up connection to Sendinblue</span></span>

1. <span data-ttu-id="13586-116">Vaia a **Administrar** > **Conexións**.</span><span class="sxs-lookup"><span data-stu-id="13586-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="13586-117">Seleccione **Engadir conexión** e elixa **Sendinblue** para configurar a conexión.</span><span class="sxs-lookup"><span data-stu-id="13586-117">Select **Add connection** and choose **Sendinblue** to configure the connection.</span></span>

1. <span data-ttu-id="13586-118">Déalle á conexión un nome recoñecible no campo **Nome para mostrar**.</span><span class="sxs-lookup"><span data-stu-id="13586-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="13586-119">O nome e o tipo de conexión describen esta conexión.</span><span class="sxs-lookup"><span data-stu-id="13586-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="13586-120">Recomendamos escoller un nome que explique o propósito e o destino da conexión.</span><span class="sxs-lookup"><span data-stu-id="13586-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="13586-121">Escolla quen pode usar esta conexión.</span><span class="sxs-lookup"><span data-stu-id="13586-121">Choose who can use this connection.</span></span> <span data-ttu-id="13586-122">Por defecto só son os administradores.</span><span class="sxs-lookup"><span data-stu-id="13586-122">By default it's only administrators.</span></span> <span data-ttu-id="13586-123">Para obter máis información, consulte [Permitir aos colaboradores usar unha conexión para as exportacións](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="13586-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="13586-124">Introduza a súa **[clave de API de SendinBlue](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**.</span><span class="sxs-lookup"><span data-stu-id="13586-124">Enter your **[SendinBlue API key](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**.</span></span>

1. <span data-ttu-id="13586-125">Seleccione **Estou de acordo** para confirmar a **Privacidade e cumprimento dos datos** e seleccione **Conectar** para iniciar a conexión con Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="13586-125">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Sendinblue.</span></span>

1. <span data-ttu-id="13586-126">Seleccione **Autoengadirse como usuario de exportación** e proporcione as súas credenciais de Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="13586-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="13586-127">Seleccione **Gardar** para completar a conexión.</span><span class="sxs-lookup"><span data-stu-id="13586-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="13586-128">Configurar unha exportación</span><span class="sxs-lookup"><span data-stu-id="13586-128">Configure an export</span></span>

<span data-ttu-id="13586-129">Pode configurar esta exportación se ten acceso a unha conexión deste tipo.</span><span class="sxs-lookup"><span data-stu-id="13586-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="13586-130">Para obter máis información, consulte [Permisos necesarios para configurar unha exportación](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="13586-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="13586-131">Vaia a **Datos** > **Exportacións**.</span><span class="sxs-lookup"><span data-stu-id="13586-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="13586-132">Seleccione **Engadir destino** para crear unha nova exportación.</span><span class="sxs-lookup"><span data-stu-id="13586-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="13586-133">No campo **Conexión para a exportación**, escolla unha conexión na sección Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="13586-133">In the **Connection for export** field, choose a connection from the Sendinblue section.</span></span> <span data-ttu-id="13586-134">Se non ve o nome desta sección, non hai conexións deste tipo dispoñibles para vostede.</span><span class="sxs-lookup"><span data-stu-id="13586-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="13586-135">Introduza o seu **ID de lista de SendinBlue**</span><span class="sxs-lookup"><span data-stu-id="13586-135">Enter your **Sendinblue list ID**</span></span> 

1. <span data-ttu-id="13586-136">Na sección **Coincidencia de datos**, no campo **Correo electrónico**, seleccione o campo do seu perfil de cliente unificado que representa o enderezo de correo electrónico dun cliente.</span><span class="sxs-lookup"><span data-stu-id="13586-136">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="13586-137">Opcionalmente, pode exportar **nome**, **apelidos** e **Teléfono** para crear correos electrónicos máis personalizados.</span><span class="sxs-lookup"><span data-stu-id="13586-137">Optionally, you can export **First name**, **Last name**, and **Phone**  to create more personalized emails.</span></span> <span data-ttu-id="13586-138">Seleccione **Engadir atributo** para asignar estes campos.</span><span class="sxs-lookup"><span data-stu-id="13586-138">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="13586-139">Seleccione os segmentos que desexa exportar.</span><span class="sxs-lookup"><span data-stu-id="13586-139">Select the segments you want to export.</span></span> 

1. <span data-ttu-id="13586-140">Seleccione **Gardar**.</span><span class="sxs-lookup"><span data-stu-id="13586-140">Select **Save**.</span></span>

<span data-ttu-id="13586-141">Ao gardar unha exportación non se executa a exportación inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="13586-141">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="13586-142">A exportación execútase con cada [actualización programada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="13586-142">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="13586-143">Tamén pode [exportar datos baixo demanda](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="13586-143">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="13586-144">Cumprimento e privacidade dos datos</span><span class="sxs-lookup"><span data-stu-id="13586-144">Data privacy and compliance</span></span>

<span data-ttu-id="13586-145">Cando permite a Dynamics 365 Customer Insights transmitir datos a Sendinblue, permite a transferencia de datos fóra do límite de cumprimento de Dynamics 365 Customer Insights, incluíndo datos potencialmente confidenciais como os datos persoais.</span><span class="sxs-lookup"><span data-stu-id="13586-145">When you enable Dynamics 365 Customer Insights to transmit data to Sendinblue, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="13586-146">Microsoft transferirá estes datos segundo a súa instrución, pero vostede é responsable de asegurarse de que Sendinblue cumpre coas obrigacións de privacidade ou seguridade que poida ter.</span><span class="sxs-lookup"><span data-stu-id="13586-146">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Sendinblue meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="13586-147">Para obter máis información, consulte a [Declaración de privacidade de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="13586-147">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="13586-148">O administrador de Dynamics 365 Customer Insights pode eliminar este destino de exportación en calquera momento para interromper o uso desta funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="13586-148">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
