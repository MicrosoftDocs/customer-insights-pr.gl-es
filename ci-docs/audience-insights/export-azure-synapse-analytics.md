---
title: Exportar datos de Customer Insights a Azure Synapse Analytics
description: Obteña información acerca da configuración da conexión a Azure Synapse Analytics.
ms.date: 04/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 822082d661863e737ea3d3a749a6c878db766967
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 05/04/2021
ms.locfileid: "5977375"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a><span data-ttu-id="0caec-103">Exportar datos a Azure Synapse Analytics (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="0caec-103">Export data to Azure Synapse Analytics (Preview)</span></span>

<span data-ttu-id="0caec-104">Azure Synapse é un servizo de análise que acelera o tempo para obter información en almacéns e grandes sistemas de datos.</span><span class="sxs-lookup"><span data-stu-id="0caec-104">Azure Synapse is an analytics service that accelerates time to insight across data warehouses and big data systems.</span></span> <span data-ttu-id="0caec-105">Pode inxerir e usar os seus datos de Customer Insights en [Azure Synapse](/azure/synapse-analytics/overview-what-is).</span><span class="sxs-lookup"><span data-stu-id="0caec-105">You can ingest and use your Customer Insights data in [Azure Synapse](/azure/synapse-analytics/overview-what-is).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0caec-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="0caec-106">Prerequisites</span></span>

<span data-ttu-id="0caec-107">Os seguintes requisitos previos deben cumprirse para configurar a conexión de Customer Insights a Azure Synapse.</span><span class="sxs-lookup"><span data-stu-id="0caec-107">The following prerequisites must be met to configure the connection from Customer Insights to Azure Synapse.</span></span>

> [!NOTE]
> <span data-ttu-id="0caec-108">Asegúrese de configurar todas as **atribucións de roles** segundo se describe.</span><span class="sxs-lookup"><span data-stu-id="0caec-108">Make sure to set all **role assignments** as described.</span></span>  

## <a name="prerequisites-in-customer-insights"></a><span data-ttu-id="0caec-109">Requisitos previos en Customer Insights</span><span class="sxs-lookup"><span data-stu-id="0caec-109">Prerequisites in Customer Insights</span></span>

* <span data-ttu-id="0caec-110">Ten un rol de **Administrador** na información do público.</span><span class="sxs-lookup"><span data-stu-id="0caec-110">You have an **Administrator** role in audience insights.</span></span> <span data-ttu-id="0caec-111">Obteña máis información acerca da [definición dos permisos do usuarios na información do público](permissions.md#assign-roles-and-permissions)</span><span class="sxs-lookup"><span data-stu-id="0caec-111">Learn more about [setting user permissions in audience insights](permissions.md#assign-roles-and-permissions)</span></span>

<span data-ttu-id="0caec-112">En Azure:</span><span class="sxs-lookup"><span data-stu-id="0caec-112">In Azure:</span></span> 

- <span data-ttu-id="0caec-113">Unha subscrición de Azure activa.</span><span class="sxs-lookup"><span data-stu-id="0caec-113">An active Azure subscription.</span></span>

- <span data-ttu-id="0caec-114">Se usa unha conta nova de Azure Data Lake Storage Gen2, a *entidade de servizo para a información do público* precisa permisos de **colaborador de datos de BLOB de almacenamento**.</span><span class="sxs-lookup"><span data-stu-id="0caec-114">If using a new Azure Data Lake Storage Gen2 account, the *service principal for audience insights* needs **Storage Blob Data Contributor** permissions.</span></span> <span data-ttu-id="0caec-115">Obteña máis información acerca da [conexión a unha conta de Azure Data Lake Storage Gen2 coa entidade de servizo de Azure para a información do público](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="0caec-115">Learn more on [connecting to an Azure Data Lake Storage Gen2 account with Azure service principal for audience insights](connect-service-principal.md).</span></span> <span data-ttu-id="0caec-116">Data Lake Storage Gen2 **debe ter o** [espazo de nomes xerárquico](/azure/storage/blobs/data-lake-storage-namespace) activado.</span><span class="sxs-lookup"><span data-stu-id="0caec-116">The Data Lake Storage Gen2 **must have** [hierarchical namespace](/azure/storage/blobs/data-lake-storage-namespace) enabled.</span></span>

- <span data-ttu-id="0caec-117">No grupo de recursos onde se atopa a área de traballo de Azure Synapse, hai que atribuírlle á *entidade de servizo* e ao *usuario da información do público* como mínimo permisos de **Lector**.</span><span class="sxs-lookup"><span data-stu-id="0caec-117">On the resource group the Azure Synapse workspace is located, the *service principal* and the *user for audience insights* needs to be assigned at least **Reader** permissions.</span></span> <span data-ttu-id="0caec-118">Para obter máis información, consulte [Atribuír roles de Azure no portal de Azure](/azure/role-based-access-control/role-assignments-portal).</span><span class="sxs-lookup"><span data-stu-id="0caec-118">For more information, see [Assign Azure roles using the Azure portal](/azure/role-based-access-control/role-assignments-portal).</span></span>

- <span data-ttu-id="0caec-119">O *usuario* precisa permisos de **colaborador de datos de BLOB de almacenamento** na conta de Azure Data Lake Storage Gen2 na que se atopan os datos ligados á área de traballo de Azure Synapse.</span><span class="sxs-lookup"><span data-stu-id="0caec-119">The *user* needs **Storage Blob Data Contributor** permissions on the Azure Data Lake Storage Gen2 account where the data is located and linked to the Azure Synapse workspace.</span></span> <span data-ttu-id="0caec-120">Obteña máis información acerca do [uso do portal de Azure para atribuír un rol de Azure para o acceso aos datos de BLOB e fila](/azure/storage/common/storage-auth-aad-rbac-portal) e dos [permisos do colaborador de datos de BLOB de almacenamento](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span><span class="sxs-lookup"><span data-stu-id="0caec-120">Learn more about [using the Azure portal to assign an Azure role for access to blob and queue data](/azure/storage/common/storage-auth-aad-rbac-portal) and [Storage Blob Data Contributor permissions](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span></span>

- <span data-ttu-id="0caec-121">A *[identidade xestionada da área de traballo de Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* precisa permisos de **colaborador de datos de BLOB de almacenamento** na conta de Azure Data Lake Storage Gen2 na que se atopan os datos ligados á área de traballo de Azure Synapse.</span><span class="sxs-lookup"><span data-stu-id="0caec-121">The *[Azure Synapse workspace managed identity](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* needs **Storage Blob Data Contributor** permissions on the Azure Data Lake Storage Gen2 account where the data is located and linked to the Azure Synapse workspace.</span></span> <span data-ttu-id="0caec-122">Obteña máis información acerca do [uso do portal de Azure para atribuír un rol de Azure para o acceso aos datos de BLOB e fila](/azure/storage/common/storage-auth-aad-rbac-portal) e dos [permisos do colaborador de datos de BLOB de almacenamento](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span><span class="sxs-lookup"><span data-stu-id="0caec-122">Learn more on [using the Azure portal to assign an Azure role for access to blob and queue data](/azure/storage/common/storage-auth-aad-rbac-portal) and [Storage Blob Data Contributor permissions](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span></span>

- <span data-ttu-id="0caec-123">Na área de traballo de Azure Synapse, a *entidade de servizo para a información do público* precisa ter atribuído o rol de **administrador de Synapse**.</span><span class="sxs-lookup"><span data-stu-id="0caec-123">On the Azure Synapse workspace, the *service principal for audience insights* needs **Synapse Administrator** role assigned.</span></span> <span data-ttu-id="0caec-124">Para obter máis información, consulte [Como configurar o control de acceso para a súa área de traballo de Synapse](/azure/synapse-analytics/security/how-to-set-up-access-control).</span><span class="sxs-lookup"><span data-stu-id="0caec-124">For more information, see [How to set up access control for your Synapse workspace](/azure/synapse-analytics/security/how-to-set-up-access-control).</span></span>

## <a name="set-up-the-connection-and-export-to-azure-synapse"></a><span data-ttu-id="0caec-125">Configurar a conexión e exportar a Azure Synapse</span><span class="sxs-lookup"><span data-stu-id="0caec-125">Set up the connection and export to Azure Synapse</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="0caec-126">Configurar unha conexión</span><span class="sxs-lookup"><span data-stu-id="0caec-126">Configure a connection</span></span>

1. <span data-ttu-id="0caec-127">Vaia a **Administrar** > **Conexións**.</span><span class="sxs-lookup"><span data-stu-id="0caec-127">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="0caec-128">Seleccione **Engadir conexión** e elixa **Azure Synapse Analytics** ou seleccione a opción **Configurar** no mosaico **Azure Synapse Analytics** para configurar a conexión.</span><span class="sxs-lookup"><span data-stu-id="0caec-128">Select **Add connection** and choose **Azure Synapse Analytics** or select the **Set up** on the **Azure Synapse Analytics** tile to configure the connection.</span></span>

1. <span data-ttu-id="0caec-129">Déalle á conexión un nome recoñecible no campo Nome para mostrar.</span><span class="sxs-lookup"><span data-stu-id="0caec-129">Give your connection a recognizable name in the Display name field.</span></span> <span data-ttu-id="0caec-130">O nome e o tipo de conexión describen esta conexión.</span><span class="sxs-lookup"><span data-stu-id="0caec-130">The name and the type of the connection describes this connection.</span></span> <span data-ttu-id="0caec-131">Recomendamos escoller un nome que explique o propósito e o destino da conexión.</span><span class="sxs-lookup"><span data-stu-id="0caec-131">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="0caec-132">Escolla quen pode usar esta conexión.</span><span class="sxs-lookup"><span data-stu-id="0caec-132">Choose who can use this connection.</span></span> <span data-ttu-id="0caec-133">Se non realiza ningunha acción, o valor predeterminado será Administradores.</span><span class="sxs-lookup"><span data-stu-id="0caec-133">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="0caec-134">Para obter máis información, consulte [Permitir aos colaboradores usar unha conexión para as exportacións](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="0caec-134">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="0caec-135">Seleccione ou busque a subscrición na que quere empregar os datos de Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="0caec-135">Select or search for the subscription you want to use the Customer Insights data in.</span></span> <span data-ttu-id="0caec-136">Cando seleccione unha subscrición, tamén pode seleccionar **Área de traballo**, **Conta de almacenamento** e **Contedor**.</span><span class="sxs-lookup"><span data-stu-id="0caec-136">As soon as a subscription is selected, you can also select **Workspace**, **Storage account**, and **Container**.</span></span>

1. <span data-ttu-id="0caec-137">Seleccione **Gardar** para gardar a conexión.</span><span class="sxs-lookup"><span data-stu-id="0caec-137">Select **Save** to save the connection.</span></span>

### <a name="configure-an-export"></a><span data-ttu-id="0caec-138">Configurar unha exportación</span><span class="sxs-lookup"><span data-stu-id="0caec-138">Configure an export</span></span>

<span data-ttu-id="0caec-139">Pode configurar esta exportación se ten acceso a unha conexión deste tipo.</span><span class="sxs-lookup"><span data-stu-id="0caec-139">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="0caec-140">Para obter máis información, consulte os [permisos necesarios para configurar unha exportación](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="0caec-140">For more information, see [permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="0caec-141">Vaia a **Datos** > **Exportacións**.</span><span class="sxs-lookup"><span data-stu-id="0caec-141">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="0caec-142">Seleccione **Engadir exportación** para crear unha nova exportación.</span><span class="sxs-lookup"><span data-stu-id="0caec-142">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="0caec-143">No campo **Conexión da exportación**, escolla unha conexión da sección **Azure Synapse Analytics**.</span><span class="sxs-lookup"><span data-stu-id="0caec-143">In the **Connection for export** field, choose a connection from the **Azure Synapse Analytics** section.</span></span> <span data-ttu-id="0caec-144">Se non ve o nome desta sección, non hai [conexións](connections.md) deste tipo dispoñibles para vostede.</span><span class="sxs-lookup"><span data-stu-id="0caec-144">If you don't see this section name, there are no [connections](connections.md) of this type available to you.</span></span>

1. <span data-ttu-id="0caec-145">Proporcione un **Nome para mostrar** recoñecible para a exportación e un **Nome da base de datos**.</span><span class="sxs-lookup"><span data-stu-id="0caec-145">Provide a recognizable **Display name** for your export and a **Database name**.</span></span>

1. <span data-ttu-id="0caec-146">Seleccione as entidades que quere exportar a Azure Synapse Analytics.</span><span class="sxs-lookup"><span data-stu-id="0caec-146">Select which entities you want to export to Azure Synapse Analytics.</span></span>

1. <span data-ttu-id="0caec-147">Seleccione **Gardar**.</span><span class="sxs-lookup"><span data-stu-id="0caec-147">Select **Save**.</span></span>

<span data-ttu-id="0caec-148">Ao gardar unha exportación non se executa a exportación inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="0caec-148">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="0caec-149">A exportación execútase con cada [actualización programada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="0caec-149">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="0caec-150">Tamén pode [exportar datos baixo demanda](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="0caec-150">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span>

### <a name="update-an-export"></a><span data-ttu-id="0caec-151">Actualizar unha exportación</span><span class="sxs-lookup"><span data-stu-id="0caec-151">Update an export</span></span>

1. <span data-ttu-id="0caec-152">Vaia a **Datos** > **Exportacións**.</span><span class="sxs-lookup"><span data-stu-id="0caec-152">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="0caec-153">Seleccione **Editar** na exportación que queira editar.</span><span class="sxs-lookup"><span data-stu-id="0caec-153">Select **Edit** on the export you want to update.</span></span>

   - <span data-ttu-id="0caec-154">**Engadir** ou **Eliminar** entidades da selección.</span><span class="sxs-lookup"><span data-stu-id="0caec-154">**Add** or **Remove** entities from the selection.</span></span> <span data-ttu-id="0caec-155">Se se eliminan entidades da selección, non se eliminarán da base de datos de Synapse Analytics.</span><span class="sxs-lookup"><span data-stu-id="0caec-155">If entities are removed from the selection, they aren't deleted from the Synapse Analytics database.</span></span> <span data-ttu-id="0caec-156">Non obstante, as futuras actualizacións de datos non actualizarán as entidades eliminadas desa base de datos.</span><span class="sxs-lookup"><span data-stu-id="0caec-156">However, future data refreshes won't update the removed entities in that database.</span></span>

   - <span data-ttu-id="0caec-157">**Cambiar o nome da base de datos** crea unha nova base de datos de Synapse Analytics.</span><span class="sxs-lookup"><span data-stu-id="0caec-157">**Changing the Database Name** creates a new Synapse Analytics database.</span></span> <span data-ttu-id="0caec-158">A base de datos co nome configurado anteriormente non se actualizará en futuras actualizacións.</span><span class="sxs-lookup"><span data-stu-id="0caec-158">The database with the name that was configured before won't receive any updates in future refreshes.</span></span>
