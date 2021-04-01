---
title: Inxestión e limitacións de datos en tempo real
description: Información xeral sobre capacidades en tempo real nas estatísticas do público.
ms.date: 10/27/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 3c84cfe7441eb026c1fd45eda1f72421388d01d7
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598567"
---
# <a name="real-time-data-ingestion-preview"></a><span data-ttu-id="8baf0-103">Inxestión de datos en tempo real (vista previa)</span><span class="sxs-lookup"><span data-stu-id="8baf0-103">Real-time data ingestion (preview)</span></span>

<span data-ttu-id="8baf0-104">A funcionalidade case en tempo real permítelle ver, en poucos segundos, as últimas interaccións que fixeron os seus clientes cos seus produtos ou servizos.</span><span class="sxs-lookup"><span data-stu-id="8baf0-104">The near real-time functionality lets you see, within seconds, the latest interactions that your customers have made with your products or services.</span></span>

<span data-ttu-id="8baf0-105">As [actualizacións programadas](system.md#schedule-tab) inclúen gran cantidade de rexistros e varias operacións complexas.</span><span class="sxs-lookup"><span data-stu-id="8baf0-105">[Scheduled refreshes](system.md#schedule-tab) include large numbers of records and several complex operations.</span></span> <span data-ttu-id="8baf0-106">En primeiro lugar, os datos son extraídos da orixe de datos.</span><span class="sxs-lookup"><span data-stu-id="8baf0-106">First, data is pulled from the data source.</span></span> <span data-ttu-id="8baf0-107">A continuación, os datos unifícanse e logo enriquécense con información adicional.</span><span class="sxs-lookup"><span data-stu-id="8baf0-107">Next, the data is unified, and then enriched with additional information.</span></span> <span data-ttu-id="8baf0-108">Cada execución deste proceso pode levar minutos ou horas.</span><span class="sxs-lookup"><span data-stu-id="8baf0-108">Every run of this process can take minutes to hours.</span></span>

<span data-ttu-id="8baf0-109">A funcionalidade en tempo real proporciona datos inmediatamente para o consumo, ata que a actualización programada posterior extrae estes datos da orixe de datos.</span><span class="sxs-lookup"><span data-stu-id="8baf0-109">The real-time functionality provides data immediately for consumption, until the subsequent scheduled refresh pulls this data from the data source.</span></span>

<span data-ttu-id="8baf0-110">As actualizacións en tempo real teñen unha hora de caducidade despois da cal xa non anularán o valor da orixe de datos:</span><span class="sxs-lookup"><span data-stu-id="8baf0-110">Real-time updates have an expiration time after which they no longer override the value from the data source:</span></span>

- <span data-ttu-id="8baf0-111">As actualizacións do perfil manteranse durante 4 horas</span><span class="sxs-lookup"><span data-stu-id="8baf0-111">Profile updates will be kept for 4 hours</span></span>
- <span data-ttu-id="8baf0-112">As actividades manteranse durante 30 días</span><span class="sxs-lookup"><span data-stu-id="8baf0-112">Activities will be kept for 30 days</span></span>

<span data-ttu-id="8baf0-113">Estes valores son parámetros de chamada de API que pode cambiar.</span><span class="sxs-lookup"><span data-stu-id="8baf0-113">These values are API call parameters that you can change.</span></span> <span data-ttu-id="8baf0-114">Pretenden garantir que os seus datos de orixes sexan a súa fonte de verdade.</span><span class="sxs-lookup"><span data-stu-id="8baf0-114">They aim to ensure that your source data remains your source of truth.</span></span> <span data-ttu-id="8baf0-115">Se quere que se inclúan actualizacións en tempo real durante máis tempo, debe engadilas a unha orixe de datos para que se poidan extraer durante a próxima actualización programada.</span><span class="sxs-lookup"><span data-stu-id="8baf0-115">If you want real-time updates to be included for longer, you need to add them to a data source so they get pulled during the next scheduled refresh.</span></span>

## <a name="real-time-update-of-the-unified-customer-profile-fields"></a><span data-ttu-id="8baf0-116">Actualización en tempo real dos campos de perfil de cliente unificados</span><span class="sxs-lookup"><span data-stu-id="8baf0-116">Real-time update of the unified customer profile fields</span></span>

<span data-ttu-id="8baf0-117">Os perfís actualizados amosaranse na vista da tarxeta de cliente ou en calquera outra visualización nuns segundos.</span><span class="sxs-lookup"><span data-stu-id="8baf0-117">Updated profiles will show in the customer card view, or any other visualization, within a few seconds.</span></span>

<span data-ttu-id="8baf0-118">Debido a que as operacións en tempo real teñen lugar despois da unificación de datos, só se aplican aos perfís de clientes unificados.</span><span class="sxs-lookup"><span data-stu-id="8baf0-118">Because real-time operations take place after the data unification has happened, they only apply to the unified customer profiles.</span></span> <span data-ttu-id="8baf0-119">Por este motivo, os cambios de perfil en tempo real non actualizarán medidas, subscricións de segmento nin enriquecementos.</span><span class="sxs-lookup"><span data-stu-id="8baf0-119">Consequently, real-time profile changes will not update measures, segment membership, or enrichments.</span></span>

### <a name="limitations"></a><span data-ttu-id="8baf0-120">Limitacións</span><span class="sxs-lookup"><span data-stu-id="8baf0-120">Limitations</span></span>

- <span data-ttu-id="8baf0-121">Os perfís de clientes pódense actualizar, pero non se poden crear ou eliminar.</span><span class="sxs-lookup"><span data-stu-id="8baf0-121">Customer profiles can be updated, but not created or deleted.</span></span>
- <span data-ttu-id="8baf0-122">Non é posible exportar polo momento actualizacións en tempo real a sistemas externos, como Power BI.</span><span class="sxs-lookup"><span data-stu-id="8baf0-122">Exporting real-time updates to external systems, like Power BI, is not possible at the moment.</span></span>

## <a name="real-time-creation-of-activities"></a><span data-ttu-id="8baf0-123">Creación de actividades en tempo real</span><span class="sxs-lookup"><span data-stu-id="8baf0-123">Real-time creation of activities</span></span>

<span data-ttu-id="8baf0-124">A API en tempo real permítelle publicar unha nova actividade do seu sistema de orixe (un rexistro de orixe individual) nun perfil de cliente unificado.</span><span class="sxs-lookup"><span data-stu-id="8baf0-124">The real-time API lets you publish a new activity from your source system (an individual source record) to a unified customer profile.</span></span> <span data-ttu-id="8baf0-125">A nova actividade estará dispoñible como actividade unificada na liña de tempo do perfil de cliente unificado en cuestión de segundos.</span><span class="sxs-lookup"><span data-stu-id="8baf0-125">The new activity will be available as a unified activity in that unified customer profile's timeline within seconds.</span></span> <span data-ttu-id="8baf0-126">Pode ver a liña de tempo na vista da tarxeta de cliente ou calquera outra integración de liña de tempo que configurase.</span><span class="sxs-lookup"><span data-stu-id="8baf0-126">You can see the timeline in the customer card view or any other timeline integration you configured.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="8baf0-127">As actividades non se poden cambiar.</span><span class="sxs-lookup"><span data-stu-id="8baf0-127">Activities are immutable.</span></span> <span data-ttu-id="8baf0-128">Non cambiarán unha vez creadas.</span><span class="sxs-lookup"><span data-stu-id="8baf0-128">They don't change once created.</span></span>
> - <span data-ttu-id="8baf0-129">Actualmente, os segmentos e as medidas non se actualizarán en función da nova actividade.</span><span class="sxs-lookup"><span data-stu-id="8baf0-129">Currently, segments and measures won't update based on the new activity.</span></span>
> - <span data-ttu-id="8baf0-130">As actividades engadidas só a través da API en tempo real non forman parte das exportacións e non aparecerán en PowerBI.</span><span class="sxs-lookup"><span data-stu-id="8baf0-130">Activities added only through the real-time API are not part of exports and won't show up in PowerBI.</span></span>

<span data-ttu-id="8baf0-131">Hai dúas formas de conectarse á API en tempo real:</span><span class="sxs-lookup"><span data-stu-id="8baf0-131">There are two ways to connect to the real-time API:</span></span>

- <span data-ttu-id="8baf0-132">[indirectamente](#connect-via-the-dynamics-365-customer-insights-connector), usando o [conector Dynamics 365 Customer Insights](/connectors/customerinsights/)</span><span class="sxs-lookup"><span data-stu-id="8baf0-132">[indirectly](#connect-via-the-dynamics-365-customer-insights-connector), using the [Dynamics 365 Customer Insights connector](/connectors/customerinsights/)</span></span>
- <span data-ttu-id="8baf0-133">[directamente](#connect-directly-to-the-real-time-api), co código</span><span class="sxs-lookup"><span data-stu-id="8baf0-133">[directly](#connect-directly-to-the-real-time-api), with code</span></span>

<span data-ttu-id="8baf0-134">Ámbolos dous xeitos comparten os seguintes requisitos previos:</span><span class="sxs-lookup"><span data-stu-id="8baf0-134">Both ways share the following prerequisites:</span></span>

- <span data-ttu-id="8baf0-135">Un ambiente de Customer Insights</span><span class="sxs-lookup"><span data-stu-id="8baf0-135">A Customer Insights environment</span></span>
- <span data-ttu-id="8baf0-136">Perfís de cliente unificados</span><span class="sxs-lookup"><span data-stu-id="8baf0-136">Unified customer profiles</span></span>
- <span data-ttu-id="8baf0-137">Actividades configuradas e executadas</span><span class="sxs-lookup"><span data-stu-id="8baf0-137">Activities configured and run</span></span>
- <span data-ttu-id="8baf0-138">Permisos de colaborador ou administrador para autenticar a súa conta</span><span class="sxs-lookup"><span data-stu-id="8baf0-138">Contributor or Administrator permissions to authenticate your account</span></span>

## <a name="connect-via-the-dynamics-365-customer-insights-connector"></a><span data-ttu-id="8baf0-139">Conectarse a través do conector de Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="8baf0-139">Connect via the Dynamics 365 Customer Insights connector</span></span>

<span data-ttu-id="8baf0-140">A API en tempo real pode inxerir datos dun conector Power Platform específico, o [conector de Dynamics 365 Customer Insights](/connectors/customerinsights/), sen necesidade de escribir e despregar ningún código.</span><span class="sxs-lookup"><span data-stu-id="8baf0-140">The real-time API can ingest data from a dedicated Power Platform connector, the [Dynamics 365 Customer Insights connector](/connectors/customerinsights/), without the need to write and deploy any code.</span></span>    
<span data-ttu-id="8baf0-141">O conector pode facer as mesmas accións en tempo real que a API.</span><span class="sxs-lookup"><span data-stu-id="8baf0-141">The connector can do the same real-time actions as the API.</span></span> <span data-ttu-id="8baf0-142">Necesita unha licenza válida para os conectores premium.</span><span class="sxs-lookup"><span data-stu-id="8baf0-142">You need a valid license for premium connectors.</span></span> <span data-ttu-id="8baf0-143">Para obter máis información, consulte [Preguntas máis frecuentes acerca de licenzas de Power Apps e Power Automate](/power-platform/admin/powerapps-flow-licensing-faq).</span><span class="sxs-lookup"><span data-stu-id="8baf0-143">For more information, see [Power Apps and Power Automate licensing FAQs](/power-platform/admin/powerapps-flow-licensing-faq).</span></span>

- <span data-ttu-id="8baf0-144">Power Platform [Power Apps e/ou Power Automate](/connectors/)</span><span class="sxs-lookup"><span data-stu-id="8baf0-144">Power Platform [Power Apps and/or Power Automate](/connectors/)</span></span>
- <span data-ttu-id="8baf0-145">Azure [Logic Apps](/azure/connectors/apis-list)</span><span class="sxs-lookup"><span data-stu-id="8baf0-145">Azure [Logic Apps](/azure/connectors/apis-list)</span></span>

<span data-ttu-id="8baf0-146">Para obter máis detalles sobre a creación de fluxos, consulte a [documentación de Power Automate](/power-automate/).</span><span class="sxs-lookup"><span data-stu-id="8baf0-146">For details about creating flows, see the [Power Automate documentation](/power-automate/).</span></span>

## <a name="connect-directly-to-the-real-time-api"></a><span data-ttu-id="8baf0-147">Conectar directamente á API en tempo real</span><span class="sxs-lookup"><span data-stu-id="8baf0-147">Connect directly to the real-time API</span></span>

<span data-ttu-id="8baf0-148">Pode usar as capacidades en tempo real creando a súa propia canle e conectándose directamente á API en tempo real.</span><span class="sxs-lookup"><span data-stu-id="8baf0-148">You can use the real-time capabilities by building your own pipeline and connecting directly to the real-time API.</span></span>    
<span data-ttu-id="8baf0-149">Pode publicar unha actividade no formato do sistema de orixe ou no formato UnifiedActivity.</span><span class="sxs-lookup"><span data-stu-id="8baf0-149">You can post an activity in the format of your source system or in the UnifiedActivity format.</span></span> <span data-ttu-id="8baf0-150">Obteña o formato facendo unha chamada a unha API a /api/instances/{instanceId}/manage/entities/UnifiedActivity.</span><span class="sxs-lookup"><span data-stu-id="8baf0-150">Get the format by making an API call to /api/instances/{instanceId}/manage/entities/UnifiedActivity.</span></span>

<span data-ttu-id="8baf0-151">Os detalles desta API, incluídos parámetros e respostas, pódense atopar na sección **EntityData** sobre a [Referencia das API de Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span><span class="sxs-lookup"><span data-stu-id="8baf0-151">Details of this API, including parameters and responses, can be found in the **EntityData** section on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="8baf0-152">Para obter máis información, consulte [Traballar coas API de Customer Insights](apis.md).</span><span class="sxs-lookup"><span data-stu-id="8baf0-152">For more information, see [Work with Customer Insights APIs](apis.md).</span></span>

## <a name="understand-your-real-time-usage-with-telemetry"></a><span data-ttu-id="8baf0-153">Comprender o seu uso en tempo real coa telemetría</span><span class="sxs-lookup"><span data-stu-id="8baf0-153">Understand your real-time usage with telemetry</span></span>

<span data-ttu-id="8baf0-154">Obteña unha visión xeral do volume de solicitudes á API en tempo real e información sobre problemas que pode atopar o sistema.</span><span class="sxs-lookup"><span data-stu-id="8baf0-154">Get an overview of the volume of requests to the real-time API and information about issues the system may encounter.</span></span> <span data-ttu-id="8baf0-155">Pode [acceder á telemetría en tempo real](system.md#api-usage-tab).</span><span class="sxs-lookup"><span data-stu-id="8baf0-155">You can [access the real-time telemetry](system.md#api-usage-tab).</span></span> 


[!INCLUDE[footer-include](../includes/footer-banner.md)]