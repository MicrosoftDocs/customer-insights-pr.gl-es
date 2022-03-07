---
title: Esquemas de entidades de Customer Insights en Common Data Model
description: Traballe con entidades en Common Data Model.
ms.date: 08/13/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: f0af2a6d8a90ff01ea9d4eeb29f34113261fd0d4
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 02/16/2022
ms.locfileid: "8231011"
---
# <a name="entity-schemas-in-common-data-model"></a>Esquemas de entidades no Common Data Model



[Common Data Model](/common-data-model/) é unha especificación declarativa e unha definición de entidades estándar que representan conceptos e actividades de uso común en aplicacións empresariais e de produtividade. Este modelo estase estendendo a datos observacionais e analíticos tamén. O Common Data Model proporciona entidades comerciais ben definidas, modulares e extensibles, como contas, unidade de negocio, caso, contacto, cliente potencial, oportunidade e produto, así como interaccións con provedores, traballadores e clientes, como actividades e acordos de nivel de servizo. Calquera pode construír e ampliar as definicións do Common Data Model para capturar ideas adicionais específicas do negocio.

Este modelo de datos compartido permite ás aplicacións e aos integradores de datos colaborar máis facilmente proporcionando unha definición unificada de datos. O Common Data Model inclúe un sistema de metadatos enriquecidos con entidades estándar, relacións, xerarquías, trazos e moito máis. Orixínase de aplicacións de Dynamics 365 e é de código aberto en GitHub con máis de 260 entidades estándar. Un gran sistema de socios internos e externos contribúe con conceptos específicos da industria ao Common Data Model.

Varios sistemas e plataformas implementan o Common Data Model actualmente, incluído fluxos de datos de Power BI e Azure Data Services. Xa é compatible con Microsoft Dataverse, Dynamics 365, Power Apps, Power BI e os próximos servizos de datos de Azure, que acumularán directamente valor en [Open Data Initiative](https://www.microsoft.com/open-data-initiative).

## <a name="customer-insights-entity-schemas"></a>Esquemas de entidades de Customer Insights

Para establecer unha visión de 360 graos do cliente e facer os modelos de Customer Insights dispoñibles no Common Data Model para a amplialos, publicamos os seguintes esquemas de entidades:

| Entidade | Descrición |
|---------|---------|
|[CustomerActivity](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customeractivity) | Actividade realizada por un usuario que ten un valor observacional para a empresa. |
|[CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile) | Unha persoa ou organización que realizou ou ten potencial para exercer actividades de negocios. |
|[MeasureDefinition](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/measuredefinition) | Definición de KPI divididos por cero ou máis dimensións (por exemplo, usuarios activos mensuais, gasto total por cliente, custo medio de adquisición de clientes) |
|[Segmento](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segment) | Define un grupo de membros con trazos comúns. |
|[SegmentMembership](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segmentmembership) | Membros que participan nun determinado segmento. |

Para obter máis información, consulte a documentación sobre [Esquemas de entidades de Customer Insights no Common Data Model](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/overview).

## <a name="view-entities-using-the-common-data-model-entity-navigator"></a>Ver as entidades que utilizan o navegador de entidades de Common Data Model

Pode ver entidades no [Navegador de entidades de Common Data Model](https://microsoft.github.io/CDM/). Seleccione unha entidade na sección de aplicacións de Insights para obter a lista de entidades de Customer Insights e as súas definicións.
> [!div class="mx-imgBorder"]
> ![Navegador de entidades CDM que mostra a entidade CustomerActivity.](media/CDM-entity-navigator.png "Navegador de entidades CDM que mostra a entidade CustomerActivity")


[!INCLUDE[footer-include](../includes/footer-banner.md)]
