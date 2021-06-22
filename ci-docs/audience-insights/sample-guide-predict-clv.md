---
title: Guía de mostra de predición do valor de duración do cliente
description: Utilice esta guía de mostra para probar o modelo de predición do valor de duración do cliente.
ms.date: 05/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: 73d294a285b4ad706bec7fe925c1daa0b839ddd6
ms.sourcegitcommit: 7b6189e47ed1f87e7ce35d40e4cf7a6730f31ef2
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 06/01/2021
ms.locfileid: "6129943"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a><span data-ttu-id="b5f76-103">Guía de mostra de predición do valor de duración do cliente (VDC)</span><span class="sxs-lookup"><span data-stu-id="b5f76-103">Customer lifetime value (CLV) prediction sample guide</span></span>

<span data-ttu-id="b5f76-104">Esta guía explicaralle un exemplo integral da predición do valor de duración do cliente (VDC) en Customer Insights usando datos de exemplo.</span><span class="sxs-lookup"><span data-stu-id="b5f76-104">This guide will walk you through an end to end example of Customer lifetime value (CLV) prediction in Customer Insights using sample data.</span></span>

## <a name="scenario"></a><span data-ttu-id="b5f76-105">Escenario</span><span class="sxs-lookup"><span data-stu-id="b5f76-105">Scenario</span></span>

<span data-ttu-id="b5f76-106">Contoso é unha empresa que produce café e máquinas de café de alta calidade.</span><span class="sxs-lookup"><span data-stu-id="b5f76-106">Contoso is a company that produces high-quality coffee and coffee machines.</span></span> <span data-ttu-id="b5f76-107">Venden os produtos a través do sitio web de Contoso Coffee.</span><span class="sxs-lookup"><span data-stu-id="b5f76-107">They sell the products through their Contoso Coffee website.</span></span> <span data-ttu-id="b5f76-108">A empresa quere comprender o valor (ingresos) que poden xerar os seus clientes nos próximos 12 meses.</span><span class="sxs-lookup"><span data-stu-id="b5f76-108">The company wants to understand the value (revenue) that their customers can generate in the next 12 months.</span></span> <span data-ttu-id="b5f76-109">Coñecer o valor esperado dos seus clientes nos próximos 12 meses axudaralles a dirixir os seus esforzos de márketing cara a clientes valiosos.</span><span class="sxs-lookup"><span data-stu-id="b5f76-109">Knowing the expected value of their customers in the next 12 months will help them steer their marketing efforts on high value customers.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b5f76-110">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="b5f76-110">Prerequisites</span></span>

- <span data-ttu-id="b5f76-111">Polo menos [permisos de colaborador](permissions.md) na información do público.</span><span class="sxs-lookup"><span data-stu-id="b5f76-111">At least [Contributor permissions](permissions.md) in audience insights.</span></span>
- <span data-ttu-id="b5f76-112">Recomendámoslle que implemente os seguintes pasos [nun novo ambiente](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="b5f76-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="b5f76-113">Tarefa 1: inxerir datos</span><span class="sxs-lookup"><span data-stu-id="b5f76-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="b5f76-114">Revise os artigos [sobre a inxestión de datos](data-sources.md) e [a importación de orixes de datos usando conectores de Power Query](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="b5f76-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md).</span></span> <span data-ttu-id="b5f76-115">A seguinte información supón que está familiarizado coa inxestión de datos en xeral.</span><span class="sxs-lookup"><span data-stu-id="b5f76-115">The following information assumes you familiarized with ingesting data in general.</span></span>

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="b5f76-116">Inxerir datos de clientes desde a plataforma de comercio electrónico</span><span class="sxs-lookup"><span data-stu-id="b5f76-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="b5f76-117">Cree unha orixe de datos denominada **eCommerce**, escolla a opción de importación e seleccione o conector **Texto/CSV**.</span><span class="sxs-lookup"><span data-stu-id="b5f76-117">Create a data source named  **eCommerce** , choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="b5f76-118">Insira o URL dos contactos de eCommerce [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).</span><span class="sxs-lookup"><span data-stu-id="b5f76-118">Enter the URL for eCommerce contacts [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).</span></span>

1. <span data-ttu-id="b5f76-119">Mentres edita os datos, seleccione **Transformar** e logo **Usar a primeira fila como cabeceiras**.</span><span class="sxs-lookup"><span data-stu-id="b5f76-119">While editing the data, select  **Transform**  and then  **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="b5f76-120">Actualice o tipo de datos para as columnas listadas a continuación:</span><span class="sxs-lookup"><span data-stu-id="b5f76-120">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="b5f76-121">**DateOfBirth**: data</span><span class="sxs-lookup"><span data-stu-id="b5f76-121">**DateOfBirth** : Date</span></span>
   - <span data-ttu-id="b5f76-122">**CreatedOn**: data/hora/fuso</span><span class="sxs-lookup"><span data-stu-id="b5f76-122">**CreatedOn** : Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transforme a data de nacemento en data.":::

1. <span data-ttu-id="b5f76-124">No campo "Nome" no panel da dereita, cambie o nome da súa orixe de datos de **Consulta** a **eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="b5f76-124">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="b5f76-125">**Garde** a orixe de datos.</span><span class="sxs-lookup"><span data-stu-id="b5f76-125">**Save** the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="b5f76-126">Inxerir datos de compra en liña</span><span class="sxs-lookup"><span data-stu-id="b5f76-126">Ingest online purchase data</span></span>

1. <span data-ttu-id="b5f76-127">Engada outro conxunto de datos á mesma orixe de datos de **comercio electrónico**.</span><span class="sxs-lookup"><span data-stu-id="b5f76-127">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="b5f76-128">Escolla o conector **Texto/CSV** de novo.</span><span class="sxs-lookup"><span data-stu-id="b5f76-128">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="b5f76-129">Introduza o URL para datos de **compras en liña** https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="b5f76-129">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="b5f76-130">Mentres edita os datos, seleccione **Transformar** e logo **Usar a primeira fila como cabeceiras**.</span><span class="sxs-lookup"><span data-stu-id="b5f76-130">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="b5f76-131">Actualice o tipo de datos para as columnas listadas a continuación:</span><span class="sxs-lookup"><span data-stu-id="b5f76-131">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="b5f76-132">**PurchasedOn**: data/hora</span><span class="sxs-lookup"><span data-stu-id="b5f76-132">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="b5f76-133">**TotalPrice**: moeda</span><span class="sxs-lookup"><span data-stu-id="b5f76-133">**TotalPrice**: Currency</span></span>

1. <span data-ttu-id="b5f76-134">No campo **Nome** do panel lateral, cambie o nome da súa orixe de datos de **Consulta** a **eCommercePurchases**.</span><span class="sxs-lookup"><span data-stu-id="b5f76-134">In the **Name** field on the side pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="b5f76-135">**Garde** a orixe de datos.</span><span class="sxs-lookup"><span data-stu-id="b5f76-135">**Save** the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="b5f76-136">Inxerir datos de clientes desde o esquema de fidelización</span><span class="sxs-lookup"><span data-stu-id="b5f76-136">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="b5f76-137">Cree unha orixe de datos denominada **LoyaltyScheme**, escolla a opción de importación e seleccione o conector **Texto/CSV**.</span><span class="sxs-lookup"><span data-stu-id="b5f76-137">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="b5f76-138">Insira o URL dos contactos de comercio electrónico https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="b5f76-138">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="b5f76-139">Mentres edita os datos, seleccione **Transformar** e logo **Usar a primeira fila como cabeceiras**.</span><span class="sxs-lookup"><span data-stu-id="b5f76-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="b5f76-140">Actualice o tipo de datos para as columnas listadas a continuación:</span><span class="sxs-lookup"><span data-stu-id="b5f76-140">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="b5f76-141">**DateOfBirth**: data</span><span class="sxs-lookup"><span data-stu-id="b5f76-141">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="b5f76-142">**RewardsPoints**: número enteiro</span><span class="sxs-lookup"><span data-stu-id="b5f76-142">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="b5f76-143">**CreatedOn**: data/hora</span><span class="sxs-lookup"><span data-stu-id="b5f76-143">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="b5f76-144">No campo **Nome** no panel da dereita, cambie o nome da súa orixe de datos de **Consulta** a **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="b5f76-144">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="b5f76-145">**Garde** a orixe de datos.</span><span class="sxs-lookup"><span data-stu-id="b5f76-145">**Save** the data source.</span></span>

### <a name="ingest-customer-data-from-website-reviews"></a><span data-ttu-id="b5f76-146">Inxerir datos de clientes a partir de comentarios de sitios web</span><span class="sxs-lookup"><span data-stu-id="b5f76-146">Ingest customer data from website reviews</span></span>

1. <span data-ttu-id="b5f76-147">Cree unha orixe de datos denominada **Website**, escolla a opción de importación e seleccione o conector **Texto/CSV**.</span><span class="sxs-lookup"><span data-stu-id="b5f76-147">Create a data source named **Website**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="b5f76-148">Insira o URL dos contactos de comercio electrónico https://aka.ms/CI-ILT/WebReviews.</span><span class="sxs-lookup"><span data-stu-id="b5f76-148">Enter the URL for eCommerce contacts https://aka.ms/CI-ILT/WebReviews.</span></span>

1. <span data-ttu-id="b5f76-149">Mentres edita os datos, seleccione **Transformar** e logo **Usar a primeira fila como cabeceiras**.</span><span class="sxs-lookup"><span data-stu-id="b5f76-149">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="b5f76-150">Actualice o tipo de datos para as columnas listadas a continuación:</span><span class="sxs-lookup"><span data-stu-id="b5f76-150">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="b5f76-151">**ReviewRating**: número decimal</span><span class="sxs-lookup"><span data-stu-id="b5f76-151">**ReviewRating**: Decimal number</span></span>
   - <span data-ttu-id="b5f76-152">**ReviewDate**: data</span><span class="sxs-lookup"><span data-stu-id="b5f76-152">**ReviewDate**: Date</span></span>

1. <span data-ttu-id="b5f76-153">No campo "Nome" no panel da dereita, cambie o nome da súa orixe de datos de **Consulta** a **Revisións**.</span><span class="sxs-lookup"><span data-stu-id="b5f76-153">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **Reviews**.</span></span>

1. <span data-ttu-id="b5f76-154">**Garde** a orixe de datos.</span><span class="sxs-lookup"><span data-stu-id="b5f76-154">**Save** the data source.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="b5f76-155">Tarefa 2: unificación de datos</span><span class="sxs-lookup"><span data-stu-id="b5f76-155">Task 2 - Data unification</span></span>

<span data-ttu-id="b5f76-156">Despois de inxerir os datos, comezamos o proceso de unificación de datos para crear un perfil de cliente unificado.</span><span class="sxs-lookup"><span data-stu-id="b5f76-156">After ingesting the data, we now begin the data unification process to create a unified customer profile.</span></span> <span data-ttu-id="b5f76-157">Para obter máis información, consulte [Unificación de datos](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="b5f76-157">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="b5f76-158">Asignar</span><span class="sxs-lookup"><span data-stu-id="b5f76-158">Map</span></span>

1. <span data-ttu-id="b5f76-159">Despois de inxerir os datos, asigne os contactos desde os datos de comercio electrónico e de fidelización a tipos de datos comúns.</span><span class="sxs-lookup"><span data-stu-id="b5f76-159">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="b5f76-160">Vaia a **Datos** > **Unificar** > **Asignar**.</span><span class="sxs-lookup"><span data-stu-id="b5f76-160">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="b5f76-161">Seleccione as entidades que representan o perfil do cliente: **eCommerceContacts** e **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="b5f76-161">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> <span data-ttu-id="b5f76-162">A continuación, seleccione **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="b5f76-162">Then, select **Apply**.</span></span>

   ![unificar fontes de datos de comercio electrónico e fidelización.](media/unify-ecommerce-loyalty.png)

1. <span data-ttu-id="b5f76-164">Seleccione **ContactId** como clave primaria para **eCommerceContacts** e **LoyaltyID** como clave primaria para **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="b5f76-164">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   ![Unificar LoyaltyId como clave principal.](media/unify-loyaltyid.png)

1. <span data-ttu-id="b5f76-166">Seleccione **Gardar**.</span><span class="sxs-lookup"><span data-stu-id="b5f76-166">Select **Save**.</span></span>

### <a name="match"></a><span data-ttu-id="b5f76-167">Buscar coincidencias</span><span class="sxs-lookup"><span data-stu-id="b5f76-167">Match</span></span>

1. <span data-ttu-id="b5f76-168">Vaia ao separador **Buscar coincidencias** e seleccione **Definir orde**.</span><span class="sxs-lookup"><span data-stu-id="b5f76-168">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="b5f76-169">No lista despregable **Primario**, escolla **eCommerceContacts: eCommerce** como fonte principal e inclúa todos os rexistros.</span><span class="sxs-lookup"><span data-stu-id="b5f76-169">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="b5f76-170">Na lista despregable **Entidade 2**, escolla **loyCustomers: LoyaltyScheme** e inclúa todos os rexistros.</span><span class="sxs-lookup"><span data-stu-id="b5f76-170">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   ![unificar coincidencias de comercio electrónico e fidelización.](media/unify-match-order.png)

1. <span data-ttu-id="b5f76-172">Seleccione **Engadir regra**.</span><span class="sxs-lookup"><span data-stu-id="b5f76-172">Select **Add rule**</span></span>

1. <span data-ttu-id="b5f76-173">Engada a súa primeira condición usando FullName.</span><span class="sxs-lookup"><span data-stu-id="b5f76-173">Add your first condition using FullName.</span></span>

   - <span data-ttu-id="b5f76-174">Para eCommerceContacts, seleccione **FullName** no menú despregable.</span><span class="sxs-lookup"><span data-stu-id="b5f76-174">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="b5f76-175">Para loyCustomers, seleccione **FullName** no menú despregable.</span><span class="sxs-lookup"><span data-stu-id="b5f76-175">For loyCustomers select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="b5f76-176">Seleccione o menú despregable **Normalizar** e escolla **Tipo (teléfono, nome, enderezo...)**.</span><span class="sxs-lookup"><span data-stu-id="b5f76-176">Select the **Normalize** drop-down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   - <span data-ttu-id="b5f76-177">Defina o **Nivel de precisión**: **Básico** e **Valor**: **Alto**.</span><span class="sxs-lookup"><span data-stu-id="b5f76-177">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="b5f76-178">Introduza o nome **FullName, Email** para a nova regra.</span><span class="sxs-lookup"><span data-stu-id="b5f76-178">Enter the name **FullName, Email** for the new rule.</span></span>

   - <span data-ttu-id="b5f76-179">Engada unha segunda condición para o enderezo de correo electrónico seleccionando **Engadir condición**</span><span class="sxs-lookup"><span data-stu-id="b5f76-179">Add a second condition for email address by selecting **Add Condition**</span></span>
   - <span data-ttu-id="b5f76-180">Para os eCommerceContacts da entidade, escolla **EMail** no menú despregable.</span><span class="sxs-lookup"><span data-stu-id="b5f76-180">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   - <span data-ttu-id="b5f76-181">Para os loyCustomers da entidade, escolla **EMail** no menú despregable.</span><span class="sxs-lookup"><span data-stu-id="b5f76-181">For entity loyCustomers, choose **EMail** in the drop-down.</span></span>
   - <span data-ttu-id="b5f76-182">Deixe Normalizar en branco.</span><span class="sxs-lookup"><span data-stu-id="b5f76-182">Leave Normalize blank.</span></span>
   - <span data-ttu-id="b5f76-183">Defina o **Nivel de precisión**: **Básico** e **Valor**: **Alto**.</span><span class="sxs-lookup"><span data-stu-id="b5f76-183">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   ![Unificar a regra de coincidencia para o nome e o correo electrónico.](media/unify-match-rule.png)

1. <span data-ttu-id="b5f76-185">Seleccione **Feito**.</span><span class="sxs-lookup"><span data-stu-id="b5f76-185">Select **Done**.</span></span>

1. <span data-ttu-id="b5f76-186">Seleccione **Gardar** e **Executar**.</span><span class="sxs-lookup"><span data-stu-id="b5f76-186">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="b5f76-187">Combinación</span><span class="sxs-lookup"><span data-stu-id="b5f76-187">Merge</span></span>

1. <span data-ttu-id="b5f76-188">Vaia ao separador **Combinar**.</span><span class="sxs-lookup"><span data-stu-id="b5f76-188">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="b5f76-189">No **ContactId** da entidade **loyCustomers**, cambie o nome de visualización a **ContactIdLOYALTY** para diferencialo dos outros identificadores inxeridos.</span><span class="sxs-lookup"><span data-stu-id="b5f76-189">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   ![renomear contactid do identificador de fidelidade.](media/unify-merge-contactid.png)

1. <span data-ttu-id="b5f76-191">Seleccione **Gardar** e **Executar combinación e procesos descendentes**.</span><span class="sxs-lookup"><span data-stu-id="b5f76-191">Select **Save** and **Run merge and downstream processes**.</span></span>

## <a name="task-3---configure-customer-lifetime-value-prediction"></a><span data-ttu-id="b5f76-192">Tarefa 3: Configurar a predición do valor de duración do cliente</span><span class="sxs-lookup"><span data-stu-id="b5f76-192">Task 3 - Configure customer lifetime value prediction</span></span>

<span data-ttu-id="b5f76-193">Cos perfís de clientes unificados no seu lugar, agora podemos executar a predición do valor de duración do cliente.</span><span class="sxs-lookup"><span data-stu-id="b5f76-193">With the unified customer profiles in place, we can now run the customer lifetime value prediction.</span></span> <span data-ttu-id="b5f76-194">Para obter os pasos detallados, consulte [Predición do valor de duración do cliente (versión preliminar)](predict-customer-lifetime-value.md).</span><span class="sxs-lookup"><span data-stu-id="b5f76-194">For detailed steps, see [Customer Lifetime Value prediction (preview)](predict-customer-lifetime-value.md).</span></span>

1. <span data-ttu-id="b5f76-195">Vaia a **Intelixencia**  > **Predicións** e seleccione o **Modelo de valor de duración do cliente**.</span><span class="sxs-lookup"><span data-stu-id="b5f76-195">Go to  **Intelligence**  > **Predictions**  and select the **Customer lifetime value model**.</span></span>

1. <span data-ttu-id="b5f76-196">Consulte a información no panel lateral e seleccione **Comezar**.</span><span class="sxs-lookup"><span data-stu-id="b5f76-196">Go through the information in the side pane and select **Get started**.</span></span>

1. <span data-ttu-id="b5f76-197">Nomee o modelo **OOB eCommerce CLV Prediction** e a entidade de saída **OOBeCommerceCLVPrediction**.</span><span class="sxs-lookup"><span data-stu-id="b5f76-197">Name the model **OOB eCommerce CLV Prediction** and the output entity  **OOBeCommerceCLVPrediction**.</span></span>

1. <span data-ttu-id="b5f76-198">Defina as preferencias do modelo para o modelo VDC:</span><span class="sxs-lookup"><span data-stu-id="b5f76-198">Define model preferences for the CLV model:</span></span>
   - <span data-ttu-id="b5f76-199">**Período de tempo da predición**: **12 meses ou un ano**.</span><span class="sxs-lookup"><span data-stu-id="b5f76-199">**Prediction time period**: **12 months or 1 year**.</span></span> <span data-ttu-id="b5f76-200">Esta configuración define o período de tempo futuro para predicir o valor de duración do cliente.</span><span class="sxs-lookup"><span data-stu-id="b5f76-200">This setting defines how far into the future to predict customer lifetime value.</span></span>
   - <span data-ttu-id="b5f76-201">**Clientes activos**: especifique que significan os clientes activos para a súa empresa.</span><span class="sxs-lookup"><span data-stu-id="b5f76-201">**Active customers**: Specify what active customers mean for your business.</span></span> <span data-ttu-id="b5f76-202">Estableza o intervalo temporal histórico no que un cliente debe ter polo menos unha transacción para considerarse activo.</span><span class="sxs-lookup"><span data-stu-id="b5f76-202">Set the historical time frame in which a customer must have had at least one transaction to be considered active.</span></span> <span data-ttu-id="b5f76-203">O modelo só predicirá o VDC para clientes activos.</span><span class="sxs-lookup"><span data-stu-id="b5f76-203">The model will only predict CLV for active customers.</span></span> <span data-ttu-id="b5f76-204">Escolla entre deixar que o modelo calcule o período de tempo en base aos datos históricos das transaccións ou proporcione un intervalo temporal específico.</span><span class="sxs-lookup"><span data-stu-id="b5f76-204">Choose between letting the model calculate the time period based on historical transaction data or provide a specific time frame.</span></span> <span data-ttu-id="b5f76-205">Nesta guía de mostra, **deixaremos que o modelo calcule o intervalo de compras**, que é a opción predefinida.</span><span class="sxs-lookup"><span data-stu-id="b5f76-205">In this sample guide, we **let the model calculate purchase interval**, which is the default option.</span></span>
   - <span data-ttu-id="b5f76-206">**Clientes valiosos**: defina os clientes valiosos como un percentil dos clientes que máis pagan.</span><span class="sxs-lookup"><span data-stu-id="b5f76-206">**High value customers**: Define high value customers as a percentile of top-paying customers.</span></span> <span data-ttu-id="b5f76-207">O modelo utiliza esta entrada para proporcionar resultados que se axusten á definición da súa empresa de clientes valiosos.</span><span class="sxs-lookup"><span data-stu-id="b5f76-207">The model uses this input to provide results that fit your business definition of high value customers.</span></span> <span data-ttu-id="b5f76-208">Pode permitir que o modelo defina os clientes valiosos.</span><span class="sxs-lookup"><span data-stu-id="b5f76-208">You can choose to let the model define high value customers.</span></span> <span data-ttu-id="b5f76-209">Emprega unha regra heurística que deriva o percentil.</span><span class="sxs-lookup"><span data-stu-id="b5f76-209">It uses a heuristic rule that derives the percentile.</span></span> <span data-ttu-id="b5f76-210">Tamén pode definir os clientes valiosos como un percentil dos clientes futuros que máis pagarán.</span><span class="sxs-lookup"><span data-stu-id="b5f76-210">You can also define high value customers as a percentile of top future paying customers.</span></span> <span data-ttu-id="b5f76-211">Nesta guía de exemplo, definimos manualmente os clientes valiosos como **o 30 % superior dos clientes activos que pagan** e seleccione **Seguinte**.</span><span class="sxs-lookup"><span data-stu-id="b5f76-211">In this sample guide, we manually define high value customers as **top 30% of active paying customers** and select **Next**.</span></span>

    :::image type="content" source="media/clv-model-preferences.png" alt-text="Paso de preferencias na experiencia guiada para o modelo VDC.":::

1. <span data-ttu-id="b5f76-213">No paso **Datos necesarios**, seleccione **Engadir datos** para fornecer os datos do historial de transaccións.</span><span class="sxs-lookup"><span data-stu-id="b5f76-213">In the **Required Data** step, select **Add data** to provide the transaction history data.</span></span>

1. <span data-ttu-id="b5f76-214">Engada a entidade **eCommercePurchases : eCommerce** e asigne os atributos que o modelo precisa:</span><span class="sxs-lookup"><span data-stu-id="b5f76-214">Add the **eCommercePurchases : eCommerce** entity and map the attributes that are required by the model:</span></span>
   - <span data-ttu-id="b5f76-215">ID da transacción: eCommerce.eCommercePurchases.PurchaseId</span><span class="sxs-lookup"><span data-stu-id="b5f76-215">Transaction ID: eCommerce.eCommercePurchases.PurchaseId</span></span>
   - <span data-ttu-id="b5f76-216">Data da transacción: eCommerce.eCommercePurchases.PurchasedOn</span><span class="sxs-lookup"><span data-stu-id="b5f76-216">Transaction date: eCommerce.eCommercePurchases.PurchasedOn</span></span>
   - <span data-ttu-id="b5f76-217">Importe da transacción: eCommerce.eCommercePurchases.TotalPrice</span><span class="sxs-lookup"><span data-stu-id="b5f76-217">Transaction amount: eCommerce.eCommercePurchases.TotalPrice</span></span>
   - <span data-ttu-id="b5f76-218">ID do produto: eCommerce.eCommercePurchases.ProductId</span><span class="sxs-lookup"><span data-stu-id="b5f76-218">Product ID: eCommerce.eCommercePurchases.ProductId</span></span>

1. <span data-ttu-id="b5f76-219">Seleccione **Seguinte**.</span><span class="sxs-lookup"><span data-stu-id="b5f76-219">Select **Next**.</span></span>

1. <span data-ttu-id="b5f76-220">Configure a relación entre a entidade **eCommercePurchases : eCommerce** e **eCommerceContacts : eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="b5f76-220">Set up the relationship between the **eCommercePurchases : eCommerce** entity and  **eCommerceContacts : eCommerce**.</span></span>

1. <span data-ttu-id="b5f76-221">O paso **Datos adicionais (opcional)** permítelle engadir máis datos de actividade do cliente.</span><span class="sxs-lookup"><span data-stu-id="b5f76-221">The **Additional data (optional)** step allows you to add more customer activity data.</span></span> <span data-ttu-id="b5f76-222">Estes datos poden axudar a obter máis información para as interaccións dos clientes coa súa empresa, o que pode contribuír ao VDC.</span><span class="sxs-lookup"><span data-stu-id="b5f76-222">This data can help to get more insights for customer interactions with your business, which can contribute to CLV.</span></span> <span data-ttu-id="b5f76-223">Engadir interaccións clave dos clientes, como rexistros web, rexistros do servizo de atención ao cliente ou historial do programa de recompensa, pode mellorar a precisión das predicións.</span><span class="sxs-lookup"><span data-stu-id="b5f76-223">Adding key customer interactions like web logs, customer service logs, or rewards program history can improve the accuracy of predictions.</span></span> <span data-ttu-id="b5f76-224">Seleccione **Engadir datos** para incluír máis datos de actividade do cliente.</span><span class="sxs-lookup"><span data-stu-id="b5f76-224">Select **Add data** to include more customer activity data.</span></span>

1. <span data-ttu-id="b5f76-225">Engada a entidade de actividade do cliente e asigne os nomes dos seus campos aos campos correspondentes requiridos polo modelo:</span><span class="sxs-lookup"><span data-stu-id="b5f76-225">Add the customer activity entity and map its fields names to the corresponding fields required by the model:</span></span>
   - <span data-ttu-id="b5f76-226">Entidade de actividade do cliente: Reviews:Website</span><span class="sxs-lookup"><span data-stu-id="b5f76-226">Customer activity entity: Reviews:Website</span></span>
   - <span data-ttu-id="b5f76-227">Clave principal: Website.Reviews.ReviewId</span><span class="sxs-lookup"><span data-stu-id="b5f76-227">Primary key: Website.Reviews.ReviewId</span></span>
   - <span data-ttu-id="b5f76-228">Marca de tempo: Website.Reviews.ReviewDate</span><span class="sxs-lookup"><span data-stu-id="b5f76-228">Timestamp: Website.Reviews.ReviewDate</span></span>
   - <span data-ttu-id="b5f76-229">Evento (nome da actividade): Website.Reviews.ActivityTypeDisplay</span><span class="sxs-lookup"><span data-stu-id="b5f76-229">Event (activity name): Website.Reviews.ActivityTypeDisplay</span></span>
   - <span data-ttu-id="b5f76-230">Detalles (importe ou valor): Website.Reviews.ReviewRating</span><span class="sxs-lookup"><span data-stu-id="b5f76-230">Details (amount or value): Website.Reviews.ReviewRating</span></span>

1. <span data-ttu-id="b5f76-231">Seleccione **Seguinte** e configure a actividade e a relación entre os datos da transacción e os datos do cliente:</span><span class="sxs-lookup"><span data-stu-id="b5f76-231">Select **Next** and configure the activity and the relationship between the transaction data and the customer data:</span></span>  
   - <span data-ttu-id="b5f76-232">Tipo de actividade: escoller existente</span><span class="sxs-lookup"><span data-stu-id="b5f76-232">Activity type: Choose existing</span></span>
   - <span data-ttu-id="b5f76-233">Etiqueta de actividade: revisar</span><span class="sxs-lookup"><span data-stu-id="b5f76-233">Activity label: Review</span></span>
   - <span data-ttu-id="b5f76-234">Etiqueta correspondente: Website.Reviews.UserId</span><span class="sxs-lookup"><span data-stu-id="b5f76-234">Corresponding label: Website.Reviews.UserId</span></span>
   - <span data-ttu-id="b5f76-235">Entidade de cliente: eCommerceContacts:eCommerce</span><span class="sxs-lookup"><span data-stu-id="b5f76-235">Customer entity: eCommerceContacts:eCommerce</span></span>
   - <span data-ttu-id="b5f76-236">Relación: WebsiteReviews</span><span class="sxs-lookup"><span data-stu-id="b5f76-236">Relationship: WebsiteReviews</span></span>

1. <span data-ttu-id="b5f76-237">Seleccione **Seguinte** para establecer a programación do modelo.</span><span class="sxs-lookup"><span data-stu-id="b5f76-237">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="b5f76-238">O modelo necesita adestrarse regularmente para aprender novos padróns cando se inxiren novos datos.</span><span class="sxs-lookup"><span data-stu-id="b5f76-238">The model needs to train regularly to learn new patterns when there's new data ingested.</span></span> <span data-ttu-id="b5f76-239">Para este exemplo, escolla **Mensual**.</span><span class="sxs-lookup"><span data-stu-id="b5f76-239">For this example, choose **Monthly**.</span></span>

1. <span data-ttu-id="b5f76-240">Despois de revisar todos os detalles, seleccione **Gardar e executar**.</span><span class="sxs-lookup"><span data-stu-id="b5f76-240">After reviewing all the details, select  **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="b5f76-241">Tarefa 4: revisar resultados e explicacións do modelo</span><span class="sxs-lookup"><span data-stu-id="b5f76-241">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="b5f76-242">Deixe que o modelo complete o adestramento e a puntuación dos datos.</span><span class="sxs-lookup"><span data-stu-id="b5f76-242">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="b5f76-243">A continuación, pode revisar os resultados e explicacións do modelo VDC.</span><span class="sxs-lookup"><span data-stu-id="b5f76-243">Next, you can review the CLV model results and explanations.</span></span> <span data-ttu-id="b5f76-244">Para obter máis información, consulte [Revisar o estado e os resultados dunha predición](predict-customer-lifetime-value.md#review-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="b5f76-244">For more information, see [Review a prediction status and results](predict-customer-lifetime-value.md#review-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-value-customers"></a><span data-ttu-id="b5f76-245">Tarefa 5: Crear un segmento de clientes valiosos</span><span class="sxs-lookup"><span data-stu-id="b5f76-245">Task 5 - Create a segment of high value customers</span></span>

<span data-ttu-id="b5f76-246">Ao executar o modelo créase unha nova entidade, que aparece na lista **Datos** > **Entidades**.</span><span class="sxs-lookup"><span data-stu-id="b5f76-246">Running the model creates a new entity, which is listed on **Data** > **Entities**.</span></span> <span data-ttu-id="b5f76-247">Pode crear un novo segmento de clientes baseado na entidade creada polo modelo.</span><span class="sxs-lookup"><span data-stu-id="b5f76-247">You can create a new customer segment based on the entity created by the model.</span></span>

1. <span data-ttu-id="b5f76-248">Vaia a **Segmentos**.</span><span class="sxs-lookup"><span data-stu-id="b5f76-248">Go to **Segments**.</span></span> 

1. <span data-ttu-id="b5f76-249">Seleccione **Novo** e elixa **Crear a partir de** > **Intelixencia**.</span><span class="sxs-lookup"><span data-stu-id="b5f76-249">Select  **New** and choose **Create from** > **Intelligence**.</span></span>

   ![Creación dun segmento coa saída do modelo.](media/segment-intelligence.png)

1. <span data-ttu-id="b5f76-251">Seleccione a entidade **OOBeCommerceCLVPrediction** e defina o segmento:</span><span class="sxs-lookup"><span data-stu-id="b5f76-251">Select the  **OOBeCommerceCLVPrediction** entity and define the segment:</span></span>
  - <span data-ttu-id="b5f76-252">Campo: CLVScore</span><span class="sxs-lookup"><span data-stu-id="b5f76-252">Field: CLVScore</span></span>
  - <span data-ttu-id="b5f76-253">Operador: maior que</span><span class="sxs-lookup"><span data-stu-id="b5f76-253">Operator: greater than</span></span>
  - <span data-ttu-id="b5f76-254">Valor: 1500</span><span class="sxs-lookup"><span data-stu-id="b5f76-254">Value: 1500</span></span>

1. <span data-ttu-id="b5f76-255">Seleccione **Revisar** e **Gardar** o segmento.</span><span class="sxs-lookup"><span data-stu-id="b5f76-255">Select **Review** and **Save** the segment.</span></span>

<span data-ttu-id="b5f76-256">Agora ten un segmento que identifica os clientes que se predí que xeren ingresos superiores a 1500 $ nos próximos 12 meses.</span><span class="sxs-lookup"><span data-stu-id="b5f76-256">You now have a segment that identifies customers who are predicted to generate more than $1500 of revenue in the next 12 months.</span></span> <span data-ttu-id="b5f76-257">Este segmento actualízase dinamicamente se se inxiren máis datos.</span><span class="sxs-lookup"><span data-stu-id="b5f76-257">This segment gets updated dynamically if more data is ingested.</span></span>

<span data-ttu-id="b5f76-258">Para ver máis información, consulte: [Creación e xestión de segmentos](segments.md).</span><span class="sxs-lookup"><span data-stu-id="b5f76-258">For more information, see [Create and manage segments](segments.md).</span></span>
