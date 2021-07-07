---
title: Guía de mostra da predición do abandono da subscrición
description: Utilice esta guía de mostra para probar o modelo de predición do abandono da subscrición listo para usar.
ms.date: 11/19/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: fa460fa5c79bc8a356ec5e90050ec85e05c55be8
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306301"
---
# <a name="subscription-churn-prediction-preview-sample-guide"></a><span data-ttu-id="d4d7f-103">Guía de mostra (previsualización) da predición do abandono da subscrición</span><span class="sxs-lookup"><span data-stu-id="d4d7f-103">Subscription churn prediction (preview) sample guide</span></span>

<span data-ttu-id="d4d7f-104">Guiarémolo a través dun exemplo integral de predición do abandono da subscrición empregando os datos de exemplo fornecidos a continuación.</span><span class="sxs-lookup"><span data-stu-id="d4d7f-104">We'll walk you through an end to end example of subscription churn prediction using the sample data provided below.</span></span> 

## <a name="scenario"></a><span data-ttu-id="d4d7f-105">Escenario</span><span class="sxs-lookup"><span data-stu-id="d4d7f-105">Scenario</span></span>

<span data-ttu-id="d4d7f-106">Contoso é unha empresa que produce café e máquinas de café de alta calidade, que se venden a través do sitio web Contoso Coffee.</span><span class="sxs-lookup"><span data-stu-id="d4d7f-106">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="d4d7f-107">Recentemente iniciaron un negocio de subscrición para que os seus clientes tomasen café de xeito habitual.</span><span class="sxs-lookup"><span data-stu-id="d4d7f-107">They recently started a subscription business for their customers to get coffee on a regular basis.</span></span> <span data-ttu-id="d4d7f-108">O seu obxectivo é comprender que clientes subscritos poden cancelar a súa subscrición nos próximos meses.</span><span class="sxs-lookup"><span data-stu-id="d4d7f-108">Their goal is to understand, which subscribed customers might cancel their subscription in the next few months.</span></span> <span data-ttu-id="d4d7f-109">Sabendo cal dos seus clientes é **susceptible de abandonar**, pode axudalos a aforrar esforzos de marketing centrándose en mantelos.</span><span class="sxs-lookup"><span data-stu-id="d4d7f-109">Knowing which of their customers is **likely to churn**, can help them save marketing efforts by focusing on keeping them.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d4d7f-110">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="d4d7f-110">Prerequisites</span></span>

- <span data-ttu-id="d4d7f-111">Polo menos [Permisos de colaborador](permissions.md) en Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="d4d7f-111">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="d4d7f-112">Recomendámoslle que implemente os seguintes pasos [nun novo ambiente](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="d4d7f-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="d4d7f-113">Tarefa 1: inxerir datos</span><span class="sxs-lookup"><span data-stu-id="d4d7f-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="d4d7f-114">Revise os artigos [sobre a inxestión de datos](data-sources.md) e a [importación de fontes de datos usando conectores de Power Query](connect-power-query.md) especificamente.</span><span class="sxs-lookup"><span data-stu-id="d4d7f-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="d4d7f-115">A seguinte información supón que está familiarizado coa inxestión de datos en xeral.</span><span class="sxs-lookup"><span data-stu-id="d4d7f-115">The following information assumes you familiarized with ingesting data in general.</span></span> 

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="d4d7f-116">Inxerir datos de clientes desde a plataforma de comercio electrónico</span><span class="sxs-lookup"><span data-stu-id="d4d7f-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="d4d7f-117">Cree unha orixe de datos denominada **eCommerce**, escolla a opción de importación e seleccione o conector **Texto/CSV**.</span><span class="sxs-lookup"><span data-stu-id="d4d7f-117">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="d4d7f-118">Insira o URL dos contactos de comercio electrónico https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="d4d7f-118">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="d4d7f-119">Mentres edita os datos, seleccione **Transformar** e logo **Usar a primeira fila como cabeceiras**.</span><span class="sxs-lookup"><span data-stu-id="d4d7f-119">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="d4d7f-120">Actualice o tipo de datos para as columnas listadas a continuación:</span><span class="sxs-lookup"><span data-stu-id="d4d7f-120">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="d4d7f-121">**DateOfBirth**: data</span><span class="sxs-lookup"><span data-stu-id="d4d7f-121">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="d4d7f-122">**CreatedOn**: data/hora/fuso</span><span class="sxs-lookup"><span data-stu-id="d4d7f-122">**CreatedOn**: Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transforme a data de nacemento en data.":::

1. <span data-ttu-id="d4d7f-124">No campo **Nome** no panel da dereita, cambie o nome da súa orixe de datos de **Consulta** a **eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="d4d7f-124">In the **Name** field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="d4d7f-125">Garde a orixe de datos.</span><span class="sxs-lookup"><span data-stu-id="d4d7f-125">Save the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="d4d7f-126">Inxerir datos de clientes desde o esquema de fidelización</span><span class="sxs-lookup"><span data-stu-id="d4d7f-126">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="d4d7f-127">Cree unha orixe de datos denominada **LoyaltyScheme**, escolla a opción de importación e seleccione o conector **Texto/CSV**.</span><span class="sxs-lookup"><span data-stu-id="d4d7f-127">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="d4d7f-128">Insira o URL dos contactos de comercio electrónico https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="d4d7f-128">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="d4d7f-129">Mentres edita os datos, seleccione **Transformar** e logo **Usar a primeira fila como cabeceiras**.</span><span class="sxs-lookup"><span data-stu-id="d4d7f-129">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="d4d7f-130">Actualice o tipo de datos para as columnas listadas a continuación:</span><span class="sxs-lookup"><span data-stu-id="d4d7f-130">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="d4d7f-131">**DateOfBirth**: data</span><span class="sxs-lookup"><span data-stu-id="d4d7f-131">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="d4d7f-132">**RewardsPoints**: número enteiro</span><span class="sxs-lookup"><span data-stu-id="d4d7f-132">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="d4d7f-133">**CreatedOn**: data/hora</span><span class="sxs-lookup"><span data-stu-id="d4d7f-133">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="d4d7f-134">No campo **Nome** no panel da dereita, cambie o nome da súa orixe de datos de **Consulta** a **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="d4d7f-134">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="d4d7f-135">Garde a orixe de datos.</span><span class="sxs-lookup"><span data-stu-id="d4d7f-135">Save the data source.</span></span>

### <a name="ingest-subscription-information"></a><span data-ttu-id="d4d7f-136">Inxerir información da subscrición</span><span class="sxs-lookup"><span data-stu-id="d4d7f-136">Ingest subscription information</span></span>

1. <span data-ttu-id="d4d7f-137">Cree unha orixe de datos denominada **SubscriptionHistory**, escolla a opción de importación e seleccione o conector **Texto/CSV**.</span><span class="sxs-lookup"><span data-stu-id="d4d7f-137">Create a data source named **SubscriptionHistory**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="d4d7f-138">Insira o URL dos contactos de comercio electrónico https://aka.ms/ciadchurnsubscriptionhistory.</span><span class="sxs-lookup"><span data-stu-id="d4d7f-138">Enter the URL for eCommerce contacts https://aka.ms/ciadchurnsubscriptionhistory.</span></span>

1. <span data-ttu-id="d4d7f-139">Mentres edita os datos, seleccione **Transformar** e logo **Usar a primeira fila como cabeceiras**.</span><span class="sxs-lookup"><span data-stu-id="d4d7f-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="d4d7f-140">Actualice o tipo de datos para as columnas listadas a continuación:</span><span class="sxs-lookup"><span data-stu-id="d4d7f-140">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="d4d7f-141">**SubscriptioID**: número enteiro</span><span class="sxs-lookup"><span data-stu-id="d4d7f-141">**SubscriptioID**: Whole Number</span></span>
   - <span data-ttu-id="d4d7f-142">**SubscriptionAmount**: moeda</span><span class="sxs-lookup"><span data-stu-id="d4d7f-142">**SubscriptionAmount**: Currency</span></span>
   - <span data-ttu-id="d4d7f-143">**SubscriptionEndDate**: data/hora</span><span class="sxs-lookup"><span data-stu-id="d4d7f-143">**SubscriptionEndDate**: Date/Time</span></span>
   - <span data-ttu-id="d4d7f-144">**SubscriptionStartDate**: data/hora</span><span class="sxs-lookup"><span data-stu-id="d4d7f-144">**SubscriptionStartDate**: Date/Time</span></span>
   - <span data-ttu-id="d4d7f-145">**TransactionDate**: data/hora</span><span class="sxs-lookup"><span data-stu-id="d4d7f-145">**TransactionDate**: Date/Time</span></span>
   - <span data-ttu-id="d4d7f-146">**SubscriptionHistory**: verdadeiro/falso</span><span class="sxs-lookup"><span data-stu-id="d4d7f-146">**IsRecurring**: True/False</span></span>
   - <span data-ttu-id="d4d7f-147">**Is_auto_renew**: verdadeiro/falso</span><span class="sxs-lookup"><span data-stu-id="d4d7f-147">**Is_auto_renew**: True/False</span></span>
   - <span data-ttu-id="d4d7f-148">**RecurringFrequencyInMonths**: número enteiro</span><span class="sxs-lookup"><span data-stu-id="d4d7f-148">**RecurringFrequencyInMonths**: Whole Number</span></span>

1. <span data-ttu-id="d4d7f-149">No campo **Nome** no panel da dereita, cambie o nome da súa orixe de datos de **Consulta** a **SubscriptionHistory**.</span><span class="sxs-lookup"><span data-stu-id="d4d7f-149">In the **Name** field on the right-hand pane, rename your data source from **Query** to **SubscriptionHistory**.</span></span>

1. <span data-ttu-id="d4d7f-150">Garde a orixe de datos.</span><span class="sxs-lookup"><span data-stu-id="d4d7f-150">Save the data source.</span></span>

### <a name="ingest-customer-data-from-website-reviews"></a><span data-ttu-id="d4d7f-151">Inxerir datos de clientes a partir de comentarios de sitios web</span><span class="sxs-lookup"><span data-stu-id="d4d7f-151">Ingest customer data from website reviews</span></span>

1. <span data-ttu-id="d4d7f-152">Cree unha orixe de datos denominada **Website**, escolla a opción de importación e seleccione o conector **Texto/CSV**.</span><span class="sxs-lookup"><span data-stu-id="d4d7f-152">Create a data source named **Website**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="d4d7f-153">Insira o URL dos contactos de comercio electrónico https://aka.ms/ciadclasswebsite.</span><span class="sxs-lookup"><span data-stu-id="d4d7f-153">Enter the URL for eCommerce contacts https://aka.ms/ciadclasswebsite.</span></span>

1. <span data-ttu-id="d4d7f-154">Mentres edita os datos, seleccione **Transformar** e logo **Usar a primeira fila como cabeceiras**.</span><span class="sxs-lookup"><span data-stu-id="d4d7f-154">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="d4d7f-155">Actualice o tipo de datos para as columnas listadas a continuación:</span><span class="sxs-lookup"><span data-stu-id="d4d7f-155">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="d4d7f-156">**ReviewRating**: número enteiro</span><span class="sxs-lookup"><span data-stu-id="d4d7f-156">**ReviewRating**: Whole Number</span></span>
   - <span data-ttu-id="d4d7f-157">**ReviewDate**: data</span><span class="sxs-lookup"><span data-stu-id="d4d7f-157">**ReviewDate**: Date</span></span>

1. <span data-ttu-id="d4d7f-158">No campo "Nome" no panel da dereita, cambie o nome da súa orixe de datos de **Consulta** a **webReviews**.</span><span class="sxs-lookup"><span data-stu-id="d4d7f-158">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **webReviews**.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="d4d7f-159">Tarefa 2: unificación de datos</span><span class="sxs-lookup"><span data-stu-id="d4d7f-159">Task 2 - Data unification</span></span>

<span data-ttu-id="d4d7f-160">Despois de inxerir os datos agora comezamos o proceso de **Asignación, busca de coincidencias e combinación** para crear un perfil de cliente unificado.</span><span class="sxs-lookup"><span data-stu-id="d4d7f-160">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="d4d7f-161">Para obter máis información, consulte [Unificación de datos](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="d4d7f-161">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="d4d7f-162">Asignar</span><span class="sxs-lookup"><span data-stu-id="d4d7f-162">Map</span></span>

1. <span data-ttu-id="d4d7f-163">Despois de inxerir os datos, asigne os contactos desde os datos de comercio electrónico e de fidelización a tipos de datos comúns.</span><span class="sxs-lookup"><span data-stu-id="d4d7f-163">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="d4d7f-164">Vaia a **Datos** > **Unificar** > **Asignar**.</span><span class="sxs-lookup"><span data-stu-id="d4d7f-164">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="d4d7f-165">Seleccione as entidades que representan o perfil do cliente: **eCommerceContacts** e **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="d4d7f-165">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="unificar fontes de datos de comercio electrónico e fidelización.":::

1. <span data-ttu-id="d4d7f-167">Seleccione **ContactId** como clave primaria para **eCommerceContacts** e **LoyaltyID** como clave primaria para **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="d4d7f-167">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="Unificar LoyaltyId como clave principal.":::

### <a name="match"></a><span data-ttu-id="d4d7f-169">Buscar coincidencias</span><span class="sxs-lookup"><span data-stu-id="d4d7f-169">Match</span></span>

1. <span data-ttu-id="d4d7f-170">Vaia ao separador **Buscar coincidencias** e seleccione **Definir orde**.</span><span class="sxs-lookup"><span data-stu-id="d4d7f-170">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="d4d7f-171">Na lista despregable **Principal**, escolla **eCommerceContacts : eCommerce** como fonte principal e inclúa todos os rexistros.</span><span class="sxs-lookup"><span data-stu-id="d4d7f-171">In the **Primary** dropdown list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="d4d7f-172">Na lista despregable **Entidade 2**, escolla **loyCustomers: LoyaltyScheme** e inclúa todos os rexistros.</span><span class="sxs-lookup"><span data-stu-id="d4d7f-172">In the **Entity 2** dropdown list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   :::image type="content" source="media/unify-match-order.PNG" alt-text="unificar coincidencias de comercio electrónico e fidelización.":::

1. <span data-ttu-id="d4d7f-174">Seleccione **Crear unha nova regra**</span><span class="sxs-lookup"><span data-stu-id="d4d7f-174">Select **Create a new rule**</span></span>

1. <span data-ttu-id="d4d7f-175">Engada a súa primeira condición usando FullName.</span><span class="sxs-lookup"><span data-stu-id="d4d7f-175">Add your first condition using FullName.</span></span>

   * <span data-ttu-id="d4d7f-176">Para eCommerceContacts, seleccione **FullName** no menú despregable.</span><span class="sxs-lookup"><span data-stu-id="d4d7f-176">For eCommerceContacts select **FullName** in the dropdown.</span></span>
   * <span data-ttu-id="d4d7f-177">Para loyCustomers, seleccione **FullName** no menú despregable.</span><span class="sxs-lookup"><span data-stu-id="d4d7f-177">For loyCustomers select **FullName** in the dropdown.</span></span>
   * <span data-ttu-id="d4d7f-178">Seleccione o menús despregable **Normalizar** e escolla **Tipo (teléfono, nome, enderezo...)**.</span><span class="sxs-lookup"><span data-stu-id="d4d7f-178">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   * <span data-ttu-id="d4d7f-179">Defina o **Nivel de precisión**: **Básico** e **Valor**: **Alto**.</span><span class="sxs-lookup"><span data-stu-id="d4d7f-179">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="d4d7f-180">Introduza o nome **FullName, Email** para a nova regra.</span><span class="sxs-lookup"><span data-stu-id="d4d7f-180">Enter the name **FullName, Email** for the new rule.</span></span>

   * <span data-ttu-id="d4d7f-181">Engada unha segunda condición para o enderezo de correo electrónico seleccionando **Engadir condición**</span><span class="sxs-lookup"><span data-stu-id="d4d7f-181">Add a second condition for email address by selecting **Add Condition**</span></span>
   * <span data-ttu-id="d4d7f-182">Para os eCommerceContacts da entidade, escolla **Correo electrónico** no menú despregable.</span><span class="sxs-lookup"><span data-stu-id="d4d7f-182">For entity eCommerceContacts, choose **EMail** in dropdown.</span></span>
   * <span data-ttu-id="d4d7f-183">Para os loyCustomers da entidade, escolla **Correo electrónico** no menú despregable.</span><span class="sxs-lookup"><span data-stu-id="d4d7f-183">For entity loyCustomers, choose **EMail** in the dropdown.</span></span> 
   * <span data-ttu-id="d4d7f-184">Deixe Normalizar en branco.</span><span class="sxs-lookup"><span data-stu-id="d4d7f-184">Leave Normalize blank.</span></span> 
   * <span data-ttu-id="d4d7f-185">Defina o **Nivel de precisión**: **Básico** e **Valor**: **Alto**.</span><span class="sxs-lookup"><span data-stu-id="d4d7f-185">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="Unificar a regra de coincidencia para o nome e o correo electrónico.":::

7. <span data-ttu-id="d4d7f-187">Seleccione **Gardar** e **Executar**.</span><span class="sxs-lookup"><span data-stu-id="d4d7f-187">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="d4d7f-188">Combinación</span><span class="sxs-lookup"><span data-stu-id="d4d7f-188">Merge</span></span>

1. <span data-ttu-id="d4d7f-189">Vaia ao separador **Combinar**.</span><span class="sxs-lookup"><span data-stu-id="d4d7f-189">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="d4d7f-190">No **ContactId** da entidade **loyCustomers**, cambie o nome de visualización a **ContactIdLOYALTY** para diferencialo dos outros identificadores inxeridos.</span><span class="sxs-lookup"><span data-stu-id="d4d7f-190">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="renomear contactid do identificador de fidelidade.":::

1. <span data-ttu-id="d4d7f-192">Seleccione **Gardar** e **Executar** para iniciar o proceso de unión.</span><span class="sxs-lookup"><span data-stu-id="d4d7f-192">Select **Save** and **Run** to start the Merge Process.</span></span>


## <a name="task-3---configure-the-subscription-churn-prediction"></a><span data-ttu-id="d4d7f-193">Tarefa 3: configurar a predición de abandono da subscrición</span><span class="sxs-lookup"><span data-stu-id="d4d7f-193">Task 3 - Configure the subscription churn prediction</span></span>

<span data-ttu-id="d4d7f-194">Cos perfís de clientes unificados no seu lugar, agora podemos executar a predición de abandono de subscricións.</span><span class="sxs-lookup"><span data-stu-id="d4d7f-194">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span> <span data-ttu-id="d4d7f-195">Para os pasos detallados, consulte o artigo [Predición de abandono de subscricións (vista previa)](predict-subscription-churn.md).</span><span class="sxs-lookup"><span data-stu-id="d4d7f-195">For detailed steps, see the [Subscription churn prediction (preview)](predict-subscription-churn.md) article.</span></span> 

1. <span data-ttu-id="d4d7f-196">Vaia a **Intelixencia** > **Descubrir** e seleccione para usar o **Modelo de abandono do cliente**.</span><span class="sxs-lookup"><span data-stu-id="d4d7f-196">Go to **Intelligence** > **Discover** and select to use the **Customer churn model**.</span></span>

1. <span data-ttu-id="d4d7f-197">Seleccione a opción **Subscrición** e seleccione **Comezar**.</span><span class="sxs-lookup"><span data-stu-id="d4d7f-197">Select the **Subscription** option and select **Get started**.</span></span>

1. <span data-ttu-id="d4d7f-198">Nomee o modelo **Predición do abandono da subscrición de OOB** e a entidade de saída **OOBSubscriptionChurnPrediction**.</span><span class="sxs-lookup"><span data-stu-id="d4d7f-198">Name the model **OOB Subscription Churn Prediction** and the output entity **OOBSubscriptionChurnPrediction**.</span></span>

1. <span data-ttu-id="d4d7f-199">Defina dúas condicións para o modelo de abandono:</span><span class="sxs-lookup"><span data-stu-id="d4d7f-199">Define two conditions for the churn model:</span></span>

   * <span data-ttu-id="d4d7f-200">**Días desde que finalizou a subscrición**: **polo menos 60** días.</span><span class="sxs-lookup"><span data-stu-id="d4d7f-200">**Days since subscription ended**: **at least 60** days.</span></span> <span data-ttu-id="d4d7f-201">Se un cliente non renova a subscrición neste período despois de que finalizase a súa subscrición, considérase perdido.</span><span class="sxs-lookup"><span data-stu-id="d4d7f-201">If a customer doesn't renew the subscription in this period after their subscription ended, they are considered churned.</span></span> 

   * <span data-ttu-id="d4d7f-202">**Definición de abandono**: **polo menos 93** días.</span><span class="sxs-lookup"><span data-stu-id="d4d7f-202">**Churn definition**: **at least 93** days.</span></span> <span data-ttu-id="d4d7f-203">A duración do modelo predí que clientes poderían abandonar.</span><span class="sxs-lookup"><span data-stu-id="d4d7f-203">The duration the model predict which customers might churn.</span></span> <span data-ttu-id="d4d7f-204">Canto máis se mira no futuro, menos precisos serán os resultados.</span><span class="sxs-lookup"><span data-stu-id="d4d7f-204">The further in the future you look, the less precise the results.</span></span>

     :::image type="content" source="media/model-subs-levers.PNG" alt-text="Seleccione as opcións do modelo Ventá de predición e Definición de abandono.":::

1. <span data-ttu-id="d4d7f-206">Seleccione **Engadir datos requiridos** e seleccione **Engadir datos** para o historial de subscricións.</span><span class="sxs-lookup"><span data-stu-id="d4d7f-206">Select **Add required data** and select **Add data** for subscription history.</span></span>

1. <span data-ttu-id="d4d7f-207">Engada a entidade **Subscription : SubscriptionHistory** e asigne os campos de comercio electrónico aos campos correspondentes requiridos polo modelo.</span><span class="sxs-lookup"><span data-stu-id="d4d7f-207">Add the **Subscription : SubscriptionHistory** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="d4d7f-208">Una a entidade **Subscription : SubscriptionHistory** con **eCommerceContacts : eCommerce**, nomee a relación **eCommerceSubscription**.</span><span class="sxs-lookup"><span data-stu-id="d4d7f-208">Join the **Subscription : SubscriptionHistory** entity with **eCommerceContacts : eCommerce**, name the relationship **eCommerceSubscription**.</span></span>

   :::image type="content" source="media/model-subscription-join.PNG" alt-text="Unir entidades de comercio electrónico.":::

1. <span data-ttu-id="d4d7f-210">En Actividades do cliente, engada a entidade **webReviews : Website** e asigne os campos de webReviews aos campos correspondentes requiridos polo modelo.</span><span class="sxs-lookup"><span data-stu-id="d4d7f-210">Under Customer Activities, add the **webReviews : Website** entity and map the fields from webReviews to the corresponding fields required by the model.</span></span> 
   - <span data-ttu-id="d4d7f-211">Clave principal: ReviewId</span><span class="sxs-lookup"><span data-stu-id="d4d7f-211">Primary key: ReviewId</span></span>
   - <span data-ttu-id="d4d7f-212">Marca de tempo: ReviewDate</span><span class="sxs-lookup"><span data-stu-id="d4d7f-212">Timestamp: ReviewDate</span></span>
   - <span data-ttu-id="d4d7f-213">Evento: ReviewRating</span><span class="sxs-lookup"><span data-stu-id="d4d7f-213">Event: ReviewRating</span></span>

1. <span data-ttu-id="d4d7f-214">Configure unha actividade para as opinións de sitios web.</span><span class="sxs-lookup"><span data-stu-id="d4d7f-214">Configure an activity for website reviews.</span></span> <span data-ttu-id="d4d7f-215">Seleccione a actividade **Opinión** e una a entidade **webReviews : Website** con **eCommerceContacts : eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="d4d7f-215">Select the activity **Review** and join the **webReviews : Website** entity with **eCommerceContacts : eCommerce**.</span></span>

1. <span data-ttu-id="d4d7f-216">Seleccione **Seguinte** para establecer a programación do modelo.</span><span class="sxs-lookup"><span data-stu-id="d4d7f-216">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="d4d7f-217">O modelo necesita adestrarse regularmente para aprender novos padróns cando se inxiren novos datos.</span><span class="sxs-lookup"><span data-stu-id="d4d7f-217">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="d4d7f-218">Para este exemplo, seleccione **Mensual**.</span><span class="sxs-lookup"><span data-stu-id="d4d7f-218">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="d4d7f-219">Despois de revisar todos os detalles, seleccione **Gardar e executar**.</span><span class="sxs-lookup"><span data-stu-id="d4d7f-219">After reviewing all the details, select **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="d4d7f-220">Tarefa 4: revisar resultados e explicacións do modelo</span><span class="sxs-lookup"><span data-stu-id="d4d7f-220">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="d4d7f-221">Deixe que o modelo complete o adestramento e a puntuación dos datos.</span><span class="sxs-lookup"><span data-stu-id="d4d7f-221">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="d4d7f-222">Agora pode revisar as explicacións do modelo de abandono de subscricións.</span><span class="sxs-lookup"><span data-stu-id="d4d7f-222">You can now review the subscription churn model explanations.</span></span> <span data-ttu-id="d4d7f-223">Para obter máis información, consulte [Revisar o estado e os resultados dunha predición](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="d4d7f-223">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a><span data-ttu-id="d4d7f-224">Tarefa 5: crear un segmento de clientes con alto risco de abandono</span><span class="sxs-lookup"><span data-stu-id="d4d7f-224">Task 5 - Create a segment of high churn-risk customers</span></span>

<span data-ttu-id="d4d7f-225">Executar o modelo de produción crea unha nova entidade na que pode ver en **Datos** > **Entidades**.</span><span class="sxs-lookup"><span data-stu-id="d4d7f-225">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>   

<span data-ttu-id="d4d7f-226">Pode crear un novo segmento baseado na entidade creada polo modelo.</span><span class="sxs-lookup"><span data-stu-id="d4d7f-226">You can create a new segment based on the entity created by the model.</span></span>

1.  <span data-ttu-id="d4d7f-227">Vaia a **Segmentos**.</span><span class="sxs-lookup"><span data-stu-id="d4d7f-227">Go to **Segments**.</span></span> <span data-ttu-id="d4d7f-228">Seleccione **Novo** e elixa **Crear a partir de** > **Intelixencia**.</span><span class="sxs-lookup"><span data-stu-id="d4d7f-228">Select **New** and choose **Create from** > **Intelligence**.</span></span> 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Creación dun segmento coa saída do modelo.":::

1. <span data-ttu-id="d4d7f-230">Seleccione o extremo **OOBSubscriptionChurnPrediction** e defina o segmento:</span><span class="sxs-lookup"><span data-stu-id="d4d7f-230">Select the **OOBSubscriptionChurnPrediction** endpoint and define the segment:</span></span> 
   - <span data-ttu-id="d4d7f-231">Campo: ChurnScore</span><span class="sxs-lookup"><span data-stu-id="d4d7f-231">Field: ChurnScore</span></span>
   - <span data-ttu-id="d4d7f-232">Operador: maior que</span><span class="sxs-lookup"><span data-stu-id="d4d7f-232">Operator: greater than</span></span>
   - <span data-ttu-id="d4d7f-233">Valor: 0,6</span><span class="sxs-lookup"><span data-stu-id="d4d7f-233">Value: 0.6</span></span>
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Configurar o segmento de abandono de subscricións.":::

<span data-ttu-id="d4d7f-235">Agora ten un segmento que se actualiza dinámicamente para identificar clientes con alto risco de abandono para este negocio da subscrición.</span><span class="sxs-lookup"><span data-stu-id="d4d7f-235">You now have a segment that is dynamically updated which identifies high churn-risk customers for this subscription business.</span></span>

<span data-ttu-id="d4d7f-236">Para ver máis información, consulte: [Creación e xestión de segmentos](segments.md).</span><span class="sxs-lookup"><span data-stu-id="d4d7f-236">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]