---
title: Exportar datos de Customer Insights
description: Xestione as exportacións para compartir datos.
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6e7793fa99f8431d9d420529b39e0b5b5dbf6748
ms.sourcegitcommit: 0689e7ed4265855d1f76745d68af390f8f4af8a0
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 06/14/2021
ms.locfileid: "6253038"
---
# <a name="exports-preview-overview"></a>Visión xeral das exportacións (versión preliminar)

A páxina **Exportacións** mostra todas as exportacións configuradas. As exportacións comparten datos específicos con varias aplicacións. Poden incluír perfís ou entidades de clientes, esquemas e detalles de asignación. Cada exportación require unha [conexión, configurada por un administrador, para xestionar a autenticación e o acceso](connections.md).

Vaia a **Datos** > **Exportacións** para ver a páxina de exportacións. Todos os roles de usuario teñen acceso para ver as exportacións configuradas. Uso do campo de busca na barra de comandos para atopar exportacións polo seu nome, nome de conexión ou tipo de conexión.

## <a name="set-up-a-new-export"></a>Configurar unha nova exportación

Para configurar ou editar unha exportación, necesita ter conexións dispoñibles. As conexións dependen do seu [rol de usuario](permissions.md):
- Os administradores teñen acceso a todas as conexións. Tamén poden crear novas conexións cando configuren unha exportación.
- Os colaboradores poden ter acceso a conexións específicas. Dependen dos administradores para configurar e compartir conexións. A lista de exportacións móstralles aos colaboradores se poden editar ou só ver unha exportación na columna **Os seus permisos**. Para obter máis información, consulte [Permitir aos colaboradores usar unha conexión para as exportacións](connections.md#allow-contributors-to-use-a-connection-for-exports).
- Os espectadores só poden ver as exportacións existentes pero non crealas.

### <a name="define-a-new-export"></a>Definir unha nova exportación

1. Vaia a **Datos** > **Exportacións**.

1. Seleccione **Engadir exportación** para crear unha nova exportación.

1. No panel **Configurar exportación**, seleccione a conexión que desexa empregar. As [conexións](connections.md) son xestionados por administradores. 

1. Proporcione os detalles requiridos e seleccione **Gardar** para crear a exportación.

### <a name="define-a-new-export-based-on-an-existing-export"></a>Definir unha nova exportación baseada nunha exportación existente

1. Vaia a **Datos** > **Exportacións**.

1. Na lista de exportacións, seleccione a exportación que quere duplicar.

1. Seleccione **Crear duplicado** na barra de comandos para abrir o panel **Configurar exportación** cos detalles da exportación seleccionada.

1. Revise e adapte a exportación e seleccione **Gardar** para crear unha nova exportación.

### <a name="edit-an-export"></a>Editar unha exportación

1. Vaia a **Datos** > **Exportacións**.

1. Na lista de exportacións, seleccione a exportación que quere editar.

1. Seleccione **Editar** na barra de comandos.

1. Cambie os valores que desexa actualizar e seccione **Gardar**.

## <a name="view-exports-and-export-details"></a>Ver exportacións e detalles das exportacións

Despois de crear destinos de exportación, aparecen en **Datos** > **Exportacións**. Todos os usuarios poden ver que datos se comparten e o seu estado máis recente.

1. Vaia a **Datos** > **Exportacións**.

1. Os usuarios sen permisos de edición seleccionan **Ver** en vez de **Editar** para ver os detalles da exportación.

1. O panel lateral mostra a configuración dunha exportación. Sen permisos de edición, non pode cambiar os valores. Seleccione **Pechar** para volver á páxina de exportacións.

## <a name="schedule-and-run-exports"></a>Programar e executar exportacións

Cada exportación que configura ten unha programación de actualización. Durante unha actualización, o sistema busca datos novos ou actualizados para incluír nunha exportación. Por defecto, as exportacións execútanse como parte de todas as [actualización do sistema programadas](system.md#schedule-tab). Pode personalizar a programación de actualización ou desactivala para executar as exportacións manualmente.

As programacións de exportación dependen do estado do seu ambiente. Se hai actualizacións en [dependencias](system.md#refresh-policies) no progreso cando debería comezar unha exportación programada, o sistema primeiro completará as dependencias e logo executará a exportación. Pode ver cando se actualizou por última vez unha exportación na columna **Actualizado**.

### <a name="schedule-exports"></a>Programar exportacións

Pode definir programacións de actualización personalizadas para exportacións individuais ou varias exportacións á vez. A programación definida actualmente aparece na columna **Programación** da lista de exportacións. O permiso para cambiar a programación é o mesmo que para [editar e eliminar as exportacións](export-destinations.md#set-up-a-new-export). 

1. Vaia a **Datos** > **Exportacións**.

1. Seleccione a exportación que quere programar.

1. Seleccione **Programar** na barra de comandos.

1. No panel **Programar exportación**, estableza **Programar execución** en **Activado** para executar a exportación automaticamente. Establézaa en **Desactivado** para actualizala manualmente.

1. Para exportacións actualizadas automaticamente, escolla un valor de **Periodicidade** e especifique os seus detalles. A hora definida aplícase a todas instancias dunha periodicidade. É a hora na que unha exportación debería comezar a actualizarse.

1. Aplique e active os cambios seleccionando **Gardar**.

Ao editar a programación de varias exportacións, ten que facer unha selección en **Manter ou anular programacións**:
- **Manter programacións individuais**: continuar coa programación previamente definida para as exportacións seleccionadas e só desactivalas ou activalas.
- **Definir unha nova programación para todas as exportación seleccionadas**: anular as programacións existentes das exportacións seleccionadas.

### <a name="run-exports-on-demand"></a>Executar exportacións a petición

Para exportar datos sen esperar a unha actualización programada, vaia a **Datos** > **Exportacións**.

- Para executar todas as exportacións, seleccione **Executar todo** na barra de comandos. Esta acción só executará exportacións que teñen unha programación activa.
- Para executar unha única exportación, selecciónea na lista e seleccione **Executar** na barra de comandos. Así é como executa as exportacións sen programación activa. 

## <a name="remove-an-export"></a>Eliminar unha exportación

1. Vaia a **Datos** > **Exportacións**.

1. Seleccione a exportación que desexe eliminar.

1. Seleccione **Eliminar** na barra de comandos.

1. Confirme a eliminación seleccionando **Eliminar** na pantalla de confirmación.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
