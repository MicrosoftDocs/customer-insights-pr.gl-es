---
title: Exportar segmentos a Campaign Monitor (versión preliminar)
description: Aprenda a configurar a conexión e exportar a Campaign Monitor.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 82303c7bcb269ee68419c9639ee743e13451f273
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724546"
---
# <a name="export-segments-to-campaign-monitor-preview"></a>Exportar segmentos a Campaign Monitor (versión preliminar)

Exporte segmentos de perfís de clientes unificados a Campaign Monitor e utilíceos para actividades de mercadotecnia.

## <a name="prerequisites"></a>Requisitos previos

- A [Conta de Campaign Monitor](https://www.campaignmonitor.com/) e as correspondentes credenciais de administrador.
- A [ID de lista de monitor de campaña](https://www.campaignmonitor.com/api/getting-started/#your-list-id).
- A [Clave API xerada](https://www.campaignmonitor.com/api/getting-started/) dende **Axustes da conta** en Campaign Monitor para obter o ID da lista de API.
- [Segmentos configurados](segments.md) en Customer Insights.
- Os perfís de clientes unificados nos segmentos exportados conteñen un campo que representa un enderezo de correo electrónico.

## <a name="known-limitations"></a>Limitacións coñecidas

- A ligazón privada en combinación con Trae o teu propio almacenamento (BYOS) non é compatible.
- Ata 1 millón de perfís de clientes por exportación a Campaign Monitor, que pode tardar ata 20 minutos en completarse. O número de perfís de clientes que pode exportar a Campaign Monitor depende do seu contrato con Campaign Monitor.
- Só segmentos.

## <a name="set-up-connection-to-campaign-monitor"></a>Configurar a conexión a Campaign Monitor

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vaia a **Administrar** > **Conexións**.

1. Seleccione **Engadir conexión** e escolle **Monitor de campaña**.

1. Déalle á conexión un nome recoñecible no campo **Nome para mostrar**. O nome e o tipo de conexión describen esta conexión. Recomendamos escoller un nome que explique o propósito e o destino da conexión.

1. Escolla quen pode usar esta conexión. Por defecto, só son os administradores. Para obter máis información, consulte [Permitir aos colaboradores usar unha conexión para as exportacións](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Revisa o [privacidade e cumprimento dos datos](connections.md#data-privacy-and-compliance) e selecciona **Estou de acordo**.

1. Seleccione **Conectar** para iniciar a conexión a Campaign Monitor.

1. Seleccione **Autenticarse con Campaign Monitor** e proporcione as súas credenciais de administrador de Campaign Monitor.

1. Seleccione **Autoengadirse como usuario de exportación** e proporcione as súas credenciais de Customer Insights.

1. Seleccione **Gardar** para completar a conexión.

## <a name="configure-an-export"></a>Configurar unha exportación

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vaia a **Datos** > **Exportacións**.

1. Seleccione **Engadir exportación** para crear unha nova exportación.

1. No campo **Conexión da exportación** escolla unha conexión da sección Campaign Monitor. Póñase en contacto cun administrador se non hai conexión dispoñible.

1. Introduza un nome para a exportación.

1. Introduce o teu **ID de lista de monitor de campaña**.

1. Na sección **Coincidencia de datos** do campo **Correo electrónico**, seleccione o campo que representa o enderezo de correo electrónico dun cliente. É necesario exportar segmentos a Campaign Monitor.

1. Seleccione os segmentos que desexa exportar.

1. Seleccione **Gardar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
