---
title: Crear e xestionar ambientes
description: Aprenda a rexistrarse no servizo e a xestionar contornos.
ms.date: 11/10/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
ms.reviewer: nimagen
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 010336445d0825a7ff82d1b7a65702fc12245788
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644131"
---
# <a name="manage-environments"></a><span data-ttu-id="e6ba1-103">Xestionar ambientes</span><span class="sxs-lookup"><span data-stu-id="e6ba1-103">Manage environments</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="e6ba1-104">Este artigo explica como crear unha nova organización e como fornecer un ambiente.</span><span class="sxs-lookup"><span data-stu-id="e6ba1-104">This article explains how to create a new organization and how to provision an environment.</span></span>

## <a name="sign-up-and-create-an-organization"></a><span data-ttu-id="e6ba1-105">Rexistrarse e crear unha organización</span><span class="sxs-lookup"><span data-stu-id="e6ba1-105">Sign up and create an organization</span></span>

1. <span data-ttu-id="e6ba1-106">Vaia ao sitio web [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/).</span><span class="sxs-lookup"><span data-stu-id="e6ba1-106">Go to the [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/) website.</span></span>

2. <span data-ttu-id="e6ba1-107">Seleccione **Comezar**.</span><span class="sxs-lookup"><span data-stu-id="e6ba1-107">Select **Get Started**.</span></span>

3. <span data-ttu-id="e6ba1-108">Escolla o escenario de rexistro preferido e seleccione a ligazón correspondente.</span><span class="sxs-lookup"><span data-stu-id="e6ba1-108">Choose your preferred sign-up scenario and select the corresponding link.</span></span>

4. <span data-ttu-id="e6ba1-109">Acepte os termos e condicións e seleccione **Continuar** para comezar a crear a organización.</span><span class="sxs-lookup"><span data-stu-id="e6ba1-109">Accept the terms and conditions and select **Continue** to start creating the organization.</span></span>

5. <span data-ttu-id="e6ba1-110">Despois de crear o ambiente, redirixiráselle a [Customer Insights](https://home.ci.ai.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="e6ba1-110">After the environment is created, you'll be redirected to [Customer Insights](https://home.ci.ai.dynamics.com).</span></span>

6. <span data-ttu-id="e6ba1-111">Use o contorno de demostración para explorar a aplicación ou crear un novo contorno seguindo os pasos da seguinte sección.</span><span class="sxs-lookup"><span data-stu-id="e6ba1-111">Use the demo environment to explore the app, or create a new environment by following the steps in the next section.</span></span>

7. <span data-ttu-id="e6ba1-112">Despois de especificar a configuración do ambiente, seleccione **Crear**.</span><span class="sxs-lookup"><span data-stu-id="e6ba1-112">After specifying the environment settings, select **Create**.</span></span>

8. <span data-ttu-id="e6ba1-113">Iniciará sesión despois de que o ambiente se cree correctamente.</span><span class="sxs-lookup"><span data-stu-id="e6ba1-113">You'll be signed in after the environment was created successfully.</span></span>

## <a name="create-an-environment-in-an-existing-organization"></a><span data-ttu-id="e6ba1-114">Crear un ambiente nunha organización existente</span><span class="sxs-lookup"><span data-stu-id="e6ba1-114">Create an environment in an existing organization</span></span>

<span data-ttu-id="e6ba1-115">Existen dúas formas de crear un ambiente novo.</span><span class="sxs-lookup"><span data-stu-id="e6ba1-115">There are two ways to create a new environment.</span></span> <span data-ttu-id="e6ba1-116">Pode especificar unha configuración completamente nova ou pode copiar algúns axustes de configuración dun ambiente existente.</span><span class="sxs-lookup"><span data-stu-id="e6ba1-116">You can either specify an entirely new configuration, or you can copy some configuration settings from an existing environment.</span></span>

<span data-ttu-id="e6ba1-117">Para crear un ambiente:</span><span class="sxs-lookup"><span data-stu-id="e6ba1-117">To create an environment:</span></span>

1. <span data-ttu-id="e6ba1-118">Seleccione o símbolo **Configuración** na cabeceira da aplicación.</span><span class="sxs-lookup"><span data-stu-id="e6ba1-118">Select the **Settings** symbol in the header of the app.</span></span>

1. <span data-ttu-id="e6ba1-119">Seleccione **Novo ambiente**.</span><span class="sxs-lookup"><span data-stu-id="e6ba1-119">Select **New environment**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e6ba1-120">![Configuración de ambientes](media/environment-settings-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="e6ba1-120">![Environment settings](media/environment-settings-dialog.png)</span></span>

1. <span data-ttu-id="e6ba1-121">No diálogo **Crear novo ambiente**, seleccione **Novo ambiente**.</span><span class="sxs-lookup"><span data-stu-id="e6ba1-121">In the **Create new environment** dialog, select **New environment**.</span></span>

   <span data-ttu-id="e6ba1-122">Se quere [copiar datos do ambiente actual](#additional-considerations-for-copy-configuration-preview), seleccione **Copiar do ambiente existente**.</span><span class="sxs-lookup"><span data-stu-id="e6ba1-122">If you want to [copy data from the current environment](#additional-considerations-for-copy-configuration-preview), select **Copy from existing environment**.</span></span> <span data-ttu-id="e6ba1-123">Verá unha lista de todos os ambientes dispoñibles da súa organización de onde pode copiar datos.</span><span class="sxs-lookup"><span data-stu-id="e6ba1-123">You'll see a list of all available environments in your organization where you can copy data from.</span></span>

1. <span data-ttu-id="e6ba1-124">Indique os seguintes detalles:</span><span class="sxs-lookup"><span data-stu-id="e6ba1-124">Provide the following details:</span></span>
   - <span data-ttu-id="e6ba1-125">**Nome**: O nome deste ambiente.</span><span class="sxs-lookup"><span data-stu-id="e6ba1-125">**Name**: The name for this environment.</span></span> <span data-ttu-id="e6ba1-126">Este campo xa está cuberto se copiou un ambiente existente, pero pode cambialo.</span><span class="sxs-lookup"><span data-stu-id="e6ba1-126">This field is already filled in if you've copied an existing environment, but you can change it.</span></span>
   - <span data-ttu-id="e6ba1-127">**Rexión**: a rexión na que se despregou e aloxou o servizo.</span><span class="sxs-lookup"><span data-stu-id="e6ba1-127">**Region**: The region into which the service is deployed and hosted.</span></span>
   - <span data-ttu-id="e6ba1-128">**Tipo**: selecciona se desexa crear un contorno de produción ou de illamento de procesos.</span><span class="sxs-lookup"><span data-stu-id="e6ba1-128">**Type**: Select whether you want to create a Production or Sandbox environment.</span></span>

2. <span data-ttu-id="e6ba1-129">Opcionalmente, pode seleccionar **Configuración avanzada**:</span><span class="sxs-lookup"><span data-stu-id="e6ba1-129">Optionally, you can select **Advanced settings**:</span></span>

   - <span data-ttu-id="e6ba1-130">**Gardar todos os datos en**: especifique onde desexa almacenar os datos de saída xerados de Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="e6ba1-130">**Save all data to**: Specifies where you want to store the output data generated from Customer Insights.</span></span> <span data-ttu-id="e6ba1-131">Terá dúas opcións: **Almacenamento de Customer Insights** (un Azure Data Lake xestionado polo equipo de Customer Insights) e **Azure Data Lake Storage Gen2** (o seu propio Azure Data Lake Storage).</span><span class="sxs-lookup"><span data-stu-id="e6ba1-131">You'll have two options: **Customer Insights storage** (an Azure Data Lake managed by the Customer Insights team) and **Azure Data Lake Storage Gen2** (your own Azure Data Lake Storage).</span></span> <span data-ttu-id="e6ba1-132">Por defecto, a opción de almacenamento de Customer Insights está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="e6ba1-132">By default, the Customer Insights storage option is selected.</span></span>

   > [!NOTE]
   > <span data-ttu-id="e6ba1-133">Ao gardar datos en Azure Data Lake Storage, acepta que os datos se transfiran e almacenen na localización xeográfica adecuada para esa conta de Azure Storage, que pode ser diferente á da conta na que están almacenados os datos en Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="e6ba1-133">By saving data to Azure Data Lake Storage, you agree that data will be transferred to and stored in the appropriate geographic location for that Azure storage account, which may differ from where data is stored in Dynamics 365 Customer Insights.</span></span> [<span data-ttu-id="e6ba1-134">Obteña máis información no Centro de confianza de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e6ba1-134">Learn more at the Microsoft Trust Center.</span></span>](https://www.microsoft.com/trust-center)
   >
   > <span data-ttu-id="e6ba1-135">Na actualidade, as entidades inxeridas sempre se almacenan no lago de datos xestionado por Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="e6ba1-135">Currently, ingested entities are always stored in the Customer Insights managed data lake.</span></span>
   > <span data-ttu-id="e6ba1-136">Só admitimos contas de almacenamento de Azure Data Lake Gen2 da mesma rexión de Azure que seleccionou ao crear o ambiente.</span><span class="sxs-lookup"><span data-stu-id="e6ba1-136">We support only Azure Data Lake Gen2 storage accounts from the same Azure region you selected when creating the environment.</span></span>
   > <span data-ttu-id="e6ba1-137">Só admitimos contas de almacenamento de Azure Data Lake Gen2 compatibles co Espazo de nomes xerárquicos (HNS).</span><span class="sxs-lookup"><span data-stu-id="e6ba1-137">We support only Azure Data Lake Gen2 Hierarchical Name Space (HNS) enabled storage accounts.</span></span>

   - <span data-ttu-id="e6ba1-138">Para a opción de Azure Data Lake Storage Gen2, pode escoller entre unha opción baseada en recursos e unha opción baseada na subscrición para a autenticación.</span><span class="sxs-lookup"><span data-stu-id="e6ba1-138">For the Azure Data Lake Storage Gen2 option, you can choose between a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="e6ba1-139">Para obter máis información, consulte [Conectar información do público a unha conta de Azure Data Lake Storage Gen2 cunha entidade principal de seguranza do servizo de Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="e6ba1-139">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="e6ba1-140">O nome do **contedor** non se pode cambiar e será "customerinsights".</span><span class="sxs-lookup"><span data-stu-id="e6ba1-140">The **Container** name can't be changed and will be "customerinsights".</span></span>
   
   - <span data-ttu-id="e6ba1-141">Se quere usar [predicións](predictions.md), introduza o URL da instancia de Common Data Service no campo **Enderezo do servidor** en **Usa predicións**.</span><span class="sxs-lookup"><span data-stu-id="e6ba1-141">If you want to use [predictions](predictions.md), enter the Common Data Service instance URL in the **Server address** field under **Use predictions**.</span></span>

   <span data-ttu-id="e6ba1-142">Cando execute procesos, como a inxestión de datos ou a creación de segmentos, crearanse os cartafoles correspondentes na conta de almacenamento que especificou anteriormente.</span><span class="sxs-lookup"><span data-stu-id="e6ba1-142">When you run processes, such as data ingestion or segment creation, corresponding folders will be created in the storage account you specified above.</span></span> <span data-ttu-id="e6ba1-143">Os ficheiros de datos e os ficheiros model.json crearanse e engadiranse aos respectivos subcartafoles en función do proceso que execute.</span><span class="sxs-lookup"><span data-stu-id="e6ba1-143">Data files and model.json files will be created and added to the respective subfolders based on the process you run.</span></span>

   <span data-ttu-id="e6ba1-144">Se crea varios contornos de Customer Insights e elixe gardar as entidades de saída deses ambientes na súa conta de almacenamento, crearanse cartafoles separados para cada contorno con ci_<environmentid> no contedor.</span><span class="sxs-lookup"><span data-stu-id="e6ba1-144">If you create multiple environments of Customer Insights and choose to save the output entities from those environments in your storage account, separate folders will be created for each environment with ci_<environmentid> in the container.</span></span>

### <a name="additional-considerations-for-copy-configuration-preview"></a><span data-ttu-id="e6ba1-145">Consideracións adicionais para a configuración da copia (previsualización)</span><span class="sxs-lookup"><span data-stu-id="e6ba1-145">Additional considerations for copy configuration (preview)</span></span>

<span data-ttu-id="e6ba1-146">Copiaranse os seguintes axustes de configuración:</span><span class="sxs-lookup"><span data-stu-id="e6ba1-146">The following configuration settings are copied:</span></span>

- <span data-ttu-id="e6ba1-147">Configuracións de funcións</span><span class="sxs-lookup"><span data-stu-id="e6ba1-147">Feature configurations</span></span>
- <span data-ttu-id="e6ba1-148">Orixes de datos importadas/incorporadas</span><span class="sxs-lookup"><span data-stu-id="e6ba1-148">Inegsted/imported data sources</span></span>
- <span data-ttu-id="e6ba1-149">Configuración da unificación de datos (mapa, coincidencia, combinación)</span><span class="sxs-lookup"><span data-stu-id="e6ba1-149">Data unification (Map, Match, Merge) configuration</span></span>
- <span data-ttu-id="e6ba1-150">Segmentos</span><span class="sxs-lookup"><span data-stu-id="e6ba1-150">Segments</span></span>
- <span data-ttu-id="e6ba1-151">Medidas</span><span class="sxs-lookup"><span data-stu-id="e6ba1-151">Measures</span></span>
- <span data-ttu-id="e6ba1-152">Relacións</span><span class="sxs-lookup"><span data-stu-id="e6ba1-152">Relationships</span></span>
- <span data-ttu-id="e6ba1-153">Actividades</span><span class="sxs-lookup"><span data-stu-id="e6ba1-153">Activities</span></span>
- <span data-ttu-id="e6ba1-154">Buscar e filtrar índice</span><span class="sxs-lookup"><span data-stu-id="e6ba1-154">Search & filter Index</span></span>
- <span data-ttu-id="e6ba1-155">Exportar destinos</span><span class="sxs-lookup"><span data-stu-id="e6ba1-155">Export destinations</span></span>
- <span data-ttu-id="e6ba1-156">Actualización programada</span><span class="sxs-lookup"><span data-stu-id="e6ba1-156">Scheduled refresh</span></span>
- <span data-ttu-id="e6ba1-157">Enriquecementos</span><span class="sxs-lookup"><span data-stu-id="e6ba1-157">Enrichments</span></span>
- <span data-ttu-id="e6ba1-158">Xestión de modelos</span><span class="sxs-lookup"><span data-stu-id="e6ba1-158">Model management</span></span>
- <span data-ttu-id="e6ba1-159">Atribución de roles</span><span class="sxs-lookup"><span data-stu-id="e6ba1-159">Role assignments</span></span>

<span data-ttu-id="e6ba1-160">*Non* se copiarán os seguintes axustes:</span><span class="sxs-lookup"><span data-stu-id="e6ba1-160">The following settings are *not* copied:</span></span>

- <span data-ttu-id="e6ba1-161">Perfís de clientes.</span><span class="sxs-lookup"><span data-stu-id="e6ba1-161">Customer profiles.</span></span>
- <span data-ttu-id="e6ba1-162">Credenciais da orixe de datos.</span><span class="sxs-lookup"><span data-stu-id="e6ba1-162">Data source credentials.</span></span> <span data-ttu-id="e6ba1-163">Deberá proporcionar as credenciais para cada orixe de datos e actualizar as fontes de datos manualmente.</span><span class="sxs-lookup"><span data-stu-id="e6ba1-163">You'll have to provide the credentials for every data source and refresh the data sources manually.</span></span>
- <span data-ttu-id="e6ba1-164">Fontes de datos do cartafol Common Data Model e lago xestionado por Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="e6ba1-164">Data sources from Common Data Model folder and Common Data Service managed lake.</span></span> <span data-ttu-id="e6ba1-165">Terá que crear esas orixes de datos manualmente co mesmo nome que no ambiente de orixe.</span><span class="sxs-lookup"><span data-stu-id="e6ba1-165">You'll have to create those data sources manually with the same name as in the source environment.</span></span>

<span data-ttu-id="e6ba1-166">Cando copie un ambiente, verá unha mensaxe de confirmación de que se creou o novo contorno.</span><span class="sxs-lookup"><span data-stu-id="e6ba1-166">When you copy an environment, you'll see a confirmation message that the new environment has been created.</span></span> <span data-ttu-id="e6ba1-167">Seleccione **Ir a orixes de datos** para ver a lista de orixes de datos.</span><span class="sxs-lookup"><span data-stu-id="e6ba1-167">Select **Go to data sources** to see the list of data sources.</span></span>

<span data-ttu-id="e6ba1-168">Todas as orixes de datos mostrarán o estado **Credenciais requiridas**.</span><span class="sxs-lookup"><span data-stu-id="e6ba1-168">All the data sources will show a **Credentials Required** status.</span></span> <span data-ttu-id="e6ba1-169">Edite as orixes de datos e insira as credenciais para actualizalas.</span><span class="sxs-lookup"><span data-stu-id="e6ba1-169">Edit the data sources and enter the credentials to refresh them.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="e6ba1-170">![Orixes de datos copiadas](media/data-sources-copied.png)</span><span class="sxs-lookup"><span data-stu-id="e6ba1-170">![Data sources copied](media/data-sources-copied.png)</span></span>

<span data-ttu-id="e6ba1-171">Despois de actualizar as orixes de datos, diríxase a **Datos** > **Unificar**.</span><span class="sxs-lookup"><span data-stu-id="e6ba1-171">After refreshing the data sources, go to **Data** > **Unify**.</span></span> <span data-ttu-id="e6ba1-172">Aquí atopará a configuración do ambiente de orixe.</span><span class="sxs-lookup"><span data-stu-id="e6ba1-172">Here you'll find settings from the source environment.</span></span> <span data-ttu-id="e6ba1-173">Edíteos segundo sexa necesario ou seleccione **Executar** para iniciar o proceso de unificación de datos e crear a entidade de cliente unificada.</span><span class="sxs-lookup"><span data-stu-id="e6ba1-173">Edit them as needed or select **Run** to start the data unification process and create the unified customer entity.</span></span>

<span data-ttu-id="e6ba1-174">Cando a unificación de datos estea completa, diríxase a **Medidas** e **Segmentos** para actualizalos tamén.</span><span class="sxs-lookup"><span data-stu-id="e6ba1-174">When the data unification is complete, go to **Measures** and **Segments** to refresh them too.</span></span>

## <a name="edit-an-existing-environment"></a><span data-ttu-id="e6ba1-175">Editar un ambiente existente</span><span class="sxs-lookup"><span data-stu-id="e6ba1-175">Edit an existing environment</span></span>

<span data-ttu-id="e6ba1-176">Pode editar algúns detalles dos contornos existentes.</span><span class="sxs-lookup"><span data-stu-id="e6ba1-176">You can edit some of the details of existing environments.</span></span>

1. <span data-ttu-id="e6ba1-177">Vaia a **Administración** > **Sistema** > **Acerca de**.</span><span class="sxs-lookup"><span data-stu-id="e6ba1-177">Go to **Admin** > **System** > **About**.</span></span>

2. <span data-ttu-id="e6ba1-178">Seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="e6ba1-178">Select **Edit**.</span></span>

3. <span data-ttu-id="e6ba1-179">Pode actualizar o **Nome para mostrar** do ambiente, pero non pode cambiar a **Rexión** ou o **Tipo**.</span><span class="sxs-lookup"><span data-stu-id="e6ba1-179">You can update the environment's **Display name**, but you can't change the **Region** or **Type**.</span></span>

4. <span data-ttu-id="e6ba1-180">Se un ambiente está configurado para almacenar datos en Azure Data Lake Storage Gen2, pode actualizar a **Clave da conta**.</span><span class="sxs-lookup"><span data-stu-id="e6ba1-180">If an environment is configured to store data in Azure Data Lake Storage Gen2, you can update the **Account key**.</span></span> <span data-ttu-id="e6ba1-181">Non obstante, non podes cambiar o **Nome da conta** nin o nome do **Contedor**.</span><span class="sxs-lookup"><span data-stu-id="e6ba1-181">However, you can't change the **Account name** or **Container** name.</span></span>

5. <span data-ttu-id="e6ba1-182">Opcionalmente, pode actualizar desde unha conexión baseada na clave de conta a unha conexión baseada en recursos ou baseada nunha subscrición.</span><span class="sxs-lookup"><span data-stu-id="e6ba1-182">Optionally, you can update from an account key based connection to a resource-based or subscription-based connection.</span></span> <span data-ttu-id="e6ba1-183">Unha vez actualizado, non poderá volver á clave da conta despois da actualización.</span><span class="sxs-lookup"><span data-stu-id="e6ba1-183">Once upgraded, you cannot revert to account key after the update.</span></span> <span data-ttu-id="e6ba1-184">Para obter máis información, consulte [Conectar información do público a unha conta de Azure Data Lake Storage Gen2 cunha entidade principal de seguranza do servizo de Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="e6ba1-184">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="e6ba1-185">Non pode cambiar a información do **contedor** ao actualizar a conexión.</span><span class="sxs-lookup"><span data-stu-id="e6ba1-185">You can't change **Container** information when updating the connection.</span></span>

## <a name="reset-an-existing-environment"></a><span data-ttu-id="e6ba1-186">Restablecer ambiente existente</span><span class="sxs-lookup"><span data-stu-id="e6ba1-186">Reset an existing environment</span></span>

<span data-ttu-id="e6ba1-187">Pode restablecer un ambiente a un estado baleiro se quere eliminar todas as configuracións e eliminar os datos inxeridos.</span><span class="sxs-lookup"><span data-stu-id="e6ba1-187">You can reset an environment to an empty state if you want to delete all configurations and remove the ingested data.</span></span>

1.  <span data-ttu-id="e6ba1-188">Vaia a **Administración** > **Sistema** > **Acerca de**.</span><span class="sxs-lookup"><span data-stu-id="e6ba1-188">Go to **Admin** > **System** > **About**.</span></span>

2.  <span data-ttu-id="e6ba1-189">Seleccione **Restablecer**.</span><span class="sxs-lookup"><span data-stu-id="e6ba1-189">Select **Reset**.</span></span> 

3.  <span data-ttu-id="e6ba1-190">Para confirmar a eliminación, introduza o nome do contorno e seleccione **Restablecer**.</span><span class="sxs-lookup"><span data-stu-id="e6ba1-190">To confirm the deletion, enter the environment name and select **Reset**.</span></span>


## <a name="delete-an-existing-environment"></a><span data-ttu-id="e6ba1-191">Eliminar un ambiente existente</span><span class="sxs-lookup"><span data-stu-id="e6ba1-191">Delete an existing environment</span></span>

1. <span data-ttu-id="e6ba1-192">Vaia a **Administración** > **Sistema** > **Acerca de**.</span><span class="sxs-lookup"><span data-stu-id="e6ba1-192">Go to **Admin** > **System** > **About**.</span></span>

1. <span data-ttu-id="e6ba1-193">Seleccione **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="e6ba1-193">Select **Delete**.</span></span>

1. <span data-ttu-id="e6ba1-194">Para confirmar a eliminación, insira o nome do ambiente e seleccione **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="e6ba1-194">To confirm the deletion, enter the environment name and select **Delete**.</span></span>
