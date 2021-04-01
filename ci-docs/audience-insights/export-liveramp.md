---
title: Conector de LiveRamp
description: Como exportar datos a LiveRamp.
ms.date: 12/02/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 6ef4388b0e8ba8bc5866807765d8a872d41c9c14
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597555"
---
# <a name="liverampreg-connector-preview"></a><span data-ttu-id="dfe77-103">Conector LiveRamp&reg; (vista previa)</span><span class="sxs-lookup"><span data-stu-id="dfe77-103">LiveRamp&reg; connector (preview)</span></span>

<span data-ttu-id="dfe77-104">Active os seus datos en LiveRamp para conectarse con máis de 500 plataformas en ecosistemas dixitais, sociais e de televisión.</span><span class="sxs-lookup"><span data-stu-id="dfe77-104">Activate your data in LiveRamp to connect with over 500 platforms across digital, social, and TV ecosystems.</span></span> <span data-ttu-id="dfe77-105">Traballe cos seus datos en LiveRamp para orientar, suprimir e personalizar as campañas publicitarias.</span><span class="sxs-lookup"><span data-stu-id="dfe77-105">Work with your data in LiveRamp to target, suppress, and personalize ad campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="dfe77-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="dfe77-106">Prerequisites</span></span>

- <span data-ttu-id="dfe77-107">Para usar este conector precisa unha subscrición a LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="dfe77-107">You need a LiveRamp subscription to use this connector.</span></span>
- <span data-ttu-id="dfe77-108">Para obter unha subscrición, [contacte con LiveRamp](https://liveramp.com/contact/) directamente.</span><span class="sxs-lookup"><span data-stu-id="dfe77-108">To get a subscription, [contact LiveRamp](https://liveramp.com/contact/) directly.</span></span> <span data-ttu-id="dfe77-109">[Obteña máis información sobre LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span><span class="sxs-lookup"><span data-stu-id="dfe77-109">[Learn more about LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span></span>

## <a name="connect-to-liveramp"></a><span data-ttu-id="dfe77-110">Conectar con LiveRamp</span><span class="sxs-lookup"><span data-stu-id="dfe77-110">Connect to LiveRamp</span></span>

1. <span data-ttu-id="dfe77-111">Na información do público, vaia a **Administrar** > **Destinos de exportación**.</span><span class="sxs-lookup"><span data-stu-id="dfe77-111">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="dfe77-112">No mosaico de **LiveRamp**, seleccione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="dfe77-112">In the **LiveRamp** tile, select **Set up**.</span></span>

1. <span data-ttu-id="dfe77-113">Déalle ao seu destino un nome recoñecible no campo **Nome para mostrar**.</span><span class="sxs-lookup"><span data-stu-id="dfe77-113">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="dfe77-114">Proporcione un **Nome de usuario** e un **Contrasinal** para a súa conta de LiveRamp Secure FTP (SFTP).</span><span class="sxs-lookup"><span data-stu-id="dfe77-114">Provide a **Username** and **Password** for your LiveRamp Secure FTP (SFTP) account.</span></span>
<span data-ttu-id="dfe77-115">Estas credenciais poden ser diferentes das súas credenciais de LiveRamp Onboarding.</span><span class="sxs-lookup"><span data-stu-id="dfe77-115">These credentials may be different from your LiveRamp Onboarding credentials.</span></span>

1. <span data-ttu-id="dfe77-116">Seleccione **Verificar** para probar a conexión a LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="dfe77-116">Select **Verify** to test the connection to LiveRamp.</span></span>

1. <span data-ttu-id="dfe77-117">Despois de facer unha verificación con éxito, proporcione o seu consentimento para a **Privacidade e cumprimento dos datos** seleccionando a caixa de verificación **Estou de acordo**.</span><span class="sxs-lookup"><span data-stu-id="dfe77-117">After successful verification, provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="dfe77-118">Seleccione **Seguinte** para configurar o conector LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="dfe77-118">Select **Next** to set up the LiveRamp connector.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="dfe77-119">Configurar o conector</span><span class="sxs-lookup"><span data-stu-id="dfe77-119">Configure the connector</span></span>

1. <span data-ttu-id="dfe77-120">No campo **Escoller o identificador clave**, seleccione **Correo electrónico**, **Nome e enderezo** ou **Teléfono** para envialos a LiveRamp para resolver a identidade.</span><span class="sxs-lookup"><span data-stu-id="dfe77-120">In the **Choose your key identifier** field, select **Email**,  **Name and address**, or **Phone** to send to LiveRamp for identity resolution.</span></span>

1. <span data-ttu-id="dfe77-121">Asigne os atributos correspondentes desde a súa entidade de cliente unificada para o identificador de clave seleccionado.</span><span class="sxs-lookup"><span data-stu-id="dfe77-121">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>

1. <span data-ttu-id="dfe77-122">Seleccione **Engadir atributo** para asignar atributos adicionais para enviar a LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="dfe77-122">Select **Add attribute** to map additional attributes to send to LiveRamp.</span></span>

   > [!TIP]
   > <span data-ttu-id="dfe77-123">O envío de máis atributos de identificador clave a LiveRamp é probable que provoque a obtención dunha taxa de coincidencia máis alta.</span><span class="sxs-lookup"><span data-stu-id="dfe77-123">Sending more key identifier attributes to LiveRamp is likely to get you a higher match rate.</span></span>

1. <span data-ttu-id="dfe77-124">Seleccione os segmentos que desexe exportar a LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="dfe77-124">Select the segments you want to export to LiveRamp.</span></span>

1. <span data-ttu-id="dfe77-125">Seleccione **Gardar**.</span><span class="sxs-lookup"><span data-stu-id="dfe77-125">Select **Save**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="dfe77-126">![Conector LiveRamp con asignación de atributos](media/export-liveramp-segments.png "Conector LiveRamp con asignación de atributos")</span><span class="sxs-lookup"><span data-stu-id="dfe77-126">![LiveRamp connector with attribute mapping](media/export-liveramp-segments.png "LiveRamp connector with attribute mapping")</span></span>

## <a name="export-the-data"></a><span data-ttu-id="dfe77-127">Exportar os datos</span><span class="sxs-lookup"><span data-stu-id="dfe77-127">Export the data</span></span>

<span data-ttu-id="dfe77-128">A exportación comezará en breve se se cumpren todos os requisitos previos para a exportación.</span><span class="sxs-lookup"><span data-stu-id="dfe77-128">The export will start shortly if all prerequisites for export have been completed.</span></span> <span data-ttu-id="dfe77-129">A exportación tamén se executará con todas as [actualizacións programadas](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="dfe77-129">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
<span data-ttu-id="dfe77-130">Unha vez rematada a exportación, pode iniciar sesión en LiveRamp Onboarding para activar e distribuír os seus datos.</span><span class="sxs-lookup"><span data-stu-id="dfe77-130">Once the export is successfully completed, you can sign in to LiveRamp Onboarding to activate and distribute your data.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="dfe77-131">Cumprimento e privacidade dos datos</span><span class="sxs-lookup"><span data-stu-id="dfe77-131">Data privacy and compliance</span></span>

<span data-ttu-id="dfe77-132">Cando habilita Dynamics 365 Customer Insights para transmitir datos a LiveRamp, permite a transferencia de datos fóra do límite de cumprimento de Dynamics 365 Customer Insights, incluíndo datos potencialmente confidenciais como os datos persoais.</span><span class="sxs-lookup"><span data-stu-id="dfe77-132">When you enable Dynamics 365 Customer Insights to transmit data to Liveramp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="dfe77-133">Microsoft transferirá estes datos segundo a súa instrución, pero vostede é responsable de garantir que LiveRamp cumpra as obrigas de privacidade ou seguridade que poida ter.</span><span class="sxs-lookup"><span data-stu-id="dfe77-133">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Liveramp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="dfe77-134">Para obter máis información, consulte a [Declaración de privacidade de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="dfe77-134">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="dfe77-135">O administrador de Dynamics 365 Customer Insights pode eliminar este destino de exportación en calquera momento para interromper o uso desta funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="dfe77-135">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]