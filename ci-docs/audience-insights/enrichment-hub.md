---
title: Enriquecer perfís de clientes unificados
description: Use capacidades para enriquecer os datos dos seus clientes.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: c35e73b366fcd5db2ba5a757295ddda6db30efa0
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305246"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="7a0f1-103">Enriquecemento dos perfís de clientes (vista previa)</span><span class="sxs-lookup"><span data-stu-id="7a0f1-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="7a0f1-104">Use datos de fontes como Microsoft e outros socios para enriquecer os seus datos de clientes.</span><span class="sxs-lookup"><span data-stu-id="7a0f1-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Páxina da plataforma común de enriquecemento":::

<span data-ttu-id="7a0f1-106">Na información do público, vaia a **Datos** > **Enriquecemento** para traballar con opcións de enriquecemento.</span><span class="sxs-lookup"><span data-stu-id="7a0f1-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>  

<span data-ttu-id="7a0f1-107">Debe ter permisos de colaborador ou administrador para crear ou editar enriquecementos.</span><span class="sxs-lookup"><span data-stu-id="7a0f1-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="7a0f1-108">Para obter máis información, consulte [Permisos](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="7a0f1-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="7a0f1-109">No separador **Descubrir**, atopará os seguintes enriquecementos:</span><span class="sxs-lookup"><span data-stu-id="7a0f1-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="7a0f1-110">[Marcas](enrichment-microsoft.md) fornecidas por Microsoft</span><span class="sxs-lookup"><span data-stu-id="7a0f1-110">[Brands](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="7a0f1-111">[Intereses](enrichment-microsoft.md) fornecidos por Microsoft</span><span class="sxs-lookup"><span data-stu-id="7a0f1-111">[Interests](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="7a0f1-112">[Enderezos mellorados](enrichment-enhanced-addresses.md) fornecidos por Microsoft</span><span class="sxs-lookup"><span data-stu-id="7a0f1-112">[Enhanced addresses](enrichment-enhanced-addresses.md) provided by Microsoft</span></span>
- <span data-ttu-id="7a0f1-113">[Datos da empresa](enrichment-leadspace.md) proporcionados por Leadspace</span><span class="sxs-lookup"><span data-stu-id="7a0f1-113">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="7a0f1-114">[Demografía](enrichment-experian.md) fornecida por Experian</span><span class="sxs-lookup"><span data-stu-id="7a0f1-114">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="7a0f1-115">[Datos de localización](enrichment-here.md) subministrados por HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="7a0f1-115">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="7a0f1-116">[Datos personalizados](enrichment-SFTP-custom-import.md) a través do protocolo seguro de transferencia de ficheiros (SFTP)</span><span class="sxs-lookup"><span data-stu-id="7a0f1-116">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="7a0f1-117">No separador **Os meus enriquecementos**, pode ver os enriquecementos que configurou e editar as súas propiedades.</span><span class="sxs-lookup"><span data-stu-id="7a0f1-117">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="7a0f1-118">Xestionar os enriquecementos existentes</span><span class="sxs-lookup"><span data-stu-id="7a0f1-118">Manage existing enrichments</span></span>

<span data-ttu-id="7a0f1-119">Vaia ao separador **Os meus enriquecementos** para ver todos os enriquecementos configurados.</span><span class="sxs-lookup"><span data-stu-id="7a0f1-119">Go to the **My enrichments** tab to see all configured enrichments.</span></span> <span data-ttu-id="7a0f1-120">Cada enriquecemento represéntase como unha liña que inclúe información adicional sobre o enriquecemento.</span><span class="sxs-lookup"><span data-stu-id="7a0f1-120">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="7a0f1-121">Seleccione un enriquecemento para ver as opcións dispoñibles.</span><span class="sxs-lookup"><span data-stu-id="7a0f1-121">Select an enrichment to see the available options.</span></span> <span data-ttu-id="7a0f1-122">Tamén pode seleccionar os puntos suspensivos (...) nun elemento da lista para ver as opcións.</span><span class="sxs-lookup"><span data-stu-id="7a0f1-122">You can also select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Opcións para xestionar os enriquecementos na lista de enriquecementos":::

- <span data-ttu-id="7a0f1-124">**Ver** detalles do enriquecemento co número de perfís de clientes enriquecidos.</span><span class="sxs-lookup"><span data-stu-id="7a0f1-124">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="7a0f1-125">**Editar** a configuración do enriquecemento.</span><span class="sxs-lookup"><span data-stu-id="7a0f1-125">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="7a0f1-126">**Execute** o enriquecemento para actualizar os perfís dos clientes cos últimos datos.</span><span class="sxs-lookup"><span data-stu-id="7a0f1-126">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="7a0f1-127">**Desactivar** un enriquecemento existente para evitar que se actualice automaticamente con cada actualización programada.</span><span class="sxs-lookup"><span data-stu-id="7a0f1-127">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="7a0f1-128">Os datos da última actualización exitosa seguirán dispoñibles.</span><span class="sxs-lookup"><span data-stu-id="7a0f1-128">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="7a0f1-129">**Activar** un enriquecemento inactivo para reiniciar a actualización automática con cada actualización programada.</span><span class="sxs-lookup"><span data-stu-id="7a0f1-129">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="7a0f1-130">**Eliminar** un enriquecemento.</span><span class="sxs-lookup"><span data-stu-id="7a0f1-130">**Delete** an enrichment.</span></span>

<span data-ttu-id="7a0f1-131">Pode executar ou desactivar varios enriquecementos á vez seleccionándoos na lista.</span><span class="sxs-lookup"><span data-stu-id="7a0f1-131">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="7a0f1-132">As opcións de visualización e edición non están dispoñibles como acción masiva e só funcionan para un enriquecemento á vez.</span><span class="sxs-lookup"><span data-stu-id="7a0f1-132">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>

## <a name="enrichments-and-connections"></a><span data-ttu-id="7a0f1-133">Enriquecementos e conexións</span><span class="sxs-lookup"><span data-stu-id="7a0f1-133">Enrichments and connections</span></span>

<span data-ttu-id="7a0f1-134">Os enriquecementos de terceiros configúranse usando [conexións](connections.md), que un administrador configura con credenciais e proporciona o consentimento para as transferencias de datos.</span><span class="sxs-lookup"><span data-stu-id="7a0f1-134">Third-party enrichments are configured using [connections](connections.md), which an administrator sets up with credentials and provides consent for data transfers.</span></span> <span data-ttu-id="7a0f1-135">A conexión pode ser usada para configurar enriquecementos por administradores e colaboradores.</span><span class="sxs-lookup"><span data-stu-id="7a0f1-135">The connection can be used by administrators and contributors to configure enrichments.</span></span>  

## <a name="multiple-enrichments-of-the-same-type"></a><span data-ttu-id="7a0f1-136">Enriquecementos múltiples do mesmo tipo</span><span class="sxs-lookup"><span data-stu-id="7a0f1-136">Multiple enrichments of the same type</span></span>

<span data-ttu-id="7a0f1-137">A entidade que se vai enriquecer especifícase durante a configuración de enriquecemento, que lle permite enriquecer só un subconxunto dos seus perfís.</span><span class="sxs-lookup"><span data-stu-id="7a0f1-137">The entity to be enriched is specified during the enrichment configuration, which allows you to enrich only a subset of your profiles.</span></span> <span data-ttu-id="7a0f1-138">Por exemplo, enriqueceza datos só para un segmento específico.</span><span class="sxs-lookup"><span data-stu-id="7a0f1-138">For example, enrich data only for a specific segment.</span></span> <span data-ttu-id="7a0f1-139">Pode configurar varios enriquecementos do mesmo tipo e reutilizar a mesma conexión.</span><span class="sxs-lookup"><span data-stu-id="7a0f1-139">You can configure several enrichments of the same type and reuse the same connection.</span></span> <span data-ttu-id="7a0f1-140">Algúns enriquecementos terán límites do número de enriquecementos do mesmo tipo que se poden crear.</span><span class="sxs-lookup"><span data-stu-id="7a0f1-140">Some enrichments will have limits to the number of enrichments of the same type that can be created.</span></span> <span data-ttu-id="7a0f1-141">Os límites e o uso actual pódense ver na páxina **Enriquecemento**.</span><span class="sxs-lookup"><span data-stu-id="7a0f1-141">The limits and current use can be seen on the **Enrichment** page.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
