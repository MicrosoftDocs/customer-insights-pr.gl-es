---
title: Exemplos de consulta de OData para as API de Customer Insights
description: Exemplos de uso habitual do protocolo de datos abertos (OData) para consultar as API de Customer Insights para revisar datos.
ms.date: 05/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 54ba9f4e9baeb4b7021bb8c20a706bbb6eb1529f
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "9083161"
---
# <a name="odata-query-examples-for-customer-insights-apis"></a>Exemplos de consulta de OData para as API de Customer Insights

O protocolo de datos abertos (OData) é un protocolo de acceso a datos construído en protocolos básicos como HTTP. Utiliza metodoloxías comúnmente aceptadas como REST para a web. Existen varios tipos de bibliotecas e ferramentas que se poden usar para consumir servizos de OData.

Este artigo enumera algunhas consultas de exemplo que se solicitan con frecuencia para axudarche a crear as túas propias implementacións baseadas no [API de Customer Insights](apis.md).

Ten que modificar as mostras de consulta para que funcionen nos ambientes de destino: 

- {serviceRoot}:`https://api.ci.ai.dynamics.com/v1/instances/{instanceId}` onde{instanceId} é o GUID do contorno de Customer Insights que quere consultar. O [Operación ListAllInstances](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) permíteche atopar o{InstanceId} tes acceso.
- {CID}: GUID dun rexistro de cliente unificado. Exemplo:`ce759201f786d590bf2134bff576c369`.
- {AlternateKey}: identificador da clave primaria dun rexistro de cliente nun orixe de datos. Exemplo: `CNTID_1002`
- {DSname}: Cadea co nome de entidade dun orixe de datos que se inxire en Customer Insights. Exemplo:`Website_contacts`.
- {SegmentName}: Cadea co nome da entidade de saída dun segmento en Customer Insights. Exemplo:`Male_under_40`.

## <a name="customer"></a>cliente/a

A seguinte táboa contén un conxunto de consultas de exemplo para o *Cliente* entidade.

|Tipo de consulta |Exemplo  | Nota  |
|---------|---------|---------|
|ID de cliente único     | `{serviceRoot}/Customer?$filter=CustomerId eq '{CID}'`          |  |
|Clave alternativa    | `{serviceRoot}/Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} eq '{AlternateKey}'`         |  As claves alternativas persisten na entidade cliente unificada       |
|Seleccionar   | `{serviceRoot}/Customer?$select=CustomerId,FullName&$filter=customerid eq '1'`        |         |
|En    | `{serviceRoot}/Customer?$filter=CustomerId in ('{CID1}',’{CID2}’)`        |         |
|Clave alternativa + In   | `Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} in ('{AlternateKey}','{AlternateKey}')`         |         |
|Buscar  | `{serviceRoot}/Customer?$top=10&$skip=0&$search="string"`        |   Devolve os 10 primeiros resultados para unha cadea de busca      |
|Segmento de pertenza  | `{serviceRoot}/Customer?select=*&$filter=IsMemberOfSegment('{SegmentName}')&$top=10`     | Devolve un número predefinido de filas da entidade de segmentación.      |

## <a name="unified-activity"></a>Actividade unificada

A seguinte táboa contén un conxunto de consultas de exemplo para o *Actividade unificada* entidade.

|Tipo de consulta |Exemplo  | Nota  |
|---------|---------|---------|
|Actividade do CID     | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}'`          | Lista actividades dun perfil de cliente específico |
|Temporalización da actividade    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityTime gt 2017-01-01T00:00:00.000Z and ActivityTime lt 2020-01-01T00:00:00.000Z`     |  Actividades dun perfil de cliente nun marco temporal       |
|Tipo de actividade    |   `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityType eq '{ActivityName}'`        |         |
|Actividade por nome de visualización     | `{serviceRoot}/UnifiedActivity$filter=CustomerId eq ‘{CID}’ and ActivityTypeDisplay eq ‘{ActivityDisplayName}’`        | |
|Clasificación de actividades    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq ‘{CID}’ & $orderby=ActivityTime asc`     |  Ordenar as actividades ascendentes ou descendentes       |
|A actividade expandiuse desde a pertenza ao segmento  |   `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId eq '{CID}'`     |         |

## <a name="other-examples"></a>Outros exemplos

A seguinte táboa contén un conxunto de consultas de exemplo para outras entidades.

|Tipo de consulta |Exemplo  | Nota  |
|---------|---------|---------|
|Medidas de CID    | `{serviceRoot}/Customer_Measure?$filter=CustomerId eq '{CID}'`          |  |
|Marcas enriquecidas de CID    | `{serviceRoot}/BrandShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`  |       |
|Intereses enriquecidos do CID    |   `{serviceRoot}/InterestShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`       |         |
|In-Clause + Expandir     | `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId in ('{CID}', '{CID}')`         | |

## <a name="not-supported-odata-queries"></a>Consultas OData non compatibles

As seguintes consultas non son compatibles con Customer Insights:

- `$filter` sobre entidades fonte inxeridas. Só pode executar consultas $filter nas entidades do sistema que crea Customer Insights.
- `$expand` dende a`$search` consulta. Exemplo: `Customer?$expand=UnifiedActivity$top=10&$skip=0&$search="corey"`
- `$expand` dende`$select` se só se selecciona un subconxunto de atributos. Exemplo: `Customer?$select=CustomerId,FullName&$expand=UnifiedActivity&$filter=CustomerId eq '{CID}'`
- `$expand` marca enriquecida ou afinidades de interese para un determinado cliente. Exemplo: `Customer?$expand=BrandShareOfVoiceFromMicrosoft&$filter=CustomerId eq '518291faaa12f6d853c417835d40eb10'`
- Consulta as entidades de saída do modelo predición a través de clave alternativa. Exemplo: `OOBModelOutputEntity?$filter=HotelCustomerID eq '{AK}'`
