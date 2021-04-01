---
title: Exportar datos de Customer Insights a Dynamics 365 Sales
description: Aprenda a configurar a conexión con Dynamics 365 Sales.
ms.date: 02/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 39ecdf528c6be4d8fb420a52a6ed998317e43bcd
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598107"
---
# <a name="connector-for-dynamics-365-sales-preview"></a><span data-ttu-id="29897-103">Conector para Dynamics 365 Sales (previsualización)</span><span class="sxs-lookup"><span data-stu-id="29897-103">Connector for Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="29897-104">Use os datos dos clientes para crear listas de márketing, realizar o seguimento de fluxos de traballo e enviar promocións con Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="29897-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite"></a><span data-ttu-id="29897-105">Requisito previo</span><span class="sxs-lookup"><span data-stu-id="29897-105">Prerequisite</span></span>

1. <span data-ttu-id="29897-106">Os rexistros de contacto deben estar presentes en Dynamics 365 Sales antes de poder exportar un segmento de Customer Insights a Sales.</span><span class="sxs-lookup"><span data-stu-id="29897-106">Contact records must be present in Dynamics 365 Sales before you can export a segment from Customer Insights to Sales.</span></span> <span data-ttu-id="29897-107">Lea máis sobre como inxerir contactos en [Dynamics 365 Sales usando Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="29897-107">Read more on how to ingest contacts in [Dynamics 365 Sales using Common Data Services](connect-power-query.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="29897-108">A exportación de segmentos de información de audiencia a Sales non creará novos rexistros de contacto nas instancias de Sales.</span><span class="sxs-lookup"><span data-stu-id="29897-108">Exporting segments from audience insights to Sales will not create new contact records in the Sales instances.</span></span> <span data-ttu-id="29897-109">Os rexistros de contacto de Sales deben ser inxeridos na información do público e utilizados como orixe de datos.</span><span class="sxs-lookup"><span data-stu-id="29897-109">The contact records from Sales must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="29897-110">Tamén deben incluírse na entidade de cliente unificada para asignar os ID de clientes a ID de contacto antes de que os segmentos poidan ser exportados.</span><span class="sxs-lookup"><span data-stu-id="29897-110">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="configure-the-connector-for-sales"></a><span data-ttu-id="29897-111">Configurar o conector para Vendas</span><span class="sxs-lookup"><span data-stu-id="29897-111">Configure the connector for Sales</span></span>

1. <span data-ttu-id="29897-112">Na información do público, vaia a **Administrar** > **Destinos de exportación**.</span><span class="sxs-lookup"><span data-stu-id="29897-112">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="29897-113">En **Dynamics 365 Sales**, seleccione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="29897-113">Under **Dynamics 365 Sales**, select **Set up**.</span></span>

1. <span data-ttu-id="29897-114">Déalle ao seu destino da exploración un nome recoñecible no campo **Nome para mostrar**.</span><span class="sxs-lookup"><span data-stu-id="29897-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="29897-115">Insira o URL de Vendas da súa organización no campo **Enderezo do servidor**.</span><span class="sxs-lookup"><span data-stu-id="29897-115">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="29897-116">Na sección **Conta de administrador do servidor**, seleccione **Iniciar sesión** e escolla unha conta de Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="29897-116">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="29897-117">Asigne un campo de ID de cliente ao ID de contacto de Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="29897-117">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="29897-118">Seleccione **Seguinte**.</span><span class="sxs-lookup"><span data-stu-id="29897-118">Select **Next**.</span></span>

1. <span data-ttu-id="29897-119">Escolla un ou máis segmentos.</span><span class="sxs-lookup"><span data-stu-id="29897-119">Choose one or more segments.</span></span>

1. <span data-ttu-id="29897-120">Seleccione **Gardar**.</span><span class="sxs-lookup"><span data-stu-id="29897-120">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="29897-121">Exportar os datos</span><span class="sxs-lookup"><span data-stu-id="29897-121">Export the data</span></span>

<span data-ttu-id="29897-122">Pode [exportar datos baixo demanda](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="29897-122">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="29897-123">A exportación tamén se executará con todas as [actualizacións programadas](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="29897-123">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]