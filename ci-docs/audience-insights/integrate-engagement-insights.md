---
title: Integrar os datos web das estatísticas de participación con información do público
description: Traia información web sobre clientes desde a información sobre a participación ata a información sobre o público.
ms.date: 12/17/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mukeshpo
manager: shellyha
ms.openlocfilehash: ba1cf6c7e85b8fe90baf34018f1309095573adf1
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267674"
---
# <a name="integrate-web-data-from-engagement-insights-with-audience-insights"></a><span data-ttu-id="f2dda-103">Integrar os datos web das estatísticas de participación con información do público</span><span class="sxs-lookup"><span data-stu-id="f2dda-103">Integrate web data from engagement insights with audience insights</span></span>

<span data-ttu-id="f2dda-104">Os clientes adoitan facer as transaccións do día a día en liña mediante sitios web.</span><span class="sxs-lookup"><span data-stu-id="f2dda-104">Customers often do their day to day transactions online using web sites.</span></span> <span data-ttu-id="f2dda-105">A capacidade de información de interacción en Dynamics 365 Customer Insights é unha solución práctica para integrar datos web como orixe.</span><span class="sxs-lookup"><span data-stu-id="f2dda-105">The engagement insights capability in Dynamics 365 Customer Insights is a handy solution to integrate web data as a source.</span></span> <span data-ttu-id="f2dda-106">Ademais de datos transaccionais, demográficos ou de comportamento, podemos ver actividades na web en perfís de clientes unificados.</span><span class="sxs-lookup"><span data-stu-id="f2dda-106">In addition to transactional, demographic, or behavioral data we can see activities on the web in unified customer profiles.</span></span> <span data-ttu-id="f2dda-107">Podemos usar este perfil para obter información adicional como segmentos, medidas ou predicións para a activación do público.</span><span class="sxs-lookup"><span data-stu-id="f2dda-107">We can use this profile to gain additional insights like segments, measures, or predictions for audience activation.</span></span>

<span data-ttu-id="f2dda-108">Neste artigo descríbense os pasos para levar os datos de actividade na web dos seus clientes desde as estatísticas de participación ao seu contorno de estatísticas de público existentes.</span><span class="sxs-lookup"><span data-stu-id="f2dda-108">This article describes the steps to bring your customers’ web activity data from engagement insights into your existing audience insights environment.</span></span>

<span data-ttu-id="f2dda-109">Neste exemplo, imaxinemos un ambiente que contén perfís de clientes unificados.</span><span class="sxs-lookup"><span data-stu-id="f2dda-109">In this example, we assume an environment that contains unified customer profiles.</span></span> <span data-ttu-id="f2dda-110">Os perfís unificáronse con orixes de enquisas, vendas polo miúdo e un sistema de tíckets.</span><span class="sxs-lookup"><span data-stu-id="f2dda-110">The profiles were unified with sources from surveys, retail sales, and a ticketing system.</span></span> <span data-ttu-id="f2dda-111">Tamén mostra as actividades relacionadas cos clientes.</span><span class="sxs-lookup"><span data-stu-id="f2dda-111">It also shows the related activities of the customers.</span></span> 

<span data-ttu-id="f2dda-112">Agora queremos saber se un cliente visita as nosas propiedades web e comprende as súas actividades.</span><span class="sxs-lookup"><span data-stu-id="f2dda-112">We now want to know if a customer visits our web properties and understand their activities.</span></span> <span data-ttu-id="f2dda-113">As actividades inclúen, por exemplo, sitios web visitados ou páxinas de produtos vistas desde unha ligazón recibida nun correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="f2dda-113">Activities include, for example, visited websites or viewed product pages from a link received in an email.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f2dda-114">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="f2dda-114">Prerequisites</span></span>

<span data-ttu-id="f2dda-115">Para integrar os datos da información de participación, cómpre cumprir algúns requisitos previos:</span><span class="sxs-lookup"><span data-stu-id="f2dda-115">To integrate data from engagement insights, a few prerequisites need to be met:</span></span> 

- <span data-ttu-id="f2dda-116">Integre o SDK de información de interacción co teu sitio web.</span><span class="sxs-lookup"><span data-stu-id="f2dda-116">Integrate the engagement insights SDK with your website.</span></span> <span data-ttu-id="f2dda-117">Para obter máis información, consulte [Comezar a usar o SDK web](../engagement-insights/instrument-website.md).</span><span class="sxs-lookup"><span data-stu-id="f2dda-117">For more information, see [Get started with the web SDK](../engagement-insights/instrument-website.md).</span></span>
- <span data-ttu-id="f2dda-118">A exportación de eventos web a partir de información de interacción require acceso a unha conta de almacenamento ADLS Gen 2 que se usará para inxerir os datos de eventos web na información da audiencia.</span><span class="sxs-lookup"><span data-stu-id="f2dda-118">Exporting web events from engagement insights requires access to an ADLS Gen 2 storage account that will be used to ingest the web events data to audience insights.</span></span> <span data-ttu-id="f2dda-119">Para obter máis información, consulte [Exportar eventos](../engagement-insights/export-events.md).</span><span class="sxs-lookup"><span data-stu-id="f2dda-119">For more information, see [Export events](../engagement-insights/export-events.md).</span></span>

## <a name="configure-refined-events-in-engagement-insights"></a><span data-ttu-id="f2dda-120">Configurar eventos refinados en información de interacción</span><span class="sxs-lookup"><span data-stu-id="f2dda-120">Configure refined events in engagement insights</span></span>

<span data-ttu-id="f2dda-121">Despois de que un administrador instrumentase un sitio web co SDK de información de interacción, os *eventos básicos* recóllense cando un usuario ve unha páxina web ou fai clic nalgún lugar.</span><span class="sxs-lookup"><span data-stu-id="f2dda-121">After an administrator instrumented a website with the engagement insights SDK, *base events* are gathered when a user views a web page or clicks somewhere.</span></span> <span data-ttu-id="f2dda-122">Os eventos base adoitan conter numerosos detalles.</span><span class="sxs-lookup"><span data-stu-id="f2dda-122">Base events tend to contain numerous details.</span></span> <span data-ttu-id="f2dda-123">Dependendo do seu caso de uso, só precisa un subconxunto de datos nun evento base.</span><span class="sxs-lookup"><span data-stu-id="f2dda-123">Depending on your use case, you only need a subset of the data in a base event.</span></span> <span data-ttu-id="f2dda-124">A información de participación permítelle crear *eventos refinados* que conteñan só as propiedades dun evento base que seleccione.</span><span class="sxs-lookup"><span data-stu-id="f2dda-124">Engagement insights let you create *refined events* that contain only the properties of a base event that you select.</span></span>     

<span data-ttu-id="f2dda-125">Para obter máis información, consulte [Crear e modificar eventos refinados](../engagement-insights/refined-events.md).</span><span class="sxs-lookup"><span data-stu-id="f2dda-125">For more information, see [Create and modify refined events](../engagement-insights/refined-events.md).</span></span>

<span data-ttu-id="f2dda-126">Consideracións á hora de crear eventos refinados:</span><span class="sxs-lookup"><span data-stu-id="f2dda-126">Considerations when creating refined events:</span></span> 

- <span data-ttu-id="f2dda-127">Proporcione un nome significativo para o evento refinado.</span><span class="sxs-lookup"><span data-stu-id="f2dda-127">Provide a meaningful name for the refined event.</span></span> <span data-ttu-id="f2dda-128">Utilízase como nome de actividade nas estatísticas do público.</span><span class="sxs-lookup"><span data-stu-id="f2dda-128">It's be used as an activity name in audience insights.</span></span>
- <span data-ttu-id="f2dda-129">Seleccione polo menos as seguintes propiedades para crear unha actividade en estatísticas de audiencia:</span><span class="sxs-lookup"><span data-stu-id="f2dda-129">Select at least the following properties to create an activity in audience insights:</span></span> 
    - <span data-ttu-id="f2dda-130">Signal.Action.Name: indica os detalles da actividade</span><span class="sxs-lookup"><span data-stu-id="f2dda-130">Signal.Action.Name - indicating the activity details</span></span>
    - <span data-ttu-id="f2dda-131">Signal.User.Id: úsase para asignar co ID de cliente</span><span class="sxs-lookup"><span data-stu-id="f2dda-131">Signal.User.Id - used to map with the customer ID</span></span>
    - <span data-ttu-id="f2dda-132">Signal.View.Uri: utilízase como enderezo web como base para segmentos ou medidas</span><span class="sxs-lookup"><span data-stu-id="f2dda-132">Signal.View.Uri - used as a web address as a basis for segments or measures</span></span>
    - <span data-ttu-id="f2dda-133">Signal.Export.Id: para usar como clave principal para eventos</span><span class="sxs-lookup"><span data-stu-id="f2dda-133">Signal.Export.Id - to use as a primary key for events</span></span> <!-- system generated, do we need to list?-->
    - <span data-ttu-id="f2dda-134">Signal.Testestamp: para determinar a data e hora da actividade</span><span class="sxs-lookup"><span data-stu-id="f2dda-134">Signal.Timestamp - to determine the date and time for the activity</span></span>

<span data-ttu-id="f2dda-135">Seleccione os filtros para concentrarse nos eventos e páxinas que importan para o seu caso de uso.</span><span class="sxs-lookup"><span data-stu-id="f2dda-135">Select the filters to focus on the events and pages that matter for your use case.</span></span> <span data-ttu-id="f2dda-136">Neste exemplo, usaremos o nome da acción "Promoción por correo electrónico".</span><span class="sxs-lookup"><span data-stu-id="f2dda-136">In this example, we'll use the "Email promotion" action name.</span></span>

## <a name="export-the-refined-web-events"></a><span data-ttu-id="f2dda-137">Exportar os eventos web refinados</span><span class="sxs-lookup"><span data-stu-id="f2dda-137">Export the Refined Web Events</span></span> 

<span data-ttu-id="f2dda-138">Despois de definir o evento refinado, ten que configurar a exportación dos datos do evento a un Azure Data Lake Storage, que se pode configurar como orixe de datos para inxerir en información do público.</span><span class="sxs-lookup"><span data-stu-id="f2dda-138">After defining the refined event is defined, you have to configure the export of the event data to an Azure Data Lake Storage, that can be set as a data source for ingestion in audience insights.</span></span> <span data-ttu-id="f2dda-139">As exportacións prodúcense constantemente a medida que os eventos flúen desde a propiedade web.</span><span class="sxs-lookup"><span data-stu-id="f2dda-139">Exports happen constantly as the events flow from the web property.</span></span>

<span data-ttu-id="f2dda-140">Para obter máis información, consulte [Exportar eventos](../engagement-insights/export-events.md).</span><span class="sxs-lookup"><span data-stu-id="f2dda-140">For more information, see [Export events](../engagement-insights/export-events.md).</span></span>

## <a name="ingest-event-data-to-audience-insights"></a><span data-ttu-id="f2dda-141">Inxerir datos de eventos para obter información sobre o público</span><span class="sxs-lookup"><span data-stu-id="f2dda-141">Ingest event data to audience insights</span></span>

<span data-ttu-id="f2dda-142">Agora que definiu o evento refinado e configurou a súa exportación, pasamos a inxerir os datos para obter información sobre o público.</span><span class="sxs-lookup"><span data-stu-id="f2dda-142">Now that you have defined the refined event and configured its export, we move on to ingesting the data to audience insights.</span></span> <span data-ttu-id="f2dda-143">Debe crear unha nova orixe de datos baseada nun cartafol de Common Data Model.</span><span class="sxs-lookup"><span data-stu-id="f2dda-143">You need to create a new data source based on a Common Data Model folder.</span></span> <span data-ttu-id="f2dda-144">Introduza os detalles da conta de almacenamento á que exportar os eventos.</span><span class="sxs-lookup"><span data-stu-id="f2dda-144">Enter the details for the storage account you export the events to.</span></span> <span data-ttu-id="f2dda-145">No ficheiro *default.cdm.json*, seleccione o evento refinado para inxerir e cree a entidade en estatísticas de audiencia.</span><span class="sxs-lookup"><span data-stu-id="f2dda-145">In the *default.cdm.json* file, select the refined event to ingest and create the entity in audience insights.</span></span>

<span data-ttu-id="f2dda-146">Para obter máis información, consulte [Conectarse a un cartafol de Common Data Model usando unha conta de Azure Data Lake](connect-common-data-model.md)</span><span class="sxs-lookup"><span data-stu-id="f2dda-146">For more information, see [Connect to a Common Data Model folder using an Azure Data Lake account](connect-common-data-model.md)</span></span>


## <a name="relate-refined-event-data-as-an-activity-of-a-customer-profile"></a><span data-ttu-id="f2dda-147">Relacionar os datos de eventos refinados como unha actividade dun perfil de cliente</span><span class="sxs-lookup"><span data-stu-id="f2dda-147">Relate refined event data as an activity of a customer profile</span></span>

<span data-ttu-id="f2dda-148">Despois de completar a inxestión da entidade, pode configurar a actividade para o perfil do cliente.</span><span class="sxs-lookup"><span data-stu-id="f2dda-148">After completing the entity ingestion, you can configure the activity for the customer profile.</span></span>

<span data-ttu-id="f2dda-149">Para obter máis información, consulte [Actividades do cliente](activities.md).</span><span class="sxs-lookup"><span data-stu-id="f2dda-149">For more information, see [Customer activities](activities.md).</span></span>

:::image type="content" source="media/web-event-activity.png" alt-text="Páxina de actividades co panel da actividade Editar expandido e campos cubertos.":::

<span data-ttu-id="f2dda-151">Configure a nova actividade coa seguinte asignación:</span><span class="sxs-lookup"><span data-stu-id="f2dda-151">Configure the new activity with the following mapping:</span></span> 

- <span data-ttu-id="f2dda-152">**Clave primaria:** Signal.Export.Id, un identificador único que está dispoñible para todos os rexistros de eventos na información de interacción.</span><span class="sxs-lookup"><span data-stu-id="f2dda-152">**Primary Key:** Signal.Export.Id, a unique ID that is available for every event record in engagement insights.</span></span> <span data-ttu-id="f2dda-153">Esta propiedade xérase automaticamente.</span><span class="sxs-lookup"><span data-stu-id="f2dda-153">This property is automatically generated.</span></span>

- <span data-ttu-id="f2dda-154">**Marca de tempo:** Signal.Timestamp na propiedade do evento.</span><span class="sxs-lookup"><span data-stu-id="f2dda-154">**Timestamp:** Signal.Timestamp in the event property.</span></span>

- <span data-ttu-id="f2dda-155">**Evento:** Signal.Name, o nome do evento que desexa rastrexar.</span><span class="sxs-lookup"><span data-stu-id="f2dda-155">**Event:** Signal.Name, the event name that you want to track.</span></span>

- <span data-ttu-id="f2dda-156">**Enderezo web:** Signal.View.Uri refírese á URI da páxina que creou o evento.</span><span class="sxs-lookup"><span data-stu-id="f2dda-156">**Web address:** Signal.View.Uri referring to the uri of the page that created the event.</span></span>

- <span data-ttu-id="f2dda-157">**Detalles:** Signal.Action.Name para representar a información para asociar co evento.</span><span class="sxs-lookup"><span data-stu-id="f2dda-157">**Details:** Signal.Action.Name to represent the information to associate with the event.</span></span> <span data-ttu-id="f2dda-158">A propiedade seleccionada neste caso indica que o evento é para promoción de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="f2dda-158">The selected property in this case indicates that the event is for email promotion.</span></span>

- <span data-ttu-id="f2dda-159">**Tipo de actividade:** Neste exemplo, escollemos o tipo de actividade existente WebLog.</span><span class="sxs-lookup"><span data-stu-id="f2dda-159">**Activity type:** In this example, we choose the exsting activity type WebLog.</span></span> <span data-ttu-id="f2dda-160">Esta selección é unha opción de filtro útil para executar modelos predición ou crear segmentos baseados neste tipo de actividade.</span><span class="sxs-lookup"><span data-stu-id="f2dda-160">This selection is a useful filter option to run prediction models or create segments based on this activity type.</span></span>

- <span data-ttu-id="f2dda-161">**Establecer relación:** Esta importante configuración vincula a actividade cos perfís de clientes existentes.</span><span class="sxs-lookup"><span data-stu-id="f2dda-161">**Set up relationship:** This important setting ties the activity to existing customer profiles.</span></span> <span data-ttu-id="f2dda-162">**Signal.User.Id** é o identificador configurado no SDK para ser recollido e que se relaciona co ID de usuario noutras orixes de datos que están configuradas nas estatísticas de audiencia.</span><span class="sxs-lookup"><span data-stu-id="f2dda-162">**Signal.User.Id** is the identifier configured in the SDK to be collected and that relates to the user ID in other data sources that are configured in audience insights.</span></span> <span data-ttu-id="f2dda-163">Neste exemplo, configuramos a relación entre Signal.User.Id e RetailCustomers: CustomerRetailId, que é a clave principal que se definiu no paso de asignación do proceso de unificación de datos.</span><span class="sxs-lookup"><span data-stu-id="f2dda-163">In this example, we configure the relationship between Signal.User.Id and RetailCustomers:CustomerRetailId, which is the primary key that was deinfed in the map step of the data unification process.</span></span>


<span data-ttu-id="f2dda-164">Despois de procesar as actividades, pode revisar os rexistros dos clientes e abrir unha tarxeta de cliente para ver as actividades a partir da información de interacción na cronoloxía.</span><span class="sxs-lookup"><span data-stu-id="f2dda-164">After processing the activities, you can review customer records and open a customer card to see activities from engagement insights in the timeline.</span></span> 

> [!TIP]
> <span data-ttu-id="f2dda-165">Para atopar un identificador de cliente que teña unha actividade de información de interacción, vaia a **Entidades** e previsualice os datos da entidade UnifiedActivity.</span><span class="sxs-lookup"><span data-stu-id="f2dda-165">To find a customer id that has an engagement insights activity, go to **Entities** and preview the data for the UnifiedActivity entity.</span></span> <span data-ttu-id="f2dda-166">ActivityTypeDisplay = WebLog contén a actividade de información de interacción configurada no exemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="f2dda-166">ActivityTypeDisplay = WebLog contain the engagement insights activity configured in the example above.</span></span> <span data-ttu-id="f2dda-167">Copie o ID de cliente para un deses rexistros e para ese ID na páxina **Clientes**.</span><span class="sxs-lookup"><span data-stu-id="f2dda-167">Copy the customer ID for one of those records and for that ID on the **Customers** page.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f2dda-168">Seguintes pasos</span><span class="sxs-lookup"><span data-stu-id="f2dda-168">Next Steps</span></span>

<span data-ttu-id="f2dda-169">Agora pode crear [segmentos](segments.md), [medidas](measures.md) e [predicións](predictions.md) para establecer unha conexión significativa cos seus clientes.</span><span class="sxs-lookup"><span data-stu-id="f2dda-169">You can now create [segments](segments.md), [measures](measures.md), and [predictions](predictions.md) to make a meaningful connection with your customers.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]