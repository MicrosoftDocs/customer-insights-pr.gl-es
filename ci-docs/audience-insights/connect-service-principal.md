---
title: Conectar cunha conta de Azure Data Lake Storage Gen2 cunha entidade de seguranza do servizo
description: Use unha entidade de seguranza do servizo de Azure para obter información sobre a audiencia para conectarse ao seu propio lago de datos ao anexalo á información sobre a audiencia.
ms.date: 11/24/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: c2fae278d34fa02b9168ac70dfa8dd351653245e
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644086"
---
# <a name="connect-to-an-azure-data-lake-storage-gen2-account-with-an-azure-service-principal-for-audience-insights"></a><span data-ttu-id="a9fd3-103">Conectarse a unha conta de Azure Data Lake Storage Gen2 cunha entidade principal de seguranza do servizo de Azure para obter información sobre o público</span><span class="sxs-lookup"><span data-stu-id="a9fd3-103">Connect to an Azure Data Lake Storage Gen2 account with an Azure service principal for audience insights</span></span>

<span data-ttu-id="a9fd3-104">As ferramentas automatizadas que utilizan servizos de Azure sempre deben ter permisos restrinxidos.</span><span class="sxs-lookup"><span data-stu-id="a9fd3-104">Automated tools that use Azure services should always have restricted permissions.</span></span> <span data-ttu-id="a9fd3-105">En lugar de ter aplicacións iniciadas como un usuario totalmente privilexiado, Azure ofrece entidades de seguranza do servizo.</span><span class="sxs-lookup"><span data-stu-id="a9fd3-105">Instead of having applications sign in as a fully privileged user, Azure offers service principals.</span></span> <span data-ttu-id="a9fd3-106">Siga a ler para aprender a conectar as estatísticas do público cunha conta de Azure Data Lake Storage Gen2 usando unha entidade de seguranza do servizo de Azure en lugar de claves da conta de almacenamento.</span><span class="sxs-lookup"><span data-stu-id="a9fd3-106">Read on to learn how to connect audience insights with an Azure Data Lake Storage Gen2 account using an Azure service principal instead of storage account keys.</span></span> 

<span data-ttu-id="a9fd3-107">Pode usar a entidade de seguranza do servizo para, de forma segura, [engadir ou editar un cartafol de Common Data Model como orixe de datos](connect-common-data-model.md) ou [crear un novo ambiente ou actualizar un existente](manage-environments.md#create-an-environment-in-an-existing-organization).</span><span class="sxs-lookup"><span data-stu-id="a9fd3-107">You can use the service principal to securely [add or edit a Common Data Model folder as a data source](connect-common-data-model.md) or [create a new or update an existing environment](manage-environments.md#create-an-environment-in-an-existing-organization).</span></span>

<span data-ttu-id="a9fd3-108">Precisa permisos de administrador para a súa subscrición a Azure para crear a entidade de seguranza do servizo.</span><span class="sxs-lookup"><span data-stu-id="a9fd3-108">You need admin permissions for your Azure subscription to create the service principal.</span></span>

## <a name="create-azure-service-principal-for-audience-insights"></a><span data-ttu-id="a9fd3-109">Crear a entidade de seguranza do servizo de Azure para obter información sobre o público</span><span class="sxs-lookup"><span data-stu-id="a9fd3-109">Create Azure service principal for audience insights</span></span>

<span data-ttu-id="a9fd3-110">Antes de crear unha nova entidade de seguranza do servizo para obter información sobre o público, comprobe se xa existe na súa organización.</span><span class="sxs-lookup"><span data-stu-id="a9fd3-110">Before creating a new service principal for audience insights, check if it already exists in your organization.</span></span>

### <a name="look-for-an-existing-service-principal"></a><span data-ttu-id="a9fd3-111">Buscar unha entidade de seguranza do servizo existente</span><span class="sxs-lookup"><span data-stu-id="a9fd3-111">Look for an existing service principal</span></span>

1. <span data-ttu-id="a9fd3-112">Vaia ao [Portal de administración de Azure](https://portal.azure.com) e inicie sesión na súa organización.</span><span class="sxs-lookup"><span data-stu-id="a9fd3-112">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

2. <span data-ttu-id="a9fd3-113">Seleccione **Azure Active Directory** dos servizos de Azure.</span><span class="sxs-lookup"><span data-stu-id="a9fd3-113">Select **Azure Active Directory** from the Azure services.</span></span>

3. <span data-ttu-id="a9fd3-114">En **Xestionar**, seleccione **Aplicacións empresariais**.</span><span class="sxs-lookup"><span data-stu-id="a9fd3-114">Under **Manage**, select **Enterprise Applications**.</span></span>

4. <span data-ttu-id="a9fd3-115">Busque o ID da aplicación interna de información sobre o público `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` ou o nome `Dynamics 365 AI for Customer Insights`.</span><span class="sxs-lookup"><span data-stu-id="a9fd3-115">Search for the audience insights first party application ID `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` or the name `Dynamics 365 AI for Customer Insights`.</span></span>

5. <span data-ttu-id="a9fd3-116">Se atopa un rexistro coincidente, significa que existe a entidade de seguranza do servizo de información sobre o público.</span><span class="sxs-lookup"><span data-stu-id="a9fd3-116">If you find a matching record, it means that the service principal for audience insights exists.</span></span> <span data-ttu-id="a9fd3-117">Non é necesario volvela crear.</span><span class="sxs-lookup"><span data-stu-id="a9fd3-117">You don't need to create it again.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Captura de pantalla que mostra a entidade de seguranza do servizo existente.":::
   
6. <span data-ttu-id="a9fd3-119">Se non se devolven resultados, cree unha nova entidade de seguranza do servizo.</span><span class="sxs-lookup"><span data-stu-id="a9fd3-119">If no results are returned, create a new service principal.</span></span>

### <a name="create-a-new-service-principal"></a><span data-ttu-id="a9fd3-120">Crear unha entidade de seguranza do servizo nova</span><span class="sxs-lookup"><span data-stu-id="a9fd3-120">Create a new service principal</span></span>

1. <span data-ttu-id="a9fd3-121">Instale a última versión de **Azure Active Directory PowerShell para Graph**.</span><span class="sxs-lookup"><span data-stu-id="a9fd3-121">Install the latest version of the **Azure Active Directory PowerShell for Graph**.</span></span> <span data-ttu-id="a9fd3-122">Para obter máis información, consulte [Instalar Azure Active Directory PowerShell para Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).</span><span class="sxs-lookup"><span data-stu-id="a9fd3-122">For more information, see [Install Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).</span></span>
   - <span data-ttu-id="a9fd3-123">No seu PC, seleccione a tecla Windows do teclado e busque **Windows PowerShell** e **Executar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="a9fd3-123">On your PC, select the Windows key on your keyboard and search for **Windows PowerShell** and **Run as Administrator**.</span></span>
   
   - <span data-ttu-id="a9fd3-124">Na xanela de PowerShell que se abre, introduza `Install-Module AzureAD`.</span><span class="sxs-lookup"><span data-stu-id="a9fd3-124">In the PowerShell window that opens, enter `Install-Module AzureAD`.</span></span>

2. <span data-ttu-id="a9fd3-125">Cree a entidade de seguranza do servizo para obter información sobre o público co módulo Azure AD PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a9fd3-125">Create the  service principal for audience insights with the Azure AD PowerShell Module.</span></span>
   - <span data-ttu-id="a9fd3-126">Na xanela de PowerShell que se abre, introduza `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span><span class="sxs-lookup"><span data-stu-id="a9fd3-126">In the PowerShell window, enter `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span></span> <span data-ttu-id="a9fd3-127">Substitúa "o seu identificador de arrendatario" polo ID real do seu arrendatario onde desexa crear a entidade de seguranza do servizo.</span><span class="sxs-lookup"><span data-stu-id="a9fd3-127">Replace “your tenant ID” with the actual ID of your tenant where you want to create the service principal.</span></span> <span data-ttu-id="a9fd3-128">O parámetro de nome do ambiente `AzureEnvironmentName` é opcional.</span><span class="sxs-lookup"><span data-stu-id="a9fd3-128">The environment name parameter `AzureEnvironmentName` is optional.</span></span>
  
   - <span data-ttu-id="a9fd3-129">Introduza `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span><span class="sxs-lookup"><span data-stu-id="a9fd3-129">Enter `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span></span> <span data-ttu-id="a9fd3-130">Este comando crea a entidade de seguranza do servizo para obter información sobre o público no inquilino seleccionado.</span><span class="sxs-lookup"><span data-stu-id="a9fd3-130">This command creates the service principal for audience insights on the selected tenant.</span></span>  

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a><span data-ttu-id="a9fd3-131">Conceder permisos á entidade de seguranza do servizo para acceder á conta de almacenamento</span><span class="sxs-lookup"><span data-stu-id="a9fd3-131">Grant permissions to the service principal to access the storage account</span></span>

<span data-ttu-id="a9fd3-132">Vaia ao portal de Azure para conceder permisos á entidade de seguranza do servizo para a conta de almacenamento que desexa empregar para a información da audiencia.</span><span class="sxs-lookup"><span data-stu-id="a9fd3-132">Go to the Azure portal to grant permissions to the service principal for the storage account you want to use in audience insights.</span></span>

1. <span data-ttu-id="a9fd3-133">Vaia ao [Portal de administración de Azure](https://portal.azure.com) e inicie sesión na súa organización.</span><span class="sxs-lookup"><span data-stu-id="a9fd3-133">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

1. <span data-ttu-id="a9fd3-134">Abra a conta de almacenamento á que desexa que teña acceso a entidade de seguranza do servizo para que teña acceso a información sobre o público.</span><span class="sxs-lookup"><span data-stu-id="a9fd3-134">Open the storage account you want the service principal for audience insights to have access to.</span></span>

1. <span data-ttu-id="a9fd3-135">Seleccione **Control de acceso (IAM)** no panel de navegación e seleccione **Engadir** > **Engadir asignación de funcións**.</span><span class="sxs-lookup"><span data-stu-id="a9fd3-135">Select **Access control (IAM)** from the navigation pane and select **Add** > **Add role assignment**.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Captura de pantalla que mostra o portal de Azure mentres se engade unha asignación de funcións.":::
   
1. <span data-ttu-id="a9fd3-137">No panel **Engadir asignación de funcións**, estableza as seguintes propiedades:</span><span class="sxs-lookup"><span data-stu-id="a9fd3-137">In the **Add role assignment** pane, set the following properties:</span></span>
   - <span data-ttu-id="a9fd3-138">Función: *Colaborador de datos do BLOB de almacenamento*</span><span class="sxs-lookup"><span data-stu-id="a9fd3-138">Role: *Storage Blob Data Contributor*</span></span>
   - <span data-ttu-id="a9fd3-139">Asignar acceso a: *Usuario, grupo ou entidade de seguranza do servizo*</span><span class="sxs-lookup"><span data-stu-id="a9fd3-139">Assign access to: *User, group, or service principal*</span></span>
   - <span data-ttu-id="a9fd3-140">Seleccione: *Dynamics 365 AI for Customer Insights* (a [entidade de seguranza do servizo que creou](#create-a-new-service-principal))</span><span class="sxs-lookup"><span data-stu-id="a9fd3-140">Select: *Dynamics 365 AI for Customer Insights* (the [service principal you created](#create-a-new-service-principal))</span></span>

1.  <span data-ttu-id="a9fd3-141">Seleccione **Gardar**.</span><span class="sxs-lookup"><span data-stu-id="a9fd3-141">Select **Save**.</span></span>

<span data-ttu-id="a9fd3-142">Pode tardar ata 15 minutos en propagar os cambios.</span><span class="sxs-lookup"><span data-stu-id="a9fd3-142">It can take up to 15 minutes to propagate the changes.</span></span>

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a><span data-ttu-id="a9fd3-143">Introduza o ID de recurso de Azure ou os detalles da subscrición a Azure no anexo da conta de almacenamento para a información do público.</span><span class="sxs-lookup"><span data-stu-id="a9fd3-143">Enter the Azure Resource ID or the Azure Subscription details in the storage account attachment to Audience Insights.</span></span>

<span data-ttu-id="a9fd3-144">Anexe unha conta de almacenamento de Azure Data Lake na información sobre a audiencia para [almacenar datos de saída](manage-environments.md) ou [úsea como orixe de datos](connect-common-data-service-lake.md).</span><span class="sxs-lookup"><span data-stu-id="a9fd3-144">Attach an Azure Data Lake storage account in audience insights to [store output data](manage-environments.md) or [use it as a data source](connect-common-data-service-lake.md).</span></span> <span data-ttu-id="a9fd3-145">Escoller a opción Azure Data Lake permítelle escoller entre un enfoque baseado en recursos ou baseado nunha subscrición.</span><span class="sxs-lookup"><span data-stu-id="a9fd3-145">Choosing the Azure Data Lake option lets you choose between a resource-based or a subscription-based based approach.</span></span>

<span data-ttu-id="a9fd3-146">Siga os pasos seguintes para proporcionar a información requirida sobre o enfoque seleccionado.</span><span class="sxs-lookup"><span data-stu-id="a9fd3-146">Follow the below steps to provide the required information on the selected approach.</span></span>

### <a name="resounce-based-storage-account-connection"></a><span data-ttu-id="a9fd3-147">Conexión de conta de almacenamento baseada en recursos</span><span class="sxs-lookup"><span data-stu-id="a9fd3-147">Resounce-based storage account connection</span></span>

1. <span data-ttu-id="a9fd3-148">Vaia ao [Portal de administración de Azure](https://portal.azure.com), inicie sesión na súa subscrición e abra a conta de almacenamento.</span><span class="sxs-lookup"><span data-stu-id="a9fd3-148">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="a9fd3-149">Vaia a **Configuración** > **Propiedades** no panel de navegación.</span><span class="sxs-lookup"><span data-stu-id="a9fd3-149">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="a9fd3-150">Copie o valor do ID do recurso da conta de almacenamento.</span><span class="sxs-lookup"><span data-stu-id="a9fd3-150">Copy the storage account resource ID value.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Copie o ID do recurso da conta de almacenamento.":::

1. <span data-ttu-id="a9fd3-152">En estatísticas de audiencia, insira o ID do recurso no campo do recurso mostrado na pantalla de conexión da conta de almacenamento.</span><span class="sxs-lookup"><span data-stu-id="a9fd3-152">In audience insights, insert the resource ID in the resource field displayed in the storage account connection screen.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Insira a información do ID do recurso da conta de almacenamento.":::   
   
1. <span data-ttu-id="a9fd3-154">Continúe cos pasos restantes nas estatísticas do público para anexar a conta de almacenamento.</span><span class="sxs-lookup"><span data-stu-id="a9fd3-154">Continue with the remaining steps in audience insights to attach the storage account.</span></span>

### <a name="subscription-based-storage-account-connection"></a><span data-ttu-id="a9fd3-155">Conexión de conta de almacenamento baseada na subscrición</span><span class="sxs-lookup"><span data-stu-id="a9fd3-155">Subscription-based storage account connection</span></span>

1. <span data-ttu-id="a9fd3-156">Vaia ao [Portal de administración de Azure](https://portal.azure.com), inicie sesión na súa subscrición e abra a conta de almacenamento.</span><span class="sxs-lookup"><span data-stu-id="a9fd3-156">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="a9fd3-157">Vaia a **Configuración** > **Propiedades** no panel de navegación.</span><span class="sxs-lookup"><span data-stu-id="a9fd3-157">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="a9fd3-158">Revise a **Subscrición**, o **Grupo de recursos** e o **Nome** da conta de almacenamento para asegurarse de que selecciona os valores correctos nas estatísticas do público.</span><span class="sxs-lookup"><span data-stu-id="a9fd3-158">Review the **Subscription**, **Resource group**, and the **Name** of the storage account to make sure you select the right values in audience insights.</span></span>

1. <span data-ttu-id="a9fd3-159">En estatísticas de audiencia, escolla os valores ou os campos correspondentes ao anexar a conta de almacenamento.</span><span class="sxs-lookup"><span data-stu-id="a9fd3-159">In audience insights, choose the values or for the corresponding fields when attaching the storage account.</span></span>

   :::image type="content" source="media/ADLS-SP-SubscriptionConnection.png" alt-text="Insira a información do ID do recurso da conta de almacenamento.":::
   
1. <span data-ttu-id="a9fd3-161">Continúe cos pasos restantes nas estatísticas do público para anexar a conta de almacenamento.</span><span class="sxs-lookup"><span data-stu-id="a9fd3-161">Continue with the remaining steps in audience insights to attach the storage account.</span></span>
