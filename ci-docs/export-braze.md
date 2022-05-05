---
title: Exporta datos de Customer Insights a Braze
description: Obtén información sobre como configurar a conexión e exportar a Braze.
ms.date: 03/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: bfc9b34506dc3385b5edf12b31e74d05f2d20655
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642546"
---
# <a name="export-segment-lists-to-braze-preview"></a>Exportar listas de segmentos a Braze (vista previa)

Exporta segmentos de perfís de clientes unificados a Braze e utilízaos para actividades de mercadotecnia.

## <a name="prerequisites"></a>Requisitos previos

-   Tes un [Conta Braze](https://www.braze.com/) e as correspondentes credenciais de administrador.
-   Tes [segmentos configurados](segments.md) en Customer Insights.
-   Os perfís de clientes unificados nos segmentos exportados conteñen un campo que representa un enderezo de correo electrónico e un ID de cliente Braze. 

## <a name="known-limitations"></a>Limitacións coñecidas

- A exportación a Braze está limitada a segmentos.
- A exportación de ata 1 millón de perfís de clientes a Braze pode levar ata 40 minutos. 
- O número de perfís de clientes que podes exportar a Braze depende e limitado do teu contrato con Braze.

## <a name="set-up-connection-to-braze"></a>Configura a conexión con Braze

1. Vaia a **Administrar** > **Conexións**.

1. Seleccione **Engadir conexión** e escolle **Braze** para configurar a conexión.

1. Déalle á conexión un nome recoñecible no campo **Nome para mostrar**. O nome e o tipo de conexión describen esta conexión. Recomendamos escoller un nome que explique o propósito e o destino da conexión.

1. Escolla quen pode usar esta conexión. Se non realiza ningunha acción, o valor predeterminado será Administradores. Para obter máis información, consulte [Permitir aos colaboradores usar unha conexión para as exportacións](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Proporciona o teu [Chave API Braze](https://www.braze.com/docs/api/basics/) para continuar iniciando sesión. 

1. Seleccione **Estou de acordo** para confirmar a **Privacidade e cumprimento dos datos**.

1. Seleccione **Conectar** para inicializar a conexión con Braze.

1. Seleccione **Autoengadirse como usuario de exportación** e proporcione as súas credenciais de Customer Insights.

1. Seleccione **Gardar** para completar a conexión.

## <a name="configure-an-export"></a>Configurar unha exportación

Pode configurar esta exportación se ten acceso a unha conexión deste tipo. Para obter máis información, consulte [Permisos necesarios para configurar unha exportación](export-destinations.md#set-up-a-new-export).

1. Vaia a **Datos** > **Exportacións**.

1. Seleccione **Engadir destino** para crear unha nova exportación.

1. No **Conexión para exportación** campo, escolla unha conexión na sección Braze. Se non ve o nome desta sección, non hai conexións deste tipo dispoñibles para vostede.  

3. No **Correspondencia de datos** sección, na **Correo electrónico** campo, seleccione o campo que representa o enderezo de correo electrónico dun cliente, no campo "ID de cliente", seleccione o campo que representa o ID de Braze do cliente. É necesario exportar segmentos a Braze. Os segmentos en Braze crearanse co mesmo nome do segmento que en Dynamics 365 Customer Insights. Pode escoller campos adicionais e opcionais para os datos coincidentes. 

1. Seleccione **Gardar**.

Ao gardar unha exportación non se executa a exportación inmediatamente.

A exportación execútase con cada [actualización programada](system.md#schedule-tab). Tamén pode [exportar datos baixo demanda](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Cumprimento e privacidade dos datos

Cando habilitas Dynamics 365 Customer Insights para transmitir datos a Braze, permite a transferencia de datos fóra do límite de conformidade para Dynamics 365 Customer Insights, incluíndo datos potencialmente sensibles, como os datos persoais. Microsoft transferirá eses datos segundo as súas instrucións, pero vostede é responsable de asegurarse de que Braze cumpra as obrigas de privacidade ou seguridade que poida ter. Para obter máis información, consulte a [Declaración de privacidade de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

O administrador de Dynamics 365 Customer Insights pode eliminar este destino de exportación en calquera momento para interromper o uso desta funcionalidade.
