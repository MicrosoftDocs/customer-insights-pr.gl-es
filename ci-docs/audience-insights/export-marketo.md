---
title: Exportar datos de Customer Insights a Marketo
description: Aprenda a configurar a conexión e exportar a Marketo.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 01290d5fae7af1737b73373d75e334ae1ed67d37
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759819"
---
# <a name="export-segments-to-marketo-preview"></a><span data-ttu-id="a561a-103">Exportar segmentos a Marketo (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="a561a-103">Export segments to Marketo (preview)</span></span>

<span data-ttu-id="a561a-104">Exporte os segmentos de perfís de clientes unificados para xerar campañas, proporcionar márketing por correo electrónico e usar grupos específicos de clientes con Marketo.</span><span class="sxs-lookup"><span data-stu-id="a561a-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Marketo.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="a561a-105">Requisitos previos para a conexión</span><span class="sxs-lookup"><span data-stu-id="a561a-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="a561a-106">Ten unha [Conta de Marketo](https://login.marketo.com/) e as correspondentes credenciais de administrador.</span><span class="sxs-lookup"><span data-stu-id="a561a-106">You have a [Marketo account](https://login.marketo.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="a561a-107">Existen listas en Marketo e os ID correspondentes.</span><span class="sxs-lookup"><span data-stu-id="a561a-107">There are existing lists in Marketo and the corresponding IDs.</span></span> <span data-ttu-id="a561a-108">Para obter máis información, consulte [Listas de Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="a561a-108">For more information, see [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>
-   <span data-ttu-id="a561a-109">Ten [segmentos configurados](segments.md).</span><span class="sxs-lookup"><span data-stu-id="a561a-109">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="a561a-110">Os perfís de clientes unificados nos segmentos exportados conteñen un campo que representa un enderezo de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="a561a-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="a561a-111">Limitacións coñecidas</span><span class="sxs-lookup"><span data-stu-id="a561a-111">Known limitations</span></span>

- <span data-ttu-id="a561a-112">Ata 1 millón de perfís por exportación a Marketo.</span><span class="sxs-lookup"><span data-stu-id="a561a-112">Up to 1 million profiles per export to Marketo.</span></span>
- <span data-ttu-id="a561a-113">A exportación a Marketo está limitada a segmentos.</span><span class="sxs-lookup"><span data-stu-id="a561a-113">Exporting to Marketo is limited to segments.</span></span>
- <span data-ttu-id="a561a-114">A exportación de segmentos cun total de 1 millón de perfís pode levar ata 3 horas.</span><span class="sxs-lookup"><span data-stu-id="a561a-114">Exporting segments with a total of 1 million profiles can take up to 3 hours.</span></span> 
- <span data-ttu-id="a561a-115">O número de perfís que pode exportar a Marketo depende e está limitado no seu contrato con Marketo.</span><span class="sxs-lookup"><span data-stu-id="a561a-115">The number of profiles that you can export to Marketo is dependent and limited on your contract with Marketo.</span></span>

## <a name="set-up-connection-to-marketo"></a><span data-ttu-id="a561a-116">Configurar conexión a Marketo</span><span class="sxs-lookup"><span data-stu-id="a561a-116">Set up connection to Marketo</span></span>

1. <span data-ttu-id="a561a-117">Vaia a **Administrar** > **Conexións**.</span><span class="sxs-lookup"><span data-stu-id="a561a-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="a561a-118">Seleccione **Engadir conexión** e elixa **Marketo** para configurar a conexión.</span><span class="sxs-lookup"><span data-stu-id="a561a-118">Select **Add connection** and choose **Marketo** to configure the connection.</span></span>

1. <span data-ttu-id="a561a-119">Déalle á conexión un nome recoñecible no campo **Nome para mostrar**.</span><span class="sxs-lookup"><span data-stu-id="a561a-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="a561a-120">O nome e o tipo de conexión describen esta conexión.</span><span class="sxs-lookup"><span data-stu-id="a561a-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="a561a-121">Recomendamos escoller un nome que explique o propósito e o destino da conexión.</span><span class="sxs-lookup"><span data-stu-id="a561a-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="a561a-122">Escolla quen pode usar esta conexión.</span><span class="sxs-lookup"><span data-stu-id="a561a-122">Choose who can use this connection.</span></span> <span data-ttu-id="a561a-123">Se non realiza ningunha acción, o valor predeterminado será Administradores.</span><span class="sxs-lookup"><span data-stu-id="a561a-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="a561a-124">Para obter máis información, consulte [Permitir aos colaboradores usar unha conexión para as exportacións](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="a561a-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="a561a-125">Introduza o seu **[ID de cliente de Marketo, segredo de cliente e nome do servidor do extremo de REST](https://developers.marketo.com/rest-api/authentication/)**.</span><span class="sxs-lookup"><span data-stu-id="a561a-125">Enter your **[Marketo client ID, Client secret, and REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/)**.</span></span>

1. <span data-ttu-id="a561a-126">Seleccione **Estou de acordo** para confirmar a **Privacidade e cumprimento de datos** e seleccione **Conectar** para inicializar a conexión con Marketo.</span><span class="sxs-lookup"><span data-stu-id="a561a-126">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Marketo.</span></span>

1. <span data-ttu-id="a561a-127">Seleccione **Autoengadirse como usuario de exportación** e proporcione as súas credenciais de Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="a561a-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="a561a-128">Seleccione **Gardar** para completar a conexión.</span><span class="sxs-lookup"><span data-stu-id="a561a-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="a561a-129">Configurar unha exportación</span><span class="sxs-lookup"><span data-stu-id="a561a-129">Configure an export</span></span>

<span data-ttu-id="a561a-130">Pode configurar esta exportación se ten acceso a unha conexión deste tipo.</span><span class="sxs-lookup"><span data-stu-id="a561a-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="a561a-131">Para obter máis información, consulte [Permisos necesarios para configurar unha exportación](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="a561a-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="a561a-132">Vaia a **Datos** > **Exportacións**.</span><span class="sxs-lookup"><span data-stu-id="a561a-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="a561a-133">Seleccione **Engadir destino** para crear unha nova exportación.</span><span class="sxs-lookup"><span data-stu-id="a561a-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="a561a-134">No campo **Conexión da exportación** escolla unha conexión da sección Marketo.</span><span class="sxs-lookup"><span data-stu-id="a561a-134">In the **Connection for export** field, choose a connection from the Marketo section.</span></span> <span data-ttu-id="a561a-135">Se non ve o nome desta sección, non hai conexións deste tipo dispoñibles para vostede.</span><span class="sxs-lookup"><span data-stu-id="a561a-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="a561a-136">Introduza o seu **[ID de lista de Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span><span class="sxs-lookup"><span data-stu-id="a561a-136">Enter your **[Marketo list ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span></span> 

1. <span data-ttu-id="a561a-137">Na sección **Coincidencia de datos**, no campo **Correo electrónico**, seleccione o campo do seu perfil de cliente unificado que representa o enderezo de correo electrónico dun cliente.</span><span class="sxs-lookup"><span data-stu-id="a561a-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="a561a-138">Opcionalmente, pode exportar o **nome**, **apelidos**, **cidade**, **estado** e **país/rexión** para crear correos electrónicos máis personalizados.</span><span class="sxs-lookup"><span data-stu-id="a561a-138">Optionally, you can export **First name**, **Last name**, **City**, **State**, and **Country/Region**  to create more personalized emails.</span></span> <span data-ttu-id="a561a-139">Seleccione **Engadir atributo** para asignar estes campos.</span><span class="sxs-lookup"><span data-stu-id="a561a-139">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="a561a-140">Seleccione os segmentos que desexa exportar.</span><span class="sxs-lookup"><span data-stu-id="a561a-140">Select the segments you want to export.</span></span> <span data-ttu-id="a561a-141">Pode exportar ata 1 millón de perfís de clientes en total a Marketo.</span><span class="sxs-lookup"><span data-stu-id="a561a-141">You can export up to 1 million customer profiles in total to Marketo.</span></span>

1. <span data-ttu-id="a561a-142">Seleccione **Gardar**.</span><span class="sxs-lookup"><span data-stu-id="a561a-142">Select **Save**.</span></span>

<span data-ttu-id="a561a-143">Ao gardar unha exportación non se executa a exportación inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="a561a-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="a561a-144">A exportación execútase con cada [actualización programada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="a561a-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="a561a-145">Tamén pode [exportar datos baixo demanda](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="a561a-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="a561a-146">En Marketo, agora pode atopar os seus segmentos en [Listas de Marketo](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="a561a-146">In Marketo, you can now find your segments under [Marketo lists](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="a561a-147">Cumprimento e privacidade dos datos</span><span class="sxs-lookup"><span data-stu-id="a561a-147">Data privacy and compliance</span></span>

<span data-ttu-id="a561a-148">Cando habilita Dynamics 365 Customer Insights para transmitir datos a Marketo, permite a transferencia de datos fóra do límite de cumprimento de Dynamics 365 Customer Insights, incluíndo datos potencialmente confidenciais como os datos persoais.</span><span class="sxs-lookup"><span data-stu-id="a561a-148">When you enable Dynamics 365 Customer Insights to transmit data to Marketo, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="a561a-149">Microsoft transferirá estes datos segundo a súa instrución, pero vostede é responsable de garantir que Marketo cumpra as obrigas de privacidade ou seguridade que poida ter.</span><span class="sxs-lookup"><span data-stu-id="a561a-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Marketo meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="a561a-150">Para obter máis información, consulte a [Declaración de privacidade de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="a561a-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="a561a-151">O administrador de Dynamics 365 Customer Insights pode eliminar este destino de exportación en calquera momento para interromper o uso desta funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="a561a-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]