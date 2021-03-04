---
title: Conectar os datos de Common Data Model a unha conta de Azure Data Lake
description: Traballe con datos de Common Data Model usando Azure Data Lake Storage.
ms.date: 05/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 247e4d9c47ff2373065ebf3c6d554323e45a120b
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267858"
---
# <a name="connect-to-a-common-data-model-folder-using-an-azure-data-lake-account"></a><span data-ttu-id="877e1-103">Conectar cun cartafol de Common Data Model cunha conta de Azure Data Lake</span><span class="sxs-lookup"><span data-stu-id="877e1-103">Connect to a Common Data Model folder using an Azure Data Lake account</span></span>

<span data-ttu-id="877e1-104">Este artigo ofrece información sobre como inxerir datos desde un cartafol de Common Data Model usando a súa conta de Azure Data Lake Storage Gen2.</span><span class="sxs-lookup"><span data-stu-id="877e1-104">This article provides information on how to ingest data from a Common Data Model folder using your Azure Data Lake Storage Gen2 account.</span></span>

## <a name="important-considerations"></a><span data-ttu-id="877e1-105">Consideracións importantes</span><span class="sxs-lookup"><span data-stu-id="877e1-105">Important considerations</span></span>

- <span data-ttu-id="877e1-106">Os datos do seu Azure Data Lake deben seguir o estándar do modelo de datos comúns.</span><span class="sxs-lookup"><span data-stu-id="877e1-106">Data in your Azure Data Lake needs to follow the Common Data Model standard.</span></span> <span data-ttu-id="877e1-107">De momento non se admiten outros formatos.</span><span class="sxs-lookup"><span data-stu-id="877e1-107">Other formats aren't supported at the moment.</span></span>

- <span data-ttu-id="877e1-108">A inxestión de datos admite contas de almacentamento de Azure Data Lake *Gen2* exclusivamente.</span><span class="sxs-lookup"><span data-stu-id="877e1-108">Data ingestion supports Azure Data Lake *Gen2* storage accounts exclusively.</span></span> <span data-ttu-id="877e1-109">Non pode usar as contas de almacenamento de Azure Data Lake Gen1 para inxerir datos.</span><span class="sxs-lookup"><span data-stu-id="877e1-109">You can't use Azure Data Lake Gen1 storage accounts to ingest data.</span></span>

- <span data-ttu-id="877e1-110">Para autenticarse cunha entidade de seguranza do servizo de Azure, asegúrese de que está configurada no seu inquilino.</span><span class="sxs-lookup"><span data-stu-id="877e1-110">To authenticate with an Azure service principal, make sure it's configured in your tenant.</span></span> <span data-ttu-id="877e1-111">Para obter máis información, consulte [Conectar información do público a unha conta de Azure Data Lake Storage Gen2 cunha entidade principal de seguranza do servizo de Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="877e1-111">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span>

- <span data-ttu-id="877e1-112">O Azure Data Lake que desexa conectar e do que inxerir datos ten que estar na mesma rexión de Azure que o ambiente de Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="877e1-112">The Azure Data Lake you want to connect and ingest data from have to be in the same Azure region as the Dynamics 365 Customer Insights environment.</span></span> <span data-ttu-id="877e1-113">Non se admiten conexións a un cartafol de Common Data Model desde un lago de datos nunha rexión de Azure diferente.</span><span class="sxs-lookup"><span data-stu-id="877e1-113">Connections to a Common Data Model folder from a data lake in a different Azure region is not supported.</span></span> <span data-ttu-id="877e1-114">Para coñecer a rexión de Azure do entorno, vaia a **Administrar** > **Sistema** > **Acerca de** na información do público.</span><span class="sxs-lookup"><span data-stu-id="877e1-114">To know the Azure region of the environment, go to **Admin** > **System** > **About** in audience insights.</span></span>

- <span data-ttu-id="877e1-115">Os datos almacenados en servizos en liña pódense almacenar nun lugar diferente a onde se procesan ou almacenan os datos en Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="877e1-115">Data stored in online services, may be stored in a different location than where data is processed or stored in Dynamics 365 Customer Insights.</span></span><span data-ttu-id="877e1-116"> Ao importar ou conectarse a datos almacenados en servizos en liña, acepta que os datos poden ser transferidos a e almacenados con Dynamics 365 Customer Insights. [Obteña máis información no Centro de confianza de Microsoft.](https://www.microsoft.com/trust-center)</span><span class="sxs-lookup"><span data-stu-id="877e1-116"> By importing or connecting to data stored in online services, you agree that data can be transferred to and stored with Dynamics 365 Customer Insights. [Learn more at the Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span></span>

## <a name="connect-to-a-common-data-model-folder"></a><span data-ttu-id="877e1-117">Conectarse a un cartafol de Common Data Model</span><span class="sxs-lookup"><span data-stu-id="877e1-117">Connect to a Common Data Model folder</span></span>

1. <span data-ttu-id="877e1-118">Na información do público, vaia a **Datos** > **Orixes de datos**.</span><span class="sxs-lookup"><span data-stu-id="877e1-118">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="877e1-119">Seleccione **Engadir orixe de datos**.</span><span class="sxs-lookup"><span data-stu-id="877e1-119">Select **Add data source**.</span></span>

1. <span data-ttu-id="877e1-120">Seleccione **Conectarse a un cartafol de Common Data Model**, introduza un **Nome** para a orixe de datos e seleccione **Seguinte**.</span><span class="sxs-lookup"><span data-stu-id="877e1-120">Select **Connect to a Common Data Model folder**, enter a **Name** for the data source, and select **Next**.</span></span> <span data-ttu-id="877e1-121">Dea nome ás instrucións:</span><span class="sxs-lookup"><span data-stu-id="877e1-121">Name guidelines:</span></span> 
   - <span data-ttu-id="877e1-122">Comece por unha letra.</span><span class="sxs-lookup"><span data-stu-id="877e1-122">Start with a letter.</span></span>
   - <span data-ttu-id="877e1-123">Use só letras e números.</span><span class="sxs-lookup"><span data-stu-id="877e1-123">Use letters and numbers only.</span></span> <span data-ttu-id="877e1-124">Non se permiten caracteres especiais nin espazos.</span><span class="sxs-lookup"><span data-stu-id="877e1-124">Special characters and spaces are not allowed.</span></span>
   - <span data-ttu-id="877e1-125">Empregue entre 3 e 64 caracteres.</span><span class="sxs-lookup"><span data-stu-id="877e1-125">Use between 3 and 64 characters.</span></span>

1. <span data-ttu-id="877e1-126">Pode escoller entre usar unha opción baseada en recursos e unha opción baseada na subscrición para a autenticación.</span><span class="sxs-lookup"><span data-stu-id="877e1-126">You can choose between using a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="877e1-127">Para obter máis información, consulte [Conectar información do público a unha conta de Azure Data Lake Storage Gen2 cunha entidade principal de seguranza do servizo de Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="877e1-127">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="877e1-128">Introduza a información do **contedor** e seleccione **Seguinte**.</span><span class="sxs-lookup"><span data-stu-id="877e1-128">Enter the **Container** information and select **Next**.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="877e1-129">![Cadro de diálogo para introducir novos detalles de conexión para Azure Data Lake](media/enter-new-storage-details.png)
   > </span><span class="sxs-lookup"><span data-stu-id="877e1-129">![Dialog box to enter new connection details for Azure Data Lake](media/enter-new-storage-details.png)
   > </span></span>[!NOTE]
<span data-ttu-id="877e1-130">Precisa unha das seguintes funcións no contedor ou na conta de almacenamento mencionada anteriormente para poder conectarse e crear unha orixe de datos:</span><span class="sxs-lookup"><span data-stu-id="877e1-130">You need one of the following roles either to the container or the storage account referred above to be able to connect to and create a data source:</span></span>
   >  - <span data-ttu-id="877e1-131">Lector de datos do BLOB de almacenamento</span><span class="sxs-lookup"><span data-stu-id="877e1-131">Storage Blob Data Reader</span></span>
   >  - <span data-ttu-id="877e1-132">Propietario dos datos do BLOB de almacenamento</span><span class="sxs-lookup"><span data-stu-id="877e1-132">Storage Blob Data Owner</span></span>
   >  - <span data-ttu-id="877e1-133">Colaborador de datos do BLOB de almacenamento</span><span class="sxs-lookup"><span data-stu-id="877e1-133">Storage Blob Data Contributor</span></span>

1. <span data-ttu-id="877e1-134">No diálogo **Seleccionar un cartafol de Common Data Model**, seleccione o ficheiro model.json ou manifest.json desde o que importar datos e seleccione **Seguinte**.</span><span class="sxs-lookup"><span data-stu-id="877e1-134">In the **Select a Common Data Model folder** dialog, select the model.json or manifest.json file to import data from, and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="877e1-135">Calquera ficheiro model.json ou manifest.json asociado a outra orixe de datos do contorno non aparecerá na lista.</span><span class="sxs-lookup"><span data-stu-id="877e1-135">Any model.json or manifest.json file associated with another data source in the environment won't show in the list.</span></span>

1. <span data-ttu-id="877e1-136">Obterá unha lista de entidades dispoñibles no ficheiro model.json ou manifest.json seleccionado.</span><span class="sxs-lookup"><span data-stu-id="877e1-136">You'll get a list of available entities in the selected model.json or manifest.json file.</span></span> <span data-ttu-id="877e1-137">Pode revisar e seleccionar na lista de entidades dispoñibles e seleccionar **Gardar**.</span><span class="sxs-lookup"><span data-stu-id="877e1-137">You can review and select from the list of available entities and select **Save**.</span></span> <span data-ttu-id="877e1-138">Todas as entidades seleccionadas inxeriranse a partir da orixe de datos nova.</span><span class="sxs-lookup"><span data-stu-id="877e1-138">All of the selected entities will be ingested from the new data source.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="877e1-139">![Caixa de diálogo que mostra unha lista de entidades dun ficheiro model.json](media/review-entities.png)</span><span class="sxs-lookup"><span data-stu-id="877e1-139">![Dialog box showing a list of entities from a model.json file](media/review-entities.png)</span></span>

8. <span data-ttu-id="877e1-140">Indique que entidades de datos quere para activar a creación de perfís de datos e seleccione **Gardar**.</span><span class="sxs-lookup"><span data-stu-id="877e1-140">Indicate which data entities you want to enable data profiling and select **Save**.</span></span> <span data-ttu-id="877e1-141">A creación de perfís de datos activa as análises e outras funcionalidades.</span><span class="sxs-lookup"><span data-stu-id="877e1-141">Data profiling enables analytics and other capabilities.</span></span> <span data-ttu-id="877e1-142">Pode seleccionar a entidade enteira, que selecciona todos os atributos da entidade, ou seleccionar certos atributos que elixa.</span><span class="sxs-lookup"><span data-stu-id="877e1-142">You can select the whole entity, which selects all attributes from the entity, or select certain attributes of your choice.</span></span> <span data-ttu-id="877e1-143">Por defecto, ningunha entidade está habilitada para a creación de perfís de datos.</span><span class="sxs-lookup"><span data-stu-id="877e1-143">By default, no entity is enabled for data profiling.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="877e1-144">![Cadro de diálogo que mostra a creación de perfís de datos](media/dataprofiling-entities.png)</span><span class="sxs-lookup"><span data-stu-id="877e1-144">![Dialog box showing a data profiling](media/dataprofiling-entities.png)</span></span>

9. <span data-ttu-id="877e1-145">Despois de gardar as súas seleccións, abrirase a páxina **Fontes de datos**.</span><span class="sxs-lookup"><span data-stu-id="877e1-145">After saving your selections, the **Data sources** page opens.</span></span> <span data-ttu-id="877e1-146">Agora debe ver a conexión do cartafol Common Data Model como orixe de datos.</span><span class="sxs-lookup"><span data-stu-id="877e1-146">You should now see the Common Data Model folder connection as a data source.</span></span>

> [!NOTE]
> <span data-ttu-id="877e1-147">Un ficheiro model.json ou manifest.json só pode asociarse cunha orixe de datos no mesmo ambiente.</span><span class="sxs-lookup"><span data-stu-id="877e1-147">A model.json file or manifest.json can only associate with one data source in the same environment.</span></span> <span data-ttu-id="877e1-148">Non obstante, o mesmo ficheiro model.json ou manifest.json pode usarse para fontes de datos en múltiples contornos.</span><span class="sxs-lookup"><span data-stu-id="877e1-148">However, the same model.json or manifest.json file can be used for data sources in multiple environments.</span></span>

## <a name="edit-a-common-data-model-folder-data-source"></a><span data-ttu-id="877e1-149">Editar unha orixe de datos do cartafol de Common Data Model</span><span class="sxs-lookup"><span data-stu-id="877e1-149">Edit a Common Data Model folder data source</span></span>

<span data-ttu-id="877e1-150">Pode actualizar a clave de acceso da conta de almacenamento que contén o cartafol de Common Data Model.</span><span class="sxs-lookup"><span data-stu-id="877e1-150">You can update the access key for the storage account containing the Common Data Model folder.</span></span> <span data-ttu-id="877e1-151">Tamén pode cambiar o ficheiro model.json ou manifest.json.</span><span class="sxs-lookup"><span data-stu-id="877e1-151">You may also change the model.json or manifest.json file.</span></span> <span data-ttu-id="877e1-152">Para conectarse a un contedor diferente da súa conta de almacenamento ou cambiar o nome da conta, [cree unha nova conexión de orixe de datos](#connect-to-a-common-data-model-folder).</span><span class="sxs-lookup"><span data-stu-id="877e1-152">To connect to a different container from your storage account, or change the account name, [create a new data source connection](#connect-to-a-common-data-model-folder).</span></span>

1. <span data-ttu-id="877e1-153">Na información do público, vaia a **Datos** > **Orixes de datos**.</span><span class="sxs-lookup"><span data-stu-id="877e1-153">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="877e1-154">A carón da orixe de datos que desexa actualizar, seleccione os tres puntos.</span><span class="sxs-lookup"><span data-stu-id="877e1-154">Next to the data source you'd like to update, select the ellipsis.</span></span>

3. <span data-ttu-id="877e1-155">Seleccione a opción **Editar** da lista.</span><span class="sxs-lookup"><span data-stu-id="877e1-155">Select the **Edit** option from the list.</span></span>

4. <span data-ttu-id="877e1-156">Tamén pode actualizar a **Clave de acceso** e seleccionar **Seguinte**.</span><span class="sxs-lookup"><span data-stu-id="877e1-156">Optionally, update the **Access key** and select **Next**.</span></span>

   ![Caixa de diálogo para editar e actualizar unha clave de acceso para un orixe de datos existente](media/edit-access-key.png)

5. <span data-ttu-id="877e1-158">Opcionalmente, pode actualizar desde unha conexión de clave de conta a unha conexión baseada en recursos ou baseada nunha subscrición.</span><span class="sxs-lookup"><span data-stu-id="877e1-158">Optionally, you can update from an account key connection to a resource-based or a subscription-based connection.</span></span> <span data-ttu-id="877e1-159">Para obter máis información, consulte [Conectar información do público a unha conta de Azure Data Lake Storage Gen2 cunha entidade principal de seguranza do servizo de Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="877e1-159">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="877e1-160">Non pode cambiar a información do **contedor** ao actualizar a conexión.</span><span class="sxs-lookup"><span data-stu-id="877e1-160">You can't change **Container** information when updating the connection.</span></span>
   > [!div class="mx-imgBorder"]

   > ![Cadro de diálogo para introducir os detalles da conexión de Azure Data Lake nunha conta de almacenamento existente](media/enter-existing-storage-details.png)

   > [!NOTE]
   > <span data-ttu-id="877e1-162">Precisa unha das seguintes funcións no contedor ou na conta de almacenamento mencionada anteriormente para poder conectarse e crear unha orixe de datos:</span><span class="sxs-lookup"><span data-stu-id="877e1-162">You need one of the following roles either to the container or the storage account referred above to be able to connect to and create a data source:</span></span>
   >  - <span data-ttu-id="877e1-163">Lector de datos do BLOB de almacenamento</span><span class="sxs-lookup"><span data-stu-id="877e1-163">Storage Blob Data Reader</span></span>
   >  - <span data-ttu-id="877e1-164">Propietario dos datos do BLOB de almacenamento</span><span class="sxs-lookup"><span data-stu-id="877e1-164">Storage Blob Data Owner</span></span>
   >  - <span data-ttu-id="877e1-165">Colaborador de datos do BLOB de almacenamento</span><span class="sxs-lookup"><span data-stu-id="877e1-165">Storage Blob Data Contributo</span></span>


6. <span data-ttu-id="877e1-166">Opcionalmente, escolla un ficheiro model.json ou manifest.json diferente cun conxunto diferente de entidades do contedor.</span><span class="sxs-lookup"><span data-stu-id="877e1-166">Optionally, choose a different model.json or manifest.json file with a different set of entities from the container.</span></span>

7. <span data-ttu-id="877e1-167">Opcionalmente, pode seleccionar entidades adicionais para inxerir.</span><span class="sxs-lookup"><span data-stu-id="877e1-167">Optionally, you can select additional entities to ingest.</span></span> <span data-ttu-id="877e1-168">Tamén pode eliminar calquera entidade xa seleccionada se non hai dependencias.</span><span class="sxs-lookup"><span data-stu-id="877e1-168">You can also remove any already selected entities if there are no dependencies.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="877e1-169">Se hai dependencias no ficheiro model.json ou manifest.json existente e no conxunto de entidades, verá unha mensaxe de erro e non poderá seleccionar un ficheiro model.json ou manifest.json diferente.</span><span class="sxs-lookup"><span data-stu-id="877e1-169">If there are dependencies on the existing model.json or manifest.json file and the set of entities, you'll see an error message and can't select a different model.json or manifest.json file.</span></span> <span data-ttu-id="877e1-170">Elimine esas dependencias antes de cambiar o ficheiro model.json ou manifest.json ou cree unha nova orixe de datos co ficheiro model.json ou manifest.json que desexe usar para evitar eliminar as dependencias.</span><span class="sxs-lookup"><span data-stu-id="877e1-170">Remove those dependencies before changing the model.json or manifest.json file or create a new data source with the model.json or manifest.json file that you want to use to avoid removing the dependencies.</span></span>

8. <span data-ttu-id="877e1-171">Opcionalmente, pode seleccionar atributos ou entidades adicionais para habilitar a creación de perfís de datos ou desactivar os xa seleccionados.</span><span class="sxs-lookup"><span data-stu-id="877e1-171">Optionally, you can select additional attributes or entities to enable data profiling on or disable already selected ones.</span></span>   


[!INCLUDE[footer-include](../includes/footer-banner.md)]