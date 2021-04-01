---
title: Exportar datos de Customer Insights ao Xestor de anuncios de Facebook
description: Aprenda a configurar a conexión ao Xestor de anuncios de Facebook.
ms.date: 06/05/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3e2b52fe743563e4bf61d870cbf1718e6c752a67
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596680"
---
# <a name="connector-for-facebook-ads-manager-preview"></a><span data-ttu-id="e6a9e-103">Conector para o Xestor de anuncios de Facebook (vista previa)</span><span class="sxs-lookup"><span data-stu-id="e6a9e-103">Connector for Facebook Ads Manager (preview)</span></span>

<span data-ttu-id="e6a9e-104">Exporte segmentos de perfís de clientes unificados ao Xestor de anuncios de Facebook para crear campañas en Facebook e Instagram.</span><span class="sxs-lookup"><span data-stu-id="e6a9e-104">Export segments of unified customer profiles to Facebook Ads Manager to create campaigns on Facebook and Instagram.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e6a9e-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="e6a9e-105">Prerequisites</span></span>

- <span data-ttu-id="e6a9e-106">Debe ter unha [**Conta de anuncios de Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) que inclúa unha [**Conta empresarial de Facebook**](https://business.facebook.com/).</span><span class="sxs-lookup"><span data-stu-id="e6a9e-106">You need to have a [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) which includes a [**Facebook Business Account**](https://business.facebook.com/).</span></span>
- <span data-ttu-id="e6a9e-107">Debe ser administrador na [**Conta de anuncios de Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span><span class="sxs-lookup"><span data-stu-id="e6a9e-107">You need to be an administrator on the [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span></span>

## <a name="connect-to-facebook-ads-manager"></a><span data-ttu-id="e6a9e-108">Conectarse ao Xestor de anuncios de Facebook</span><span class="sxs-lookup"><span data-stu-id="e6a9e-108">Connect to Facebook Ads Manager</span></span>

1. <span data-ttu-id="e6a9e-109">Vaia a **Administrador** > **Exportar destinos**.</span><span class="sxs-lookup"><span data-stu-id="e6a9e-109">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="e6a9e-110">En **Xestor de anuncios de Facebook** seleccione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="e6a9e-110">Under **Facebook Ads Manager**, select **Set up**.</span></span>

1. <span data-ttu-id="e6a9e-111">Déalle ao seu destino da exploración un nome recoñecible no campo **Nome para mostrar**.</span><span class="sxs-lookup"><span data-stu-id="e6a9e-111">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="e6a9e-112">Seleccione **Continuar con Facebook** para iniciar sesión na súa Conta de anuncios de Facebook.</span><span class="sxs-lookup"><span data-stu-id="e6a9e-112">Select **Continue with Facebook** to sign in to your Facebook Ad Account.</span></span>

1. <span data-ttu-id="e6a9e-113">Permitir o permiso de **xestión_anuncios** despois de autenticarse con Facebook.</span><span class="sxs-lookup"><span data-stu-id="e6a9e-113">Allow the **ads_management** permission after authenticating with Facebook.</span></span>

1. <span data-ttu-id="e6a9e-114">Seleccione a **conta publicitaria de Facebook** coa que desexa traballar.</span><span class="sxs-lookup"><span data-stu-id="e6a9e-114">Select the **Facebook Ads Account** that you want to work with.</span></span>

1. <span data-ttu-id="e6a9e-115">Seleccione un **Público personalizado existente** da lista despregable ou cree un **Novo público personalizado**.</span><span class="sxs-lookup"><span data-stu-id="e6a9e-115">Select an **Existing custom audience** from the drop-down list or create a **New custom audience**.</span></span> <span data-ttu-id="e6a9e-116">Para obter máis información, consulte [**Públicos no Xestor de anuncios de Facebook**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span><span class="sxs-lookup"><span data-stu-id="e6a9e-116">For more information, see [**Audiences in Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span></span>

1. <span data-ttu-id="e6a9e-117">Seleccione **Estou de acordo** para confirmar a **Privacidade e cumprimento dos datos**.</span><span class="sxs-lookup"><span data-stu-id="e6a9e-117">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="e6a9e-118">Seleccione **Seguinte** para configurar a exportación.</span><span class="sxs-lookup"><span data-stu-id="e6a9e-118">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="e6a9e-119">Configurar o conector</span><span class="sxs-lookup"><span data-stu-id="e6a9e-119">Configure the connector</span></span>

1. <span data-ttu-id="e6a9e-120">No **campo Escoller o identificador clave**, seleccione **Correo electrónico**, **Nome e enderezo** ou **Teléfono** para enviar ao Xestor de anuncios de Facebook.</span><span class="sxs-lookup"><span data-stu-id="e6a9e-120">In the **Choose your key identifier field**, select **Email**, **Name and address**, or **Phone** to send to Facebook Ads Manager.</span></span>

1. <span data-ttu-id="e6a9e-121">Asigne os atributos correspondentes desde a súa entidade de cliente unificada para o identificador de clave seleccionado.</span><span class="sxs-lookup"><span data-stu-id="e6a9e-121">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>
   > <span data-ttu-id="e6a9e-122">[CONSELLO] As mellores posibilidades de coincidencia danse se selecciona **Correo electrónico** como identificador clave.</span><span class="sxs-lookup"><span data-stu-id="e6a9e-122">[TIP] The best chances for a match occur if you select **Email** as key identifier.</span></span> <span data-ttu-id="e6a9e-123">Se engade identificadores adicionais pode mellorar a coincidencia.</span><span class="sxs-lookup"><span data-stu-id="e6a9e-123">Adding additional identifiers may improve the matching.</span></span>

1. <span data-ttu-id="e6a9e-124">Seleccione **Engadir atributo** para asignar atributos adicionais que enviar ao Xestor de anuncios de Facebook.</span><span class="sxs-lookup"><span data-stu-id="e6a9e-124">Select **Add attribute** to map additional attributes to send to Facebook Ads Manager.</span></span> <span data-ttu-id="e6a9e-125">Os atributos do Administrador de anuncios de Facebook asígnanse aos seguintes nomes amigables de usuario: **FN** = **Nome**, **LN** = **Apelidos**, **FI** = **Inicial nome**, **PHONE** = **Teléfono**, **GEN** = **Sexo**, **DOB** = **Data de nacemento**, **ST** = **Estado**, **CT** = **Cidade**, **ZIP** = **Código postal**, **COUNTRY** = **País/rexión**</span><span class="sxs-lookup"><span data-stu-id="e6a9e-125">Attributes from Facebook Ads Manager are mapping to the following user friendly names: **FN** = **First Name**, **LN** = **Last Name**, **FI** = **First Initial**, **PHONE** = **Phone**, **GEN** = **Gender**, **DOB** = **Date of birth**, **ST** = **State**, **CT** = **City**, **ZIP** = **Postal code / Zip code**, **COUNTRY** = **Country / Region**</span></span>

1. <span data-ttu-id="e6a9e-126">Seleccione os segmentos que desexa exportar.</span><span class="sxs-lookup"><span data-stu-id="e6a9e-126">Select the segments you want to export.</span></span>

1. <span data-ttu-id="e6a9e-127">Seleccione **Gardar**.</span><span class="sxs-lookup"><span data-stu-id="e6a9e-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="e6a9e-128">Exportar os datos</span><span class="sxs-lookup"><span data-stu-id="e6a9e-128">Export the data</span></span>

<span data-ttu-id="e6a9e-129">Pode [exportar datos baixo demanda](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="e6a9e-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="e6a9e-130">A exportación tamén se executará con todas as [actualizacións programadas](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="e6a9e-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="e6a9e-131">Limitacións coñecidas</span><span class="sxs-lookup"><span data-stu-id="e6a9e-131">Known limitations</span></span>

- <span data-ttu-id="e6a9e-132">Ata 10 millóns de perfís de clientes por exportación ao Xestor de anuncios de Facebook</span><span class="sxs-lookup"><span data-stu-id="e6a9e-132">Up to 10 million customer profile per export to Facebook Ads Manager</span></span> 
- <span data-ttu-id="e6a9e-133">A exportación ao Xestor de anuncios de Facebook está limitada a segmentos</span><span class="sxs-lookup"><span data-stu-id="e6a9e-133">Export to Facebook Ads Manager is limited to segments</span></span>
- <span data-ttu-id="e6a9e-134">A exportación de segmentos cun total de 10 millón de perfís pode tardar ata 90 minutos en finalizar</span><span class="sxs-lookup"><span data-stu-id="e6a9e-134">Exporting segments with a total of 10 million profiles can take up to 90 minutes to complete</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="e6a9e-135">Cumprimento e privacidade dos datos</span><span class="sxs-lookup"><span data-stu-id="e6a9e-135">Data privacy and compliance</span></span>

<span data-ttu-id="e6a9e-136">Cando habilita Dynamics 365 Customer Insights para transmitir datos ao xestor de anuncios de Facebook, permite a transferencia de datos fóra do límite de cumprimento de Dynamics 365 Customer Insights, incluíndo datos potencialmente confidenciais como os datos persoais.</span><span class="sxs-lookup"><span data-stu-id="e6a9e-136">When you enable Dynamics 365 Customer Insights to transmit data to Facebook Ads Manager, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="e6a9e-137">Microsoft transferirá estes datos segundo a súa instrución, pero vostede é responsable de garantir que Anuncios de Facebook cumpra as obrigas de privacidade ou seguridade que poida ter.</span><span class="sxs-lookup"><span data-stu-id="e6a9e-137">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Facebook Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="e6a9e-138">Para obter máis información, consulte a [Declaración de privacidade de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="e6a9e-138">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="e6a9e-139">O administrador de Dynamics 365 Customer Insights pode eliminar este destino de exportación en calquera momento para interromper o uso desta funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="e6a9e-139">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]