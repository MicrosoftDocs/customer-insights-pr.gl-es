---
title: Exportar segmentos a Marketo (versión preliminar)
description: Aprenda a configurar a conexión e exportar a Marketo.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f57cdfbb24df8a8ffa1670b426d50dbba2c5f40f
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195242"
---
# <a name="export-segments-to-marketo-preview"></a>Exportar segmentos a Marketo (versión preliminar)

Exporte os segmentos de perfís de clientes unificados para xerar campañas, proporcionar márketing por correo electrónico e usar grupos específicos de clientes con Marketo.

## <a name="prerequisites"></a>Requisitos previos

- A [Conta Marketo](https://login.marketo.com/) e as correspondentes credenciais de administrador.
- A [ID de cliente de Marketo, segredo do cliente e nome de host do punto final REST](https://developers.marketo.com/rest-api/authentication/).
- [Listas existentes en Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists) e os DNI correspondentes.
- [Segmentos configurados](segments.md).
- Os perfís de clientes unificados nos segmentos exportados conteñen un campo que representa un enderezo de correo electrónico.

## <a name="known-limitations"></a>Limitacións coñecidas

- Ata 1 millón de perfís de clientes por exportación a Marketo, o que pode levar ata 3 horas. O número de perfís de clientes que pode exportar a Marketo depende do seu contrato con Marketo.
- Só segmentos.

## <a name="set-up-connection-to-marketo"></a>Configurar conexión a Marketo

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vaia a **Administrar** > **Conexións**.

1. Seleccione **Engadir conexión** e escolle **Mercado**.

1. Déalle á conexión un nome recoñecible no campo **Nome para mostrar**. O nome e o tipo de conexión describen esta conexión. Recomendamos escoller un nome que explique o propósito e o destino da conexión.

1. Escolla quen pode usar esta conexión. Por defecto, só son os administradores. Para obter máis información, consulte [Permitir aos colaboradores usar unha conexión para as exportacións](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduce o teu **ID de cliente de Marketo, segredo do cliente e nome de host do punto final REST**. O nome do servidor do extremo de REST é só o nome do servidor, sen https://. Exemplo: xyz-abc-123.mktorest.com.

1. Revisa o [privacidade e cumprimento dos datos](connections.md#data-privacy-and-compliance) e selecciona **Estou de acordo**.

1. Seleccione **Conectar** para inicializar a conexión.

1. Seleccione **Autoengadirse como usuario de exportación** e proporcione as súas credenciais de Customer Insights.

1. Seleccione **Gardar** para completar a conexión.

## <a name="configure-an-export"></a>Configurar unha exportación

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vaia a **Datos** > **Exportacións**.

1. Seleccione **Engadir exportación**.

1. No campo **Conexión da exportación** escolla unha conexión da sección Marketo. Póñase en contacto cun administrador se non hai conexión dispoñible.

1. Introduza un nome para a exportación.

1. Introduce o teu **ID da lista de Marketo**. O ID da lista é un valor unicamente numérico. Por exemplo, se o seu ID de lista de Marketo é ST12345A7, elimine o carácter antes e despois dos números e introduza *12345*.

1. No **Correspondencia de datos** sección, seleccione polo menos un campo que represente o enderezo de correo electrónico dun cliente ou o ID de Marketo dun cliente.

1. Opcionalmente, exportar **nome**, **·**, **·**, **·**, e **País/Rexión** para crear correos electrónicos máis personalizados. Seleccione **Engadir atributo** para asignar estes campos.

1. Seleccione os segmentos que desexa exportar.

1. Seleccione **Gardar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

En Marketo, busca os teus segmentos debaixo [Listas de mercado](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).

[!INCLUDE [footer-include](includes/footer-banner.md)]
