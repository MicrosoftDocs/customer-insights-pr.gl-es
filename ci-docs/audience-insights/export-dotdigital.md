---
title: Exportar datos de Customer Insights a DotDigital
description: Aprenda a configurar a conexión e exportar a DotDigital.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 235bcdfa4a7c4c1a382778bd4f66c1a9f5b7beb1
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759957"
---
# <a name="export-segment-lists-to-dotdigital-preview"></a><span data-ttu-id="a6156-103">Exportar listas de segmentos a DotDigital (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="a6156-103">Export segment lists to DotDigital (preview)</span></span>

<span data-ttu-id="a6156-104">Exporte segmentos de perfís de clientes unificados a axendas de enderezos de DotDigital e utilíceos para campañas, mercadotecnia por correo electrónico e para crear segmentos de clientes con DotDigital.</span><span class="sxs-lookup"><span data-stu-id="a6156-104">Export segments of unified customer profiles to DotDigital address books and use them for campaigns, email marketing, and to build customer segments with DotDigital.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="a6156-105">Requisitos previos para unha conexión</span><span class="sxs-lookup"><span data-stu-id="a6156-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="a6156-106">Ten unha [Conta de DotDigital](https://dotdigital.com/) e as correspondentes credenciais de administrador.</span><span class="sxs-lookup"><span data-stu-id="a6156-106">You have a [DotDigital account](https://dotdigital.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="a6156-107">Existen axendas de enderezos en DotDigital e os ID correspondentes.</span><span class="sxs-lookup"><span data-stu-id="a6156-107">There are existing address books in DotDigital and the corresponding IDs.</span></span> <span data-ttu-id="a6156-108">A identificación pódese atopar na URL cando selecciona e abre unha axenda de enderezos.</span><span class="sxs-lookup"><span data-stu-id="a6156-108">The ID can be found in the URL when you select and open an address book.</span></span> <span data-ttu-id="a6156-109">Para obter máis información, consulte [Axendas de enderezos de DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="a6156-109">For more information, see [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>
-   <span data-ttu-id="a6156-110">Ten [segmentos configurados](segments.md) na información do público.</span><span class="sxs-lookup"><span data-stu-id="a6156-110">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="a6156-111">Os perfís de clientes unificados nos segmentos exportados conteñen un campo que representa un enderezo de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="a6156-111">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="a6156-112">Limitacións coñecidas</span><span class="sxs-lookup"><span data-stu-id="a6156-112">Known limitations</span></span>

- <span data-ttu-id="a6156-113">Ata 1 millón de perfís por exportación a DotDigital.</span><span class="sxs-lookup"><span data-stu-id="a6156-113">Up to 1 million profiles per export to DotDigital.</span></span>
- <span data-ttu-id="a6156-114">A exportación a DotDigital está limitada a segmentos.</span><span class="sxs-lookup"><span data-stu-id="a6156-114">Exporting to DotDigital is limited to segments.</span></span>
- <span data-ttu-id="a6156-115">A exportación de segmentos cun total de 1 millón de perfís pode levar ata 3 horas debido ás limitacións do provedor.</span><span class="sxs-lookup"><span data-stu-id="a6156-115">Exporting segments with a total of 1 million profiles can take up to 3 hours because of limitations on the provider side.</span></span> 
- <span data-ttu-id="a6156-116">O número de perfís que pode exportar a DotDigital depende e está limitado no seu contrato con DotDigital.</span><span class="sxs-lookup"><span data-stu-id="a6156-116">The number of profiles that you can export to DotDigital is dependent and limited on your contract with DotDigital.</span></span>

## <a name="set-up-connection-to-dotdigital"></a><span data-ttu-id="a6156-117">Configurar conexión a DotDigital</span><span class="sxs-lookup"><span data-stu-id="a6156-117">Set up connection to DotDigital</span></span>

1. <span data-ttu-id="a6156-118">Vaia a **Administrar** > **Conexións**.</span><span class="sxs-lookup"><span data-stu-id="a6156-118">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="a6156-119">Seleccione **Engadir conexión** e elixa **DotDigital** para configurar a conexión.</span><span class="sxs-lookup"><span data-stu-id="a6156-119">Select **Add connection** and choose **DotDigital** to configure the connection.</span></span>

1. <span data-ttu-id="a6156-120">Déalle á conexión un nome recoñecible no campo **Nome para mostrar**.</span><span class="sxs-lookup"><span data-stu-id="a6156-120">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="a6156-121">O nome e o tipo de conexión describen esta conexión.</span><span class="sxs-lookup"><span data-stu-id="a6156-121">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="a6156-122">Recomendamos escoller un nome que explique o propósito e o destino da conexión.</span><span class="sxs-lookup"><span data-stu-id="a6156-122">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="a6156-123">Escolla quen pode usar esta conexión.</span><span class="sxs-lookup"><span data-stu-id="a6156-123">Choose who can use this connection.</span></span> <span data-ttu-id="a6156-124">Se non realiza ningunha acción, o valor predeterminado será Administradores.</span><span class="sxs-lookup"><span data-stu-id="a6156-124">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="a6156-125">Para obter máis información, consulte [Permitir aos colaboradores usar unha conexión para as exportacións](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="a6156-125">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="a6156-126">Escriba o seu **nome de usuario e contrasinal de DotDigital**.</span><span class="sxs-lookup"><span data-stu-id="a6156-126">Enter your **DotDigital username and password**.</span></span>

1. <span data-ttu-id="a6156-127">Introduza o seu **[ID da axenda de enderezos de DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span><span class="sxs-lookup"><span data-stu-id="a6156-127">Enter your **[DotDigital address book ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span></span>

1. <span data-ttu-id="a6156-128">Seleccione **Estou de acordo** para confirmar a **Privacidade e cumprimento dos datos**.</span><span class="sxs-lookup"><span data-stu-id="a6156-128">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="a6156-129">Seleccione **Conectar** para inicializar a conexión a DotDigital.</span><span class="sxs-lookup"><span data-stu-id="a6156-129">Select **Connect** to initialize the connection to DotDigital.</span></span>

1. <span data-ttu-id="a6156-130">Seleccione **Autoengadirse como usuario de exportación** e proporcione as súas credenciais de Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="a6156-130">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="a6156-131">Seleccione **Gardar** para completar a conexión.</span><span class="sxs-lookup"><span data-stu-id="a6156-131">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="a6156-132">Configurar unha exportación</span><span class="sxs-lookup"><span data-stu-id="a6156-132">Configure an export</span></span>

<span data-ttu-id="a6156-133">Pode configurar esta exportación se ten acceso a unha conexión deste tipo.</span><span class="sxs-lookup"><span data-stu-id="a6156-133">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="a6156-134">Para obter máis información, consulte [Permisos necesarios para configurar unha exportación](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="a6156-134">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="a6156-135">Vaia a **Datos** > **Exportacións**.</span><span class="sxs-lookup"><span data-stu-id="a6156-135">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="a6156-136">Seleccione **Engadir destino** para crear unha nova exportación.</span><span class="sxs-lookup"><span data-stu-id="a6156-136">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="a6156-137">No campo **Conexión da exportación** escolla unha conexión da sección DotDigital.</span><span class="sxs-lookup"><span data-stu-id="a6156-137">In the **Connection for export** field, choose a connection from the DotDigital section.</span></span> <span data-ttu-id="a6156-138">Se non ve o nome desta sección, non hai conexións deste tipo dispoñibles para vostede.</span><span class="sxs-lookup"><span data-stu-id="a6156-138">If you don't see this section name, there are no connections of this type available to you.</span></span>


1. <span data-ttu-id="a6156-139">Na sección **Coincidencia de datos**, no campo **Correo electrónico**, seleccione o campo do seu perfil de cliente unificado que representa o enderezo de correo electrónico dun cliente.</span><span class="sxs-lookup"><span data-stu-id="a6156-139">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="a6156-140">Repita os mesmos pasos para outros campos opcionais como **nome**, **apelidos**, **Nome completo**, **sexos** e **Código postal**.</span><span class="sxs-lookup"><span data-stu-id="a6156-140">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Full name**, **Gender**, and **Post code**.</span></span>

1. <span data-ttu-id="a6156-141">Seleccione os segmentos que desexa exportar.</span><span class="sxs-lookup"><span data-stu-id="a6156-141">Select the segments you want to export.</span></span> <span data-ttu-id="a6156-142">Pode exportar ata 1 millón de perfís de clientes en total a DotDigital.</span><span class="sxs-lookup"><span data-stu-id="a6156-142">You can export up to 1 million customer profiles in total to DotDigital.</span></span>

1. <span data-ttu-id="a6156-143">Seleccione **Gardar**.</span><span class="sxs-lookup"><span data-stu-id="a6156-143">Select **Save**.</span></span>

<span data-ttu-id="a6156-144">Ao gardar unha exportación non se executa a exportación inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="a6156-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="a6156-145">A exportación execútase con cada [actualización programada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="a6156-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="a6156-146">Tamén pode [exportar datos baixo demanda](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="a6156-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 
 
<span data-ttu-id="a6156-147">En DotDigital, agora pode atopar os seus segmentos en [Axendas de enderezos de DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="a6156-147">In DotDigital, you can now find your segments in [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="a6156-148">Cumprimento e privacidade dos datos</span><span class="sxs-lookup"><span data-stu-id="a6156-148">Data privacy and compliance</span></span>

<span data-ttu-id="a6156-149">Cando habilita Dynamics 365 Customer Insights para transmitir datos a DotDigital, permite a transferencia de datos fóra do límite de cumprimento de Dynamics 365 Customer Insights, incluíndo datos potencialmente confidenciais como os datos persoais.</span><span class="sxs-lookup"><span data-stu-id="a6156-149">When you enable Dynamics 365 Customer Insights to transmit data to DotDigital, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="a6156-150">Microsoft transferirá estes datos segundo a súa instrución, pero vostede é responsable de garantir que DotDigital cumpra as obrigas de privacidade ou seguridade que poida ter.</span><span class="sxs-lookup"><span data-stu-id="a6156-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that DotDigital meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="a6156-151">Para obter máis información, consulte a [Declaración de privacidade de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="a6156-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="a6156-152">O administrador de Dynamics 365 Customer Insights pode eliminar este destino de exportación en calquera momento para interromper o uso desta funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="a6156-152">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
