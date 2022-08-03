---
title: Exportar segmentos a Iterable (vista previa)
description: Aprende a configurar a conexión e a exportar a Iterable.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ccf10b6e3a28a75f9d1bd3d8da3bf870ebc2b1b2
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195427"
---
# <a name="export-segments-to-iterable-preview"></a>Exportar segmentos a Iterable (vista previa)

Exporta segmentos de perfís de clientes unificados a Iterable e utilízaos para actividades de mercadotecnia.

## <a name="prerequisites"></a>Requisitos previos

- An [Conta iterable](https://iterable.com/) e as correspondentes credenciais de administrador.
- An [Clave API iterable](https://support.iterable.com/hc/en-us/articles/360043464871)
- [Segmentos configurados](segments.md) en Customer Insights.
- Os perfís de clientes unificados nos segmentos exportados conteñen un campo que representa un enderezo de correo electrónico.

## <a name="known-limitations"></a>Limitacións coñecidas

- Ata 1 millón de perfís de clientes para Iterable, o que pode tardar ata 30 minutos en completarse. O número de perfís de clientes que pode exportar a Iterable depende do seu contrato con Iterable.
- Só segmentos.

## <a name="set-up-connection-to-iterable"></a>Configura a conexión a Iterable

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vaia a **Administrar** > **Conexións**.

1. Seleccione **Engadir conexión** e escolle **Iterable**.

1. Déalle á conexión un nome recoñecible no campo **Nome para mostrar**. O nome e o tipo de conexión describen esta conexión. Recomendamos escoller un nome que explique o propósito e o destino da conexión.

1. Escolla quen pode usar esta conexión. Por defecto, só son os administradores. Para obter máis información, consulte [Permitir aos colaboradores usar unha conexión para as exportacións](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Proporciona a túa clave de API iterable para continuar iniciando sesión.

1. Revisa o [privacidade e cumprimento dos datos](connections.md#data-privacy-and-compliance) e selecciona **Estou de acordo**.

1. Seleccione **Conectar** para inicializar a conexión.

1. Seleccione **Autoengadirse como usuario de exportación** e proporcione as súas credenciais de Customer Insights.

1. Seleccione **Gardar** para completar a conexión.

## <a name="configure-an-export"></a>Configurar unha exportación

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vaia a **Datos** > **Exportacións**.

1. Seleccione **Engadir exportación**.

1. No **Conexión para exportación** campo, escolla unha conexión na sección Iterable. Póñase en contacto cun administrador se non hai conexión dispoñible.

1. Introduza un nome para a exportación.

1. Na sección **Coincidencia de datos** do campo **Correo electrónico**, seleccione o campo que representa o enderezo de correo electrónico dun cliente. A lista creada en Iterable recibirá exactamente o mesmo nome que o nome do seu segmento Dynamics 365 Customer Insights.

1. Seleccione os segmentos que desexa exportar.

1. Seleccione **Gardar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
