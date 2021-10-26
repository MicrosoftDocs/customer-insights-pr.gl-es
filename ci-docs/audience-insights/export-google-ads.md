---
title: Exportar datos de Customer Insights a Google Ads
description: Aprenda a configurar a conexión e exportar a Google Ads.
ms.date: 09/27/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: ce9579f3d31207e666665237fd8935bb86889f8d
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 10/08/2021
ms.locfileid: "7617916"
---
# <a name="export-segments-to-google-ads-preview"></a>Exportar segmentos a Google Ads (versión preliminar)

Exporte segmentos de perfís de clientes unificados a unha lista de público de Google Ads e utilíceos para anunciarse na Busca de Google, Gmail, YouTube e a Rede de visualización de Google. 

> [!IMPORTANT]
> Actualmente, só pode crear unha nova conexión e exportar datos a Google Ads se xa ten un token de programador de Google Ads aprobado. Debido a cambios na política, actualizaremos a exportación de Google Ads en breve e ofreceremos unha opción de exportación que non requirirá un token de programador para garantir a continuidade da súa experiencia e simplificar a exportación a Google Ads. Recomendamos non configurar máis conexións con Google Ads para facilitar o cambio á nova opción de exportación.

## <a name="prerequisites-for-connection"></a>Requisitos previos para a conexión

-   Ten unha [Conta de Google Ads](https://ads.google.com/) e as correspondentes credenciais de administrador.
-   Ten un [token de programador de Google Ads aprobado](https://developers.google.com/google-ads/api/docs/first-call/dev-token). 
-   Cumpre os requisitos da [Política de coincidencia de clientes](https://support.google.com/adspolicy/answer/6299717).
-   Cumpre os requisitos dos [tamaños de lista de remárketing](https://support.google.com/google-ads/answer/7558048).
-   Existen públicos en Google Ads e os ID correspondentes. Para obter máis información, consulte [Públicos de Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).
-   Ten [segmentos configurados](segments.md).
-   Os perfís de clientes unificados nos segmentos exportados conteñen campos que representan un enderezo de correo electrónico, nome e apelidos.

## <a name="known-limitations"></a>Limitacións coñecidas

- Ata 1 millón de perfís de clientes por exportación a Google Ads.
- A exportación a Google Ads está limitada a segmentos.
- A exportación de segmentos cun total de 1 millón de perfís de clientes pode levar ata 5 minutos por mor das limitacións do provedor. 
- A busca de coincidencias en Google Ads pode levar ata 48 horas.

## <a name="set-up-connection-to-google-ads"></a>Configurar conexión a Google Ads

1. Vaia a **Administrar** > **Conexións**.

1. Seleccione **Engadir conexión** e elixa **Google Ads** para configurar a conexión.

1. Déalle á conexión un nome recoñecible no campo **Nome para mostrar**. O nome e o tipo de conexión describen esta conexión. Recomendamos escoller un nome que explique o propósito e o destino da conexión.

1. Escolla quen pode usar esta conexión. Se non realiza ningunha acción, o valor predeterminado será Administradores. Para obter máis información, consulte [Permitir aos colaboradores usar unha conexión para as exportacións](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Insira o seu **[ID de cliente de Google Ads](https://support.google.com/google-ads/answer/1704344)**.

1. Introduza o seu **[Token de programador aprobado por Google Ads](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.

1. Seleccione **Estou de acordo** para confirmar a **Privacidade e cumprimento dos datos**.

1. Seleccione **Autenticarse con Google Ads** e proporcione as súas credenciais de Google Ads.

1. Seleccione **Autoengadirse como usuario de exportación** e proporcione as súas credenciais de Customer Insights.

1. Seleccione **Gardar** para completar a conexión. 

## <a name="configure-an-export"></a>Configurar unha exportación

Pode configurar esta exportación se ten acceso a unha conexión deste tipo. Para obter máis información, consulte [Permisos necesarios para configurar unha exportación](export-destinations.md#set-up-a-new-export).

1. Vaia a **Datos** > **Exportacións**.

1. Seleccione **Engadir destino** para crear unha nova exportación.

1. No campo **Conexión da exportación** escolla unha conexión da sección Google Ads. Se non ve o nome desta sección, non ten ningunha conexión deste tipo dispoñible.

1. Introduza o seu **[ID de audiencia de Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** e seleccione **Conectar** para inicializar a conexión a Google Ads.

1. Na sección **Coincidencia de datos** do campo **Correo electrónico**, seleccione o campo que representa o enderezo de correo electrónico dun cliente.

1. Seleccione os segmentos que desexa exportar. Pode exportar ata 1 millón de perfís de clientes en total a Google Ads.

Ao gardar unha exportación non se executa a exportación inmediatamente.

A exportación execútase con cada [actualización programada](system.md#schedule-tab). 

Tamén pode [exportar datos baixo demanda](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Cumprimento e privacidade dos datos

Cando habilita Dynamics 365 Customer Insights para transmitir datos a Google Ads, permite a transferencia de datos fóra do límite de cumprimento de Dynamics 365 Customer Insights, incluíndo datos potencialmente confidenciais como os datos persoais. Microsoft transferirá estes datos segundo a súa instrución, pero vostede é responsable de garantir que Google Ads cumpra as obrigas de privacidade ou seguridade que poida ter. Para obter máis información, consulte a [Declaración de privacidade de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
O administrador de Dynamics 365 Customer Insights pode eliminar este destino de exportación en calquera momento para interromper o uso desta funcionalidade.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
