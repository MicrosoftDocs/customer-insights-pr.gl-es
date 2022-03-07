---
title: Exportar datos de Customer Insights a Klaviyo
description: Aprenda a configurar a conexión e exportar a Klaviyo.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 027aee70d9fdab0a92d7fd99209a6ac2ca3cc361
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 02/16/2022
ms.locfileid: "8225450"
---
# <a name="export-segment-lists-to-klaviyo-preview"></a>Exportar listas de segmentos a Klaviyo (versión preliminar)

Exporte segmentos de perfís de clientes unificados a Klaviyo e utilíceos para actividades de márketing.

## <a name="prerequisites"></a>Requisitos previos

-   Ten unha [conta de Klaviyo](https://www.klaviyo.com/) e as correspondentes credenciais de administrador.
-   Ten [segmentos configurados](segments.md) na información do público.
-   Os perfís de clientes unificados nos segmentos exportados conteñen un campo que representa un enderezo de correo electrónico.

## <a name="known-limitations"></a>Limitacións coñecidas

- Pode exportar ata 100.000 perfís de clientes por exportación a Klaviyo.
- A exportación a Klaviyo está limitada a segmentos.
- A exportación de ata 1 millón de perfís de clientes a Klaviyo pode levar ata 20 minutos en completarse. 
- O número de perfís de clientes que pode exportar a Klaviyo depende e está limitado ao seu contrato con Klaviyo.

## <a name="set-up-connection-to-klaviyo"></a>Configurar conexión a Klaviyo

1. Vaia a **Administrar** > **Conexións**.

1. Seleccione **Engadir conexión** e elixa **Klaviyo** para configurar a conexión.

1. Déalle á conexión un nome recoñecible no campo **Nome para mostrar**. O nome e o tipo de conexión describen esta conexión. Recomendamos escoller un nome que explique o propósito e o destino da conexión.

1. Escolla quen pode usar esta conexión. Se non realiza ningunha acción, o valor predeterminado será Administradores. Para obter máis información, consulte [Permitir aos colaboradores usar unha conexión para as exportacións](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Proporcione a súa [clave da API de Klaviyo](https://help.klaviyo.com/hc/articles/115005062267-How-to-Manage-Your-Account-s-API-Keys) para continuar co inicio de sesión. 

1. Seleccione **Estou de acordo** para confirmar a **Privacidade e cumprimento dos datos**.

1. Seleccione **Conectar** para iniciar a conexión a Klaviyo.

1. Seleccione **Autenticar con Klaviyo** e proporcione as súas credenciais de administrador de Klaviyo.

1. Seleccione **Autoengadirse como usuario de exportación** e proporcione as súas credenciais de Customer Insights.

1. Seleccione **Gardar** para completar a conexión.

## <a name="configure-an-export"></a>Configurar unha exportación

Pode configurar esta exportación se ten acceso a unha conexión deste tipo. Para obter máis información, consulte [Permisos necesarios para configurar unha exportación](export-destinations.md#set-up-a-new-export).

1. Vaia a **Datos** > **Exportacións**.

1. Seleccione **Engadir destino** para crear unha nova exportación.

1. No campo **Conexión para a exportación**, escolla unha conexión na sección de Klaviyo. Se non ve o nome desta sección, non hai conexións deste tipo dispoñibles para vostede.

1. Introduza o seu [**ID de lista de Klaviyo**](https://help.klaviyo.com/hc/articles/115005078647-How-to-Find-a-List-ID).     

3. Na sección **Coincidencia de datos** do campo **Correo electrónico**, seleccione o campo que representa o enderezo de correo electrónico dun cliente. É necesario para exportar segmentos a Klaviyo.

1. Seleccione **Gardar**.

Ao gardar unha exportación non se executa a exportación inmediatamente.

A exportación execútase con cada [actualización programada](system.md#schedule-tab). Tamén pode [exportar datos baixo demanda](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Cumprimento e privacidade dos datos

Cando permite a Dynamics 365 Customer Insights transmitir datos a Klaviyo, permite a transferencia de datos fóra do límite de cumprimento de Dynamics 365 Customer Insights, incluíndo datos potencialmente confidenciais como os datos persoais. Microsoft transferirá estes datos segundo a súa instrución, pero vostede é responsable de asegurarse de que Klaviyo cumpre coas obrigacións de privacidade ou seguridade que poida ter. Para obter máis información, consulte a [Declaración de privacidade de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

O administrador de Dynamics 365 Customer Insights pode eliminar este destino de exportación en calquera momento para interromper o uso desta funcionalidade.
