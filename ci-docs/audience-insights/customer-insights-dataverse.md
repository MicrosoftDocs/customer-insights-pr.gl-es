---
title: Datos de Customer Insights en Microsoft Dataverse
description: Use as entidades de Customer Insights como táboas en Microsoft Dataverse.
ms.date: 06/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 7157ad930f3cea17c12bd4f95028d291483329d3
ms.sourcegitcommit: e5425f060c8d80f9510283dc610ce70a4e709b1e
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 06/15/2021
ms.locfileid: "6259189"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Traballar con datos de Customer Insights en Microsoft Dataverse

Customer Insights ofrece a opción de pór dispoñibles as entidades de saída en [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro.md). Esta integración permite compartir datos e desenvolver de forma personalizada facilmente mediante un enfoque de pouco código ou sen código. As entidades de saída estarán dispoñibles como táboas en Dataverse. Estas táboas permiten escenarios como [fluxos de traballo automatizados mediante Power Automate](/power-automate/getting-started), [aplicacións controladas por modelos](/powerapps/maker/model-driven-apps/) e [aplicacións de lenzo](/powerapps/maker/canvas-apps/) mediante Power Apps. Pode usar os datos para calquera outra aplicación baseada en táboas de Dataverse. A implantación actual admite principalmente buscas onde se poden obter datos das entidades de información do público dispoñibles para un determinado ID de cliente.

## <a name="attach-a-dataverse-environment-to-customer-insights"></a>Anexar un ambiente de Dataverse a Customer Insights

**Organizacións con ambientes existentes de Dataverse**

As organizacións que xa utilizan Dataverse poden [usar un dos seus ambientes existentes de Dataverse](manage-environments.md#create-an-environment-in-an-existing-organization) cando un administrador configura a información do público. Ao proporcionar o URL ao ambiente de Dataverse, anéxase ao seu novo ambiente de información do público. Para garantir o mellor desempeño posible, os ambientes de Customer Insights e Dataverse deben estar aloxados na mesma rexión.

Para anexar un ambiente de Dataverse, expanda a **Configuración avanzada** ao crear o ambiente de información do público. Proporcione o **URL do ambiente de Microsoft Dataverse** e seleccione a caixa de verificación para **Activar o uso compartido de datos**.

:::image type="content" source="media/Datasharing-with-DataverseMDL.png" alt-text="alt":::

**Nova organización**

Se crea unha nova organización ao configurar Customer Insights, obterá automaticamente un novo ambiente de Dataverse.

> [!NOTE]
> Se as súas organizacións xa usan Dataverse no seu arrendatario, é importante recordar que [a creación de ambientes de Dataverse está controlada por un administrador](/power-platform/admin/control-environment-creation.md). Por exemplo, se está configurando un novo ambiente de información do público coa súa conta de organización e o administrador desactivou a creación de ambientes de proba de Dataverse para todos excepto para os administradores, non pode crear un novo ambiente de proba.
> 
> Os ambientes de proba de Dataverse creados en Customer Insights teñen 3 GB de almacenamento que non contarán para a capacidade total á que ten dereito o arrendatario. As subscricións de pago reciben o dereito de Dataverse a 15 GB para a base de datos e 20 GB para o almacenamento de ficheiros.

## <a name="output-entities"></a>Entidades de saída

Algunhas entidades de saída da información do público están dispoñibles como táboas en Dataverse. As seccións seguintes describen o esquema esperado destas táboas.

- [CustomerProfile](#customerprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Enriquecemento](#enrichment)
- [Predición](#prediction)


### <a name="customerprofile"></a>CustomerProfile

Esta táboa contén o perfil de cliente unificado de Customer Insights. O esquema dun perfil de cliente unificado depende das entidades e atributos empregados no proceso de combinación. Un esquema de perfil de cliente normalmente contén un subconxunto dos atributos da [definición de Common Data Model de CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile).

### <a name="alternatekey"></a>AlternateKey

A táboa AlternateKey contén as claves das entidades que participaron no proceso de unificación.

|Column  |Tipo  |Descripción  |
|---------|---------|---------|
|DataSourceName    |String         | Nome da orixe de datos. Por exemplo: `datasource5`        |
|EntityName        | String        | Nome da entidade na información do público. Por exemplo: `contact1`        |
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
