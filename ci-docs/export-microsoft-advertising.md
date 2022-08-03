---
title: Exportar segmentos a Microsoft Advertising (versión preliminar)
description: Aprenda a configurar a conexión e exportar a Microsoft Advertising.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 44217e7823ffbe14d232b3e33de1b4ea6ed69dcf
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196530"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a>Exportar segmentos a Microsoft Advertising (versión preliminar)

Exporte segmentos de Customer Insights a Microsoft Advertising para crear públicos de Coincidencia de clientes. Use estes públicos para as súas campañas publicitarias.

## <a name="prerequisites"></a>Requisitos previos

- A [Conta de Microsoft Advertising](https://ads.microsoft.com/) e as correspondentes credenciais de administrador.
- ID de cliente e ID de conta de Microsoft Advertising. Atopar o ID do cliente (`cid`) e ID da conta (`aid`) nos parámetros do URL cando inicia sesión en Microsoft Advertising.
- Acéptanse as condicións de uso de Customer Match.
- [Segmentos configurados](segments.md) en Customer Insights.
- Os perfís de clientes unificados nos segmentos exportados conteñen un campo que representa un enderezo de correo electrónico.

## <a name="known-limitations"></a>Limitacións coñecidas

- Ata 500.000 perfís de clientes por exportación a Microsoft Advertising, o que pode levar ata 10 minutos.
- Só segmentos.

## <a name="set-up-connection-to-microsoft-advertising"></a>Configura a conexión con Microsoft Advertising

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vaia a **Administrar** > **Conexións**.

1. Seleccione **Engadir conexión** e escolle **Microsoft Advertising**.

1. Déalle á conexión un nome recoñecible no campo **Nome para mostrar**. O nome e o tipo de conexión describen esta conexión. Recomendamos escoller un nome que explique o propósito e o destino da conexión.

1. Escolla quen pode usar esta conexión. A opción predefinida é administradores. Para obter máis información, consulte [Permitir aos colaboradores usar unha conexión para as exportacións](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduza o **ID de cliente de Microsoft Advertising**.

1. Revisa o [privacidade e cumprimento dos datos](connections.md#data-privacy-and-compliance) e selecciona **Estou de acordo**.

1. Seleccione **Conectar** para inicializar a conexión.

1. Seleccione **Autenticarse con Microsoft Advertising** e proporcione as súas credenciais de administrador de Microsoft Advertising.

1. Seleccione **Autoengadirse como usuario de exportación** e proporcione as súas credenciais de Customer Insights.

1. Seleccione **Gardar** para completar a conexión.

## <a name="configure-an-export"></a>Configurar unha exportación

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vaia a **Datos** > **Exportacións**.

1. Seleccione **Engadir exportación**.

1. No campo **Conexión da exportación** escolla unha conexión da sección Microsoft Advertising. Póñase en contacto cun administrador se non hai conexión dispoñible.

1. Introduza un nome para a exportación.

1. Seleccione os segmentos que se van exportar. Os públicos de Coincidencia de clientes en Microsoft Advertising créanse automaticamente co nome dos segmentos seleccionados para a exportación. Cada segmento dará lugar a un público separado de Coincidencia de clientes.

1. Introduza os seus **ID de cliente e conta de Microsoft Advertising**.

1. Na sección **Coincidencia de datos** do campo **Correo electrónico**, seleccione o campo cun enderezo de correo electrónico dun cliente.

1. Seleccione **Gardar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
