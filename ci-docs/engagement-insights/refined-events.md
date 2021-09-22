---
title: Crear e modificar eventos refinados
description: Como crear e modificar eventos refinados.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 04/30/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 0344bac5f4d43df853309f43c94d95f962937f77c936ed7305c5de4a08835f04
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034772"
---
# <a name="create-and-modify-refined-events"></a>Crear e modificar eventos refinados

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]


Un evento son datos que representan o comportamento dos usuarios, como a actividade nun sitio web.

- Un evento *base* rexistra cando un usuario ve unha páxina (evento de visualización) ou interactúa co contido (evento de acción).
- Un evento *refinado* é unha visualización virtual dun evento base. Defina eventos refinados eliminando e engadindo propiedades ou filtrando eventos en función dos valores das propiedades.

Use eventos refinados para reducir o ámbito dun evento base para [exportar](export-events.md) ou coa finalidade de eliminar as propiedades que non sexan necesarias para a exposición.

## <a name="create-refined-events"></a>Crear eventos refinados

Hai tres formas de crear un evento refinado a partir dun evento base. 

1. Vaia a **Datos**> **Eventos** e escolla unha das seguintes opcións:
    - Seleccione **Novos eventos** e logo **Crear eventos refinados**.
    - Seleccione un evento base para abrir unha vista detallada e seleccione **Crear eventos refinados** no menú superior.
    - Seleccione **Máis [...]** para abrir o menú de atallo para un evento base. Despois seleccione **Crear eventos refinados**.
    
    :::image type="content" source="media/create-refined-events-options.png" alt-text="Opcións para crear eventos refinados.":::

1. No diálogo **Crear eventos refinados**, introduza a seguinte información:

- Seleccione un evento no despregable de **Eventos base** se está a crear un novo evento.
- Introduza un nome na caixa do **nome para mostrar dos eventos refinados**.
- Opcionalmente, actualice o **nome real** suxerido sen usar espazos.

3. Seleccione **Crear** para aplicar a súa configuración.

1. Na vista detallada do seu evento refinado, seleccione **Engadir e eliminar propiedades** para abrir o panel **Editar propiedades**. 

1. Use as caixas de verificación para seleccionar as propiedades que quere mostrar e as que quere ocultar. 
   :::image type="content" source="media/edit-properties-refined-events.png" alt-text="Edición das propiedades para eventos refinados.":::

1. Seleccione **Confirmar** para aplicar a súa selección.

1. Seleccione **Gardar** para gardar a configuración.

## <a name="edit-refined-events"></a>Editar eventos refinados

Pode cambiar o nome e as propiedades dun evento refinado.

### <a name="edit-event-name"></a>Editar o nome do evento

1. Vaia a **Datos** > **Eventos**. 
1. Seleccione **Máis [...]** para un evento e seleccione **Editar nome**.
1. Actualice o nome do evento e seleccione **Renomear**.

### <a name="edit-selected-properties"></a>Editar as propiedades seleccionadas

1. Vaia a **Datos** > **Eventos** e seleccione os eventos refinados para abrir a vista detallada.
1. Seleccione **Engadir e eliminar propiedades**. 
1. Edite a selección das caixas de verificación.
1. Seleccione **Confirmar** e despois **Gardar** para aplicar as modificacións.

Para obter información acerca da exportación de eventos, consulte [Exportar eventos](export-events.md).
[!INCLUDE[footer-include](../includes/footer-banner.md)]
