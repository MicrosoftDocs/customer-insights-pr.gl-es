---
title: Guía de mostra de predición de recomendacións de produtos
description: Utilice esta guía de mostra para probar o modelo de predición de recomendacións de produtos.
ms.date: 02/10/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: b136084316da5ae17a8428236381f69e5c21f9ea
ms.sourcegitcommit: 7b6189e47ed1f87e7ce35d40e4cf7a6730f31ef2
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 06/01/2021
ms.locfileid: "6129897"
---
# <a name="product-recommendation-prediction-preview-sample-guide"></a><span data-ttu-id="65d58-103">Guía de mostra de predición de recomendacións de produtos (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="65d58-103">Product recommendation prediction (preview) sample guide</span></span>

<span data-ttu-id="65d58-104">Guiarémolo a través dun exemplo integral de predición de recomendacións de produtos empregando os datos de exemplo fornecidos a continuación.</span><span class="sxs-lookup"><span data-stu-id="65d58-104">We'll walk you through an end to end example of product recommendation prediction using the sample data provided below.</span></span>

## <a name="scenario"></a><span data-ttu-id="65d58-105">Escenario</span><span class="sxs-lookup"><span data-stu-id="65d58-105">Scenario</span></span>

<span data-ttu-id="65d58-106">Contoso é unha empresa que produce café e máquinas de café de alta calidade, que se venden a través do sitio web Contoso Coffee.</span><span class="sxs-lookup"><span data-stu-id="65d58-106">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="65d58-107">O seu obxectivo é comprender que produtos deben recomendar aos seus clientes recorrentes.</span><span class="sxs-lookup"><span data-stu-id="65d58-107">Their goal is to understand which products should they recommend to their recurring customers.</span></span> <span data-ttu-id="65d58-108">Sabendo que clientes son máis **susceptibles a comprar**, pode axudalos a aforrar esforzos de marketing centrándose en elementos específicos.</span><span class="sxs-lookup"><span data-stu-id="65d58-108">Knowing what customers are more **likely to purchase**, can help them save marketing efforts by focusing on specific items.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="65d58-109">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="65d58-109">Prerequisites</span></span>

- <span data-ttu-id="65d58-110">Polo menos [Permisos de colaborador](permissions.md) en Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="65d58-110">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="65d58-111">Recomendámoslle que implemente os seguintes pasos [nun novo ambiente](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="65d58-111">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="65d58-112">Tarefa 1: inxerir datos</span><span class="sxs-lookup"><span data-stu-id="65d58-112">Task 1 - Ingest data</span></span>

<span data-ttu-id="65d58-113">Revise os artigos [sobre a inxestión de datos](data-sources.md) e a [importación de fontes de datos usando conectores de Power Query](connect-power-query.md) especificamente.</span><span class="sxs-lookup"><span data-stu-id="65d58-113">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="65d58-114">A seguinte información supón que está familiarizado coa inxestión de datos en xeral.</span><span class="sxs-lookup"><span data-stu-id="65d58-114">The following information assumes you familiarized with ingesting data in general.</span></span>

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="65d58-115">Inxerir datos de clientes desde a plataforma de comercio electrónico</span><span class="sxs-lookup"><span data-stu-id="65d58-115">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="65d58-116">Cree unha orixe de datos denominada **eCommerce**, escolla a opción de importación e seleccione o conector **Texto/CSV**.</span><span class="sxs-lookup"><span data-stu-id="65d58-116">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="65d58-117">Insira o URL dos contactos de comercio electrónico https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="65d58-117">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="65d58-118">Mentres edita os datos, seleccione **Transformar** e logo **Usar a primeira fila como cabeceiras**.</span><span class="sxs-lookup"><span data-stu-id="65d58-118">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="65d58-119">Actualice o tipo de datos para as columnas listadas a continuación:</span><span class="sxs-lookup"><span data-stu-id="65d58-119">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="65d58-120">**DateOfBirth**: data</span><span class="sxs-lookup"><span data-stu-id="65d58-120">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="65d58-121">**CreatedOn**: data/hora/fuso</span><span class="sxs-lookup"><span data-stu-id="65d58-121">**CreatedOn**: Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transforme a data de nacemento en data.":::

5. <span data-ttu-id="65d58-123">No campo "Nome" no panel da dereita, cambie o nome da súa orixe de datos de **Consulta** a **eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="65d58-123">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

6. <span data-ttu-id="65d58-124">**Garde** a orixe de datos.</span><span class="sxs-lookup"><span data-stu-id="65d58-124">**Save** the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="65d58-125">Inxerir datos de compra en liña</span><span class="sxs-lookup"><span data-stu-id="65d58-125">Ingest online purchase data</span></span>

1. <span data-ttu-id="65d58-126">Engada outro conxunto de datos á mesma orixe de datos de **comercio electrónico**.</span><span class="sxs-lookup"><span data-stu-id="65d58-126">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="65d58-127">Escolla o conector **Texto/CSV** de novo.</span><span class="sxs-lookup"><span data-stu-id="65d58-127">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="65d58-128">Introduza o URL para datos de **compras en liña** https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="65d58-128">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="65d58-129">Mentres edita os datos, seleccione **Transformar** e logo **Usar a primeira fila como cabeceiras**.</span><span class="sxs-lookup"><span data-stu-id="65d58-129">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="65d58-130">Actualice o tipo de datos para as columnas listadas a continuación:</span><span class="sxs-lookup"><span data-stu-id="65d58-130">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="65d58-131">**PurchasedOn**: data/hora</span><span class="sxs-lookup"><span data-stu-id="65d58-131">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="65d58-132">**TotalPrice**: moeda</span><span class="sxs-lookup"><span data-stu-id="65d58-132">**TotalPrice**: Currency</span></span>

1. <span data-ttu-id="65d58-133">No campo **Nome** do panel lateral, cambie o nome da súa orixe de datos de **Consulta** a **eCommercePurchases**.</span><span class="sxs-lookup"><span data-stu-id="65d58-133">In the **Name** field on the side pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="65d58-134">**Garde** a orixe de datos.</span><span class="sxs-lookup"><span data-stu-id="65d58-134">**Save** the data source.</span></span>


### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="65d58-135">Inxerir datos de clientes desde o esquema de fidelización</span><span class="sxs-lookup"><span data-stu-id="65d58-135">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="65d58-136">Cree unha orixe de datos denominada **LoyaltyScheme**, escolla a opción de importación e seleccione o conector **Texto/CSV**.</span><span class="sxs-lookup"><span data-stu-id="65d58-136">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="65d58-137">Insira o URL dos contactos de comercio electrónico https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="65d58-137">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="65d58-138">Mentres edita os datos, seleccione **Transformar** e logo **Usar a primeira fila como cabeceiras**.</span><span class="sxs-lookup"><span data-stu-id="65d58-138">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="65d58-139">Actualice o tipo de datos para as columnas listadas a continuación:</span><span class="sxs-lookup"><span data-stu-id="65d58-139">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="65d58-140">**DateOfBirth**: data</span><span class="sxs-lookup"><span data-stu-id="65d58-140">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="65d58-141">**RewardsPoints**: número enteiro</span><span class="sxs-lookup"><span data-stu-id="65d58-141">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="65d58-142">**CreatedOn**: data/hora</span><span class="sxs-lookup"><span data-stu-id="65d58-142">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="65d58-143">No campo **Nome** no panel da dereita, cambie o nome da súa orixe de datos de **Consulta** a **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="65d58-143">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="65d58-144">**Garde** a orixe de datos.</span><span class="sxs-lookup"><span data-stu-id="65d58-144">**Save** the data source.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="65d58-145">Tarefa 2: unificación de datos</span><span class="sxs-lookup"><span data-stu-id="65d58-145">Task 2 - Data unification</span></span>

<span data-ttu-id="65d58-146">Despois de inxerir os datos, comezamos o proceso de unificación de datos para crear un perfil de cliente unificado.</span><span class="sxs-lookup"><span data-stu-id="65d58-146">After ingesting the data, we now begin the data unification process to create a unified customer profile.</span></span> <span data-ttu-id="65d58-147">Para obter máis información, consulte [Unificación de datos](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="65d58-147">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="65d58-148">Asignar</span><span class="sxs-lookup"><span data-stu-id="65d58-148">Map</span></span>

1. <span data-ttu-id="65d58-149">Despois de inxerir os datos, asigne os contactos desde os datos de comercio electrónico e de fidelización a tipos de datos comúns.</span><span class="sxs-lookup"><span data-stu-id="65d58-149">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="65d58-150">Vaia a **Datos** > **Unificar** > **Asignar**.</span><span class="sxs-lookup"><span data-stu-id="65d58-150">Go to **Data** > **Unify** > **Map**.</span></span>

2. <span data-ttu-id="65d58-151">Seleccione as entidades que representan o perfil do cliente: **eCommerceContacts** e **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="65d58-151">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span>

   ![unificar fontes de datos de comercio electrónico e fidelización.](media/unify-ecommerce-loyalty.png)

3. <span data-ttu-id="65d58-153">Seleccione **ContactId** como clave primaria para **eCommerceContacts** e **LoyaltyID** como clave primaria para **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="65d58-153">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   ![Unificar LoyaltyId como clave principal.](media/unify-loyaltyid.png)

### <a name="match"></a><span data-ttu-id="65d58-155">Buscar coincidencias</span><span class="sxs-lookup"><span data-stu-id="65d58-155">Match</span></span>

1. <span data-ttu-id="65d58-156">Vaia ao separador **Buscar coincidencias** e seleccione **Definir orde**.</span><span class="sxs-lookup"><span data-stu-id="65d58-156">Go to the **Match** tab and select **Set Order**.</span></span>

2. <span data-ttu-id="65d58-157">No lista despregable **Primario**, escolla **eCommerceContacts: eCommerce** como fonte principal e inclúa todos os rexistros.</span><span class="sxs-lookup"><span data-stu-id="65d58-157">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

3. <span data-ttu-id="65d58-158">Na lista despregable **Entidade 2**, escolla **loyCustomers: LoyaltyScheme** e inclúa todos os rexistros.</span><span class="sxs-lookup"><span data-stu-id="65d58-158">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   ![unificar coincidencias de comercio electrónico e fidelización.](media/unify-match-order.png)

4. <span data-ttu-id="65d58-160">Seleccione **Crear unha nova regra**</span><span class="sxs-lookup"><span data-stu-id="65d58-160">Select **Create a new rule**</span></span>

5. <span data-ttu-id="65d58-161">Engada a súa primeira condición usando FullName.</span><span class="sxs-lookup"><span data-stu-id="65d58-161">Add your first condition using FullName.</span></span>

   - <span data-ttu-id="65d58-162">Para eCommerceContacts, seleccione **FullName** no menú despregable.</span><span class="sxs-lookup"><span data-stu-id="65d58-162">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="65d58-163">Para loyCustomers, seleccione **FullName** no menú despregable.</span><span class="sxs-lookup"><span data-stu-id="65d58-163">For loyCustomers select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="65d58-164">Seleccione o menús despregable **Normalizar** e escolla **Tipo (teléfono, nome, enderezo...)**.</span><span class="sxs-lookup"><span data-stu-id="65d58-164">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   - <span data-ttu-id="65d58-165">Defina o **Nivel de precisión**: **Básico** e **Valor**: **Alto**.</span><span class="sxs-lookup"><span data-stu-id="65d58-165">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

6. <span data-ttu-id="65d58-166">Introduza o nome **FullName, Email** para a nova regra.</span><span class="sxs-lookup"><span data-stu-id="65d58-166">Enter the name **FullName, Email** for the new rule.</span></span>

   - <span data-ttu-id="65d58-167">Engada unha segunda condición para o enderezo de correo electrónico seleccionando **Engadir condición**</span><span class="sxs-lookup"><span data-stu-id="65d58-167">Add a second condition for email address by selecting **Add Condition**</span></span>
   - <span data-ttu-id="65d58-168">Para os eCommerceContacts da entidade, escolla **EMail** no menú despregable.</span><span class="sxs-lookup"><span data-stu-id="65d58-168">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   - <span data-ttu-id="65d58-169">Para os loyCustomers da entidade, escolla **EMail** no menú despregable.</span><span class="sxs-lookup"><span data-stu-id="65d58-169">For entity loyCustomers, choose **EMail** in the drop-down.</span></span>
   - <span data-ttu-id="65d58-170">Deixe Normalizar en branco.</span><span class="sxs-lookup"><span data-stu-id="65d58-170">Leave Normalize blank.</span></span>
   - <span data-ttu-id="65d58-171">Defina o **Nivel de precisión**: **Básico** e **Valor**: **Alto**.</span><span class="sxs-lookup"><span data-stu-id="65d58-171">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   ![Unificar a regra de coincidencia para o nome e o correo electrónico.](media/unify-match-rule.png)

7. <span data-ttu-id="65d58-173">Seleccione **Gardar** e **Executar**.</span><span class="sxs-lookup"><span data-stu-id="65d58-173">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="65d58-174">Combinación</span><span class="sxs-lookup"><span data-stu-id="65d58-174">Merge</span></span>

1. <span data-ttu-id="65d58-175">Vaia ao separador **Combinar**.</span><span class="sxs-lookup"><span data-stu-id="65d58-175">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="65d58-176">No **ContactId** da entidade **loyCustomers**, cambie o nome de visualización a **ContactIdLOYALTY** para diferencialo dos outros identificadores inxeridos.</span><span class="sxs-lookup"><span data-stu-id="65d58-176">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   ![renomear contactid do identificador de fidelidade.](media/unify-merge-contactid.png)

1. <span data-ttu-id="65d58-178">Seleccione **Gardar** e **Executar** para iniciar o proceso de unión.</span><span class="sxs-lookup"><span data-stu-id="65d58-178">Select **Save** and **Run** to start the Merge Process.</span></span>

## <a name="task-3---configure-product-recommendation-prediction"></a><span data-ttu-id="65d58-179">Tarefa 3: configurar a predición de recomendacións de produtos</span><span class="sxs-lookup"><span data-stu-id="65d58-179">Task 3 - Configure product recommendation prediction</span></span>

<span data-ttu-id="65d58-180">Cos perfís de clientes unificados no seu lugar, agora podemos executar a predición de abandono de subscricións.</span><span class="sxs-lookup"><span data-stu-id="65d58-180">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span>

1. <span data-ttu-id="65d58-181">Vaia a **Intelixencia** > **Predición** e escolla **Recomendación de produtos**.</span><span class="sxs-lookup"><span data-stu-id="65d58-181">Go to **Intelligence** > **Prediction** choose **Product recommendation**.</span></span>

1. <span data-ttu-id="65d58-182">Seleccione **Comezar**.</span><span class="sxs-lookup"><span data-stu-id="65d58-182">Select **Get started**.</span></span>

1. <span data-ttu-id="65d58-183">Dea nome ao modelo **Predición do modelo de recomendación de produtos de OOB** e a entidade de saída **OOBProductRecommendationModelPrediction**.</span><span class="sxs-lookup"><span data-stu-id="65d58-183">Name the model **OOB Product Recommendation Model Prediction** and the output entity **OOBProductRecommendationModelPrediction**.</span></span>

1. <span data-ttu-id="65d58-184">Defina tres condicións para o modelo:</span><span class="sxs-lookup"><span data-stu-id="65d58-184">Define three conditions for the model:</span></span>

   - <span data-ttu-id="65d58-185">**Número de produtos**: Configure este valor en **5**.</span><span class="sxs-lookup"><span data-stu-id="65d58-185">**Number of products**: Set this value to **5**.</span></span> <span data-ttu-id="65d58-186">Esta configuración define cantos produtos desexa recomendar aos seus clientes.</span><span class="sxs-lookup"><span data-stu-id="65d58-186">This setting defines how many products you want to recommend to your customers.</span></span>

   - <span data-ttu-id="65d58-187">**Compras repetidas esperadas**: seleccione **Si** para indicar que quere incluír produtos na recomendación que os seus clientes compraron con anterioridade.</span><span class="sxs-lookup"><span data-stu-id="65d58-187">**Repeat purchases expected**: Select **Yes** to indicate that you want to include products in the recommendation that your customers have purchased before.</span></span>

   - <span data-ttu-id="65d58-188">**Ventá para ver días pasados:** Seleccione polo menos **365 días**.</span><span class="sxs-lookup"><span data-stu-id="65d58-188">**Look back window:** Select at least **365 days**.</span></span> <span data-ttu-id="65d58-189">Esta configuración define o número de días pasados que o modelo mira na actividade do cliente que se van usar como entrada para as súas recomendacións.</span><span class="sxs-lookup"><span data-stu-id="65d58-189">This setting defines how far the model will look back at the customer's activity to use it as input to their recommendations.</span></span>
   
   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Preferencias do modelo de recomendación de produtos.":::

1. <span data-ttu-id="65d58-191">Seleccione **Datos requiridos** e seleccione **Engadir datos** para o historial de compras.</span><span class="sxs-lookup"><span data-stu-id="65d58-191">Select **Required data** and select **Add data** for purchase history.</span></span>

1. <span data-ttu-id="65d58-192">Engada a entidade **eCommercePurchases : eCommerce** e asigne os campos de comercio electrónico aos campos correspondentes requiridos polo modelo.</span><span class="sxs-lookup"><span data-stu-id="65d58-192">Add the **eCommercePurchases : eCommerce** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="65d58-193">Una a entidade **eCommercePurchases : eCommerce** con **eCommerceContacts : eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="65d58-193">Join the **eCommercePurchases : eCommerce** entity with **eCommerceContacts : eCommerce**.</span></span>

   ![Unir entidades de comercio electrónico.](media/model-purchase-join.png)

1. <span data-ttu-id="65d58-195">Seleccione **Seguinte** para establecer a programación do modelo.</span><span class="sxs-lookup"><span data-stu-id="65d58-195">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="65d58-196">O modelo necesita adestrarse regularmente para aprender novos padróns cando se inxiren novos datos.</span><span class="sxs-lookup"><span data-stu-id="65d58-196">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="65d58-197">Para este exemplo, seleccione **Mensual**.</span><span class="sxs-lookup"><span data-stu-id="65d58-197">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="65d58-198">Despois de revisar todos os detalles, seleccione **Gardar e executar**.</span><span class="sxs-lookup"><span data-stu-id="65d58-198">After reviewing all the details, select **Save and Run**.</span></span>


## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="65d58-199">Tarefa 4: revisar resultados e explicacións do modelo</span><span class="sxs-lookup"><span data-stu-id="65d58-199">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="65d58-200">Deixe que o modelo complete o adestramento e a puntuación dos datos.</span><span class="sxs-lookup"><span data-stu-id="65d58-200">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="65d58-201">Agora pode revisar as explicacións do modelo de recomendación de produtos.</span><span class="sxs-lookup"><span data-stu-id="65d58-201">You can now review the product recommendation model explanations.</span></span> <span data-ttu-id="65d58-202">Para obter máis información, consulte [Revisar o estado e os resultados dunha predición](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="65d58-202">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-purchased-products"></a><span data-ttu-id="65d58-203">Tarefa 5: crear un segmento de produtos moi comprados</span><span class="sxs-lookup"><span data-stu-id="65d58-203">Task 5 - Create a segment of high purchased products</span></span>

<span data-ttu-id="65d58-204">Executar o modelo de produción crea unha nova entidade na que pode ver en **Datos** > **Entidades**.</span><span class="sxs-lookup"><span data-stu-id="65d58-204">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>

<span data-ttu-id="65d58-205">Pode crear un novo segmento baseado na entidade creada polo modelo.</span><span class="sxs-lookup"><span data-stu-id="65d58-205">You can create a new segment based on the entity created by the model.</span></span>

1. <span data-ttu-id="65d58-206">Vaia a **Segmentos**.</span><span class="sxs-lookup"><span data-stu-id="65d58-206">Go to **Segments**.</span></span> <span data-ttu-id="65d58-207">Seleccione **Novo** e elixa **Crear a partir de** > **Intelixencia**.</span><span class="sxs-lookup"><span data-stu-id="65d58-207">Select **New** and choose **Create from** > **Intelligence**.</span></span>

   ![Creación dun segmento coa saída do modelo.](media/segment-intelligence.png)

1. <span data-ttu-id="65d58-209">Seleccione o extremo **OOBProductRecommendationModelPrediction** e defina o segmento:</span><span class="sxs-lookup"><span data-stu-id="65d58-209">Select the **OOBProductRecommendationModelPrediction** endpoint and define the segment:</span></span>

   - <span data-ttu-id="65d58-210">Campo: ProductID</span><span class="sxs-lookup"><span data-stu-id="65d58-210">Field: ProductID</span></span>
   - <span data-ttu-id="65d58-211">Operador: Valor</span><span class="sxs-lookup"><span data-stu-id="65d58-211">Operator: Value</span></span>
   - <span data-ttu-id="65d58-212">Valor: seleccione os tres identificadores de produto principais</span><span class="sxs-lookup"><span data-stu-id="65d58-212">Value: Select the top three product IDs</span></span>

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="Cree un segmento a partir dos resultados do modelo.":::

<span data-ttu-id="65d58-214">Agora ten un segmento que se actualiza dinamicamente e identifica aos clientes que están máis dispostos a mercar os tres produtos máis recomendados</span><span class="sxs-lookup"><span data-stu-id="65d58-214">You now have a segment that is dynamically updated which identifies the customers who are more willing to purchase the three most recommended products</span></span> 

<span data-ttu-id="65d58-215">Para ver máis información, consulte: [Creación e xestión de segmentos](segments.md).</span><span class="sxs-lookup"><span data-stu-id="65d58-215">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
