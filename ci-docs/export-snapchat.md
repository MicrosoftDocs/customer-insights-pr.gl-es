---
title: Exportar segmentos a Snapchat (versión preliminar)
description: Aprenda a configurar a conexión e exportar a Snapchat.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 85443dcb54ebd58182997fbb56a738901f2a051f
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195380"
---
# <a name="export-segments-to-snapchat-preview"></a>Exportar segmentos a Snapchat (versión preliminar)

Exporte segmentos de perfís de clientes unificados a Snapchat e utilíceos para a publicidade.

## <a name="prerequisites"></a>Requisitos previos

- A [Conta de empresa de Snapchat](https://business.snapchat.com/), a [Conta de anuncios de Snapchat](https://ads.snapchat.com/), e as correspondentes credenciais de administrador. Debes polo menos ser membro dunha conta de organización e xestor de datos dunha conta de anuncios específica.
- Polo menos unha audiencia en Snapchat Audience Manager do tipo SAM (Snap Audience Match).
- O [Segmento de Snapchat/ID de audiencia](https://businesshelp.snapchat.com/s/article/custom-audiences). O ID da audiencia pódese atopar no URL despois de seleccionar a audiencia en Snapchat Audience Manager.
- [Segmentos configurados](segments.md) en Customer Insights.
- Os perfís de clientes unificados nos segmentos exportados conteñen un campo que representa un enderezo de correo electrónico.

## <a name="known-limitations"></a>Limitacións coñecidas

- Ata 1 millón de perfís de clientes, que poden tardar ata 15 minutos en completarse.
- Só segmentos.

## <a name="set-up-connection-to-snapchat"></a>Configurar conexión a Snapchat

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vaia a **Administrar** > **Conexións**.

1. Seleccione **Engadir conexión** e escolle **Snapchat**.

1. Déalle á conexión un nome recoñecible no campo **Nome para mostrar**. O nome e o tipo de conexión describen esta conexión. Recomendamos escoller un nome que explique o propósito e o destino da conexión.

1. Escolla quen pode usar esta conexión. Por defecto, só son os administradores. Para obter máis información, consulte [Permitir aos colaboradores usar unha conexión para as exportacións](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Revisa o [privacidade e cumprimento dos datos](connections.md#data-privacy-and-compliance) e selecciona **Estou de acordo**.

1. Seleccione **Conectar** para inicializar a conexión.

1. Seleccione **Autenticarse con Snapchat** e proporcione as súas credenciais de administrador de Snapchat.

1. Seleccione **Autoengadirse como usuario de exportación** e proporcione as súas credenciais de Customer Insights.

1. Seleccione **Gardar** para completar a conexión.

## <a name="configure-an-export"></a>Configurar unha exportación

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vaia a **Datos** > **Exportacións**.

1. Seleccione **Engadir exportación**.

1. No campo **Conexión da exportación** escolla unha conexión da sección Snapchat. Póñase en contacto cun administrador se non hai conexión dispoñible.

1. Introduza un nome para a exportación.

1. Introduza o **Segmento de Snapchat/ID de audiencia**.

1. Na sección **Coincidencia de datos** do campo **Correo electrónico**, seleccione o campo que representa o enderezo de correo electrónico dun cliente.

1. Seleccione os segmentos que desexa exportar.

1. Seleccione **Gardar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
