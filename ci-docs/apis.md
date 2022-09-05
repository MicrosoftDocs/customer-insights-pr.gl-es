---
title: Traballar coas API de Customer Insights
description: Use as API e comprenda as limitacións.
ms.date: 08/31/2022
ms.reviewer: wimohabb
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
searchScope:
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: f499bff4a6ac07a88ff0f773b9cee77dc74989e8
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387338"
---
# <a name="work-with-customer-insights-apis"></a>Traballar coas API de Customer Insights

Dynamics 365 Customer Insights ofrece as API para crear as súas propias aplicacións baseadas nos seus datos en Customer Insights.

> [!IMPORTANT]
> Os detalles destas API enuméranse na [referencia das API de Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). Inclúen información adicional sobre operacións, parámetros e respostas.

Proba as API de Customer Insights, crea un rexistro de aplicacións de Azure e comece coas bibliotecas de clientes.

## <a name="get-started-trying-the-customer-insights-apis"></a>Comezar a probar as API de Customer Insights

Activa as API de Customer Insights e próbaas. Un administrador de Customer Insights debe activar o acceso da API a Customer Insights. Unha vez habilitado o acceso, calquera usuario pode usar a API coa clave de subscrición.

1. [Inicie sesión](https://home.ci.ai.dynamics.com) en Customer Insights. Se aínda non ten unha subscrición, [Rexístrese para obter unha versión de proba de Customer Insights](https://aka.ms/tryci).

1. Ir a **Admin** > **Seguridade** e selecciona o **APIs** ficha.

1. Se non se configurou o acceso da API ao contorno, seleccione **Activar** .

   Habilitar as API crea unha clave de subscrición principal e secundaria para a súa instancia que se usa nas solicitudes de API. Para rexenerar as teclas, seleccione **Rexenerar primaria** ou **Rexenerar secundaria** no **APIs** ficha.

1. Seleccione [**Explora as nosas API**](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) para probar as API.

1. Busca e selecciona unha operación da API e selecciona **Próbao**.

   :::image type="content" source="media/try-api.png" alt-text="Como probar as API.":::

1. No panel lateral, configure o valor no menú despregable **Autorización** a **implícita**. A cabeceira `Authorization` engádese cun token de portador. A túa clave de subscrición enchérase automaticamente.
  
1. Opcionalmente, engada todos os parámetros de consulta necesarios.

1. Desprácese ata a parte inferior do panel lateral e seleccione **Enviar**.

   A resposta HTTP móstrase na parte inferior do panel.

## <a name="create-a-new-app-registration-in-the-azure-portal"></a>Crear un novo rexistro de aplicacións no portal de Azure

Crea un novo [rexistro da aplicación](/graph/auth-register-app-v2) para usar as API de Customer Insights nunha aplicación de Azure mediante permisos delegados.

1. Completar o [Sección de inicio](#get-started-trying-the-customer-insights-apis).

1. Inicie sesión no [Portal de Azure](https://portal.azure.com) coa conta que pode acceder aos datos de Customer Insights.

1. Busca e despois selecciona **Rexistros da aplicación**.

1. Seleccione **Novo rexistro**, forneza un nome de aplicación e elixa o tipo de conta.

   Opcionalmente, engada un URL de redireccionamento. http://localhost é suficiente para desenvolver unha aplicación no seu computador local.

1. Seleccione **Rexistrar**.

1. No novo rexistro da aplicación, vaia a **Permisos de API**.

1. Seleccione **Engade un permiso** e selecciona **Dynamics 365 AI para Customer Insights** no panel lateral.

1. Para **Tipo de permiso**, seleccione **Permisos delegados** e logo seleccione o permiso **user_impersonation**.

1. Seleccione **Engadir permisos**.

1. Seleccione **Outorgar o consentimento do administrador para...** para completar o rexistro da aplicación.

1. Para acceder á API sen que o usuario inicie sesión, vai a [Permisos de aplicación de servidor a servidor](#server-to-server-application-permissions).

Podes usar o ID da aplicación/cliente para o rexistro desta aplicación co [Biblioteca de autenticación de Microsoft (MSAL)](/azure/active-directory/develop/msal-overview) para obter un token de portador para enviar coa súa solicitude á API.

<!-- :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

Para obter información sobre o uso das API nas nosas bibliotecas de clientes, consulte [Bibliotecas clientes de Customer Insights](#customer-insights-client-libraries).

### <a name="server-to-server-application-permissions"></a>Permisos de aplicacións de servidor a servidor

Crea un rexistro de aplicación que non necesite interacción do usuario e que se poida executar nun servidor.

1. No rexistro da súa aplicación no portal de Azure, vaia a **Permisos de API**.

1. Seleccione **Engadir un permiso**.

1. Seleccione o separador **API que usa a miña organización** e escolla **Dynamics 365 AI for Customer Insights** da lista.

1. Para **Tipo de permiso**, seleccione **Permisos de aplicación** e logo seleccione o permiso **CustomerInsights.Api.All**.

1. Seleccione **Engadir permisos**.

1. Volva a **Permisos de API** para rexistrar a aplicación.

1. Seleccione **Outorgar o consentimento do administrador para...** para completar o rexistro da aplicación.

   <!--  :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

1. Engade o nome do rexistro da aplicación como usuario en Customer Insights.

   1. Abre Customer Insights, vai a **Admin** > **Seguridade** e selecciona **Engadir usuarios**.

   1. Busque o nome do rexistro da súa aplicación, seleccióneo entre os resultados da busca e seleccione **Gardar**.

## <a name="sample-queries"></a>Consultas de exemplo

Para obter unha breve lista de consultas de mostra de OData para traballar coas API, consulte [Exemplos de consulta OData](odata-examples.md).

## <a name="customer-insights-client-libraries"></a>Bibliotecas de clientes de Customer Insights

Comeza a usar as bibliotecas de clientes dispoñibles para as API de Customer Insights. Todos os códigos fonte da biblioteca e as aplicacións de mostra pódense atopar na [Páxina de GitHub de Customer Insights](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries).

### <a name="c-nuget"></a>C# NuGet

Use as bibliotecas cliente C# de NuGet .org. Actualmente, o paquete está dirixido aos marcos netstandard2.0 e netcoreapp2.0. Para máis información sobre o NuGet paquete, ver [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).

#### <a name="add-the-c-client-library-to-a-c-project"></a>Engadir a biblioteca de clientes de C# a un proxecto de C#

1. En Visual Studio, abra o **Xestor de paquetes de NuGet** para o seu proxecto.

1. Buscar **Microsoft.Dynamics.CustomerInsights.Api**.

1. Seleccione **Instalar** para engadir o paquete ao proxecto.

   Como alternativa, execute este comando na **Consola do xestor de paquetes de NuGet**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`

   <!--  :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Add NuGet package to Visual Studio project."::: -->

#### <a name="use-the-c-client-library"></a>Usar a biblioteca de clientes de C#

1. Use a [Biblioteca de autenticación de Microsoft (MSAL)](/azure/active-directory/develop/msal-overview) para obter un `AccessToken` usando o seu [Rexistro de aplicacións de Azure](#create-a-new-app-registration-in-the-azure-portal) existente.

1. Despois de autenticarse e adquirir un token con éxito, constrúe un novo ou use un existente`HttpClient` co **DefaultRequestHeaders "Autorización"** configurado en **"Token de acceso" do portador** e **Ocp-Apim-Clave de subscrición** establecer a [**clave de subscrición** desde o teu ambiente de Customer Insights](#get-started-trying-the-customer-insights-apis).   

   Restableza a cabeceira da **Autorización** cando corresponda. Por exemplo, cando o token caducou.

1. Pase este `HttpClient` na construción do cliente de `CustomerInsights`.

   <!--   :::image type="content" source="media/httpclient-sample.png" alt-text="Sample of httpclient."::: -->

1. Faga chamadas co cliente aos "métodos de extensión", por exemplo, `GetAllInstancesAsync`. Se o acceso ao subxacente`Microsoft.Rest.HttpOperationResponse` prefire, use os "métodos de mensaxes http", por exemplo,`GetAllInstancesWithHttpMessagesAsync`.

1. A resposta é probable`object` tipo porque o método pode devolver varios tipos (por exemplo,`IList<InstanceInfo>` e`ApiErrorResult`). Para comprobar o tipo de devolución, use os obxectos dos tipos de resposta especificados no ficheiro [Páxina de detalles da API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) para esa operación.

   Se precisa máis información sobre a solicitude, use os **Métodos de mensaxes http** para acceder ao obxecto de resposta orixinal.

### <a name="nodejs-package"></a>Paquete NodeJS

Use as bibliotecas cliente de NodeJS dispoñibles a través de NPM: https://www.npmjs.com/package/@microsoft/customerinsights

### <a name="python-package"></a>Paquete Python

Use as bibliotecas cliente de Python dispoñibles a través de PyPi: https://pypi.org/project/customerinsights/

[!INCLUDE [footer-include](includes/footer-banner.md)]
