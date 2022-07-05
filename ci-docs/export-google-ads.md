---
title: Exportar segmentos a Google Ads (versión preliminar)
description: Aprenda a configurar a conexión e exportar a Google Ads.
ms.date: 03/31/2022
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: b7f08936d7d90322cb4e62396a2961fe06273b76
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082993"
---
# <a name="export-segments-to-google-ads-preview"></a>Exportar segmentos a Google Ads (versión preliminar)

Exporte segmentos de perfís de clientes unificados a unha lista de público de Google Ads e utilíceos para anunciarse na Busca de Google, Gmail, YouTube e a Rede de visualización de Google. 


## <a name="prerequisites-for-connection"></a>Requisitos previos para a conexión

-   Ten unha [Conta de Google Ads](https://ads.google.com/) e as correspondentes credenciais de administrador.
-   Cumpre os requisitos da [Política de coincidencia de clientes](https://support.google.com/adspolicy/answer/6299717).
-   Cumpre os requisitos dos [tamaños de lista de remárketing](https://support.google.com/google-ads/answer/7558048).
-   Ten [segmentos configurados](segments.md).
-   Os perfís de clientes unificados nos segmentos exportados conteñen campos que representan un enderezo de correo electrónico, teléfono, ID de anunciante móbil, ID de usuario de terceiros ou enderezo.

## <a name="known-limitations"></a>Limitacións coñecidas

- A exportación a Google Ads está limitada a segmentos.
- A exportación de segmentos cun total de 1 millón de perfís de clientes pode levar ata 30 minutos por mor das limitacións do provedor. 
- A busca de coincidencias en Google Ads pode levar ata 48 horas.

## <a name="set-up-connection-to-google-ads"></a>Configurar conexión a Google Ads

1. Vaia a **Administrar** > **Conexións**.

1. Seleccione **Engadir conexión** e elixa **Google Ads** para configurar a conexión.

1. Déalle á conexión un nome recoñecible no campo **Nome para mostrar**. O nome e o tipo de conexión describen esta conexión. Recomendamos escoller un nome que explique o propósito e o destino da conexión.

1. Escolla quen pode usar esta conexión. Se non realiza ningunha acción, o valor predeterminado será Administradores. Para obter máis información, consulte [Permitir aos colaboradores usar unha conexión para as exportacións](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Insira o seu **[ID de cliente de Google Ads](https://support.google.com/google-ads/answer/1704344)**.

1. Seleccione **Estou de acordo** para confirmar a **Privacidade e cumprimento dos datos**.

1. Seleccione **Autenticarse con Google Ads** e proporcione as súas credenciais de Google Ads.

1. Seleccione **Autoengadirse como usuario de exportación** e proporcione as súas credenciais de Customer Insights.

1. Seleccione **Gardar** para completar a conexión. 

## <a name="configure-an-export"></a>Configurar unha exportación

Pode configurar esta exportación se ten acceso a unha conexión deste tipo. Para obter máis información, consulte [Permisos necesarios para configurar unha exportación](export-destinations.md#set-up-a-new-export).

1. Vaia a **Datos** > **Exportacións**.

1. Seleccione **Engadir destino** para crear unha nova exportación.

1. No campo **Conexión da exportación** escolla unha conexión da sección Google Ads. Se non ve o nome desta sección, non ten ningunha conexión deste tipo dispoñible.

1. Se queres crear unha nova audiencia, deixa o campo de ID de audiencia de Google en branco. Crearemos automaticamente unha nova audiencia na túa conta de Google Ads e utilizaremos o nome do segmento exportado. Se queres actualizar un público de Google Ads existente, introduce o teu [ID de público de Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)

1. No **Correspondencia de datos** sección, seleccione un ou máis campos de datos para exportar e seleccione o campo que representa os campos de datos correspondentes en Customer Insights.

1. Seleccione os segmentos que desexa exportar. 

Ao gardar unha exportación non se executa a exportación inmediatamente.

A exportación execútase con cada [actualización programada](system.md#schedule-tab). 

Tamén pode [exportar datos baixo demanda](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Cumprimento e privacidade dos datos

Cando habilita Dynamics 365 Customer Insights para transmitir datos a Google Ads, permite a transferencia de datos fóra do límite de cumprimento de Dynamics 365 Customer Insights, incluíndo datos potencialmente confidenciais como os datos persoais. Microsoft transferirá estes datos segundo a súa instrución, pero vostede é responsable de garantir que Google Ads cumpra as obrigas de privacidade ou seguridade que poida ter. Para obter máis información, consulte a [Declaración de privacidade de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
O administrador de Dynamics 365 Customer Insights pode eliminar este destino de exportación en calquera momento para interromper o uso desta funcionalidade.


[!INCLUDE [footer-include](includes/footer-banner.md)]
