---
title: Exportar datos de Customer Insights a AdRoll
description: Aprenda a configurar a conexión e exportar a AdRoll.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 67bfa23d56b26ae592efa4d7197713664bb02623
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304817"
---
# <a name="export-segments-to-adroll-preview"></a>Exportar segmentos a AdRoll (versión preliminar)

Exporte segmentos de perfís de clientes unificados a AdRoll e utilíceos para publicidade. 

## <a name="prerequisites-for-a-connection"></a>Requisitos previos para unha conexión

-   Ten unha [conta de AdRoll](https://www.adroll.com/) e as correspondentes credenciais de administrador.
-   Ten [segmentos configurados](segments.md) na información do público.
-   Os perfís de clientes unificados nos segmentos exportados conteñen un campo que representa un enderezo de correo electrónico.

## <a name="known-limitations"></a>Limitacións coñecidas

- Pode exportar até 250.000 perfís ao mesmo tempo a AdRoll.
- Non pode exportar segmentos con menos de 100 perfís a AdRoll. 
- A exportación a AdRoll está limitada a segmentos.
- Exportar ata 250.000 perfís a AdRoll pode levar ata 10 minutos en completarse. 
- O número de perfís que pode exportar a AdRoll depende do seu contrato con AdRoll.

## <a name="set-up-connection-to-adroll"></a>Configurar conexión a AdRoll

1. Vaia a **Administrar** > **Conexións**.

1. Seleccione **Engadir conexión** e elixa **AdRoll** para configurar a conexión.

1. Déalle á conexión un nome recoñecible no campo **Nome para mostrar**. O nome e o tipo de conexión describen esta conexión. Recomendamos escoller un nome que explique o propósito e o destino da conexión.

1. Escolla quen pode usar esta conexión. Se non realiza ningunha acción, o valor predeterminado será Administradores. Para obter máis información, consulte [Permitir aos colaboradores usar unha conexión para as exportacións](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Seleccione **Estou de acordo** para confirmar a **Privacidade e cumprimento dos datos**.

1. Seleccione **Conectar** para iniciar a conexión a AdRoll.

1. Seleccione **Autenticarse con AdRoll** e proporcione as súas credenciais de administrador de AdRoll. 

1. Seleccione **Autoengadirse como usuario de exportación** e proporcione as súas credenciais de Customer Insights.

1. Seleccione **Gardar** para completar a conexión.

## <a name="configure-an-export"></a>Configurar unha exportación

Pode configurar esta exportación se ten acceso a unha conexión deste tipo. Para obter máis información, consulte [Permisos necesarios para configurar unha exportación](export-destinations.md#set-up-a-new-export).

1. Vaia a **Datos** > **Exportacións**.

1. Seleccione **Engadir destino** para crear unha nova exportación.

1. No campo **Conexión da exportación** escolla unha conexión da sección AdRoll. Se non ve o nome desta sección, non ten ningunha conexión deste tipo dispoñible.

1. Introduza o seu **ID de anunciante de AdRoll**. Para obter máis información, consulte [Perfís de anunciantes de AdRoll](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).

3. Na sección **Coincidencia de datos**, no campo **Correo electrónico**, seleccione o campo do seu perfil de cliente unificado que representa o enderezo de correo electrónico dun cliente. É necesario exportar segmentos a AdRoll.

1. Seleccione os segmentos que desexa exportar. Seleccione un segmento cun mínimo de 100 membros. Non pode exportar segmentos máis pequenos. Ademais, o tamaño máximo dun segmento para exportar é de 250.000 membros por exportación. 

1. Seleccione **Gardar**.

Ao gardar unha exportación non se executa a exportación inmediatamente.

A exportación execútase con cada [actualización programada](system.md#schedule-tab). 

Tamén pode [exportar datos baixo demanda](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Cumprimento e privacidade dos datos

Cando habilita Dynamics 365 Customer Insights para transmitir datos a AdRoll, permite a transferencia de datos fóra do límite de cumprimento de Dynamics 365 Customer Insights, incluíndo datos potencialmente confidenciais como os datos persoais. Microsoft transferirá estes datos segundo a súa instrución, pero vostede é responsable de garantir que AdRoll cumpra as obrigas de privacidade ou seguridade que poida ter. Para obter máis información, consulte a [Declaración de privacidade de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

O administrador de Dynamics 365 Customer Insights pode eliminar este destino de exportación en calquera momento para interromper o uso desta funcionalidade.
