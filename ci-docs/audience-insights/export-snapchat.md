---
title: Exportar datos de Customer Insights a Snapchat
description: Aprenda a configurar a conexión e exportar a Snapchat.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6565ab81599abcc0f94465e1153f08e0bc119839
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124041"
---
# <a name="export-segments-to-snapchat-preview"></a><span data-ttu-id="917b6-103">Exportar segmentos a Snapchat (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="917b6-103">Export segments to Snapchat (preview)</span></span>

<span data-ttu-id="917b6-104">Exporte segmentos de perfís de clientes unificados a Snapchat e utilíceos para a publicidade.</span><span class="sxs-lookup"><span data-stu-id="917b6-104">Export segments of unified customer profiles to Snapchat and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="917b6-105">Requisitos previos para unha conexión</span><span class="sxs-lookup"><span data-stu-id="917b6-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="917b6-106">Ten unha [Conta empresarial de Snapchat](https://business.snapchat.com/), unha [Conta publicitaria de Snapchat](https://ads.snapchat.com/) e as correspondentes credenciais de administrador.</span><span class="sxs-lookup"><span data-stu-id="917b6-106">You have a [Snapchat Business account](https://business.snapchat.com/), a [Snapchat Ads account](https://ads.snapchat.com/), and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="917b6-107">Ten [segmentos configurados](segments.md) na información do público.</span><span class="sxs-lookup"><span data-stu-id="917b6-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="917b6-108">Os perfís de clientes unificados nos segmentos exportados conteñen un campo que representa un enderezo de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="917b6-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="917b6-109">Limitacións coñecidas</span><span class="sxs-lookup"><span data-stu-id="917b6-109">Known limitations</span></span>

- <span data-ttu-id="917b6-110">A exportación a Snapchat está limitada a segmentos.</span><span class="sxs-lookup"><span data-stu-id="917b6-110">Exporting to Snapchat is limited to segments.</span></span>
- <span data-ttu-id="917b6-111">A exportación de segmentos de ata 1 millón de perfís a Snapchat pode tardar ata 15 minutos en finalizar.</span><span class="sxs-lookup"><span data-stu-id="917b6-111">Exporting up to 1 million profiles to Snapchat can take up to 15 minutes to complete.</span></span> 

## <a name="set-up-connection-to-snapchat"></a><span data-ttu-id="917b6-112">Configurar conexión a Snapchat</span><span class="sxs-lookup"><span data-stu-id="917b6-112">Set up connection to Snapchat</span></span>

1. <span data-ttu-id="917b6-113">Vaia a **Administrar** > **Conexións**.</span><span class="sxs-lookup"><span data-stu-id="917b6-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="917b6-114">Seleccione **Engadir conexión** e elixa **Snapchat** para configurar a conexión.</span><span class="sxs-lookup"><span data-stu-id="917b6-114">Select **Add connection** and choose **Snapchat** to configure the connection.</span></span>

1. <span data-ttu-id="917b6-115">Déalle á conexión un nome recoñecible no campo **Nome para mostrar**.</span><span class="sxs-lookup"><span data-stu-id="917b6-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="917b6-116">O nome e o tipo de conexión describen esta conexión.</span><span class="sxs-lookup"><span data-stu-id="917b6-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="917b6-117">Recomendamos escoller un nome que explique o propósito e o destino da conexión.</span><span class="sxs-lookup"><span data-stu-id="917b6-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="917b6-118">Escolla quen pode usar esta conexión.</span><span class="sxs-lookup"><span data-stu-id="917b6-118">Choose who can use this connection.</span></span> <span data-ttu-id="917b6-119">Se non realiza ningunha acción, o valor predeterminado será Administradores.</span><span class="sxs-lookup"><span data-stu-id="917b6-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="917b6-120">Para obter máis información, consulte [Permitir aos colaboradores usar unha conexión para as exportacións](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="917b6-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="917b6-121">Seleccione **Estou de acordo** para confirmar a **Privacidade e cumprimento dos datos**.</span><span class="sxs-lookup"><span data-stu-id="917b6-121">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="917b6-122">Seleccione **Conectar** para iniciar a conexión a Snapchat.</span><span class="sxs-lookup"><span data-stu-id="917b6-122">Select **Connect** to initialize the connection to Snapchat.</span></span>

1. <span data-ttu-id="917b6-123">Seleccione **Autenticarse con Snapchat** e proporcione as súas credenciais de administrador de Snapchat.</span><span class="sxs-lookup"><span data-stu-id="917b6-123">Select **Authenticate with Snapchat** and provide your admin credentials for Snapchat.</span></span> 

1. <span data-ttu-id="917b6-124">Seleccione **Autoengadirse como usuario de exportación** e proporcione as súas credenciais de Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="917b6-124">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="917b6-125">Seleccione **Gardar** para completar a conexión.</span><span class="sxs-lookup"><span data-stu-id="917b6-125">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="917b6-126">Configurar unha exportación</span><span class="sxs-lookup"><span data-stu-id="917b6-126">Configure an export</span></span>

<span data-ttu-id="917b6-127">Pode configurar esta exportación se ten acceso a unha conexión deste tipo.</span><span class="sxs-lookup"><span data-stu-id="917b6-127">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="917b6-128">Para obter máis información, consulte [Permisos necesarios para configurar unha exportación](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="917b6-128">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="917b6-129">Vaia a **Datos** > **Exportacións**.</span><span class="sxs-lookup"><span data-stu-id="917b6-129">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="917b6-130">Seleccione **Engadir destino** para crear unha nova exportación.</span><span class="sxs-lookup"><span data-stu-id="917b6-130">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="917b6-131">No campo **Conexión da exportación** escolla unha conexión da sección Snapchat.</span><span class="sxs-lookup"><span data-stu-id="917b6-131">In the **Connection for export** field, choose a connection from the Snapchat section.</span></span> <span data-ttu-id="917b6-132">Se non ve o nome desta sección, non hai conexións deste tipo dispoñibles para vostede.</span><span class="sxs-lookup"><span data-stu-id="917b6-132">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="917b6-133">Introduza o [**ID de audiencia de Snapchat**](https://businesshelp.snapchat.com/s/article/custom-audiences).</span><span class="sxs-lookup"><span data-stu-id="917b6-133">Enter the [**Snapchat Audience ID**](https://businesshelp.snapchat.com/s/article/custom-audiences).</span></span>

1. <span data-ttu-id="917b6-134">Na sección **Coincidencia de datos**, no campo **Correo electrónico**, seleccione o campo do seu perfil de cliente unificado que representa o enderezo de correo electrónico dun cliente.</span><span class="sxs-lookup"><span data-stu-id="917b6-134">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="917b6-135">É necesario exportar segmentos a Snapchat.</span><span class="sxs-lookup"><span data-stu-id="917b6-135">It's required to export segments to Snapchat.</span></span>

1. <span data-ttu-id="917b6-136">Seleccione os segmentos que desexa exportar.</span><span class="sxs-lookup"><span data-stu-id="917b6-136">Select the segments you want to export.</span></span> 

1. <span data-ttu-id="917b6-137">Seleccione **Gardar**.</span><span class="sxs-lookup"><span data-stu-id="917b6-137">Select **Save**.</span></span>

<span data-ttu-id="917b6-138">Ao gardar unha exportación non se executa a exportación inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="917b6-138">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="917b6-139">A exportación execútase con cada [actualización programada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="917b6-139">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="917b6-140">Tamén pode [exportar datos baixo demanda](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="917b6-140">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="917b6-141">Cumprimento e privacidade dos datos</span><span class="sxs-lookup"><span data-stu-id="917b6-141">Data privacy and compliance</span></span>

<span data-ttu-id="917b6-142">Cando habilita Dynamics 365 Customer Insights para transmitir datos a Snapchat, permite a transferencia de datos fóra do límite de cumprimento de Dynamics 365 Customer Insights, incluíndo datos potencialmente confidenciais como os datos persoais.</span><span class="sxs-lookup"><span data-stu-id="917b6-142">When you enable Dynamics 365 Customer Insights to transmit data to Snapchat, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="917b6-143">Microsoft transferirá estes datos segundo a súa instrución, pero vostede é responsable de asegurarse de que Snapchat cumpra as obrigas de privacidade ou seguridade que poida ter.</span><span class="sxs-lookup"><span data-stu-id="917b6-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Snapchat meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="917b6-144">Para obter máis información, consulte a [Declaración de privacidade de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="917b6-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="917b6-145">O administrador de Dynamics 365 Customer Insights pode eliminar este destino de exportación en calquera momento para interromper o uso desta funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="917b6-145">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
