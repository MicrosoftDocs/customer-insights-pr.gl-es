---
title: Exportar datos de Customer Insights
description: Xestione as exportacións para compartir datos.
ms.date: 11/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: overview
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 05485fc7def3d699d5179bcaa005ceb57024f840
ms.sourcegitcommit: bb1ca84bc38e81fb2ff2961c457384b7beb5b5fa
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 01/15/2022
ms.locfileid: "7977965"
---
# <a name="exports-preview-overview"></a>Visión xeral das exportacións (versión preliminar)

A páxina **Exportacións** mostra todas as exportacións configuradas. As exportacións comparten datos específicos con varias aplicacións. Poden incluír perfís de clientes, entidades, esquemas e detalles de asignación. Cada exportación require unha [conexión, configurada por un administrador, para xestionar a autenticación e o acceso](connections.md).

Vaia a **Datos** > **Exportacións** para ver a páxina de exportacións. Todos os roles de usuario poden ver as exportacións configuradas. Use o campo de busca na barra de comandos para buscar exportacións polo seu nome, nome de conexión ou tipo de conexión.

## <a name="export-types"></a>Tipos de exportación

Existen dous tipos principais de exportacións:  

- **Exportacións de datos** permítelle exportar calquera tipo de entidade dispoñible en estatísticas de audiencia. As entidades que selecciona para exportar expórtanse con todos os campos de datos, metadatos, esquemas e detalles de asignación. 
- **Segmentar exportacións** permítelle exportar entidades de segmento a partir de estatísticas de audiencia. Os segmentos representan unha lista de perfís de clientes. Ao configurar a exportación, selecciona os campos de datos incluídos, dependendo do sistema de destino ao que estea exportando os datos. 

### <a name="export-segments"></a>Exportar segmentos

**Exportación de segmentos en contornos para contas comerciais (B-a-B) ou consumidores individuais (B-a-C)**  
A maioría das opcións de exportación admiten os dous tipos de ambientes. A exportación de segmentos a varios sistemas de destino ten requisitos específicos. En xeral, un membro do segmento, o perfil do cliente, contén información de contacto. Aínda que normalmente é o caso dos segmentos baseados en consumidores individuais (B-a-C), non é necesariamente o caso dos segmentos baseados en contas comerciais (B-a-B). 

**O segmento exporta contornos para contas empresariais (B-a-B)**  
- Os segmentos no contexto de contornos para contas empresariais constrúense sobre a entidade *conta*. Para exportar os segmentos de conta tal cal, o sistema de destino debe soportar segmentos de conta puros. Este é o caso de [LinkedIn](export-linkedin-ads.md) cando escolla a opción **empresa** mentres se define a exportación.
- O resto de sistemas de destino requiren campos da entidade de contacto. Para garantir que os segmentos de conta poden recuperar datos de contactos relacionados, a definición do seu segmento debe proxectar atributos da entidade de contacto. Máis información sobre como [configurar segmentos e atributos do proxecto](segment-builder.md).

**Exportacións de segmentos en contornos para consumidores individuais (B-a-C)**  
- Os segmentos no contexto de contornos para clientes individuais constrúense sobre a entidade de *perfil de cliente unificado*. Pódense exportar todos os segmentos que cumpran os requisitos dos sistemas de destino (por exemplo, un enderezo de correo electrónico).

**Límites das exportacións de segmentos**  
- Os sistemas de destino de terceiros poden limitar o número de perfís de clientes que pode exportar. 
- Para clientes individuais, verá o número real de membros do segmento cando seleccione un segmento para exportar. Recibirás un aviso se un segmento é demasiado grande. 
- Para as contas comerciais, verá o número de contas dun segmento; con todo, o número de contactos que se poden proxectar non aparece. Nalgúns casos, isto podería levar a que o segmento exportado conteña realmente máis perfís de clientes dos que acepta o sistema de destino. O exceder os límites dos resultados dos sistemas de destino omitirá a exportación. 

## <a name="set-up-a-new-export"></a>Configurar unha nova exportación  
Para configurar ou editar unha exportación, necesita ter conexións dispoñibles. As conexións dependen do seu [rol de usuario](permissions.md):
- Os **administradores** teñen acceso a todas as conexións. Tamén poden crear novas conexións cando configuren unha exportación.
- Os **colaboradores** poden ter acceso a conexións específicas. Dependen dos administradores para configurar e compartir conexións. A lista de exportacións móstralles aos colaboradores se poden editar ou só ver unha exportación na columna **Os seus permisos**. Para obter máis información, vaia a [Permitir aos colaboradores usar unha conexión para exportar](connections.md#allow-contributors-to-use-a-connection-for-exports).
- Os **espectadores** só poden ver as exportacións existentes e non crealas.

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

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

As programacións de exportación dependen do estado do seu ambiente. Se hai actualizacións en curso nas [dependencias](system.md#refresh-processes) cando debería iniciarse unha exportación programada, o sistema primeiro completará as actualizacións e logo executará a exportación. Pode ver cando se actualizou por última vez unha exportación na columna **Actualizado**.

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
