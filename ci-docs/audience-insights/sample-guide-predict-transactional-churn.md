---
title: Guía de mostra da predición do abandono transaccional
description: Utilice esta guía de mostra para probar o modelo de predición do abandono transaccional listo para usar.
ms.date: 11/19/2020
ms.reviewer: digranad
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 81540ad2f490cf566f031233543b3cb6aa838033
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269788"
---
# <a name="transactional-churn-prediction-preview-sample-guide"></a><span data-ttu-id="42fc8-103">Guía de mostra (previsualización) da predición do abandono transaccional</span><span class="sxs-lookup"><span data-stu-id="42fc8-103">Transactional churn prediction (preview) sample guide</span></span>

<span data-ttu-id="42fc8-104">Esta guía guiarao a través dun exemplo integral de predición do abandono transaccional en Customer Insights empregando os datos fornecidos a continuación.</span><span class="sxs-lookup"><span data-stu-id="42fc8-104">This guide will walk you through an end to end example of Transactional Churn prediction in Customer Insights using the data provided below.</span></span> <span data-ttu-id="42fc8-105">Todos os datos empregados nesta guía non son datos reais do cliente e forman parte do conxunto de datos de Contoso que se atopan no ambiente de *demostración* dentro da súa subscrición a Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="42fc8-105">All data used in this guide is not real customer data and is part of the Contoso dataset found in the *Demo* environment within your Customer Insights Subscription.</span></span>

## <a name="scenario"></a><span data-ttu-id="42fc8-106">Escenario</span><span class="sxs-lookup"><span data-stu-id="42fc8-106">Scenario</span></span>

<span data-ttu-id="42fc8-107">Contoso é unha empresa que produce cafés e máquinas de café de alta calidade, que venden a través do seu sitio web Contoso Coffee.</span><span class="sxs-lookup"><span data-stu-id="42fc8-107">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="42fc8-108">O seu obxectivo é saber que clientes que adoitan mercar os seus produtos de xeito regular deixarán de ser clientes activos nos próximos 60 días.</span><span class="sxs-lookup"><span data-stu-id="42fc8-108">Their goal is to know which customers who typically purchase their products on a regular basis, will stop being active customers in the next 60 days.</span></span> <span data-ttu-id="42fc8-109">Sabendo cal dos seus clientes é **susceptible de abandonar**, pode axudalos a aforrar esforzos de marketing centrándose en mantelos.</span><span class="sxs-lookup"><span data-stu-id="42fc8-109">Knowing which of their customers is **likely to churn**, can help them save marketing efforts by focusing on keeping them.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="42fc8-110">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="42fc8-110">Prerequisites</span></span>

- <span data-ttu-id="42fc8-111">Polo menos [Permisos de colaborador](permissions.md) en Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="42fc8-111">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="42fc8-112">Recomendámoslle que implemente os seguintes pasos [nun novo ambiente](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="42fc8-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="42fc8-113">Tarefa 1: inxerir datos</span><span class="sxs-lookup"><span data-stu-id="42fc8-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="42fc8-114">Revise os artigos [sobre a inxestión de datos](data-sources.md) e a [importación de fontes de datos usando conectores de Power Query](connect-power-query.md) especificamente.</span><span class="sxs-lookup"><span data-stu-id="42fc8-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="42fc8-115">A seguinte información supón que está familiarizado coa inxestión de datos en xeral.</span><span class="sxs-lookup"><span data-stu-id="42fc8-115">The following information assumes you familiarized with ingesting data in general.</span></span> 

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="42fc8-116">Inxerir datos de clientes desde a plataforma de comercio electrónico</span><span class="sxs-lookup"><span data-stu-id="42fc8-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="42fc8-117">Cree unha orixe de datos denominada **eCommerce**, escolla a opción de importación e seleccione o conector **Texto/CSV**.</span><span class="sxs-lookup"><span data-stu-id="42fc8-117">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="42fc8-118">Insira o URL dos contactos de comercio electrónico https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="42fc8-118">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="42fc8-119">Mentres edita os datos, seleccione **Transformar** e logo **Usar a primeira fila como cabeceiras**.</span><span class="sxs-lookup"><span data-stu-id="42fc8-119">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="42fc8-120">Actualice o tipo de datos para as columnas listadas a continuación:</span><span class="sxs-lookup"><span data-stu-id="42fc8-120">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="42fc8-121">**DateOfBirth**: data</span><span class="sxs-lookup"><span data-stu-id="42fc8-121">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="42fc8-122">**CreatedOn**: data/hora/fuso</span><span class="sxs-lookup"><span data-stu-id="42fc8-122">**CreatedOn**: Date/Time/Zone</span></span>

   [!div class="mx-imgBorder"]
   <span data-ttu-id="42fc8-123">![Transformar DoB en data](media/ecommerce-dob-date.PNG "transformar data de nacemento en data")</span><span class="sxs-lookup"><span data-stu-id="42fc8-123">![Transform DoB to Date](media/ecommerce-dob-date.PNG "transform date of birth to date")</span></span>

1. <span data-ttu-id="42fc8-124">No campo **Nome** no panel da dereita, cambie o nome da súa orixe de datos de **Consulta** a **eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="42fc8-124">In the **Name** field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="42fc8-125">Garde a orixe de datos.</span><span class="sxs-lookup"><span data-stu-id="42fc8-125">Save the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="42fc8-126">Inxerir datos de compra en liña</span><span class="sxs-lookup"><span data-stu-id="42fc8-126">Ingest online purchase data</span></span>

1. <span data-ttu-id="42fc8-127">Engada outro conxunto de datos á mesma orixe de datos de **comercio electrónico**.</span><span class="sxs-lookup"><span data-stu-id="42fc8-127">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="42fc8-128">Escolla o conector **Texto/CSV** de novo.</span><span class="sxs-lookup"><span data-stu-id="42fc8-128">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="42fc8-129">Introduza o URL para datos de **compras en liña** https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="42fc8-129">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="42fc8-130">Mentres edita os datos, seleccione **Transformar** e logo **Usar a primeira fila como cabeceiras**.</span><span class="sxs-lookup"><span data-stu-id="42fc8-130">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="42fc8-131">Actualice o tipo de datos para as columnas listadas a continuación:</span><span class="sxs-lookup"><span data-stu-id="42fc8-131">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="42fc8-132">**PurchasedOn**: data/hora</span><span class="sxs-lookup"><span data-stu-id="42fc8-132">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="42fc8-133">**TotalPrice**: moeda</span><span class="sxs-lookup"><span data-stu-id="42fc8-133">**TotalPrice**: Currency</span></span>
   
1. <span data-ttu-id="42fc8-134">No campo **Nome** no panel da dereita, cambie o nome da súa orixe de datos de **Consulta** a **eCommercePurchases**.</span><span class="sxs-lookup"><span data-stu-id="42fc8-134">In the **Name** field on the right-hand pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="42fc8-135">Garde a orixe de datos.</span><span class="sxs-lookup"><span data-stu-id="42fc8-135">Save the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="42fc8-136">Inxerir datos de clientes desde o esquema de fidelización</span><span class="sxs-lookup"><span data-stu-id="42fc8-136">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="42fc8-137">Cree unha orixe de datos denominada **LoyaltyScheme**, escolla a opción de importación e seleccione o conector **Texto/CSV**.</span><span class="sxs-lookup"><span data-stu-id="42fc8-137">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="42fc8-138">Insira o URL dos contactos de comercio electrónico https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="42fc8-138">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="42fc8-139">Mentres edita os datos, seleccione **Transformar** e logo **Usar a primeira fila como cabeceiras**.</span><span class="sxs-lookup"><span data-stu-id="42fc8-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="42fc8-140">Actualice o tipo de datos para as columnas listadas a continuación:</span><span class="sxs-lookup"><span data-stu-id="42fc8-140">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="42fc8-141">**DateOfBirth**: data</span><span class="sxs-lookup"><span data-stu-id="42fc8-141">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="42fc8-142">**RewardsPoints**: número enteiro</span><span class="sxs-lookup"><span data-stu-id="42fc8-142">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="42fc8-143">**CreatedOn**: data/hora</span><span class="sxs-lookup"><span data-stu-id="42fc8-143">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="42fc8-144">No campo **Nome** no panel da dereita, cambie o nome da súa orixe de datos de **Consulta** a **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="42fc8-144">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="42fc8-145">Garde a orixe de datos.</span><span class="sxs-lookup"><span data-stu-id="42fc8-145">Save the data source.</span></span>


## <a name="task-2---data-unification"></a><span data-ttu-id="42fc8-146">Tarefa 2: unificación de datos</span><span class="sxs-lookup"><span data-stu-id="42fc8-146">Task 2 - Data unification</span></span>

<span data-ttu-id="42fc8-147">Despois de inxerir os datos agora comezamos o proceso de **Asignación, busca de coincidencias e combinación** para crear un perfil de cliente unificado.</span><span class="sxs-lookup"><span data-stu-id="42fc8-147">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="42fc8-148">Para obter máis información, consulte [Unificación de datos](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="42fc8-148">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="42fc8-149">Asignar</span><span class="sxs-lookup"><span data-stu-id="42fc8-149">Map</span></span>

1. <span data-ttu-id="42fc8-150">Despois de inxerir os datos, asigne os contactos desde os datos de comercio electrónico e de fidelización a tipos de datos comúns.</span><span class="sxs-lookup"><span data-stu-id="42fc8-150">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="42fc8-151">Vaia a **Datos** > **Unificar** > **Asignar**.</span><span class="sxs-lookup"><span data-stu-id="42fc8-151">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="42fc8-152">Seleccione as entidades que representan o perfil do cliente: **eCommerceContacts** e **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="42fc8-152">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="unificar fontes de datos de comercio electrónico e fidelización.":::

1. <span data-ttu-id="42fc8-154">Seleccione **ContactId** como clave primaria para **eCommerceContacts** e **LoyaltyID** como clave primaria para **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="42fc8-154">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="Unificar LoyaltyId como clave principal.":::

### <a name="match"></a><span data-ttu-id="42fc8-156">Buscar coincidencias</span><span class="sxs-lookup"><span data-stu-id="42fc8-156">Match</span></span>

1. <span data-ttu-id="42fc8-157">Vaia ao separador **Buscar coincidencias** e seleccione **Definir orde**.</span><span class="sxs-lookup"><span data-stu-id="42fc8-157">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="42fc8-158">No lista despregable **Primario**, escolla **eCommerceContacts: eCommerce** como fonte principal e inclúa todos os rexistros.</span><span class="sxs-lookup"><span data-stu-id="42fc8-158">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="42fc8-159">Na lista despregable **Entidade 2**, escolla **loyCustomers: LoyaltyScheme** e inclúa todos os rexistros.</span><span class="sxs-lookup"><span data-stu-id="42fc8-159">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   :::image type="content" source="media/unify-match-order.PNG" alt-text="unificar coincidencias de comercio electrónico e fidelización.":::

1. <span data-ttu-id="42fc8-161">Seleccione **Crear unha nova regra**</span><span class="sxs-lookup"><span data-stu-id="42fc8-161">Select **Create a new rule**</span></span>

1. <span data-ttu-id="42fc8-162">Engada a súa primeira condición usando FullName.</span><span class="sxs-lookup"><span data-stu-id="42fc8-162">Add your first condition using FullName.</span></span>

   * <span data-ttu-id="42fc8-163">Para eCommerceContacts, seleccione **FullName** no menú despregable.</span><span class="sxs-lookup"><span data-stu-id="42fc8-163">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="42fc8-164">Para loyCustomers, seleccione **FullName** no menú despregable.</span><span class="sxs-lookup"><span data-stu-id="42fc8-164">For loyCustomers select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="42fc8-165">Seleccione o menús despregable **Normalizar** e escolla **Tipo (teléfono, nome, enderezo...)**.</span><span class="sxs-lookup"><span data-stu-id="42fc8-165">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   * <span data-ttu-id="42fc8-166">Defina o **Nivel de precisión**: **Básico** e **Valor**: **Alto**.</span><span class="sxs-lookup"><span data-stu-id="42fc8-166">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="42fc8-167">Introduza o nome **FullName, Email** para a nova regra.</span><span class="sxs-lookup"><span data-stu-id="42fc8-167">Enter the name **FullName, Email** for the new rule.</span></span>

   * <span data-ttu-id="42fc8-168">Engada unha segunda condición para o enderezo de correo electrónico seleccionando **Engadir condición**</span><span class="sxs-lookup"><span data-stu-id="42fc8-168">Add a second condition for email address by selecting **Add Condition**</span></span>
   * <span data-ttu-id="42fc8-169">Para os eCommerceContacts da entidade, escolla **EMail** no menú despregable.</span><span class="sxs-lookup"><span data-stu-id="42fc8-169">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   * <span data-ttu-id="42fc8-170">Para os loyCustomers da entidade, escolla **EMail** no menú despregable.</span><span class="sxs-lookup"><span data-stu-id="42fc8-170">For entity loyCustomers, choose **EMail** in the drop-down.</span></span> 
   * <span data-ttu-id="42fc8-171">Deixe Normalizar en branco.</span><span class="sxs-lookup"><span data-stu-id="42fc8-171">Leave Normalize blank.</span></span> 
   * <span data-ttu-id="42fc8-172">Defina o **Nivel de precisión**: **Básico** e **Valor**: **Alto**.</span><span class="sxs-lookup"><span data-stu-id="42fc8-172">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="Unificar a regra de coincidencia para o nome e o correo electrónico.":::

7. <span data-ttu-id="42fc8-174">Seleccione **Gardar** e **Executar**.</span><span class="sxs-lookup"><span data-stu-id="42fc8-174">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="42fc8-175">Combinación</span><span class="sxs-lookup"><span data-stu-id="42fc8-175">Merge</span></span>

1. <span data-ttu-id="42fc8-176">Vaia ao separador **Combinar**.</span><span class="sxs-lookup"><span data-stu-id="42fc8-176">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="42fc8-177">No **ContactId** da entidade **loyCustomers**, cambie o nome de visualización a **ContactIdLOYALTY** para diferencialo dos outros identificadores inxeridos.</span><span class="sxs-lookup"><span data-stu-id="42fc8-177">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="renomear contactid do identificador de fidelidade.":::

1. <span data-ttu-id="42fc8-179">Seleccione **Gardar** e **Executar** para iniciar o proceso de unión.</span><span class="sxs-lookup"><span data-stu-id="42fc8-179">Select **Save** and **Run** to start the Merge Process.</span></span>



## <a name="task-3---configure-transaction-churn-prediction"></a><span data-ttu-id="42fc8-180">Tarefa 3: configurar a predición de abandono transaccional</span><span class="sxs-lookup"><span data-stu-id="42fc8-180">Task 3 - Configure transaction churn prediction</span></span>

<span data-ttu-id="42fc8-181">Cos perfís de clientes unificados no seu lugar, agora podemos executar a predición de abandono de subscricións.</span><span class="sxs-lookup"><span data-stu-id="42fc8-181">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span> <span data-ttu-id="42fc8-182">Para os pasos detallados, consulte o artigo [Predición de abandono de subscricións (vista previa)](predict-subscription-churn.md).</span><span class="sxs-lookup"><span data-stu-id="42fc8-182">For detailed steps, see the [Subscription churn prediction (preview)](predict-subscription-churn.md) article.</span></span> 

1. <span data-ttu-id="42fc8-183">Vaia a **Intelixencia** > **Descubrir** e seleccione para usar o **Modelo de abandono do cliente**.</span><span class="sxs-lookup"><span data-stu-id="42fc8-183">Go to **Intelligence** > **Discover** and select to use the **Customer churn model**.</span></span>

1. <span data-ttu-id="42fc8-184">Seleccione a opción **Transaccional** e seleccione **Comezar**.</span><span class="sxs-lookup"><span data-stu-id="42fc8-184">Select the **Transactional** option and select **Get started**.</span></span>

1. <span data-ttu-id="42fc8-185">Nomee o modelo **Predición do abandono de transaccións de comercio electrónico de OOB** e a entidade de saída **OOBeCommerceChurnPrediction**.</span><span class="sxs-lookup"><span data-stu-id="42fc8-185">Name the model **OOB eCommerce Transaction Churn Prediction** and the output entity **OOBeCommerceChurnPrediction**.</span></span>

1. <span data-ttu-id="42fc8-186">Defina dúas condicións para o modelo de abandono:</span><span class="sxs-lookup"><span data-stu-id="42fc8-186">Define two conditions for the churn model:</span></span>

   * <span data-ttu-id="42fc8-187">**Xanela de predición**: **polo menos 60** días.</span><span class="sxs-lookup"><span data-stu-id="42fc8-187">**Prediction window**: **at least 60** days.</span></span> <span data-ttu-id="42fc8-188">Esta configuración define ata que punto do futuro queremos predicir o abandono do cliente.</span><span class="sxs-lookup"><span data-stu-id="42fc8-188">This setting defines how far into the future do we want to predict customer churn.</span></span>

   * <span data-ttu-id="42fc8-189">**Definición de abandono**: **polo menos 60** días.</span><span class="sxs-lookup"><span data-stu-id="42fc8-189">**Churn definition**: **at least 60** days.</span></span> <span data-ttu-id="42fc8-190">A duración sen compra despois da cal se considera que un cliente abandonou.</span><span class="sxs-lookup"><span data-stu-id="42fc8-190">The duration without purchase after which a customer is considered churned.</span></span>

     :::image type="content" source="media/model-levers.PNG" alt-text="Seleccione as opcións do modelo Ventá de predición e Definición de abandono.":::

1. <span data-ttu-id="42fc8-192">Seleccione **Historial de compras (obrigatorio)** e seleccione **Engadir datos** para o historial de compras.</span><span class="sxs-lookup"><span data-stu-id="42fc8-192">Select **Purchase History (required)** and select **Add data** for purchase history.</span></span>

1. <span data-ttu-id="42fc8-193">Engada a entidade **eCommercePurchases : eCommerce** e asigne os campos de comercio electrónico aos campos correspondentes requiridos polo modelo.</span><span class="sxs-lookup"><span data-stu-id="42fc8-193">Add the **eCommercePurchases : eCommerce** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="42fc8-194">Una a entidade **eCommercePurchases : eCommerce** con **eCommerceContacts : eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="42fc8-194">Join the **eCommercePurchases : eCommerce** entity with **eCommerceContacts : eCommerce**.</span></span>

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="Unir entidades de comercio electrónico.":::

1. <span data-ttu-id="42fc8-196">Seleccione **Seguinte** para establecer a programación do modelo.</span><span class="sxs-lookup"><span data-stu-id="42fc8-196">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="42fc8-197">O modelo necesita adestrarse regularmente para aprender novos padróns cando se inxiren novos datos.</span><span class="sxs-lookup"><span data-stu-id="42fc8-197">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="42fc8-198">Para este exemplo, seleccione **Mensual**.</span><span class="sxs-lookup"><span data-stu-id="42fc8-198">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="42fc8-199">Despois de revisar todos os detalles, seleccione **Gardar e executar**.</span><span class="sxs-lookup"><span data-stu-id="42fc8-199">After reviewing all the details, select **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="42fc8-200">Tarefa 4: revisar resultados e explicacións do modelo</span><span class="sxs-lookup"><span data-stu-id="42fc8-200">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="42fc8-201">Deixe que o modelo complete o adestramento e a puntuación dos datos.</span><span class="sxs-lookup"><span data-stu-id="42fc8-201">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="42fc8-202">Agora pode revisar as explicacións do modelo de abandono de subscricións.</span><span class="sxs-lookup"><span data-stu-id="42fc8-202">You can now review the subscription churn model explanations.</span></span> <span data-ttu-id="42fc8-203">Para obter máis información, consulte [Revisar o estado e os resultados dunha predición](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="42fc8-203">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a><span data-ttu-id="42fc8-204">Tarefa 5: crear un segmento de clientes con alto risco de abandono</span><span class="sxs-lookup"><span data-stu-id="42fc8-204">Task 5 - Create a segment of high churn-risk customers</span></span>

<span data-ttu-id="42fc8-205">Executar o modelo de produción crea unha nova entidade na que pode ver en **Datos** > **Entidades**.</span><span class="sxs-lookup"><span data-stu-id="42fc8-205">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>   

<span data-ttu-id="42fc8-206">Pode crear un novo segmento baseado na entidade creada polo modelo.</span><span class="sxs-lookup"><span data-stu-id="42fc8-206">You can create a new segment based on the entity created by the model.</span></span>

1.  <span data-ttu-id="42fc8-207">Vaia a **Segmentos**.</span><span class="sxs-lookup"><span data-stu-id="42fc8-207">Go to **Segments**.</span></span> <span data-ttu-id="42fc8-208">Seleccione **Novo** e elixa **Crear a partir de** > **Intelixencia**.</span><span class="sxs-lookup"><span data-stu-id="42fc8-208">Select **New** and choose **Create from** > **Intelligence**.</span></span> 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Creación dun segmento coa saída do modelo.":::

1. <span data-ttu-id="42fc8-210">Seleccione o extremo **OOBSubscriptionChurnPrediction** e defina o segmento:</span><span class="sxs-lookup"><span data-stu-id="42fc8-210">Select the **OOBSubscriptionChurnPrediction** endpoint and define the segment:</span></span> 
   - <span data-ttu-id="42fc8-211">Campo: ChurnScore</span><span class="sxs-lookup"><span data-stu-id="42fc8-211">Field: ChurnScore</span></span>
   - <span data-ttu-id="42fc8-212">Operador: maior que</span><span class="sxs-lookup"><span data-stu-id="42fc8-212">Operator: greater than</span></span>
   - <span data-ttu-id="42fc8-213">Valor: 0,6</span><span class="sxs-lookup"><span data-stu-id="42fc8-213">Value: 0.6</span></span>
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Configurar o segmento de abandono de subscricións.":::

<span data-ttu-id="42fc8-215">Agora ten un segmento que se actualiza dinámicamente para identificar clientes con alto risco de abandono para este negocio da subscrición.</span><span class="sxs-lookup"><span data-stu-id="42fc8-215">You now have a segment that is dynamically updated which identifies high churn-risk customers for this subscription business.</span></span>

<span data-ttu-id="42fc8-216">Para ver máis información, consulte: [Creación e xestión de segmentos](segments.md).</span><span class="sxs-lookup"><span data-stu-id="42fc8-216">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]