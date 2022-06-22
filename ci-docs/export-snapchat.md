---
title: Exportar datos de Customer Insights a Snapchat
description: Aprenda a configurar a conexión e exportar a Snapchat.
ms.date: 06/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d64b482c322af8632e29ec41d6e34c390c5e646c
ms.sourcegitcommit: 8e9f0a9693fd8d91ad0227735ff03688fef5406f
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 06/10/2022
ms.locfileid: "8947274"
---
# <a name="export-segments-to-snapchat-preview"></a>Exportar segmentos a Snapchat (versión preliminar)

Exporte segmentos de perfís de clientes unificados a Snapchat e utilíceos para a publicidade. 

## <a name="prerequisites-for-a-connection"></a>Requisitos previos para unha conexión

-   Ten unha [Conta empresarial de Snapchat](https://business.snapchat.com/), unha [Conta publicitaria de Snapchat](https://ads.snapchat.com/) e as correspondentes credenciais de administrador. Polo menos debes ser membro dunha conta de organización e xestor de datos dunha conta de anuncios específica. 
-   Tes polo menos unha audiencia en Snapchat Audience Manager do tipo SAM (Snap Audience Match). 
-   Tes [segmentos configurados](segments.md) en Customer Insights.
-   Os perfís de clientes unificados nos segmentos exportados conteñen un campo que representa un enderezo de correo electrónico.

## <a name="known-limitations"></a>Limitacións coñecidas

- A exportación a Snapchat está limitada a segmentos.
- A exportación de ata 1 millón de perfís de clientes a Snapchat pode levar ata 15 minutos en completarse. 

## <a name="set-up-connection-to-snapchat"></a>Configurar conexión a Snapchat

1. Vaia a **Administrar** > **Conexións**.

1. Seleccione **Engadir conexión** e elixa **Snapchat** para configurar a conexión.

1. Déalle á conexión un nome recoñecible no campo **Nome para mostrar**. O nome e o tipo de conexión describen esta conexión. Recomendamos escoller un nome que explique o propósito e o destino da conexión.

1. Escolla quen pode usar esta conexión. Se non realiza ningunha acción, o valor predeterminado será Administradores. Para obter máis información, consulte [Permitir aos colaboradores usar unha conexión para as exportacións](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Seleccione **Estou de acordo** para confirmar a **Privacidade e cumprimento dos datos**.

1. Seleccione **Conectar** para iniciar a conexión a Snapchat.

1. Seleccione **Autenticarse con Snapchat** e proporcione as súas credenciais de administrador de Snapchat. 

1. Seleccione **Autoengadirse como usuario de exportación** e proporcione as súas credenciais de Customer Insights.

1. Seleccione **Gardar** para completar a conexión.

## <a name="configure-an-export"></a>Configurar unha exportación

Pode configurar esta exportación se ten acceso a unha conexión deste tipo. Para obter máis información, consulte [Permisos necesarios para configurar unha exportación](export-destinations.md#set-up-a-new-export).

1. Vaia a **Datos** > **Exportacións**.

1. Seleccione **Engadir destino** para crear unha nova exportación.

1. No campo **Conexión da exportación** escolla unha conexión da sección Snapchat. Se non ve o nome desta sección, non hai conexións deste tipo dispoñibles para vostede.

1. Introduza o [**Segmento de Snapchat/ID de audiencia**](https://businesshelp.snapchat.com/s/article/custom-audiences). O ID da audiencia pódese atopar no URL despois de seleccionar a audiencia en Snapchat Audience Manager. 

1. Na sección **Coincidencia de datos** do campo **Correo electrónico**, seleccione o campo que representa o enderezo de correo electrónico dun cliente. É necesario exportar segmentos a Snapchat.

1. Seleccione os segmentos que desexa exportar. 

1. Seleccione **Gardar**.

Ao gardar unha exportación non se executa a exportación inmediatamente.

A exportación execútase con cada [actualización programada](system.md#schedule-tab). Tamén pode [exportar datos baixo demanda](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Cumprimento e privacidade dos datos

Cando habilita Dynamics 365 Customer Insights para transmitir datos a Snapchat, permite a transferencia de datos fóra do límite de cumprimento de Dynamics 365 Customer Insights, incluíndo datos potencialmente confidenciais como os datos persoais. Microsoft transferirá estes datos segundo a súa instrución, pero vostede é responsable de asegurarse de que Snapchat cumpra as obrigas de privacidade ou seguridade que poida ter. Para obter máis información, consulte a [Declaración de privacidade de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

O administrador de Dynamics 365 Customer Insights pode eliminar este destino de exportación en calquera momento para interromper o uso desta funcionalidade.
