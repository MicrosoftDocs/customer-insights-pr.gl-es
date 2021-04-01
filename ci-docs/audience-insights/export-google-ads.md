---
title: Exportar datos de Customer Insights a Google Ads
description: Aprenda a configurar a conexión a Google Ads.
ms.date: 11/18/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6d9a25af3913e755cccec745c532b35aef3cccf9
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598245"
---
# <a name="connector-for-google-ads-preview"></a>Conector para Google Ads (vista previa)

Exporte segmentos de perfís de clientes unificados á lista de públicos de Google Ads e utilíceos para anunciarse na Busca de Google, en Gmail, YouTube e na Rede de Display de Google. 

## <a name="prerequisites"></a>Requisitos previos

-   Ten unha [Conta de Google Ads](https://ads.google.com/) e as correspondentes credenciais de administrador.
-   Existen públicos en Google Ads e os ID correspondentes. Para obter máis información, consulte [Públicos de Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).
-   Ten [segmentos configurados](segments.md)
-   Os perfís de clientes unificados nos segmentos exportados conteñen campos que representan un enderezo de correo electrónico, nome e apelidos

## <a name="connect-to-google-ads"></a>Conectarse con Google Ads

1. Vaia a **Administrador** > **Exportar destinos**.

1. En **Google Ads**, seleccione **Configurar**.

1. Déalle ao seu destino da exploración un nome recoñecible no campo **Nome para mostrar**.

1. Insira o seu **[ID de cliente de Google Ads](https://support.google.com/google-ads/answer/1704344)**.

1. Introduza o seu **[Token de programador aprobado por Google Ads](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.

1. Seleccione **Estou de acordo** para confirmar a **Privacidade e cumprimento dos datos**.

1. Introduza o seu **[ID de audiencia de Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** e seleccione **Conectar** para inicializar a conexión a Google Ads.

1. Seleccione **Autenticarse con Google Ads** e proporcione as súas credenciais de Google Ads.

1. Seleccione **Autoengadirse como usuario de exportación** e proporcione as súas credenciais de Customer Insights.

   :::image type="content" source="media/export-segments-googleads.PNG" alt-text="Captura de pantalla de exportación para a conexión de Google Ads":::

1. Seleccione **Seguinte** para configurar a exportación.

## <a name="configure-the-connector"></a>Configurar o conector

1. Na sección **Coincidencia de datos**, no campo **Correo electrónico**, seleccione o campo do seu perfil de cliente unificado que representa o enderezo de correo electrónico dun cliente. Repita os mesmos pasos para os campos **nome** e **apelidos**.

1. Seleccione os segmentos que desexa exportar. Pode exportar ata 1 millón de perfís de clientes en total a Google Ads.

1. Seleccione **Gardar**.

## <a name="export-the-data"></a>Exportar os datos

Pode [exportar datos baixo demanda](export-destinations.md). A exportación tamén se executará con todas as [actualizacións programadas](system.md#schedule-tab). En Google Ads, agora pode atopar os seus segmentos en [Públicos de Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en/).

## <a name="known-limitations"></a>Limitacións coñecidas

- Ata 1 millón de perfís por exportación a Google Ads.
- A exportación a Google Ads está limitada a segmentos.
- A exportación de segmentos cun total de 1 millón de perfís pode levar ata 5 minutos debido ás limitacións do provedor. 
- A busca de coincidencias en Google Ads pode levar ata 48 horas.

## <a name="data-privacy-and-compliance"></a>Cumprimento e privacidade dos datos

Cando habilita Dynamics 365 Customer Insights para transmitir datos a Google Ads, permite a transferencia de datos fóra do límite de cumprimento de Dynamics 365 Customer Insights, incluíndo datos potencialmente confidenciais como os datos persoais. Microsoft transferirá estes datos segundo a súa instrución, pero vostede é responsable de garantir que Google Ads cumpra as obrigas de privacidade ou seguridade que poida ter. Para obter máis información, consulte a [Declaración de privacidade de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
O administrador de Dynamics 365 Customer Insights pode eliminar este destino de exportación en calquera momento para interromper o uso desta funcionalidade.


[!INCLUDE[footer-include](../includes/footer-banner.md)]