---
title: Exportar segmentos a LinkedIn Ads (versión preliminar)
description: Aprenda a configurar a conexión e exportar a LinkedIn Ads.
ms.date: 08/12/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 4c3928e05db0ebda262b4ad3e928ce85f70035b9
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304701"
---
# <a name="export-segments-to-linkedin-ads-preview"></a>Exportar segmentos a LinkedIn Ads (versión preliminar)

Exporte segmentos de perfís de clientes unificados a LinkedIn Ads para crear públicos coincidentes. Utilice os públicos coincidentes para dirixirse ás empresas e aos contactos.

## <a name="prerequisites"></a>Requisitos previos

- A [LinkedIn Campaign Manager conta](https://business.linkedin.com/marketing-solutions/ads) e as correspondentes credenciais de administrador.
- A [LinkedIn Campaign Manager ID da conta](https://www.linkedin.com/help/lms/answer/a424270).
- [Segmentos configurados](segments.md) en Customer Insights.
- Os segmentos exportados necesitan polo menos un campo específico dependendo de se escolla [orientación de contactos](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) ou [orientación da empresa](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) en LinkedIn. Os campos posibles están listados no **Correspondencia de datos** paso cando [configurando a exportación](#configure-an-export).

## <a name="known-limitations"></a>Limitacións coñecidas

- Ata 100.000 perfís de clientes por exportación a LinkedIn Ads, o que pode tardar ata 10 minutos en completarse.
- Só segmentos. Un segmento debe conter polo menos 300 perfís únicos.

## <a name="set-up-connection-to-linkedin-ads"></a>Configura a conexión con LinkedIn Ads

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vaia a **Administrar** > **Conexións**.

1. Seleccione **Engadir conexión** e escolle **Anuncios de LinkedIn**.

1. Déalle á conexión un nome recoñecible no campo **Nome para mostrar**. O nome e o tipo de conexión describen esta conexión. Recomendamos escoller un nome que explique o propósito e o destino da conexión.

1. Escolla quen pode usar esta conexión. Por defecto, só son os administradores. Para obter máis información, consulte [Permitir aos colaboradores usar unha conexión para as exportacións](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Proporciona o teu LinkedIn Campaign Manager ID da conta.

1. Revisa o [privacidade e cumprimento dos datos](connections.md#data-privacy-and-compliance) e selecciona **Estou de acordo**.

1. Seleccione **Conectar** para inicializar a conexión.

1. Seleccione **Autenticarse con LinkedIn** e proporcione as súas credenciais de administrador de LinkedIn Campaign Manager.

1. Seleccione **Autoengadirse como usuario de exportación** e proporcione as súas credenciais de Customer Insights.

1. Seleccione **Gardar** para completar a conexión.

## <a name="configure-an-export"></a>Configurar unha exportación

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vaia a **Datos** > **Exportacións**.

1. Seleccione **Engadir exportación**.

1. No campo **Conexión da exportación**, escolla unha conexión da sección LinkedIn Ads. Póñase en contacto cun administrador se non hai conexión dispoñible.

1. Introduza un nome para a exportación.

1. Escolla se quere exportar datos para [dirixirse aos contactos](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) ou [dirixirse ás empresas](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) en LinkedIn.

1. Na sección **Coincidencia de datos**, para a orientación por contactos, seleccione polo menos un campo que represente un enderezo de correo electrónico dun cliente, Apple Ad ID, Google Ad ID, Google User ID ou nome e apelidos. Se escolle a orientación por empresa, seleccione polo menos un campo que represente un nome de empresa, dominio de correo electrónico, URL da páxina de LinkedIn, símbolo de acción ou sitio web.

1. Opcionalmente, engade campos para definir aínda máis a súa exportación. Seleccione **Engadir atributo** para asignar estes campos.

1. Seleccione os segmentos que desexa exportar. Os públicos coincidentes en LinkedIn Campaign Manager crearanse automaticamente co nome dos segmentos que seleccionou para exportar. Cada segmento dará lugar a un público coincidente diferente.

1. Seleccione **Gardar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
