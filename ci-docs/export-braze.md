---
title: Exportar segmentos a Braze (vista previa)
description: Obtén información sobre como configurar a conexión e exportar a Braze.
ms.date: 10/06/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 2f52eb8196e057f934c8d2b5ac0518ce121606b6
ms.sourcegitcommit: 003c1929f730d7d505c108aba84f6269f4c98978
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 10/12/2022
ms.locfileid: "9655295"
---
# <a name="export-segments-to-braze-preview"></a>Exportar segmentos a Braze (vista previa)

Exporta segmentos de perfís de clientes unificados a Braze e utilízaos para actividades de mercadotecnia.

## <a name="prerequisites"></a>Requisitos previos

- A [Conta Braze](https://www.braze.com/) e as correspondentes credenciais de administrador.
- A [Chave API Braze](https://www.braze.com/docs/api/basics/)
- O teu [Punto final de Braze REST](https://www.braze.com/docs/api/basics/#api-definitions) 
- [Segmentos configurados](segments.md) en Customer Insights.
- Os perfís de clientes unificados nos segmentos exportados conteñen un campo que representa un enderezo de correo electrónico e un ID de cliente Braze.

## <a name="known-limitations"></a>Limitacións coñecidas

- Ata 1 millón de perfís de clientes para Braze, o que pode tardar ata 40 minutos en completarse. O número de perfís de clientes que podes exportar a Braze depende do teu contrato con Braze.
- Só segmentos.
- Azure Private Link non é compatible coa exportación Braze.

## <a name="set-up-connection-to-braze"></a>Configura a conexión con Braze

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vaia a **Administrar** > **Conexións**.

1. Seleccione **Engadir conexión** e escolle **Braze**.

1. Déalle á conexión un nome recoñecible no campo **Nome para mostrar**. O nome e o tipo de conexión describen esta conexión. Recomendamos escoller un nome que explique o propósito e o destino da conexión.

1. Escolla quen pode usar esta conexión. Por defecto, só son os administradores. Para obter máis información, consulte [Permitir aos colaboradores usar unha conexión para as exportacións](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Proporciona a túa chave da API de Braze para continuar iniciando sesión.

1. Revisa o [privacidade e cumprimento dos datos](connections.md#data-privacy-and-compliance) e selecciona **Estou de acordo**.

1. Seleccione **Conectar** para inicializar a conexión.

1. Seleccione **Autoengadirse como usuario de exportación** e proporcione as súas credenciais de Customer Insights.

1. Seleccione **Gardar** para completar a conexión.

## <a name="configure-an-export"></a>Configurar unha exportación

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vaia a **Datos** > **Exportacións**.

1. Seleccione **Engadir exportación**.

1. No **Conexión para exportación** campo, escolla unha conexión na sección Braze. Póñase en contacto cun administrador se non hai conexión dispoñible.

1. Introduza o seu punto final REST no **Nome de host** campo no seguinte formato:`rest.iad-03.braze.com`.

1. Introduza un nome para a exportación.

1. Na sección **Coincidencia de datos** do campo **Correo electrónico**, seleccione o campo que representa o enderezo de correo electrónico dun cliente. No **ID de cliente** campo, seleccione o campo que representa o ID de Braze do cliente. Os segmentos en Braze crearanse co mesmo nome do segmento que en Dynamics 365 Customer Insights. Pode escoller máis campos opcionais para os datos coincidentes.

1. Seleccione as entidades ou segmentos que quere exportar.

1. Seleccione **Gardar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
