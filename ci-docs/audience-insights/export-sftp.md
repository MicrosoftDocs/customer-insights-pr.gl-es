---
title: Exportar datos de Customer Insights a servidores SFTP
description: Aprenda a configurar a conexión a un servidor SFTP.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c2529744d7a26a06324b79cad6a8001d75903545
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643501"
---
# <a name="connector-for-sftp-preview"></a><span data-ttu-id="66cb7-103">Conector de SFTP (vista previa)</span><span class="sxs-lookup"><span data-stu-id="66cb7-103">Connector for SFTP (preview)</span></span>

<span data-ttu-id="66cb7-104">Use os datos de cliente nas aplicacións de terceiros mediante a súa exportación a un servidor de protocolo seguro de transferencia de ficheiros (SFTP).</span><span class="sxs-lookup"><span data-stu-id="66cb7-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol(SFTP) host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="66cb7-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="66cb7-105">Prerequisites</span></span>

- <span data-ttu-id="66cb7-106">Dispoñibilidade dun servidor SFTP e correspondentes credenciais.</span><span class="sxs-lookup"><span data-stu-id="66cb7-106">Availability of a SFTP host and corresponding credentials.</span></span>

## <a name="connect-to-sftp"></a><span data-ttu-id="66cb7-107">Conectar con SFTP</span><span class="sxs-lookup"><span data-stu-id="66cb7-107">Connect to SFTP</span></span>

1. <span data-ttu-id="66cb7-108">Vaia a **Administrador** > **Exportar destinos**.</span><span class="sxs-lookup"><span data-stu-id="66cb7-108">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="66cb7-109">En **SFTP**, seleccione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="66cb7-109">Under **SFTP**, select **Set up**.</span></span>

1. <span data-ttu-id="66cb7-110">Déalle ao seu destino un nome recoñecible no campo **Nome para mostrar**.</span><span class="sxs-lookup"><span data-stu-id="66cb7-110">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="66cb7-111">Proporcione un **Nome de usuario**, **Contrasinal** e **Nome de servidor** para a súa conta de SFTP.</span><span class="sxs-lookup"><span data-stu-id="66cb7-111">Provide a **Username**, **Password** and **Hostname** for your SFTP account.</span></span> <span data-ttu-id="66cb7-112">Exemplo: se o cartafol raíz do seu servidor SFTP é /root/folder e desexa que os datos se exporten a /root/folder/ci_export_destination_folder, o servidor debería ser sftp://<server_address>/ci_export_destination_folder".</span><span class="sxs-lookup"><span data-stu-id="66cb7-112">Example: If your SFTP server's root folder is /root/folder, and you would like the data to be exported to /root/folder/ci_export_destination_folder, the the host should be sftp://<server_address>/ci_export_destination_folder".</span></span>

1. <span data-ttu-id="66cb7-113">Seleccionar **Verificar** para probar a conexión.</span><span class="sxs-lookup"><span data-stu-id="66cb7-113">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="66cb7-114">Despois de verificar con éxito, escolla se desexa exportar os seus datos **comprimidos** ou **descompromidos** e selecciona o **delimitador de campos** para os ficheiros exportados.</span><span class="sxs-lookup"><span data-stu-id="66cb7-114">After successful verification, choose if you want to export your data **Zipped** or **Unzipped**, and select the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="66cb7-115">Seleccione **Estou de acordo** para confirmar a **Privacidade e cumprimento dos datos**.</span><span class="sxs-lookup"><span data-stu-id="66cb7-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="66cb7-116">Seleccione **Seguinte** para comezar a configurar a exportación.</span><span class="sxs-lookup"><span data-stu-id="66cb7-116">Select **Next** to start configuring the export.</span></span>

## <a name="configure-the-connection"></a><span data-ttu-id="66cb7-117">Configurar a conexión</span><span class="sxs-lookup"><span data-stu-id="66cb7-117">Configure the connection</span></span>

1. <span data-ttu-id="66cb7-118">Seleccione os **atributos do cliente** que quere exportar.</span><span class="sxs-lookup"><span data-stu-id="66cb7-118">Select the **customer attributes** you want to export.</span></span> <span data-ttu-id="66cb7-119">Pode exportar un ou varios atributos.</span><span class="sxs-lookup"><span data-stu-id="66cb7-119">You can export one or multiple attributes.</span></span>

1. <span data-ttu-id="66cb7-120">Seleccione **Seguinte**.</span><span class="sxs-lookup"><span data-stu-id="66cb7-120">Select **Next**.</span></span>

1. <span data-ttu-id="66cb7-121">Seleccione os segmentos que desexa exportar.</span><span class="sxs-lookup"><span data-stu-id="66cb7-121">Select the segments you want to export.</span></span>

1. <span data-ttu-id="66cb7-122">Seleccione **Gardar**.</span><span class="sxs-lookup"><span data-stu-id="66cb7-122">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="66cb7-123">Exportar os datos</span><span class="sxs-lookup"><span data-stu-id="66cb7-123">Export the data</span></span>

<span data-ttu-id="66cb7-124">Pode [exportar datos baixo demanda](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="66cb7-124">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="66cb7-125">A exportación tamén se executará con todas as [actualizacións programadas](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="66cb7-125">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="66cb7-126">Cumprimento e privacidade dos datos</span><span class="sxs-lookup"><span data-stu-id="66cb7-126">Data privacy and compliance</span></span>

<span data-ttu-id="66cb7-127">Cando habilita Dynamics 365 Customer Insights para transmitir datos a SFTP, permite a transferencia de datos fóra do límite de cumprimento de Dynamics 365 Customer Insights, incluíndo datos potencialmente confidenciais como os datos persoais.</span><span class="sxs-lookup"><span data-stu-id="66cb7-127">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="66cb7-128">Microsoft transferirá estes datos segundo a súa instrución, pero vostede é responsable de garantir que o destino de exportación cumpra as obrigas de privacidade ou seguridade que poida ter.</span><span class="sxs-lookup"><span data-stu-id="66cb7-128">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="66cb7-129">Para obter máis información, consulte a [Declaración de privacidade de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="66cb7-129">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="66cb7-130">O administrador de Dynamics 365 Customer Insights pode eliminar este destino de exportación en calquera momento para interromper o uso desta funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="66cb7-130">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
