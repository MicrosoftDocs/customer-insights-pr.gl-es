---
title: Exportar datos de Customer Insights a Microsoft Advertising
description: Aprenda a configurar a conexión e exportar a Microsoft Advertising.
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c2ac92de2718cf7f0622b407bf198a7a7e50a37b
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124486"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a><span data-ttu-id="de475-103">Exportar segmentos a Microsoft Advertising (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="de475-103">Export segments to Microsoft Advertising (preview)</span></span>

<span data-ttu-id="de475-104">Exporte segmentos de Customer Insights a Microsoft Advertising para crear públicos de Coincidencia de clientes.</span><span class="sxs-lookup"><span data-stu-id="de475-104">Export Customer Insights segments to Microsoft Advertising to create Customer Match audiences.</span></span> <span data-ttu-id="de475-105">Use estes públicos para as súas campañas publicitarias.</span><span class="sxs-lookup"><span data-stu-id="de475-105">Use these audiences for your ad campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="de475-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="de475-106">Prerequisites</span></span>

-   <span data-ttu-id="de475-107">Unha [conta de Microsoft Advertising](https://ads.microsoft.com/) e as correspondentes credenciais de administrador.</span><span class="sxs-lookup"><span data-stu-id="de475-107">An [Microsoft Advertising account](https://ads.microsoft.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="de475-108">Aceptou as condicións de uso de Coincidencia de clientes.</span><span class="sxs-lookup"><span data-stu-id="de475-108">You've accepted the Customer Match terms of use.</span></span> 
-   <span data-ttu-id="de475-109">[Segmentos configurados](segments.md) na información do público.</span><span class="sxs-lookup"><span data-stu-id="de475-109">[Configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="de475-110">Os perfís de clientes unificados nos segmentos exportados conteñen un campo cun enderezo de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="de475-110">Unified customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="de475-111">Limitacións coñecidas</span><span class="sxs-lookup"><span data-stu-id="de475-111">Known limitations</span></span>

- <span data-ttu-id="de475-112">Pode exportar ata 500 000 perfís por exportación a Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="de475-112">You can export up to 500 K profiles per export to Microsoft Advertising.</span></span>
- <span data-ttu-id="de475-113">A exportación a Microsoft Advertising está limitada a segmentos.</span><span class="sxs-lookup"><span data-stu-id="de475-113">Exporting to Microsoft Advertising is limited to segments.</span></span>
- <span data-ttu-id="de475-114">A exportación de ata 500 000 perfís a Microsoft Advertising pode tardar ata 10 minutos en finalizar.</span><span class="sxs-lookup"><span data-stu-id="de475-114">Exporting up to 500 K profiles to Microsoft Advertising can take up to 10 minutes to complete.</span></span> 


## <a name="set-up-the-connection-to-microsoft-advertising"></a><span data-ttu-id="de475-115">Configurar a conexión a Microsoft Advertising</span><span class="sxs-lookup"><span data-stu-id="de475-115">Set up the connection to Microsoft Advertising</span></span>

1. <span data-ttu-id="de475-116">Vaia a **Administrar** > **Conexións**.</span><span class="sxs-lookup"><span data-stu-id="de475-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="de475-117">Seleccione **Engadir conexión** e elixa **Microsoft Advertising** para configurar a conexión.</span><span class="sxs-lookup"><span data-stu-id="de475-117">Select **Add connection** and choose **Microsoft Advertising** to configure the connection.</span></span>

1. <span data-ttu-id="de475-118">Déalle á conexión un nome recoñecible no campo **Nome para mostrar**.</span><span class="sxs-lookup"><span data-stu-id="de475-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="de475-119">O nome e o tipo de conexión describen esta conexión.</span><span class="sxs-lookup"><span data-stu-id="de475-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="de475-120">Recomendamos escoller un nome que explique o propósito e o destino da conexión.</span><span class="sxs-lookup"><span data-stu-id="de475-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="de475-121">Escolla quen pode usar esta conexión.</span><span class="sxs-lookup"><span data-stu-id="de475-121">Choose who can use this connection.</span></span> <span data-ttu-id="de475-122">A opción predefinida é administradores.</span><span class="sxs-lookup"><span data-stu-id="de475-122">The default is administrators.</span></span> <span data-ttu-id="de475-123">Para obter máis información, consulte [Permitir aos colaboradores usar unha conexión para as exportacións](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="de475-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="de475-124">Seleccione **Estou de acordo** para confirmar a **Privacidade e cumprimento dos datos**.</span><span class="sxs-lookup"><span data-stu-id="de475-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="de475-125">Seleccione **Conectar** para iniciar a conexión a Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="de475-125">Select **Connect** to initialize the connection to Microsoft Advertising.</span></span>

1. <span data-ttu-id="de475-126">Seleccione **Autenticarse con Microsoft Advertising** e proporcione as súas credenciais de administrador de Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="de475-126">Select **Authenticate with Microsoft Advertising** and provide your admin credentials for Microsoft Advertising.</span></span>

1. <span data-ttu-id="de475-127">Seleccione **Autoengadirse como usuario de exportación** e proporcione as súas credenciais de Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="de475-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="de475-128">Seleccione **Gardar** para completar a conexión.</span><span class="sxs-lookup"><span data-stu-id="de475-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="de475-129">Configurar unha exportación</span><span class="sxs-lookup"><span data-stu-id="de475-129">Configure an export</span></span>

<span data-ttu-id="de475-130">Pode configurar esta exportación se ten acceso a unha conexión deste tipo.</span><span class="sxs-lookup"><span data-stu-id="de475-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="de475-131">Para obter máis información, consulte [Permisos necesarios para configurar unha exportación](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="de475-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="de475-132">Vaia a **Datos** > **Exportacións**.</span><span class="sxs-lookup"><span data-stu-id="de475-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="de475-133">Seleccione **Engadir destino** para crear unha nova exportación.</span><span class="sxs-lookup"><span data-stu-id="de475-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="de475-134">No campo **Conexión da exportación** escolla unha conexión da sección Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="de475-134">In the **Connection for export** field, choose a connection from the Microsoft Advertising section.</span></span> <span data-ttu-id="de475-135">Se non ve o nome desta sección, non hai conexións deste tipo dispoñibles para vostede.</span><span class="sxs-lookup"><span data-stu-id="de475-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="de475-136">Seleccione os segmentos que se van exportar.</span><span class="sxs-lookup"><span data-stu-id="de475-136">Select the segments to export.</span></span> <span data-ttu-id="de475-137">Os públicos de Coincidencia de clientes en Microsoft Advertising créanse automaticamente co nome dos segmentos seleccionados para a exportación.</span><span class="sxs-lookup"><span data-stu-id="de475-137">The Customer Match audiences in Microsoft Advertising are automatically created with the name of the segments selected for export.</span></span> <span data-ttu-id="de475-138">Cada segmento dará lugar a un público separado de Coincidencia de clientes.</span><span class="sxs-lookup"><span data-stu-id="de475-138">Each segment will result in a separate Customer Match audience.</span></span> 

1. <span data-ttu-id="de475-139">Introduza os seus **ID de cliente e conta de Microsoft Advertising**.</span><span class="sxs-lookup"><span data-stu-id="de475-139">Enter your **Microsoft Advertising Customer ID and Account ID**.</span></span> <span data-ttu-id="de475-140">Pode atopar o ID de cliente (`cid`) e o ID de conta (`aid`) nos parámetros do URL cando ten a sesión iniciada en Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="de475-140">You can find the Customer ID (`cid`) and Account ID (`aid`) in the parameters of the URL when you're signed in Microsoft Advertising.</span></span>

1. <span data-ttu-id="de475-141">Na sección **Coincidencia de datos**, no campo **Correo electrónico**, seleccione o campo do seu perfil de cliente unificado co enderezo de correo electrónico dun cliente.</span><span class="sxs-lookup"><span data-stu-id="de475-141">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile with a customer's email address.</span></span> <span data-ttu-id="de475-142">É necesario exportar segmentos a Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="de475-142">It's required to export segments to Microsoft Advertising.</span></span>

1. <span data-ttu-id="de475-143">Seleccione **Gardar**.</span><span class="sxs-lookup"><span data-stu-id="de475-143">Select **Save**.</span></span>

<span data-ttu-id="de475-144">Ao gardar unha exportación non se executa a exportación inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="de475-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="de475-145">A exportación execútase con cada [actualización programada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="de475-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="de475-146">Tamén pode [exportar datos baixo demanda](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="de475-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="de475-147">Cumprimento e privacidade dos datos</span><span class="sxs-lookup"><span data-stu-id="de475-147">Data privacy and compliance</span></span>

<span data-ttu-id="de475-148">Cando habilita Dynamics 365 Customer Insights para transmitir datos a Microsoft Advertising, permite a transferencia de datos fóra do límite de cumprimento de Dynamics 365 Customer Insights, incluíndo datos potencialmente confidenciais como os datos persoais.</span><span class="sxs-lookup"><span data-stu-id="de475-148">When you enable Dynamics 365 Customer Insights to transmit data to Microsoft Advertising, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="de475-149">Microsoft transferirá estes datos segundo a súa instrución, pero vostede é responsable de asegurarse de que Microsoft Advertising cumpra as obrigas de privacidade ou seguridade que poida ter.</span><span class="sxs-lookup"><span data-stu-id="de475-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Microsoft Advertising meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="de475-150">Para obter máis información, consulte a [Declaración de privacidade de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="de475-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="de475-151">O administrador de Dynamics 365 Customer Insights pode eliminar este destino de exportación en calquera momento para deter o uso desta funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="de475-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to stop use of this functionality.</span></span>
