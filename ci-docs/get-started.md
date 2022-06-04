---
title: Comezar a utilizar Dynamics 365 Customer Insights
description: Unha visión xeral de Customer Insights axuda aos recursos a comezar rapidamente.
ms.reviewer: v-wendysmith
ms.author: mhart
author: m-hartmann
ms.date: 04/12/2022
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: 1a19d83930d667bdca5301dcc5a3ffa5db6a7bdc
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741131"
---
# <a name="get-started-with-dynamics-365-customer-insights"></a>Comezar a utilizar Dynamics 365 Customer Insights

Customer Insights pode axudarche a construír unha comprensión máis profunda dos teus clientes. Conecte datos de varias fontes transaccionais, de comportamento e de observación para crear unha vista dos clientes integral. Use estes datos para dirixir experiencias e procesos centrados nos clientes. Unifique e comprenda os datos dos clientes e aproveiteos para obter información e accións intelixentes.

## <a name="step-1-create-an-environment"></a>Paso 1: Crear un ambiente

Para comezar, primeiro ten que crear un ambiente no que traballar. Se a súa organización xa adquiriu unha licenza, consulte [Crea un ambiente](create-environment.md). Para iniciar unha proba de Customer Insights, consulte [Configura un ambiente de proba](trial-signup.md).

## <a name="step-2-explore-customer-insights"></a>Paso 2: Explore os datos do cliente

A primeira vez que inicie sesión en Customer Insights, pode configurar a configuración e explorar o produto.

1. [inicia sesión en Customer Insights](https://home.ci.ai.dynamics.com) usando o teu Microsoft Azure Active Directory (AAD) conta de usuario.

1. [Cambia o ambiente](manage-environments.md#switch-environments) para ver datos de demostración e [explorar Customer Insights](home.md).

## <a name="step-3-ingest-unify-and-set-up-relationships-for-your-data"></a>Paso 3: inxerir, unificar e establecer relacións para os seus datos

Os perfís unificados son a base para obter información e tomar medidas sobre os datos. Traia datos de varias fontes e execute o proceso de unificación de datos para combinar perfís unificados. Especificar as relacións entre as entidades inxeridas usan funcións de enriquecemento para engadir información aos perfís.

1. Inxira datos creando fontes de datos a partir de varias opcións. Escolle entre [Power Query conectores](connect-power-query.md), a [Cartafol Common Data Model](connect-common-data-model.md), ou [Microsoft Dataverse](connect-dataverse-managed-lake.md). 

1. Executar o [proceso de unificación de datos](data-unification.md) mediante a identificación do [campos de orixe](map-entities.md), eliminando [duplicados](remove-duplicates.md),[condicións de coincidencia](match-entities.md), e [unificando campos](merge-entities.md).

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

1. Revisa as opcións de integración, por exemplo con outras aplicacións de Dynamics 365 co [Complemento da tarxeta de cliente](customer-card-add-in.md).  


[!INCLUDE [footer-include](includes/footer-banner.md)]