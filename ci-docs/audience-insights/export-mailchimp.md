---
title: Exportar datos de Customer Insights a Mailchimp
description: Aprenda a configurar a conexión a Mailchimp.
ms.date: 10/26/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 9f86616731c3cc3d26370727103ea9c5d4288c8d
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598199"
---
# <a name="connector-for-mailchimp-preview"></a>Conector para Mailchimp (vista previa)

Exporte segmentos de perfís de clientes unificados a Mailchimp para crear boletíns e campañas de correo electrónico.

## <a name="prerequisites"></a>Requisitos previos

-   Ten unha [Conta de Mailchimp](https://mailchimp.com/) e as correspondentes credenciais de administrador.
-   Existen públicos en Mailchimp e os ID correspondentes. Para obter máis información, consulte [públicos de Mailchimp](https://mailchimp.com/help/create-audience/).
-   Ten [segmentos configurados](segments.md)
-   Os perfís de clientes unificados nos segmentos exportados conteñen un campo que representa un enderezo de correo electrónico.

## <a name="connect-to-mailchimp"></a>Conectarse a MailChimp

1. Vaia a **Administrador** > **Exportar destinos**.

1. En **Mailchimp**, seleccione **Configurar**.

1. Déalle ao seu destino da exploración un nome recoñecible no campo **Nome para mostrar**.

1. Seleccione **Estou de acordo** para confirmar a **Privacidade e cumprimento dos datos**.

1. Introduza o seu **[ID de audiencia de Mailchimp](https://mailchimp.com/help/find-audience-id/)** e seleccione **Conectar** para inicializar a conexión a Mailchimp.

1. Seleccione **Autenticarse con Mailchimp** e proporcione as súas credenciais de Mailchimp.

1. Seleccione **Autoengadirse como usuario de exportación** e proporcione as súas credenciais de Customer Insights.

   :::image type="content" source="media/export-connect-mailchimp.png" alt-text="Captura de pantalla de exportación para a conexión de Mailchimp":::

1. Seleccione **Seguinte** para configurar a exportación.

## <a name="configure-the-connector"></a>Configurar o conector

1. Na sección **Coincidencia de datos**, no campo **Correo electrónico**, seleccione o campo do seu perfil de cliente unificado que representa o enderezo de correo electrónico dun cliente. 

1. Opcionalmente, pode exportar o **nome** e os **apelidos** como campos adicionais para crear correos electrónicos máis personalizados. Seleccione **Engadir atributo** para asignar estes campos.

1. Seleccione os segmentos que desexa exportar. Pode exportar ata 1 millón de perfís de clientes en total a Mailchimp.

   :::image type="content" source="media/export-segments-mailchimp.png" alt-text="Seleccionar campos e segmentos para exportar a Mailchimp":::

1. Seleccione **Gardar**.

## <a name="export-the-data"></a>Exportar os datos

Pode [exportar datos baixo demanda](export-destinations.md). A exportación tamén se executará con todas as [actualizacións programadas](system.md#schedule-tab). En Mailchimp, agora pode atopar os seus segmentos en [Públicos de Mailchimp](https://mailchimp.com/help/create-audience/).

## <a name="known-limitations"></a>Limitacións coñecidas

- Ata 1 millón de perfís por exportación a Mailchimp.
- A exportación a Mailchimp está limitada a segmentos.
- A exportación de segmentos cun total de 1 millón de perfís pode levar ata tres horas debido ás limitacións do provedor. 
- O número de perfís que pode exportar a Mailchimp depende e está limitado no seu contrato con Mailchimp.

## <a name="data-privacy-and-compliance"></a>Cumprimento e privacidade dos datos

Cando habilita Dynamics 365 Customer Insights para transmitir datos a Mailchimp, permite a transferencia de datos fóra do límite de cumprimento de Dynamics 365 Customer Insights, incluíndo datos potencialmente confidenciais como os datos persoais. Microsoft transferirá estes datos segundo a súa instrución, pero vostede é responsable de garantir que Mailchimp cumpra as obrigas de privacidade ou seguridade que poida ter. Para obter máis información, consulte a [Declaración de privacidade de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
O administrador de Dynamics 365 Customer Insights pode eliminar este destino de exportación en calquera momento para interromper o uso desta funcionalidade.


[!INCLUDE[footer-include](../includes/footer-banner.md)]