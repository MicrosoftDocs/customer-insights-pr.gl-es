---
title: Exportar datos de Customer Insights a DotDigital
description: Aprenda a configurar a conexión a DotDigital.
ms.date: 11/14/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ed6bd40e8575fc90258f79f60abffe54f136d274
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644446"
---
# <a name="connector-for-dotdigital-preview"></a>Conector para DotDigital (vista previa)

Exporte segmentos de perfís de clientes unificados a axendas de enderezos de DotDigital e utilíceos para campañas, mercadotecnia por correo electrónico e para crear segmentos de clientes con DotDigital. 

## <a name="prerequisites"></a>Requisitos previos

-   Ten unha [Conta de DotDigital](https://dotdigital.com/) e as correspondentes credenciais de administrador.
-   Existen axendas de enderezos en DotDigital e os ID correspondentes. A identificación pódese atopar na URL cando selecciona e abre unha axenda de enderezos. Para obter máis información, consulte [Axendas de enderezos de DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).
-   Ten [segmentos configurados](segments.md) na información do público.
-   Os perfís de clientes unificados nos segmentos exportados conteñen un campo que representa un enderezo de correo electrónico.

## <a name="connect-to-dotdigital"></a>Conectarse a DotDigital

1. Vaia a **Administrador** > **Exportar destinos**.

1. En **DotDigital**, seleccione **Configurar**.

1. Déalle ao seu destino da exploración un nome recoñecible no campo **Nome para mostrar**.

   :::image type="content" source="media/DotDigital_config.PNG" alt-text="Panel de configuración para a exportación a DotDigital.":::

1. Escriba o seu **nome de usuario e contrasinal de DotDigital**.

1. Introduza o seu **[ID da axenda de enderezos de DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.

1. Seleccione **Estou de acordo** para confirmar a **Privacidade e cumprimento dos datos**.

1. Seleccione **Conectar** para inicializar a conexión a DotDigital.

1. Seleccione **Autoengadirse como usuario de exportación** e proporcione as súas credenciais de Customer Insights.

1. Seleccione **Seguinte** para configurar a exportación.

## <a name="configure-the-connector"></a>Configurar o conector

1. Na sección **Coincidencia de datos**, no campo **Correo electrónico**, seleccione o campo do seu perfil de cliente unificado que representa o enderezo de correo electrónico dun cliente. Repita os mesmos pasos para outros campos opcionais como **nome**, **apelidos**, **Nome completo**, **sexos** e **Código postal**.

1. Seleccione os segmentos que desexa exportar. Pode exportar ata 1 millón de perfís de clientes en total a DotDigital.

1. Seleccione **Gardar**.

## <a name="export-the-data"></a>Exportar os datos

Pode [exportar datos baixo demanda](export-destinations.md). A exportación tamén se executará con todas as [actualizacións programadas](system.md#schedule-tab). En DotDigital, agora pode atopar os seus segmentos en [Axendas de enderezos de DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).

## <a name="known-limitations"></a>Limitacións coñecidas

- Ata 1 millón de perfís por exportación a DotDigital.
- A exportación a DotDigital está limitada a segmentos.
- A exportación de segmentos cun total de 1 millón de perfís pode levar ata 3 horas debido ás limitacións do provedor. 
- O número de perfís que pode exportar a DotDigital depende e está limitado no seu contrato con DotDigital.

## <a name="data-privacy-and-compliance"></a>Cumprimento e privacidade dos datos

Cando habilita Dynamics 365 Customer Insights para transmitir datos a DotDigital, permite a transferencia de datos fóra do límite de cumprimento de Dynamics 365 Customer Insights, incluíndo datos potencialmente confidenciais como os datos persoais. Microsoft transferirá estes datos segundo a súa instrución, pero vostede é responsable de garantir que DotDigital cumpra as obrigas de privacidade ou seguridade que poida ter. Para obter máis información, consulte a [Declaración de privacidade de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
O administrador de Dynamics 365 Customer Insights pode eliminar este destino de exportación en calquera momento para interromper o uso desta funcionalidade.
