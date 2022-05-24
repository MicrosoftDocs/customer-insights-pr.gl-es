---
title: Exemplos de OData para o Dynamics 365 Customer Insights APIs
description: Exemplos de uso habitual do protocolo de datos abertos (OData) para consultar as API de Customer Insights para revisar datos.
ms.date: 05/10/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 007278e1330e1a8e64d524ded8496acaf83b874c
ms.sourcegitcommit: a50c5e70d2baf4db41a349162fd1b1f84c3e03b6
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 05/11/2022
ms.locfileid: "8740065"
---
# <a name="odata-query-examples"></a>Exemplos de consulta OData

O protocolo de datos abertos (OData) é un protocolo de acceso a datos construído en protocolos básicos como HTTP. Utiliza metodoloxías comúnmente aceptadas como REST para a web. Existen varios tipos de bibliotecas e ferramentas que se poden usar para consumir servizos de OData.

Este artigo enumera algunhas consultas de exemplo que se solicitan con frecuencia para axudarche a crear as túas propias implementacións baseadas no [API de Customer Insights](apis.md).

Ten que modificar as mostras de consulta para que funcionen nos ambientes de destino: 

- {serviceRoot}:`https://api.ci.ai.dynamics.com/v1/instances/{instanceId}` onde{instanceId} é o GUID do entorno de Customer Insights que quere consultar. O [Operación ListAllInstances](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) permíteche atopar o{InstanceId} tes acceso.
- {CID}: GUID dun rexistro de cliente unificado. Exemplo:`ce759201f786d590bf2134bff576c369`.
- {AlternateKey}: identificador da clave primaria dun rexistro de cliente nun orixe de datos. Exemplo: `CNTID_1002`
- {DSname}: Cadea co nome de entidade dun orixe de datos que se inxire en Customer Insights. Exemplo:`Website_contacts`.
- {SegmentName}: Cadea co nome da entidade de saída dun segmento en Customer Insights. Exemplo:`Male_under_40`.

## <a name="customer"></a>cliente/a

A seguinte táboa contén un conxunto de consultas de exemplo para o *Cliente* entidade.


|Tipo de consulta |Exemplo  | Nota  |
|---------|---------|---------|
|ID de cliente único     | `{serviceRoot}/Customer?$filter=CustomerId eq '{CID}'`          |  |
|Clave alternativa    | `{serviceRoot}/Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} eq '{AlternateKey}' `         |  As claves alternativas persisten na entidade cliente unificada       |
|Seleccionar   | `{serviceRoot}/Customer?$select=CustomerId,FullName&$filter=customerid eq '1'`        |         |
|En    | `{serviceRoot}/Customer?$filter=CustomerId in ('{CID1}',’{CID2}’)`        |         |
|Clave alternativa + In   | `Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} in ('{AlternateKey}','{AlternateKey}')`         |         |
|Buscar  | `{serviceRoot}/Customer?$top=10&$skip=0&$search="string"`        |   Devolve os 10 primeiros resultados para unha cadea de busca      |
|Segmento de pertenza  | `{serviceRoot}/Customer?select=*&$filter=IsMemberOfSegment('{SegmentName}')&$top=10  `     | Devolve un número predefinido de filas da entidade de segmentación.      |

## <a name="unified-activity"></a>Actividade unificada

A seguinte táboa contén un conxunto de consultas de exemplo para o *Actividade unificada* entidade.

|Tipo de consulta |Exemplo  | Nota  |
|---------|---------|---------|
|Actividade do CID     | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}'`          | Lista actividades dun perfil de cliente específico |
|Temporalización da actividade    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityTime gt 2017-01-01T00:00:00.000Z and ActivityTime lt 2020-01-01T00:00:00.000Z`     |  Actividades dun perfil de cliente nun marco temporal       |
|Tipo de actividade    |   `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityType eq '{ActivityName}'`        |         |
|Actividade por nome de visualización     | `{serviceRoot}/UnifiedActivity$filter=CustomerId eq ‘{CID}’ and ActivityTypeDisplay eq ‘{ActivityDisplayName}’ `        | |
|Clasificación de actividades    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq ‘{CID}’ & $orderby=ActivityTime asc`     |  Ordenar as actividades ascendente ou descendente       |
|A actividade expandiuse desde a pertenza ao segmento  |   `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId eq '{CID}'`     |         |

## <a name="other-examples"></a>Outros exemplos

A seguinte táboa contén un conxunto de consultas de exemplo para outras entidades.

|Tipo de consulta |Exemplo  | Nota  |
|---------|---------|---------|
|Medidas de CID    | `{serviceRoot}/Customer_Measure?$filter=CustomerId eq '{CID}'`          |  |
|Marcas enriquecidas de CID    | `{serviceRoot}/BrandShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`  |       |
|Intereses enriquecidos do CID    |   `{serviceRoot}/InterestShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`       |         |
|In-Clause + Expandir     | `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId in ('{CID}', '{CID}')`         | |
