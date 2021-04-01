---
title: Conectar cunha conta de Azure Data Lake Storage Gen2 cunha entidade de seguranza do servizo
description: Use unha entidade de seguranza do servizo de Azure para obter información sobre a audiencia para conectarse ao seu propio lago de datos ao anexalo á información sobre a audiencia.
ms.date: 02/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: c670b0065a2833a6dc311d9e86d2b351140382ce
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596497"
---
# <a name="connect-to-an-azure-data-lake-storage-gen2-account-with-an-azure-service-principal-for-audience-insights"></a><span data-ttu-id="2208a-103">Conectarse a unha conta de Azure Data Lake Storage Gen2 cunha entidade principal de seguranza do servizo de Azure para obter información sobre o público</span><span class="sxs-lookup"><span data-stu-id="2208a-103">Connect to an Azure Data Lake Storage Gen2 account with an Azure service principal for audience insights</span></span>

<span data-ttu-id="2208a-104">As ferramentas automatizadas que utilizan servizos de Azure sempre deben ter permisos restrinxidos.</span><span class="sxs-lookup"><span data-stu-id="2208a-104">Automated tools that use Azure services should always have restricted permissions.</span></span> <span data-ttu-id="2208a-105">En lugar de ter aplicacións iniciadas como un usuario totalmente privilexiado, Azure ofrece entidades de seguranza do servizo.</span><span class="sxs-lookup"><span data-stu-id="2208a-105">Instead of having applications sign in as a fully privileged user, Azure offers service principals.</span></span> <span data-ttu-id="2208a-106">Siga a ler para aprender a conectar as estatísticas do público cunha conta de Azure Data Lake Storage Gen2 usando unha entidade de seguranza do servizo de Azure en lugar de claves da conta de almacenamento.</span><span class="sxs-lookup"><span data-stu-id="2208a-106">Read on to learn how to connect audience insights with an Azure Data Lake Storage Gen2 account using an Azure service principal instead of storage account keys.</span></span> 

<span data-ttu-id="2208a-107">Pode usar a entidade de seguranza do servizo para, de forma segura, [engadir ou editar un cartafol de Common Data Model como orixe de datos](connect-common-data-model.md) ou [crear un novo ambiente ou actualizar un existente](manage-environments.md#create-an-environment-in-an-existing-organization).</span><span class="sxs-lookup"><span data-stu-id="2208a-107">You can use the service principal to securely [add or edit a Common Data Model folder as a data source](connect-common-data-model.md) or [create a new or update an existing environment](manage-environments.md#create-an-environment-in-an-existing-organization).</span></span>

> [!IMPORTANT]
> - <span data-ttu-id="2208a-108">A conta de almacenamento de Azure Data Lake Gen2 que pretenda utilizar a entidade de seguranza do servizo debe ter o [Espazo de nomes xerárquicos (HNS) activado](/azure/storage/blobs/data-lake-storage-namespace).</span><span class="sxs-lookup"><span data-stu-id="2208a-108">The Azure Data Lake Gen2 storage account that intends to use the service principal must have [Hierarchical Name Space (HNS) enabled](/azure/storage/blobs/data-lake-storage-namespace).</span></span>
> - <span data-ttu-id="2208a-109">Precisa permisos de administrador para a súa subscrición a Azure para crear a entidade de seguranza do servizo.</span><span class="sxs-lookup"><span data-stu-id="2208a-109">You need admin permissions for your Azure subscription to create the service principal.</span></span>

## <a name="create-azure-service-principal-for-audience-insights"></a><span data-ttu-id="2208a-110">Crear a entidade de seguranza do servizo de Azure para obter información sobre o público</span><span class="sxs-lookup"><span data-stu-id="2208a-110">Create Azure service principal for audience insights</span></span>

<span data-ttu-id="2208a-111">Antes de crear unha nova entidade de seguranza do servizo para obter información sobre o público, comprobe se xa existe na súa organización.</span><span class="sxs-lookup"><span data-stu-id="2208a-111">Before creating a new service principal for audience insights, check if it already exists in your organization.</span></span>

### <a name="look-for-an-existing-service-principal"></a><span data-ttu-id="2208a-112">Buscar unha entidade de seguranza do servizo existente</span><span class="sxs-lookup"><span data-stu-id="2208a-112">Look for an existing service principal</span></span>

1. <span data-ttu-id="2208a-113">Vaia ao [Portal de administración de Azure](https://portal.azure.com) e inicie sesión na súa organización.</span><span class="sxs-lookup"><span data-stu-id="2208a-113">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

2. <span data-ttu-id="2208a-114">Seleccione **Azure Active Directory** dos servizos de Azure.</span><span class="sxs-lookup"><span data-stu-id="2208a-114">Select **Azure Active Directory** from the Azure services.</span></span>

3. <span data-ttu-id="2208a-115">En **Xestionar**, seleccione **Aplicacións empresariais**.</span><span class="sxs-lookup"><span data-stu-id="2208a-115">Under **Manage**, select **Enterprise Applications**.</span></span>

4. <span data-ttu-id="2208a-116">Busque o ID da aplicación interna de información sobre o público `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` ou o nome `Dynamics 365 AI for Customer Insights`.</span><span class="sxs-lookup"><span data-stu-id="2208a-116">Search for the audience insights first party application ID `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` or the name `Dynamics 365 AI for Customer Insights`.</span></span>

5. <span data-ttu-id="2208a-117">Se atopa un rexistro coincidente, significa que existe a entidade de seguranza do servizo de información sobre o público.</span><span class="sxs-lookup"><span data-stu-id="2208a-117">If you find a matching record, it means that the service principal for audience insights exists.</span></span> <span data-ttu-id="2208a-118">Non é necesario volvela crear.</span><span class="sxs-lookup"><span data-stu-id="2208a-118">You don't need to create it again.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Captura de pantalla que mostra a entidade de seguranza do servizo existente.":::
   
6. <span data-ttu-id="2208a-120">Se non se devolven resultados, cree unha nova entidade de seguranza do servizo.</span><span class="sxs-lookup"><span data-stu-id="2208a-120">If no results are returned, create a new service principal.</span></span>

### <a name="create-a-new-service-principal"></a><span data-ttu-id="2208a-121">Crear unha entidade de seguranza do servizo nova</span><span class="sxs-lookup"><span data-stu-id="2208a-121">Create a new service principal</span></span>

1. <span data-ttu-id="2208a-122">Instale a última versión de **Azure Active Directory PowerShell para Graph**.</span><span class="sxs-lookup"><span data-stu-id="2208a-122">Install the latest version of the **Azure Active Directory PowerShell for Graph**.</span></span> <span data-ttu-id="2208a-123">Para obter máis información, consulte [Instalar Azure Active Directory PowerShell para Graph](/powershell/azure/active-directory/install-adv2).</span><span class="sxs-lookup"><span data-stu-id="2208a-123">For more information, see [Install Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).</span></span>
   - <span data-ttu-id="2208a-124">No seu PC, seleccione a tecla Windows do teclado e busque **Windows PowerShell** e **Executar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="2208a-124">On your PC, select the Windows key on your keyboard and search for **Windows PowerShell** and **Run as Administrator**.</span></span>
   
   - <span data-ttu-id="2208a-125">Na xanela de PowerShell que se abre, introduza `Install-Module AzureAD`.</span><span class="sxs-lookup"><span data-stu-id="2208a-125">In the PowerShell window that opens, enter `Install-Module AzureAD`.</span></span>

2. <span data-ttu-id="2208a-126">Cree a entidade de seguranza do servizo para obter información sobre o público co módulo Azure AD PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2208a-126">Create the  service principal for audience insights with the Azure AD PowerShell Module.</span></span>
   - <span data-ttu-id="2208a-127">Na xanela de PowerShell que se abre, introduza `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span><span class="sxs-lookup"><span data-stu-id="2208a-127">In the PowerShell window, enter `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span></span> <span data-ttu-id="2208a-128">Substitúa "o seu identificador de arrendatario" polo ID real do seu arrendatario onde desexa crear a entidade de seguranza do servizo.</span><span class="sxs-lookup"><span data-stu-id="2208a-128">Replace “your tenant ID” with the actual ID of your tenant where you want to create the service principal.</span></span> <span data-ttu-id="2208a-129">O parámetro de nome do ambiente `AzureEnvironmentName` é opcional.</span><span class="sxs-lookup"><span data-stu-id="2208a-129">The environment name parameter `AzureEnvironmentName` is optional.</span></span>
  
   - <span data-ttu-id="2208a-130">Introduza `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span><span class="sxs-lookup"><span data-stu-id="2208a-130">Enter `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span></span> <span data-ttu-id="2208a-131">Este comando crea a entidade de seguranza do servizo para obter información sobre o público no inquilino seleccionado.</span><span class="sxs-lookup"><span data-stu-id="2208a-131">This command creates the service principal for audience insights on the selected tenant.</span></span>  

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a><span data-ttu-id="2208a-132">Conceder permisos á entidade de seguranza do servizo para acceder á conta de almacenamento</span><span class="sxs-lookup"><span data-stu-id="2208a-132">Grant permissions to the service principal to access the storage account</span></span>

<span data-ttu-id="2208a-133">Vaia ao portal de Azure para conceder permisos á entidade de seguranza do servizo para a conta de almacenamento que desexa empregar para a información da audiencia.</span><span class="sxs-lookup"><span data-stu-id="2208a-133">Go to the Azure portal to grant permissions to the service principal for the storage account you want to use in audience insights.</span></span>

1. <span data-ttu-id="2208a-134">Vaia ao [Portal de administración de Azure](https://portal.azure.com) e inicie sesión na súa organización.</span><span class="sxs-lookup"><span data-stu-id="2208a-134">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

1. <span data-ttu-id="2208a-135">Abra a conta de almacenamento á que desexa que teña acceso a entidade de seguranza do servizo para que teña acceso a información sobre o público.</span><span class="sxs-lookup"><span data-stu-id="2208a-135">Open the storage account you want the service principal for audience insights to have access to.</span></span>

1. <span data-ttu-id="2208a-136">Seleccione **Control de acceso (IAM)** no panel de navegación e seleccione **Engadir** > **Engadir asignación de funcións**.</span><span class="sxs-lookup"><span data-stu-id="2208a-136">Select **Access control (IAM)** from the navigation pane and select **Add** > **Add role assignment**.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Captura de pantalla que mostra o portal de Azure mentres se engade unha asignación de funcións.":::
   
1. <span data-ttu-id="2208a-138">No panel **Engadir asignación de funcións**, estableza as seguintes propiedades:</span><span class="sxs-lookup"><span data-stu-id="2208a-138">In the **Add role assignment** pane, set the following properties:</span></span>
   - <span data-ttu-id="2208a-139">Función: *Colaborador de datos do BLOB de almacenamento*</span><span class="sxs-lookup"><span data-stu-id="2208a-139">Role: *Storage Blob Data Contributor*</span></span>
   - <span data-ttu-id="2208a-140">Asignar acceso a: *Usuario, grupo ou entidade de seguranza do servizo*</span><span class="sxs-lookup"><span data-stu-id="2208a-140">Assign access to: *User, group, or service principal*</span></span>
   - <span data-ttu-id="2208a-141">Seleccione: *Dynamics 365 AI for Customer Insights* (a [entidade de seguranza do servizo que creou](#create-a-new-service-principal))</span><span class="sxs-lookup"><span data-stu-id="2208a-141">Select: *Dynamics 365 AI for Customer Insights* (the [service principal you created](#create-a-new-service-principal))</span></span>

1.  <span data-ttu-id="2208a-142">Seleccione **Gardar**.</span><span class="sxs-lookup"><span data-stu-id="2208a-142">Select **Save**.</span></span>

<span data-ttu-id="2208a-143">Pode tardar ata 15 minutos en propagar os cambios.</span><span class="sxs-lookup"><span data-stu-id="2208a-143">It can take up to 15 minutes to propagate the changes.</span></span>

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a><span data-ttu-id="2208a-144">Introduza o ID de recurso de Azure ou os detalles da subscrición a Azure no anexo da conta de almacenamento para a información do público.</span><span class="sxs-lookup"><span data-stu-id="2208a-144">Enter the Azure Resource ID or the Azure Subscription details in the storage account attachment to Audience Insights.</span></span>

<span data-ttu-id="2208a-145">Anexe unha conta de almacenamento de Azure Data Lake na información sobre a audiencia para [almacenar datos de saída](manage-environments.md) ou [úsea como orixe de datos](connect-common-data-service-lake.md).</span><span class="sxs-lookup"><span data-stu-id="2208a-145">Attach an Azure Data Lake storage account in audience insights to [store output data](manage-environments.md) or [use it as a data source](connect-common-data-service-lake.md).</span></span> <span data-ttu-id="2208a-146">Escoller a opción Azure Data Lake permítelle escoller entre un enfoque baseado en recursos ou baseado nunha subscrición.</span><span class="sxs-lookup"><span data-stu-id="2208a-146">Choosing the Azure Data Lake option lets you choose between a resource-based or a subscription-based based approach.</span></span>

<span data-ttu-id="2208a-147">Siga os pasos seguintes para proporcionar a información requirida sobre o enfoque seleccionado.</span><span class="sxs-lookup"><span data-stu-id="2208a-147">Follow the below steps to provide the required information on the selected approach.</span></span>

### <a name="resource-based-storage-account-connection"></a><span data-ttu-id="2208a-148">Conexión de conta de almacenamento baseada en recursos</span><span class="sxs-lookup"><span data-stu-id="2208a-148">Resource-based storage account connection</span></span>

1. <span data-ttu-id="2208a-149">Vaia ao [Portal de administración de Azure](https://portal.azure.com), inicie sesión na súa subscrición e abra a conta de almacenamento.</span><span class="sxs-lookup"><span data-stu-id="2208a-149">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="2208a-150">Vaia a **Configuración** > **Propiedades** no panel de navegación.</span><span class="sxs-lookup"><span data-stu-id="2208a-150">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="2208a-151">Copie o valor do ID do recurso da conta de almacenamento.</span><span class="sxs-lookup"><span data-stu-id="2208a-151">Copy the storage account resource ID value.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Copie o ID do recurso da conta de almacenamento.":::

1. <span data-ttu-id="2208a-153">En estatísticas de audiencia, insira o ID do recurso no campo do recurso mostrado na pantalla de conexión da conta de almacenamento.</span><span class="sxs-lookup"><span data-stu-id="2208a-153">In audience insights, insert the resource ID in the resource field displayed in the storage account connection screen.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Insira a información do ID do recurso da conta de almacenamento.":::   
   
1. <span data-ttu-id="2208a-155">Continúe cos pasos restantes nas estatísticas do público para anexar a conta de almacenamento.</span><span class="sxs-lookup"><span data-stu-id="2208a-155">Continue with the remaining steps in audience insights to attach the storage account.</span></span>

### <a name="subscription-based-storage-account-connection"></a><span data-ttu-id="2208a-156">Conexión de conta de almacenamento baseada na subscrición</span><span class="sxs-lookup"><span data-stu-id="2208a-156">Subscription-based storage account connection</span></span>

1. <span data-ttu-id="2208a-157">Vaia ao [Portal de administración de Azure](https://portal.azure.com), inicie sesión na súa subscrición e abra a conta de almacenamento.</span><span class="sxs-lookup"><span data-stu-id="2208a-157">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="2208a-158">Vaia a **Configuración** > **Propiedades** no panel de navegación.</span><span class="sxs-lookup"><span data-stu-id="2208a-158">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="2208a-159">Revise a **Subscrición**, o **Grupo de recursos** e o **Nome** da conta de almacenamento para asegurarse de que selecciona os valores correctos nas estatísticas do público.</span><span class="sxs-lookup"><span data-stu-id="2208a-159">Review the **Subscription**, **Resource group**, and the **Name** of the storage account to make sure you select the right values in audience insights.</span></span>

1. <span data-ttu-id="2208a-160">En estatísticas de audiencia, escolla os valores ou os campos correspondentes ao anexar a conta de almacenamento.</span><span class="sxs-lookup"><span data-stu-id="2208a-160">In audience insights, choose the values or for the corresponding fields when attaching the storage account.</span></span>
   
1. <span data-ttu-id="2208a-161">Continúe cos pasos restantes nas estatísticas do público para anexar a conta de almacenamento.</span><span class="sxs-lookup"><span data-stu-id="2208a-161">Continue with the remaining steps in audience insights to attach the storage account.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]