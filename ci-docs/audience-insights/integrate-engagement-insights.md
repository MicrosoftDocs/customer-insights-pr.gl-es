---
title: Integrar os datos web das estatísticas de participación con información do público
description: Traia información web sobre clientes desde a información sobre a participación ata a información sobre o público.
ms.date: 06/24/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: c2789a7d1379e0cf56511b272a763c904d8a3d347058ea9e029aaff0f723a028
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033767"
---
# <a name="integrate-web-data-from-engagement-insights-with-audience-insights"></a>Integrar os datos web das estatísticas de participación con información do público

Os clientes adoitan facer as transaccións do día a día en liña mediante sitios web. A capacidade de información de interacción (versión preliminar) en Dynamics 365 Customer Insights é unha solución práctica para integrar datos web como fonte. Ademais de datos transaccionais, demográficos ou de comportamento, podemos ver actividades na web en perfís de clientes unificados. Podemos usar estes perfís para obter información adicional como segmentos, medidas ou predicións para a activación do público.

Neste artigo descríbense os pasos para levar os datos de actividade na web dos seus clientes desde as estatísticas de participación ao seu contorno de estatísticas de público existentes.

Neste exemplo, imaxinemos un ambiente que contén perfís de clientes unificados. Os perfís unificáronse con orixes de enquisas, vendas polo miúdo e un sistema de tíckets. Tamén mostra as actividades relacionadas cos clientes. 

Agora queremos saber se un cliente visita as nosas propiedades web e comprende as súas actividades. As actividades inclúen, por exemplo, sitios web visitados ou páxinas de produtos vistas desde unha ligazón recibida nun correo electrónico.

## <a name="prerequisites"></a>Requisitos previos

Para integrar os datos da información de participación, cómpre cumprir algúns requisitos previos: 

- Integre o SDK de información de interacción co teu sitio web. Para obter máis información, consulte [Visión xeral dos recursos para programadores](../engagement-insights/developer-resources.md).
- A exportación de eventos web a partir da información de interacción require acceso a unha conta de Azure Data Lake Storage que se usará para inxerir os datos de eventos web na información do público. Para obter máis información, consulte [Exportar eventos](../engagement-insights/export-events.md).

## <a name="configure-refined-events-in-engagement-insights"></a>Configurar eventos refinados en información de interacción

Despois de que un administrador instrumente un sitio web co SDK de información de interación, os *eventos básicos* recóllense cando un usuario ve unha páxina web ou fai clic nalgún lugar. Os eventos base adoitan conter numerosos detalles. Dependendo do seu caso de uso, só precisa un subconxunto de datos nun evento base. A información de participación permítelle crear *eventos refinados* que conteñan só as propiedades dun evento base que seleccione.     

Para obter máis información, consulte [Crear e modificar eventos refinados](../engagement-insights/refined-events.md).

Consideracións á hora de crear eventos refinados: 

- Proporcione un nome significativo para o evento refinado. Utilizarase como nome dunha actividade na información do público.
- Seleccione polo menos as seguintes propiedades para crear unha actividade en estatísticas de audiencia: 
    - Signal.Action.Name: indica os detalles da actividade.
    - Signal.User.Id: úsase para asignar co ID de cliente.
    - Signal.View.Uri: utilízase como enderezo web como base para segmentos ou medidas.
    - Signal.Export.Id: utilízase como clave principal para eventos.
    - Signal.Timestamp: determina a data e hora da actividade.

Seleccione os filtros para concentrarse nos eventos e páxinas que importan para o seu caso de uso. Neste exemplo, usaremos o nome da acción "Promoción por correo electrónico".

## <a name="export-the-refined-web-events"></a>Exportar os eventos web refinados 

Despois de definir o evento refinado, ten que configurar a exportación dos datos do evento a Azure Data Lake Storage, que se pode configurar como orixe de datos para a inxestión na información do público. As exportacións prodúcense constantemente a medida que os eventos flúen desde a propiedade web.

Para obter máis información, consulte [Exportar eventos](../engagement-insights/export-events.md).

## <a name="ingest-event-data-to-audience-insights"></a>Inxerir datos de eventos para obter información sobre o público

Agora que definiu o evento refinado e configurou a súa exportación, pasamos a inxerir os datos para obter información sobre o público. Debe crear unha nova orixe de datos baseada nun cartafol de Common Data Model. Introduza os detalles da conta de almacenamento á que exportar os eventos. No ficheiro *default.cdm.json*, seleccione o evento refinado para inxerir e cree a entidade en estatísticas de audiencia.

Para obter máis información, consulte [Conectarse a un cartafol de Common Data Model usando unha conta de Azure Data Lake](connect-common-data-model.md).


## <a name="relate-refined-event-data-as-an-activity-of-a-customer-profile"></a>Relacionar os datos de eventos refinados como unha actividade dun perfil de cliente

Despois de completar a inxestión da entidade, pode configurar a actividade para o perfil do cliente.

Para obter máis información, consulte [Actividades do cliente](activities.md).

:::image type="content" source="media/web-event-activity.png" alt-text="Páxina de actividades co panel da actividade Editar expandido e campos cubertos.":::

Configure a nova actividade coa seguinte asignación: 

- **Clave primaria**: Signal.Export.Id, un identificador único que está dispoñible para todos os rexistros de eventos na información de interacción. Esta propiedade xérase automaticamente.

- **Marca de tempo**: Signal.Timestamp na propiedade do evento.

- **Evento**: Signal.Name, o nome do evento que desexa rastrexar.

- **Enderezo web** : Signal.View.Uri que fai referencia ao URI da páxina que creou o evento.

- **Detalles**: Signal.Action.Name para representar a información para asociar co evento. A propiedade seleccionada neste caso indica que o evento é para promoción de correo electrónico.

- **Tipo de actividade**: Neste exemplo, escollemos o tipo de actividade existente WebLog. Esta selección é unha opción de filtro útil para executar modelos predición ou crear segmentos baseados neste tipo de actividade.

- **Establecer relación**: Esta importante configuración vincula a actividade cos perfís de clientes existentes. **Signal.User.Id** é o identificador configurado no SDK para ser recollido e que se relaciona co ID de usuario noutras orixes de datos que están configuradas nas estatísticas de audiencia. Neste exemplo, configuramos a relación entre Signal.User.Id e RetailCustomers:CustomerRetailId, que é a clave principal que se identificou no paso do mapa do proceso de unificación de datos.

Despois de procesar as actividades, pode revisar os rexistros dos clientes e abrir unha tarxeta de cliente para ver as actividades a partir da información de interacción na cronoloxía. 

> [!TIP]
> Para atopar un identificador de cliente que teña unha actividade de información de interacción, vaia a **Entidades** e previsualice os datos da entidade UnifiedActivity. ActivityTypeDisplay = WebLog contén a actividade de información de compromiso configurada no exemplo anterior. Copie o ID de cliente para un deses rexistros e para ese ID na páxina **Clientes**.

## <a name="next-steps"></a>Pasos seguintes

Agora pode crear [segmentos](segments.md), [medidas](measures.md) e [predicións](predictions.md) para establecer unha conexión significativa cos seus clientes.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
