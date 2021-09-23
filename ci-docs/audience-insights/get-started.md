---
title: Comezar coa capacidade de información do público en Dynamics 365 Customer Insights
description: Unha visión xeral da información do público axuda aos recursos a comezar rapidamente.
ms.reviewer: mhart
ms.author: mhart
author: m-hartmann
ms.date: 08/31/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: aaaf1848df175469d8af07754ac153b777781ffb
ms.sourcegitcommit: 971716c761871cee390519cacef617dac21ecd60
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 09/01/2021
ms.locfileid: "7466575"
---
# <a name="get-started-with-dynamics-365-customer-insights-audience-insights-capability"></a>Comezar coa capacidade de información do público de Dynamics 365 Customer Insights

A información do público pode axudalo a comprender máis profundamente os seus clientes. Conecte datos de varias fontes transaccionais, de comportamento e de observación para crear unha vista dos clientes integral. Use estes datos para dirixir experiencias e procesos centrados nos clientes. Unifique e comprenda os datos dos clientes e aproveiteos para obter información e accións intelixentes.

## <a name="step-1-create-an-environment"></a>Paso 1: Crear un ambiente

Para comezar, primeiro ten que crear un ambiente no que traballar. Se a súa organización xa adquiriu unha licenza, consulte [Comezar cunha subscrición de pago](get-started-paid.md). Para comezar unha proba de información sobre o público, consulte [Configure un ambiente de proba](get-started-trial.md). 

## <a name="step-2-explore-audience-insights"></a>Paso 2: explorar a información do público

A primeira vez que inicie sesión en información sobre o público, pode configurar a configuración e explorar o produto.

1. [Inicie sesión na información do público](https://home.ci.ai.dynamics.com) usando a súa conta de usuario de Microsoft Azure Active Directory (AAD).

1. [Cambie o ambiente](manage-environments.md#switch-environments) para ver datos de demostración e [explorar información do público](home.md).

##  <a name="step-3-ingest-unify-and-set-up-relationships-for-your-data"></a>Paso 3: inxerir, unificar e establecer relacións para os seus datos

Os perfís unificados son a base para obter información e tomar medidas sobre os datos. Traia datos de varias fontes e execute o proceso de unificación de datos para combinar perfís unificados. Especificar as relacións entre as entidades inxeridas usan funcións de enriquecemento para engadir información aos perfís. 

1. Inxira datos creando fontes de datos a partir de varias opcións. Escolla entre [conectores de Power Query](connect-power-query.md), un [Cartafol de Modelo de datos comúns](connect-common-data-model.md) ou [Microsoft Dataverse](connect-common-data-service-lake.md). 

1. Execute o [proceso de unificación de datos](data-unification.md) percorrendo as fases [mapa](map-entities.md), [coincidencia](match-entities.md) e [combinación](merge-entities.md).

1. Familiarícese coas [entidades que crea o sistema](entities.md) e cree [relacións entre as entidades inxeridas](relationships.md).
    
## <a name="step-4-enhance-unified-profiles-with-predictions-activities-and-measures"></a>Paso 4: mellorar os perfís unificados con predicións, actividades e medidas

Con perfís unificados configurados, pode mellorar os seus datos e aumentar aínda máis a información que proporcionan.

1. Escolla entre unha biblioteca en expansión de provedores de enriquecemento para [enriquecer os seus datos de clientes](enrichment-hub.md).

1. Use [modelos listos para usar](predictions-overview.md) para predicir a probabilidade de renovación ou os ingresos esperados.

1. [Configure actividades](activities.md) baseándose en datos inxeridos e visualice as interaccións cos seus clientes nunha liña de tempo cronolóxica. 

1. [Constrúa medidas](measures.md) para medir os seus obxectivos comerciais e KPI.
 
## <a name="step-5-create-segments-and-activate-data-through-various-export-options"></a>Paso 5: crear segmentos e activar datos a través de varias opcións de exportación

Agora que os seus datos están completos e conteñen unha ampla gama de información sobre os seus clientes, é hora de buscar formas de actuar sobre estes datos. 

1. [Cree segmentos](segments.md), subconxuntos da súa base de clientes, para garantir que as súas accións sexan relevantes para os clientes obxecto de aprendizaxe.

1. Explore o catálogo en expansión de [opcións de exportación](export-destinations.md) onde pode usar os datos do cliente. Por exemplo, pode usar datos para xestionar promocións e contactar co márketing dixital.

1. Revise as opcións de integración, por exemplo coa [conexión directa coa información de interacción](../engagement-insights/integrate-audience-insights-engagement-insights.md) ou a outras aplicacións de Dynamics 365 co [Complemento de tarxeta de cliente](customer-card-add-in.md).  


[!INCLUDE[footer-include](../includes/footer-banner.md)]
