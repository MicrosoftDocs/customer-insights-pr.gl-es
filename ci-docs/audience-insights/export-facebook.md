---
title: Exportar datos de Customer Insights ao Xestor de anuncios de Facebook
description: Aprenda a configurar a conexión ao Xestor de anuncios de Facebook.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 8260e3b5e529f3d54678d9d6e11aebb2795e27fd
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643681"
---
# <a name="connector-for-facebook-ads-manager-preview"></a><span data-ttu-id="7dfc0-103">Conector para o Xestor de anuncios de Facebook (vista previa)</span><span class="sxs-lookup"><span data-stu-id="7dfc0-103">Connector for Facebook Ads Manager (preview)</span></span>

<span data-ttu-id="7dfc0-104">Exporte segmentos de perfís de clientes unificados ao Xestor de anuncios de Facebook para crear campañas en Facebook e Instagram.</span><span class="sxs-lookup"><span data-stu-id="7dfc0-104">Export segments of unified customer profiles to Facebook Ads Manager to create campaigns on Facebook and Instagram.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7dfc0-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="7dfc0-105">Prerequisites</span></span>

- <span data-ttu-id="7dfc0-106">Debe ter unha [**Conta de anuncios de Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) que inclúa unha [**Conta empresarial de Facebook**](https://business.facebook.com/).</span><span class="sxs-lookup"><span data-stu-id="7dfc0-106">You need to have a [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) which includes a [**Facebook Business Account**](https://business.facebook.com/).</span></span>
- <span data-ttu-id="7dfc0-107">Debe ser administrador na [**Conta de anuncios de Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span><span class="sxs-lookup"><span data-stu-id="7dfc0-107">You need to be an administrator on the [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span></span>

## <a name="connect-to-facebook-ads-manager"></a><span data-ttu-id="7dfc0-108">Conectarse ao Xestor de anuncios de Facebook</span><span class="sxs-lookup"><span data-stu-id="7dfc0-108">Connect to Facebook Ads Manager</span></span>

1. <span data-ttu-id="7dfc0-109">Vaia a **Administrador** > **Exportar destinos**.</span><span class="sxs-lookup"><span data-stu-id="7dfc0-109">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="7dfc0-110">En **Xestor de anuncios de Facebook** seleccione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="7dfc0-110">Under **Facebook Ads Manager**, select **Set up**.</span></span>

1. <span data-ttu-id="7dfc0-111">Déalle ao seu destino da exploración un nome recoñecible no campo **Nome para mostrar**.</span><span class="sxs-lookup"><span data-stu-id="7dfc0-111">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="7dfc0-112">Seleccione **Continuar con Facebook** para iniciar sesión na súa Conta de anuncios de Facebook.</span><span class="sxs-lookup"><span data-stu-id="7dfc0-112">Select **Continue with Facebook** to sign in to your Facebook Ad Account.</span></span>

1. <span data-ttu-id="7dfc0-113">Permitir o permiso de **xestión_anuncios** despois de autenticarse con Facebook.</span><span class="sxs-lookup"><span data-stu-id="7dfc0-113">Allow the **ads_management** permission after authenticating with Facebook.</span></span>

1. <span data-ttu-id="7dfc0-114">Seleccione a **conta publicitaria de Facebook** coa que desexa traballar.</span><span class="sxs-lookup"><span data-stu-id="7dfc0-114">Select the **Facebook Ads Account** that you want to work with.</span></span>

1. <span data-ttu-id="7dfc0-115">Seleccione un **Público personalizado existente** da lista despregable ou cree un **Novo público personalizado**.</span><span class="sxs-lookup"><span data-stu-id="7dfc0-115">Select an **Existing custom audience** from the drop-down list or create a **New custom audience**.</span></span> <span data-ttu-id="7dfc0-116">Para obter máis información, consulte [**Públicos no Xestor de anuncios de Facebook**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span><span class="sxs-lookup"><span data-stu-id="7dfc0-116">For more information, see [**Audiences in Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span></span>

1. <span data-ttu-id="7dfc0-117">Seleccione **Estou de acordo** para confirmar a **Privacidade e cumprimento dos datos**.</span><span class="sxs-lookup"><span data-stu-id="7dfc0-117">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="7dfc0-118">Seleccione **Seguinte** para configurar a exportación.</span><span class="sxs-lookup"><span data-stu-id="7dfc0-118">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="7dfc0-119">Configurar o conector</span><span class="sxs-lookup"><span data-stu-id="7dfc0-119">Configure the connector</span></span>

1. <span data-ttu-id="7dfc0-120">No **campo Escoller o identificador clave**, seleccione **Correo electrónico**, **Nome e enderezo** ou **Teléfono** para enviar ao Xestor de anuncios de Facebook.</span><span class="sxs-lookup"><span data-stu-id="7dfc0-120">In the **Choose your key identifier field**, select **Email**, **Name and address**, or **Phone** to send to Facebook Ads Manager.</span></span>

1. <span data-ttu-id="7dfc0-121">Asigne os atributos correspondentes desde a súa entidade de cliente unificada para o identificador de clave seleccionado.</span><span class="sxs-lookup"><span data-stu-id="7dfc0-121">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>
   > <span data-ttu-id="7dfc0-122">[CONSELLO] As mellores posibilidades de coincidencia danse se selecciona **Correo electrónico** como identificador clave.</span><span class="sxs-lookup"><span data-stu-id="7dfc0-122">[TIP] The best chances for a match occur if you select **Email** as key identifier.</span></span> <span data-ttu-id="7dfc0-123">Se engade identificadores adicionais pode mellorar a coincidencia.</span><span class="sxs-lookup"><span data-stu-id="7dfc0-123">Adding additional identifiers may improve the matching.</span></span>

1. <span data-ttu-id="7dfc0-124">Seleccione **Engadir atributo** para asignar atributos adicionais que enviar ao Xestor de anuncios de Facebook.</span><span class="sxs-lookup"><span data-stu-id="7dfc0-124">Select **Add attribute** to map additional attributes to send to Facebook Ads Manager.</span></span> <span data-ttu-id="7dfc0-125">Os atributos do Administrador de anuncios de Facebook asígnanse aos seguintes nomes amigables de usuario: **FN** = **Nome**, **LN** = **Apelidos**, **FI** = **Inicial nome**, **PHONE** = **Teléfono**, **GEN** = **Sexo**, **DOB** = **Data de nacemento**, **ST** = **Estado**, **CT** = **Cidade**, **ZIP** = **Código postal**, **COUNTRY** = **País/rexión**</span><span class="sxs-lookup"><span data-stu-id="7dfc0-125">Attributes from Facebook Ads Manager are mapping to the following user friendly names: **FN** = **First Name**, **LN** = **Last Name**, **FI** = **First Initial**, **PHONE** = **Phone**, **GEN** = **Gender**, **DOB** = **Date of birth**, **ST** = **State**, **CT** = **City**, **ZIP** = **Postal code / Zip code**, **COUNTRY** = **Country / Region**</span></span>

1. <span data-ttu-id="7dfc0-126">Seleccione os segmentos que desexa exportar.</span><span class="sxs-lookup"><span data-stu-id="7dfc0-126">Select the segments you want to export.</span></span>

1. <span data-ttu-id="7dfc0-127">Seleccione **Gardar**.</span><span class="sxs-lookup"><span data-stu-id="7dfc0-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="7dfc0-128">Exportar os datos</span><span class="sxs-lookup"><span data-stu-id="7dfc0-128">Export the data</span></span>

<span data-ttu-id="7dfc0-129">Pode [exportar datos baixo demanda](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="7dfc0-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="7dfc0-130">A exportación tamén se executará con todas as [actualizacións programadas](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="7dfc0-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="7dfc0-131">Cumprimento e privacidade dos datos</span><span class="sxs-lookup"><span data-stu-id="7dfc0-131">Data privacy and compliance</span></span>

<span data-ttu-id="7dfc0-132">Cando habilita Dynamics 365 Customer Insights para transmitir datos ao xestor de anuncios de Facebook, permite a transferencia de datos fóra do límite de cumprimento de Dynamics 365 Customer Insights, incluíndo datos potencialmente confidenciais como os datos persoais.</span><span class="sxs-lookup"><span data-stu-id="7dfc0-132">When you enable Dynamics 365 Customer Insights to transmit data to Facebook Ads Manager, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="7dfc0-133">Microsoft transferirá estes datos segundo a súa instrución, pero vostede é responsable de garantir que Anuncios de Facebook cumpra as obrigas de privacidade ou seguridade que poida ter.</span><span class="sxs-lookup"><span data-stu-id="7dfc0-133">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Facebook Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="7dfc0-134">Para obter máis información, consulte a [Declaración de privacidade de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="7dfc0-134">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="7dfc0-135">O administrador de Dynamics 365 Customer Insights pode eliminar este destino de exportación en calquera momento para interromper o uso desta funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="7dfc0-135">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
