---
title: Introdución á capacidade de información de interacción
description: Unha visión xeral dos recursos de axuda para comezar rapidamente.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 12/21/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 5ee1567cea834670a16aaa3253912b7957ce26b3
ms.sourcegitcommit: 86739a3f238162fc96837270b5d184e648fab15c
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 08/20/2021
ms.locfileid: "7405356"
---
# <a name="get-started-with-dynamics-365-customer-insights-engagement-insights-capability-public-preview"></a>Introdución á capacidade de información de interacción (versión preliminar pública) de Dynamics 365 Customer Insights

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

A capacidade de información de interacción permítelle recompilar e medir o comportamento dos clientes no seu sitio web. Integra a capacidade de información do público para que poida ver análises de comportamento enriquecidas en tempo real xunto con informes de perfís de clientes. As ligazóns deste artigo axúdanlle a configurar rapidamente o seu ambiente.

## <a name="step-1-review-prerequisites"></a>Paso 1: Revise os requisitos previos

En primeiro lugar, debe ter unha conta de usuario de Microsoft Azure Active Directory activa. A continuación, lea os seguintes artigos antes de configurar unha área de traballo de información de interacción.

- Revise e acepte as [Condicións de servizo](terms-of-service.md) de Microsoft.  
- Lea o artigo sobre a [Xestión das cookies e o consentimento do usuario](user-consent-storage.md). Despois de revisar este artigo, avalíe se precisa actualizar a notificación de consentimento do usuario. Se anteriormente non tiña cookies "non esenciais", é probable que precise actualizar a política do seu sitio.
- Revise o [glosario](glossary.md) para obter unha introdución rápida a termos e conceptos clave.

## <a name="step-2-explore-engagement-insights"></a>Paso 2: Explore a información de interacción

A primeira vez que visite a información de interacción, pode configurar as opcións, revisar as políticas e explorar o produto.

1. Inicie sesión no [portal da capacidade de información de interacción](https://pi.dynamics.com) usando a súa conta de usuario de Microsoft Azure Active Directory. (Pode ser a conta de traballo ou escolar).

1. Seleccione a súa rexión e use a caixa de verificación para indicar se quere optar por recibir actualizacións e ofertas por correo electrónico.

1. Revise as **Condicións de uso da información de interacción (versión preliminar)** e a **Declaración de privacidade** e seleccione **Explorar a demostración** para aceptalas.

1. Explore o produto usando un conxunto de datos de exemplo.

##  <a name="step-3-set-up-a-workspace-and-add-code-to-your-website"></a>Paso 3: Configure unha área de traballo e engada código ao sitio web

A área de traballo é o lugar no que pode ver a actividade dos usuarios en tempo real e almacenar e xestionar informes. Engada código ao sitio web para comezar a recompilar *eventos*, os datos de actividade que chegan dos usuarios.

1. [Cree unha área de traballo](create-workspace.md) e engada membros.

1. [Engada o código ao seu sitio web](instrument-website.md) ou [aplicación móbil](developer-resources.md#capture-events-from-mobile-apps) para ver a actividade do usuario chegar ao seu espazo de traballo.

1. Consulte un [informe en tempo real](view-reports.md) que mostra os usuarios activos por explorador, dispositivo, sistema operativo, localización e idioma. Tamén pode crear [informes personalizados](custom-reports.md) para obter as súas propias visualizacións.
    
## <a name="step-4-export-data-to-other-channels"></a>Paso 4: Exportar datos a outras canles

Pode crear *eventos refinados* (unha visualización virtual) dos seus datos de análise web. Despois, filtre e exporte os datos a Azure Data Lake Storage. Pode inxerir os datos exportados como orixe de datos. Para obter máis información, consulte [Crear unha ligazón entre a información do público e a información de interacción](integrate-audience-insights-engagement-insights.md).

1. [Cree eventos refinados](refined-events.md) para exportar.

1. [Exporte os datos](export-events.md) a Data Lake Storage.

1. Obteña información acerca de como [eliminar e exportar datos de eventos que conteñan información persoal](delete-export-personal-data.md).
 
## <a name="step-5-stay-connected"></a>Paso 5: Manterse conectado

Agradecemos a súa participación activa e teremos en conta todos os comentarios relevantes no desenvolvemento de futuras versións. Comparta os seus comentarios e informe dos problemas a través dunha destas canles:
- [Comunidade](https://go.microsoft.com/fwlink/?linkid=2141648)
- [Fornecer comentarios](https://go.microsoft.com/fwlink/?linkid=2143222)
- [Solicitude de asistencia](https://go.microsoft.com/fwlink/?linkid=2145734) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
