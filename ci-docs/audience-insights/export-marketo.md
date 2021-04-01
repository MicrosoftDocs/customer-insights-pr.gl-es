---
title: Exportar datos de Customer Insights a Marketo
description: Aprenda a configurar a conexión a Marketo.
ms.date: 11/12/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 74d19a0448123904210c26f7b8760d00296c9cfd
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597969"
---
# <a name="connector-for-marketo-preview"></a>Conector para Marketo (vista previa)

Exporte os segmentos de perfís de clientes unificados para xerar campañas, proporcionar márketing por correo electrónico e usar grupos específicos de clientes con Marketo.

## <a name="prerequisites"></a>Requisitos previos

-   Ten unha [Conta de Marketo](https://login.marketo.com/) e as correspondentes credenciais de administrador.
-   Existen listas en Marketo e os ID correspondentes. Para obter máis información, consulte [Listas de Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).
-   Ten [segmentos configurados](segments.md).
-   Os perfís de clientes unificados nos segmentos exportados conteñen un campo que representa un enderezo de correo electrónico.

## <a name="connect-to-marketo"></a>Conectar con Marketo

1. Vaia a **Administrador** > **Exportar destinos**.

1. En **Marketo**, seleccione **Configurar**.

1. Déalle ao seu destino da exploración un nome recoñecible no campo **Nome para mostrar**.

1. Introduza o seu **[ID de cliente de Marketo, segredo de cliente e nome do servidor do extremo de REST](https://developers.marketo.com/rest-api/authentication/)**.

1. Introduza o seu **[ID de lista de Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)** 

1. Seleccione **Estou de acordo** para confirmar a **Privacidade e cumprimento de datos** e seleccione **Conectar** para inicializar a conexión con Marketo.

1. Seleccione **Autoengadirse como usuario de exportación** e proporcione as súas credenciais de Customer Insights.

   :::image type="content" source="media/export-connect-marketo.png" alt-text="Captura de pantalla de exportación para a conexión de Marketo":::

1. Seleccione **Seguinte** para configurar a exportación.

## <a name="configure-the-connector"></a>Configurar o conector

1. Na sección **Coincidencia de datos**, no campo **Correo electrónico**, seleccione o campo do seu perfil de cliente unificado que representa o enderezo de correo electrónico dun cliente. 

1. Opcionalmente, pode exportar o **nome**, os **apelidos**, a **cidade**, o **esstado** e o **país/rexión** como campos adicionais para crear correos electrónicos máis personalizados. Seleccione **Engadir atributo** para asignar estes campos.

1. Seleccione os segmentos que desexa exportar. Pode exportar ata 1 millón de perfís de clientes en total a Marketo.

   :::image type="content" source="media/export-segment-marketo.png" alt-text="Seleccionar campos e segmentos para exportar a Marketo":::

1. Seleccione **Gardar**.

## <a name="export-the-data"></a>Exportar os datos

Pode [exportar datos baixo demanda](export-destinations.md). A exportación tamén se executará con todas as [actualizacións programadas](system.md#schedule-tab). En Marketo, agora pode atopar os seus segmentos en [Listas de Marketo](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).

## <a name="known-limitations"></a>Limitacións coñecidas

- Ata 1 millón de perfís por exportación a Marketo.
- A exportación a Marketo está limitada a segmentos.
- A exportación de segmentos cun total de 1 millón de perfís pode levar ata 3 horas. 
- O número de perfís que pode exportar a Marketo depende e está limitado no seu contrato con Marketo.

## <a name="data-privacy-and-compliance"></a>Cumprimento e privacidade dos datos

Cando habilita Dynamics 365 Customer Insights para transmitir datos a Marketo, permite a transferencia de datos fóra do límite de cumprimento de Dynamics 365 Customer Insights, incluíndo datos potencialmente confidenciais como os datos persoais. Microsoft transferirá estes datos segundo a súa instrución, pero vostede é responsable de garantir que Marketo cumpra as obrigas de privacidade ou seguridade que poida ter. Para obter máis información, consulte a [Declaración de privacidade de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
O administrador de Dynamics 365 Customer Insights pode eliminar este destino de exportación en calquera momento para interromper o uso desta funcionalidade.


[!INCLUDE[footer-include](../includes/footer-banner.md)]