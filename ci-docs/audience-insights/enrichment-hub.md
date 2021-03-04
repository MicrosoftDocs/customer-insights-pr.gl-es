---
title: Enriquecer perfís de clientes unificados
description: Use capacidades para enriquecer os datos dos seus clientes.
ms.date: 11/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 6b73aa93ec1a98f2b8d20d02e88bc6304f887078
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269466"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="35b8f-103">Enriquecemento dos perfís de clientes (vista previa)</span><span class="sxs-lookup"><span data-stu-id="35b8f-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="35b8f-104">Use datos de fontes como Microsoft e outros socios para enriquecer os seus datos de clientes.</span><span class="sxs-lookup"><span data-stu-id="35b8f-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Páxina da plataforma común de enriquecemento":::

<span data-ttu-id="35b8f-106">Na información do público, vaia a **Datos** > **Enriquecemento** para traballar con opcións de enriquecemento.</span><span class="sxs-lookup"><span data-stu-id="35b8f-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>    
<span data-ttu-id="35b8f-107">Debe ter permisos de colaborador ou administrador para crear ou editar enriquecementos.</span><span class="sxs-lookup"><span data-stu-id="35b8f-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="35b8f-108">Para obter máis información, consulte [Permisos](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="35b8f-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="35b8f-109">No separador **Descubrir**, atopará os seguintes enriquecementos:</span><span class="sxs-lookup"><span data-stu-id="35b8f-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="35b8f-110">[Marcas](enrichment-microsoft-graph.md) fornecidas por Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="35b8f-110">[Brands](enrichment-microsoft-graph.md) provided by Microsoft Graph</span></span>
- <span data-ttu-id="35b8f-111">[Intereses](enrichment-microsoft-graph.md) fornecidos por Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="35b8f-111">[Interests](enrichment-microsoft-graph.md) provided by Microsoft Graph</span></span>
- <span data-ttu-id="35b8f-112">[Datos da empresa](enrichment-leadspace.md) proporcionados por Leadspace</span><span class="sxs-lookup"><span data-stu-id="35b8f-112">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="35b8f-113">[Datos demográficos](enrichment-experian.md) proporcionados por Experian</span><span class="sxs-lookup"><span data-stu-id="35b8f-113">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="35b8f-114">[Datos de localización](enrichment-here.md) subministrados por HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="35b8f-114">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="35b8f-115">[Datos personalizados](enrichment-SFTP-custom-import.md) a través do protocolo seguro de transferencia de ficheiros (SFTP)</span><span class="sxs-lookup"><span data-stu-id="35b8f-115">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="35b8f-116">No separador **Os meus enriquecementos**, pode ver os enriquecementos que configurou e editar as súas propiedades.</span><span class="sxs-lookup"><span data-stu-id="35b8f-116">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="35b8f-117">Xestionar os enriquecementos existentes</span><span class="sxs-lookup"><span data-stu-id="35b8f-117">Manage existing enrichments</span></span>

<span data-ttu-id="35b8f-118">Vaia a **Os meus enriquecementos** para ver todos os enriquecementos configurados.</span><span class="sxs-lookup"><span data-stu-id="35b8f-118">Go to the **My enrichments** to see all configured enrichments.</span></span> <span data-ttu-id="35b8f-119">Cada enriquecemento represéntase como unha liña que inclúe información adicional sobre o enriquecemento.</span><span class="sxs-lookup"><span data-stu-id="35b8f-119">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="35b8f-120">Seleccione un enriquecemento para ver as opcións dispoñibles.</span><span class="sxs-lookup"><span data-stu-id="35b8f-120">Select an enrichment to see the available options.</span></span> <span data-ttu-id="35b8f-121">Tamén pode seleccionar os puntos suspensivos (...) nun elemento da lista para ver as opcións.</span><span class="sxs-lookup"><span data-stu-id="35b8f-121">Alternatively, you can select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Opcións para xestionar os enriquecementos na lista de enriquecementos":::

- <span data-ttu-id="35b8f-123">**Ver** detalles do enriquecemento co número de perfís de clientes enriquecidos.</span><span class="sxs-lookup"><span data-stu-id="35b8f-123">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="35b8f-124">**Editar** a configuración do enriquecemento.</span><span class="sxs-lookup"><span data-stu-id="35b8f-124">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="35b8f-125">**Execute** o enriquecemento para actualizar os perfís dos clientes cos últimos datos.</span><span class="sxs-lookup"><span data-stu-id="35b8f-125">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="35b8f-126">**Desactivar** un enriquecemento existente para evitar que se actualice automaticamente con cada actualización programada.</span><span class="sxs-lookup"><span data-stu-id="35b8f-126">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="35b8f-127">Os datos da última actualización exitosa seguirán dispoñibles.</span><span class="sxs-lookup"><span data-stu-id="35b8f-127">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="35b8f-128">**Activar** un enriquecemento inactivo para reiniciar a actualización automática con cada actualización programada.</span><span class="sxs-lookup"><span data-stu-id="35b8f-128">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="35b8f-129">**Eliminar** un enriquecemento.</span><span class="sxs-lookup"><span data-stu-id="35b8f-129">**Delete** an enrichment.</span></span>

<span data-ttu-id="35b8f-130">Pode executar ou desactivar varios enriquecementos á vez seleccionándoos na lista.</span><span class="sxs-lookup"><span data-stu-id="35b8f-130">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="35b8f-131">As opcións de visualización e edición non están dispoñibles como acción masiva e só funcionan para un enriquecemento á vez.</span><span class="sxs-lookup"><span data-stu-id="35b8f-131">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]