---
title: Exportar segmentos a ActiveCampaign
description: Aprenda a configurar a conexión e exportar a ActiveCampaign.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 178d2df8edf1abcec72664e19d73a88f2b97f12d
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195564"
---
# <a name="export-segments-to-activecampaign-preview"></a>Exportar segmentos a ActiveCampaign (versión preliminar)

Exporte segmentos de perfís de clientes unificados a ActiveCampaign e utilíceos para actividades de mercadotecnia.

## <a name="prerequisites"></a>Requisitos previos

- An [Conta de ActiveCampaign](https://www.activecampaign.com/) e as correspondentes credenciais de administrador.
- An [ID da lista de ActiveCampaign](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).
- An [Clave da API de ActiveCampaign](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key) e REST Endpoint Hostname.
- [Segmentos configurados](segments.md) en Customer Insights.
- Os perfís de clientes unificados nos segmentos exportados conteñen un campo que representa un enderezo de correo electrónico.

## <a name="known-limitations"></a>Limitacións coñecidas

- Ata 1 millón de perfís de clientes por exportación a ActiveCampaign, que pode tardar ata 90 minutos en completarse. O número de perfís de clientes que pode exportar a ActiveCampaign depende do seu contrato con ActiveCampaign.
- Só segmentos.

## <a name="set-up-connection-to-activecampaign"></a>Configurar conexión a ActiveCampaign

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vaia a **Administrar** > **Conexións**.

1. Seleccione **Engadir conexión** e escolle **ActiveCampaign**.

1. Déalle á conexión un nome recoñecible no campo **Nome para mostrar**. O nome e o tipo de conexión describen esta conexión. Recomendamos escoller un nome que explique o propósito e o destino da conexión.

1. Escolla quen pode usar esta conexión. Por defecto, só son os administradores. Para obter máis información, consulte [Permitir aos colaboradores usar unha conexión para as exportacións](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduza a súa Clave da API de ActiveCampaign e o nome de servidor do extremo de REST. O nome do servidor do extremo de REST é só o nome do servidor, sen https://.

1. Revisa o [privacidade e cumprimento dos datos](connections.md#data-privacy-and-compliance) e selecciona **Estou de acordo**.

1. Seleccione **Conectar** para inicializar a conexión.

1. Seleccione **Autoengadirse como usuario de exportación** e proporcione as súas credenciais de Customer Insights.

1. Seleccione **Gardar** para completar a conexión.

## <a name="configure-an-export"></a>Configurar unha exportación

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vaia a **Datos** > **Exportacións**.

1. Seleccione **Engadir exportación**.

1. No campo **Conexión para a exportación**, escolla unha conexión na sección ActiveCampaign. Póñase en contacto cun administrador se non hai conexión dispoñible.

1. Introduza un nome para a exportación.

1. Introduce o teu **ID da lista de ActiveCampaign**.

1. Na sección **Coincidencia de datos** do campo **Correo electrónico**, seleccione o campo que representa o enderezo de correo electrónico dun cliente.

1. Opcionalmente, exportar **nome**, **·**, e **Teléfono** para crear correos electrónicos máis personalizados. Seleccione **Engadir atributo** para asignar estes campos.

1. Seleccione os segmentos que desexa exportar.

1. Seleccione **Gardar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
