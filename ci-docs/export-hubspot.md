---
title: Exporta datos de Customer Insights a HubSpot
description: Obtén información sobre como configurar a conexión e exportar a HubSpot.
ms.date: 09/23/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b34f1d54fa499f6c6b80fa547a8aaf61af3b35a1
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725352"
---
# <a name="export-segments-to-hubspot-preview"></a>Exportar segmentos a HubSpot (vista previa)

Exporta segmentos de perfís de clientes unificados a HubSpot e utilízaos para marketing por correo electrónico.

## <a name="prerequisites-for-a-connection"></a>Requisitos previos para unha conexión

- A [Conta HubSpot](https://www.hubspot.com/) e as correspondentes credenciais de administrador.
- [Chave API](https://knowledge.hubspot.com/Integrations/How-do-I-get-my-HubSpot-API-key) de HubSpot.
- [Segmentos configurados](segments.md) en Customer Insights.

## <a name="known-limitations"></a>Limitacións coñecidas

- A ligazón privada en combinación con Trae o teu propio almacenamento (BYOS) non é compatible.
- Ata 100.000 perfís de clientes por exportación a HubSpot, o que pode levar ata 15 minutos en completarse. O número de perfís de clientes que pode exportar a HubSpot depende e está limitado do seu contrato con HubSpot.
- Só segmentos.

## <a name="set-up-connection-to-hubspot"></a>Configura a conexión a HubSpot

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vaia a **Administrar** > **Conexións**.

1. Seleccione **Engadir conexión** e escolle **HubSpot** para configurar a conexión.

1. Déalle á conexión un nome recoñecible no campo **Nome para mostrar**. O nome e o tipo de conexión describen esta conexión. Recomendamos escoller un nome que explique o propósito e o destino da conexión.

1. Escolla quen pode usar esta conexión. Se non realiza ningunha acción, o valor predeterminado será Administradores. Para obter máis información, consulte [Permitir aos colaboradores usar unha conexión para as exportacións](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduza as súas credenciais de HubSpot cando se lle solicite.

1. Revisa o [privacidade e cumprimento dos datos](connections.md#data-privacy-and-compliance) e selecciona **Estou de acordo**.

1. Seleccione **Conectar** para inicializar a conexión a HubSpot.

1. Seleccione **Autoengadirse como usuario de exportación** e proporcione as súas credenciais de Customer Insights.

1. Seleccione **Gardar** para completar a conexión.

## <a name="configure-an-export"></a>Configurar unha exportación

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vaia a **Datos** > **Exportacións**.

1. Seleccione **Engadir exportación** para crear unha nova exportación.

1. No **Conexión para exportación** campo, escolla unha conexión na sección HubSpot. Se non ve o nome desta sección, non hai conexións deste tipo dispoñibles para vostede.

1. Na sección **Coincidencia de datos** do campo **Correo electrónico**, seleccione o campo que representa o enderezo de correo electrónico dun cliente. Repita os mesmos pasos para outros campos opcionais.

1. Seleccione os segmentos que desexa exportar.

1. Seleccione **Gardar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
