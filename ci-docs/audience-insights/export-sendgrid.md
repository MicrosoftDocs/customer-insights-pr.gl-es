---
title: Exportar datos de Customer Insights a SendGrid
description: Aprenda a configurar a conexión a SendGrid.
ms.date: 12/08/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: f16d69deb2a0b48270ed04f9b72f03056f20b619
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268730"
---
# <a name="connector-for-sendgrid-preview"></a>Conector para SendGrid (versión preliminar)

Exporte segmentos de perfís de clientes unificados a listas de contactos de SendGrid e utilíceos para campañas e mercadotecnia por correo electrónico en SendGrid. 

## <a name="prerequisites"></a>Requisitos previos

-   Ten unha [Conta de SendGrid](https://sendgrid.com/) e as correspondentes credenciais de administrador.
-   Existen listas de contacto en SendGrid e os ID correspondentes. Para obter máis información, consulte [SendGrid: xestionar contactos](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).
-   Ten [segmentos configurados](segments.md) na información do público.
-   Os perfís de clientes unificados nos segmentos exportados conteñen un campo que representa un enderezo de correo electrónico.

## <a name="connect-to-sendgrid"></a>Conectar con SendGrid

1. Vaia a **Administrador** > **Exportar destinos**.

1. En **SendGrid**, seleccione **Configurar**.

1. Déalle ao seu destino da exploración un nome recoñecible no campo **Nome para mostrar**.

   :::image type="content" source="media/export-sendgrid.PNG" alt-text="Panel de configuración de exportación de SendGrid.":::

1. Introduza a súa **Clave da API de SendGrid** [Clave da API de SendGrid](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).

1. Introduza o seu **[ID de lista de SendGrid](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.

1. Seleccione **Estou de acordo** para confirmar a **Privacidade e cumprimento dos datos**.

1. Seleccione **Conectar** para inicializar a conexión a SendGrid.

1. Seleccione **Autoengadirse como usuario de exportación** e proporcione as súas credenciais de Customer Insights.

1. Seleccione **Seguinte** para configurar a exportación.

## <a name="configure-the-connector"></a>Configurar o conector

1. Na sección **Coincidencia de datos**, no campo **Correo electrónico**, seleccione o campo do seu perfil de cliente unificado que representa o enderezo de correo electrónico dun cliente. Repita os mesmos pasos para outros campos opcionais como **nome**, **apelidos**, **país/rexión**, **estado**, **cidade** e **código postal**.

1. Seleccione os segmentos que desexa exportar. Nós fortemente **recomendamos non exportar máis de 100.000 perfís de clientes en total** a SendGrid. 

1. Seleccione **Gardar**.

## <a name="export-the-data"></a>Exportar os datos

Pode [exportar datos baixo demanda](export-destinations.md). A exportación tamén se executará con todas as [actualizacións programadas](system.md#schedule-tab).

## <a name="known-limitations"></a>Limitacións coñecidas

- Ata 100.000 perfís en total en SendGrid.
- A exportación a SendGrid está limitada a segmentos.
- Exportar ata 100.000 perfís a SendGrid pode tardar unhas horas en completarse. 
- O número de perfís que pode exportar a SendGrid depende e está limitado no seu contrato con SendGrid.

## <a name="data-privacy-and-compliance"></a>Cumprimento e privacidade dos datos

Cando habilita Dynamics 365 Customer Insights para transmitir datos a SendGrid, permite a transferencia de datos fóra do límite de cumprimento de Dynamics 365 Customer Insights, incluíndo datos potencialmente confidenciais como os datos persoais. Microsoft transferirá estes datos segundo a súa instrución, pero vostede é responsable de garantir que SendGrid cumpra as obrigas de privacidade ou seguridade que poida ter. Para obter máis información, consulte a [Declaración de privacidade de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
O administrador de Dynamics 365 Customer Insights pode eliminar este destino de exportación en calquera momento para interromper o uso desta funcionalidade.


[!INCLUDE[footer-include](../includes/footer-banner.md)]