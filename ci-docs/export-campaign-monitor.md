---
title: Exportar datos de Customer Insights a Campaign Monitor
description: Aprenda a configurar a conexión e exportar a Campaign Monitor.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b351e491ee830b6360d4efe33d32a726c2e553ba
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642543"
---
# <a name="export-segments-to-campaign-monitor-preview"></a>Exportar segmentos a Campaign Monitor (versión preliminar)

Exporte segmentos de perfís de clientes unificados a Campaign Monitor e utilíceos para actividades de mercadotecnia.

## <a name="prerequisites"></a>Requisitos previos

-   Ten unha [conta de Campaign Monitor](https://www.campaignmonitor.com/) e as correspondentes credenciais de administrador.
-   Tes [segmentos configurados](segments.md) en Customer Insights.
-   Os perfís de clientes unificados nos segmentos exportados conteñen un campo que representa un enderezo de correo electrónico.

## <a name="known-limitations"></a>Limitacións coñecidas

- Pode exportar ata 1 millón de perfís de clientes por exportación a Campaign Monitor.
- A exportación a Campaign Monitor está limitada a segmentos.
- A exportación de ata 1 millón de perfís de clientes a Campaign Monitor pode levar ata 20 minutos en completarse. 
- O número de perfís de clientes que pode exportar a Campaign Monitor depende e está limitado ao seu contrato con Campaign Monitor.

## <a name="set-up-connection-to-campaign-monitor"></a>Configurar a conexión a Campaign Monitor

1. Vaia a **Administrar** > **Conexións**.

1. Seleccione **Engadir conexión** e elixa **Campaign Monitor** para configurar a conexión.

1. Déalle á conexión un nome recoñecible no campo **Nome para mostrar**. O nome e o tipo de conexión describen esta conexión. Recomendamos escoller un nome que explique o propósito e o destino da conexión.

1. Escolla quen pode usar esta conexión. Se non realiza ningunha acción, o valor predeterminado será Administradores. Para obter máis información, consulte [Permitir aos colaboradores usar unha conexión para as exportacións](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Seleccione **Estou de acordo** para confirmar a **Privacidade e cumprimento dos datos**.

1. Seleccione **Conectar** para iniciar a conexión a Campaign Monitor.

1. Seleccione **Autenticarse con Campaign Monitor** e proporcione as súas credenciais de administrador de Campaign Monitor.

1. Seleccione **Autoengadirse como usuario de exportación** e proporcione as súas credenciais de Customer Insights.

1. Seleccione **Gardar** para completar a conexión.

## <a name="configure-an-export"></a>Configurar unha exportación

Pode configurar esta exportación se ten acceso a unha conexión deste tipo. Para obter máis información, consulte [Permisos necesarios para configurar unha exportación](export-destinations.md#set-up-a-new-export).

1. Vaia a **Datos** > **Exportacións**.

1. Seleccione **Engadir destino** para crear unha nova exportación.

1. No campo **Conexión da exportación** escolla unha conexión da sección Campaign Monitor. Se non ve o nome desta sección, non hai conexións deste tipo dispoñibles para vostede.

1. Insira o seu [**ID de lista de Campaign Monitor**](https://www.campaignmonitor.com/api/getting-started/#your-list-id).    
   [Xere a clave de API](https://www.campaignmonitor.com/api/getting-started/) desde **Axustes da conta** primeiro en Campaign Monitor para ver o ID da lista de API.  

1. Na sección **Coincidencia de datos** do campo **Correo electrónico**, seleccione o campo que representa o enderezo de correo electrónico dun cliente. É necesario exportar segmentos a Campaign Monitor.

1. Seleccione **Gardar**.

Ao gardar unha exportación non se executa a exportación inmediatamente.

A exportación execútase con cada [actualización programada](system.md#schedule-tab). Tamén pode [exportar datos baixo demanda](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Cumprimento e privacidade dos datos

Cando habilita Dynamics 365 Customer Insights para transmitir datos a Campaign Monitor, permite a transferencia de datos fóra do límite de cumprimento de Dynamics 365 Customer Insights, incluíndo datos potencialmente confidenciais como os datos persoais. Microsoft transferirá estes datos segundo a súa instrución, pero vostede é responsable de asegurarse de que Campaign Monitor cumpra as obrigas de privacidade ou seguridade que poida ter. Para obter máis información, consulte a [Declaración de privacidade de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

O administrador de Dynamics 365 Customer Insights pode eliminar este destino de exportación en calquera momento para interromper o uso desta funcionalidade.