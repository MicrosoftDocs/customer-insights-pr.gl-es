---
title: Traballar con API
description: Use as API e comprenda as limitacións.
ms.date: 05/10/2021
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 9326f821f9970ba2254ab804814e369abb677eb0
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304740"
---
# <a name="work-with-customer-insights-apis"></a><span data-ttu-id="34c03-103">Traballar coas API de Customer Insights</span><span class="sxs-lookup"><span data-stu-id="34c03-103">Work with Customer Insights APIs</span></span>

<span data-ttu-id="34c03-104">Dynamics 365 Customer Insights ofrece as API para crear as súas propias aplicacións baseadas nos seus datos en Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="34c03-104">Dynamics 365 Customer Insights provides APIs to build your own applications based on your data in Customer Insights.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="34c03-105">Os detalles destas API enuméranse na [referencia das API de Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span><span class="sxs-lookup"><span data-stu-id="34c03-105">Details of these APIs are listed on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="34c03-106">Inclúen información adicional sobre operacións, parámetros e respostas.</span><span class="sxs-lookup"><span data-stu-id="34c03-106">They include additional information about operations, parameters, and responses.</span></span>

<span data-ttu-id="34c03-107">Este artigo describe como acceder ás API de Customer Insights, crear un rexistro de aplicacións de Azure e comezar a usar as bibliotecas de clientes dispoñibles.</span><span class="sxs-lookup"><span data-stu-id="34c03-107">This article describes how to access the Customer Insights APIs, create an Azure App Registration, and get started with the available client libraries.</span></span>

## <a name="get-started-trying-the-customer-insights-apis"></a><span data-ttu-id="34c03-108">Comezar a probar as API de Customer Insights</span><span class="sxs-lookup"><span data-stu-id="34c03-108">Get started trying the Customer Insights APIs</span></span>

1. <span data-ttu-id="34c03-109">[Inicie sesión](https://home.ci.ai.dynamics.com) en Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="34c03-109">[Sign in](https://home.ci.ai.dynamics.com) to Customer Insights.</span></span> <span data-ttu-id="34c03-110">Se aínda non ten unha subscrición, [Rexístrese para obter unha versión de proba de Customer Insights](https://aka.ms/tryci).</span><span class="sxs-lookup"><span data-stu-id="34c03-110">If you don't have a subscription yet, [sign up for a trial of Customer Insights](https://aka.ms/tryci).</span></span>

1. <span data-ttu-id="34c03-111">Para habilitar as API no seu contorno de Customer Insights, vaia a **Administrar** > **Permisos**.</span><span class="sxs-lookup"><span data-stu-id="34c03-111">To enable APIs on your Customer Insights environment, go to **Admin** > **Permissions**.</span></span> <span data-ttu-id="34c03-112">Necesitará permisos de administrador para facelo.</span><span class="sxs-lookup"><span data-stu-id="34c03-112">You'll need admin permissions to do so.</span></span>

1. <span data-ttu-id="34c03-113">Vaia ao separador **API** e seleccione o botón **Activar**.</span><span class="sxs-lookup"><span data-stu-id="34c03-113">Go to the **APIs** tab and select the **Enable** button.</span></span>    
 
   <span data-ttu-id="34c03-114">Habilitar as API crea unha clave de subscrición principal e secundaria para a súa instancia que se usa nas solicitudes de API.</span><span class="sxs-lookup"><span data-stu-id="34c03-114">Enabling the APIs creates a primary and secondary subscription key for your instance that gets used in the API requests.</span></span> <span data-ttu-id="34c03-115">Pode volver xerar as teclas seleccionando **Volver xerar primaria** ou **Volver xerar secundaria** en **Administrar** > **Permisos** > **API**.</span><span class="sxs-lookup"><span data-stu-id="34c03-115">You can regenerate the keys by selecting the **Regenerate primary** or **Regenerate secondary** on **Admin** > **Permissions** > **APIs**.</span></span>

   :::image type="content" source="media/enable-apis.gif" alt-text="Activar API de Customer Insights":::

1. <span data-ttu-id="34c03-117">Seleccione **Explorar as nosas API** para [probar as API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).</span><span class="sxs-lookup"><span data-stu-id="34c03-117">Select **Explore our APIs** to [try out the APIs](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).</span></span>

1. <span data-ttu-id="34c03-118">Escolla unha operación de API e seleccione **Probala**.</span><span class="sxs-lookup"><span data-stu-id="34c03-118">Choose an API operation and select **Try it**.</span></span>

1. <span data-ttu-id="34c03-119">No panel lateral, configure o valor no menú despregable **Autorización** a **implícita**.</span><span class="sxs-lookup"><span data-stu-id="34c03-119">In the side pane, set the value in the **Authorization** dropdown menu to **implicit**.</span></span> <span data-ttu-id="34c03-120">A cabeceira `Authorization` engádese cun token de portador.</span><span class="sxs-lookup"><span data-stu-id="34c03-120">The `Authorization` header gets added with a bearer token.</span></span> <span data-ttu-id="34c03-121">A súa clave de subscrición encherase automaticamente.</span><span class="sxs-lookup"><span data-stu-id="34c03-121">Your subscription key will be automatically populated.</span></span>
  
1. <span data-ttu-id="34c03-122">Opcionalmente, engada todos os parámetros de consulta necesarios.</span><span class="sxs-lookup"><span data-stu-id="34c03-122">Optionally, add all necessary query parameters.</span></span>

1. <span data-ttu-id="34c03-123">Desprácese ata a parte inferior do panel lateral e seleccione **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="34c03-123">Scroll to the bottom of the side pane and select **Send**.</span></span>

<span data-ttu-id="34c03-124">A resposta HTTP aparecerá en breve a continuación.</span><span class="sxs-lookup"><span data-stu-id="34c03-124">The HTTP response will soon appear below.</span></span>

   :::image type="content" source="media/try-apis.gif" alt-text="Como probar as API.":::

## <a name="create-a-new-app-registration-in-the-azure-portal"></a><span data-ttu-id="34c03-126">Crear un novo rexistro de aplicacións no portal de Azure</span><span class="sxs-lookup"><span data-stu-id="34c03-126">Create a new app registration in the Azure portal</span></span>

<span data-ttu-id="34c03-127">Estes pasos axúdanlle a comezar a usar as API de Customer Insights nunha aplicación de Azure mediante permisos delegados.</span><span class="sxs-lookup"><span data-stu-id="34c03-127">These steps help you get started with using the Customer Insights APIs in an Azure application using delegated permissions.</span></span> <span data-ttu-id="34c03-128">Asegúrese de completar a [Sección de inicio](#get-started-trying-the-customer-insights-apis) primeiro.</span><span class="sxs-lookup"><span data-stu-id="34c03-128">Make sure to complete the [Getting started section](#get-started-trying-the-customer-insights-apis) first.</span></span>

1. <span data-ttu-id="34c03-129">Inicie sesión no [Portal de Azure](https://portal.azure.com) coa conta que pode acceder aos datos de Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="34c03-129">Sign in to the [Azure portal](https://portal.azure.com) with the account that can access the Customer Insights data.</span></span>

1. <span data-ttu-id="34c03-130">Á esquerda, seleccione **Rexistros de aplicacións**.</span><span class="sxs-lookup"><span data-stu-id="34c03-130">On the left, select **App registrations**.</span></span>

1. <span data-ttu-id="34c03-131">Seleccione **Novo rexistro**, forneza un nome de aplicación e elixa o tipo de conta.</span><span class="sxs-lookup"><span data-stu-id="34c03-131">Select **New registration**, provide an application name and choose the account type.</span></span>
 
   <span data-ttu-id="34c03-132">Opcionalmente, engada un URL de redireccionamento.</span><span class="sxs-lookup"><span data-stu-id="34c03-132">Optionally, add a redirect URL.</span></span> <span data-ttu-id="34c03-133">http://localhost é suficiente para desenvolver unha aplicación no seu computador local.</span><span class="sxs-lookup"><span data-stu-id="34c03-133">http://localhost is sufficient for developing an application on your local computer.</span></span>

1. <span data-ttu-id="34c03-134">No novo rexistro da aplicación, vaia a **Permisos de API**.</span><span class="sxs-lookup"><span data-stu-id="34c03-134">On your new App registration, go to **API permissions**.</span></span>

   :::image type="content" source="media/app-registration-1.gif" alt-text="Como configurar os permisos da API no rexistro da aplicación.":::

1. <span data-ttu-id="34c03-136">Seleccione **Engadir un permiso** e seleccione **Customer Insights** no panel lateral.</span><span class="sxs-lookup"><span data-stu-id="34c03-136">Select **Add a permission** and select **Customer Insights** in the side pane.</span></span>

1. <span data-ttu-id="34c03-137">Para **Tipo de permiso**, seleccione **Permisos delegados** e logo seleccione o permiso **user_impersonation**.</span><span class="sxs-lookup"><span data-stu-id="34c03-137">For **Permission type**, select **Delegated permissions** and then select the **user_impersonation** permission.</span></span>

1. <span data-ttu-id="34c03-138">Seleccione **Engadir permisos**.</span><span class="sxs-lookup"><span data-stu-id="34c03-138">Select **Add permissions**.</span></span> <span data-ttu-id="34c03-139">Se precisa acceder á API sen que un usuario inicie sesión, revise a sección [Permisos de aplicacións de servidor a servidor](#server-to-server-application-permissions).</span><span class="sxs-lookup"><span data-stu-id="34c03-139">If you need to access the API without a user signing in, review the [Server-to-server application permissions](#server-to-server-application-permissions) section.</span></span>

1. <span data-ttu-id="34c03-140">Seleccione **Outorgar o consentimento do administrador para...** para completar o rexistro da aplicación.</span><span class="sxs-lookup"><span data-stu-id="34c03-140">Select **Grant admin consent for...** to complete the app registration.</span></span>

<span data-ttu-id="34c03-141">Pode usar o ID de aplicación/cliente para este rexistro de aplicación coa Biblioteca de autenticación de Microsoft (MSAL) para obter un token de portador para enviar coa súa solicitude á API.</span><span class="sxs-lookup"><span data-stu-id="34c03-141">You can use the Application/Client ID for this app registration with the Microsoft Authentication Library (MSAL) to obtain a bearer token to send with your request to the API.</span></span>

:::image type="content" source="media/grant-admin-consent.gif" alt-text="Como conceder o consentimento do administrador.":::

<span data-ttu-id="34c03-143">Para obter máis información sobre a MSAL, consulte [Vista xeral da biblioteca de autenticación de Microsoft (MSAL)](/azure/active-directory/develop/msal-overview).</span><span class="sxs-lookup"><span data-stu-id="34c03-143">For more information about MSAL, see [Overview of Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview).</span></span>

<span data-ttu-id="34c03-144">Para obter máis información sobre o rexistro de aplicacións en Azure, consulte [Rexistrar unha aplicación](/azure/active-directory/develop/quickstart-register-app.md#register-an-application).</span><span class="sxs-lookup"><span data-stu-id="34c03-144">For more information about app registration in Azure, see [Register an application](/azure/active-directory/develop/quickstart-register-app.md#register-an-application).</span></span>

<span data-ttu-id="34c03-145">Para obter información sobre o uso das API nas nosas bibliotecas de clientes, consulte [Bibliotecas clientes de Customer Insights](#customer-insights-client-libraries).</span><span class="sxs-lookup"><span data-stu-id="34c03-145">For information on using the APIs in our client libraries, see [Customer Insights client libraries](#customer-insights-client-libraries).</span></span>

### <a name="server-to-server-application-permissions"></a><span data-ttu-id="34c03-146">Permisos de aplicacións de servidor a servidor</span><span class="sxs-lookup"><span data-stu-id="34c03-146">Server-to-server application permissions</span></span>

<span data-ttu-id="34c03-147">A [sección de rexistro de aplicacións](#create-a-new-app-registration-in-the-azure-portal) describe como rexistrar unha aplicación que require que un usuario inicie sesión para autenticarse.</span><span class="sxs-lookup"><span data-stu-id="34c03-147">The [app registration section](#create-a-new-app-registration-in-the-azure-portal) outlines how to register an app that requires a user to sign in for authentication.</span></span> <span data-ttu-id="34c03-148">Aprenda a crear un rexistro de aplicacións que non precisa a interacción do usuario e que se pode executar nun servidor.</span><span class="sxs-lookup"><span data-stu-id="34c03-148">Learn how to create an app registration that does not need user interaction and can be run on a server.</span></span>

1. <span data-ttu-id="34c03-149">No rexistro da súa aplicación no portal de Azure, vaia a **Permisos de API**.</span><span class="sxs-lookup"><span data-stu-id="34c03-149">On your App registration in the Azure portal, go to **API permissions**.</span></span>

1. <span data-ttu-id="34c03-150">Seleccione **Engadir un permiso**.</span><span class="sxs-lookup"><span data-stu-id="34c03-150">Select **Add a permission**.</span></span> 

1. <span data-ttu-id="34c03-151">Seleccione o separador **API que usa a miña organización** e escolla **Dynamics 365 AI for Customer Insights** da lista.</span><span class="sxs-lookup"><span data-stu-id="34c03-151">Select the **APIs my organization uses** tab and choose **Dynamics 365 AI for Customer Insights** from the list.</span></span> 

1. <span data-ttu-id="34c03-152">Para **Tipo de permiso**, seleccione **Permisos de aplicación** e logo seleccione o permiso **CustomerInsights.Api.All**.</span><span class="sxs-lookup"><span data-stu-id="34c03-152">For **Permission type**, select **Application permissions** and then select the **CustomerInsights.Api.All** permission.</span></span>

1. <span data-ttu-id="34c03-153">Seleccione **Engadir permisos**.</span><span class="sxs-lookup"><span data-stu-id="34c03-153">Select **Add permissions**.</span></span>

1. <span data-ttu-id="34c03-154">Volva a **Permisos de API** para rexistrar a aplicación.</span><span class="sxs-lookup"><span data-stu-id="34c03-154">Go back to **API permissions** for your app registration.</span></span>

1. <span data-ttu-id="34c03-155">Seleccione **Outorgar o consentimento do administrador para...** para completar o rexistro da aplicación.</span><span class="sxs-lookup"><span data-stu-id="34c03-155">Select **Grant admin consent for...** to complete the app registration.</span></span>

   :::image type="content" source="media/grant-admin-consent.gif" alt-text="Como conceder o consentimento do administrador.":::

1. <span data-ttu-id="34c03-157">Para finalizar, temos que engadir o nome do rexistro da aplicación como usuario en Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="34c03-157">To conclude, we have to add the name of the app registration as a user in Customer Insights.</span></span>  
   
   <span data-ttu-id="34c03-158">Abra Customer Insights, vaia a **Administrar** > **Permisos** e seleccione **Engadir usuario**.</span><span class="sxs-lookup"><span data-stu-id="34c03-158">Open Customer Insights, go to **Admin** > **Permissions** and select **Add user**.</span></span>

1. <span data-ttu-id="34c03-159">Busque o nome do rexistro da súa aplicación, seleccióneo entre os resultados da busca e seleccione **Gardar**.</span><span class="sxs-lookup"><span data-stu-id="34c03-159">Search for the name of your app registration, select it from the search results, and select **Save**.</span></span>

## <a name="customer-insights-client-libraries"></a><span data-ttu-id="34c03-160">Bibliotecas de clientes de Customer Insights</span><span class="sxs-lookup"><span data-stu-id="34c03-160">Customer Insights client libraries</span></span>

<span data-ttu-id="34c03-161">Esta sección axuda a comezar a usar as bibliotecas de clientes dispoñibles para as API de Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="34c03-161">This section helps you get started using the client libraries available for the Customer Insights APIs.</span></span> <span data-ttu-id="34c03-162">Todos os códigos fonte da biblioteca e as aplicacións de mostra pódense atopar na [Páxina de GitHub de Customer Insights](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries).</span><span class="sxs-lookup"><span data-stu-id="34c03-162">All library source code and sample applications can be found on the [Customer Insights GitHub page](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries).</span></span> 

### <a name="c-nuget"></a><span data-ttu-id="34c03-163">C# NuGet</span><span class="sxs-lookup"><span data-stu-id="34c03-163">C# NuGet</span></span>

<span data-ttu-id="34c03-164">Aprenda a comezar a usar as bibliotecas de clientes de C # desde NuGet.org. Para obter máis información sobre o paquete NuGet, vexa [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span><span class="sxs-lookup"><span data-stu-id="34c03-164">Learn how to get started using the C# client libraries from NuGet.org. For more information on the NuGet package, see [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span></span> <span data-ttu-id="34c03-165">Actualmente, este paquete ten como obxectivo os frameworks netstandard2.0 e netcoreapp2.0.</span><span class="sxs-lookup"><span data-stu-id="34c03-165">Currently, this package targets the netstandard2.0 and netcoreapp2.0 frameworks.</span></span>

#### <a name="add-the-c-client-library-to-a-c-project"></a><span data-ttu-id="34c03-166">Engadir a biblioteca de clientes de C# a un proxecto de C#</span><span class="sxs-lookup"><span data-stu-id="34c03-166">Add the C# client library to a C# project</span></span>

1. <span data-ttu-id="34c03-167">En Visual Studio, abra o **Xestor de paquetes de NuGet** para o seu proxecto.</span><span class="sxs-lookup"><span data-stu-id="34c03-167">In Visual Studio, open the **NuGet Package Manager** for your project.</span></span>

1. <span data-ttu-id="34c03-168">Buscar **Microsoft.Dynamics.CustomerInsights.Api**.</span><span class="sxs-lookup"><span data-stu-id="34c03-168">Search for **Microsoft.Dynamics.CustomerInsights.Api**.</span></span>

1. <span data-ttu-id="34c03-169">Seleccione **Instalar** para engadir o paquete ao proxecto.</span><span class="sxs-lookup"><span data-stu-id="34c03-169">Select **Install** to add the package to the project.</span></span>
 
   <span data-ttu-id="34c03-170">Como alternativa, execute este comando na **Consola do xestor de paquetes de NuGet**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span><span class="sxs-lookup"><span data-stu-id="34c03-170">Alternatively, run this command in the **NuGet Package Manager Console**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span></span>

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Engadir paquete de NuGet a un proxecto de Visual Studio":::

#### <a name="use-the-c-client-library"></a><span data-ttu-id="34c03-172">Usar a biblioteca de clientes de C#</span><span class="sxs-lookup"><span data-stu-id="34c03-172">Use the C# client library</span></span>

1. <span data-ttu-id="34c03-173">Use a [Biblioteca de autenticación de Microsoft (MSAL)](/azure/active-directory/develop/msal-overview) para obter un `AccessToken` usando o seu [Rexistro de aplicacións de Azure](#create-a-new-app-registration-in-the-azure-portal) existente.</span><span class="sxs-lookup"><span data-stu-id="34c03-173">Use the [Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview) to get an `AccessToken` using your existing [Azure app registration](#create-a-new-app-registration-in-the-azure-portal).</span></span>

1. <span data-ttu-id="34c03-174">Despois de autenticar e adquirir con éxito un token, constrúa un `HttpClient` novo ou use un xa existente coa **"Autorización" de DefaultRequestHeaders** adicional definida en **<access token> de portador** e **Ocp-Apim-Subscription-Key** definida como [**clave de subscrición** do seu contorno de Customer Insights](#get-started-trying-the-customer-insights-apis).</span><span class="sxs-lookup"><span data-stu-id="34c03-174">After successfully authenticating and acquiring a token, construct a new or use an existing `HttpClient` with the additional **DefaultRequestHeaders "Authorization"** set to **Bearer <access token>** and **Ocp-Apim-Subscription-Key** set to the [**subscription key** from your Customer Insights environment](#get-started-trying-the-customer-insights-apis).</span></span>   
 
   <span data-ttu-id="34c03-175">Restableza a cabeceira da **Autorización** cando corresponda.</span><span class="sxs-lookup"><span data-stu-id="34c03-175">Reset the **Authorization** header when appropriate.</span></span> <span data-ttu-id="34c03-176">Por exemplo, cando o token caducou.</span><span class="sxs-lookup"><span data-stu-id="34c03-176">For example, when the token expired.</span></span>

1. <span data-ttu-id="34c03-177">Pase este `HttpClient` na construción do cliente de `CustomerInsights`.</span><span class="sxs-lookup"><span data-stu-id="34c03-177">Pass this `HttpClient` into the construction of the `CustomerInsights` client.</span></span>

   :::image type="content" source="media/httpclient-sample.png" alt-text="Mostra de httpclient":::

1. <span data-ttu-id="34c03-179">Faga chamadas co cliente aos "métodos de extensión", por exemplo, `GetAllInstancesAsync`.</span><span class="sxs-lookup"><span data-stu-id="34c03-179">Make calls with the client to the "extension methods"—for example, `GetAllInstancesAsync`.</span></span> <span data-ttu-id="34c03-180">Se o acceso á `Microsoft.Rest.HttpOperationResponse` subxacente é preferible, use os "métodos de mensaxes http", por exemplo `GetAllInstancesWithHttpMessagesAsync`.</span><span class="sxs-lookup"><span data-stu-id="34c03-180">If access to the underlying `Microsoft.Rest.HttpOperationResponse` is preferred, use the "http message methods"—for example, `GetAllInstancesWithHttpMessagesAsync`.</span></span>

1. <span data-ttu-id="34c03-181">É probable que a resposta sexa de tipo `object` porque o método pode devolver varios tipos (por exemplo, `IList<InstanceInfo>` e `ApiErrorResult`).</span><span class="sxs-lookup"><span data-stu-id="34c03-181">The response will likely be of type `object` because the method can return multiple types (for example, `IList<InstanceInfo>` and `ApiErrorResult`).</span></span> <span data-ttu-id="34c03-182">Para comprobar o tipo de devolución, pode lanzar os obxectos con seguridade nos tipos de resposta especificados na [Páxina de detalles da API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) para esa operación.</span><span class="sxs-lookup"><span data-stu-id="34c03-182">To check the return type, you can safely cast the objects into the response types specified on the [API details page](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) for that operation.</span></span>    
   
   <span data-ttu-id="34c03-183">Se precisa máis información sobre a solicitude, use os **Métodos de mensaxes http** para acceder ao obxecto de resposta orixinal.</span><span class="sxs-lookup"><span data-stu-id="34c03-183">If more information on the request is needed, use the **http message methods** to access the raw response object.</span></span>

### <a name="nodejs-package"></a><span data-ttu-id="34c03-184">Paquete NodeJS</span><span class="sxs-lookup"><span data-stu-id="34c03-184">NodeJS package</span></span>

<span data-ttu-id="34c03-185">Use as bibliotecas cliente de NodeJS dispoñibles a través de NPM: https://www.npmjs.com/package/@microsoft/customerinsights</span><span class="sxs-lookup"><span data-stu-id="34c03-185">Use the NodeJS client libraries available through NPM: https://www.npmjs.com/package/@microsoft/customerinsights</span></span>

### <a name="python-package"></a><span data-ttu-id="34c03-186">Paquete Python</span><span class="sxs-lookup"><span data-stu-id="34c03-186">Python package</span></span>

<span data-ttu-id="34c03-187">Use as bibliotecas cliente de Python dispoñibles a través de PyPi: https://pypi.org/project/customerinsights/</span><span class="sxs-lookup"><span data-stu-id="34c03-187">Use the Python client libraries available through PyPi: https://pypi.org/project/customerinsights/</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
