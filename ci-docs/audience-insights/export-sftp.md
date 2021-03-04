---
title: Exportar datos de Customer Insights a servidores SFTP
description: Aprenda a configurar a conexión a un servidor SFTP.
ms.date: 01/27/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ddba55b3ca159c0095371e46385dcf1d3ed4a63d
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267996"
---
# <a name="connector-for-sftp-preview"></a><span data-ttu-id="f903d-103">Conector de SFTP (vista previa)</span><span class="sxs-lookup"><span data-stu-id="f903d-103">Connector for SFTP (preview)</span></span>

<span data-ttu-id="f903d-104">Use os datos de cliente nas aplicacións de terceiros mediante a súa exportación a un servidor de protocolo seguro de transferencia de ficheiros (SFTP).</span><span class="sxs-lookup"><span data-stu-id="f903d-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol (SFTP) host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f903d-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="f903d-105">Prerequisites</span></span>

- <span data-ttu-id="f903d-106">Dispoñibilidade dun servidor SFTP e as credenciais correspondentes.</span><span class="sxs-lookup"><span data-stu-id="f903d-106">Availability of an SFTP host and corresponding credentials.</span></span>

## <a name="connect-to-sftp"></a><span data-ttu-id="f903d-107">Conectar con SFTP</span><span class="sxs-lookup"><span data-stu-id="f903d-107">Connect to SFTP</span></span>

1. <span data-ttu-id="f903d-108">Vaia a **Administrador** > **Exportar destinos**.</span><span class="sxs-lookup"><span data-stu-id="f903d-108">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="f903d-109">En **SFTP**, seleccione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="f903d-109">Under **SFTP**, select **Set up**.</span></span>

1. <span data-ttu-id="f903d-110">Déalle ao seu destino un nome recoñecible no campo **Nome para mostrar**.</span><span class="sxs-lookup"><span data-stu-id="f903d-110">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="f903d-111">Proporcione un **Nome de usuario**, **Contrasinal**, **Nome de servidor** e **Cartafol de exportación** para a súa conta de SFTP.</span><span class="sxs-lookup"><span data-stu-id="f903d-111">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="f903d-112">Seleccionar **Verificar** para probar a conexión.</span><span class="sxs-lookup"><span data-stu-id="f903d-112">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="f903d-113">Despois de verificar correctamente, escolla se desexa exportar os seus datos **Comprimidos con gzip** ou **Descomprimidos** e seleccione o **delimitador de campo** para os ficheiros exportados.</span><span class="sxs-lookup"><span data-stu-id="f903d-113">After successful verification, choose if you want to export your data **Gzipped** or **Unzipped**, and select the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="f903d-114">Seleccione **Estou de acordo** para confirmar a **Privacidade e cumprimento dos datos**.</span><span class="sxs-lookup"><span data-stu-id="f903d-114">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="f903d-115">Seleccione **Seguinte** para comezar a configurar a exportación.</span><span class="sxs-lookup"><span data-stu-id="f903d-115">Select **Next** to start configuring the export.</span></span>

## <a name="configure-the-export"></a><span data-ttu-id="f903d-116">Configurar a exportación</span><span class="sxs-lookup"><span data-stu-id="f903d-116">Configure the export</span></span>

1. <span data-ttu-id="f903d-117">Seleccione as entidades, por exemplo, segmentos que desexa exportar.</span><span class="sxs-lookup"><span data-stu-id="f903d-117">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="f903d-118">Cada entidade seleccionada terá ata cinco ficheiros de saída cando se exporten.</span><span class="sxs-lookup"><span data-stu-id="f903d-118">Each selected entity will be up to five output files when exported.</span></span> 

1. <span data-ttu-id="f903d-119">Seleccione **Gardar**.</span><span class="sxs-lookup"><span data-stu-id="f903d-119">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="f903d-120">Exportar os datos</span><span class="sxs-lookup"><span data-stu-id="f903d-120">Export the data</span></span>

<span data-ttu-id="f903d-121">Pode [exportar datos baixo demanda](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="f903d-121">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="f903d-122">A exportación tamén se executará con todas as [actualizacións programadas](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="f903d-122">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="f903d-123">Limitacións coñecidas</span><span class="sxs-lookup"><span data-stu-id="f903d-123">Known limitations</span></span>

- <span data-ttu-id="f903d-124">O tempo de execución dunha exportación depende do rendemento do seu sistema.</span><span class="sxs-lookup"><span data-stu-id="f903d-124">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="f903d-125">Recomendamos dous núcleos de CPU e 1 Gb de memoria como configuración mínima do seu servidor.</span><span class="sxs-lookup"><span data-stu-id="f903d-125">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="f903d-126">As entidades exportadoras con ata 100 millóns de perfís de clientes poden tardar 90 minutos cando se usa a configuración mínima recomendada de dous núcleos de CPU e 1 Gb de memoria.</span><span class="sxs-lookup"><span data-stu-id="f903d-126">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration of two CPU cores and 1 Gb of memory.</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="f903d-127">Cumprimento e privacidade dos datos</span><span class="sxs-lookup"><span data-stu-id="f903d-127">Data privacy and compliance</span></span>

<span data-ttu-id="f903d-128">Cando habilita Dynamics 365 Customer Insights para transmitir datos a SFTP, permite a transferencia de datos fóra do límite de cumprimento de Dynamics 365 Customer Insights, incluíndo datos potencialmente confidenciais como os datos persoais.</span><span class="sxs-lookup"><span data-stu-id="f903d-128">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="f903d-129">Microsoft transferirá estes datos segundo a súa instrución, pero vostede é responsable de garantir que o destino de exportación cumpra as obrigas de privacidade ou seguridade que poida ter.</span><span class="sxs-lookup"><span data-stu-id="f903d-129">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="f903d-130">Para obter máis información, consulte a [Declaración de privacidade de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="f903d-130">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="f903d-131">O administrador de Dynamics 365 Customer Insights pode eliminar este destino de exportación en calquera momento para interromper o uso desta funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="f903d-131">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]