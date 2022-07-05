---
title: Exportar segmentos a Criteo (vista previa)
description: Aprende a configurar a conexión e a exportar a Criteo.
ms.date: 05/27/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ace9056d200a3179e442132004324a01f0d247b6
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082783"
---
# <a name="export-segments-to-criteo-preview"></a>Exportar segmentos a Criteo (vista previa)

Exporta segmentos de perfís de clientes unificados para xerar campañas, ofrecer marketing por correo electrónico e utilizar grupos específicos de clientes con Criteo.

## <a name="prerequisites-for-connection"></a>Requisitos previos para a conexión

-   Tes un [Conta de retargeting de Criteo Dynamics](https://www.criteo.com/login/) e as correspondentes credenciais de administrador.
-   Ten [segmentos configurados](segments.md).
-   Os perfís de clientes unificados nos segmentos exportados conteñen un campo que representa un enderezo de correo electrónico.

## <a name="known-limitations"></a>Limitacións coñecidas

- Ata 1 millón de perfís de clientes por exportación a Criteo.
- A exportación a Criteo está limitada a segmentos.
- A exportación de segmentos cun total de 1 millón de perfís de clientes pode levar ata 30 minutos. 
- O número de perfís de clientes que pode exportar a Criteo depende e está limitado do seu contrato con Criteo.

## <a name="set-up-connection-to-criteo"></a>Configura a conexión con Criteo

1. Vaia a **Administrar** > **Conexións**.

1. Seleccione **Engadir conexión** e escolle **Criteo** para configurar a conexión.

1. Déalle á conexión un nome recoñecible no campo **Nome para mostrar**. O nome e o tipo de conexión describen esta conexión. Recomendamos escoller un nome que explique o propósito e o destino da conexión.

1. Escolla quen pode usar esta conexión. Se non realiza ningunha acción, o valor predeterminado será Administradores. Para obter máis información, consulte [Permitir aos colaboradores usar unha conexión para as exportacións](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Seleccione **Estou de acordo** para confirmar o **Privacidade e cumprimento dos datos** e selecciona **Conectar** para inicializar a conexión con Criteo.

1. Seleccione **Autenticarse con Criteo** e proporcione o seu nome de usuario de administrador e credenciais para Criteo. 

1. Seleccione **Autoengadirse como usuario de exportación** e proporcione as súas credenciais de Customer Insights.

1. Seleccione **Gardar** para completar a conexión.

## <a name="configure-an-export"></a>Configurar unha exportación

Pode configurar esta exportación se ten acceso a unha conexión deste tipo. Para obter máis información, consulte [Permisos necesarios para configurar unha exportación](export-destinations.md#set-up-a-new-export).

1. Vaia a **Datos** > **Exportacións**.

1. Seleccione **Engadir destino** para crear unha nova exportación.

1. No **Conexión para exportación** campo, escolla unha conexión na sección de Criteo. Se non ve o nome desta sección, non hai conexións deste tipo dispoñibles para vostede. 

1. Na sección **Coincidencia de datos** do campo **Correo electrónico**, seleccione o campo que representa o enderezo de correo electrónico dun cliente. 

1. Opcionalmente, pode exportar **ID do anunciante** e **Nome**

1. Seleccione os segmentos que desexa exportar. 

1. Seleccione **Gardar**.

Ao gardar unha exportación non se executa a exportación inmediatamente.

A exportación execútase con cada [actualización programada](system.md#schedule-tab). Tamén pode [exportar datos baixo demanda](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Cumprimento e privacidade dos datos

Cando habilitas Dynamics 365 Customer Insights para transmitir datos a Criteo, permite a transferencia de datos fóra dos límites de conformidade Dynamics 365 Customer Insights, incluíndo datos potencialmente sensibles, como os datos persoais. Microsoft transferirá eses datos segundo as súas instrucións, pero vostede é responsable de asegurarse de que Criteo cumpra as obrigas de privacidade ou seguridade que poida ter. Para obter máis información, consulte a [Declaración de privacidade de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
O administrador de Dynamics 365 Customer Insights pode eliminar este destino de exportación en calquera momento para interromper o uso desta funcionalidade.


[!INCLUDE[footer-include](includes/footer-banner.md)]
