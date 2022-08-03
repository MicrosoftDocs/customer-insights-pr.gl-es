---
title: Exportar segmentos a Google Ads (versión preliminar)
description: Aprenda a configurar a conexión e exportar a Google Ads.
ms.date: 07/25/2022
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: fd7498ecf17ef8a3a8f22dcc49ae204bef88b47f
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196576"
---
# <a name="export-segments-to-google-ads-preview"></a>Exportar segmentos a Google Ads (versión preliminar)

Exporte segmentos de perfís de clientes unificados a unha lista de público de Google Ads e utilíceos para anunciarse na Busca de Google, Gmail, YouTube e a Rede de visualización de Google.

## <a name="prerequisites"></a>Requisitos previos

- A [Conta de Google Ads](https://ads.google.com/) e as correspondentes credenciais de administrador.
- A [ID de cliente de Google Ads](https://support.google.com/google-ads/answer/1704344).
- Os requisitos do [Política de selección de clientes](https://support.google.com/adspolicy/answer/6299717) se cumpren.
- Os requisitos do [tamaños das listas de remarketing](https://support.google.com/google-ads/answer/7558048) se cumpren.
- [Segmentos configurados](segments.md).
- Os perfís de clientes unificados nos segmentos exportados conteñen campos que representan un enderezo de correo electrónico, teléfono, ID de anunciante móbil, ID de usuario de terceiros ou enderezo.

## <a name="known-limitations"></a>Limitacións coñecidas

- Exporta ata 1 millón de perfís de clientes por exportación a Google Ads, o que pode tardar ata 30 minutos en completarse debido ás limitacións do provedor.
- Só segmentos.
- A coincidencia en Google Ads pode tardar ata 48 horas.

## <a name="set-up-connection-to-google-ads"></a>Configurar conexión a Google Ads

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vaia a **Administrar** > **Conexións**.

1. Seleccione **Engadir conexión** e escolle **Google Ads**.

1. Déalle á conexión un nome recoñecible no campo **Nome para mostrar**. O nome e o tipo de conexión describen esta conexión. Recomendamos escoller un nome que explique o propósito e o destino da conexión.

1. Escolla quen pode usar esta conexión. Por defecto, só son os administradores. Para obter máis información, consulte [Permitir aos colaboradores usar unha conexión para as exportacións](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduce o teu ID de cliente de Google Ads.

1. Revisa o [privacidade e cumprimento dos datos](connections.md#data-privacy-and-compliance) e selecciona **Estou de acordo**.

1. Seleccione **Autenticarse con Google Ads** e proporcione as súas credenciais de Google Ads.

1. Seleccione **Autoengadirse como usuario de exportación** e proporcione as súas credenciais de Customer Insights.

1. Seleccione **Gardar** para completar a conexión.

## <a name="configure-an-export"></a>Configurar unha exportación

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vaia a **Datos** > **Exportacións**.

1. Seleccione **Engadir exportación**.

1. No campo **Conexión da exportación** escolla unha conexión da sección Google Ads. Póñase en contacto cun administrador se non hai conexión dispoñible.

1. Introduza un nome para a exportación.

1. Escolle se queres utilizar un público existente ou crear un novo:
   - Para actualizar unha audiencia de Google Ads existente, introduce o teu [ID de público de Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns).
   - Para crear unha nova audiencia, deixa o campo de ID de público de Google en branco. Customer Insights creará automaticamente unha nova audiencia na túa conta de Google Ads e utilizará o nome do segmento exportado.

1. No **Correspondencia de datos** sección, seleccione un ou máis campos de datos para exportar e seleccione o campo que representa os campos de datos correspondentes en Customer Insights.

1. Seleccione os segmentos que desexa exportar.

1. Seleccione **Gardar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
