---
title: Traballar con API
description: Use as API e comprenda as limitacións.
ms.date: 12/04/2020
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 5a03e916676800afdd8692da865a1060952d5c4f
ms.sourcegitcommit: b50c754481d0af6d0cf4b550775d7b31d95846ef
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 12/06/2020
ms.locfileid: "4689128"
---
# <a name="work-with-customer-insights-apis"></a><span data-ttu-id="3aef1-103">Traballar coas API de Customer Insights</span><span class="sxs-lookup"><span data-stu-id="3aef1-103">Work with Customer Insights APIs</span></span>

<span data-ttu-id="3aef1-104">Dynamics 365 Customer Insights ofrece API para crear as súas propias aplicacións baseadas nos seus datos en Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="3aef1-104">Dynamics 365 Customer Insights provides APIs to build your own applications based you data in Customer Insights.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3aef1-105">Os detalles destas API enuméranse na [referencia das API de Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span><span class="sxs-lookup"><span data-stu-id="3aef1-105">Details of these APIs, are listed on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="3aef1-106">Inclúen información adicional sobre operacións, parámetros e respostas.</span><span class="sxs-lookup"><span data-stu-id="3aef1-106">They include additional information about operations, parameters, and responses.</span></span>

<span data-ttu-id="3aef1-107">Este artigo guíao para acceder ás API de Customer Insights, crear un rexistro de aplicacións de Azure e axudarlle a comezar coas bibliotecas de clientes dispoñibles.</span><span class="sxs-lookup"><span data-stu-id="3aef1-107">This article guides you to access to the Customer Insights APIs, create an Azure App Registration, and help you get started with the available client libraries.</span></span>

## <a name="get-started-trying-the-customer-insights-apis"></a><span data-ttu-id="3aef1-108">Comezar a probar as API de Customer Insights</span><span class="sxs-lookup"><span data-stu-id="3aef1-108">Get started trying the Customer Insights APIs</span></span>

1. <span data-ttu-id="3aef1-109">[Inicie sesión](https://home.ci.ai.dynamics.com) en Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="3aef1-109">[Sign in](https://home.ci.ai.dynamics.com) to Customer Insights.</span></span> <span data-ttu-id="3aef1-110">Se aínda non ten unha subscrición, [Rexístrese para obter unha versión de proba de Customer Insights](https://aka.ms/tryci).</span><span class="sxs-lookup"><span data-stu-id="3aef1-110">If you don't have a subscription yet, [sign up for a trial of Customer Insights](https://aka.ms/tryci).</span></span>

1. <span data-ttu-id="3aef1-111">Para habilitar as API no seu contorno de Customer Insights, vaia a **Administrar** > **Permisos**.</span><span class="sxs-lookup"><span data-stu-id="3aef1-111">To enable APIs on your Customer Insights environment, go to **Admin** > **Permissions**.</span></span> <span data-ttu-id="3aef1-112">Necesitará permisos de administrador para facelo.</span><span class="sxs-lookup"><span data-stu-id="3aef1-112">You'll need admin permissions to do so.</span></span>

1. <span data-ttu-id="3aef1-113">Vaia ao separador **API** e seleccione o botón **Activar**.</span><span class="sxs-lookup"><span data-stu-id="3aef1-113">Go to the **APIs** tab and select the **Enable** button.</span></span>    
   <span data-ttu-id="3aef1-114">Habilitar as API crea unha clave de subscrición principal e secundaria para a súa instancia que se usa nas solicitudes de API.</span><span class="sxs-lookup"><span data-stu-id="3aef1-114">Enabling the APIs creates a primary and secondary subscription key for your instance that gets used in the API requests.</span></span> <span data-ttu-id="3aef1-115">Pode volver xerar as teclas seleccionando **Volver xerar primaria** ou **Volver xerar secundaria** en **Administrar** > **Permisos** > **API**.</span><span class="sxs-lookup"><span data-stu-id="3aef1-115">You can regenerate the keys by selecting the **Regenerate primary** or **Regenerate secondary** on **Admin** > **Permissions** > **APIs**.</span></span>

   :::image type="content" source="media/enable-apis.gif" alt-text="Activar API de Customer Insights":::

1. <span data-ttu-id="3aef1-117">Seleccione **Explorar as nosas API** para probar as API.</span><span class="sxs-lookup"><span data-stu-id="3aef1-117">Select **Explore our APIs** to try out the APIs.</span></span>

1. <span data-ttu-id="3aef1-118">Escolla unha operación de API e seleccione **Probala**.</span><span class="sxs-lookup"><span data-stu-id="3aef1-118">Choose an API operation and select **Try it**.</span></span>

1. <span data-ttu-id="3aef1-119">No panel lateral, configure o valor do menú despregable **Autorización** en **implícito**.</span><span class="sxs-lookup"><span data-stu-id="3aef1-119">In the side pane, set the value in the **Authorization** drop-down menu to **implicit**.</span></span> <span data-ttu-id="3aef1-120">A cabeceira `Authorization` engádese cun token de portador.</span><span class="sxs-lookup"><span data-stu-id="3aef1-120">The `Authorization` header gets with a bearer token added.</span></span> <span data-ttu-id="3aef1-121">A súa clave de subscrición encherase automaticamente.</span><span class="sxs-lookup"><span data-stu-id="3aef1-121">Your subscription key will be automatically populated.</span></span>
  
1. <span data-ttu-id="3aef1-122">Opcionalmente, engada todos os parámetros de consulta necesarios.</span><span class="sxs-lookup"><span data-stu-id="3aef1-122">Optionally, add all necessary query parameters.</span></span>

1. <span data-ttu-id="3aef1-123">Desprácese ata a parte inferior do panel lateral e seleccione **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="3aef1-123">Scroll to the bottom of the side pane and select **Send**.</span></span>

<span data-ttu-id="3aef1-124">A resposta HTTP aparecerá en breve a continuación.</span><span class="sxs-lookup"><span data-stu-id="3aef1-124">The HTTP response will soon appear below.</span></span>

## <a name="create-a-new-app-registration-in-the-azure-portal"></a><span data-ttu-id="3aef1-125">Crear un novo rexistro de aplicacións no portal de Azure</span><span class="sxs-lookup"><span data-stu-id="3aef1-125">Create a new app registration in the Azure portal</span></span>

<span data-ttu-id="3aef1-126">Estes pasos axúdanlle a comezar a usar as API de Customer Insights nunha aplicación de Azure mediante permisos delegados.</span><span class="sxs-lookup"><span data-stu-id="3aef1-126">These steps help you get started in using the Customer Insights APIs in an Azure application using delegated permissions.</span></span> <span data-ttu-id="3aef1-127">Asegúrese de que completou a [sección de inicio](#get-started-trying-the-customer-insights-apis) primeiro.</span><span class="sxs-lookup"><span data-stu-id="3aef1-127">Make sure to have completed [Getting started section](#get-started-trying-the-customer-insights-apis) first.</span></span>

1. <span data-ttu-id="3aef1-128">Inicie sesión no [Portal de Azure](https://portal.azure.com) coa conta que pode acceder aos datos de Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="3aef1-128">Sign in to the [Azure portal](https://portal.azure.com) with the account that can access the Customer Insights data.</span></span>

1. <span data-ttu-id="3aef1-129">Á esquerda, seleccione **Rexistros de aplicacións**.</span><span class="sxs-lookup"><span data-stu-id="3aef1-129">On the left, select **App registrations**.</span></span>

1. <span data-ttu-id="3aef1-130">Seleccione **Novo rexistro**, forneza un nome de aplicación e elixa o tipo de conta.</span><span class="sxs-lookup"><span data-stu-id="3aef1-130">Select **New registration** provide an application name and choose the account type.</span></span>
   <span data-ttu-id="3aef1-131">Opcionalmente, engada un URL de redireccionamento.</span><span class="sxs-lookup"><span data-stu-id="3aef1-131">Optionally, add a redirect URL.</span></span> <span data-ttu-id="3aef1-132">http://localhost é suficiente para desenvolver unha aplicación no seu computador local.</span><span class="sxs-lookup"><span data-stu-id="3aef1-132">http://localhost is sufficient for developing an application on your local computer.</span></span>

1. <span data-ttu-id="3aef1-133">No novo rexistro da aplicación, vaia a **Permisos de API**.</span><span class="sxs-lookup"><span data-stu-id="3aef1-133">On your new App registration, go to **API permissions**.</span></span>

1. <span data-ttu-id="3aef1-134">Seleccione **Engadir un permiso** e seleccione **Customer Insights** no panel lateral.</span><span class="sxs-lookup"><span data-stu-id="3aef1-134">Select **Add a permission** and select **Customer Insights** in the side pane.</span></span>

1. <span data-ttu-id="3aef1-135">Para o **Tipo de permiso**, seleccione **Permisos delegados** e seleccione o permiso **representación_usuario**.</span><span class="sxs-lookup"><span data-stu-id="3aef1-135">For **Permission type**, select **Delegated permissions** and select the **user_impersonation** permission.</span></span>

1. <span data-ttu-id="3aef1-136">Seleccione **Engadir permisos**.</span><span class="sxs-lookup"><span data-stu-id="3aef1-136">Select **Add permissions**.</span></span> <span data-ttu-id="3aef1-137">Se precisa acceder á API sen que un usuario inicie sesión, revise a sección [Permisos de aplicacións de servidor a servidor](#server-to-server-application-permissions).</span><span class="sxs-lookup"><span data-stu-id="3aef1-137">If you need to access the API without a user signing in, review the [Server-to-server application permissions](#server-to-server-application-permissions) section.</span></span>

1. <span data-ttu-id="3aef1-138">Seleccione **Outorgar o consentimento do administrador para...** para completar o rexistro da aplicación.</span><span class="sxs-lookup"><span data-stu-id="3aef1-138">Select **Grant admin consent for...** to complete the app registration.</span></span>

<span data-ttu-id="3aef1-139">Pode usar o ID de aplicación/cliente para este rexistro de aplicación coa Biblioteca de autenticación de Microsoft (MSAL) para obter un token de portador para enviar coa súa solicitude á API.</span><span class="sxs-lookup"><span data-stu-id="3aef1-139">You can use the Application/Client ID for this app registration with the Microsoft Authentication Library (MSAL) to obtain a bearer token to send with your request to the API.</span></span>

<span data-ttu-id="3aef1-140">Para obter máis información sobre a MSAL, consulte [Vista xeral da biblioteca de autenticación de Microsoft (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview).</span><span class="sxs-lookup"><span data-stu-id="3aef1-140">For more information about MSAL, see [Overview of Microsoft Authentication Library (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview).</span></span>

<span data-ttu-id="3aef1-141">Para obter máis información sobre o rexistro de aplicacións en Azure, consulte [A nova experiencia de rexistro de aplicacións do portal de Azure](https://docs.microsoft.com/azure/active-directory/develop/app-registration-portal-training-guide).</span><span class="sxs-lookup"><span data-stu-id="3aef1-141">For more information about app registration in Azure, see [The new Azure portal app registration experience](https://docs.microsoft.com/azure/active-directory/develop/app-registration-portal-training-guide).</span></span>

<span data-ttu-id="3aef1-142">Para obter información sobre o uso das API das nosas bibliotecas de clientes, consulte [Bibliotecas de clientes de Customer Insights](#customer-insights-client-libraries).</span><span class="sxs-lookup"><span data-stu-id="3aef1-142">For information on using the APIs our client libraries, see [Customer Insights client libraries](#customer-insights-client-libraries).</span></span>

### <a name="server-to-server-application-permissions"></a><span data-ttu-id="3aef1-143">Permisos de aplicacións de servidor a servidor</span><span class="sxs-lookup"><span data-stu-id="3aef1-143">Server-to-server application permissions</span></span>

<span data-ttu-id="3aef1-144">A [sección de rexistro de aplicacións](#create-a-new-app-registration-in-the-azure-portal) describe como rexistrar unha aplicación que require que un usuario inicie sesión para autenticarse.</span><span class="sxs-lookup"><span data-stu-id="3aef1-144">The [app registration section](#create-a-new-app-registration-in-the-azure-portal) outlines how to register an app that requires a user to sign in for authentication.</span></span> <span data-ttu-id="3aef1-145">Aprenda a crear un rexistro de aplicacións que non precisa a interacción do usuario e que se pode executar nun servidor.</span><span class="sxs-lookup"><span data-stu-id="3aef1-145">Learn how to create an app registration that does not need user interaction and can be run on a server.</span></span>

1. <span data-ttu-id="3aef1-146">No rexistro da súa aplicación no portal de Azure, vaia a **Permisos de API**.</span><span class="sxs-lookup"><span data-stu-id="3aef1-146">On your App registration in the Azure portal, go to **API permissions**.</span></span>

1. <span data-ttu-id="3aef1-147">Seleccione **Engadir un permiso** e seleccione **Customer Insights** no panel lateral.</span><span class="sxs-lookup"><span data-stu-id="3aef1-147">Select **Add a permission** and select **Customer Insights** in the side pane.</span></span>

1. <span data-ttu-id="3aef1-148">Para o **Tipo de permiso**, seleccione **Permisos de aplicación** e seleccione o permiso **CustomerInsights.Api.All**.</span><span class="sxs-lookup"><span data-stu-id="3aef1-148">For **Permission type**, select **Application permissions** and select the **CustomerInsights.Api.All** permission.</span></span>

1. <span data-ttu-id="3aef1-149">Seleccione **Engadir permisos**.</span><span class="sxs-lookup"><span data-stu-id="3aef1-149">Select **Add permissions**.</span></span>

1. <span data-ttu-id="3aef1-150">Para dar o consentimento do administrador neste permiso de aplicación, cómpre engadir unha entidade de seguranza do servizo.</span><span class="sxs-lookup"><span data-stu-id="3aef1-150">To give admin consent on this Application permission, you need to add a Service Principal.</span></span>

   1. <span data-ttu-id="3aef1-151">Instale o módulo Azure Active Directory (AD) PowerShell: `Install-Module -Name AzureAD -AllowClobber -Scope AllUsers`</span><span class="sxs-lookup"><span data-stu-id="3aef1-151">Install the Azure Active Directory (AD) PowerShell module: `Install-Module -Name AzureAD -AllowClobber -Scope AllUsers`</span></span>
   1. <span data-ttu-id="3aef1-152">Conecte coa conta de AD: `Connect-AzureAD -TenantId <your tenant id>`.</span><span class="sxs-lookup"><span data-stu-id="3aef1-152">Connect to your AD account: `Connect-AzureAD -TenantId <your tenant id>`.</span></span> <span data-ttu-id="3aef1-153">Pode atopar o seu ID de inquilino en **Visión xeral** > **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="3aef1-153">You can find your tenant ID on **Overview** > **Azure Active Directory**.</span></span>
   1. <span data-ttu-id="3aef1-154">Execute o seguinte comando para engadir unha entidade de seguranza do servizo de Azure AD: `New-AzureADServicePrincipal -AppId "38c77d00-5fcb-4cce-9d93-af4738258e3c" -DisplayName "Microsoft Dynamics 365 Customer Insights"` O parámetro AppId pertence á aplicación de API de Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="3aef1-154">Run the following command to add an Azure AD Service Principal: `New-AzureADServicePrincipal -AppId "38c77d00-5fcb-4cce-9d93-af4738258e3c" -DisplayName "Microsoft Dynamics 365 Customer Insights"` The AppId parameter pertains to the Customer Insights API app.</span></span>

   :::image type="content" source="media/azureAD-service-principal.png" alt-text="Exemplo de entidade de seguranza do servizo":::

1. <span data-ttu-id="3aef1-156">Volva a **Permisos de API** para rexistrar a aplicación.</span><span class="sxs-lookup"><span data-stu-id="3aef1-156">Go back to **API permissions** for your app registration.</span></span>

1. <span data-ttu-id="3aef1-157">Seleccione **Outorgar o consentimento do administrador para...** para completar o rexistro da aplicación.</span><span class="sxs-lookup"><span data-stu-id="3aef1-157">Select **Grant admin consent for...** to complete the app registration.</span></span>

1. <span data-ttu-id="3aef1-158">Para finalizar, temos que engadir o nome do rexistro da aplicación como usuario en Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="3aef1-158">To conclude, we have to add the name of the app registration as a user in Customer Insights.</span></span>    
   <span data-ttu-id="3aef1-159">Abra Customer Insights, vaia a **Administrar** > **Permisos** e seleccione **Engadir usuario**.</span><span class="sxs-lookup"><span data-stu-id="3aef1-159">Open Customer Insights, go to **Admin** > **Permissions** and select **Add user**.</span></span>

1. <span data-ttu-id="3aef1-160">Busque o nome do rexistro da súa aplicación, seleccióneo entre os resultados da busca e seleccione **Gardar**.</span><span class="sxs-lookup"><span data-stu-id="3aef1-160">Search for the name of your app registration, select it from the search results, and select **Save**.</span></span>

## <a name="customer-insights-client-libraries"></a><span data-ttu-id="3aef1-161">Bibliotecas de clientes de Customer Insights</span><span class="sxs-lookup"><span data-stu-id="3aef1-161">Customer Insights client libraries</span></span>

<span data-ttu-id="3aef1-162">Esta sección axuda a comezar a usar as bibliotecas de clientes dispoñibles para as API de Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="3aef1-162">This section helps you get started using the client libraries available for the Customer Insights APIs.</span></span>

### <a name="c-nuget"></a><span data-ttu-id="3aef1-163">C# NuGet</span><span class="sxs-lookup"><span data-stu-id="3aef1-163">C# NuGet</span></span>

<span data-ttu-id="3aef1-164">Aprenda a comezar a usar as bibliotecas de clientes de C # desde NuGet.org. Para obter máis información sobre o paquete NuGet, vexa [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span><span class="sxs-lookup"><span data-stu-id="3aef1-164">Learn how to get started using the C# client libraries from NuGet.org. For more information on the NuGet package, see [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span></span> <span data-ttu-id="3aef1-165">Actualmente, este paquete ten como obxectivo os frameworks netstandard2.0 e netcoreapp2.0.</span><span class="sxs-lookup"><span data-stu-id="3aef1-165">Currently, this package targets the netstandard2.0 and netcoreapp2.0 frameworks.</span></span>

#### <a name="add-the-c-client-library-to-a-c-project"></a><span data-ttu-id="3aef1-166">Engadir a biblioteca de clientes de C# a un proxecto de C#</span><span class="sxs-lookup"><span data-stu-id="3aef1-166">Add the C# client library to a C# project</span></span>

1. <span data-ttu-id="3aef1-167">En Visual Studio, abra o **Xestor de paquetes de NuGet** para o seu proxecto.</span><span class="sxs-lookup"><span data-stu-id="3aef1-167">In Visual Studio, open the **NuGet Package Manager** for your project.</span></span>

1. <span data-ttu-id="3aef1-168">Buscar **Microsoft.Dynamics.CustomerInsights.Api**.</span><span class="sxs-lookup"><span data-stu-id="3aef1-168">Search for **Microsoft.Dynamics.CustomerInsights.Api**.</span></span>

1. <span data-ttu-id="3aef1-169">Seleccione **Instalar** para engadir o paquete ao proxecto.</span><span class="sxs-lookup"><span data-stu-id="3aef1-169">Select **Install** to add the package to the project.</span></span>
   <span data-ttu-id="3aef1-170">Como alternativa, execute este comando na **Consola do xestor de paquetes de NuGet**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span><span class="sxs-lookup"><span data-stu-id="3aef1-170">Alternatively, run this command in the **NuGet Package Manager Console**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span></span>

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Engadir paquete de NuGet a un proxecto de Visual Studio":::

#### <a name="use-the-c-client-library"></a><span data-ttu-id="3aef1-172">Usar a biblioteca de clientes de C#</span><span class="sxs-lookup"><span data-stu-id="3aef1-172">Use the C# client library</span></span>

1. <span data-ttu-id="3aef1-173">Use a [Biblioteca de autenticación de Microsoft (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview) para obter un `AccessToken` usando o seu [Rexistro de aplicacións de Azure](#create-a-new-app-registration-in-the-azure-portal) existente.</span><span class="sxs-lookup"><span data-stu-id="3aef1-173">Use the [Microsoft Authentication Library (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview) to get an `AccessToken` using your existing [Azure app registration](#create-a-new-app-registration-in-the-azure-portal).</span></span>

1. <span data-ttu-id="3aef1-174">Despois de autenticar e adquirir con éxito un token, constrúa un `HttpClient` novo ou use un xa existente coa **"Autorización" de DefaultRequestHeaders** adicional definida en **<access token> de portador** e **Ocp-Apim-Subscription-Key** definida como [**clave de subscrición** do seu contorno de Customer Insights](#get-started-trying-the-customer-insights-apis).</span><span class="sxs-lookup"><span data-stu-id="3aef1-174">After successfully authenticating and acquiring a token, construct a new or use an existing `HttpClient` with the additional **DefaultRequestHeaders "Authorization"** set to **Bearer <access token>** and **Ocp-Apim-Subscription-Key** set to the [**subscription key** from your Customer Insights environment](#get-started-trying-the-customer-insights-apis).</span></span>    
   <span data-ttu-id="3aef1-175">Restableza a cabeceira da **Autorización** cando corresponda.</span><span class="sxs-lookup"><span data-stu-id="3aef1-175">Reset the **Authorization** header when appropriate.</span></span> <span data-ttu-id="3aef1-176">Por exemplo, cando o token caducou.</span><span class="sxs-lookup"><span data-stu-id="3aef1-176">For example, when the token expired.</span></span>

1. <span data-ttu-id="3aef1-177">Pase este `HttpClient` na construción do cliente de `CustomerInsights`.</span><span class="sxs-lookup"><span data-stu-id="3aef1-177">Pass this `HttpClient` into the construction of the `CustomerInsights` client.</span></span>

   :::image type="content" source="media/httpclient-sample.png" alt-text="Mostra de httpclient":::

1. <span data-ttu-id="3aef1-179">Faga chamadas co cliente aos "métodos de extensión", por exemplo, `GetAllInstancesAsync`.</span><span class="sxs-lookup"><span data-stu-id="3aef1-179">Make calls with the client to the "extension methods", for example, `GetAllInstancesAsync`.</span></span> <span data-ttu-id="3aef1-180">Se o acceso á `Microsoft.Rest.HttpOperationResponse` subxacente é preferible, use os "métodos de mensaxes http", por exemplo `GetAllInstancesWithHttpMessagesAsync`.</span><span class="sxs-lookup"><span data-stu-id="3aef1-180">If access to the underlying `Microsoft.Rest.HttpOperationResponse` is preferred, use the "http message methods", for example `GetAllInstancesWithHttpMessagesAsync`.</span></span>

1. <span data-ttu-id="3aef1-181">É probable que a resposta sexa de tipo `object` porque o método pode devolver varios tipos (por exemplo, `IList<InstanceInfo>` e `ApiErrorResult`).</span><span class="sxs-lookup"><span data-stu-id="3aef1-181">The response will likely be of type `object` because the method can return multiple types (for example, `IList<InstanceInfo>` and `ApiErrorResult`).</span></span> <span data-ttu-id="3aef1-182">Para comprobar o tipo de devolución, pode lanzar os obxectos con seguridade nos tipos de resposta especificados na [Páxina de detalles da API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) para esa operación.</span><span class="sxs-lookup"><span data-stu-id="3aef1-182">To check the return type, you can safely cast the objects into the response types specified on the [API details page](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) for that operation.</span></span>    
   <span data-ttu-id="3aef1-183">Se precisa máis información sobre a solicitude, use os **Métodos de mensaxes http** para acceder ao obxecto de resposta orixinal.</span><span class="sxs-lookup"><span data-stu-id="3aef1-183">If more information on the request is needed, use the **http message methods** to access the raw response object.</span></span>
