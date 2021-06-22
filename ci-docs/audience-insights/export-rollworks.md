---
title: Exportar datos de Customer Insights a RollWorks
description: Aprenda a configurar a conexión e exportar a RollWorks.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: dce5d51ca4587b4d7a0644cc701c1826854882b5
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124087"
---
# <a name="export-segments-to-rollworks-preview"></a><span data-ttu-id="ea651-103">Exportar segmentos a RollWorks (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="ea651-103">Export segments to RollWorks (preview)</span></span>

<span data-ttu-id="ea651-104">Exporte segmentos de perfís de clientes unificados a RollWorks e utilíceos para a publicidade.</span><span class="sxs-lookup"><span data-stu-id="ea651-104">Export segments of unified customer profiles to RollWorks and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="ea651-105">Requisitos previos para unha conexión</span><span class="sxs-lookup"><span data-stu-id="ea651-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="ea651-106">Ten unha [conta de RollWorks](https://www.rollworks.com/) e as correspondentes credenciais de administrador.</span><span class="sxs-lookup"><span data-stu-id="ea651-106">You have an [RollWorks account](https://www.rollworks.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="ea651-107">Ten [segmentos configurados](segments.md) na información do público.</span><span class="sxs-lookup"><span data-stu-id="ea651-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="ea651-108">Os perfís de clientes unificados nos segmentos exportados conteñen un campo que representa un enderezo de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="ea651-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="ea651-109">Limitacións coñecidas</span><span class="sxs-lookup"><span data-stu-id="ea651-109">Known limitations</span></span>

- <span data-ttu-id="ea651-110">Pode exportar ata 250.000 perfís por exportación a RollWorks.</span><span class="sxs-lookup"><span data-stu-id="ea651-110">You can export up to 250'000 profiles in per export to RollWorks.</span></span>
- <span data-ttu-id="ea651-111">Non pode exportar segmentos con menos de 100 perfís a RollWorks.</span><span class="sxs-lookup"><span data-stu-id="ea651-111">You can't export segments with fewer than 100 profiles to RollWorks.</span></span> 
- <span data-ttu-id="ea651-112">A exportación a RollWorks está limitada a segmentos.</span><span class="sxs-lookup"><span data-stu-id="ea651-112">Exporting to RollWorks is limited to segments.</span></span>
- <span data-ttu-id="ea651-113">A exportación de segmentos de ata 250.000 perfís a RollWorks pode tardar ata 10 minutos en finalizar.</span><span class="sxs-lookup"><span data-stu-id="ea651-113">Exporting up to 250'000 profiles to RollWorks can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="ea651-114">O número de perfís que pode exportar a RollWorks depende e está limitado ao seu contrato con RollWorks.</span><span class="sxs-lookup"><span data-stu-id="ea651-114">The number of profiles that you can export to RollWorks is dependent and limited on your contract with RollWorks.</span></span>

## <a name="set-up-connection-to-rollworks"></a><span data-ttu-id="ea651-115">Configurar conexión a RollWorks</span><span class="sxs-lookup"><span data-stu-id="ea651-115">Set up connection to RollWorks</span></span>

1. <span data-ttu-id="ea651-116">Vaia a **Administrar** > **Conexións**.</span><span class="sxs-lookup"><span data-stu-id="ea651-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="ea651-117">Seleccione **Engadir conexión** e elixa **RollWorks** para configurar a conexión.</span><span class="sxs-lookup"><span data-stu-id="ea651-117">Select **Add connection** and choose **RollWorks** to configure the connection.</span></span>

1. <span data-ttu-id="ea651-118">Déalle á conexión un nome recoñecible no campo **Nome para mostrar**.</span><span class="sxs-lookup"><span data-stu-id="ea651-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="ea651-119">O nome e o tipo de conexión describen esta conexión.</span><span class="sxs-lookup"><span data-stu-id="ea651-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="ea651-120">Recomendamos escoller un nome que explique o propósito e o destino da conexión.</span><span class="sxs-lookup"><span data-stu-id="ea651-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="ea651-121">Escolla quen pode usar esta conexión.</span><span class="sxs-lookup"><span data-stu-id="ea651-121">Choose who can use this connection.</span></span> <span data-ttu-id="ea651-122">Se non realiza ningunha acción, o valor predeterminado será Administradores.</span><span class="sxs-lookup"><span data-stu-id="ea651-122">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="ea651-123">Para obter máis información, consulte [Permitir aos colaboradores usar unha conexión para as exportacións](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="ea651-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="ea651-124">Seleccione **Estou de acordo** para confirmar a **Privacidade e cumprimento dos datos**.</span><span class="sxs-lookup"><span data-stu-id="ea651-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="ea651-125">Seleccione **Conectar** para iniciar a conexión a RollWorks.</span><span class="sxs-lookup"><span data-stu-id="ea651-125">Select **Connect** to initialize the connection to RollWorks.</span></span>

1. <span data-ttu-id="ea651-126">Seleccione **Autenticarse con RollWorks** e proporcione as súas credenciais de administrador de RollWorks.</span><span class="sxs-lookup"><span data-stu-id="ea651-126">Select **Authenticate with RollWorks** and provide your admin credentials for RollWorks.</span></span>

1. <span data-ttu-id="ea651-127">Seleccione **Autoengadirse como usuario de exportación** e proporcione as súas credenciais de Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="ea651-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="ea651-128">Seleccione **Gardar** para completar a conexión.</span><span class="sxs-lookup"><span data-stu-id="ea651-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="ea651-129">Configurar unha exportación</span><span class="sxs-lookup"><span data-stu-id="ea651-129">Configure an export</span></span>

<span data-ttu-id="ea651-130">Pode configurar esta exportación se ten acceso a unha conexión deste tipo.</span><span class="sxs-lookup"><span data-stu-id="ea651-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="ea651-131">Para obter máis información, consulte [Permisos necesarios para configurar unha exportación](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="ea651-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="ea651-132">Vaia a **Datos** > **Exportacións**.</span><span class="sxs-lookup"><span data-stu-id="ea651-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="ea651-133">Seleccione **Engadir destino** para crear unha nova exportación.</span><span class="sxs-lookup"><span data-stu-id="ea651-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="ea651-134">No campo **Conexión da exportación** escolla unha conexión da sección RollWorks.</span><span class="sxs-lookup"><span data-stu-id="ea651-134">In the **Connection for export** field, choose a connection from the RollWorks section.</span></span> <span data-ttu-id="ea651-135">Se non ve o nome desta sección, non hai conexións deste tipo dispoñibles para vostede.</span><span class="sxs-lookup"><span data-stu-id="ea651-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="ea651-136">Introduza o seu **ID de anunciante de RollWorks** [Publicidade de RollWorks](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span><span class="sxs-lookup"><span data-stu-id="ea651-136">Enter your **RollWorks Advertiser ID** [RollWorks Advertisable](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span></span>

3. <span data-ttu-id="ea651-137">Na sección **Coincidencia de datos**, no campo **Correo electrónico**, seleccione o campo do seu perfil de cliente unificado que representa o enderezo de correo electrónico dun cliente.</span><span class="sxs-lookup"><span data-stu-id="ea651-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="ea651-138">É necesario exportar segmentos a RollWorks.</span><span class="sxs-lookup"><span data-stu-id="ea651-138">It's required to export segments to RollWorks.</span></span>

1. <span data-ttu-id="ea651-139">Seleccione os segmentos que desexa exportar.</span><span class="sxs-lookup"><span data-stu-id="ea651-139">Select the segments you want to export.</span></span> <span data-ttu-id="ea651-140">Seleccione un segmento cun mínimo de 100 membros.</span><span class="sxs-lookup"><span data-stu-id="ea651-140">Select a segment with a least 100 members.</span></span> <span data-ttu-id="ea651-141">Non pode exportar segmentos máis pequenos.</span><span class="sxs-lookup"><span data-stu-id="ea651-141">You can't export smaller segments.</span></span> <span data-ttu-id="ea651-142">Ademais, o tamaño máximo dun segmento para exportar é de 250.000 membros por exportación.</span><span class="sxs-lookup"><span data-stu-id="ea651-142">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="ea651-143">Seleccione **Gardar**.</span><span class="sxs-lookup"><span data-stu-id="ea651-143">Select **Save**.</span></span>

<span data-ttu-id="ea651-144">Ao gardar unha exportación non se executa a exportación inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="ea651-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="ea651-145">A exportación execútase con cada [actualización programada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="ea651-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="ea651-146">Tamén pode [exportar datos baixo demanda](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="ea651-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="ea651-147">Cumprimento e privacidade dos datos</span><span class="sxs-lookup"><span data-stu-id="ea651-147">Data privacy and compliance</span></span>

<span data-ttu-id="ea651-148">Cando habilita Dynamics 365 Customer Insights para transmitir datos a RollWorks, permite a transferencia de datos fóra do límite de cumprimento de Dynamics 365 Customer Insights, incluíndo datos potencialmente confidenciais como os datos persoais.</span><span class="sxs-lookup"><span data-stu-id="ea651-148">When you enable Dynamics 365 Customer Insights to transmit data to RollWorks, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="ea651-149">Microsoft transferirá estes datos segundo a súa instrución, pero vostede é responsable de asegurarse de que RollWorks cumpra as obrigas de privacidade ou seguridade que poida ter.</span><span class="sxs-lookup"><span data-stu-id="ea651-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that RollWorks meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="ea651-150">Para obter máis información, consulte a [Declaración de privacidade de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="ea651-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="ea651-151">O administrador de Dynamics 365 Customer Insights pode eliminar este destino de exportación en calquera momento para interromper o uso desta funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="ea651-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
