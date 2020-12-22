---
title: Exportar datos de Customer Insights a Dynamics 365 Marketing
description: Aprenda a configurar a conexión con Dynamics 365 Marketing.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 163387779b64bd78ef08e2d96a5f1c9615062f28
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643771"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a><span data-ttu-id="9680f-103">Conector para Dynamics 365 Marketing (previsualización)</span><span class="sxs-lookup"><span data-stu-id="9680f-103">Connector for Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="9680f-104">Use os [segmentos](segments.md) para xerar campañas e contactar con grupos específicos de clientes con Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="9680f-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="9680f-105">Para obter máis información, consulte [Usar segmentos de Dynamics 365 Customer Insights con Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="9680f-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite"></a><span data-ttu-id="9680f-106">Requisito previo</span><span class="sxs-lookup"><span data-stu-id="9680f-106">Prerequisite</span></span>

<span data-ttu-id="9680f-107">Rexistros de contactos [de Dynamics 365 Marketing inxeridos en Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="9680f-107">Contact records [from Dynamics 365 Marketing ingested Common Data Service](connect-power-query.md).</span></span>

## <a name="configure-the-connector-for-marketing"></a><span data-ttu-id="9680f-108">Configurar o conector para márketing</span><span class="sxs-lookup"><span data-stu-id="9680f-108">Configure the connector for Marketing</span></span>

1. <span data-ttu-id="9680f-109">Na información do público, vaia a **Administrar** > **Destinos de exportación**.</span><span class="sxs-lookup"><span data-stu-id="9680f-109">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="9680f-110">En **Dynamics 365 Marketing**, seleccione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="9680f-110">Under **Dynamics 365 Marketing**, select **Set up**.</span></span>

1. <span data-ttu-id="9680f-111">Déalle ao seu destino da exploración un nome recoñecible no campo **Nome para mostrar**.</span><span class="sxs-lookup"><span data-stu-id="9680f-111">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="9680f-112">Insira o URL de mercadotecnia da súa organización no campo **Enderezo do servidor**.</span><span class="sxs-lookup"><span data-stu-id="9680f-112">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="9680f-113">Na sección **Conta de administrador do servidor**, seleccione **Iniciar sesión** e escolla unha conta de Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="9680f-113">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="9680f-114">Asigne un campo de ID de cliente ao ID de contacto de Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="9680f-114">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="9680f-115">Seleccione **Seguinte**.</span><span class="sxs-lookup"><span data-stu-id="9680f-115">Select **Next**.</span></span>

1. <span data-ttu-id="9680f-116">Escolla un ou máis segmentos.</span><span class="sxs-lookup"><span data-stu-id="9680f-116">Choose one or more segments.</span></span>

1. <span data-ttu-id="9680f-117">Seleccione **Gardar**.</span><span class="sxs-lookup"><span data-stu-id="9680f-117">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="9680f-118">Exportar os datos</span><span class="sxs-lookup"><span data-stu-id="9680f-118">Export the data</span></span>

<span data-ttu-id="9680f-119">Pode [exportar datos baixo demanda](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="9680f-119">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="9680f-120">A exportación tamén se executará con todas as [actualizacións programadas](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="9680f-120">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
