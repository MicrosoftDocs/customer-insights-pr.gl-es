---
title: Traballar con API
description: Use as API e comprenda as limitacións.
ms.date: 05/10/2021
ms.reviewer: wimohabb
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
searchScope:
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: b1e022f8afb8b7dbb707636009b6a25ee242a4e0
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 02/25/2022
ms.locfileid: "8354783"
---
# <a name="work-with-customer-insights-apis"></a>Traballar coas API de Customer Insights

Dynamics 365 Customer Insights ofrece as API para crear as súas propias aplicacións baseadas nos seus datos en Customer Insights.

> [!IMPORTANT]
> Os detalles destas API enuméranse na [referencia das API de Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). Inclúen información adicional sobre operacións, parámetros e respostas.

Este artigo describe como acceder ás API de Customer Insights, crear un rexistro de aplicacións de Azure e comezar a usar as bibliotecas de clientes dispoñibles.

## <a name="get-started-trying-the-customer-insights-apis"></a>Comezar a probar as API de Customer Insights

1. [Inicie sesión](https://home.ci.ai.dynamics.com) en Customer Insights. Se aínda non ten unha subscrición, [Rexístrese para obter unha versión de proba de Customer Insights](https://aka.ms/tryci).

1. Para habilitar as API no seu contorno de Customer Insights, vaia a **Administrar** > **Permisos**. Necesitará permisos de administrador para facelo.

1. Vaia ao separador **API** e seleccione o botón **Activar**.    
 
   Habilitar as API crea unha clave de subscrición principal e secundaria para a súa instancia que se usa nas solicitudes de API. Pode volver xerar as teclas seleccionando **Volver xerar primaria** ou **Volver xerar secundaria** en **Administrar** > **Permisos** > **API**.

<!--  :::image type="content" source="media/enable-apis.gif" alt-text="Enable Customer Insights APIs."::: -->

1. Seleccione **Explorar as nosas API** para [probar as API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).

1. Escolla unha operación de API e seleccione **Probala**.

1. No panel lateral, configure o valor no menú despregable **Autorización** a **implícita**. A cabeceira `Authorization` engádese cun token de portador. A súa clave de subscrición encherase automaticamente.
  
1. Opcionalmente, engada todos os parámetros de consulta necesarios.

1. Desprácese ata a parte inferior do panel lateral e seleccione **Enviar**.

A resposta HTTP aparecerá en breve a continuación.

<!--   :::image type="content" source="media/try-apis.gif" alt-text="How to test the APIs."::: -->

## <a name="create-a-new-app-registration-in-the-azure-portal"></a>Crear un novo rexistro de aplicacións no portal de Azure

Estes pasos axúdanlle a comezar a usar as API de Customer Insights nunha aplicación de Azure mediante permisos delegados. Asegúrese de completar a [Sección de inicio](#get-started-trying-the-customer-insights-apis) primeiro.

1. Inicie sesión no [Portal de Azure](https://portal.azure.com) coa conta que pode acceder aos datos de Customer Insights.

1. Á esquerda, seleccione **Rexistros de aplicacións**.

1. Seleccione **Novo rexistro**, forneza un nome de aplicación e elixa o tipo de conta.
 
   Opcionalmente, engada un URL de redireccionamento. http://localhost é suficiente para desenvolver unha aplicación no seu computador local.

1. No novo rexistro da aplicación, vaia a **Permisos de API**.

<!--   :::image type="content" source="media/app-registration-1.gif" alt-text="How to set API permissions in App registration."::: -->

1. Seleccione **Engadir un permiso** e seleccione **Customer Insights** no panel lateral.

1. Para **Tipo de permiso**, seleccione **Permisos delegados** e logo seleccione o permiso **user_impersonation**.

1. Seleccione **Engadir permisos**. Se precisa acceder á API sen que un usuario inicie sesión, revise a sección [Permisos de aplicacións de servidor a servidor](#server-to-server-application-permissions).

1. Seleccione **Outorgar o consentimento do administrador para...** para completar o rexistro da aplicación.

Pode usar o ID de aplicación/cliente para este rexistro de aplicación coa Biblioteca de autenticación de Microsoft (MSAL) para obter un token de portador para enviar coa súa solicitude á API.

<!-- :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

Para obter máis información sobre a MSAL, consulte [Vista xeral da biblioteca de autenticación de Microsoft (MSAL)](/azure/active-directory/develop/msal-overview).

Para obter máis información sobre o rexistro de aplicacións en Azure, consulte [Rexistrar unha aplicación](/azure/active-directory/develop/quickstart-register-app.md#register-an-application).

Para obter información sobre o uso das API nas nosas bibliotecas de clientes, consulte [Bibliotecas clientes de Customer Insights](#customer-insights-client-libraries).

### <a name="server-to-server-application-permissions"></a>Permisos de aplicacións de servidor a servidor

A [sección de rexistro de aplicacións](#create-a-new-app-registration-in-the-azure-portal) describe como rexistrar unha aplicación que require que un usuario inicie sesión para autenticarse. Aprenda a crear un rexistro de aplicacións que non precisa a interacción do usuario e que se pode executar nun servidor.

1. No rexistro da súa aplicación no portal de Azure, vaia a **Permisos de API**.

1. Seleccione **Engadir un permiso**. 

1. Seleccione o separador **API que usa a miña organización** e escolla **Dynamics 365 AI for Customer Insights** da lista. 

1. Para **Tipo de permiso**, seleccione **Permisos de aplicación** e logo seleccione o permiso **CustomerInsights.Api.All**.

1. Seleccione **Engadir permisos**.

1. Volva a **Permisos de API** para rexistrar a aplicación.

1. Seleccione **Outorgar o consentimento do administrador para...** para completar o rexistro da aplicación.

 <!--  :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

1. Para finalizar, temos que engadir o nome do rexistro da aplicación como usuario en Customer Insights.  
   
   Abra Customer Insights, vaia a **Administrar** > **Permisos** e seleccione **Engadir usuario**.

1. Busque o nome do rexistro da súa aplicación, seleccióneo entre os resultados da busca e seleccione **Gardar**.

## <a name="customer-insights-client-libraries"></a>Bibliotecas de clientes de Customer Insights

Esta sección axuda a comezar a usar as bibliotecas de clientes dispoñibles para as API de Customer Insights. Todos os códigos fonte da biblioteca e as aplicacións de mostra pódense atopar na [Páxina de GitHub de Customer Insights](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries). 

### <a name="c-nuget"></a>C# NuGet

Aprenda a comezar a usar as bibliotecas de clientes de C # desde NuGet.org. Para obter máis información sobre o paquete NuGet, vexa [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/). Actualmente, este paquete ten como obxectivo os frameworks netstandard2.0 e netcoreapp2.0.

#### <a name="add-the-c-client-library-to-a-c-project"></a>Engadir a biblioteca de clientes de C# a un proxecto de C#

1. En Visual Studio, abra o **Xestor de paquetes de NuGet** para o seu proxecto.

1. Buscar **Microsoft.Dynamics.CustomerInsights.Api**.

1. Seleccione **Instalar** para engadir o paquete ao proxecto.
 
   Como alternativa, execute este comando na **Consola do xestor de paquetes de NuGet**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`

 <!--  :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Add NuGet package to Visual Studio project."::: -->

#### <a name="use-the-c-client-library"></a>Usar a biblioteca de clientes de C#

1. Use a [Biblioteca de autenticación de Microsoft (MSAL)](/azure/active-directory/develop/msal-overview) para obter un `AccessToken` usando o seu [Rexistro de aplicacións de Azure](#create-a-new-app-registration-in-the-azure-portal) existente.

1. Despois de autenticarse e adquirir un token con éxito, constrúe un novo ou use un existente`HttpClient` co adicional **DefaultRequestHeaders "Autorización"** configurado para **"Token de acceso" do portador** e **Ocp-Apim-Clave de subscrición** establecer a [**clave de subscrición** desde o teu ambiente de Customer Insights](#get-started-trying-the-customer-insights-apis).   
 
   Restableza a cabeceira da **Autorización** cando corresponda. Por exemplo, cando o token caducou.

1. Pase este `HttpClient` na construción do cliente de `CustomerInsights`.

<!--   :::image type="content" source="media/httpclient-sample.png" alt-text="Sample of httpclient."::: -->

1. Faga chamadas co cliente aos "métodos de extensión", por exemplo, `GetAllInstancesAsync`. Se o acceso á `Microsoft.Rest.HttpOperationResponse` subxacente é preferible, use os "métodos de mensaxes http", por exemplo `GetAllInstancesWithHttpMessagesAsync`.

1. É probable que a resposta sexa de tipo `object` porque o método pode devolver varios tipos (por exemplo, `IList<InstanceInfo>` e `ApiErrorResult`). Para comprobar o tipo de devolución, pode lanzar os obxectos con seguridade nos tipos de resposta especificados na [Páxina de detalles da API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) para esa operación.    
   
   Se precisa máis información sobre a solicitude, use os **Métodos de mensaxes http** para acceder ao obxecto de resposta orixinal.

### <a name="nodejs-package"></a>Paquete NodeJS

Use as bibliotecas cliente de NodeJS dispoñibles a través de NPM: https://www.npmjs.com/package/@microsoft/customerinsights

### <a name="python-package"></a>Paquete Python

Use as bibliotecas cliente de Python dispoñibles a través de PyPi: https://pypi.org/project/customerinsights/

[!INCLUDE[footer-include](../includes/footer-banner.md)]
