---
title: Exportar datos de Customer Insights a DotDigital
description: Aprenda a configurar a conexión e exportar a DotDigital.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f9302e17c07238d837dcafb82baecb5aedda17de
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 02/16/2022
ms.locfileid: "8231616"
---
# <a name="export-segments-to-dotdigital-preview"></a>Exportar segmentos a DotDigital (versión preliminar)

Exporte segmentos de perfís de clientes unificados a axendas de enderezos de DotDigital e utilíceos para campañas, mercadotecnia por correo electrónico e para crear segmentos de clientes con DotDigital. 

## <a name="prerequisites-for-a-connection"></a>Requisitos previos para unha conexión

-   Ten unha [Conta DotDigital](https://dotdigital.com/) e creou un [Usuario da API](https://support.dotdigital.com/hc/articles/115001718730-How-do-I-create-an-API-user). Necesitará empregar as credenciais de usuario da API para crear unha conexión
-   Existen axendas de enderezos en DotDigital e os ID correspondentes. A identificación pódese atopar na URL cando selecciona e abre unha axenda de enderezos. Para obter máis información, consulte [Axendas de enderezos de DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).
-   Ten [segmentos configurados](segments.md) na información do público.
-   Os perfís de clientes unificados nos segmentos exportados conteñen un campo que representa un enderezo de correo electrónico.

## <a name="known-limitations"></a>Limitacións coñecidas

- Ata 1 millón de perfís de clientes por exportación a DotDigital.
- A exportación a DotDigital está limitada a segmentos.
- A exportación de segmentos cun total de 1 millón de perfís de clientes pode levar ata 3 horas por mor das limitacións do provedor. 
- O número de perfís de clientes que pode exportar a DotDigital depende e está limitado ao seu contrato con DotDigital.

## <a name="set-up-connection-to-dotdigital"></a>Configurar conexión a DotDigital

1. Vaia a **Administrar** > **Conexións**.

1. Seleccione **Engadir conexión** e elixa **DotDigital** para configurar a conexión.

1. Déalle á conexión un nome recoñecible no campo **Nome para mostrar**. O nome e o tipo de conexión describen esta conexión. Recomendamos escoller un nome que explique o propósito e o destino da conexión.

1. Escolla quen pode usar esta conexión. Se non realiza ningunha acción, o valor predeterminado será Administradores. Para obter máis información, consulte [Permitir aos colaboradores usar unha conexión para as exportacións](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Escriba o seu **nome de usuario e contrasinal da API de DotDigital**. 

1. Introduza o seu **[ID da axenda de enderezos de DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.

1. Seleccione **Estou de acordo** para confirmar a **Privacidade e cumprimento dos datos**.

1. Seleccione **Conectar** para inicializar a conexión a DotDigital.

1. Seleccione **Autoengadirse como usuario de exportación** e proporcione as súas credenciais de Customer Insights.

1. Seleccione **Gardar** para completar a conexión. 

## <a name="configure-an-export"></a>Configurar unha exportación

Pode configurar esta exportación se ten acceso a unha conexión deste tipo. Para obter máis información, consulte [Permisos necesarios para configurar unha exportación](export-destinations.md#set-up-a-new-export).

1. Vaia a **Datos** > **Exportacións**.

1. Seleccione **Engadir destino** para crear unha nova exportación.

1. No campo **Conexión da exportación** escolla unha conexión da sección DotDigital. Se non ve o nome desta sección, non hai conexións deste tipo dispoñibles para vostede.


1. Na sección **Coincidencia de datos** do campo **Correo electrónico**, seleccione o campo que representa o enderezo de correo electrónico dun cliente. Repita os mesmos pasos para outros campos opcionais como **nome**, **apelidos**, **Nome completo**, **sexos** e **Código postal**.

1. Seleccione os segmentos que desexa exportar. Pode exportar ata 1 millón de perfís de clientes en total a DotDigital.

1. Seleccione **Gardar**.

Ao gardar unha exportación non se executa a exportación inmediatamente.

A exportación execútase con cada [actualización programada](system.md#schedule-tab). Tamén pode [exportar datos baixo demanda](export-destinations.md#run-exports-on-demand). 
 
En DotDigital, agora pode atopar os seus segmentos en [Axendas de enderezos de DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).


## <a name="data-privacy-and-compliance"></a>Cumprimento e privacidade dos datos

Cando habilita Dynamics 365 Customer Insights para transmitir datos a DotDigital, permite a transferencia de datos fóra do límite de cumprimento de Dynamics 365 Customer Insights, incluíndo datos potencialmente confidenciais como os datos persoais. Microsoft transferirá estes datos segundo a súa instrución, pero vostede é responsable de garantir que DotDigital cumpra as obrigas de privacidade ou seguridade que poida ter. Para obter máis información, consulte a [Declaración de privacidade de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
O administrador de Dynamics 365 Customer Insights pode eliminar este destino de exportación en calquera momento para interromper o uso desta funcionalidade.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
