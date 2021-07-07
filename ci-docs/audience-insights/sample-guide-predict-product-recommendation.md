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
ms.openlocfilehash: a85ee598ec747d0594755314e83a127ce0f2af95
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306164"
---
# <a name="product-recommendation-prediction-preview-sample-guide"></a><span data-ttu-id="2f908-103">Guía de mostra de predición de recomendacións de produtos (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="2f908-103">Product recommendation prediction (preview) sample guide</span></span>

<span data-ttu-id="2f908-104">Guiarémolo a través dun exemplo integral de predición de recomendacións de produtos empregando os datos de exemplo fornecidos a continuación.</span><span class="sxs-lookup"><span data-stu-id="2f908-104">We'll walk you through an end to end example of product recommendation prediction using the sample data provided below.</span></span>

## <a name="scenario"></a><span data-ttu-id="2f908-105">Escenario</span><span class="sxs-lookup"><span data-stu-id="2f908-105">Scenario</span></span>

<span data-ttu-id="2f908-106">Contoso é unha empresa que produce café e máquinas de café de alta calidade, que se venden a través do sitio web Contoso Coffee.</span><span class="sxs-lookup"><span data-stu-id="2f908-106">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="2f908-107">O seu obxectivo é comprender que produtos deben recomendar aos seus clientes recorrentes.</span><span class="sxs-lookup"><span data-stu-id="2f908-107">Their goal is to understand which products should they recommend to their recurring customers.</span></span> <span data-ttu-id="2f908-108">Sabendo que clientes son máis **susceptibles a comprar**, pode axudalos a aforrar esforzos de marketing centrándose en elementos específicos.</span><span class="sxs-lookup"><span data-stu-id="2f908-108">Knowing what customers are more **likely to purchase**, can help them save marketing efforts by focusing on specific items.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2f908-109">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="2f908-109">Prerequisites</span></span>

- <span data-ttu-id="2f908-110">Polo menos [Permisos de colaborador](permissions.md) en Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="2f908-110">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="2f908-111">Recomendámoslle que implemente os seguintes pasos [nun novo ambiente](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="2f908-111">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="2f908-112">Tarefa 1: inxerir datos</span><span class="sxs-lookup"><span data-stu-id="2f908-112">Task 1 - Ingest data</span></span>

<span data-ttu-id="2f908-113">Revise os artigos [sobre a inxestión de datos](data-sources.md) e a [importación de fontes de datos usando conectores de Power Query](connect-power-query.md) especificamente.</span><span class="sxs-lookup"><span data-stu-id="2f908-113">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="2f908-114">A seguinte información supón que está familiarizado coa inxestión de datos en xeral.</span><span class="sxs-lookup"><span data-stu-id="2f908-114">The following information assumes you familiarized with ingesting data in general.</span></span>

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="2f908-115">Inxerir datos de clientes desde a plataforma de comercio electrónico</span><span class="sxs-lookup"><span data-stu-id="2f908-115">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="2f908-116">Cree unha orixe de datos denominada **eCommerce**, escolla a opción de importación e seleccione o conector **Texto/CSV**.</span><span class="sxs-lookup"><span data-stu-id="2f908-116">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="2f908-117">Insira o URL dos contactos de comercio electrónico https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="2f908-117">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="2f908-118">Mentres edita os datos, seleccione **Transformar** e logo **Usar a primeira fila como cabeceiras**.</span><span class="sxs-lookup"><span data-stu-id="2f908-118">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="2f908-119">Actualice o tipo de datos para as columnas listadas a continuación:</span><span class="sxs-lookup"><span data-stu-id="2f908-119">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="2f908-120">**DateOfBirth**: data</span><span class="sxs-lookup"><span data-stu-id="2f908-120">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="2f908-121">**CreatedOn**: data/hora/fuso</span><span class="sxs-lookup"><span data-stu-id="2f908-121">**CreatedOn**: Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transforme a data de nacemento en data.":::

5. <span data-ttu-id="2f908-123">No campo "Nome" no panel da dereita, cambie o nome da súa orixe de datos de **Consulta** a **eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="2f908-123">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

6. <span data-ttu-id="2f908-124">**Garde** a orixe de datos.</span><span class="sxs-lookup"><span data-stu-id="2f908-124">**Save** the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="2f908-125">Inxerir datos de compra en liña</span><span class="sxs-lookup"><span data-stu-id="2f908-125">Ingest online purchase data</span></span>

1. <span data-ttu-id="2f908-126">Engada outro conxunto de datos á mesma orixe de datos de **comercio electrónico**.</span><span class="sxs-lookup"><span data-stu-id="2f908-126">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="2f908-127">Escolla o conector **Texto/CSV** de novo.</span><span class="sxs-lookup"><span data-stu-id="2f908-127">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="2f908-128">Introduza o URL para datos de **compras en liña** https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="2f908-128">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="2f908-129">Mentres edita os datos, seleccione **Transformar** e logo **Usar a primeira fila como cabeceiras**.</span><span class="sxs-lookup"><span data-stu-id="2f908-129">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="2f908-130">Actualice o tipo de datos para as columnas listadas a continuación:</span><span class="sxs-lookup"><span data-stu-id="2f908-130">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="2f908-131">**PurchasedOn**: data/hora</span><span class="sxs-lookup"><span data-stu-id="2f908-131">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="2f908-132">**TotalPrice**: moeda</span><span class="sxs-lookup"><span data-stu-id="2f908-132">**TotalPrice**: Currency</span></span>

1. <span data-ttu-id="2f908-133">No campo **Nome** do panel lateral, cambie o nome da súa orixe de datos de **Consulta** a **eCommercePurchases**.</span><span class="sxs-lookup"><span data-stu-id="2f908-133">In the **Name** field on the side pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="2f908-134">**Garde** a orixe de datos.</span><span class="sxs-lookup"><span data-stu-id="2f908-134">**Save** the data source.</span></span>


### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="2f908-135">Inxerir datos de clientes desde o esquema de fidelización</span><span class="sxs-lookup"><span data-stu-id="2f908-135">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="2f908-136">Cree unha orixe de datos denominada **LoyaltyScheme**, escolla a opción de importación e seleccione o conector **Texto/CSV**.</span><span class="sxs-lookup"><span data-stu-id="2f908-136">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="2f908-137">Insira o URL dos contactos de comercio electrónico https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="2f908-137">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="2f908-138">Mentres edita os datos, seleccione **Transformar** e logo **Usar a primeira fila como cabeceiras**.</span><span class="sxs-lookup"><span data-stu-id="2f908-138">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="2f908-139">Actualice o tipo de datos para as columnas listadas a continuación:</span><span class="sxs-lookup"><span data-stu-id="2f908-139">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="2f908-140">**DateOfBirth**: data</span><span class="sxs-lookup"><span data-stu-id="2f908-140">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="2f908-141">**RewardsPoints**: número enteiro</span><span class="sxs-lookup"><span data-stu-id="2f908-141">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="2f908-142">**CreatedOn**: data/hora</span><span class="sxs-lookup"><span data-stu-id="2f908-142">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="2f908-143">No campo **Nome** no panel da dereita, cambie o nome da súa orixe de datos de **Consulta** a **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="2f908-143">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="2f908-144">**Garde** a orixe de datos.</span><span class="sxs-lookup"><span data-stu-id="2f908-144">**Save** the data source.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="2f908-145">Tarefa 2: unificación de datos</span><span class="sxs-lookup"><span data-stu-id="2f908-145">Task 2 - Data unification</span></span>

<span data-ttu-id="2f908-146">Despois de inxerir os datos, comezamos o proceso de unificación de datos para crear un perfil de cliente unificado.</span><span class="sxs-lookup"><span data-stu-id="2f908-146">After ingesting the data, we now begin the data unification process to create a unified customer profile.</span></span> <span data-ttu-id="2f908-147">Para obter máis información, consulte [Unificación de datos](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="2f908-147">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="2f908-148">Asignar</span><span class="sxs-lookup"><span data-stu-id="2f908-148">Map</span></span>

1. <span data-ttu-id="2f908-149">Despois de inxerir os datos, asigne os contactos desde os datos de comercio electrónico e de fidelización a tipos de datos comúns.</span><span class="sxs-lookup"><span data-stu-id="2f908-149">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="2f908-150">Vaia a **Datos** > **Unificar** > **Asignar**.</span><span class="sxs-lookup"><span data-stu-id="2f908-150">Go to **Data** > **Unify** > **Map**.</span></span>

2. <span data-ttu-id="2f908-151">Seleccione as entidades que representan o perfil do cliente: **eCommerceContacts** e **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="2f908-151">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span>

   ![unificar fontes de datos de comercio electrónico e fidelización.](media/unify-ecommerce-loyalty.png)

3. <span data-ttu-id="2f908-153">Seleccione **ContactId** como clave primaria para **eCommerceContacts** e **LoyaltyID** como clave primaria para **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="2f908-153">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   ![Unificar LoyaltyId como clave principal.](media/unify-loyaltyid.png)

### <a name="match"></a><span data-ttu-id="2f908-155">Buscar coincidencias</span><span class="sxs-lookup"><span data-stu-id="2f908-155">Match</span></span>

1. <span data-ttu-id="2f908-156">Vaia ao separador **Buscar coincidencias** e seleccione **Definir orde**.</span><span class="sxs-lookup"><span data-stu-id="2f908-156">Go to the **Match** tab and select **Set Order**.</span></span>

2. <span data-ttu-id="2f908-157">Na lista despregable **Principal**, escolla **eCommerceContacts : eCommerce** como fonte principal e inclúa todos os rexistros.</span><span class="sxs-lookup"><span data-stu-id="2f908-157">In the **Primary** dropdown list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

3. <span data-ttu-id="2f908-158">Na lista despregable **Entidade 2**, escolla **loyCustomers: LoyaltyScheme** e inclúa todos os rexistros.</span><span class="sxs-lookup"><span data-stu-id="2f908-158">In the **Entity 2** dropdown list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   ![unificar coincidencias de comercio electrónico e fidelización.](media/unify-match-order.png)

4. <span data-ttu-id="2f908-160">Seleccione **Crear unha nova regra**</span><span class="sxs-lookup"><span data-stu-id="2f908-160">Select **Create a new rule**</span></span>

5. <span data-ttu-id="2f908-161">Engada a súa primeira condición usando FullName.</span><span class="sxs-lookup"><span data-stu-id="2f908-161">Add your first condition using FullName.</span></span>

   - <span data-ttu-id="2f908-162">Para eCommerceContacts, seleccione **FullName** no menú despregable.</span><span class="sxs-lookup"><span data-stu-id="2f908-162">For eCommerceContacts select **FullName** in the dropdown.</span></span>
   - <span data-ttu-id="2f908-163">Para loyCustomers, seleccione **FullName** no menú despregable.</span><span class="sxs-lookup"><span data-stu-id="2f908-163">For loyCustomers select **FullName** in the dropdown.</span></span>
   - <span data-ttu-id="2f908-164">Seleccione o menús despregable **Normalizar** e escolla **Tipo (teléfono, nome, enderezo...)**.</span><span class="sxs-lookup"><span data-stu-id="2f908-164">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   - <span data-ttu-id="2f908-165">Defina o **Nivel de precisión**: **Básico** e **Valor**: **Alto**.</span><span class="sxs-lookup"><span data-stu-id="2f908-165">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

6. <span data-ttu-id="2f908-166">Introduza o nome **FullName, Email** para a nova regra.</span><span class="sxs-lookup"><span data-stu-id="2f908-166">Enter the name **FullName, Email** for the new rule.</span></span>

   - <span data-ttu-id="2f908-167">Engada unha segunda condición para o enderezo de correo electrónico seleccionando **Engadir condición**</span><span class="sxs-lookup"><span data-stu-id="2f908-167">Add a second condition for email address by selecting **Add Condition**</span></span>
   - <span data-ttu-id="2f908-168">Para os eCommerceContacts da entidade, escolla **Correo electrónico** no menú despregable.</span><span class="sxs-lookup"><span data-stu-id="2f908-168">For entity eCommerceContacts, choose **EMail** in dropdown.</span></span>
   - <span data-ttu-id="2f908-169">Para os loyCustomers da entidade, escolla **Correo electrónico** no menú despregable.</span><span class="sxs-lookup"><span data-stu-id="2f908-169">For entity loyCustomers, choose **EMail** in the dropdown.</span></span>
   - <span data-ttu-id="2f908-170">Deixe Normalizar en branco.</span><span class="sxs-lookup"><span data-stu-id="2f908-170">Leave Normalize blank.</span></span>
   - <span data-ttu-id="2f908-171">Defina o **Nivel de precisión**: **Básico** e **Valor**: **Alto**.</span><span class="sxs-lookup"><span data-stu-id="2f908-171">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   ![Unificar a regra de coincidencia para o nome e o correo electrónico.](media/unify-match-rule.png)

7. <span data-ttu-id="2f908-173">Seleccione **Gardar** e **Executar**.</span><span class="sxs-lookup"><span data-stu-id="2f908-173">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="2f908-174">Combinación</span><span class="sxs-lookup"><span data-stu-id="2f908-174">Merge</span></span>

1. <span data-ttu-id="2f908-175">Vaia ao separador **Combinar**.</span><span class="sxs-lookup"><span data-stu-id="2f908-175">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="2f908-176">No **ContactId** da entidade **loyCustomers**, cambie o nome de visualización a **ContactIdLOYALTY** para diferencialo dos outros identificadores inxeridos.</span><span class="sxs-lookup"><span data-stu-id="2f908-176">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   ![renomear contactid do identificador de fidelidade.](media/unify-merge-contactid.png)

1. <span data-ttu-id="2f908-178">Seleccione **Gardar** e **Executar** para iniciar o proceso de unión.</span><span class="sxs-lookup"><span data-stu-id="2f908-178">Select **Save** and **Run** to start the Merge Process.</span></span>

## <a name="task-3---configure-product-recommendation-prediction"></a><span data-ttu-id="2f908-179">Tarefa 3: configurar a predición de recomendacións de produtos</span><span class="sxs-lookup"><span data-stu-id="2f908-179">Task 3 - Configure product recommendation prediction</span></span>

<span data-ttu-id="2f908-180">Cos perfís de clientes unificados no seu lugar, agora podemos executar a predición de abandono de subscricións.</span><span class="sxs-lookup"><span data-stu-id="2f908-180">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span>

1. <span data-ttu-id="2f908-181">Vaia a **Intelixencia** > **Predición** e escolla **Recomendación de produtos**.</span><span class="sxs-lookup"><span data-stu-id="2f908-181">Go to **Intelligence** > **Prediction** choose **Product recommendation**.</span></span>

1. <span data-ttu-id="2f908-182">Seleccione **Comezar**.</span><span class="sxs-lookup"><span data-stu-id="2f908-182">Select **Get started**.</span></span>

1. <span data-ttu-id="2f908-183">Dea nome ao modelo **Predición do modelo de recomendación de produtos de OOB** e a entidade de saída **OOBProductRecommendationModelPrediction**.</span><span class="sxs-lookup"><span data-stu-id="2f908-183">Name the model **OOB Product Recommendation Model Prediction** and the output entity **OOBProductRecommendationModelPrediction**.</span></span>

1. <span data-ttu-id="2f908-184">Defina tres condicións para o modelo:</span><span class="sxs-lookup"><span data-stu-id="2f908-184">Define three conditions for the model:</span></span>

   - <span data-ttu-id="2f908-185">**Número de produtos**: Configure este valor en **5**.</span><span class="sxs-lookup"><span data-stu-id="2f908-185">**Number of products**: Set this value to **5**.</span></span> <span data-ttu-id="2f908-186">Esta configuración define cantos produtos desexa recomendar aos seus clientes.</span><span class="sxs-lookup"><span data-stu-id="2f908-186">This setting defines how many products you want to recommend to your customers.</span></span>

   - <span data-ttu-id="2f908-187">**Compras repetidas esperadas**: seleccione **Si** para indicar que quere incluír produtos na recomendación que os seus clientes compraron con anterioridade.</span><span class="sxs-lookup"><span data-stu-id="2f908-187">**Repeat purchases expected**: Select **Yes** to indicate that you want to include products in the recommendation that your customers have purchased before.</span></span>

   - <span data-ttu-id="2f908-188">**Ventá para ver días pasados:** Seleccione polo menos **365 días**.</span><span class="sxs-lookup"><span data-stu-id="2f908-188">**Look back window:** Select at least **365 days**.</span></span> <span data-ttu-id="2f908-189">Esta configuración define o número de días pasados que o modelo mira na actividade do cliente que se van usar como entrada para as súas recomendacións.</span><span class="sxs-lookup"><span data-stu-id="2f908-189">This setting defines how far the model will look back at the customer's activity to use it as input to their recommendations.</span></span>
   
   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Preferencias do modelo de recomendación de produtos.":::

1. <span data-ttu-id="2f908-191">Seleccione **Datos requiridos** e seleccione **Engadir datos** para o historial de compras.</span><span class="sxs-lookup"><span data-stu-id="2f908-191">Select **Required data** and select **Add data** for purchase history.</span></span>

1. <span data-ttu-id="2f908-192">Engada a entidade **eCommercePurchases : eCommerce** e asigne os campos de comercio electrónico aos campos correspondentes requiridos polo modelo.</span><span class="sxs-lookup"><span data-stu-id="2f908-192">Add the **eCommercePurchases : eCommerce** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="2f908-193">Una a entidade **eCommercePurchases : eCommerce** con **eCommerceContacts : eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="2f908-193">Join the **eCommercePurchases : eCommerce** entity with **eCommerceContacts : eCommerce**.</span></span>

   ![Unir entidades de comercio electrónico.](media/model-purchase-join.png)

1. <span data-ttu-id="2f908-195">Seleccione **Seguinte** para establecer a programación do modelo.</span><span class="sxs-lookup"><span data-stu-id="2f908-195">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="2f908-196">O modelo necesita adestrarse regularmente para aprender novos padróns cando se inxiren novos datos.</span><span class="sxs-lookup"><span data-stu-id="2f908-196">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="2f908-197">Para este exemplo, seleccione **Mensual**.</span><span class="sxs-lookup"><span data-stu-id="2f908-197">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="2f908-198">Despois de revisar todos os detalles, seleccione **Gardar e executar**.</span><span class="sxs-lookup"><span data-stu-id="2f908-198">After reviewing all the details, select **Save and Run**.</span></span>


## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="2f908-199">Tarefa 4: revisar resultados e explicacións do modelo</span><span class="sxs-lookup"><span data-stu-id="2f908-199">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="2f908-200">Deixe que o modelo complete o adestramento e a puntuación dos datos.</span><span class="sxs-lookup"><span data-stu-id="2f908-200">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="2f908-201">Agora pode revisar as explicacións do modelo de recomendación de produtos.</span><span class="sxs-lookup"><span data-stu-id="2f908-201">You can now review the product recommendation model explanations.</span></span> <span data-ttu-id="2f908-202">Para obter máis información, consulte [Revisar o estado e os resultados dunha predición](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="2f908-202">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-purchased-products"></a><span data-ttu-id="2f908-203">Tarefa 5: crear un segmento de produtos moi comprados</span><span class="sxs-lookup"><span data-stu-id="2f908-203">Task 5 - Create a segment of high purchased products</span></span>

<span data-ttu-id="2f908-204">Executar o modelo de produción crea unha nova entidade na que pode ver en **Datos** > **Entidades**.</span><span class="sxs-lookup"><span data-stu-id="2f908-204">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>

<span data-ttu-id="2f908-205">Pode crear un novo segmento baseado na entidade creada polo modelo.</span><span class="sxs-lookup"><span data-stu-id="2f908-205">You can create a new segment based on the entity created by the model.</span></span>

1. <span data-ttu-id="2f908-206">Vaia a **Segmentos**.</span><span class="sxs-lookup"><span data-stu-id="2f908-206">Go to **Segments**.</span></span> <span data-ttu-id="2f908-207">Seleccione **Novo** e elixa **Crear a partir de** > **Intelixencia**.</span><span class="sxs-lookup"><span data-stu-id="2f908-207">Select **New** and choose **Create from** > **Intelligence**.</span></span>

   ![Creación dun segmento coa saída do modelo.](media/segment-intelligence.png)

1. <span data-ttu-id="2f908-209">Seleccione o extremo **OOBProductRecommendationModelPrediction** e defina o segmento:</span><span class="sxs-lookup"><span data-stu-id="2f908-209">Select the **OOBProductRecommendationModelPrediction** endpoint and define the segment:</span></span>

   - <span data-ttu-id="2f908-210">Campo: ProductID</span><span class="sxs-lookup"><span data-stu-id="2f908-210">Field: ProductID</span></span>
   - <span data-ttu-id="2f908-211">Operador: Valor</span><span class="sxs-lookup"><span data-stu-id="2f908-211">Operator: Value</span></span>
   - <span data-ttu-id="2f908-212">Valor: seleccione os tres identificadores de produto principais</span><span class="sxs-lookup"><span data-stu-id="2f908-212">Value: Select the top three product IDs</span></span>

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="Cree un segmento a partir dos resultados do modelo.":::

<span data-ttu-id="2f908-214">Agora ten un segmento que se actualiza dinamicamente e identifica aos clientes que están máis dispostos a mercar os tres produtos máis recomendados</span><span class="sxs-lookup"><span data-stu-id="2f908-214">You now have a segment that is dynamically updated which identifies the customers who are more willing to purchase the three most recommended products</span></span> 

<span data-ttu-id="2f908-215">Para ver máis información, consulte: [Creación e xestión de segmentos](segments.md).</span><span class="sxs-lookup"><span data-stu-id="2f908-215">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
