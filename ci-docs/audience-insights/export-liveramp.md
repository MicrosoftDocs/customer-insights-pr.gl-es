---
title: Conector de LiveRamp
description: Aprenda a configurar a conexión e a exportación a LiveRamp.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 987457966fe1fc034d9e3cd2a1ce33902c7a84f4
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760325"
---
# <a name="export-segments-to-liverampreg-preview"></a><span data-ttu-id="92098-103">Exportar segmentos a LiveRamp&reg; (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="92098-103">Export segments to LiveRamp&reg; (preview)</span></span>

<span data-ttu-id="92098-104">Active os seus datos en LiveRamp para conectar con máis de 500 plataformas dixitais, sociais e televisivas.</span><span class="sxs-lookup"><span data-stu-id="92098-104">Activate your data in LiveRamp to connect with over 500 platforms across digital, social, and TVs.</span></span> <span data-ttu-id="92098-105">Traballe cos seus datos en LiveRamp para orientar, suprimir e personalizar as campañas publicitarias.</span><span class="sxs-lookup"><span data-stu-id="92098-105">Work with your data in LiveRamp to target, suppress, and personalize ad campaigns.</span></span>

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="92098-106">Requisitos previos para unha conexión</span><span class="sxs-lookup"><span data-stu-id="92098-106">Prerequisites for a connection</span></span>

- <span data-ttu-id="92098-107">Para usar este conector precisa unha subscrición a LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="92098-107">You need a LiveRamp subscription to use this connector.</span></span>
- <span data-ttu-id="92098-108">Para obter unha subscrición, [contacte con LiveRamp](https://liveramp.com/contact/) directamente.</span><span class="sxs-lookup"><span data-stu-id="92098-108">To get a subscription, [contact LiveRamp](https://liveramp.com/contact/) directly.</span></span> <span data-ttu-id="92098-109">[Obteña máis información sobre LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span><span class="sxs-lookup"><span data-stu-id="92098-109">[Learn more about LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span></span>

## <a name="set-up-connection-to-liveramp"></a><span data-ttu-id="92098-110">Configurar conexión a LiveRamp</span><span class="sxs-lookup"><span data-stu-id="92098-110">Set up connection to LiveRamp</span></span>

1. <span data-ttu-id="92098-111">Vaia a **Administrar** > **Conexións**.</span><span class="sxs-lookup"><span data-stu-id="92098-111">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="92098-112">Seleccione **Engadir conexión** e elixa **LiveRamp** para configurar a conexión.</span><span class="sxs-lookup"><span data-stu-id="92098-112">Select **Add connection** and choose **LiveRamp** to configure the connection.</span></span>

1. <span data-ttu-id="92098-113">Déalle á conexión un nome recoñecible no campo **Nome para mostrar**.</span><span class="sxs-lookup"><span data-stu-id="92098-113">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="92098-114">O nome e o tipo de conexión describen esta conexión.</span><span class="sxs-lookup"><span data-stu-id="92098-114">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="92098-115">Recomendamos escoller un nome que explique o propósito e o destino da conexión.</span><span class="sxs-lookup"><span data-stu-id="92098-115">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="92098-116">Escolla quen pode usar esta conexión.</span><span class="sxs-lookup"><span data-stu-id="92098-116">Choose who can use this connection.</span></span> <span data-ttu-id="92098-117">Se non realiza ningunha acción, o valor predeterminado será Administradores.</span><span class="sxs-lookup"><span data-stu-id="92098-117">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="92098-118">Para obter máis información, consulte [Permitir aos colaboradores usar unha conexión para as exportacións](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="92098-118">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="92098-119">Proporcione un **Nome de usuario** e un **Contrasinal** para a súa conta de LiveRamp Secure FTP (SFTP).</span><span class="sxs-lookup"><span data-stu-id="92098-119">Provide a **Username** and **Password** for your LiveRamp Secure FTP (SFTP) account.</span></span>
<span data-ttu-id="92098-120">Estas credenciais poden ser diferentes das súas credenciais de LiveRamp Onboarding.</span><span class="sxs-lookup"><span data-stu-id="92098-120">These credentials may be different from your LiveRamp Onboarding credentials.</span></span>

1. <span data-ttu-id="92098-121">Seleccione **Verificar** para probar a conexión a LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="92098-121">Select **Verify** to test the connection to LiveRamp.</span></span>

1. <span data-ttu-id="92098-122">Despois de facer unha verificación con éxito, proporcione o seu consentimento para a **Privacidade e cumprimento dos datos** seleccionando a caixa de verificación **Estou de acordo**.</span><span class="sxs-lookup"><span data-stu-id="92098-122">After successful verification, provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="92098-123">Seleccione **Gardar** para completar a conexión.</span><span class="sxs-lookup"><span data-stu-id="92098-123">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="92098-124">Configurar unha exportación</span><span class="sxs-lookup"><span data-stu-id="92098-124">Configure an export</span></span>

<span data-ttu-id="92098-125">Pode configurar esta exportación se ten acceso a unha conexión deste tipo.</span><span class="sxs-lookup"><span data-stu-id="92098-125">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="92098-126">Para obter máis información, consulte [Permisos necesarios para configurar unha exportación](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="92098-126">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="92098-127">Vaia a **Datos** > **Exportacións**.</span><span class="sxs-lookup"><span data-stu-id="92098-127">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="92098-128">Seleccione **Engadir destino** para crear unha nova exportación.</span><span class="sxs-lookup"><span data-stu-id="92098-128">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="92098-129">No campo **Conexión da exportación** escolla unha conexión da sección LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="92098-129">In the **Connection for export** field, choose a connection from the LiveRamp section.</span></span> <span data-ttu-id="92098-130">Se non ve o nome desta sección, non hai conexións deste tipo dispoñibles para vostede.</span><span class="sxs-lookup"><span data-stu-id="92098-130">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="92098-131">No campo **Escoller o identificador clave**, seleccione **Correo electrónico**, **Nome e enderezo** ou **Teléfono** para envialos a LiveRamp para resolver a identidade.</span><span class="sxs-lookup"><span data-stu-id="92098-131">In the **Choose your key identifier** field, select **Email**,  **Name and address**, or **Phone** to send to LiveRamp for identity resolution.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="92098-132">![Conector LiveRamp con asignación de atributos](media/export-liveramp-segments.png "Conector LiveRamp con asignación de atributos")</span><span class="sxs-lookup"><span data-stu-id="92098-132">![LiveRamp connector with attribute mapping](media/export-liveramp-segments.png "LiveRamp connector with attribute mapping")</span></span>

1. <span data-ttu-id="92098-133">Asigne os atributos correspondentes desde a súa entidade de cliente unificada para o identificador de clave seleccionado.</span><span class="sxs-lookup"><span data-stu-id="92098-133">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>

1. <span data-ttu-id="92098-134">Seleccione **Engadir atributo** para asignar máis atributos para envialos a LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="92098-134">Select **Add attribute** to map more attributes to send to LiveRamp.</span></span>

   > [!TIP]
   > <span data-ttu-id="92098-135">O envío de máis atributos de identificador clave a LiveRamp é probable que provoque a obtención dunha taxa de coincidencia máis alta.</span><span class="sxs-lookup"><span data-stu-id="92098-135">Sending more key identifier attributes to LiveRamp is likely to get you a higher match rate.</span></span>

1. <span data-ttu-id="92098-136">Seleccione os segmentos que desexe exportar a LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="92098-136">Select the segments you want to export to LiveRamp.</span></span>

1. <span data-ttu-id="92098-137">Seleccione **Gardar**.</span><span class="sxs-lookup"><span data-stu-id="92098-137">Select **Save**.</span></span>

<span data-ttu-id="92098-138">Ao gardar unha exportación non se executa a exportación inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="92098-138">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="92098-139">A exportación execútase con cada [actualización programada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="92098-139">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="92098-140">Tamén pode [exportar datos baixo demanda](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="92098-140">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="92098-141">Cumprimento e privacidade dos datos</span><span class="sxs-lookup"><span data-stu-id="92098-141">Data privacy and compliance</span></span>

<span data-ttu-id="92098-142">Cando habilita Dynamics 365 Customer Insights para transmitir datos a LiveRamp, permite a transferencia de datos fóra do límite de cumprimento de Dynamics 365 Customer Insights, incluíndo datos potencialmente confidenciais como os datos persoais.</span><span class="sxs-lookup"><span data-stu-id="92098-142">When you enable Dynamics 365 Customer Insights to transmit data to Liveramp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="92098-143">Microsoft transferirá estes datos segundo a súa instrución, pero vostede é responsable de garantir que LiveRamp cumpra as obrigas de privacidade ou seguridade que poida ter.</span><span class="sxs-lookup"><span data-stu-id="92098-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Liveramp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="92098-144">Para obter máis información, consulte a [Declaración de privacidade de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="92098-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="92098-145">O administrador de Dynamics 365 Customer Insights pode eliminar este destino de exportación en calquera momento para interromper o uso desta funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="92098-145">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
