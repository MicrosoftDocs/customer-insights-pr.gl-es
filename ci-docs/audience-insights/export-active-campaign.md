---
title: Exportar datos de Customer Insights a ActiveCampaign
description: Aprenda a configurar a conexión e exportar a ActiveCampaign.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 4fbdd5a51a3df35d31ad072eef64d20ee967d7ee
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 10/08/2021
ms.locfileid: "7618151"
---
# <a name="export-segments-to-activecampaign-preview"></a>Exportar segmentos a ActiveCampaign (versión preliminar)

Exporte segmentos de perfís de clientes unificados a ActiveCampaign e utilíceos para actividades de mercadotecnia.

## <a name="prerequisites"></a>Requisitos previos

-   Ten unha [conta de ActiveCampaign](https://www.activecampaign.com/) e as correspondentes credenciais de administrador.
-   Ten [segmentos configurados](segments.md) na información do público.
-   Os perfís de clientes unificados nos segmentos exportados conteñen un campo cun enderezo de correo electrónico.

## <a name="known-limitations"></a>Limitacións coñecidas

- Pode exportar ata 1 millón de perfís de clientes por exportación a ActiveCampaign e pode levar ata 90 minutos en completarse.
- A exportación a ActiveCampaign está limitada a segmentos.
- O número de perfís de clientes que pode exportar a ActiveCampaign depende do seu contrato con ActiveCampaign.

## <a name="set-up-connection-to-activecampaign"></a>Configurar conexión a ActiveCampaign

1. Vaia a **Administrar** > **Conexións**.

1. Seleccione **Engadir conexión** e elixa **ActiveCampaign** para configurar a conexión.

1. Déalle á conexión un nome recoñecible no campo **Nome para mostrar**. O nome e o tipo de conexión describen esta conexión. Recomendamos escoller un nome que explique o propósito e o destino da conexión.

1. Escolla quen pode usar esta conexión. Por defecto, só son os administradores. Para obter máis información, consulte [Permitir aos colaboradores usar unha conexión para as exportacións](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduza a súa [Clave da API de ActiveCampaign e o nome de servidor do extremo de REST](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key). O nome do servidor do extremo de REST é só o nome do servidor, sen https://. 

1. Seleccione **Estou de acordo** para confirmar a **Privacidade e cumprimento dos datos**.

1. Seleccione **Conectar** para iniciar a conexión a ActiveCampaign.

1. Seleccione **Autoengadirse como usuario de exportación** e proporcione as súas credenciais de Customer Insights.

1. Seleccione **Gardar** para completar a conexión.

## <a name="configure-an-export"></a>Configurar unha exportación

Pode configurar unha exportación se ten acceso a unha conexión deste tipo. Para obter máis información, consulte [Permisos necesarios para configurar unha exportación](export-destinations.md#set-up-a-new-export).

1. Vaia a **Datos** > **Exportacións**.

1. Seleccione **Engadir destino** para crear unha nova exportación.

1. No campo **Conexión para a exportación**, escolla unha conexión na sección ActiveCampaign. Se non ve o nome desta sección, non hai conexións deste tipo dispoñibles para vostede.

1. Introduza o seu [**ID de lista de ActiveCampaign**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).    

1. Na sección **Coincidencia de datos** do campo **Correo electrónico**, seleccione o campo que representa o enderezo de correo electrónico dun cliente. É necesario exportar segmentos a ActiveCampaign. Opcionalmente, pode exportar nome, apelidos e Teléfono para crear correos electrónicos máis personalizados. Seleccione Engadir atributo para asignar estes campos.

1. Seleccione **Gardar**.

Ao gardar unha exportación non se executa a exportación inmediatamente.

A exportación execútase con cada [actualización programada](system.md#schedule-tab). Tamén pode [exportar datos baixo demanda](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Cumprimento e privacidade dos datos

Cando permite a Dynamics 365 Customer Insights transmitir datos a ActiveCampaign, permite a transferencia de datos fóra do límite de cumprimento de Dynamics 365 Customer Insights, incluíndo datos potencialmente confidenciais como os datos persoais. Microsoft transferirá estes datos segundo a súa instrución, pero vostede é responsable de asegurarse de que ActiveCampaign cumpre coas obrigacións de privacidade ou seguridade que poida ter. Para obter máis información, consulte a [Declaración de privacidade de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

O administrador de Dynamics 365 Customer Insights pode eliminar este destino de exportación en calquera momento para interromper o uso desta funcionalidade.
