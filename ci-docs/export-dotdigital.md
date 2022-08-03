---
title: Exportar segmentos a DotDigital (versión preliminar)
description: Aprenda a configurar a conexión e exportar a DotDigital.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: cabaea84e31f8fe97bc558a8dca8d93bc40f43b7
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196070"
---
# <a name="export-segments-to-dotdigital-preview"></a>Exportar segmentos a DotDigital (versión preliminar)

Exporte segmentos de perfís de clientes unificados a axendas de enderezos de DotDigital e utilíceos para campañas, mercadotecnia por correo electrónico e para crear segmentos de clientes con DotDigital.

## <a name="prerequisites"></a>Requisitos previos

- A [Conta DotDigital](https://dotdigital.com/) e un [Usuario da API](https://support.dotdigital.com/hc/articles/115001718730-How-do-I-create-an-API-user).
- Un ID de DotDigital de a [novo](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book) ou a axenda de enderezos existente en DotDigital. A identificación pódese atopar na URL cando selecciona e abre unha axenda de enderezos.
- [Segmentos configurados](segments.md) en Customer Insights.
- Os perfís de clientes unificados nos segmentos exportados conteñen un campo que representa un enderezo de correo electrónico.

## <a name="known-limitations"></a>Limitacións coñecidas

- Ata 1 millón de perfís de clientes por exportación a DotDigital, o que pode levar ata tres horas en completarse debido ás limitacións do provedor. O número de perfís de clientes que pode exportar a DotDigital depende do seu contrato con DotDigital.
- Só segmentos.

## <a name="set-up-connection-to-dotdigital"></a>Configurar conexión a DotDigital

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vaia a **Administrar** > **Conexións**.

1. Seleccione **Engadir conexión** e escolle **DotDigital**.

1. Déalle á conexión un nome recoñecible no campo **Nome para mostrar**. O nome e o tipo de conexión describen esta conexión. Recomendamos escoller un nome que explique o propósito e o destino da conexión.

1. Escolla quen pode usar esta conexión. Por defecto, só son os administradores. Para obter máis información, consulte [Permitir aos colaboradores usar unha conexión para as exportacións](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Escriba o seu **nome de usuario e contrasinal da API de DotDigital**.

1. Introduce o teu **ID da axenda de enderezos de DotDigital**.

1. Revisa o [privacidade e cumprimento dos datos](connections.md#data-privacy-and-compliance) e selecciona **Estou de acordo**.

1. Seleccione **Conectar** para inicializar a conexión.

1. Seleccione **Autoengadirse como usuario de exportación** e proporcione as súas credenciais de Customer Insights.

1. Seleccione **Gardar** para completar a conexión.

## <a name="configure-an-export"></a>Configurar unha exportación

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vaia a **Datos** > **Exportacións**.

1. Seleccione **Engadir exportación**.

1. No campo **Conexión da exportación** escolla unha conexión da sección DotDigital. Póñase en contacto cun administrador se non hai conexión dispoñible.

1. Introduza un nome para a exportación.

1. Na sección **Coincidencia de datos** do campo **Correo electrónico**, seleccione o campo que representa o enderezo de correo electrónico dun cliente.

1. Opcionalmente, exportar **nome**, **·**, **completo**, **·**, e **Código postal**.

1. Seleccione os segmentos que desexa exportar.

1. Seleccione **Gardar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

En DotDigital, busca os teus segmentos [Libretas de enderezos DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).

[!INCLUDE [footer-include](includes/footer-banner.md)]
