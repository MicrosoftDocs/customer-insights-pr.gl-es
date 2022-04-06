---
title: Inxestión de datos en tempo real (vista previa)
description: Información xeral sobre capacidades en tempo real nas estatísticas do público.
ms.date: 10/27/2020
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
searchScope:
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: 138704445d52df3336af6af60420f0bd0ee0c639
ms.sourcegitcommit: a8e99cf8b23ccc00d76c1dee22afd808a160a5c8
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 03/22/2022
ms.locfileid: "8464024"
---
# <a name="real-time-data-ingestion-preview"></a>Inxestión de datos en tempo real (vista previa)

A funcionalidade case en tempo real permítelle ver, en poucos segundos, as últimas interaccións que fixeron os seus clientes cos seus produtos ou servizos.

As [actualizacións programadas](system.md#schedule-tab) inclúen gran cantidade de rexistros e varias operacións complexas. En primeiro lugar, os datos son extraídos da orixe de datos. A continuación, os datos unifícanse e logo enriquécense con información adicional. Cada execución deste proceso pode levar minutos ou horas.

A funcionalidade en tempo real proporciona datos inmediatamente para o consumo, ata que a actualización programada posterior extrae estes datos da orixe de datos.

As actualizacións en tempo real teñen unha hora de caducidade despois da cal xa non anularán o valor da orixe de datos:

- As actualizacións do perfil manteranse durante 4 horas
- As actividades manteranse durante 30 días

Estes valores son parámetros de chamada de API que pode cambiar. Pretenden garantir que os seus datos de orixes sexan a súa fonte de verdade. Se quere que se inclúan actualizacións en tempo real durante máis tempo, debe engadilas a unha orixe de datos para que se poidan extraer durante a próxima actualización programada.

## <a name="real-time-update-of-the-unified-customer-profile-fields"></a>Actualización en tempo real dos campos de perfil de cliente unificados

Os perfís actualizados amosaranse na vista da tarxeta de cliente ou en calquera outra visualización nuns segundos.

Debido a que as operacións en tempo real teñen lugar despois da unificación de datos, só se aplican aos perfís de clientes unificados. Por este motivo, os cambios de perfil en tempo real non actualizarán medidas, subscricións de segmento nin enriquecementos.

### <a name="limitations"></a>Limitacións

- Os perfís de clientes pódense actualizar, pero non se poden crear ou eliminar.
- Non é posible exportar polo momento actualizacións en tempo real a sistemas externos, como Power BI.

## <a name="real-time-creation-of-activities"></a>Creación de actividades en tempo real

A API en tempo real permítelle publicar unha nova actividade do seu sistema de orixe (un rexistro de orixe individual) nun perfil de cliente unificado. A nova actividade estará dispoñible como actividade unificada na liña de tempo do perfil de cliente unificado en cuestión de segundos. Pode ver a liña de tempo na vista da tarxeta de cliente ou calquera outra integración de liña de tempo que configurase.

> [!NOTE]
>
> - As actividades non se poden cambiar. Non cambiarán unha vez creadas.
> - Actualmente, os segmentos e as medidas non se actualizarán en función da nova actividade.
> - As actividades engadidas só a través da API en tempo real non forman parte das exportacións e non aparecerán en PowerBI.

Hai dúas formas de conectarse á API en tempo real:

- [indirectamente](#connect-via-the-dynamics-365-customer-insights-connector), usando o [conector Dynamics 365 Customer Insights](/connectors/customerinsights/)
- [directamente](#connect-directly-to-the-real-time-api), co código

Ámbolos dous xeitos comparten os seguintes requisitos previos:

- Un ambiente de Customer Insights
- Perfís de cliente unificados
- Actividades configuradas e executadas
- Permisos de colaborador ou administrador para autenticar a súa conta

## <a name="connect-via-the-dynamics-365-customer-insights-connector"></a>Conectarse a través do conector de Dynamics 365 Customer Insights

A API en tempo real pode inxerir datos dun conector Power Platform específico, o [conector de Dynamics 365 Customer Insights](/connectors/customerinsights/), sen necesidade de escribir e despregar ningún código.    
O conector pode facer as mesmas accións en tempo real que a API. Necesita unha licenza válida para os conectores premium. Para obter máis información, consulte [Preguntas máis frecuentes acerca de licenzas de Power Apps e Power Automate](/power-platform/admin/powerapps-flow-licensing-faq).

- Power Platform [Power Apps e/ou Power Automate](/connectors/)
- Azure [Logic Apps](/azure/connectors/apis-list)

Para obter máis detalles sobre a creación de fluxos, consulte a [documentación de Power Automate](/power-automate/).

## <a name="connect-directly-to-the-real-time-api"></a>Conectar directamente á API en tempo real

Pode usar as capacidades en tempo real creando a súa propia canle e conectándose directamente á API en tempo real.    
Pode publicar unha actividade no formato do sistema de orixe ou no formato UnifiedActivity. Obteña o formato facendo unha chamada a unha API a /api/instances/{instanceId}/manage/entities/UnifiedActivity.

Os detalles desta API, incluídos parámetros e respostas, pódense atopar na sección **EntityData** sobre a [Referencia das API de Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). Para obter máis información, consulte [Traballar coas API de Customer Insights](apis.md).

## <a name="understand-your-real-time-usage-with-telemetry"></a>Comprender o seu uso en tempo real coa telemetría

Obteña unha visión xeral do volume de solicitudes á API en tempo real e información sobre problemas que pode atopar o sistema. Pode [acceder á telemetría en tempo real](system.md#api-usage-tab). 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
