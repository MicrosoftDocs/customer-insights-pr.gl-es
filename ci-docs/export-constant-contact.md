---
title: Exportar segmentos a Constant Contact (versión preliminar)
description: Aprenda a configurar a conexión e exportar a Constant Contact.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c0affd3ed45f462696850813bd50331061dde780
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724499"
---
# <a name="export-segments-to-constant-contact-preview"></a>Exportar segmentos a Constant Contact (versión preliminar)

Exporte segmentos de perfís de clientes unificados a Constant Contact e utilíceos para actividades de mercadotecnia.

## <a name="prerequisites"></a>Requisitos previos

- A [Conta de Contacto constante](https://www.constantcontact.com/account-home) e as correspondentes credenciais de administrador.
- A [ID da lista de contactos constante](https://app.constantcontact.com/pages/contacts/ui#lists). Abra unha lista en Constant Contact para atopar o ID da lista no URL.
- [Segmentos configurados](segments.md) en Customer Insights.
- Os perfís de clientes unificados nos segmentos exportados conteñen un campo que representa un enderezo de correo electrónico.

## <a name="known-limitations"></a>Limitacións coñecidas

- A ligazón privada en combinación con Trae o teu propio almacenamento (BYOS) non é compatible.
- Ata 1 millón de perfís de clientes por exportación a Constant Contact, que pode tardar ata unha hora en completarse. O número de perfís de clientes que pode exportar a Constant Contact depende do seu contrato con Constant Contact.
- Só segmentos.

## <a name="set-up-connection-to-constant-contact"></a>Configurar a conexión a Constant Contact

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vaia a **Administrar** > **Conexións**.

1. Seleccione **Engadir conexión** e escolle **Contacto constante**.

1. Déalle á conexión un nome recoñecible no campo **Nome para mostrar**. O nome e o tipo de conexión describen esta conexión. Recomendamos escoller un nome que explique o propósito e o destino da conexión.

1. Escolla quen pode usar esta conexión. Por defecto, só son os administradores. Para obter máis información, consulte [Permitir aos colaboradores usar unha conexión para as exportacións](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Revisa o [privacidade e cumprimento dos datos](connections.md#data-privacy-and-compliance) e selecciona **Estou de acordo**.

1. Seleccione **Conectar** para inicializar a conexión.

1. Seleccione **Autenticar con Constant Contact** e proporcione as súas credenciais de administrador de Constant Contact.

1. Seleccione **Autoengadirse como usuario de exportación** e proporcione as súas credenciais de Customer Insights.

1. Seleccione **Gardar** para completar a conexión.

## <a name="configure-an-export"></a>Configurar unha exportación

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vaia a **Datos** > **Exportacións**.

1. Seleccione **Engadir exportación**.

1. No campo **Conexión da exportación** escolla unha conexión da sección Constant Contact. Póñase en contacto cun administrador se non hai conexión dispoñible.

1. Introduza un nome para a exportación.

1. Introduce o teu **ID da lista de contactos constante**.

1. Na sección **Coincidencia de datos** do campo **Correo electrónico**, seleccione o campo que representa o enderezo de correo electrónico dun cliente.

1. Opcionalmente, exportar **nome** e **apelidos** como campos adicionais para crear correos electrónicos máis personalizados. Seleccione **Engadir atributo** para asignar estes campos.

1. Seleccione os segmentos que desexa exportar.

1. Seleccione **Gardar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
