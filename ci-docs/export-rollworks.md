---
title: Exportar segmentos a RollWorks (versión preliminar)
description: Aprenda a configurar a conexión e exportar a RollWorks.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e13aeca4ee5309f85e7de2986cd1a2ba5d2992fb
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195610"
---
# <a name="export-segments-to-rollworks-preview"></a>Exportar segmentos a RollWorks (versión preliminar)

Exporte segmentos de perfís de clientes unificados a RollWorks e utilíceos para a publicidade.

## <a name="prerequisites"></a>Requisitos previos

- A [Conta RollWorks](https://www.rollworks.com/) e as correspondentes credenciais de administrador.
- A [ID de anunciante de RollWorks](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).
- [Segmentos configurados](segments.md) en Customer Insights.
- Os perfís de clientes unificados nos segmentos exportados conteñen un campo que representa un enderezo de correo electrónico.

## <a name="known-limitations"></a>Limitacións coñecidas

- Ata 250.000 perfís de clientes por exportación a RollWorks, o que pode levar ata 10 minutos en completarse. O número de perfís de clientes que pode exportar a RollWorks depende do seu contrato con RollWorks.
- Só segmentos.

## <a name="set-up-connection-to-rollworks"></a>Configurar conexión a RollWorks

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vaia a **Administrar** > **Conexións**.

1. Seleccione **Engadir conexión** e escolle **RollWorks**.

1. Déalle á conexión un nome recoñecible no campo **Nome para mostrar**. O nome e o tipo de conexión describen esta conexión. Recomendamos escoller un nome que explique o propósito e o destino da conexión.

1. Escolla quen pode usar esta conexión.  Por defecto, só son os administradores. Para obter máis información, consulte [Permitir aos colaboradores usar unha conexión para as exportacións](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Revisa o [privacidade e cumprimento dos datos](connections.md#data-privacy-and-compliance) e selecciona **Estou de acordo**.

1. Seleccione **Conectar** para inicializar a conexión.

1. Seleccione **Autenticarse con RollWorks** e proporcione as súas credenciais de administrador de RollWorks.

1. Seleccione **Autoengadirse como usuario de exportación** e proporcione as súas credenciais de Customer Insights.

1. Seleccione **Gardar** para completar a conexión.

## <a name="configure-an-export"></a>Configurar unha exportación

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vaia a **Datos** > **Exportacións**.

1. Seleccione **Engadir exportación**.

1. No campo **Conexión da exportación** escolla unha conexión da sección RollWorks. Póñase en contacto cun administrador se non hai conexión dispoñible.

1. Introduza un nome para a exportación.

1. Introduce o teu **ID de anunciante de RollWorks**.

1. Na sección **Coincidencia de datos** do campo **Correo electrónico**, seleccione o campo que representa o enderezo de correo electrónico dun cliente.

1. Seleccione os segmentos que desexa exportar.

1. Seleccione **Gardar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
