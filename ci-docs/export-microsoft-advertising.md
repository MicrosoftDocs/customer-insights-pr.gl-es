---
title: Exportar datos de Customer Insights a Microsoft Advertising
description: Aprenda a configurar a conexión e exportar a Microsoft Advertising.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 14479e915dd6ae76e018b59bee5980a600bb222d
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642923"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a>Exportar segmentos a Microsoft Advertising (versión preliminar)

Exporte segmentos de Customer Insights a Microsoft Advertising para crear públicos de Coincidencia de clientes. Use estes públicos para as súas campañas publicitarias.

## <a name="prerequisites"></a>Requisitos previos

-   Unha [conta de Microsoft Advertising](https://ads.microsoft.com/) e as correspondentes credenciais de administrador.
-   Aceptou as condicións de uso de Coincidencia de clientes. 
-   [Segmentos configurados](segments.md) en Customer Insights.
-   Os perfís de clientes unificados nos segmentos exportados conteñen un campo cun enderezo de correo electrónico.

## <a name="known-limitations"></a>Limitacións coñecidas

- Pode exportar ata 500.000 perfís de clientes por exportación a Microsoft Advertising.
- A exportación a Microsoft Advertising está limitada a segmentos.
- A exportación de ata 500.000 perfís de clientes a Microsoft Advertising pode levar ata 10 minutos en completarse. 


## <a name="set-up-the-connection-to-microsoft-advertising"></a>Configurar a conexión a Microsoft Advertising

1. Vaia a **Administrar** > **Conexións**.

1. Seleccione **Engadir conexión** e elixa **Microsoft Advertising** para configurar a conexión.

1. Déalle á conexión un nome recoñecible no campo **Nome para mostrar**. O nome e o tipo de conexión describen esta conexión. Recomendamos escoller un nome que explique o propósito e o destino da conexión.

1. Escolla quen pode usar esta conexión. A opción predefinida é administradores. Para obter máis información, consulte [Permitir aos colaboradores usar unha conexión para as exportacións](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Seleccione **Estou de acordo** para confirmar a **Privacidade e cumprimento dos datos**.

1. Seleccione **Conectar** para iniciar a conexión a Microsoft Advertising.

1. Seleccione **Autenticarse con Microsoft Advertising** e proporcione as súas credenciais de administrador de Microsoft Advertising.

1. Seleccione **Autoengadirse como usuario de exportación** e proporcione as súas credenciais de Customer Insights.

1. Seleccione **Gardar** para completar a conexión.

## <a name="configure-an-export"></a>Configurar unha exportación

Pode configurar esta exportación se ten acceso a unha conexión deste tipo. Para obter máis información, consulte [Permisos necesarios para configurar unha exportación](export-destinations.md#set-up-a-new-export).

1. Vaia a **Datos** > **Exportacións**.

1. Seleccione **Engadir destino** para crear unha nova exportación.

1. No campo **Conexión da exportación** escolla unha conexión da sección Microsoft Advertising. Se non ve o nome desta sección, non hai conexións deste tipo dispoñibles para vostede.

1. Seleccione os segmentos que se van exportar. Os públicos de Coincidencia de clientes en Microsoft Advertising créanse automaticamente co nome dos segmentos seleccionados para a exportación. Cada segmento dará lugar a un público separado de Coincidencia de clientes. 

1. Introduza os seus **ID de cliente e conta de Microsoft Advertising**. Pode atopar o ID de cliente (`cid`) e o ID de conta (`aid`) nos parámetros do URL cando ten a sesión iniciada en Microsoft Advertising.

1. Na sección **Coincidencia de datos** do campo **Correo electrónico**, seleccione o campo cun enderezo de correo electrónico dun cliente. É necesario exportar segmentos a Microsoft Advertising.

1. Seleccione **Gardar**.

Ao gardar unha exportación non se executa a exportación inmediatamente.

A exportación execútase con cada [actualización programada](system.md#schedule-tab). Tamén pode [exportar datos baixo demanda](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Cumprimento e privacidade dos datos

Cando habilita Dynamics 365 Customer Insights para transmitir datos a Microsoft Advertising, permite a transferencia de datos fóra do límite de cumprimento de Dynamics 365 Customer Insights, incluíndo datos potencialmente confidenciais como os datos persoais. Microsoft transferirá estes datos segundo a súa instrución, pero vostede é responsable de asegurarse de que Microsoft Advertising cumpra as obrigas de privacidade ou seguridade que poida ter. Para obter máis información, consulte a [Declaración de privacidade de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

O administrador de Dynamics 365 Customer Insights pode eliminar este destino de exportación en calquera momento para deter o uso desta funcionalidade.
