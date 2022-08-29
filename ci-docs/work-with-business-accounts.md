---
title: Traballar con contas de negocio
description: Obtén información sobre as contas empresariais como público obxectivo principal en Dynamics 365 Customer Insights.
ms.date: 10/19/2021
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.custom: intro-internal
ms.author: wimohabb
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-semantic-mapping
- ci-connections
- customerInsights
ms.openlocfilehash: abb77a720ab737520a905b0c93b65573e669109f
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 08/16/2022
ms.locfileid: "9303914"
---
# <a name="work-with-business-accounts"></a>Traballar con contas de negocio

O Dynamics 365 Customer Insights permíteche configurar o teu ambiente para diferentes públicos obxectivos principais: consumidores individuais (B-to-C) e contas empresariais (B-to-B). Nos escenarios B-a-C, os datos céntranse arredor das persoas. Para o B-a-B, o público obxectivo principal son as contas (organizacións ou empresas) e os contactos. Este artigo axúdalle a comezar cun ambiente para contas de empresas. Enumera as diferenzas para as áreas de funcións en Customer Insights, dependendo do foco do teu contorno. Para obter máis información sobre as diferenzas, revise os documentos das áreas de funcións. 

## <a name="create-an-environment-for-business-accounts"></a>Crear un contorno para contas de empresa

Os administradores poden [crear un ambiente nunha organización existente](create-environment.md). Un paso no proceso de creación dun novo contorno pide aos administradores o público obxectivo principal do contorno. No caso de que se trate da configuración inicial despois de comprar unha licenza, unha experiencia guiada axuda coa creación do primeiro ambiente.

A continuación, poderá [inxerir datos](data-sources.md) para contas comerciais e contactos relacionados como fontes de datos de todas as fontes compatibles.

 [Unificar](data-unification.md) os datos da túa conta seguidos dos teus datos de contacto para conectar as entidades de contacto e conta.

## <a name="switch-between-primary-target-audience"></a>Cambiar entre o público obxectivo principal

Se a súa organización mantén contornos para clientes individuais e contas comerciais, pode usar o conmutador do panel esquerdo para escoller o público obxectivo principal.

:::image type="content" source="media/switch-primary-target-audience.png" alt-text="Cambiador para cambiar o público obxectivo principal entre clientes individuais e contas empresariais.":::

## <a name="supported-feature-areas"></a>Áreas de funcións compatibles

- [Actividades](activities.md): compatibilidade con contas e contactos relacionados para crear actividades e mostralas nunha liña de tempo.
- [Relacións](relationships.md): o asistente de actividades axuda a crear relacións entre as entidades para que a vista de conta poida amosar todas as actividades dos contactos. Os contactos pódense detallar para ver a vista de contactos e as xerarquías pódense usar para agregar actividades de contas.
- [Medidas](measures.md): Admite as medidas creadas a partir do creador de medidas cun só cálculo. Unha configuración opcional permite a acumulación de subcontas ao crear medidas.
- [Segmentos](segments.md): admite segmentos creados desde cero co creador de segmentos. Os segmentos poden estar baseados en contas ou contactos.
- [Inxestión de datos](data-sources.md): todas as funcións desta área son iguais para as contas comerciais e os clientes individuais.
- A unificación de datos B-to-B é moi semellante á unificación de datos B-to-C, pero ten un paso adicional para unificar os contactos despois da unificación da conta. Ver [Contas empresariais (B-to-B)](data-unification.md).
- [Enriquecemento](enrichment-hub.md): Algúns tipos de enriquecemento están dispoñibles só para escenarios de clientes individuais, mentres que outros están dispoñibles exclusivamente para contas comerciais.
- [Predicións e modelos listos para usar](predictions-overview.md): A predición do abandono de transaccións contén pasos adicionais para as contas da empresa. Outras predicións só están dispoñibles para clientes individuais.
- [Activación e exportación](export-destinations.md): As exportacións están dispoñibles para contas comerciais e clientes individuais. Algunhas exportacións requiren configuración adicional e información de contacto proxectada nos segmentos subxacentes para ser válida para as contas comerciais.
- [Configuración do sistema](system.md) e [xestión de usuarios](permissions.md): todas as funcións desta área son iguais para as contas comerciais e os clientes individuais.

[!INCLUDE [footer-include](includes/footer-banner.md)]
