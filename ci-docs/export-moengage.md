---
title: Exportar segmentos a MoEngage
description: Aprende a configurar a conexión e a exportar a MoEngage.
ms.date: 07/26/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ffc591c01a5a9434cde41f2da25fa930a515b8c1
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 07/27/2022
ms.locfileid: "9199186"
---
# <a name="export-segments-to-moengage-preview"></a>Exportar segmentos a MoEngage (vista previa)

Exporta segmentos de perfís de clientes unificados a MoEngage e utilízaos para marketing por correo electrónico en MoEngage.

## <a name="prerequisites-for-a-connection"></a>Requisitos previos para unha conexión

- [Conta MoEngage](https://www.moengage.com/) e as correspondentes credenciais de administrador.
- Clave API de MoEngage desde Configuración > API en MoEngage.
- [Segmentos configurados](segments.md) en Customer Insights.

## <a name="known-limitations"></a>Limitacións coñecidas

- Ata 100.000 perfís de clientes por exportación a MoEngage, o que pode levar ata 15 minutos. O número de perfís de clientes que pode exportar a MoEngage depende do seu contrato con MoEngage.
- Só segmentos.

## <a name="set-up-connection-to-moengage"></a>Configura a conexión a MoEngage

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vaia a **Administrar** > **Conexións**.

1. Seleccione **Engadir conexión** e escolle **MoEngage** para configurar a conexión.

1. Déalle á conexión un nome recoñecible no campo **Nome para mostrar**. O nome e o tipo de conexión describen esta conexión. Recomendamos escoller un nome que explique o propósito e o destino da conexión.

1. Escolla quen pode usar esta conexión. Se non realiza ningunha acción, o valor predeterminado será Administradores. Para obter máis información, consulte [Permitir aos colaboradores usar unha conexión para as exportacións](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduce o teu [ID de API de MoEngage Data e clave de API](https://developers.moengage.com/hc/articles/4404674776724-Overview#:~:text=Navigate%20to%20Settings%20%3E%20APIs%20%3E%20DATA,ID%20Password%20%2D%20DATA%20API%20KEY).

1. Revisa o [privacidade e cumprimento dos datos](connections.md#data-privacy-and-compliance) e selecciona **Estou de acordo**.

1. Seleccione **Conectar** para inicializar a conexión a MoEngage.

1. Seleccione **Autoengadirse como usuario de exportación** e proporcione as súas credenciais de Customer Insights.

1. Seleccione **Gardar** para completar a conexión.

## <a name="configure-an-export"></a>Configurar unha exportación

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vaia a **Datos** > **Exportacións**.

1. Seleccione **Engadir exportación** para crear unha nova exportación.

1. No **Conexión para exportación** campo, escolla unha conexión na sección MoEngage. Se non ve o nome desta sección, non hai conexións deste tipo dispoñibles para vostede.

1. Na sección **Coincidencia de datos** do campo **Correo electrónico**, seleccione o campo que representa o enderezo de correo electrónico dun cliente. Repita os mesmos pasos para outros campos opcionais.

1. Seleccione os segmentos que desexa exportar. Crearemos un ou máis segmentos co mesmo nome que os segmentos seleccionados en MoEngage baixo **Segmentos** > **Segmentos personalizados**.

1. Seleccione **Gardar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
