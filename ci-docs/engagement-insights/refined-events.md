---
title: Crear e modificar eventos
description: Como crear e modificar eventos.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 935dc4cd41218842e8406b747daef47de04e337a
ms.sourcegitcommit: 693458e13e4b4d94b6205093559912f6a4dc4a1c
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 10/06/2021
ms.locfileid: "7606205"
---
# <a name="create-and-modify-events"></a>Crear e modificar eventos

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Un evento son datos que representan o comportamento dos usuarios, como a actividade nun sitio web.

- Un evento *base* rexistra cando un usuario ve unha páxina (evento de visualización) ou interactúa co contido (evento de acción).
- Un evento *refinado* é unha visualización virtual dun evento base. Defina eventos refinados eliminando e engadindo propiedades ou filtrando eventos en función dos valores das propiedades.

## <a name="prerequisites"></a>Requisitos previos

Para obter eventos, deberá conectar primeiro os datos do sitio web á información de interacción cun fragmento de código. Para obter máis información, consulte [Instalar o SDK web nun sitio web](instrument-website.md).

 :::image type="content" source="media/new-events-connect-data.png" alt-text="Conecte os seus datos en primeiro lugar.":::

## <a name="create-refined-events"></a>Crear eventos refinados

Use eventos refinados para reducir o ámbito dun evento base para [exportar](export-events.md) ou coa finalidade de eliminar as propiedades que non sexan necesarias para a exposición.

> [!NOTE]
> Unha vez que engada o SDK web ao seu sitio web, poderá ver os seus eventos básicos e crear eventos refinados. 

Para ver os seus eventos básicos:

1. Vaia a **Datos** no panel de navegación esquerdo.

1. Seleccione **Eventos** para ver unha lista de todos os eventos no espazo de traballo.

    :::image type="content" source="media/data-events.png" alt-text="Ver eventos.":::

Para crear un evento refinado a partir dun evento base: 

1. Vaia a **Datos** > **Eventos** e seleccione **+ Novos eventos** na parte superior da pantalla.

1. No diálogo **Novos eventos**, seleccione **Crear eventos refinados** e logo seleccione **Seguinte**.
   
     :::image type="content" source="media/new-events-wizard.png" alt-text="Asistente de eventos novos.":::
     
1. No diálogo **Novos eventos**, introduza a seguinte información:

   - Seleccione un evento no menú despregable **Eventos base**.
   - Introduza un nome na caixa do **nome para mostrar dos eventos refinados**.
   - Opcionalmente, actualice o **nome real** suxerido sen usar espazos.

1. Seleccione **Crear** para aplicar a súa configuración.

O evento refinado aparece agora na súa lista de **Eventos**.

### <a name="edit-event-name"></a>Editar o nome do evento

Pode cambiar o nome e as propiedades dun evento base ou refinado.

1. Vaia a **Datos** > **Eventos**. 

1. Seleccione **Máis [...]** para un evento e seleccione **Editar nome**.
    
     :::image type="content" source="media/create-refined-events-options.png" alt-text="Opcións para crear eventos refinados.":::

3. Actualice o nome do evento e seleccione **Renomear**.

### <a name="view-the-details-of-a-refined-event"></a>Consulte os detalles dun evento refinado:

1. Na lista **Evento**, seleccione o seu evento base ou refinado. 

1. Seleccione **Engadir e eliminar propiedades** na parte superior da pantalla para abrir o panel **Editar propiedades**. 

     :::image type="content" source="media/add-remove-properties.png" alt-text="Engadir e eliminar propiedades.":::

1. Use as caixas de verificación para seleccionar as propiedades que quere mostrar e as que quere ocultar. 

   :::image type="content" source="media/edit-properties-refined-events.png" alt-text="Edición das propiedades para eventos refinados.":::

1. Seleccione **Confirmar** para aplicar a súa selección e logo seleccione **Gardar**.


### <a name="edit-selected-properties-for-a-refined-event"></a>Editar as propiedades seleccionadas para un evento refinado

1. Vaia a **Datos** > **Eventos** e seleccione os eventos refinados para abrir a vista detallada.
1. Seleccione **Engadir e eliminar propiedades**. 
1. Edite a selección das caixas de verificación.
1. Seleccione **Confirmar** e despois **Gardar** para aplicar as modificacións.

Para obter información acerca da exportación de eventos, consulte [Exportar eventos](export-events.md).
[!INCLUDE[footer-include](../includes/footer-banner.md)]
