---
title: Visión xeral das exportacións (versión preliminar)
description: Xestione as exportacións para compartir datos.
ms.date: 08/12/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: overview
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- ci-connections
- customerInsights
ms.openlocfilehash: c580b6c01e1b4ac6b095733193d86ebd0b4005f2
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304057"
---
# <a name="exports-preview-overview"></a>Visión xeral das exportacións (versión preliminar)

 As exportacións permítenche compartir datos específicos con varias aplicacións. Poden incluír perfís de clientes, entidades, esquemas e detalles de asignación. Cada exportación require unha [conexión, configurada por un administrador, para xestionar a autenticación e o acceso](connections.md). A páxina **Exportacións** mostra todas as exportacións configuradas.

## <a name="export-types"></a>Tipos de exportación

Existen dous tipos principais de exportacións:  

- **Exportación de datos** permíteche exportar calquera tipo de entidade dispoñible en Customer Insights. As entidades que selecciona para exportar expórtanse con todos os campos de datos, metadatos, esquemas e detalles de asignación.
- **Exportacións por segmentos** permíteche exportar entidades de segmentos desde Customer Insights. Para consumidores individuais (B-to-C), os segmentos representan unha lista de perfís de clientes. Para empresas (B-to-B), [os segmentos poden representar unha lista de contas ou contactos](segment-builder.md#create-a-new-segment-with-segment-builder). Ao configurar a exportación, selecciona os campos de datos incluídos, dependendo do sistema de destino ao que exportes os datos.

### <a name="export-segments"></a>Exportar segmentos

**Exportación de segmentos en contornos para contas comerciais (B-a-B) ou consumidores individuais (B-a-C)**  
A maioría das opcións de exportación admiten ambos tipos de ambientes. A exportación de segmentos a varios sistemas de destino ten requisitos específicos. 

**Exportacións de segmentos en contornos para consumidores individuais (B-a-C)**  
- Os segmentos no contexto de contornos para clientes individuais constrúense sobre a entidade de *perfil de cliente unificado*. Pódense exportar todos os segmentos que cumpran os requisitos dos sistemas de destino (por exemplo, un enderezo de correo electrónico).

**Segmenta as exportacións en contornos para contas empresariais (B-to-B)**  
- Os segmentos no contexto de ambientes para contas empresariais están construídos sobre o *conta* entidade ou o *contacto* entidade. Para exportar os segmentos de conta tal cal, o sistema de destino debe soportar segmentos de conta puros. Este é o caso de [LinkedIn](export-linkedin-ads.md) cando escolla a opción **empresa** mentres se define a exportación.
- O resto de sistemas de destino requiren campos da entidade de contacto.
- Con dous tipos de segmentos (contactos e contas), Customer Insights identifica automaticamente que tipo de segmentos son aptos para exportar en función do sistema de destino. Por exemplo, para un sistema de destino centrado nos contactos como Mailchimp, Customer Insights só che permite escoller segmentos de contacto para exportar.

**Límites das exportacións de segmentos**  
- Os sistemas de destino de terceiros poden limitar o número de perfís de clientes que pode exportar. 
- Para clientes individuais, verá o número real de membros do segmento cando seleccione un segmento para exportar. Recibirás unha advertencia se un segmento é demasiado grande. 
- Para as contas empresariais, verás o número de contas ou contactos dependendo do segmento. Recibirás un aviso se o segmento é demasiado grande. O exceder os límites dos resultados dos sistemas de destino omitirá a exportación.

## <a name="set-up-a-new-export"></a>Configurar unha nova exportación

Para configurar ou editar unha exportación, necesitas as conexións correctas dispoñibles. As conexións dependen do seu [rol de usuario](permissions.md):
- Os **administradores** teñen acceso a todas as conexións. Tamén poden crear novas conexións cando configuren unha exportación.
- Os **colaboradores** poden ter acceso a conexións específicas. Dependen dos administradores para configurar e compartir conexións. A lista de exportacións móstralles aos colaboradores se poden editar ou só ver unha exportación na columna **Os seus permisos**. Para obter máis información, vaia a [Permitir aos colaboradores usar unha conexión para exportar](connections.md#allow-contributors-to-use-a-connection-for-exports).
- Os **espectadores** só poden ver as exportacións existentes e non crealas.

1. Vaia a **Datos** > **Exportacións**.

1. Seleccione **Engadir exportación** para crear unha nova exportación.

1. No **Configura a exportación** panel, seleccione cal [conexión](connections.md) usar.

1. Proporcione os detalles requiridos e seleccione **Gardar** para crear a exportación. Para obter os detalles necesarios, revise a documentación de Customer Insights para a exportación específica.

## <a name="manage-existing-exports"></a>Xestionar as exportacións existentes

Ir a **Datos** > **Exportacións** para ver as exportacións, o seu nome de conexión, tipo de conexión e estado. Todos os roles de usuario poden ver as exportacións configuradas. Podes ordenar a lista de exportacións por calquera columna ou usar a caixa de busca para atopar a exportación que queres xestionar.

Seleccione unha exportación para ver as accións dispoñibles.

:::image type="content" source="media/exports_showmore.png" alt-text="Páxina de exportacións.":::

- **Ver** ou **Editar** a exportación. Os usuarios sen permisos de edición seleccionan **Ver** en vez de **Editar** para ver os detalles da exportación.
- **Corre** a exportación para exportar os datos máis recentes.
- **Crear duplicado** dunha exportación.
- **[Horario](#schedule-and-run-exports)** a exportación.
- **Separar a conexión** para eliminar a conexión para esta exportación. Desconectar non elimina a conexión, pero desactiva a exportación. O **Conexión utilizada** a columna mostra Sen conexión.
- **Quitar** a exportación.

## <a name="schedule-and-run-exports"></a>Programar e executar exportacións

Cada exportación que configura ten unha programación de actualización. Durante unha actualización, o sistema busca datos novos ou actualizados para incluír nunha exportación. Por defecto, as exportacións execútanse como parte de todas as [actualización do sistema programadas](schedule-refresh.md). Pode personalizar a programación de actualización ou desactivala para executar as exportacións manualmente.

As programacións de exportación dependen do estado do seu ambiente. Se hai actualizacións en curso nas [dependencias](system.md#refresh-processes) cando debería iniciarse unha exportación programada, o sistema primeiro completará as actualizacións e logo executará a exportación. O **Actualizado** a columna mostra a última vez que se actualizou unha exportación.

### <a name="schedule-exports"></a>Programar exportacións

Defina programacións de actualización personalizadas para exportacións individuais ou varias exportacións á vez. A programación definida actualmente aparece na columna **Programación** da lista de exportacións. O permiso para cambiar o horario é o mesmo que [edición e definición de exportacións](export-destinations.md#set-up-a-new-export).

1. Vaia a **Datos** > **Exportacións**.

1. Seleccione a exportación que quere programar.

1. Seleccione **Programar**.

1. No panel **Programar exportación**, estableza **Programar execución** en **Activado** para executar a exportación automaticamente. Establézaa en **Desactivado** para actualizala manualmente.

1. Para exportacións actualizadas automaticamente, escolla un valor de **Periodicidade** e especifique os seus detalles. A hora definida aplícase a todas instancias dunha periodicidade. É a hora na que unha exportación debería comezar a actualizarse.

1. Seleccione **Gardar**.

Ao editar a programación de varias exportacións, seleccione unha opción en **Manter ou anular horarios**:

- **Manter horarios individuais** : Manteña a programación previamente definida para as exportacións seleccionadas e só desactívaas ou activalas.
- **Definir unha nova programación para todas as exportación seleccionadas**: anular as programacións existentes das exportacións seleccionadas.

### <a name="run-exports-on-demand"></a>Executar exportacións a petición

Para exportar datos sen esperar a unha actualización programada, vaia a **Datos** > **Exportacións**.

- Para executar todas as exportacións, seleccione **Executar todo** na barra de comandos. Só se executan as exportacións que teñen unha programación activa. Para executar unha exportación que non estea activa, executa unha única exportación.
- Para executar unha única exportación, selecciónea na lista e seleccione **Executar** na barra de comandos.

## <a name="troubleshooting"></a>Resolución de problemas

### <a name="segment-not-eligible-for-export"></a>Segmento non apto para exportación

**Problema** Nun entorno de contas empresariais, as súas exportacións fallan coa mensaxe de erro: "O seguinte segmento non é apto para este destino de exportación: '{ nome do segmento} '. Escolle só segmentos do tipo ContactProfile e téntao de novo."

**Resolución** Actualizáronse os contornos de Customer Insights para contas empresariais para admitir segmentos de contacto ademais dos segmentos de conta. Debido a ese cambio, as exportacións que necesitan detalles de contacto só funcionan con segmentos baseados en contactos.

1. [Crea un segmento baseado en contactos](segment-builder.md) que coincide co teu segmento usado anteriormente.

1. Unha vez executado ese segmento de contacto, edite a exportación respectiva e seleccione o novo segmento.

1. Seleccione **Gardar** para gardar a configuración ou **Garda e executa** para probar esta exportación de inmediato.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]


[!INCLUDE [footer-include](includes/footer-banner.md)]
