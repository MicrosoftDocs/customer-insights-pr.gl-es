---
title: Exportar datos de Customer Insights ao Xestor de anuncios de Facebook
description: Aprenda a configurar a conexión e exportar ao Xestor de anuncios de Facebook.
ms.date: 04/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e20c7b7fd3989d7621cb7765f38b85c8ab4adfcb
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305108"
---
# <a name="export-segments-list-to-facebook-ads-manager-preview"></a><span data-ttu-id="323b5-103">Exportar lista de segmentos ao Xestor de anuncios de Facebook (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="323b5-103">Export segments list to Facebook Ads Manager (preview)</span></span>

<span data-ttu-id="323b5-104">Exporte segmentos de perfís de clientes unificados ao Xestor de anuncios de Facebook para crear campañas en Facebook e Instagram.</span><span class="sxs-lookup"><span data-stu-id="323b5-104">Export segments of unified customer profiles to Facebook Ads Manager to create campaigns on Facebook and Instagram.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="323b5-105">Requisitos previos para a conexión</span><span class="sxs-lookup"><span data-stu-id="323b5-105">Prerequisites for connection</span></span>

- <span data-ttu-id="323b5-106">Debe ter unha [**conta publicitaria de Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) que inclúa unha [**conta empresarial de Facebook**](https://business.facebook.com/).</span><span class="sxs-lookup"><span data-stu-id="323b5-106">You need to have a [**Facebook Ads Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) that includes a [**Facebook Business Account**](https://business.facebook.com/).</span></span>
- <span data-ttu-id="323b5-107">Debe ser administrador da [**Conta de anuncios de Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span><span class="sxs-lookup"><span data-stu-id="323b5-107">You need to be an administrator on the [**Facebook Ads Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="323b5-108">Limitacións coñecidas</span><span class="sxs-lookup"><span data-stu-id="323b5-108">Known limitations</span></span>

- <span data-ttu-id="323b5-109">Ata 10 millóns de perfís de clientes por exportación ao Xestor de anuncios de Facebook.</span><span class="sxs-lookup"><span data-stu-id="323b5-109">Up to 10 million customer profiles per export to Facebook Ads Manager.</span></span>
- <span data-ttu-id="323b5-110">A exportación ao Xestor de anuncios de Facebook está limitada a segmentos.</span><span class="sxs-lookup"><span data-stu-id="323b5-110">Export to Facebook Ads Manager is limited to segments.</span></span>
- <span data-ttu-id="323b5-111">Cree ou actualice audiencias personalizadas en Facebook de tipo *lista de clientes* só.</span><span class="sxs-lookup"><span data-stu-id="323b5-111">Create or update custom audiences in Facebook of type *customer list* only.</span></span>
- <span data-ttu-id="323b5-112">A exportación de segmentos cun total de 10 millón de perfís pode tardar ata 90 minutos en finalizar.</span><span class="sxs-lookup"><span data-stu-id="323b5-112">Exporting segments with a total of 10 million profiles can take up to 90 minutes to complete.</span></span>

## <a name="set-up-connection-to-facebook-ads-manager"></a><span data-ttu-id="323b5-113">Configurar conexión ao xestor de anuncios de Facebook</span><span class="sxs-lookup"><span data-stu-id="323b5-113">Set up connection to Facebook Ads Manager</span></span>

<span data-ttu-id="323b5-114">Antes de que os usuarios poidan crear unha exportación, un administrador debe configurar a conexión ao servizo e permitir aos colaboradores que utilicen a conexión.</span><span class="sxs-lookup"><span data-stu-id="323b5-114">Before users can create an export, an administrator must configure the connection to the service and allow contributors to use the connection.</span></span>

1. <span data-ttu-id="323b5-115">Vaia a **Administrar** > **Conexións**.</span><span class="sxs-lookup"><span data-stu-id="323b5-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="323b5-116">Seleccione **Engadir conexión** e elixa **Xestor de anuncios de Facebook** para configurar a conexión.</span><span class="sxs-lookup"><span data-stu-id="323b5-116">Select **Add connection** and choose **Facebook Ads Manager** to configure the connection.</span></span>

1. <span data-ttu-id="323b5-117">Déalle á conexión un nome recoñecible no campo **Nome para mostrar**.</span><span class="sxs-lookup"><span data-stu-id="323b5-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="323b5-118">O nome e o tipo de conexión describen esta conexión.</span><span class="sxs-lookup"><span data-stu-id="323b5-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="323b5-119">Recomendamos escoller un nome que explique o propósito e o destino da conexión.</span><span class="sxs-lookup"><span data-stu-id="323b5-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="323b5-120">Escolla quen pode usar esta conexión.</span><span class="sxs-lookup"><span data-stu-id="323b5-120">Choose who can use this connection.</span></span> <span data-ttu-id="323b5-121">Se non realiza ningunha acción, o valor predeterminado será Administradores.</span><span class="sxs-lookup"><span data-stu-id="323b5-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="323b5-122">Para obter máis información, consulte [Permitir aos colaboradores usar unha conexión para as exportacións](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="323b5-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="323b5-123">Autenticar con anuncios de Facebook:</span><span class="sxs-lookup"><span data-stu-id="323b5-123">Authenticate with Facebook Ads:</span></span> 

   1. <span data-ttu-id="323b5-124">Seleccione **Continuar con Facebook** para iniciar sesión na súa Conta de anuncios de Facebook.</span><span class="sxs-lookup"><span data-stu-id="323b5-124">Select **Continue with Facebook** to sign in to your Facebook Ads account.</span></span>

   1. <span data-ttu-id="323b5-125">Permitir o permiso de **xestión_anuncios** despois de autenticarse con Facebook.</span><span class="sxs-lookup"><span data-stu-id="323b5-125">Allow the **ads_management** permission after authenticating with Facebook.</span></span>

   1. <span data-ttu-id="323b5-126">Seleccione a **conta publicitaria de Facebook** coa que desexa traballar.</span><span class="sxs-lookup"><span data-stu-id="323b5-126">Select the **Facebook Ads Account** that you want to work with.</span></span>

   1. <span data-ttu-id="323b5-127">Seleccione un **Público personalizado existente** na lista despregable ou cree un **Novo público personalizado**.</span><span class="sxs-lookup"><span data-stu-id="323b5-127">Select an **Existing custom audience** from the dropdown list or create a **New custom audience**.</span></span> <span data-ttu-id="323b5-128">Para obter máis información, consulte [**Públicos no Xestor de anuncios de Facebook**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span><span class="sxs-lookup"><span data-stu-id="323b5-128">For more information, see [**Audiences in Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span></span>
      > [!NOTE]
      > <span data-ttu-id="323b5-129">Só pode crear ou actualizar públicos personalizados eb Facebook do tipo *lista de clientes* con esta exportación.</span><span class="sxs-lookup"><span data-stu-id="323b5-129">You can only create or update custom audiences on Facebook of the type *customer list* with this export.</span></span> <span data-ttu-id="323b5-130">Nalgúns casos, ve audiencias personalizadas de diferentes tipos na lista despregable.</span><span class="sxs-lookup"><span data-stu-id="323b5-130">In some cases, you see custom audiences of different types in the dropdown list.</span></span> <span data-ttu-id="323b5-131">Seleccionar un tipo diferente á *lista de clientes* producirá un fallo na exportación.</span><span class="sxs-lookup"><span data-stu-id="323b5-131">Selecting a different type than *customer list* will result in a failing export.</span></span> 

1. <span data-ttu-id="323b5-132">Revise a **Privacidade dos datos e cumprimento** e seleccione **Estou de acordo**.</span><span class="sxs-lookup"><span data-stu-id="323b5-132">Review the **Data privacy and compliance** and select **I agree**.</span></span>

1. <span data-ttu-id="323b5-133">Seleccione **Gardar** para completar a conexión.</span><span class="sxs-lookup"><span data-stu-id="323b5-133">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="323b5-134">Configurar unha exportación</span><span class="sxs-lookup"><span data-stu-id="323b5-134">Configure an export</span></span>

<span data-ttu-id="323b5-135">Pode configurar esta exportación se ten acceso a unha conexión deste tipo.</span><span class="sxs-lookup"><span data-stu-id="323b5-135">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="323b5-136">Para obter máis información, consulte [Permisos necesarios para configurar unha exportación](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="323b5-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="323b5-137">Vaia a **Datos** > **Exportacións**.</span><span class="sxs-lookup"><span data-stu-id="323b5-137">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="323b5-138">Seleccione **Engadir destino** para crear unha nova exportación.</span><span class="sxs-lookup"><span data-stu-id="323b5-138">To create a new export, select **Add destination**.</span></span> 

1. <span data-ttu-id="323b5-139">En **Conexión da exportación** escolla unha conexión da sección **Xestor de anuncios de Facebook**.</span><span class="sxs-lookup"><span data-stu-id="323b5-139">In **Connection for export** choose a connection from the **Facebook Ads Manager** section.</span></span> <span data-ttu-id="323b5-140">Se non ve o nome desta sección, non ten ningunha conexión deste tipo dispoñible.</span><span class="sxs-lookup"><span data-stu-id="323b5-140">If you don't see this section name, then no connections of this type are available to you.</span></span>

1. <span data-ttu-id="323b5-141">No **campo Escoller o identificador clave**, seleccione **Correo electrónico**, **Nome e enderezo** ou **Teléfono** para enviar ao Xestor de anuncios de Facebook.</span><span class="sxs-lookup"><span data-stu-id="323b5-141">In the **Choose your key identifier field**, select **Email**, **Name and address**, or **Phone** to send to Facebook Ads Manager.</span></span> 

1. <span data-ttu-id="323b5-142">Déalle á conexión un nome recoñecible no campo **Nome para mostrar**.</span><span class="sxs-lookup"><span data-stu-id="323b5-142">Give your connection a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="323b5-143">Asigne os atributos correspondentes desde a súa entidade de cliente unificada para o identificador de clave seleccionado.</span><span class="sxs-lookup"><span data-stu-id="323b5-143">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>
   > [!TIP]
   > <span data-ttu-id="323b5-144">As mellores posibilidades de coincidencia danse se selecciona **Correo electrónico** como identificador clave.</span><span class="sxs-lookup"><span data-stu-id="323b5-144">The best chances for a match occur if you select **Email** as key identifier.</span></span> <span data-ttu-id="323b5-145">Se engade identificadores adicionais pode mellorar a coincidencia.</span><span class="sxs-lookup"><span data-stu-id="323b5-145">Adding additional identifiers may improve the matching.</span></span>

1. <span data-ttu-id="323b5-146">Seleccione **Engadir atributo** para asignar máis atributos para envialos ao Xestor de anuncios de Facebook.</span><span class="sxs-lookup"><span data-stu-id="323b5-146">Select **Add attribute** to map more attributes to send to Facebook Ads Manager.</span></span> <span data-ttu-id="323b5-147">Os atributos do Administrador de anuncios de Facebook asígnanse aos seguintes nomes descritivos de usuario: **FN** = **Nome**, **LN** = **Apelidos**, **FI** = **Inicial nome**, **PHONE** = **Teléfono**, **GEN** = **Sexo**, **DOB** = **Data de nacemento**, **ST** = **Estado**, **CT** = **Cidade**, **ZIP** = **Código postal**, **COUNTRY** = **País/rexión**</span><span class="sxs-lookup"><span data-stu-id="323b5-147">Attributes from Facebook Ads Manager are mapping to the following user-friendly names: **FN** = **First Name**, **LN** = **Last Name**, **FI** = **First Initial**, **PHONE** = **Phone**, **GEN** = **Gender**, **DOB** = **Date of birth**, **ST** = **State**, **CT** = **City**, **ZIP** = **Postal code / ZIP Code**, **COUNTRY** = **Country / Region**</span></span>

1. <span data-ttu-id="323b5-148">Seleccione os segmentos que desexa exportar.</span><span class="sxs-lookup"><span data-stu-id="323b5-148">Select the segments you want to export.</span></span>

1. <span data-ttu-id="323b5-149">Seleccione **Gardar**.</span><span class="sxs-lookup"><span data-stu-id="323b5-149">Select **Save**.</span></span>

<span data-ttu-id="323b5-150">Ao gardar unha exportación non se executa a exportación inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="323b5-150">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="323b5-151">A exportación execútase con cada [actualización programada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="323b5-151">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> 

<span data-ttu-id="323b5-152">Tamén pode [exportar datos baixo demanda](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="323b5-152">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="323b5-153">Cumprimento e privacidade dos datos</span><span class="sxs-lookup"><span data-stu-id="323b5-153">Data privacy and compliance</span></span>

<span data-ttu-id="323b5-154">Cando habilita Dynamics 365 Customer Insights para transmitir datos ao xestor de anuncios de Facebook, permite a transferencia de datos fóra do límite de cumprimento de Dynamics 365 Customer Insights, incluíndo datos potencialmente confidenciais como os datos persoais.</span><span class="sxs-lookup"><span data-stu-id="323b5-154">When you enable Dynamics 365 Customer Insights to transmit data to Facebook Ads Manager, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="323b5-155">Microsoft transferirá estes datos segundo a súa instrución, pero vostede é responsable de garantir que Anuncios de Facebook cumpra as obrigas de privacidade ou seguridade que poida ter.</span><span class="sxs-lookup"><span data-stu-id="323b5-155">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Facebook Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="323b5-156">Para obter máis información, consulte a [Declaración de privacidade de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="323b5-156">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="323b5-157">O administrador de Dynamics 365 Customer Insights pode eliminar este destino de exportación en calquera momento para interromper o uso desta funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="323b5-157">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
