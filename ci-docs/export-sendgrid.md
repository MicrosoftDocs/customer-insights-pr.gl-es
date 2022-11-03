---
title: Exportar segmentos a SendGrid (versión preliminar)
description: Aprenda a configurar a conexión e exportar a SendGrid.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 855e77055eeb24a2c6cff0d45cd23edf93cc0581
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724846"
---
# <a name="export-segments-to-sendgrid-preview"></a>Exportar segmentos a SendGrid (versión preliminar)

Exporte segmentos de perfís de clientes unificados a listas de contactos de SendGrid e utilíceos para campañas e mercadotecnia por correo electrónico en SendGrid.

## <a name="prerequisites"></a>Requisitos previos

- A [Conta SendGrid](https://sendgrid.com/) e as correspondentes credenciais de administrador.
- [Listas de contactos existentes en SendGrid](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts) e os DNI correspondentes.
- A [Clave da API de SendGrid](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).
- [Segmentos configurados](segments.md) en Customer Insights.
- Os perfís de clientes unificados nos segmentos exportados conteñen un campo que representa un enderezo de correo electrónico.

## <a name="known-limitations"></a>Limitacións coñecidas

- A ligazón privada en combinación con Trae o teu propio almacenamento (BYOS) non é compatible.
- Ata 100.000 perfís de clientes en total para SendGrid, o que pode tardar ata unhas horas en completarse. O número de perfís de clientes que pode exportar a SendGrid depende do seu contrato con SendGrid.
- Só segmentos.

## <a name="set-up-connection-to-sendgrid"></a>Configurar conexión a SendGrid

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vaia a **Administrar** > **Conexións**.

1. Seleccione **Engadir conexión** e escolle **SendGrid**.

1. Déalle á conexión un nome recoñecible no campo **Nome para mostrar**. O nome e o tipo de conexión describen esta conexión. Recomendamos escoller un nome que explique o propósito e o destino da conexión.

1. Escolla quen pode usar esta conexión. Por defecto, só son os administradores. Para obter máis información, consulte [Permitir aos colaboradores usar unha conexión para as exportacións](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduce o teu **Clave da API de SendGrid**.

1. Revisa o [privacidade e cumprimento dos datos](connections.md#data-privacy-and-compliance) e selecciona **Estou de acordo**.

1. Seleccione **Conectar** para inicializar a conexión.

1. Seleccione **Autoengadirse como usuario de exportación** e proporcione as súas credenciais de Customer Insights.

1. Seleccione **Gardar** para completar a conexión.

## <a name="configure-an-export"></a>Configurar unha exportación

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vaia a **Datos** > **Exportacións**.

1. Seleccione **Engadir exportación**.

1. No campo **Conexión da exportación** escolla unha conexión da sección SendGrid. Póñase en contacto cun administrador se non hai conexión dispoñible.

1. Introduza un nome para a exportación.

1. Introduce o teu **ID da lista SendGrid**.

1. Na sección **Coincidencia de datos** do campo **Correo electrónico**, seleccione o campo que representa o enderezo de correo electrónico dun cliente.

1. Opcionalmente, seleccione campos como **nome**, **·**, **/Rexión**, **·**, **·**, e **Código postal**.

1. Seleccione os segmentos que quere exportar seguindo as limitacións coñecidas.

1. Seleccione **Gardar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
