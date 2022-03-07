---
title: Exportar datos de Customer Insights a Marketo
description: Aprenda a configurar a conexión e exportar a Marketo.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ec286bb6a90fb4d18e89caf9166aa659b29d668e
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 02/16/2022
ms.locfileid: "8231977"
---
# <a name="export-segments-to-marketo-preview"></a>Exportar segmentos a Marketo (versión preliminar)

Exporte os segmentos de perfís de clientes unificados para xerar campañas, proporcionar márketing por correo electrónico e usar grupos específicos de clientes con Marketo.

## <a name="prerequisites-for-connection"></a>Requisitos previos para a conexión

-   Ten unha [Conta de Marketo](https://login.marketo.com/) e as correspondentes credenciais de administrador.
-   Existen listas en Marketo e os ID correspondentes. Para obter máis información, consulte [Listas de Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).
-   Ten [segmentos configurados](segments.md).
-   Os perfís de clientes unificados nos segmentos exportados conteñen un campo que representa un enderezo de correo electrónico.

## <a name="known-limitations"></a>Limitacións coñecidas

- Ata 1 millón de perfís de clientes por exportación a Marketo.
- A exportación a Marketo está limitada a segmentos.
- A exportación de segmentos cun total de 1 millón de perfís de clientes pode levar ata 3 horas. 
- O número de perfís de clientes que pode exportar a Marketo depende e está limitado ao seu contrato con Marketo.

## <a name="set-up-connection-to-marketo"></a>Configurar conexión a Marketo

1. Vaia a **Administrar** > **Conexións**.

1. Seleccione **Engadir conexión** e elixa **Marketo** para configurar a conexión.

1. Déalle á conexión un nome recoñecible no campo **Nome para mostrar**. O nome e o tipo de conexión describen esta conexión. Recomendamos escoller un nome que explique o propósito e o destino da conexión.

1. Escolla quen pode usar esta conexión. Se non realiza ningunha acción, o valor predeterminado será Administradores. Para obter máis información, consulte [Permitir aos colaboradores usar unha conexión para as exportacións](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduza o seu **[ID de cliente de Marketo, segredo de cliente e nome do servidor do extremo de REST](https://developers.marketo.com/rest-api/authentication/)**. O nome do servidor do extremo de REST é só o nome do servidor, sen `https://`. Exemplo:`xyz-abc-123.mktorest.com`. 

1. Seleccione **Estou de acordo** para confirmar a **Privacidade e cumprimento de datos** e seleccione **Conectar** para inicializar a conexión con Marketo.

1. Seleccione **Autoengadirse como usuario de exportación** e proporcione as súas credenciais de Customer Insights.

1. Seleccione **Gardar** para completar a conexión.

## <a name="configure-an-export"></a>Configurar unha exportación

Pode configurar esta exportación se ten acceso a unha conexión deste tipo. Para obter máis información, consulte [Permisos necesarios para configurar unha exportación](export-destinations.md#set-up-a-new-export).

1. Vaia a **Datos** > **Exportacións**.

1. Seleccione **Engadir destino** para crear unha nova exportación.

1. No campo **Conexión da exportación** escolla unha conexión da sección Marketo. Se non ve o nome desta sección, non hai conexións deste tipo dispoñibles para vostede.

1. Introduza o seu **[ID de lista de Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**. O ID da lista é un valor unicamente numérico. Por exemplo, se o seu ID de lista de Marketo é ST12345A7, elimine o carácter de antes e despois dos números e introduza `12345`. 

1. Na sección **Coincidencia de datos** do campo **Correo electrónico**, seleccione o campo que representa o enderezo de correo electrónico dun cliente. 

1. Opcionalmente, pode exportar o **nome**, **apelidos**, **cidade**, **estado** e **país/rexión** para crear correos electrónicos máis personalizados. Seleccione **Engadir atributo** para asignar estes campos.

1. Seleccione os segmentos que desexa exportar. Pode exportar ata 1 millón de perfís de clientes en total a Marketo.

1. Seleccione **Gardar**.

Ao gardar unha exportación non se executa a exportación inmediatamente.

A exportación execútase con cada [actualización programada](system.md#schedule-tab). Tamén pode [exportar datos baixo demanda](export-destinations.md#run-exports-on-demand). En Marketo, agora pode atopar os seus segmentos en [Listas de Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).


## <a name="data-privacy-and-compliance"></a>Cumprimento e privacidade dos datos

Cando habilita Dynamics 365 Customer Insights para transmitir datos a Marketo, permite a transferencia de datos fóra do límite de cumprimento de Dynamics 365 Customer Insights, incluíndo datos potencialmente confidenciais como os datos persoais. Microsoft transferirá estes datos segundo a súa instrución, pero vostede é responsable de garantir que Marketo cumpra as obrigas de privacidade ou seguridade que poida ter. Para obter máis información, consulte a [Declaración de privacidade de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
O administrador de Dynamics 365 Customer Insights pode eliminar este destino de exportación en calquera momento para interromper o uso desta funcionalidade.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
