---
title: Exportar datos de Customer Insights a Marketo
description: Aprenda a configurar a conexión a Marketo.
ms.date: 11/12/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: e0245f2d01aabc86f43532822c056965ff7ae67a
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267079"
---
# <a name="connector-for-marketo-preview"></a><span data-ttu-id="2e7ac-103">Conector para Marketo (vista previa)</span><span class="sxs-lookup"><span data-stu-id="2e7ac-103">Connector for Marketo (preview)</span></span>

<span data-ttu-id="2e7ac-104">Exporte os segmentos de perfís de clientes unificados para xerar campañas, proporcionar márketing por correo electrónico e usar grupos específicos de clientes con Marketo.</span><span class="sxs-lookup"><span data-stu-id="2e7ac-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Marketo.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2e7ac-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="2e7ac-105">Prerequisites</span></span>

-   <span data-ttu-id="2e7ac-106">Ten unha [Conta de Marketo](https://login.marketo.com/) e as correspondentes credenciais de administrador.</span><span class="sxs-lookup"><span data-stu-id="2e7ac-106">You have a [Marketo account](https://login.marketo.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="2e7ac-107">Existen listas en Marketo e os ID correspondentes.</span><span class="sxs-lookup"><span data-stu-id="2e7ac-107">There are existing lists in Marketo and the corresponding IDs.</span></span> <span data-ttu-id="2e7ac-108">Para obter máis información, consulte [Listas de Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="2e7ac-108">For more information, see [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>
-   <span data-ttu-id="2e7ac-109">Ten [segmentos configurados](segments.md).</span><span class="sxs-lookup"><span data-stu-id="2e7ac-109">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="2e7ac-110">Os perfís de clientes unificados nos segmentos exportados conteñen un campo que representa un enderezo de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="2e7ac-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-marketo"></a><span data-ttu-id="2e7ac-111">Conectar con Marketo</span><span class="sxs-lookup"><span data-stu-id="2e7ac-111">Connect to Marketo</span></span>

1. <span data-ttu-id="2e7ac-112">Vaia a **Administrador** > **Exportar destinos**.</span><span class="sxs-lookup"><span data-stu-id="2e7ac-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="2e7ac-113">En **Marketo**, seleccione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="2e7ac-113">Under **Marketo**, select **Set up**.</span></span>

1. <span data-ttu-id="2e7ac-114">Déalle ao seu destino da exploración un nome recoñecible no campo **Nome para mostrar**.</span><span class="sxs-lookup"><span data-stu-id="2e7ac-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="2e7ac-115">Introduza o seu **[ID de cliente de Marketo, segredo de cliente e nome do servidor do extremo de REST](https://developers.marketo.com/rest-api/authentication/)**.</span><span class="sxs-lookup"><span data-stu-id="2e7ac-115">Enter your **[Marketo client ID, Client secret and REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/)**.</span></span>

1. <span data-ttu-id="2e7ac-116">Introduza o seu **[ID de lista de Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span><span class="sxs-lookup"><span data-stu-id="2e7ac-116">Enter your **[Marketo list ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span></span> 

1. <span data-ttu-id="2e7ac-117">Seleccione **Estou de acordo** para confirmar a **Privacidade e cumprimento de datos** e seleccione **Conectar** para inicializar a conexión con Marketo.</span><span class="sxs-lookup"><span data-stu-id="2e7ac-117">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Marketo.</span></span>

1. <span data-ttu-id="2e7ac-118">Seleccione **Autoengadirse como usuario de exportación** e proporcione as súas credenciais de Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="2e7ac-118">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-connect-marketo.png" alt-text="Captura de pantalla de exportación para a conexión de Marketo":::

1. <span data-ttu-id="2e7ac-120">Seleccione **Seguinte** para configurar a exportación.</span><span class="sxs-lookup"><span data-stu-id="2e7ac-120">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="2e7ac-121">Configurar o conector</span><span class="sxs-lookup"><span data-stu-id="2e7ac-121">Configure the connector</span></span>

1. <span data-ttu-id="2e7ac-122">Na sección **Coincidencia de datos**, no campo **Correo electrónico**, seleccione o campo do seu perfil de cliente unificado que representa o enderezo de correo electrónico dun cliente.</span><span class="sxs-lookup"><span data-stu-id="2e7ac-122">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="2e7ac-123">Opcionalmente, pode exportar o **nome**, os **apelidos**, a **cidade**, o **esstado** e o **país/rexión** como campos adicionais para crear correos electrónicos máis personalizados.</span><span class="sxs-lookup"><span data-stu-id="2e7ac-123">Optionally, you can export **First name**, **Last name**, **City**, **State**, and **Country/Region**  as additional fields to create more personalized emails.</span></span> <span data-ttu-id="2e7ac-124">Seleccione **Engadir atributo** para asignar estes campos.</span><span class="sxs-lookup"><span data-stu-id="2e7ac-124">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="2e7ac-125">Seleccione os segmentos que desexa exportar.</span><span class="sxs-lookup"><span data-stu-id="2e7ac-125">Select the segments you want to export.</span></span> <span data-ttu-id="2e7ac-126">Pode exportar ata 1 millón de perfís de clientes en total a Marketo.</span><span class="sxs-lookup"><span data-stu-id="2e7ac-126">You can export up to 1 million customer profiles in total to Marketo.</span></span>

   :::image type="content" source="media/export-segment-marketo.png" alt-text="Seleccionar campos e segmentos para exportar a Marketo":::

1. <span data-ttu-id="2e7ac-128">Seleccione **Gardar**.</span><span class="sxs-lookup"><span data-stu-id="2e7ac-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="2e7ac-129">Exportar os datos</span><span class="sxs-lookup"><span data-stu-id="2e7ac-129">Export the data</span></span>

<span data-ttu-id="2e7ac-130">Pode [exportar datos baixo demanda](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="2e7ac-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="2e7ac-131">A exportación tamén se executará con todas as [actualizacións programadas](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="2e7ac-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="2e7ac-132">En Marketo, agora pode atopar os seus segmentos en [Listas de Marketo](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="2e7ac-132">In Marketo, you can now find your segments under [Marketo lists](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="2e7ac-133">Limitacións coñecidas</span><span class="sxs-lookup"><span data-stu-id="2e7ac-133">Known limitations</span></span>

- <span data-ttu-id="2e7ac-134">Ata 1 millón de perfís por exportación a Marketo.</span><span class="sxs-lookup"><span data-stu-id="2e7ac-134">Up to 1 million profiles per export to Marketo.</span></span>
- <span data-ttu-id="2e7ac-135">A exportación a Marketo está limitada a segmentos.</span><span class="sxs-lookup"><span data-stu-id="2e7ac-135">Exporting to Marketo is limited to segments.</span></span>
- <span data-ttu-id="2e7ac-136">A exportación de segmentos cun total de 1 millón de perfís pode levar ata 3 horas.</span><span class="sxs-lookup"><span data-stu-id="2e7ac-136">Exporting segments with a total of 1 million profiles can take up to 3 hours.</span></span> 
- <span data-ttu-id="2e7ac-137">O número de perfís que pode exportar a Marketo depende e está limitado no seu contrato con Marketo.</span><span class="sxs-lookup"><span data-stu-id="2e7ac-137">The number of profiles that you can export to Marketo is dependent and limited on your contract with Marketo.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="2e7ac-138">Cumprimento e privacidade dos datos</span><span class="sxs-lookup"><span data-stu-id="2e7ac-138">Data privacy and compliance</span></span>

<span data-ttu-id="2e7ac-139">Cando habilita Dynamics 365 Customer Insights para transmitir datos a Marketo, permite a transferencia de datos fóra do límite de cumprimento de Dynamics 365 Customer Insights, incluíndo datos potencialmente confidenciais como os datos persoais.</span><span class="sxs-lookup"><span data-stu-id="2e7ac-139">When you enable Dynamics 365 Customer Insights to transmit data to Marketo, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="2e7ac-140">Microsoft transferirá estes datos segundo a súa instrución, pero vostede é responsable de garantir que Marketo cumpra as obrigas de privacidade ou seguridade que poida ter.</span><span class="sxs-lookup"><span data-stu-id="2e7ac-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Marketo meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="2e7ac-141">Para obter máis información, consulte a [Declaración de privacidade de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="2e7ac-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="2e7ac-142">O administrador de Dynamics 365 Customer Insights pode eliminar este destino de exportación en calquera momento para interromper o uso desta funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="2e7ac-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]