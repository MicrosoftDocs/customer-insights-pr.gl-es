---
title: Exportar segmentos a Autopilot (versión preliminar)
description: Aprenda a configurar a conexión e exportar a Autopilot.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e3af3d03e70c4ce9d229c84c582ec4f302be8c9f
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082531"
---
# <a name="export-segments-to-autopilot-preview"></a>Exportar segmentos a Autopilot (versión preliminar)

Exporte segmentos de perfís de clientes unificados a Autopilot e utilíceos para campañas e mercadotecnia por correo electrónico en Autopilot. 

## <a name="prerequisites-for-a-connection"></a>Requisitos previos para unha conexión

-   Ten unha [Conta de Autopilot](https://www.autopilothq.com/) e as correspondentes credenciais de administrador.
-   Tes [segmentos configurados](segments.md) en Customer Insights.
-   Os perfís de clientes unificados nos segmentos exportados conteñen un campo que representa un enderezo de correo electrónico.

## <a name="known-limitations"></a>Limitacións coñecidas

- Pode exportar ata 100.000 perfís de clientes en total ao piloto automático.
- A exportación a Autopilot está limitada a segmentos.
- A exportación de ata 100.000 perfís de clientes ao piloto automático pode tardar unhas horas en completarse. 
- O número de perfís de clientes que pode exportar ao piloto automático depende e está limitado ao seu contrato co piloto automático.

## <a name="set-up-connection-to-autopilot"></a>Configurar conexión a Autopilot

1. Vaia a **Administrar** > **Conexións**.

1. Seleccione **Engadir conexión** e elixa **Autopilot** para configurar a conexión.

1. Déalle á conexión un nome recoñecible no campo **Nome para mostrar**. O nome e o tipo de conexión describen esta conexión. Recomendamos escoller un nome que explique o propósito e o destino da conexión.

1. Escolla quen pode usar esta conexión. Se non realiza ningunha acción, o valor predeterminado será Administradores. Para obter máis información, consulte [Permitir aos colaboradores usar unha conexión para as exportacións](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduza a súa [Clave da API de Autopilot](https://autopilot.docs.apiary.io/#).

1. Seleccione **Estou de acordo** para confirmar a **Privacidade e cumprimento dos datos**.

1. Seleccione **Conectar** para inicializar a conexión a Autopilot.

1. Seleccione **Autoengadirse como usuario de exportación** e proporcione as súas credenciais de Customer Insights.

1. Seleccione **Gardar** para completar a conexión.

## <a name="configure-an-export"></a>Configurar unha exportación

Pode configurar esta exportación se ten acceso a unha conexión deste tipo. Para obter máis información, consulte [Permisos necesarios para configurar unha exportación](export-destinations.md#set-up-a-new-export).

1. Vaia a **Datos** > **Exportacións**.

1. Seleccione **Engadir destino** para crear unha nova exportación.

1. No campo **Conexión da exportación** escolla unha conexión da sección Autopilot. Se non ve o nome desta sección, non hai conexións deste tipo dispoñibles para vostede.

1. Na sección **Coincidencia de datos** do campo **Correo electrónico**, seleccione o campo que representa o enderezo de correo electrónico dun cliente. Repita os mesmos pasos para outros campos opcionais como **nome**, **apelidos**.

1. Seleccione os segmentos que desexa exportar. Nós fortemente **recomendamos non exportar máis de 100.000 perfís de clientes en total** a Autopilot. 

1. Seleccione **Gardar**.

Ao gardar unha exportación non se executa a exportación inmediatamente.

A exportación execútase con cada [actualización programada](system.md#schedule-tab). Tamén pode [exportar datos baixo demanda](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Cumprimento e privacidade dos datos

Cando habilita Dynamics 365 Customer Insights para transmitir datos a Autopilot, permite a transferencia de datos fóra do límite de cumprimento de Dynamics 365 Customer Insights, incluíndo datos potencialmente confidenciais como os datos persoais. Microsoft transferirá estes datos segundo a súa instrución, pero vostede é responsable de garantir que Autopilot cumpra as obrigas de privacidade ou seguridade que poida ter. Para obter máis información, consulte a [Declaración de privacidade de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
O administrador de Dynamics 365 Customer Insights pode eliminar este destino de exportación en calquera momento para interromper o uso desta funcionalidade.


[!INCLUDE [footer-include](includes/footer-banner.md)]
