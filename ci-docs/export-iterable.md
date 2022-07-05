---
title: Exportar segmentos a Iterable (vista previa)
description: Aprende a configurar a conexión e a exportar a Iterable.
ms.date: 03/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 98d5aeab6b0e932d291213053d509ec72da82e47
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "9052233"
---
# <a name="export-segments-to-iterable-preview"></a>Exportar segmentos a Iterable (vista previa)

Exporta segmentos de perfís de clientes unificados a Iterable e utilízaos para actividades de mercadotecnia.

## <a name="prerequisites"></a>Requisitos previos

-   Tes un [Conta iterable](https://iterable.com/) e as correspondentes credenciais de administrador.
-   Tes [segmentos configurados](segments.md) en Customer Insights.
-   Os perfís de clientes unificados nos segmentos exportados conteñen un campo que representa un enderezo de correo electrónico.

## <a name="known-limitations"></a>Limitacións coñecidas

- A exportación a Iterable está limitada a segmentos.
- A exportación de ata 1 millón de perfís de clientes a Iterable pode levar ata 30 minutos. 
- O número de perfís de clientes que pode exportar a Iterable depende e está limitado do seu contrato con Iterable.

## <a name="set-up-connection-to-iterable"></a>Configura a conexión a Iterable

1. Vaia a **Administrar** > **Conexións**.

1. Seleccione **Engadir conexión** e escolle **Iterable** para configurar a conexión.

1. Déalle á conexión un nome recoñecible no campo **Nome para mostrar**. O nome e o tipo de conexión describen esta conexión. Recomendamos escoller un nome que explique o propósito e o destino da conexión.

1. Escolla quen pode usar esta conexión. Se non realiza ningunha acción, o valor predeterminado será Administradores. Para obter máis información, consulte [Permitir aos colaboradores usar unha conexión para as exportacións](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Proporciona o teu [Clave API iterable](https://support.iterable.com/hc/en-us/articles/360043464871) para continuar iniciando sesión. 

1. Seleccione **Estou de acordo** para confirmar a **Privacidade e cumprimento dos datos**.

1. Seleccione **Conectar** para inicializar a conexión a Iterable.

1. Seleccione **Autoengadirse como usuario de exportación** e proporcione as súas credenciais de Customer Insights.

1. Seleccione **Gardar** para completar a conexión.

## <a name="configure-an-export"></a>Configurar unha exportación

Pode configurar esta exportación se ten acceso a unha conexión deste tipo. Para obter máis información, consulte [Permisos necesarios para configurar unha exportación](export-destinations.md#set-up-a-new-export).

1. Vaia a **Datos** > **Exportacións**.

1. Seleccione **Engadir destino** para crear unha nova exportación.

1. No **Conexión para exportación** campo, escolla unha conexión na sección Iterable. Se non ve o nome desta sección, non hai conexións deste tipo dispoñibles para vostede.

3. Na sección **Coincidencia de datos** do campo **Correo electrónico**, seleccione o campo que representa o enderezo de correo electrónico dun cliente. É necesario exportar segmentos a Iterable. A lista creada en Iterable recibirá exactamente o mesmo nome que o nome do seu segmento en Dynamics 365 Customer Insights.

1. Seleccione **Gardar**.

Ao gardar unha exportación non se executa a exportación inmediatamente.

A exportación execútase con cada [actualización programada](system.md#schedule-tab). Tamén pode [exportar datos baixo demanda](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Cumprimento e privacidade dos datos

Cando habilitas Dynamics 365 Customer Insights para transmitir datos a Iterable, permite a transferencia de datos fóra do límite de conformidade para Dynamics 365 Customer Insights, incluíndo datos potencialmente sensibles, como os datos persoais. Microsoft transferirá eses datos segundo as súas instrucións, pero vostede é responsable de asegurarse de que Iterable cumpra as obrigas de privacidade ou seguridade que poida ter. Para obter máis información, consulte a [Declaración de privacidade de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

O administrador de Dynamics 365 Customer Insights pode eliminar este destino de exportación en calquera momento para interromper o uso desta funcionalidade.
