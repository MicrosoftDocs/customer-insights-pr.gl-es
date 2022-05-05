---
title: Exportar datos de Customer Insights a LinkedIn Ads
description: Aprenda a configurar a conexión e exportar a LinkedIn Ads.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: bf1d12ffbd7a4cfd7d268fea8a1f90cc37589e00
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642930"
---
# <a name="export-segments-to-linkedin-ads-preview"></a>Exportar segmentos a LinkedIn Ads (versión preliminar)

Exporte segmentos de perfís de clientes unificados a LinkedIn Ads para crear públicos coincidentes. Utilice os públicos coincidentes para dirixirse ás empresas e aos contactos.

## <a name="prerequisites"></a>Requisitos previos

-   Ten unha [conta de LinkedIn Campaign Manager](https://business.linkedin.com/marketing-solutions/ads) e as correspondentes credenciais de administrador.
-   Tes [segmentos configurados](segments.md) en Customer Insights.
-   Os perfís de clientes dos segmentos exportados conteñen un campo cun enderezo de correo electrónico.

## <a name="known-limitations"></a>Limitacións coñecidas

- O teu segmento en Customer Insights debe conter polo menos 300 perfís únicos. 
- Pode exportar ata 100.000 perfís de clientes por exportación a LinkedIn Ads.
- A exportación a LinkedIn Ads está limitada a segmentos.
- A exportación de ata 100.000 perfís de clientes a LinkedIn Ads pode levar ata 10 minutos en completarse. 

## <a name="set-up-the-connection-to-linkedin-ads"></a>Configurar a conexión a LinkedIn Ads

1. Vaia a **Administrar** > **Conexións**.

1. Seleccione **Engadir conexión** e elixa **LinkedIn Ads** para configurar a conexión.

1. Déalle á conexión un nome recoñecible no campo **Nome para mostrar**. O nome e o tipo de conexión describen esta conexión. Recomendamos escoller un nome que explique o propósito e o destino da conexión.

1. Escolla quen pode usar esta conexión. Se non realiza ningunha acción, o valor predefinido será administradores. Para obter máis información, consulte [Permitir aos colaboradores usar unha conexión para as exportacións](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Proporcione o [ID da conta de LinkedIn Campaign Manager](https://www.linkedin.com/help/lms/answer/a424270).

1. Seleccione **Estou de acordo** para confirmar a **Privacidade e cumprimento dos datos**.

1. Seleccione **Conectar** para iniciar a conexión a Campaign Monitor.

1. Seleccione **Autenticarse con LinkedIn** e proporcione as súas credenciais de administrador de LinkedIn Campaign Manager.

1. Seleccione **Autoengadirse como usuario de exportación** e proporcione as súas credenciais de Customer Insights.

1. Seleccione **Gardar** para completar a conexión.

## <a name="configure-an-export"></a>Configurar unha exportación

Pode configurar unha exportación se ten acceso a unha conexión deste tipo. Para obter máis información, consulte [Permisos necesarios para configurar unha exportación](export-destinations.md#set-up-a-new-export).

1. Vaia a **Datos** > **Exportacións**.

1. Seleccione **Engadir destino** para crear unha nova exportación.

1. No campo **Conexión da exportación**, escolla unha conexión da sección LinkedIn Ads. Se non ve o nome desta sección, non hai conexións deste tipo dispoñibles para vostede.

1. Escolla se quere exportar datos para [dirixirse aos contactos](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) ou [dirixirse ás empresas](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) en LinkedIn. 

1. Na sección **Coincidencia de datos**, para a orientación por contactos, seleccione polo menos un campo que represente un enderezo de correo electrónico dun cliente, Apple Ad ID, Google Ad ID, Google User ID ou nome e apelidos. Se escolle a orientación por empresa, seleccione polo menos un campo que represente un nome de empresa, dominio de correo electrónico, URL da páxina de LinkedIn, símbolo de acción ou sitio web. Pódense seleccionar campos adicionais para definir a exportación. 

1. Seleccione os segmentos que desexa exportar. Os públicos coincidentes en LinkedIn Campaign Manager crearanse automaticamente co nome dos segmentos que seleccionou para exportar. Cada segmento dará lugar a un público coincidente diferente. 

1. Seleccione **Gardar**.

Ao gardar unha exportación non se executa a exportación inmediatamente.

A exportación execútase con cada [actualización programada](system.md#schedule-tab). Tamén pode [exportar datos baixo demanda](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Cumprimento e privacidade dos datos

Cando habilita Dynamics 365 Customer Insights para transmitir datos a LinkedIn Ads, permite a transferencia de datos fóra do límite de cumprimento de Dynamics 365 Customer Insights, incluíndo datos potencialmente confidenciais como os datos persoais. Microsoft transferirá estes datos segundo a súa instrución, pero vostede é responsable de asegurarse de que LinkedIn Ads cumpra as obrigas de privacidade ou seguridade que poida ter. Para obter máis información, consulte a [Declaración de privacidade de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

O administrador de Dynamics 365 Customer Insights pode eliminar este destino de exportación en calquera momento para deter o uso desta funcionalidade.
