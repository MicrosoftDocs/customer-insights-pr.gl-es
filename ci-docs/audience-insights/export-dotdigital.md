---
title: Exportar datos de Customer Insights a DotDigital
description: Aprenda a configurar a conexión a DotDigital.
ms.date: 11/14/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 51a28bdf0de34f0555d8ad7e3d13b2ef8911d417
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598015"
---
# <a name="connector-for-dotdigital-preview"></a><span data-ttu-id="73b5b-103">Conector para DotDigital (vista previa)</span><span class="sxs-lookup"><span data-stu-id="73b5b-103">Connector for DotDigital (preview)</span></span>

<span data-ttu-id="73b5b-104">Exporte segmentos de perfís de clientes unificados a axendas de enderezos de DotDigital e utilíceos para campañas, mercadotecnia por correo electrónico e para crear segmentos de clientes con DotDigital.</span><span class="sxs-lookup"><span data-stu-id="73b5b-104">Export segments of unified customer profiles to DotDigital address books and use them for campaigns, email marketing, and to build customer segments with DotDigital.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="73b5b-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="73b5b-105">Prerequisites</span></span>

-   <span data-ttu-id="73b5b-106">Ten unha [Conta de DotDigital](https://dotdigital.com/) e as correspondentes credenciais de administrador.</span><span class="sxs-lookup"><span data-stu-id="73b5b-106">You have a [DotDigital account](https://dotdigital.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="73b5b-107">Existen axendas de enderezos en DotDigital e os ID correspondentes.</span><span class="sxs-lookup"><span data-stu-id="73b5b-107">There are existing address books in DotDigital and the corresponding IDs.</span></span> <span data-ttu-id="73b5b-108">A identificación pódese atopar na URL cando selecciona e abre unha axenda de enderezos.</span><span class="sxs-lookup"><span data-stu-id="73b5b-108">The ID can be found in the URL when you select and open an address book.</span></span> <span data-ttu-id="73b5b-109">Para obter máis información, consulte [Axendas de enderezos de DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="73b5b-109">For more information, see [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>
-   <span data-ttu-id="73b5b-110">Ten [segmentos configurados](segments.md) na información do público.</span><span class="sxs-lookup"><span data-stu-id="73b5b-110">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="73b5b-111">Os perfís de clientes unificados nos segmentos exportados conteñen un campo que representa un enderezo de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="73b5b-111">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-dotdigital"></a><span data-ttu-id="73b5b-112">Conectarse a DotDigital</span><span class="sxs-lookup"><span data-stu-id="73b5b-112">Connect to DotDigital</span></span>

1. <span data-ttu-id="73b5b-113">Vaia a **Administrador** > **Exportar destinos**.</span><span class="sxs-lookup"><span data-stu-id="73b5b-113">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="73b5b-114">En **DotDigital**, seleccione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="73b5b-114">Under **DotDigital**, select **Set up**.</span></span>

1. <span data-ttu-id="73b5b-115">Déalle ao seu destino da exploración un nome recoñecible no campo **Nome para mostrar**.</span><span class="sxs-lookup"><span data-stu-id="73b5b-115">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/DotDigital_config.PNG" alt-text="Panel de configuración para a exportación a DotDigital.":::

1. <span data-ttu-id="73b5b-117">Escriba o seu **nome de usuario e contrasinal de DotDigital**.</span><span class="sxs-lookup"><span data-stu-id="73b5b-117">Enter your **DotDigital username and password**.</span></span>

1. <span data-ttu-id="73b5b-118">Introduza o seu **[ID da axenda de enderezos de DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span><span class="sxs-lookup"><span data-stu-id="73b5b-118">Enter your **[DotDigital address book ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span></span>

1. <span data-ttu-id="73b5b-119">Seleccione **Estou de acordo** para confirmar a **Privacidade e cumprimento dos datos**.</span><span class="sxs-lookup"><span data-stu-id="73b5b-119">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="73b5b-120">Seleccione **Conectar** para inicializar a conexión a DotDigital.</span><span class="sxs-lookup"><span data-stu-id="73b5b-120">Select **Connect** to initialize the connection to DotDigital.</span></span>

1. <span data-ttu-id="73b5b-121">Seleccione **Autoengadirse como usuario de exportación** e proporcione as súas credenciais de Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="73b5b-121">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="73b5b-122">Seleccione **Seguinte** para configurar a exportación.</span><span class="sxs-lookup"><span data-stu-id="73b5b-122">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="73b5b-123">Configurar o conector</span><span class="sxs-lookup"><span data-stu-id="73b5b-123">Configure the connector</span></span>

1. <span data-ttu-id="73b5b-124">Na sección **Coincidencia de datos**, no campo **Correo electrónico**, seleccione o campo do seu perfil de cliente unificado que representa o enderezo de correo electrónico dun cliente.</span><span class="sxs-lookup"><span data-stu-id="73b5b-124">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="73b5b-125">Repita os mesmos pasos para outros campos opcionais como **nome**, **apelidos**, **Nome completo**, **sexos** e **Código postal**.</span><span class="sxs-lookup"><span data-stu-id="73b5b-125">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Full name**, **Gender**, and **Post code**.</span></span>

1. <span data-ttu-id="73b5b-126">Seleccione os segmentos que desexa exportar.</span><span class="sxs-lookup"><span data-stu-id="73b5b-126">Select the segments you want to export.</span></span> <span data-ttu-id="73b5b-127">Pode exportar ata 1 millón de perfís de clientes en total a DotDigital.</span><span class="sxs-lookup"><span data-stu-id="73b5b-127">You can export up to 1 million customer profiles in total to DotDigital.</span></span>

1. <span data-ttu-id="73b5b-128">Seleccione **Gardar**.</span><span class="sxs-lookup"><span data-stu-id="73b5b-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="73b5b-129">Exportar os datos</span><span class="sxs-lookup"><span data-stu-id="73b5b-129">Export the data</span></span>

<span data-ttu-id="73b5b-130">Pode [exportar datos baixo demanda](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="73b5b-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="73b5b-131">A exportación tamén se executará con todas as [actualizacións programadas](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="73b5b-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="73b5b-132">En DotDigital, agora pode atopar os seus segmentos en [Axendas de enderezos de DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="73b5b-132">In DotDigital, you can now find your segments in [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="73b5b-133">Limitacións coñecidas</span><span class="sxs-lookup"><span data-stu-id="73b5b-133">Known limitations</span></span>

- <span data-ttu-id="73b5b-134">Ata 1 millón de perfís por exportación a DotDigital.</span><span class="sxs-lookup"><span data-stu-id="73b5b-134">Up to 1 million profiles per export to DotDigital.</span></span>
- <span data-ttu-id="73b5b-135">A exportación a DotDigital está limitada a segmentos.</span><span class="sxs-lookup"><span data-stu-id="73b5b-135">Exporting to DotDigital is limited to segments.</span></span>
- <span data-ttu-id="73b5b-136">A exportación de segmentos cun total de 1 millón de perfís pode levar ata 3 horas debido ás limitacións do provedor.</span><span class="sxs-lookup"><span data-stu-id="73b5b-136">Exporting segments with a total of 1 million profiles can take up to 3 hours because of limitations on the provider side.</span></span> 
- <span data-ttu-id="73b5b-137">O número de perfís que pode exportar a DotDigital depende e está limitado no seu contrato con DotDigital.</span><span class="sxs-lookup"><span data-stu-id="73b5b-137">The number of profiles that you can export to DotDigital is dependent and limited on your contract with DotDigital.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="73b5b-138">Cumprimento e privacidade dos datos</span><span class="sxs-lookup"><span data-stu-id="73b5b-138">Data privacy and compliance</span></span>

<span data-ttu-id="73b5b-139">Cando habilita Dynamics 365 Customer Insights para transmitir datos a DotDigital, permite a transferencia de datos fóra do límite de cumprimento de Dynamics 365 Customer Insights, incluíndo datos potencialmente confidenciais como os datos persoais.</span><span class="sxs-lookup"><span data-stu-id="73b5b-139">When you enable Dynamics 365 Customer Insights to transmit data to DotDigital, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="73b5b-140">Microsoft transferirá estes datos segundo a súa instrución, pero vostede é responsable de garantir que DotDigital cumpra as obrigas de privacidade ou seguridade que poida ter.</span><span class="sxs-lookup"><span data-stu-id="73b5b-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that DotDigital meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="73b5b-141">Para obter máis información, consulte a [Declaración de privacidade de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="73b5b-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="73b5b-142">O administrador de Dynamics 365 Customer Insights pode eliminar este destino de exportación en calquera momento para interromper o uso desta funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="73b5b-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]