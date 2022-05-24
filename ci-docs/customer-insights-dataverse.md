---
title: Datos de Customer Insights en Microsoft Dataverse
description: Use as entidades de Customer Insights como táboas en Microsoft Dataverse.
ms.date: 04/05/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 1e629cd218b104b115f74f59a53a14e9d60fcc8a
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741363"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Traballar con datos de Customer Insights en Microsoft Dataverse

Customer Insights ofrece a opción de pór dispoñibles as entidades de saída en [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). Esta integración permite compartir datos sinxelos e desenvolvemento personalizado a través dun enfoque de código baixo/sen código. O [entidades de saída](#output-entities) están dispoñibles como táboas en a Dataverse ambiente. Podes usar os datos para calquera outra aplicación baseada en Dataverse táboas. Estas táboas permiten escenarios como fluxos de traballo automatizados Power Automate ou crear aplicacións con Power Apps. A implementación actual admite principalmente buscas nas que se poden obter datos das entidades de Customer Insights dispoñibles para un determinado ID de cliente.

## <a name="attach-a-dataverse-environment-to-customer-insights"></a>Anexar un ambiente de Dataverse a Customer Insights

**Organización existente**

Os administradores poden configurar Customer Insights para [utilizar un existente Dataverse ambiente](create-environment.md) cando crean un ambiente de Customer Insights. Ao proporcionar o URL ao Dataverse ambiente, está unido ao seu novo ambiente de Customer Insights. Información do cliente e Dataverse os ambientes deben estar aloxados na mesma rexión. 

Se non queres utilizar un existente Dataverse ambiente, o sistema crea un novo ambiente para os datos de Customer Insights no seu inquilino. 

> [!NOTE]
> Se as túas organizacións xa usan Dataverse no seu inquilino, é importante lembralo [Dataverse a creación do ambiente está controlada por un administrador](/power-platform/admin/control-environment-creation) . Por exemplo, se estás configurando un novo ambiente de Customer Insights coa túa conta da organización e o administrador desactivou a creación de Dataverse ambientes de proba para todos, excepto para administradores, non podes crear un novo ambiente de proba.
> 
> Os ambientes de proba de Dataverse creados en Customer Insights teñen 3 GB de almacenamento que non contarán para a capacidade total á que ten dereito o arrendatario. As subscricións de pago reciben o dereito de Dataverse a 15 GB para a base de datos e 20 GB para o almacenamento de ficheiros.

**Nova organización**

Se crea unha nova organización ao configurar Customer Insights, o sistema crea automaticamente unha nova Dataverse ambiente na súa organización para vostede.

## <a name="output-entities"></a>Entidades de saída

Algunhas entidades de saída de Customer Insights están dispoñibles como táboas Dataverse. As seccións seguintes describen o esquema esperado destas táboas.

- [CustomerProfile](#customerprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Enriquecemento](#enrichment)
- [Predición](#prediction)
- [Segmento de pertenza](#segment-membership)


### <a name="customerprofile"></a>CustomerProfile

Esta táboa contén o perfil de cliente unificado de Customer Insights. O esquema para un perfil de cliente unificado depende das entidades e atributos utilizados no proceso de unificación de datos. Un esquema de perfil de cliente normalmente contén un subconxunto dos atributos da [definición de Common Data Model de CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile).

### <a name="alternatekey"></a>AlternateKey

A táboa AlternateKey contén as claves das entidades que participaron no proceso de unificación.

|Column  |Tipo  |Descripción  |
|---------|---------|---------|
|DataSourceName    |String         | Nome da orixe de datos. Por exemplo: `datasource5`        |
|EntityName        | String        | Nome da entidade en Customer Insights. Por exemplo: `contact1`        |
|AlternateValue    |String         |ID alternativo que está asignado ao ID de cliente. Exemplo: `cntid_1078`         |
|KeyRing           | Texto de varias liñas        | Valor JSON  </br> Exemplo: [{"dataSourceName":" datasource5 ",</br>"entityName":" contact1",</br>"preferredKey":" cntid_1078",</br>"keys":[" cntid_1078"]}]       |
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
| SegmentProvider      | String       | Aplicación que publica os segmentos.      |
| SegmentMembershipType | String       | Tipo de cliente deste segmento rexistro de pertenza. Admite varios tipos, como Cliente, Contacto ou Conta. Valor predeterminado: cliente  |
| Segmentos       | Cadea JSON  | Lista de segmentos únicos dos que é membro o perfil do cliente      |
| msdynci_identifier  | String   | Identificador único do rexistro de pertenza ao segmento. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| msdynci_segmentmembershipid | GUID      | GUID determinista xerado a partir de`msdynci_identifier`          |
