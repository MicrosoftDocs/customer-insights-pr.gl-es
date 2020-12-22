---
title: Exportar datos de Customer Insights a Mailchimp
description: Aprenda a configurar a conexión a Mailchimp.
ms.date: 10/26/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: edff494f6edf26a8b641cb1d788a715389ddb346
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405699"
---
# <a name="connector-for-mailchimp-preview"></a><span data-ttu-id="14179-103">Conector para Mailchimp (vista previa)</span><span class="sxs-lookup"><span data-stu-id="14179-103">Connector for Mailchimp (preview)</span></span>

<span data-ttu-id="14179-104">Exporte segmentos de perfís de clientes unificados a Mailchimp para crear boletíns e campañas de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="14179-104">Export segments of unified customer profiles to Mailchimp to create newsletters and email campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="14179-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="14179-105">Prerequisites</span></span>

-   <span data-ttu-id="14179-106">Ten unha [Conta de Mailchimp](https://mailchimp.com/) e as correspondentes credenciais de administrador.</span><span class="sxs-lookup"><span data-stu-id="14179-106">You have a [Mailchimp account](https://mailchimp.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="14179-107">Existen públicos en Mailchimp e os ID correspondentes.</span><span class="sxs-lookup"><span data-stu-id="14179-107">There are existing audiences in Mailchimp and the corresponding IDs.</span></span> <span data-ttu-id="14179-108">Para obter máis información, consulte [públicos de Mailchimp](https://mailchimp.com/help/create-audience/).</span><span class="sxs-lookup"><span data-stu-id="14179-108">For more information, see [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>
-   <span data-ttu-id="14179-109">Ten [segmentos configurados](segments.md)</span><span class="sxs-lookup"><span data-stu-id="14179-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="14179-110">Os perfís de clientes unificados nos segmentos exportados conteñen un campo que representa un enderezo de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="14179-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-mailchimp"></a><span data-ttu-id="14179-111">Conectarse a MailChimp</span><span class="sxs-lookup"><span data-stu-id="14179-111">Connect to Mailchimp</span></span>

1. <span data-ttu-id="14179-112">Vaia a **Administrador** > **Exportar destinos**.</span><span class="sxs-lookup"><span data-stu-id="14179-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="14179-113">En **Mailchimp**, seleccione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="14179-113">Under **Mailchimp**, select **Set up**.</span></span>

1. <span data-ttu-id="14179-114">Déalle ao seu destino da exploración un nome recoñecible no campo **Nome para mostrar**.</span><span class="sxs-lookup"><span data-stu-id="14179-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="14179-115">Seleccione **Estou de acordo** para confirmar a **Privacidade e cumprimento dos datos**.</span><span class="sxs-lookup"><span data-stu-id="14179-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="14179-116">Introduza o seu **[ID de audiencia de Mailchimp](https://mailchimp.com/help/find-audience-id/)** e seleccione **Conectar** para inicializar a conexión a Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="14179-116">Enter your **[Mailchimp audience ID](https://mailchimp.com/help/find-audience-id/)** and select **Connect** to initialize the connection to Mailchimp.</span></span>

1. <span data-ttu-id="14179-117">Seleccione **Autenticarse con Mailchimp** e proporcione as súas credenciais de Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="14179-117">Select **Authenticate with Mailchimp** and provide your Mailchimp credentials.</span></span>

1. <span data-ttu-id="14179-118">Seleccione **Autoengadirse como usuario de exportación** e proporcione as súas credenciais de Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="14179-118">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-connect-mailchimp.png" alt-text="Captura de pantalla de exportación para a conexión de Mailchimp":::

1. <span data-ttu-id="14179-120">Seleccione **Seguinte** para configurar a exportación.</span><span class="sxs-lookup"><span data-stu-id="14179-120">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="14179-121">Configurar o conector</span><span class="sxs-lookup"><span data-stu-id="14179-121">Configure the connector</span></span>

1. <span data-ttu-id="14179-122">Na sección **Coincidencia de datos**, no campo **Correo electrónico**, seleccione o campo do seu perfil de cliente unificado que representa o enderezo de correo electrónico dun cliente.</span><span class="sxs-lookup"><span data-stu-id="14179-122">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="14179-123">Opcionalmente, pode exportar o **nome** e os **apelidos** como campos adicionais para crear correos electrónicos máis personalizados.</span><span class="sxs-lookup"><span data-stu-id="14179-123">Optionally, you can export **First name** and **Last name** as additional fields to create more personalized emails.</span></span> <span data-ttu-id="14179-124">Seleccione **Engadir atributo** para asignar estes campos.</span><span class="sxs-lookup"><span data-stu-id="14179-124">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="14179-125">Seleccione os segmentos que desexa exportar.</span><span class="sxs-lookup"><span data-stu-id="14179-125">Select the segments you want to export.</span></span> <span data-ttu-id="14179-126">Pode exportar ata 1 millón de perfís de clientes en total a Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="14179-126">You can export up to 1 million customer profiles in total to Mailchimp.</span></span>

   :::image type="content" source="media/export-segments-mailchimp.png" alt-text="Seleccionar campos e segmentos para exportar a Mailchimp":::

1. <span data-ttu-id="14179-128">Seleccione **Gardar**.</span><span class="sxs-lookup"><span data-stu-id="14179-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="14179-129">Exportar os datos</span><span class="sxs-lookup"><span data-stu-id="14179-129">Export the data</span></span>

<span data-ttu-id="14179-130">Pode [exportar datos baixo demanda](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="14179-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="14179-131">A exportación tamén se executará con todas as [actualizacións programadas](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="14179-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="14179-132">En Mailchimp, agora pode atopar os seus segmentos en [Públicos de Mailchimp](https://mailchimp.com/help/create-audience/).</span><span class="sxs-lookup"><span data-stu-id="14179-132">In Mailchimp, you can now find your segments under [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="14179-133">Limitacións coñecidas</span><span class="sxs-lookup"><span data-stu-id="14179-133">Known limitations</span></span>

- <span data-ttu-id="14179-134">Ata 1 millón de perfís por exportación a Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="14179-134">Up to 1 million profiles per export to Mailchimp.</span></span>
- <span data-ttu-id="14179-135">A exportación a Mailchimp está limitada a segmentos.</span><span class="sxs-lookup"><span data-stu-id="14179-135">Exporting to Mailchimp is limited to segments.</span></span>
- <span data-ttu-id="14179-136">A exportación de segmentos cun total de 1 millón de perfís pode levar ata tres horas debido ás limitacións do provedor.</span><span class="sxs-lookup"><span data-stu-id="14179-136">Exporting segments with a total of 1 million profiles can take up to three hours due to limitations on the provider side.</span></span> 
- <span data-ttu-id="14179-137">O número de perfís que pode exportar a Mailchimp depende e está limitado no seu contrato con Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="14179-137">The number of profiles that you can export to Mailchimp is dependent and limited on your contract with Mailchimp.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="14179-138">Cumprimento e privacidade dos datos</span><span class="sxs-lookup"><span data-stu-id="14179-138">Data privacy and compliance</span></span>

<span data-ttu-id="14179-139">Cando habilita Dynamics 365 Customer Insights para transmitir datos a Mailchimp, permite a transferencia de datos fóra do límite de cumprimento de Dynamics 365 Customer Insights, incluíndo datos potencialmente confidenciais como os datos persoais.</span><span class="sxs-lookup"><span data-stu-id="14179-139">When you enable Dynamics 365 Customer Insights to transmit data to Mailchimp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="14179-140">Microsoft transferirá estes datos segundo a súa instrución, pero vostede é responsable de garantir que Mailchimp cumpra as obrigas de privacidade ou seguridade que poida ter.</span><span class="sxs-lookup"><span data-stu-id="14179-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Mailchimp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="14179-141">Para obter máis información, consulte a [Declaración de privacidade de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="14179-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="14179-142">O administrador de Dynamics 365 Customer Insights pode eliminar este destino de exportación en calquera momento para interromper o uso desta funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="14179-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
