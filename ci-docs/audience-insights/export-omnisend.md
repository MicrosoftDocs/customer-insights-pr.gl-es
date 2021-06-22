---
title: Exportar datos de Customer Insights a Omnisend
description: Aprenda a configurar a conexión e exportar a Omnisend.
ms.date: 05/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8bd692819fa8451ded5e74191ee717f81f87425d
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124487"
---
# <a name="export-segments-to-omnisend-preview"></a><span data-ttu-id="0e03b-103">Exportar segmentos a Omnisend (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="0e03b-103">Export segments to Omnisend (preview)</span></span>

<span data-ttu-id="0e03b-104">Exporte segmentos de perfís de clientes unificados a Omnisend e utilíceos para actividades de márketing.</span><span class="sxs-lookup"><span data-stu-id="0e03b-104">Export segments of unified customer profiles to Omnisend and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0e03b-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="0e03b-105">Prerequisites</span></span>

-   <span data-ttu-id="0e03b-106">Ten unha [conta de Omnisend](https://www.omnisend.com/) e as correspondentes credenciais de administrador.</span><span class="sxs-lookup"><span data-stu-id="0e03b-106">You have an [Omnisend account](https://www.omnisend.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="0e03b-107">Ten [segmentos configurados](segments.md) na información do público.</span><span class="sxs-lookup"><span data-stu-id="0e03b-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="0e03b-108">Os perfís de clientes unificados nos segmentos exportados conteñen un campo que representa un enderezo de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="0e03b-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="0e03b-109">Limitacións coñecidas</span><span class="sxs-lookup"><span data-stu-id="0e03b-109">Known limitations</span></span>

- <span data-ttu-id="0e03b-110">Pode exportar ata 1 millón de perfís por exportación a Omnisend e pode tardar ata 4 horas en completarse.</span><span class="sxs-lookup"><span data-stu-id="0e03b-110">You can export up to 1 million profiles per export to Omnisend and it can take up to 4 hours to complete.</span></span>
- <span data-ttu-id="0e03b-111">A exportación a Omnisend está limitada a segmentos.</span><span class="sxs-lookup"><span data-stu-id="0e03b-111">Exporting to Omnisend is limited to segments.</span></span>
- <span data-ttu-id="0e03b-112">O número de perfís que pode exportar a Omnisend depende do seu contrato con Omnisend.</span><span class="sxs-lookup"><span data-stu-id="0e03b-112">The number of profiles that you can export to Omnisend depends on your contract with Omnisend.</span></span>

## <a name="set-up-connection-to-omnisend"></a><span data-ttu-id="0e03b-113">Configurar conexión a Omnisend</span><span class="sxs-lookup"><span data-stu-id="0e03b-113">Set up connection to Omnisend</span></span>

1. <span data-ttu-id="0e03b-114">Vaia a **Administrar** > **Conexións**.</span><span class="sxs-lookup"><span data-stu-id="0e03b-114">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="0e03b-115">Seleccione **Engadir conexión** e elixa **Omnisend** para configurar a conexión.</span><span class="sxs-lookup"><span data-stu-id="0e03b-115">Select **Add connection** and choose **Omnisend** to configure the connection.</span></span>

1. <span data-ttu-id="0e03b-116">Déalle á conexión un nome recoñecible no campo **Nome para mostrar**.</span><span class="sxs-lookup"><span data-stu-id="0e03b-116">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="0e03b-117">O nome e o tipo de conexión describen esta conexión.</span><span class="sxs-lookup"><span data-stu-id="0e03b-117">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="0e03b-118">Recomendamos escoller un nome que explique o propósito e o destino da conexión.</span><span class="sxs-lookup"><span data-stu-id="0e03b-118">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="0e03b-119">Escolla quen pode usar esta conexión.</span><span class="sxs-lookup"><span data-stu-id="0e03b-119">Choose who can use this connection.</span></span> <span data-ttu-id="0e03b-120">Por defecto só son os administradores.</span><span class="sxs-lookup"><span data-stu-id="0e03b-120">By default it's only administrators.</span></span> <span data-ttu-id="0e03b-121">Para obter máis información, consulte [Permitir aos colaboradores usar unha conexión para as exportacións](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="0e03b-121">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="0e03b-122">Introduza a súa [clave da API de Omnisend](https://support.omnisend.com/en/articles/1061890-generating-api-key).</span><span class="sxs-lookup"><span data-stu-id="0e03b-122">Enter your [Omnisend API key](https://support.omnisend.com/en/articles/1061890-generating-api-key).</span></span>

1. <span data-ttu-id="0e03b-123">Seleccione **Estou de acordo** para confirmar a **Privacidade e cumprimento dos datos**.</span><span class="sxs-lookup"><span data-stu-id="0e03b-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="0e03b-124">Seleccione **Conectar** para iniciar a conexión a Omnisend.</span><span class="sxs-lookup"><span data-stu-id="0e03b-124">Select **Connect** to initialize the connection to Omnisend.</span></span>

1. <span data-ttu-id="0e03b-125">Seleccione **Autoengadirse como usuario de exportación** e proporcione as súas credenciais de Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="0e03b-125">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="0e03b-126">Seleccione **Gardar** para completar a conexión.</span><span class="sxs-lookup"><span data-stu-id="0e03b-126">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="0e03b-127">Configurar unha exportación</span><span class="sxs-lookup"><span data-stu-id="0e03b-127">Configure an export</span></span>

<span data-ttu-id="0e03b-128">Pode configurar esta exportación se ten acceso a unha conexión deste tipo.</span><span class="sxs-lookup"><span data-stu-id="0e03b-128">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="0e03b-129">Para obter máis información, consulte [Permisos necesarios para configurar unha exportación](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="0e03b-129">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="0e03b-130">Vaia a **Datos** > **Exportacións**.</span><span class="sxs-lookup"><span data-stu-id="0e03b-130">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="0e03b-131">Seleccione **Engadir destino** para crear unha nova exportación.</span><span class="sxs-lookup"><span data-stu-id="0e03b-131">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="0e03b-132">No campo **Conexión da exportación** escolla unha conexión da sección Omnisend.</span><span class="sxs-lookup"><span data-stu-id="0e03b-132">In the **Connection for export** field, choose a connection from the Omnisend section.</span></span> <span data-ttu-id="0e03b-133">Se non ve o nome desta sección, non hai conexións deste tipo dispoñibles para vostede.</span><span class="sxs-lookup"><span data-stu-id="0e03b-133">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="0e03b-134">Na sección **Coincidencia de datos**, no campo **Correo electrónico**, seleccione o campo do seu perfil de cliente unificado que representa o enderezo de correo electrónico dun cliente.</span><span class="sxs-lookup"><span data-stu-id="0e03b-134">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="0e03b-135">É necesario exportar segmentos a Omnisend.</span><span class="sxs-lookup"><span data-stu-id="0e03b-135">It's required to export segments to Omnisend.</span></span> <span data-ttu-id="0e03b-136">Opcionalmente, pode exportar o nome, apelidos, enderezo, país ou rexión, estado, cidade e código postal para crear correos electrónicos máis personalizados.</span><span class="sxs-lookup"><span data-stu-id="0e03b-136">Optionally, you can export First name, Last name, Address, Country/Region, State, City, and Post Code to create more personalized emails.</span></span> <span data-ttu-id="0e03b-137">Seleccione **Engadir atributo** para asignar estes campos.</span><span class="sxs-lookup"><span data-stu-id="0e03b-137">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="0e03b-138">Seleccione **Gardar**.</span><span class="sxs-lookup"><span data-stu-id="0e03b-138">Select **Save**.</span></span>

<span data-ttu-id="0e03b-139">Ao gardar unha exportación non se executa a exportación inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="0e03b-139">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="0e03b-140">A exportación execútase con cada [actualización programada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="0e03b-140">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="0e03b-141">Tamén pode [exportar datos baixo demanda](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="0e03b-141">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="0e03b-142">Cumprimento e privacidade dos datos</span><span class="sxs-lookup"><span data-stu-id="0e03b-142">Data privacy and compliance</span></span>

<span data-ttu-id="0e03b-143">Cando habilita Dynamics 365 Customer Insights para transmitir datos a Omnisend, permite a transferencia de datos fóra do límite de cumprimento de Dynamics 365 Customer Insights, incluíndo datos potencialmente confidenciais como os datos persoais.</span><span class="sxs-lookup"><span data-stu-id="0e03b-143">When you enable Dynamics 365 Customer Insights to transmit data to Ommisend, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="0e03b-144">Microsoft transferirá estes datos segundo a súa instrución, pero vostede é responsable de asegurarse de que Omnisend cumpra as obrigas de privacidade ou seguridade que poida ter.</span><span class="sxs-lookup"><span data-stu-id="0e03b-144">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Omnisend meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="0e03b-145">Para obter máis información, consulte a [Declaración de privacidade de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="0e03b-145">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="0e03b-146">O administrador de Dynamics 365 Customer Insights pode eliminar este destino de exportación en calquera momento para interromper o uso desta funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="0e03b-146">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
