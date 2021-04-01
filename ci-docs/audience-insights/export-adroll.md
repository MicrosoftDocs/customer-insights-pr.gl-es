---
title: Exportar datos de Customer Insights a AdRoll
description: Aprenda a configurar a conexión a AdRoll.
ms.date: 02/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6fedd549c2e7de362f36e3fb23d363200bb92a04
ms.sourcegitcommit: d24e52150fe5a4fab45128e12d6a03637771d9b9
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "5697072"
---
# <a name="connector-for-adroll-preview"></a>Conector para AdRoll (versión preliminar)

Exporte segmentos de perfís de clientes unificados a AdRoll e utilíceos para publicidade. 

## <a name="prerequisites"></a>Requisitos previos

-   Ten unha [conta de AdRoll](https://www.adroll.com/) e as correspondentes credenciais de administrador.
-   Ten [segmentos configurados](segments.md) na información do público.
-   Os perfís de clientes unificados nos segmentos exportados conteñen un campo que representa un enderezo de correo electrónico.

## <a name="connect-to-adroll"></a>Conectar con AdRoll

1. Vaia a **Administrador** > **Exportar destinos**.

1. En **AdRoll**, seleccione **Configurar**.

1. Déalle ao seu destino da exploración un nome recoñecible no campo **Nome para mostrar**.

   :::image type="content" source="media/AdRoll_config.PNG" alt-text="Panel de configuración para a conexión de AdRoll.":::

1. Seleccione **Estou de acordo** para confirmar a **Privacidade e cumprimento dos datos**.

1. Seleccione **Conectar** para iniciar a conexión a AdRoll.

1. Seleccione **Autenticarse con AdRoll** e proporcione as súas credenciais de administrador de AdRoll. 

1. Seleccione **Autoengadirse como usuario de exportación** e proporcione as súas credenciais de Customer Insights.

1. Introduza o seu **ID de anunciante de AdRoll** [Posible publicidade en AdRoll](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).

1. Seleccione **Seguinte** para configurar a exportación.

## <a name="configure-the-connector"></a>Configurar o conector

1. Na sección **Coincidencia de datos**, no campo **Correo electrónico**, seleccione o campo do seu perfil de cliente unificado que representa o enderezo de correo electrónico dun cliente. É necesario exportar segmentos a AdRoll.

1. Seleccione os segmentos que desexa exportar. Seleccione un segmento cun mínimo de 100 membros. Non pode exportar segmentos máis pequenos. Ademais, o tamaño máximo dun segmento para exportar é de 250.000 membros por exportación. 

1. Seleccione **Gardar**.

## <a name="export-the-data"></a>Exportar os datos

Pode [exportar datos baixo demanda](export-destinations.md). A exportación tamén se executará con todas as [actualizacións programadas](system.md#schedule-tab).

## <a name="known-limitations"></a>Limitacións coñecidas

- Pode exportar ata 250.000 perfís por exportación a AdRoll.
- Non pode exportar segmentos con menos de 100 perfís a AdRoll. 
- A exportación a AdRoll está limitada a segmentos.
- Exportar ata 250.000 perfís a AdRoll pode levar ata 10 minutos en completarse. 
- O número de perfís que pode exportar a AdRoll depende e está limitado no seu contrato con AdRoll.

## <a name="data-privacy-and-compliance"></a>Cumprimento e privacidade dos datos

Cando habilita Dynamics 365 Customer Insights para transmitir datos a AdRoll, permite a transferencia de datos fóra do límite de cumprimento de Dynamics 365 Customer Insights, incluíndo datos potencialmente confidenciais como os datos persoais. Microsoft transferirá estes datos segundo a súa instrución, pero vostede é responsable de garantir que AdRoll cumpra as obrigas de privacidade ou seguridade que poida ter. Para obter máis información, consulte a [Declaración de privacidade de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

O administrador de Dynamics 365 Customer Insights pode eliminar este destino de exportación en calquera momento para interromper o uso desta funcionalidade.
