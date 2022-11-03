---
title: Exportar segmentos a Autopilot (versión preliminar)
description: Aprenda a configurar a conexión e exportar a Autopilot.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b4b14ba9de2c7e20175fac664a705f2212a411fd
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724755"
---
# <a name="export-segments-to-autopilot-preview"></a>Exportar segmentos a Autopilot (versión preliminar)

Exporte segmentos de perfís de clientes unificados a Autopilot e utilíceos para campañas e mercadotecnia por correo electrónico en Autopilot.

## <a name="prerequisites-for-a-connection"></a>Requisitos previos para unha conexión

- An [Conta de piloto automático](https://www.autopilothq.com/) e as correspondentes credenciais de administrador.
- An [Chave da API de piloto automático](https://autopilot.docs.apiary.io/#)
- [Segmentos configurados](segments.md) en Customer Insights.
- Os perfís de clientes unificados nos segmentos exportados conteñen un campo que representa un enderezo de correo electrónico.

## <a name="known-limitations"></a>Limitacións coñecidas

- A ligazón privada en combinación con Trae o teu propio almacenamento (BYOS) non é compatible.
- Ata 100.000 perfís de clientes por exportación a Autopilot, o que pode tardar ata unhas horas en completarse. O número de perfís de clientes que pode exportar a Autopilot depende do seu contrato con Autopilot.
- Só segmentos.

## <a name="set-up-connection-to-autopilot"></a>Configurar conexión a Autopilot

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vaia a **Administrar** > **Conexións**.

1. Seleccione **Engadir conexión** e escolle **Piloto automático**.

1. Déalle á conexión un nome recoñecible no campo **Nome para mostrar**. O nome e o tipo de conexión describen esta conexión. Recomendamos escoller un nome que explique o propósito e o destino da conexión.

1. Escolla quen pode usar esta conexión. Por defecto, só son os administradores. Para obter máis información, consulte [Permitir aos colaboradores usar unha conexión para as exportacións](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduza a súa Clave da API de Autopilot.

1. Revisa o [privacidade e cumprimento dos datos](connections.md#data-privacy-and-compliance) e selecciona **Estou de acordo**.

1. Seleccione **Conectar** para inicializar a conexión.

1. Seleccione **Autoengadirse como usuario de exportación** e proporcione as súas credenciais de Customer Insights.

1. Seleccione **Gardar** para completar a conexión.

## <a name="configure-an-export"></a>Configurar unha exportación

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vaia a **Datos** > **Exportacións**.

1. Seleccione **Engadir exportación**.

1. No campo **Conexión da exportación** escolla unha conexión da sección Autopilot. Póñase en contacto cun administrador se non hai conexión dispoñible.

1. Introduza un nome para a exportación.

1. Na sección **Coincidencia de datos** do campo **Correo electrónico**, seleccione o campo que representa o enderezo de correo electrónico dun cliente.

1. Opcionalmente, exporta outros campos como **nome** e **apelidos**.

1. Seleccione os segmentos que quere exportar cumprindo as limitacións coñecidas.

1. Seleccione **Gardar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
