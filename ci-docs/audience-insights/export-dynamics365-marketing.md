---
title: Exportar datos de Customer Insights a Dynamics 365 Marketing
description: Aprenda a configurar a conexión con Dynamics 365 Marketing.
ms.date: 02/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 892aff643872f11307a2c43e5670edab657d7848
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597601"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a><span data-ttu-id="fc4d3-103">Conector para Dynamics 365 Marketing (previsualización)</span><span class="sxs-lookup"><span data-stu-id="fc4d3-103">Connector for Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="fc4d3-104">Use os [segmentos](segments.md) para xerar campañas e contactar con grupos específicos de clientes con Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="fc4d3-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="fc4d3-105">Para obter máis información, consulte [Usar segmentos de Dynamics 365 Customer Insights con Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="fc4d3-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite"></a><span data-ttu-id="fc4d3-106">Requisito previo</span><span class="sxs-lookup"><span data-stu-id="fc4d3-106">Prerequisite</span></span>

- <span data-ttu-id="fc4d3-107">Os rexistros de contacto deben estar presentes en Dynamics 365 Marketing antes de poder exportar un segmento de Customer Insights a Marketing.</span><span class="sxs-lookup"><span data-stu-id="fc4d3-107">Contact records must be present in Dynamics 365 Marketing before you can export a segment from Customer Insights to Marketing.</span></span> <span data-ttu-id="fc4d3-108">Lea máis sobre como inxerir contactos en [Dynamics 365 Marketing usando Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="fc4d3-108">Read more on how to ingest contacts in [Dynamics 365 Marketing using Common Data Services](connect-power-query.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="fc4d3-109">A exportación de segmentos de información de audiencia a Marketing non creará novos rexistros de contacto nas instancias de Marketing.</span><span class="sxs-lookup"><span data-stu-id="fc4d3-109">Exporting segments from audience insights to Marketing will not create new contact records in the Marketing instances.</span></span> <span data-ttu-id="fc4d3-110">Os rexistros de contacto de Marketing deben ser inxeridos na información do público e utilizados como orixe de datos.</span><span class="sxs-lookup"><span data-stu-id="fc4d3-110">The contact records from Marketing must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="fc4d3-111">Tamén deben incluírse na entidade de cliente unificada para asignar os ID de clientes a ID de contacto antes de que os segmentos poidan ser exportados.</span><span class="sxs-lookup"><span data-stu-id="fc4d3-111">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="configure-the-connector-for-marketing"></a><span data-ttu-id="fc4d3-112">Configurar o conector para márketing</span><span class="sxs-lookup"><span data-stu-id="fc4d3-112">Configure the connector for Marketing</span></span>

1. <span data-ttu-id="fc4d3-113">Na información do público, vaia a **Administrar** > **Destinos de exportación**.</span><span class="sxs-lookup"><span data-stu-id="fc4d3-113">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="fc4d3-114">En **Dynamics 365 Marketing**, seleccione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="fc4d3-114">Under **Dynamics 365 Marketing**, select **Set up**.</span></span>

1. <span data-ttu-id="fc4d3-115">Déalle ao seu destino da exploración un nome recoñecible no campo **Nome para mostrar**.</span><span class="sxs-lookup"><span data-stu-id="fc4d3-115">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="fc4d3-116">Insira o URL de mercadotecnia da súa organización no campo **Enderezo do servidor**.</span><span class="sxs-lookup"><span data-stu-id="fc4d3-116">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="fc4d3-117">Na sección **Conta de administrador do servidor**, seleccione **Iniciar sesión** e escolla unha conta de Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="fc4d3-117">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="fc4d3-118">Asigne un campo de ID de cliente ao ID de contacto de Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="fc4d3-118">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="fc4d3-119">Seleccione **Seguinte**.</span><span class="sxs-lookup"><span data-stu-id="fc4d3-119">Select **Next**.</span></span>

1. <span data-ttu-id="fc4d3-120">Escolla un ou máis segmentos.</span><span class="sxs-lookup"><span data-stu-id="fc4d3-120">Choose one or more segments.</span></span>

1. <span data-ttu-id="fc4d3-121">Seleccione **Gardar**.</span><span class="sxs-lookup"><span data-stu-id="fc4d3-121">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="fc4d3-122">Exportar os datos</span><span class="sxs-lookup"><span data-stu-id="fc4d3-122">Export the data</span></span>

<span data-ttu-id="fc4d3-123">Pode [exportar datos baixo demanda](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="fc4d3-123">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="fc4d3-124">A exportación tamén se executará con todas as [actualizacións programadas](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="fc4d3-124">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]