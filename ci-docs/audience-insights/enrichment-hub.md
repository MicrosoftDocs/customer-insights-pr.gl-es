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
ms.openlocfilehash: 10c338b89a6f9971912d05986c105cba1221b01b
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896003"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="c2a1d-103">Enriquecemento dos perfís de clientes (vista previa)</span><span class="sxs-lookup"><span data-stu-id="c2a1d-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="c2a1d-104">Use datos de fontes como Microsoft e outros socios para enriquecer os seus datos de clientes.</span><span class="sxs-lookup"><span data-stu-id="c2a1d-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Páxina da plataforma común de enriquecemento":::

<span data-ttu-id="c2a1d-106">Na información do público, vaia a **Datos** > **Enriquecemento** para traballar con opcións de enriquecemento.</span><span class="sxs-lookup"><span data-stu-id="c2a1d-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>    
<span data-ttu-id="c2a1d-107">Debe ter permisos de colaborador ou administrador para crear ou editar enriquecementos.</span><span class="sxs-lookup"><span data-stu-id="c2a1d-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="c2a1d-108">Para obter máis información, consulte [Permisos](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="c2a1d-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="c2a1d-109">No separador **Descubrir**, atopará os seguintes enriquecementos:</span><span class="sxs-lookup"><span data-stu-id="c2a1d-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="c2a1d-110">[Marcas](enrichment-microsoft.md) fornecidas por Microsoft</span><span class="sxs-lookup"><span data-stu-id="c2a1d-110">[Brands](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="c2a1d-111">[Intereses](enrichment-microsoft.md) fornecidos por Microsoft</span><span class="sxs-lookup"><span data-stu-id="c2a1d-111">[Interests](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="c2a1d-112">[Datos da empresa](enrichment-leadspace.md) proporcionados por Leadspace</span><span class="sxs-lookup"><span data-stu-id="c2a1d-112">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="c2a1d-113">[Datos demográficos](enrichment-experian.md) proporcionados por Experian</span><span class="sxs-lookup"><span data-stu-id="c2a1d-113">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="c2a1d-114">[Datos de localización](enrichment-here.md) subministrados por HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="c2a1d-114">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="c2a1d-115">[Datos personalizados](enrichment-SFTP-custom-import.md) a través do protocolo seguro de transferencia de ficheiros (SFTP)</span><span class="sxs-lookup"><span data-stu-id="c2a1d-115">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="c2a1d-116">No separador **Os meus enriquecementos**, pode ver os enriquecementos que configurou e editar as súas propiedades.</span><span class="sxs-lookup"><span data-stu-id="c2a1d-116">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="c2a1d-117">Xestionar os enriquecementos existentes</span><span class="sxs-lookup"><span data-stu-id="c2a1d-117">Manage existing enrichments</span></span>

<span data-ttu-id="c2a1d-118">Vaia a **Os meus enriquecementos** para ver todos os enriquecementos configurados.</span><span class="sxs-lookup"><span data-stu-id="c2a1d-118">Go to the **My enrichments** to see all configured enrichments.</span></span> <span data-ttu-id="c2a1d-119">Cada enriquecemento represéntase como unha liña que inclúe información adicional sobre o enriquecemento.</span><span class="sxs-lookup"><span data-stu-id="c2a1d-119">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="c2a1d-120">Seleccione un enriquecemento para ver as opcións dispoñibles.</span><span class="sxs-lookup"><span data-stu-id="c2a1d-120">Select an enrichment to see the available options.</span></span> <span data-ttu-id="c2a1d-121">Tamén pode seleccionar os puntos suspensivos (...) nun elemento da lista para ver as opcións.</span><span class="sxs-lookup"><span data-stu-id="c2a1d-121">You can also select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Opcións para xestionar os enriquecementos na lista de enriquecementos":::

- <span data-ttu-id="c2a1d-123">**Ver** detalles do enriquecemento co número de perfís de clientes enriquecidos.</span><span class="sxs-lookup"><span data-stu-id="c2a1d-123">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="c2a1d-124">**Editar** a configuración do enriquecemento.</span><span class="sxs-lookup"><span data-stu-id="c2a1d-124">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="c2a1d-125">**Execute** o enriquecemento para actualizar os perfís dos clientes cos últimos datos.</span><span class="sxs-lookup"><span data-stu-id="c2a1d-125">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="c2a1d-126">**Desactivar** un enriquecemento existente para evitar que se actualice automaticamente con cada actualización programada.</span><span class="sxs-lookup"><span data-stu-id="c2a1d-126">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="c2a1d-127">Os datos da última actualización exitosa seguirán dispoñibles.</span><span class="sxs-lookup"><span data-stu-id="c2a1d-127">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="c2a1d-128">**Activar** un enriquecemento inactivo para reiniciar a actualización automática con cada actualización programada.</span><span class="sxs-lookup"><span data-stu-id="c2a1d-128">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="c2a1d-129">**Eliminar** un enriquecemento.</span><span class="sxs-lookup"><span data-stu-id="c2a1d-129">**Delete** an enrichment.</span></span>

<span data-ttu-id="c2a1d-130">Pode executar ou desactivar varios enriquecementos á vez seleccionándoos na lista.</span><span class="sxs-lookup"><span data-stu-id="c2a1d-130">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="c2a1d-131">As opcións de visualización e edición non están dispoñibles como acción masiva e só funcionan para un enriquecemento á vez.</span><span class="sxs-lookup"><span data-stu-id="c2a1d-131">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>

## <a name="enrichments-and-connections"></a><span data-ttu-id="c2a1d-132">Enriquecementos e conexións</span><span class="sxs-lookup"><span data-stu-id="c2a1d-132">Enrichments and connections</span></span>

<span data-ttu-id="c2a1d-133">Os enriquecementos de terceiros configúranse usando [conexións](connections.md), que un administrador configura con credenciais e proporciona o consentimento para as transferencias de datos.</span><span class="sxs-lookup"><span data-stu-id="c2a1d-133">Third-party enrichments are configured using [connections](connections.md), which an administrator sets up with credentials and provides consent for data transfers.</span></span> <span data-ttu-id="c2a1d-134">A conexión pode ser usada para configurar enriquecementos por administradores e colaboradores.</span><span class="sxs-lookup"><span data-stu-id="c2a1d-134">The connection can be used by administrators and contributors to configure enrichments.</span></span>  

## <a name="multiple-enrichments-of-the-same-type"></a><span data-ttu-id="c2a1d-135">Enriquecementos múltiples do mesmo tipo</span><span class="sxs-lookup"><span data-stu-id="c2a1d-135">Multiple enrichments of the same type</span></span>

<span data-ttu-id="c2a1d-136">A entidade que se vai enriquecer especifícase durante a configuración de enriquecemento, que lle permite enriquecer só un subconxunto dos seus perfís.</span><span class="sxs-lookup"><span data-stu-id="c2a1d-136">The entity to be enriched is specified during the enrichment configuration, which allows you to enrich only a subset of your profiles.</span></span> <span data-ttu-id="c2a1d-137">Por exemplo, enriqueza os datos só dun segmento específico.</span><span class="sxs-lookup"><span data-stu-id="c2a1d-137">For exmaple, enrich data only for a specific segment.</span></span> <span data-ttu-id="c2a1d-138">Pode configurar varios enriquecementos do mesmo tipo e reutilizar a mesma conexión.</span><span class="sxs-lookup"><span data-stu-id="c2a1d-138">You can configure several enrichments of the same type and reuse the same connection.</span></span> <span data-ttu-id="c2a1d-139">Algúns enriquecementos terán límites do número de enriquecementos do mesmo tipo que se poden crear.</span><span class="sxs-lookup"><span data-stu-id="c2a1d-139">Some enrichments will have limits to the number of enrichments of the same type that can be created.</span></span> <span data-ttu-id="c2a1d-140">Os límites e o uso actual pódense ver na páxina **Enriquecemento**.</span><span class="sxs-lookup"><span data-stu-id="c2a1d-140">The limits and current use can be seen on the **Enrichment** page.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
