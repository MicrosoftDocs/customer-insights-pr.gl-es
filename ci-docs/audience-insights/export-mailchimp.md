---
title: Exportar datos de Customer Insights a Mailchimp
description: Aprenda a configurar a conexión e exportar a Mailchimp.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 7922a6a69f863caae5401549ed6f88a61aa77d39
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124225"
---
# <a name="export-segments-to-mailchimp-preview"></a>Exportar segmentos a Mailchimp (versión preliminar)

Exporte segmentos de perfís de clientes unificados a Mailchimp para crear boletíns e campañas de correo electrónico.

## <a name="prerequisites-for-connection"></a>Requisitos previos para a conexión

-   Ten unha [Conta de Mailchimp](https://mailchimp.com/) e as correspondentes credenciais de administrador.
-   Existen públicos en Mailchimp e os ID correspondentes. Para obter máis información, consulte [públicos de Mailchimp](https://mailchimp.com/help/create-audience/).
-   Ten [segmentos configurados](segments.md)
-   Os perfís de clientes unificados nos segmentos exportados conteñen un campo que representa un enderezo de correo electrónico.

## <a name="known-limitations"></a>Limitacións coñecidas

- Ata 1 millón de perfís por exportación a Mailchimp.
- A exportación a Mailchimp está limitada a segmentos.
- Exportar segmentos cun millón de perfís pode levar ata tres horas. 
- O número de perfís que pode exportar a Mailchimp depende e está limitado no seu contrato con Mailchimp.

## <a name="set-up-connection-to-mailchimp"></a>Configurar conexión a Mailchimp

1. Vaia a **Administrar** > **Conexións**.

1. Seleccione **Engadir conexión** e elixa **Autopilot** para configurar a conexión.

1. Déalle á conexión un nome recoñecible no campo **Nome para mostrar**. O nome e o tipo de conexión describen esta conexión. Recomendamos escoller un nome que explique o propósito e o destino da conexión.

1. Escolla quen pode usar esta conexión. Se non realiza ningunha acción, o valor predeterminado será Administradores. Para obter máis información, consulte [Permitir aos colaboradores usar unha conexión para as exportacións](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Seleccione **Estou de acordo** para confirmar a **Privacidade e cumprimento dos datos**.

1. Seleccione **Conectar** para iniciar a conexión a Mailchimp.

1. Seleccione **Autenticarse con Mailchimp** e proporcione as súas credenciais de Mailchimp.

1. Seleccione **Autoengadirse como usuario de exportación** e proporcione as súas credenciais de Customer Insights.

1. Seleccione **Gardar** para completar a conexión. 

## <a name="configure-the-connector"></a>Configurar o conector

Pode configurar esta exportación se ten acceso a unha conexión deste tipo. Para obter máis información, consulte [Permisos necesarios para configurar unha exportación](export-destinations.md#set-up-a-new-export).

1. Vaia a **Datos**> **Exportacións**.

1. Seleccione **Engadir destino** para crear unha nova exportación.

1. No campo **Conexión da exportación** escolla unha conexión da sección Mailchimp. Se non ve o nome desta sección, non hai conexións deste tipo dispoñibles para vostede.

1. Insira o seu **[ID de público de MailChimp](https://mailchimp.com/help/find-audience-id/)**

3. Na sección **Coincidencia de datos**, no campo **Correo electrónico**, seleccione o campo do seu perfil de cliente unificado que representa o enderezo de correo electrónico dun cliente. 

1. Opcionalmente, pode exportar o **nome** e **apelidos** para crear correos electrónicos máis personalizados. Seleccione **Engadir atributo** para asignar estes campos.

1. Seleccione os segmentos que desexa exportar. Pode exportar ata 1 millón de perfís de clientes en total a Mailchimp.

1. Seleccione **Gardar**.

Ao gardar unha exportación non se executa a exportación inmediatamente.

A exportación execútase con cada [actualización programada](system.md#schedule-tab). Tamén pode [exportar datos baixo demanda](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Cumprimento e privacidade dos datos

Cando habilita Dynamics 365 Customer Insights para transmitir datos a Mailchimp, permite a transferencia de datos fóra do límite de cumprimento de Dynamics 365 Customer Insights, incluíndo datos potencialmente confidenciais como os datos persoais. Microsoft transferirá estes datos segundo a súa instrución, pero vostede é responsable de garantir que Mailchimp cumpra as obrigas de privacidade ou seguridade que poida ter. Para obter máis información, consulte a [Declaración de privacidade de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
O administrador de Dynamics 365 Customer Insights pode eliminar este destino de exportación en calquera momento para interromper o uso desta funcionalidade.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
