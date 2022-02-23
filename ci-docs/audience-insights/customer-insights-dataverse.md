---
title: Datos de Customer Insights en Microsoft Dataverse
description: Usa as entidades de Customer Insights como táboas en Microsoft Dataverse.
ms.date: 11/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 6f74559b34a95ed976a4e353c2dbabe59e1a8839
ms.sourcegitcommit: 9558ff772ee6c944fcb8db4bfc8cda13b38a1bff
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 11/29/2021
ms.locfileid: "7866932"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Traballa cos datos de Customer Insights en Microsoft Dataverse

Customer Insights ofrece a opción de facer as entidades de saída dispoñibles en [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro.md). Esta integración permite compartir datos e desenvolver de forma personalizada facilmente mediante un enfoque de pouco código ou sen código. As entidades de saída estarán dispoñibles como táboas en Dataverse. Estas táboas permiten escenarios como [fluxos de traballo automatizados a través de Power Automate](/power-automate/getting-started),[aplicacións dirixidas por modelos](/powerapps/maker/model-driven-apps/) e [aplicacións de lenzo](/powerapps/maker/canvas-apps/) a través de Power Apps. Podes usar os datos para calquera outra aplicación que estea baseada en táboas Dataverse. A implantación actual admite principalmente buscas onde se poden obter datos das entidades de información do público dispoñibles para un determinado ID de cliente.

## <a name="attach-a-dataverse-environment-to-customer-insights"></a>Anexa un ambiente Dataverse a Customer Insights

**Organizacións con contornos Dataverse existentes**

As organizacións que xa usan Dataverse poden [use un dos seus ambientes Dataverse existentes](create-environment.md) cando un administrador configura os coñecementos sobre o público. Ao fornecer o URL para o ambiente Dataverse, engádese ao seu novo ambiente de información sobre a audiencia. Para garantir o mellor rendemento posible, os ambientes Customer Insights e Dataverse deben estar aloxados na mesma rexión.

**Nova organización**

Se creas unha nova organización ao configurar Customer Insights, obterás automaticamente un novo ambiente Dataverse.

> [!NOTE]
> Se as túas organizacións xa usan Dataverse no seu inquilino, é importante lembrar que [A creación do ambiente Dataverse está controlada por un administrador](/power-platform/admin/control-environment-creation.md) . Por exemplo, se estás a configurar un novo ambiente de información sobre o público coa túa conta da organización e o administrador desactivou a creación de ambientes de proba Dataverse para todos, excepto para os administradores, non poderás crear un novo ambiente de proba.
> 
> Os contornos de proba de Dataverse creados en Customer Insights teñen 3 GB de almacenamento que non contarán para a capacidade total que lle corresponde ao inquilino. As subscricións de pago teñen dereito a Dataverse de 15 GB para a base de datos e 20 GB para o almacenamento de ficheiros.

## <a name="output-entities"></a>Entidades de saída

Algunhas entidades de saída das estatísticas do público están dispoñibles como táboas en Dataverse. As seccións seguintes describen o esquema esperado destas táboas.

- [CustomerProfile](#customerprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Enriquecemento](#enrichment)
- [Predición](#prediction)
- [Segmento de pertenza](#segment-membership)


### <a name="customerprofile"></a>CustomerProfile

Esta táboa contén o perfil de cliente unificado de Customer Insights. O esquema dun perfil de cliente unificado depende das entidades e atributos empregados no proceso de combinación. Un esquema de perfil de cliente normalmente contén un subconxunto dos atributos da [definición de Common Data Model de CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile).

### <a name="alternatekey"></a>AlternateKey

A táboa AlternateKey contén as claves das entidades que participaron no proceso de unificación.

|Column  |Tipo  |Descripción  |
|---------|---------|---------|
|DataSourceName    |String         | Nome da orixe de datos. Por exemplo: `datasource5`        |
|EntityName        | String        | Nome da entidade na información do público. Por exemplo: `contact1`        |
|AlternateValue    |String         |ID alternativo que está asignado ao ID de cliente. Exemplo: `cntid_1078`         |
|KeyRing           | Texto de varias liñas        | Valor JSON  </br> Exemplo: [{"dataSourceName":" datasource5 ",</br>"entityName":" contact1",</br>"preferredKey":" cntid_1078",</br>"claves":[" cntid_1078"]}]       |
|CustomerId         | String        | ID do perfil de cliente unificado.         |
|AlternateKeyId     | GUID         |  GUID determinista de AlternateKey baseado en msdynci_identifier       |
|msdynci_identifier |   String      |   `DataSourceName|EntityName|AlternateValue`  </br> Exemplo: `testdatasource|contact1|cntid_1078`    |

### <a name="unifiedactivity"></a>UnifiedActivity

Esta táboa contén actividades dos usuarios dispoñibles en Customer Insights.

| Column            | Tipo        | Descripción                                                                              |
|-------------------|-------------|------------------------------------------------------------------------------------------|
| CustomerId        | String      | ID do perfil do cliente                                                                      |
| ActivityId        | String      | ID interno da actividade do cliente (clave principal)                                       |
| SourceEntityName  | String      | Nome da entidade de orixe                                                                |
| SourceActivityId  | String      | Clave principal da entidade de orixe                                                       |
| ActivityType      | String      | Tipo de actividade semántica ou nome da actividade personalizada                                        |
| ActivityTimeStamp | DATAHORA    | Marca de hora da actividade                                                                      |
| Título             | String      | Título ou nome da actividade                                                               |
| Descripción       | String      | Descrición da actividade                                                                     |
| Enderezo URL               | String      | Ligazón a un URL externo específico da actividade                                         |
| SemanticData      | Cadea JSON | Inclúe unha lista de pares clave-valor para campos de asignación semántica específicos do tipo de actividade |
| RangeIndex        | String      | Marca de hora de Unix empregada para ordenar a liña de tempo da actividade e as consultas de alcance efectivas |
| mydynci_unifiedactivityid   | GUID | ID interno da actividade do cliente (ActivityId) |

### <a name="customermeasure"></a>CustomerMeasure

Esta táboa contén os datos de saída das medidas baseadas en atributos do cliente.

| Column             | Tipo             | Descripción                 |
|--------------------|------------------|-----------------------------|
| CustomerId         | String           | ID do perfil do cliente        |
| Medidas           | Cadea JSON      | Inclúe unha lista de pares clave-valor para o nome e os valores da medida para o cliente indicado | 
| msdynci_identifier | String           | `Customer_Measure|CustomerId` |
| msdynci_customermeasureid | GUID      | ID do perfil do cliente |


### <a name="enrichment"></a>Enriquecemento

Esta táboa contén a saída do proceso de enriquecemento.

| Column               | Tipo             |  Descripción                                          |
|----------------------|------------------|------------------------------------------------------|
| CustomerId           | String           | ID do perfil do cliente                                 |
| EnrichmentProvider   | String           | Nome do fornecedor do enriquecemento                                  |
| EnrichmentType       | String           | Tipo de enriquecemento                                      |
| Valores               | Cadea JSON      | Lista de atributos producidos polo proceso de enriquecemento |
| msdynci_enrichmentid | GUID             | GUID determinista xerado a partir de msdynci_identifier |
| msdynci_identifier   | String           | `EnrichmentProvider|EnrichmentType|CustomerId`         |

### <a name="prediction"></a>Predición

Esta táboa contén a saída das predicións do modelo.

| Column               | Tipo        | Descripción                                          |
|----------------------|-------------|------------------------------------------------------|
| CustomerId           | String      | ID do perfil do cliente                                  |
| ModelProvider        | String      | Nome do fornecedor do modelo                                      |
| Modelo                | String      | Nome do modelo                                                |
| Valores               | Cadea JSON | Lista de atributos producidos polo modelo |
| msdynci_predictionid | GUID        | GUID determinista xerado a partir de msdynci_identifier | 
| msdynci_identifier   | String      |  `Model|ModelProvider|CustomerId`                      |

### <a name="segment-membership"></a>Segmento de pertenza

Esta táboa contén información sobre a pertenza ao segmento dos perfís de clientes.

| Column        | Tipo | Descripción                        |
|--------------------|--------------|-----------------------------|
| CustomerId        | String       | ID do perfil do cliente        |
| SegmentProvider      | String       | Aplicación que publica os segmentos. Valor predeterminado: información sobre o público         |
| SegmentMembershipType | String       | Tipo de cliente deste segmento rexistro de pertenza. Admite varios tipos, como Cliente, Contacto ou Conta. Valor predeterminado: cliente  |
| Segmentos       | Cadea JSON  | Lista de segmentos únicos dos que é membro o perfil do cliente      |
| msdynci_identifier  | String   | Identificador único do rexistro de pertenza ao segmento. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| msdynci_segmentmembershipid | GUID      | GUID determinista xerado a partir de`msdynci_identifier`          |
