---
title: Exportar datos de Customer Insights a SendGrid
description: Aprenda a configurar a conexión a SendGrid.
ms.date: 12/08/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: f16d69deb2a0b48270ed04f9b72f03056f20b619
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268730"
---
# <a name="connector-for-sendgrid-preview"></a><span data-ttu-id="799dc-103">Conector para SendGrid (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="799dc-103">Connector for SendGrid (preview)</span></span>

<span data-ttu-id="799dc-104">Exporte segmentos de perfís de clientes unificados a listas de contactos de SendGrid e utilíceos para campañas e mercadotecnia por correo electrónico en SendGrid.</span><span class="sxs-lookup"><span data-stu-id="799dc-104">Export segments of unified customer profiles to SendGrid contact lists and use them for campaigns and email marketing in SendGrid.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="799dc-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="799dc-105">Prerequisites</span></span>

-   <span data-ttu-id="799dc-106">Ten unha [Conta de SendGrid](https://sendgrid.com/) e as correspondentes credenciais de administrador.</span><span class="sxs-lookup"><span data-stu-id="799dc-106">You have a [SendGrid account](https://sendgrid.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="799dc-107">Existen listas de contacto en SendGrid e os ID correspondentes.</span><span class="sxs-lookup"><span data-stu-id="799dc-107">There are existing contact lists in SendGrid and the corresponding IDs.</span></span> <span data-ttu-id="799dc-108">Para obter máis información, consulte [SendGrid: xestionar contactos](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span><span class="sxs-lookup"><span data-stu-id="799dc-108">For more information, see [SendGrid - Manage contacts](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span></span>
-   <span data-ttu-id="799dc-109">Ten [segmentos configurados](segments.md) na información do público.</span><span class="sxs-lookup"><span data-stu-id="799dc-109">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="799dc-110">Os perfís de clientes unificados nos segmentos exportados conteñen un campo que representa un enderezo de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="799dc-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-sendgrid"></a><span data-ttu-id="799dc-111">Conectar con SendGrid</span><span class="sxs-lookup"><span data-stu-id="799dc-111">Connect to SendGrid</span></span>

1. <span data-ttu-id="799dc-112">Vaia a **Administrador** > **Exportar destinos**.</span><span class="sxs-lookup"><span data-stu-id="799dc-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="799dc-113">En **SendGrid**, seleccione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="799dc-113">Under **SendGrid**, select **Set up**.</span></span>

1. <span data-ttu-id="799dc-114">Déalle ao seu destino da exploración un nome recoñecible no campo **Nome para mostrar**.</span><span class="sxs-lookup"><span data-stu-id="799dc-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/export-sendgrid.PNG" alt-text="Panel de configuración de exportación de SendGrid.":::

1. <span data-ttu-id="799dc-116">Introduza a súa **Clave da API de SendGrid** [Clave da API de SendGrid](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span><span class="sxs-lookup"><span data-stu-id="799dc-116">Enter your **SendGrid API key** [SendGrid API key](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span></span>

1. <span data-ttu-id="799dc-117">Introduza o seu **[ID de lista de SendGrid](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span><span class="sxs-lookup"><span data-stu-id="799dc-117">Enter your **[SendGrid list ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span></span>

1. <span data-ttu-id="799dc-118">Seleccione **Estou de acordo** para confirmar a **Privacidade e cumprimento dos datos**.</span><span class="sxs-lookup"><span data-stu-id="799dc-118">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="799dc-119">Seleccione **Conectar** para inicializar a conexión a SendGrid.</span><span class="sxs-lookup"><span data-stu-id="799dc-119">Select **Connect** to initialize the connection to SendGrid.</span></span>

1. <span data-ttu-id="799dc-120">Seleccione **Autoengadirse como usuario de exportación** e proporcione as súas credenciais de Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="799dc-120">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="799dc-121">Seleccione **Seguinte** para configurar a exportación.</span><span class="sxs-lookup"><span data-stu-id="799dc-121">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="799dc-122">Configurar o conector</span><span class="sxs-lookup"><span data-stu-id="799dc-122">Configure the connector</span></span>

1. <span data-ttu-id="799dc-123">Na sección **Coincidencia de datos**, no campo **Correo electrónico**, seleccione o campo do seu perfil de cliente unificado que representa o enderezo de correo electrónico dun cliente.</span><span class="sxs-lookup"><span data-stu-id="799dc-123">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="799dc-124">Repita os mesmos pasos para outros campos opcionais como **nome**, **apelidos**, **país/rexión**, **estado**, **cidade** e **código postal**.</span><span class="sxs-lookup"><span data-stu-id="799dc-124">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Country/Region**, **State**, **City**, and **Post code**.</span></span>

1. <span data-ttu-id="799dc-125">Seleccione os segmentos que desexa exportar.</span><span class="sxs-lookup"><span data-stu-id="799dc-125">Select the segments you want to export.</span></span> <span data-ttu-id="799dc-126">Nós fortemente **recomendamos non exportar máis de 100.000 perfís de clientes en total** a SendGrid.</span><span class="sxs-lookup"><span data-stu-id="799dc-126">We strongly **recommend to not export more than 100'000 customer profiles in total** to SendGrid.</span></span> 

1. <span data-ttu-id="799dc-127">Seleccione **Gardar**.</span><span class="sxs-lookup"><span data-stu-id="799dc-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="799dc-128">Exportar os datos</span><span class="sxs-lookup"><span data-stu-id="799dc-128">Export the data</span></span>

<span data-ttu-id="799dc-129">Pode [exportar datos baixo demanda](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="799dc-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="799dc-130">A exportación tamén se executará con todas as [actualizacións programadas](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="799dc-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="799dc-131">Limitacións coñecidas</span><span class="sxs-lookup"><span data-stu-id="799dc-131">Known limitations</span></span>

- <span data-ttu-id="799dc-132">Ata 100.000 perfís en total en SendGrid.</span><span class="sxs-lookup"><span data-stu-id="799dc-132">Up to 100'000 profiles in total to SendGrid.</span></span>
- <span data-ttu-id="799dc-133">A exportación a SendGrid está limitada a segmentos.</span><span class="sxs-lookup"><span data-stu-id="799dc-133">Exporting to SendGrid is limited to segments.</span></span>
- <span data-ttu-id="799dc-134">Exportar ata 100.000 perfís a SendGrid pode tardar unhas horas en completarse.</span><span class="sxs-lookup"><span data-stu-id="799dc-134">Exporting up to 100'000 profiles to SendGrid can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="799dc-135">O número de perfís que pode exportar a SendGrid depende e está limitado no seu contrato con SendGrid.</span><span class="sxs-lookup"><span data-stu-id="799dc-135">The number of profiles that you can export to SendGrid is dependent and limited on your contract with SendGrid.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="799dc-136">Cumprimento e privacidade dos datos</span><span class="sxs-lookup"><span data-stu-id="799dc-136">Data privacy and compliance</span></span>

<span data-ttu-id="799dc-137">Cando habilita Dynamics 365 Customer Insights para transmitir datos a SendGrid, permite a transferencia de datos fóra do límite de cumprimento de Dynamics 365 Customer Insights, incluíndo datos potencialmente confidenciais como os datos persoais.</span><span class="sxs-lookup"><span data-stu-id="799dc-137">When you enable Dynamics 365 Customer Insights to transmit data to SendGrid, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="799dc-138">Microsoft transferirá estes datos segundo a súa instrución, pero vostede é responsable de garantir que SendGrid cumpra as obrigas de privacidade ou seguridade que poida ter.</span><span class="sxs-lookup"><span data-stu-id="799dc-138">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that SendGrid meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="799dc-139">Para obter máis información, consulte a [Declaración de privacidade de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="799dc-139">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="799dc-140">O administrador de Dynamics 365 Customer Insights pode eliminar este destino de exportación en calquera momento para interromper o uso desta funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="799dc-140">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]