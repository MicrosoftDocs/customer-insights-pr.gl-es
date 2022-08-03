---
title: Exportar segmentos a Mailchimp (versión preliminar)
description: Aprenda a configurar a conexión e exportar a Mailchimp.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 54aec10e24b6356e2e4317cf33e740a1a086a2dd
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196852"
---
# <a name="export-segments-to-mailchimp-preview"></a>Exportar segmentos a Mailchimp (versión preliminar)

Exporte segmentos de perfís de clientes unificados a Mailchimp para crear boletíns e campañas de correo electrónico.

## <a name="prerequisites"></a>Requisitos previos

- A [Conta Mailchimp](https://mailchimp.com/) e as correspondentes credenciais de administrador.
- [Públicos existentes en Mailchimp](https://mailchimp.com/help/create-audience/) e correspondente [ID de audiencia](https://mailchimp.com/help/find-audience-id/).
- [Segmentos configurados](segments.md).
- Os perfís de clientes unificados nos segmentos exportados conteñen un campo que representa un enderezo de correo electrónico.

## <a name="known-limitations"></a>Limitacións coñecidas

- Ata 1 millón de perfís de clientes por exportación a Mailchimp, o que pode levar ata tres horas. O número de perfís de clientes que podes exportar a Mailchimp depende do teu contrato con Mailchimp.
- Só segmentos.

## <a name="set-up-connection-to-mailchimp"></a>Configurar conexión a Mailchimp

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vaia a **Administrar** > **Conexións**.

1. Seleccione **Engadir conexión** e escolle **Mailchimp**.

1. Déalle á conexión un nome recoñecible no campo **Nome para mostrar**. O nome e o tipo de conexión describen esta conexión. Recomendamos escoller un nome que explique o propósito e o destino da conexión.

1. Escolla quen pode usar esta conexión. Por defecto, só son os administradores. Para obter máis información, consulte [Permitir aos colaboradores usar unha conexión para as exportacións](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Revisa o [privacidade e cumprimento dos datos](connections.md#data-privacy-and-compliance) e selecciona **Estou de acordo**.

1. Seleccione **Conectar** para inicializar a conexión.

1. Seleccione **Autenticarse con Mailchimp** e proporcione as súas credenciais de Mailchimp.

1. Seleccione **Autoengadirse como usuario de exportación** e proporcione as súas credenciais de Customer Insights.

1. Seleccione **Gardar** para completar a conexión.

## <a name="configure-an-export"></a>Configurar unha exportación

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vaia a **Datos** > **Exportacións**.

1. Seleccione **Engadir exportación**.

1. No campo **Conexión da exportación** escolla unha conexión da sección Mailchimp. Póñase en contacto cun administrador se non hai conexión dispoñible.

1. Introduza un nome para a exportación.

1. Introduce o teu **ID de audiencia de Mailchimp**.

1. Na sección **Coincidencia de datos** do campo **Correo electrónico**, seleccione o campo que representa o enderezo de correo electrónico dun cliente.

1. Opcionalmente, exportar **nome** e **apelidos** para crear correos electrónicos máis personalizados. Seleccione **Engadir atributo** para asignar estes campos.

1. Seleccione os segmentos que desexa exportar.

1. Seleccione **Gardar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
