---
title: Exportar rexistros de diagnóstico (vista previa)
description: Aprende a enviar rexistros a Microsoft Azure Monitor.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: article
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 60b039173fd938482c782c7394420d4951c222a7
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245923"
---
# <a name="export-diagnostic-logs-preview"></a>Exportar rexistros de diagnóstico (vista previa)

Reenviar rexistros de Customer Insights mediante Azure Monitor. Os rexistros de recursos de Azure Monitor permítenlle supervisar e enviar rexistros [Almacenamento Azure](https://azure.microsoft.com/services/storage/),[Azure Log Analytics](/azure/azure-monitor/logs/log-analytics-overview), ou transmitilos en streaming [Azure Event Hubs](https://azure.microsoft.com/services/event-hubs/).

Customer Insights envía os seguintes rexistros de eventos:

- **Auditoría de eventos**
  - **Evento APIE** - permite o seguimento de cambios a través de Dynamics 365 Customer Insights IU.
- **Eventos Operativos**
  - **Evento de fluxo de traballo** - permíteche configurar [fontes de datos](data-sources.md),[unificar](data-unification.md),[enriquecer](enrichment-hub.md), e [exportar](export-destinations.md) datos noutros sistemas. Estes pasos pódense facer individualmente (por exemplo, activar unha única exportación). Tamén poden executarse orquestrados (por exemplo, a actualización de datos a partir de fontes de datos que desencadean o proceso de unificación, que incorporará enriquecementos e exportará os datos a outro sistema). Para obter máis información, consulte o [Esquema WorkflowEvent](#workflow-event-schema).
  - **Evento APIE** - envía todas as chamadas API da instancia dos clientes Dynamics 365 Customer Insights. Para obter máis información, consulte o [Esquema APIEvent](#api-event-schema).

## <a name="set-up-the-diagnostic-settings"></a>Configura a configuración de diagnóstico

### <a name="prerequisites"></a>Requisitos previos

- Un activo [Subscrición Azure](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/).
- [Administrador](permissions.md#admin) permisos en Customer Insights.
- [Rol de colaborador e administrador de acceso de usuarios](/azure/role-based-access-control/role-assignments-portal) no recurso de destino en Azure. O recurso pode ser un Azure Data Lake Storage conta, un Azure Event Hub ou un espazo de traballo de Azure Log Analytics. Este permiso é necesario ao configurar os axustes de diagnóstico en Customer Insights, pero pódese cambiar despois da configuración correcta.
- [Requisitos do destino](/azure/azure-monitor/platform/diagnostic-settings#destination-requirements) para Azure Storage, Azure Event Hub ou Azure Log Analytics se cumpren.
- Polo menos o **Lector** papel no grupo de recursos ao que pertence o recurso.

### <a name="set-up-diagnostics-with-azure-monitor"></a>Configura diagnósticos con Azure Monitor

1. En Customer Insights, vai a **Admin** > **Sistema** e selecciona o **Diagnóstico** ficha.

1. Seleccione **Engadir destino**.

   :::image type="content" source="media/diagnostics-pane.png" alt-text="Conexión de diagnóstico.":::

1. Proporcione un nome no **Nome do destino de diagnóstico** campo.

1. Seleccione o **Tipo de recurso** (Conta de almacenamento, Centro de eventos ou Log Analytics).

1. Seleccione o **Subscrición**, **de recursos**, e **Recurso** para o recurso de destino. Ver [Configuración no recurso de destino](#configuration-on-the-destination-resource) para obter permisos e información de rexistro.

1. Revisa o [privacidade e cumprimento dos datos](connections.md#data-privacy-and-compliance) e selecciona **Estou de acordo**.

1. Seleccione **Conectar ao sistema** para conectarse ao recurso de destino. Os rexistros comezan a aparecer no destino despois de 15 minutos, se a API está en uso e xera eventos.

## <a name="configuration-on-the-destination-resource"></a>Configuración no recurso de destino

En función do tipo de recurso que escolla, prodúcense automaticamente os seguintes cambios:

### <a name="storage-account"></a>Conta de almacenamento

O principal do servizo de Customer Insights obtén o **Colaborador da conta de almacenamento** permiso sobre o recurso seleccionado e crea dous contedores baixo o espazo de nomes seleccionado:

- `insight-logs-audit` que contén **eventos de auditoría**
- `insight-logs-operational` que contén **eventos operativos**

### <a name="event-hub"></a>Centro de eventos

O principal do servizo de Customer Insights obtén o **Propietario de datos de Azure Event Hubs** permiso sobre o recurso e crea dous Event Hubs baixo o espazo de nomes seleccionado:

- `insight-logs-audit` que contén **eventos de auditoría**
- `insight-logs-operational` que contén **eventos operativos**

### <a name="log-analytics"></a>Log Analytics

O principal do servizo de Customer Insights obtén o **Colaborador de Log Analytics** permiso sobre o recurso. Os rexistros están dispoñibles en **Rexistros** > **Táboas** > **Xestión de rexistros** no espazo de traballo de Log Analytics seleccionado. Amplía o **Xestión de rexistros** solución e localizar o`CIEventsAudit` e`CIEventsOperational` táboas.

- `CIEventsAudit` que contén **eventos de auditoría**
- `CIEventsOperational` que contén **eventos operativos**

Baixo a **Consultas** fiestra, expanda o **Auditoría** solución e localice as consultas de exemplo proporcionadas ao buscar `CIEvents`.

## <a name="remove-a-diagnostics-destination"></a>Eliminar un destino de diagnóstico

1. Ir a **Admin** > **Sistema** e selecciona o **Diagnóstico** ficha.

1. Seleccione o destino de diagnóstico na lista.

   > [!TIP]
   > Ao eliminar o destino detén o reenvío de rexistro, pero non elimina o recurso na subscrición de Azure. Para eliminar o recurso en Azure, seleccione a ligazón no ficheiro **Accións** columna para abrir o portal de Azure para o recurso seleccionado e elimínao alí. A continuación, elimine o destino do diagnóstico.

1. No **Accións** columna, seleccione a **Eliminar** ícona.

1. Confirme a eliminación para eliminar o destino e deter o reenvío de rexistro.

## <a name="log-categories-and-event-schemas"></a>Categorías de rexistro e esquemas de eventos

Actualmente [Eventos da API](apis.md) e os eventos de fluxo de traballo son compatibles e aplícanse as seguintes categorías e esquemas.
O esquema de rexistro segue o [Esquema común de Azure Monitor](/azure/azure-monitor/platform/resource-logs-schema#top-level-common-schema).

### <a name="categories"></a>Categorías

Customer Insights ofrece dúas categorías:

- **Auditoría de eventos** :[Eventos da API](#api-event-schema) para rastrexar os cambios de configuración no servizo. `POST|PUT|DELETE|PATCH` operacións entran nesta categoría.
- **Eventos operativos** :[Eventos da API](#api-event-schema) ou [eventos de fluxo de traballo](#workflow-event-schema) xerado ao utilizar o servizo.  Por exemplo,`GET` solicitudes ou eventos de execución dun fluxo de traballo.

## <a name="event-schemas"></a>Esquemas de eventos

Os eventos da API e os eventos de fluxo de traballo teñen unha estrutura común, pero con algunhas diferenzas. Para obter máis información, consulte [Esquema de eventos da API](#api-event-schema) ou [esquema de eventos de fluxo de traballo](#workflow-event-schema).

### <a name="api-event-schema"></a>Esquema de eventos da API

| Campo             | Tipo de datos  | Obrigatorio/Opcional | Descripción       | Exemplo        |
| ----------------- | --------- | ----------------- | --------------------- | ------------------------ |
| `time`            | Marca de hora | Obrigatorio          | Marca de tempo do evento (UTC)       | `2020-09-08T09:48:14.8050869Z`         |
| `resourceId`      | String    | Obrigatorio          | ResourceId da instancia que emitiu o evento         | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX`  |
| `operationName`   | String    | Obrigatorio          | Nome da operación representada por este evento.                                                                                                                | `Workflows.GetWorkFlowStatusAsync`                                                                                                                                       |
| `category`        | String    | Obrigatorio          | Categoría de rexistro do evento. Calquera cousa`Operational` ou `Audit`. Todas as solicitudes HTTP POST/PUT/PATCH/DELETE están etiquetadas con`Audit`, todo o demais con`Operational` | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resultType`      | String    | Obrigatorio          | Estado do evento. `Success`,`ClientError`,`Failure`                                                                                                        |                                                                                                                                                                          |
| `resultSignature` | String    | Opcional          | Estado do resultado do evento. Se a operación corresponde a unha chamada á API REST, é o código de estado HTTP.        | `200`             |
| `durationMs`      | Longo      | Opcional          | Duración da operación en milisegundos.     | `133`     |
| `callerIpAddress` | String    | Opcional          | Enderezo IP da persoa que chama, se a operación corresponde a unha chamada API procedente dun enderezo IP dispoñible publicamente.                                                 | `144.318.99.233`         |
| `identity`        | String    | Opcional          | Obxecto JSON que describe a identidade do usuario ou aplicación que fixo a operación.       | Ver [Identidade](#identity-schema) sección.     |  
| `properties`      | String    | Opcional          | Obxecto JSON con máis propiedades para a categoría particular de eventos.      | Ver [Propiedades](#api-properties-schema) sección.    |
| `level`           | String    | Obrigatorio          | Grao de gravidade do evento.    | `Informational`,`Warning`,`Error`, ou `Critical`.           |
| `uri`             | String    | Opcional          | URI de solicitude absoluta.    |               |

#### <a name="identity-schema"></a>Esquema de identidade

O`identity` O obxecto JSON ten a seguinte estrutura

```json
{
  "Authorization" : {
    "UserRole": "Admin",
    "RequiredRoles": [
      "Contributor",
      "Viewer"
      ]
    },
  "Claims" {
    "claimNameX" : "claimValueX",
    "claimNameY" : "claimValueY"
   }
}  
```

| Campo                         | Descripción                                                                                                                          |
| ----------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| `Authorization.UserRole`      | Función asignada ao usuario ou á aplicación. Para obter máis información, consulte [permisos de usuario](permissions.md).                                     |
| `Authorization.RequiredRoles` | Papeis necesarios para realizar a operación. `Admin` Permítese facer todas as operacións.                                                    |
| `Claims`                      | Reivindicacións do token web JSON (JWT) do usuario ou da aplicación. As propiedades das reclamacións varían segundo a organización e a Azure Active Directory configuración. |

#### <a name="api-properties-schema"></a>Esquema de propiedades da API

[Eventos da API](apis.md) teñen as seguintes propiedades.

| Campo                        | Descripción                                                                                                            |
| ---------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| `properties.eventType`       | Sempre`ApiEvent`, marcando o evento de rexistro como evento da API.                                                                 |
| `properties.userAgent`       | Axente do navegador que envía a solicitude ou `unknown`.                                                                        |
| `properties.method`          | Método HTTP:`GET/POST/PUT/PATCH/HEAD`.                                                                                |
| `properties.path`            | Camiño relativo da solicitude.                                                                                          |
| `properties.origin`          | URI que indica de onde procede unha recuperación ou `unknown`.                                                                  |
| `properties.operationStatus` | `Success` para o código de estado HTTP < 400 <br> `ClientError` para o código de estado HTTP < 500 <br> `Error` para o estado HTTP >= 500 |
| `properties.tenantId`        | Identificador da organización                                                                                                        |
| `properties.tenantName`      | Nome da organización.                                                                                              |
| `properties.callerObjectId`  | Azure Active Directory ObjectId da persoa que chama.                                                                         |
| `properties.instanceId`      | Insights do cliente`instanceId`                                                                                         |

### <a name="workflow-event-schema"></a>Esquema de eventos de fluxo de traballo

O fluxo de traballo contén varios pasos. [Inxerir fontes de datos](data-sources.md),[unificar](data-unification.md),[enriquecer](enrichment-hub.md), e [exportar](export-destinations.md) datos. Todos eses pasos poden executarse individualmente ou orquestrados cos seguintes procesos.

#### <a name="operation-types"></a>Tipos de operación

| OperationType     | Agrupar                                     |
| ----------------- | ----------------------------------------- |
| Inxestión         | [Fontes de datos](data-sources.md)           |
| Preparación de datos   | [Fontes de datos](data-sources.md)           |
| Asignación               | [Unificación de datos](data-unification.md)   |
| Buscar coincidencias             | [Unificación de datos](data-unification.md)   |
| Combinación             | [Unificación de datos](data-unification.md)   |
| ProfileStore      | [Perfís de clientes](customer-profiles.md) |
| Buscar            | [Perfís de clientes](customer-profiles.md) |
| Actividade          | [Actividades](activities.md)                  |
| Medidas de atributos | [Segmentos e medidas](segments.md)      |
| Medidas da entidade    | [Segmentos e medidas](segments.md)      |
| Medidas          | [Segmentos e medidas](segments.md)      |
| Segmentación      | [Segmentos e medidas](segments.md)      |
| Enriquecemento        | [Enriquecemento](enrichment-hub.md)                                          |
| Intelixencia      | [Predicións](predictions-overview.md)                                          |
| AiBuilder         | [Predicións](predictions-overview.md)                                          |
| Conclusións          | [Predicións](predictions-overview.md)                                          |
| Export            | [Exportacións](export-destinations.md)                                          |
| Xestión de modelos   | [Predicións](custom-models.md)                                           |
| Relacións      | [Unificación de datos](relationships.md)                                           |

#### <a name="field-description"></a>Descrición do campo

| Campo           | Tipo de datos  | Obrigatorio/Opcional | Descripción                                                                                                                                                   | Exemplo                                                                                                                                                                  |
| --------------- | --------- | ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `time`          | Marca de hora | Obrigatorio          | Marca de tempo do evento (UTC).                                                                                                                                 | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resourceId`    | String    | Obrigatorio          | ResourceId da instancia que emitiu o evento.                                                                                                            | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX` |
| `operationName` | String    | Obrigatorio          | Nome da operación representada por este evento. `{OperationType}.[WorkFlow|Task][Started|Completed]`. Ver [Tipos de operación](#operation-types) como referencia. | `Segmentation.WorkflowStarted`,<br> `Segmentation.TaskStarted`, <br> `Segmentation.TaskCompleted`, <br> `Segmentation.WorkflowCompleted`                                 |
| `category`      | String    | Obrigatorio          | Categoría de rexistro do evento. Sempre`Operational` para eventos de fluxo de traballo                                                                                           | `Operational`                                                                                                                                                            |
| `resultType`    | String    | Obrigatorio          | Estado do evento. `Running`,`Skipped`,`Successful`,`Failure`                                                                                            |                                                                                                                                                                          |
| `durationMs`    | Longo      | Opcional          | Duración da operación en milisegundos.                                                                                                                    | `133`                                                                                                                                                                    |
| `properties`    | String    | Opcional          | Obxecto JSON con máis propiedades para a categoría particular de eventos.                                                                                        | Ver subsección [Propiedades do fluxo de traballo](#workflow-properties-schema)                                                                                                       |
| `level`         | String    | Obrigatorio          | Grao de gravidade do evento.                                                                                                                                  | `Informational`, `Warning` ou `Error`                                                                                                                                   |

#### <a name="workflow-properties-schema"></a>Esquema de propiedades do fluxo de traballo

Os eventos de fluxo de traballo teñen as seguintes propiedades.

| Campo              | Workflow | Tarefa | Descripción            |
| ------------------------------- | -------- | ---- | ----------- |
| `properties.eventType`                       | Si      | Si  | Sempre`WorkflowEvent`, marcando o evento como evento de fluxo de traballo.                                                                                                                                                                                                |
| `properties.workflowJobId`                   | Si      | Si  | Identificador do fluxo de traballo executado. Todos os eventos de fluxo de traballo e tarefa dentro da execución do fluxo de traballo teñen o mesmo `workflowJobId`.                                                                                                                                   |
| `properties.operationType`                   | Si      | Si  | Identificador da operación, ver [Tipos de operación](#operation-types).                                                                                                                                                                               |
| `properties.tasksCount`                      | Si      | No   | Só fluxo de traballo. Número de tarefas que desencadea o fluxo de traballo.                                                                                                                                                                                                       |
| `properties.submittedBy`                     | Si      | No   | Opcional. Só eventos de fluxo de traballo. O Azure Active Directory [objectId do usuario](/azure/marketplace/find-tenant-object-id#find-user-object-id) quen desencadeou o fluxo de traballo, consulte tamén `properties.workflowSubmissionKind`.                                   |
| `properties.workflowType`                    | Si      | No   | `full` ou`incremental` refrescar.                                                                                                                                                                                                                            |
| `properties.workflowSubmissionKind`          | Si      | No   | `OnDemand` ou `Scheduled`.                                                                                                                                                                                                                                  |
| `properties.workflowStatus`                  | Si      | No   | `Running` ou `Successful`.                                                                                                                                                                                                                                 |
| `properties.startTimestamp`                  | Si      | Si  | Marca de tempo UTC`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.endTimestamp`                    | Si      | Si  | Marca de tempo UTC`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.submittedTimestamp`              | Si      | Si  | Marca de tempo UTC`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.instanceId`                      | Si      | Si  | Insights do cliente`instanceId`                                                                                                                                                                                                                              |  
| `properties.identifier`                      | No       | Si  | - Para OperationType =`Export`, o identificador é a guía da configuración de exportación. <br> - Para OperationType =`Enrichment`, é a guía do enriquecemento <br> - Para OperationType`Measures` e`Segmentation`, o identificador é o nome da entidade. |
| `properties.friendlyName`                    | No       | Si  | Nome fácil de usar da exportación ou da entidade que se procesa.                                                                                                                                                                                           |
| `properties.error`                           | No       | Si  | Opcional. Mensaxe de erro con máis detalles.                                                                                                                                                                                                                  |
| `properties.additionalInfo.Kind`             | No       | Si  | Opcional. Para OperationType`Export` só. Identifica o tipo de exportación. Para obter máis información, consulte [visión xeral dos destinos de exportación](export-destinations.md).                                                                                          |
| `properties.additionalInfo.AffectedEntities` | No       | Si  | Opcional. Para OperationType`Export` só. Contén unha lista de entidades configuradas na exportación.                                                                                                                                                            |
| `properties.additionalInfo.MessageCode`      | No       | Si  | Opcional. Para OperationType`Export` só. Mensaxe detallada para a exportación.                                                                                                                                                                                 |
| `properties.additionalInfo.entityCount`      | No       | Si  | Opcional. Para OperationType`Segmentation` só. Indica o número total de membros que ten o segmento.                                                                                                                                                    |

[!INCLUDE [footer-include](includes/footer-banner.md)]
