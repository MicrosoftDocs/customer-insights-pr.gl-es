---
title: Exportar datos de Customer Insights
description: Xestione as exportacións para compartir datos.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c1078ed0ba259a6e9cde3c7ede3570890ae48e67
ms.sourcegitcommit: 33a8e21b3bf6521bdb8346f81f79fce88091ddfd
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 05/10/2021
ms.locfileid: "6016612"
---
# <a name="exports-preview-overview"></a>Visión xeral das exportacións (versión preliminar)

A páxina **Exportacións** mostra todas as exportacións configuradas. As exportacións comparten datos específicos con varias aplicacións. Poden incluír perfís ou entidades de clientes, esquemas e detalles de asignación. Cada exportación require unha [conexión, configurada por un administrador, para xestionar a autenticación e o acceso](connections.md).

Vaia a **Datos** > **Exportacións** para ver a páxina de exportacións. Todos os roles de usuario teñen acceso para ver as exportacións configuradas. Uso do campo de busca na barra de comandos para atopar exportacións polo seu nome, nome de conexión ou tipo de conexión.

## <a name="set-up-a-new-export"></a>Configurar unha nova exportación

Para configurar ou editar unha exportación, necesita ter conexións dispoñibles. As conexións dependen do seu [rol de usuario](permissions.md):
- Os administradores teñen acceso a todas as conexións. Tamén poden crear novas conexións cando configuren unha exportación.
- Os colaboradores poden ter acceso a conexións específicas. Dependen dos administradores para configurar e compartir conexións. Para obter máis información, consulte [Permitir aos colaboradores usar unha conexión para as exportacións](connections.md#allow-contributors-to-use-a-connection-for-exports).
- Os espectadores só poden ver as exportacións existentes pero non crealas.

1. Vaia a **Datos** > **Exportacións**.

1. Seleccione **Engadir exportación** para crear un novo destino de exportación.

1. No panel **Configurar exportación**, seleccione a conexión que desexa empregar. As [conexións](connections.md) son xestionados por administradores. 

1. Proporcione os detalles requiridos e seleccione **Gardar** para crear a exportación.

### <a name="edit-an-export"></a>Editar unha exportación

1. Seleccione os tres puntos verticais para o destino de exportación que desexa editar.

1. No menú despregable, seleccione **Editar**.

1. Cambie os valores que desexa actualizar e seccione **Gardar**.

## <a name="view-exports-and-export-details"></a>Ver Exportacións e detalles das exportacións

Despois de crear destinos de exportación, aparecen en **Datos** > **Exportacións**. Todos os usuarios poden ver que datos se comparten e o seu estado máis recente.

1. Vaia a **Datos** > **Exportacións**.

1. Os usuarios sen permisos de edición seleccionan **Ver** en vez de **Editar** para ver os detalles da exportación.

1. Este panel lateral mostra a configuración desta exportación. Sen permisos de edición, non pode cambiar os valores. Seleccione **Pechar** para volver á páxina de exportacións.

## <a name="run-exports-on-demand"></a>Executar exportacións a petición

Despois de configurar unha exportación, executarase con cada [actualización programada](system.md#schedule-tab) sempre que teña unha conexión que funcione.

Para exportar datos sen esperar a unha actualización programada, vaia a **Datos** > **Exportacións**. Ten dúas opcións:

- Para executar todas as exportacións, seleccione **Executar todo** na barra de comandos. 
- Para executar unha única exportación, seleccione os puntos suspensivos (...) nun elemento da lista e logo escolla **Executar**.

## <a name="remove-an-export"></a>Eliminar unha exportación

1. Vaia a **Datos** > **Exportacións**.

1. Seleccione os tres puntos verticais para a exportación que desexa eliminar.

1. Seleccione **Eliminar** do menú despregable.

1. Confirme a eliminación seleccionando **Eliminar** na pantalla de confirmación.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
