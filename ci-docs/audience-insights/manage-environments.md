---
title: Crear e xestionar ambientes
description: Aprenda a rexistrarse no servizo e a xestionar contornos.
ms.date: 02/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 1c2dfdd2889b5cb6c5285b4d7cc7f52a3d6de4d1
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598291"
---
# <a name="manage-environments"></a><span data-ttu-id="93648-103">Xestionar ambientes</span><span class="sxs-lookup"><span data-stu-id="93648-103">Manage environments</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="93648-104">Este artigo explica como crear unha nova organización e como fornecer un ambiente.</span><span class="sxs-lookup"><span data-stu-id="93648-104">This article explains how to create a new organization and how to provision an environment.</span></span>

## <a name="sign-up-and-create-an-organization"></a><span data-ttu-id="93648-105">Rexistrarse e crear unha organización</span><span class="sxs-lookup"><span data-stu-id="93648-105">Sign up and create an organization</span></span>

1. <span data-ttu-id="93648-106">Vaia ao sitio web [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/).</span><span class="sxs-lookup"><span data-stu-id="93648-106">Go to the [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/) website.</span></span>

2. <span data-ttu-id="93648-107">Seleccione **Comezar**.</span><span class="sxs-lookup"><span data-stu-id="93648-107">Select **Get Started**.</span></span>

3. <span data-ttu-id="93648-108">Escolla o escenario de rexistro preferido e seleccione a ligazón correspondente.</span><span class="sxs-lookup"><span data-stu-id="93648-108">Choose your preferred sign-up scenario and select the corresponding link.</span></span>

4. <span data-ttu-id="93648-109">Acepte os termos e condicións e seleccione **Continuar** para comezar a crear a organización.</span><span class="sxs-lookup"><span data-stu-id="93648-109">Accept the terms and conditions and select **Continue** to start creating the organization.</span></span>

5. <span data-ttu-id="93648-110">Despois de crear o ambiente, redirixiráselle a [Customer Insights](https://home.ci.ai.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="93648-110">After the environment is created, you'll be redirected to [Customer Insights](https://home.ci.ai.dynamics.com).</span></span>

6. <span data-ttu-id="93648-111">Use o contorno de demostración para explorar a aplicación ou crear un novo contorno seguindo os pasos da seguinte sección.</span><span class="sxs-lookup"><span data-stu-id="93648-111">Use the demo environment to explore the app, or create a new environment by following the steps in the next section.</span></span>

7. <span data-ttu-id="93648-112">Despois de especificar a configuración do ambiente, seleccione **Crear**.</span><span class="sxs-lookup"><span data-stu-id="93648-112">After specifying the environment settings, select **Create**.</span></span>

8. <span data-ttu-id="93648-113">Iniciará sesión despois de que o ambiente se cree correctamente.</span><span class="sxs-lookup"><span data-stu-id="93648-113">You'll be signed in after the environment was created successfully.</span></span>

## <a name="create-an-environment-in-an-existing-organization"></a><span data-ttu-id="93648-114">Crear un ambiente nunha organización existente</span><span class="sxs-lookup"><span data-stu-id="93648-114">Create an environment in an existing organization</span></span>

<span data-ttu-id="93648-115">Existen dúas formas de crear un ambiente novo.</span><span class="sxs-lookup"><span data-stu-id="93648-115">There are two ways to create a new environment.</span></span> <span data-ttu-id="93648-116">Pode especificar unha configuración completamente nova ou pode copiar algúns axustes de configuración dun ambiente existente.</span><span class="sxs-lookup"><span data-stu-id="93648-116">You can either specify an entirely new configuration, or you can copy some configuration settings from an existing environment.</span></span>

<span data-ttu-id="93648-117">Para crear un ambiente:</span><span class="sxs-lookup"><span data-stu-id="93648-117">To create an environment:</span></span>

1. <span data-ttu-id="93648-118">Seleccione o selector de **ambiente** na cabeceira da aplicación.</span><span class="sxs-lookup"><span data-stu-id="93648-118">Select the **Environment** picker in the header of the app.</span></span>

1. <span data-ttu-id="93648-119">Seleccione **Nova**.</span><span class="sxs-lookup"><span data-stu-id="93648-119">Select **New**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="93648-120">![Configuración de ambientes](media/environment-settings-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="93648-120">![Environment settings](media/environment-settings-dialog.png)</span></span>

1. <span data-ttu-id="93648-121">No diálogo **Crear novo ambiente**, seleccione **Novo ambiente**.</span><span class="sxs-lookup"><span data-stu-id="93648-121">In the **Create new environment** dialog, select **New environment**.</span></span>

   <span data-ttu-id="93648-122">Se quere [copiar datos do ambiente actual](#additional-considerations-for-copy-configuration-preview), seleccione **Copiar do ambiente existente**.</span><span class="sxs-lookup"><span data-stu-id="93648-122">If you want to [copy data from the current environment](#additional-considerations-for-copy-configuration-preview), select **Copy from existing environment**.</span></span> <span data-ttu-id="93648-123">Verá unha lista de todos os ambientes dispoñibles da súa organización de onde pode copiar datos.</span><span class="sxs-lookup"><span data-stu-id="93648-123">You'll see a list of all available environments in your organization where you can copy data from.</span></span>

1. <span data-ttu-id="93648-124">Indique os seguintes detalles:</span><span class="sxs-lookup"><span data-stu-id="93648-124">Provide the following details:</span></span>
   - <span data-ttu-id="93648-125">**Nome**: O nome deste ambiente.</span><span class="sxs-lookup"><span data-stu-id="93648-125">**Name**: The name for this environment.</span></span> <span data-ttu-id="93648-126">Este campo xa está cuberto se copiou un ambiente existente, pero pode cambialo.</span><span class="sxs-lookup"><span data-stu-id="93648-126">This field is already filled in if you've copied an existing environment, but you can change it.</span></span>
   - <span data-ttu-id="93648-127">**Rexión**: a rexión na que se despregou e aloxou o servizo.</span><span class="sxs-lookup"><span data-stu-id="93648-127">**Region**: The region into which the service is deployed and hosted.</span></span>
   - <span data-ttu-id="93648-128">**Tipo**: selecciona se desexa crear un contorno de produción ou de illamento de procesos.</span><span class="sxs-lookup"><span data-stu-id="93648-128">**Type**: Select whether you want to create a Production or Sandbox environment.</span></span>

2. <span data-ttu-id="93648-129">Opcionalmente, pode seleccionar **Configuración avanzada**:</span><span class="sxs-lookup"><span data-stu-id="93648-129">Optionally, you can select **Advanced settings**:</span></span>

   - <span data-ttu-id="93648-130">**Gardar todos os datos en**: especifique onde desexa almacenar os datos de saída xerados de Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="93648-130">**Save all data to**: Specifies where you want to store the output data generated from Customer Insights.</span></span> <span data-ttu-id="93648-131">Terá dúas opcións: **Almacenamento de Customer Insights** (un Azure Data Lake xestionado polo equipo de Customer Insights) e **Azure Data Lake Storage Gen2** (o seu propio Azure Data Lake Storage).</span><span class="sxs-lookup"><span data-stu-id="93648-131">You'll have two options: **Customer Insights storage** (an Azure Data Lake managed by the Customer Insights team) and **Azure Data Lake Storage Gen2** (your own Azure Data Lake Storage).</span></span> <span data-ttu-id="93648-132">Por defecto, a opción de almacenamento de Customer Insights está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="93648-132">By default, the Customer Insights storage option is selected.</span></span>

   > [!NOTE]
   > <span data-ttu-id="93648-133">Ao gardar datos en Azure Data Lake Storage, acepta que os datos se transfiran e almacenen na localización xeográfica adecuada para esa conta de Azure Storage, que pode ser diferente á da conta na que están almacenados os datos en Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="93648-133">By saving data to Azure Data Lake Storage, you agree that data will be transferred to and stored in the appropriate geographic location for that Azure storage account, which may differ from where data is stored in Dynamics 365 Customer Insights.</span></span> [<span data-ttu-id="93648-134">Obteña máis información no Centro de confianza de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="93648-134">Learn more at the Microsoft Trust Center.</span></span>](https://www.microsoft.com/trust-center)
   >
   > <span data-ttu-id="93648-135">Na actualidade, as entidades inxeridas sempre se almacenan no lago de datos xestionado por Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="93648-135">Currently, ingested entities are always stored in the Customer Insights managed data lake.</span></span>
   > <span data-ttu-id="93648-136">Só admitimos contas de almacenamento de Azure Data Lake Gen2 da mesma rexión de Azure que seleccionou ao crear o ambiente.</span><span class="sxs-lookup"><span data-stu-id="93648-136">We support only Azure Data Lake Gen2 storage accounts from the same Azure region you selected when creating the environment.</span></span>
   > <span data-ttu-id="93648-137">Só admitimos contas de almacenamento de Azure Data Lake Gen2 compatibles co Espazo de nomes xerárquicos (HNS).</span><span class="sxs-lookup"><span data-stu-id="93648-137">We support only Azure Data Lake Gen2 Hierarchical Name Space (HNS) enabled storage accounts.</span></span>

   - <span data-ttu-id="93648-138">Para a opción de Azure Data Lake Storage Gen2, pode escoller entre unha opción baseada en recursos e unha opción baseada na subscrición para a autenticación.</span><span class="sxs-lookup"><span data-stu-id="93648-138">For the Azure Data Lake Storage Gen2 option, you can choose between a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="93648-139">Para obter máis información, consulte [Conectar información do público a unha conta de Azure Data Lake Storage Gen2 cunha entidade principal de seguranza do servizo de Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="93648-139">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="93648-140">O nome do **contedor** non se pode cambiar e será "customerinsights".</span><span class="sxs-lookup"><span data-stu-id="93648-140">The **Container** name can't be changed and will be "customerinsights".</span></span>
   
   - <span data-ttu-id="93648-141">Se quere usar [predicións](predictions.md) ou configurar o intercambio de datos con aplicacións e solucións baseadas en Microsoft Dataverse, forneza o URL do ambiente de Microsoft Dataverse en **Configurar o uso compartido de datos con Microsoft Dataverse e habilitar capacidades adicionais**.</span><span class="sxs-lookup"><span data-stu-id="93648-141">If you want to use [predictions](predictions.md) or configure data sharing with applications and solutions based on Microsoft Dataverse, provide the Microsoft Dataverse environment URL under **Configure data sharing with Microsoft Dataverse and enable additional capabilities**.</span></span> <span data-ttu-id="93648-142">Seleccione **Activar o uso compartido de datos** para compartir os datos de saída de Customer Insights cun Data Lake xestionado de Microsoft Dataverse.</span><span class="sxs-lookup"><span data-stu-id="93648-142">Select **Enable data sharing** to share Customer Insights output data with a Microsoft Dataverse Managed Data Lake.</span></span>

     > [!NOTE]
     > - <span data-ttu-id="93648-143">Compartir datos cun Data Lake xestionado Microsoft Dataverse actualmente non é compatible cando garda todos os datos no seu propio Azure Data Lake Storage.</span><span class="sxs-lookup"><span data-stu-id="93648-143">Data sharing with Microsoft Dataverse Managed Data Lake is currently not supported when you save all data to your own Azure Data Lake Storage.</span></span>
     > - <span data-ttu-id="93648-144">A [predición de valores que faltan nunha entidade](predictions.md) non se admite actualmente cando habilita o uso compartido de datos cun Data Lake xestionado de Microsoft Dataverse.</span><span class="sxs-lookup"><span data-stu-id="93648-144">[Prediction of missing values in an entity](predictions.md) is not currently supported when you enable data sharing with Microsoft Dataverse Managed Data Lake.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="93648-145">![Opcións de configuración para habilitar o uso compartido de datos con Microsoft Dataverse](media/Datasharing-with-DataverseMDL.png)</span><span class="sxs-lookup"><span data-stu-id="93648-145">![Configuration options to enable data sharing with Microsoft Dataverse](media/Datasharing-with-DataverseMDL.png)</span></span>

   <span data-ttu-id="93648-146">Cando execute procesos, como a inxestión de datos ou a creación de segmentos, crearanse os cartafoles correspondentes na conta de almacenamento que especificou anteriormente.</span><span class="sxs-lookup"><span data-stu-id="93648-146">When you run processes, such as data ingestion or segment creation, corresponding folders will be created in the storage account you specified above.</span></span> <span data-ttu-id="93648-147">Os ficheiros de datos e os ficheiros model.json crearanse e engadiranse aos respectivos subcartafoles en función do proceso que execute.</span><span class="sxs-lookup"><span data-stu-id="93648-147">Data files and model.json files will be created and added to the respective subfolders based on the process you run.</span></span>

   <span data-ttu-id="93648-148">Se crea varios contornos de Customer Insights e elixe gardar as entidades de saída deses ambientes na súa conta de almacenamento, crearanse cartafoles separados para cada contorno con ci_<environmentid> no contedor.</span><span class="sxs-lookup"><span data-stu-id="93648-148">If you create multiple environments of Customer Insights and choose to save the output entities from those environments in your storage account, separate folders will be created for each environment with ci_<environmentid> in the container.</span></span>

### <a name="additional-considerations-for-copy-configuration-preview"></a><span data-ttu-id="93648-149">Consideracións adicionais para a configuración da copia (previsualización)</span><span class="sxs-lookup"><span data-stu-id="93648-149">Additional considerations for copy configuration (preview)</span></span>

<span data-ttu-id="93648-150">Copiaranse os seguintes axustes de configuración:</span><span class="sxs-lookup"><span data-stu-id="93648-150">The following configuration settings are copied:</span></span>

- <span data-ttu-id="93648-151">Configuracións de funcións</span><span class="sxs-lookup"><span data-stu-id="93648-151">Feature configurations</span></span>
- <span data-ttu-id="93648-152">Fontes de datos inxeridas ou importadas</span><span class="sxs-lookup"><span data-stu-id="93648-152">Ingested/imported data sources</span></span>
- <span data-ttu-id="93648-153">Configuración da unificación de datos (mapa, coincidencia, combinación)</span><span class="sxs-lookup"><span data-stu-id="93648-153">Data unification (Map, Match, Merge) configuration</span></span>
- <span data-ttu-id="93648-154">Segmentos</span><span class="sxs-lookup"><span data-stu-id="93648-154">Segments</span></span>
- <span data-ttu-id="93648-155">Medidas</span><span class="sxs-lookup"><span data-stu-id="93648-155">Measures</span></span>
- <span data-ttu-id="93648-156">Relacións</span><span class="sxs-lookup"><span data-stu-id="93648-156">Relationships</span></span>
- <span data-ttu-id="93648-157">Actividades</span><span class="sxs-lookup"><span data-stu-id="93648-157">Activities</span></span>
- <span data-ttu-id="93648-158">Buscar e filtrar índice</span><span class="sxs-lookup"><span data-stu-id="93648-158">Search & filter Index</span></span>
- <span data-ttu-id="93648-159">Exportar destinos</span><span class="sxs-lookup"><span data-stu-id="93648-159">Export destinations</span></span>
- <span data-ttu-id="93648-160">Actualización programada</span><span class="sxs-lookup"><span data-stu-id="93648-160">Scheduled refresh</span></span>
- <span data-ttu-id="93648-161">Enriquecementos</span><span class="sxs-lookup"><span data-stu-id="93648-161">Enrichments</span></span>
- <span data-ttu-id="93648-162">Xestión de modelos</span><span class="sxs-lookup"><span data-stu-id="93648-162">Model management</span></span>
- <span data-ttu-id="93648-163">Atribución de roles</span><span class="sxs-lookup"><span data-stu-id="93648-163">Role assignments</span></span>

<span data-ttu-id="93648-164">*Non* se copiarán os seguintes axustes:</span><span class="sxs-lookup"><span data-stu-id="93648-164">The following settings are *not* copied:</span></span>

- <span data-ttu-id="93648-165">Perfís de clientes.</span><span class="sxs-lookup"><span data-stu-id="93648-165">Customer profiles.</span></span>
- <span data-ttu-id="93648-166">Credenciais da orixe de datos.</span><span class="sxs-lookup"><span data-stu-id="93648-166">Data source credentials.</span></span> <span data-ttu-id="93648-167">Deberá proporcionar as credenciais para cada orixe de datos e actualizar as fontes de datos manualmente.</span><span class="sxs-lookup"><span data-stu-id="93648-167">You'll have to provide the credentials for every data source and refresh the data sources manually.</span></span>
- <span data-ttu-id="93648-168">Fontes de datos do cartafol Common Data Model e lago xestionado por Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="93648-168">Data sources from Common Data Model folder and Common Data Service managed lake.</span></span> <span data-ttu-id="93648-169">Terá que crear esas orixes de datos manualmente co mesmo nome que no ambiente de orixe.</span><span class="sxs-lookup"><span data-stu-id="93648-169">You'll have to create those data sources manually with the same name as in the source environment.</span></span>

<span data-ttu-id="93648-170">Cando copie un ambiente, verá unha mensaxe de confirmación de que se creou o novo contorno.</span><span class="sxs-lookup"><span data-stu-id="93648-170">When you copy an environment, you'll see a confirmation message that the new environment has been created.</span></span> <span data-ttu-id="93648-171">Seleccione **Ir a orixes de datos** para ver a lista de orixes de datos.</span><span class="sxs-lookup"><span data-stu-id="93648-171">Select **Go to data sources** to see the list of data sources.</span></span>

<span data-ttu-id="93648-172">Todas as orixes de datos mostrarán o estado **Credenciais requiridas**.</span><span class="sxs-lookup"><span data-stu-id="93648-172">All the data sources will show a **Credentials Required** status.</span></span> <span data-ttu-id="93648-173">Edite as orixes de datos e insira as credenciais para actualizalas.</span><span class="sxs-lookup"><span data-stu-id="93648-173">Edit the data sources and enter the credentials to refresh them.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="93648-174">![Orixes de datos copiadas](media/data-sources-copied.png)</span><span class="sxs-lookup"><span data-stu-id="93648-174">![Data sources copied](media/data-sources-copied.png)</span></span>

<span data-ttu-id="93648-175">Despois de actualizar as orixes de datos, diríxase a **Datos** > **Unificar**.</span><span class="sxs-lookup"><span data-stu-id="93648-175">After refreshing the data sources, go to **Data** > **Unify**.</span></span> <span data-ttu-id="93648-176">Aquí atopará a configuración do ambiente de orixe.</span><span class="sxs-lookup"><span data-stu-id="93648-176">Here you'll find settings from the source environment.</span></span> <span data-ttu-id="93648-177">Edíteos segundo sexa necesario ou seleccione **Executar** para iniciar o proceso de unificación de datos e crear a entidade de cliente unificada.</span><span class="sxs-lookup"><span data-stu-id="93648-177">Edit them as needed or select **Run** to start the data unification process and create the unified customer entity.</span></span>

<span data-ttu-id="93648-178">Cando a unificación de datos estea completa, diríxase a **Medidas** e **Segmentos** para actualizalos tamén.</span><span class="sxs-lookup"><span data-stu-id="93648-178">When the data unification is complete, go to **Measures** and **Segments** to refresh them too.</span></span>

## <a name="edit-an-existing-environment"></a><span data-ttu-id="93648-179">Editar un ambiente existente</span><span class="sxs-lookup"><span data-stu-id="93648-179">Edit an existing environment</span></span>

<span data-ttu-id="93648-180">Pode editar algúns detalles dos contornos existentes.</span><span class="sxs-lookup"><span data-stu-id="93648-180">You can edit some of the details of existing environments.</span></span>

1.  <span data-ttu-id="93648-181">Seleccione o selector de **ambiente** na cabeceira da aplicación.</span><span class="sxs-lookup"><span data-stu-id="93648-181">Select the **Environment** picker in the header of the app.</span></span>

2.  <span data-ttu-id="93648-182">Seleccione a icona de **edición**.</span><span class="sxs-lookup"><span data-stu-id="93648-182">Select the **Edit** icon.</span></span>

3. <span data-ttu-id="93648-183">Na caixa **Editar contorno**, pode actualizar o **Nome de visualización** do contorno, pero non pode cambiar a **Rexión** nin o **Tipo**.</span><span class="sxs-lookup"><span data-stu-id="93648-183">In the **Edit environment** box, you can update the environment's **Display name**, but you can't change the **Region** or **Type**.</span></span>

4. <span data-ttu-id="93648-184">Se un ambiente está configurado para almacenar datos en Azure Data Lake Storage Gen2, pode actualizar a **Clave da conta**.</span><span class="sxs-lookup"><span data-stu-id="93648-184">If an environment is configured to store data in Azure Data Lake Storage Gen2, you can update the **Account key**.</span></span> <span data-ttu-id="93648-185">Non obstante, non podes cambiar o **Nome da conta** nin o nome do **Contedor**.</span><span class="sxs-lookup"><span data-stu-id="93648-185">However, you can't change the **Account name** or **Container** name.</span></span>

5. <span data-ttu-id="93648-186">Opcionalmente, pode actualizar desde unha conexión baseada na clave de conta a unha conexión baseada en recursos ou baseada nunha subscrición.</span><span class="sxs-lookup"><span data-stu-id="93648-186">Optionally, you can update from an account key based connection to a resource-based or subscription-based connection.</span></span> <span data-ttu-id="93648-187">Unha vez actualizado, non poderá volver á clave da conta despois da actualización.</span><span class="sxs-lookup"><span data-stu-id="93648-187">Once upgraded, you cannot revert to account key after the update.</span></span> <span data-ttu-id="93648-188">Para obter máis información, consulte [Conectar información do público a unha conta de Azure Data Lake Storage Gen2 cunha entidade principal de seguranza do servizo de Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="93648-188">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="93648-189">Non pode cambiar a información do **contedor** ao actualizar a conexión.</span><span class="sxs-lookup"><span data-stu-id="93648-189">You can't change **Container** information when updating the connection.</span></span>

## <a name="reset-an-existing-environment"></a><span data-ttu-id="93648-190">Restablecer ambiente existente</span><span class="sxs-lookup"><span data-stu-id="93648-190">Reset an existing environment</span></span>

<span data-ttu-id="93648-191">Como administrador, pode restablecer un ambiente a un estado baleiro se quere eliminar todas as configuracións e eliminar os datos inxeridos.</span><span class="sxs-lookup"><span data-stu-id="93648-191">As an administrator, you can reset an environment to an empty state if you want to delete all configurations and remove the ingested data.</span></span>

1.  <span data-ttu-id="93648-192">Seleccione o selector de **ambiente** na cabeceira da aplicación.</span><span class="sxs-lookup"><span data-stu-id="93648-192">Select the **Environment** picker in the header of the app.</span></span> 

2.  <span data-ttu-id="93648-193">Seleccione o ambiente que desexa restablecer e seleccione os puntos suspensivos **...**.</span><span class="sxs-lookup"><span data-stu-id="93648-193">Select the environment you want to reset and select the ellipsis **...**.</span></span> 

3. <span data-ttu-id="93648-194">Escolla a opción **Restablecer**.</span><span class="sxs-lookup"><span data-stu-id="93648-194">Choose the **Reset** option.</span></span> 

4.  <span data-ttu-id="93648-195">Para confirmar a eliminación, introduza o nome do contorno e seleccione **Restablecer**.</span><span class="sxs-lookup"><span data-stu-id="93648-195">To confirm the deletion, enter the environment name and select **Reset**.</span></span>

## <a name="delete-an-existing-environment-available-only-for-admins"></a><span data-ttu-id="93648-196">Eliminar un ambiente existente (dispoñible só para administradores)</span><span class="sxs-lookup"><span data-stu-id="93648-196">Delete an existing environment (available only for admins)</span></span>

<span data-ttu-id="93648-197">Como administrador, pode eliminar un ambiente que administra.</span><span class="sxs-lookup"><span data-stu-id="93648-197">As an administrator, you can delete an environment you administer.</span></span>

1.  <span data-ttu-id="93648-198">Seleccione o selector de **ambiente** na cabeceira da aplicación.</span><span class="sxs-lookup"><span data-stu-id="93648-198">Select the **Environment** picker in the header of the app.</span></span>

2.  <span data-ttu-id="93648-199">Seleccione o ambiente que desexa restablecer e seleccione os puntos suspensivos **...**.</span><span class="sxs-lookup"><span data-stu-id="93648-199">Select the environment you want to reset and select the ellipsis **...**.</span></span> 

3. <span data-ttu-id="93648-200">Escolla a opción **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="93648-200">Choose the **Delete** option.</span></span> 

4.  <span data-ttu-id="93648-201">Para confirmar a eliminación, insira o nome do ambiente e seleccione **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="93648-201">To confirm the deletion, enter the environment name and select **Delete**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]