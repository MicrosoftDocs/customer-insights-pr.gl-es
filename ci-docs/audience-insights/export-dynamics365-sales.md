---
title: Exportar datos de Customer Insights a Dynamics 365 Sales
description: Aprenda a configurar a conexión con Dynamics 365 Sales.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: af0824e69dfdf620a0ac756e32a9bd3dd85e5151
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643816"
---
# <a name="connector-for-dynamics-365-sales-preview"></a><span data-ttu-id="06b66-103">Conector para Dynamics 365 Sales (previsualización)</span><span class="sxs-lookup"><span data-stu-id="06b66-103">Connector for Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="06b66-104">Use os datos dos clientes para crear listas de márketing, realizar o seguimento de fluxos de traballo e enviar promocións con Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="06b66-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite"></a><span data-ttu-id="06b66-105">Requisito previo</span><span class="sxs-lookup"><span data-stu-id="06b66-105">Prerequisite</span></span>

<span data-ttu-id="06b66-106">Rexistros de contactos [de Dynamics 365 Sales inxeridos mediante Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="06b66-106">Contact records [from Dynamics 365 Sales ingested using Common Data Service](connect-power-query.md).</span></span>

## <a name="configure-the-connector-for-sales"></a><span data-ttu-id="06b66-107">Configurar o conector para Vendas</span><span class="sxs-lookup"><span data-stu-id="06b66-107">Configure the connector for Sales</span></span>

1. <span data-ttu-id="06b66-108">Na información do público, vaia a **Administrar** > **Destinos de exportación**.</span><span class="sxs-lookup"><span data-stu-id="06b66-108">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="06b66-109">En **Dynamics 365 Sales**, seleccione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="06b66-109">Under **Dynamics 365 Sales**, select **Set up**.</span></span>

1. <span data-ttu-id="06b66-110">Déalle ao seu destino da exploración un nome recoñecible no campo **Nome para mostrar**.</span><span class="sxs-lookup"><span data-stu-id="06b66-110">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="06b66-111">Insira o URL de Vendas da súa organización no campo **Enderezo do servidor**.</span><span class="sxs-lookup"><span data-stu-id="06b66-111">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="06b66-112">Na sección **Conta de administrador do servidor**, seleccione **Iniciar sesión** e escolla unha conta de Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="06b66-112">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="06b66-113">Asigne un campo de ID de cliente ao ID de contacto de Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="06b66-113">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="06b66-114">Seleccione **Seguinte**.</span><span class="sxs-lookup"><span data-stu-id="06b66-114">Select **Next**.</span></span>

1. <span data-ttu-id="06b66-115">Escolla un ou máis segmentos.</span><span class="sxs-lookup"><span data-stu-id="06b66-115">Choose one or more segments.</span></span>

1. <span data-ttu-id="06b66-116">Seleccione **Gardar**.</span><span class="sxs-lookup"><span data-stu-id="06b66-116">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="06b66-117">Exportar os datos</span><span class="sxs-lookup"><span data-stu-id="06b66-117">Export the data</span></span>

<span data-ttu-id="06b66-118">Pode [exportar datos baixo demanda](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="06b66-118">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="06b66-119">A exportación tamén se executará con todas as [actualizacións programadas](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="06b66-119">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
