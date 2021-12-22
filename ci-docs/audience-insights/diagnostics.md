---
title: Auditoría Dynamics 365 Customer Insights con Azure Monitor
description: Aprende a enviar rexistros a Microsoft Azure Monitor.
ms.date: 12/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: article
author: brndkfr
ms.author: bkief
manager: shellyha
ms.openlocfilehash: d962c359d70a068fcf939b61e340f86de088b419
ms.sourcegitcommit: 0c3c473e0220de9ee3c1f1ee1825de0b3b3663c3
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 12/14/2021
ms.locfileid: "7920866"
---
# <a name="log-forwarding-in-dynamics-365-customer-insights-with-azure-monitor-preview"></a>Reenvío de sesión Dynamics 365 Customer Insights con Azure Monitor (vista previa)

Dynamics 365 Customer Insights proporciona unha integración directa con Azure Monitor. Os rexistros de recursos de Azure Monitor permítenche supervisar e enviar rexistros [Almacenamento Azure](https://azure.microsoft.com/services/storage/),[Azure Log Analytics](/azure/azure-monitor/logs/log-analytics-overview), ou transmitilos en streaming [Azure Event Hubs](https://azure.microsoft.com/services/event-hubs/).

Customer Insights envía os seguintes rexistros de eventos:

- **Auditoría de eventos**
  - **Evento APIE** - permite o seguimento de cambios feito a través de Dynamics 365 Customer Insights IU.
- **Eventos Operativos**
  - **WorkflowEvent** - O fluxo de traballo permite configurar [Fontes de datos](data-sources.md),[unificar](data-unification.md) e [enriquecer](enrichment-hub.md) e finalmente [exportar](export-destinations.md) datos noutros sistemas. Todos eses pasos pódense facer individualmente (por exemplo, desencadear unha única exportación) ou orquestrados (por exemplo, a actualización de datos de fontes de datos que desencadea o proceso de unificación que incorporará enriquecementos adicionais e, unha vez feito, exportará os datos a outro sistema). Para máis detalles consulte o [Esquema WorkflowEvent](#workflow-event-schema).
  - **Evento APIE** - todas as chamadas de API á instancia dos clientes Dynamics 365 Customer Insights. Para máis detalles consulte o [Esquema APIEvent](#api-event-schema).

## <a name="set-up-the-diagnostic-settings"></a>Configura a configuración de diagnóstico

### <a name="prerequisites"></a>Requisitos previos

Para configurar diagnósticos en Customer Insights, débense cumprir os seguintes requisitos previos:

- Tes un activo [Subscrición Azure](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/).
- Tes [Administrador](permissions.md#administrator) permisos en Customer Insights.
- Tes o **Colaborador** e **Administrador de acceso de usuarios** papel no recurso de destino en Azure. O recurso pode ser unha conta de Azure Storage, un Azure Event Hub ou un espazo de traballo de Azure Log Analytics. Para obter máis información, consulte [Engadir ou eliminar asignacións de roles de Azure mediante o portal de Azure](/azure/role-based-access-control/role-assignments-portal).
- [Requisitos do destino](/azure/azure-monitor/platform/diagnostic-settings#destination-requirements) para Azure Storage, Azure Event Hub ou Azure Log Analytics.
- Tes polo menos o **Lector** papel no grupo de recursos ao que pertence o recurso.

### <a name="set-up-diagnostics-with-azure-monitor"></a>Configura diagnósticos con Azure Monitor

1. En Customer Insights, seleccione **Sistema** > **Diagnóstico** para ver os destinos de diagnóstico configurados nesta instancia.

1. Seleccione **Engadir destino**.

   > [!div class="mx-imgBorder"]
   > ![Conexión de diagnóstico](media/diagnostics-pane.png "Conexión de diagnóstico")

1. Proporcione un nome no **Nome do destino do diagnóstico** campo.

1. Escolle o **Inquilino** da subscrición de Azure co recurso de destino e seleccione **acceder**.

1. Seleccione o **Tipo de recurso** (Conta de almacenamento, Centro de eventos ou análise de rexistro).

1. Seleccione o **Subscrición** para o recurso de destino.

1. Seleccione o **Grupo de recursos** para o recurso de destino.

1. Seleccione o **Recurso**.

1. Confirme o **Privacidade e cumprimento dos datos** declaración.

1. Seleccione **Conectar ao sistema** para conectarse ao recurso de destino. Os rexistros comezan a aparecer no destino despois de 15 minutos, se a API está en uso e xera eventos.

### <a name="remove-a-destination"></a>Eliminar un destino

1. Ir a **Sistema** > **Diagnóstico**.

1. Seleccione o destino de diagnóstico na lista.

1. No **Accións** columna, seleccione a **Eliminar** ícona.

1. Confirme a eliminación para deter o reenvío de rexistro. O recurso da subscrición de Azure non se eliminará. Podes seleccionar a ligazón no **Accións** columna para abrir o portal de Azure para o recurso seleccionado e elimínao alí.

## <a name="log-categories-and-event-schemas"></a>Categorías de rexistro e esquemas de eventos

Actualmente [Eventos da API](apis.md) e os eventos de fluxo de traballo son compatibles e aplícanse as seguintes categorías e esquemas.
O esquema de rexistro segue o [Esquema común de Azure Monitor](/azure/azure-monitor/platform/resource-logs-schema#top-level-common-schema).

### <a name="categories"></a>Categorías

Customer Insights ofrece dúas categorías:

- **Auditoría de eventos** :[Eventos da API](#api-event-schema) para rastrexar os cambios de configuración no servizo. `POST|PUT|DELETE|PATCH` operacións entran nesta categoría.
- **Eventos operativos** :[Eventos da API](#api-event-schema) ou [eventos de fluxo de traballo](#workflow-event-schema) xerado ao utilizar o servizo.  Por exemplo,`GET` solicitudes ou eventos de execución dun fluxo de traballo.

## <a name="configuration-on-the-destination-resource"></a>Configuración no recurso de destino

En función da súa elección sobre o tipo de recurso, aplicaranse automaticamente os seguintes pasos:

### <a name="storage-account"></a>Conta de almacenamento

O principal do servizo de Customer Insights obtén o **Colaborador da conta de almacenamento** permiso sobre o recurso seleccionado e crea dous contedores baixo o espazo de nomes seleccionado:

- `insight-logs-audit` que contén **eventos de auditoría**
- `insight-logs-operational` que contén **eventos operativos**

### <a name="event-hub"></a>Centro de eventos

O principal do servizo de Customer Insights obtén o **Propietario de datos de Azure Event Hubs** permiso sobre o recurso e creará dous centros de eventos baixo o espazo de nomes seleccionado:

- `insight-logs-audit` que contén **eventos de auditoría**
- `insight-logs-operational` que contén **eventos operativos**

### <a name="log-analytics"></a>Log Analytics

O principal do servizo de Customer Insights obtén o **Colaborador de Log Analytics** permiso sobre o recurso. Os rexistros estarán dispoñibles en **Rexistros** > **Táboas** > **Xestión de rexistros** no espazo de traballo de Log Analytics seleccionado. Amplía o **Xestión de rexistros** solución e localiza o`CIEventsAudit` e`CIEventsOperational` táboas.

- `CIEventsAudit` que contén **eventos de auditoría**
- `CIEventsOperational` que contén **eventos operativos**

Baixo a **Consultas** xanela, expanda **Auditoría** solución e localice as consultas de exemplo proporcionadas ao buscar `CIEvents`.

## <a name="event-schemas"></a>Esquemas de eventos

Os eventos da API e os eventos de fluxo de traballo teñen unha estrutura común e detalles onde difiren, consulte [Esquema de eventos da API](#api-event-schema) ou [esquema de eventos de fluxo de traballo](#workflow-event-schema).

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
| `identity`        | String    | Opcional          | Obxecto JSON que describe a identidade do usuario ou aplicación que fixo a operación.       | Ver [Identidade](#identity-schema) sección.     |  |
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
| `properties.instanceId`      | Información do cliente`instanceId`                                                                                         |

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
| Medidas de atributos | [Segmentos e Medidas](segments.md)      |
| Medidas da entidade    | [Segmentos e Medidas](segments.md)      |
| Medidas          | [Segmentos e Medidas](segments.md)      |
| Segmentación      | [Segmentos e Medidas](segments.md)      |
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
|                 |

#### <a name="workflow-properties-schema"></a>Esquema de propiedades do fluxo de traballo

Os eventos de fluxo de traballo teñen as seguintes propiedades.

| Campo              | Workflow | Tarefa | Descripción            |
| ------------------------------- | -------- | ---- | ----------- |
| `properties.eventType`                       | Si      | Si  | Sempre`WorkflowEvent`, marcando o evento como evento de fluxo de traballo.                                                                                                                                                                                                |
| `properties.workflowJobId`                   | Si      | Si  | Identificador do fluxo de traballo executado. Todos os eventos de fluxo de traballo e tarefa dentro da execución do fluxo de traballo teñen o mesmo `workflowJobId`.                                                                                                                                   |
| `properties.operationType`                   | Si      | Si  | Identificador da operación, consulte [Tipos de operación].(#operation-types)                                                                                                                                                                                       |
| `properties.tasksCount`                      | Si      | No   | Só fluxo de traballo. Número de tarefas que desencadea o fluxo de traballo.                                                                                                                                                                                                       |
| `properties.submittedBy`                     | Si      | No   | Opcional. Só eventos de fluxo de traballo. O Azure Active Directory [objectId do usuario](/azure/marketplace/find-tenant-object-id#find-user-object-id) quen desencadeou o fluxo de traballo, consulte tamén `properties.workflowSubmissionKind`.                                   |
| `properties.workflowType`                    | Si      | No   | `full` ou`incremental` refrescar.                                                                                                                                                                                                                            |
| `properties.workflowSubmissionKind`          | Si      | No   | `OnDemand` ou `Scheduled`.                                                                                                                                                                                                                                  |
| `properties.workflowStatus`                  | Si      | No   | `Running` ou `Successful`.                                                                                                                                                                                                                                 |
| `properties.startTimestamp`                  | Si      | Si  | Marca de tempo UTC`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.endTimestamp`                    | Si      | Si  | Marca de tempo UTC`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.submittedTimestamp`              | Si      | Si  | Marca de tempo UTC`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.instanceId`                      | Si      | Si  | Información do cliente`instanceId`                                                                                                                                                                                                                              |  |
| `properties.identifier`                      | No       | Si  | - Para OperationType =`Export`, o identificador é a guía da configuración de exportación. <br> - Para OperationType =`Enrichment`, é a guía do enriquecemento <br> - Para OperationType`Measures` e`Segmentation`, o identificador é o nome da entidade. |
| `properties.friendlyName`                    | No       | Si  | Nome fácil de usar da exportación ou da entidade que se procesa.                                                                                                                                                                                           |
| `properties.error`                           | No       | Si  | Opcional. Mensaxe de erro con máis detalles.                                                                                                                                                                                                                  |
| `properties.additionalInfo.Kind`             | No       | Si  | Opcional. Para OperationType`Export` só. Identifica o tipo de exportación. Para obter máis información, consulte [visión xeral dos destinos de exportación](export-destinations.md).                                                                                          |
| `properties.additionalInfo.AffectedEntities` | No       | Si  | Opcional. Para OperationType`Export` só. Contén unha lista de entidades configuradas na exportación.                                                                                                                                                            |
| `properties.additionalInfo.MessageCode`      | No       | Si  | Opcional. Para OperationType`Export` só. Mensaxe detallada para a exportación.                                                                                                                                                                                 |
| `properties.additionalInfo.entityCount`      | No       | Si  | Opcional. Para OperationType`Segmentation` só. Indica o número total de membros que ten o segmento.                                                                                                                                                    |
