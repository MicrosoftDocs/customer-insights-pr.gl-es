---
title: Comezar coas contas de empresa como público obxectivo principal
description: Obteña información acerca das contas de empresa como público obxectivo principal Dynamics 365 Customer Insights.
ms.date: 10/19/2021
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.custom: intro-internal
ms.author: wimohabb
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-semantic-mapping
- ci-connections
- customerInsights
ms.openlocfilehash: 88882dc727c37262c9f204fbc8049abe17bd21a3
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 02/25/2022
ms.locfileid: "8353541"
---
# <a name="work-with-business-accounts-in-audience-insights"></a>Traballar con contas empresariais en estatísticas de público

A capacidade de información de público de Dynamics 365 Customer Insights permítelle configurar o seu contorno para diferentes públicos obxectivo principais: consumidores individuais (B-a-C) e contas empresariais (B-a-B). Nos escenarios B-a-C, os datos céntranse arredor das persoas. Para o B-a-B, o público obxectivo principal son as contas (organizacións ou empresas) e os contactos. Este artigo axúdalle a comezar cun ambiente para contas de empresas. Enumera as diferenzas para as áreas de funcións nas estatísticas do público, dependendo do foco do seu contorno. Para obter máis información sobre as diferenzas, revise os documentos das áreas de funcións. 

## <a name="create-an-environment-for-business-accounts"></a>Crear un contorno para contas de empresa

Os administradores poden [crear un ambiente nunha organización existente](create-environment.md). Un paso no proceso de creación dun novo contorno pide aos administradores o público obxectivo principal do contorno. No caso de que se trate da configuración inicial de información do público despois de mercar unha licenza, unha experiencia guiada axuda á creación do primeiro contorno.

A continuación, poderá [inxerir datos](data-sources.md) para contas comerciais e contactos relacionados como fontes de datos de todas as fontes compatibles.

Despois de unificar os datos, [especifique xerarquías de contas](relationships.md#set-up-account-hierarchies) como parte da configuración da relación. Tamén pode [configurar asignacións semánticas](semantic-mappings.md) para conectar entidades de contacto e de contas. 

## <a name="switch-between-primary-target-audience"></a>Cambiar entre o público obxectivo principal

Se a súa organización mantén contornos para clientes individuais e contas comerciais, pode usar o conmutador do panel esquerdo para escoller o público obxectivo principal.

:::image type="content" source="media/switch-primary-target-audience.png" alt-text="Cambiador para cambiar o público obxectivo principal entre clientes individuais e contas empresariais.":::

## <a name="supported-feature-areas"></a>Áreas de funcións compatibles

- [Actividades](activities.md): compatibilidade con contas e contactos relacionados para crear actividades e mostralas nunha liña de tempo.
- [Relacións](relationships.md): o asistente de actividades axuda a crear relacións entre as entidades para que a vista de conta poida amosar todas as actividades dos contactos. Os contactos pódense detallar para ver a vista de contactos e as xerarquías pódense usar para agregar actividades de contas.
- [Medidas](measures.md): Admite as medidas creadas a partir do creador de medidas cun só cálculo. Unha configuración opcional permite a acumulación de subcontas ao crear medidas.
- [Segmentos](segments.md): admite segmentos creados desde cero co creador de segmentos. Os novos operadores permiten incorporar a xerarquía de contas ao construír segmentos.
- [Inxestión de datos](data-sources.md): todas as funcións desta área son iguais para as contas comerciais e os clientes individuais.
- [Unificación de datos](data-unification.md): todas as funcións desta área son iguais para as contas comerciais e os clientes individuais.
- [Enriquecemento](enrichment-hub.md): Algúns tipos de enriquecemento están dispoñibles só para escenarios de clientes individuais, mentres que outros están dispoñibles exclusivamente para contas comerciais.
- [Predicións e modelos listos para usar](predictions-overview.md): A predición do abandono de transaccións contén pasos adicionais para as contas da empresa. Outras predicións só están dispoñibles para clientes individuais.
- [Activación e exportación](export-destinations.md): As exportacións están dispoñibles para contas comerciais e clientes individuais. Algunhas exportacións requiren configuración adicional e información de contacto proxectada nos segmentos subxacentes para ser válida para as contas comerciais.
- [Configuración do sistema](system.md) e [xestión de usuarios](permissions.md): todas as funcións desta área son iguais para as contas comerciais e os clientes individuais.

