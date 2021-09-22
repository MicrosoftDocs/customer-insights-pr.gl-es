---
title: Ver e crear segmentos
description: Como crear, editar e eliminar segmentos e onde empregalos.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 06/09/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: cedcd58373428dd35ba29ce8fdd00007257f8fa59b0d25bc584b4e832df13604
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036146"
---
# <a name="view-and-create-segments"></a>Ver e crear segmentos

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Os segmentos permiten identificar subconxuntos de visitantes en función das características ou interaccións do sitio web. Os segmentos permiten aplicar filtros e analizar eses subconxuntos. A análise pode axudar a examinar e responder ás tendencias do seu negocio. 

:::image type="content" source="media/segments-page.png" alt-text="Captura de pantalla da aplicación de información de interacción que mostra a lista de segmentos existentes nunha área de traballo.":::

## <a name="view-segments"></a>Ver segmentos

1. Vaia a **Datos** no panel de navegación esquerdo. 

1. Seleccione o separador **Segmentos** para ver unha lista de todos os segmentos na área de traballo. 

## <a name="create-a-segment"></a>Crear un segmento

Os segmentos consisten en regras e condicións que están conectadas con operadores lóxicos. As condicións aplican filtros a unha dimensión seleccionada. Cada segmento pode usar ata cinco dimensións.

O seguinte exemplo mostra un segmento con dúas condicións nunha regra única. Filtra todos os eventos do sitio web onde o explorador é Chrome e o sistema operativo é iOS ou Android.

:::image type="content" source="media/segment-sample.png" alt-text="Segmentos de exemplo con dúas condicións nunha regra para filtrar para eventos do sitio web.":::

Esta sección describe como crear un *segmento en branco* a partir de cero.

1. Vaia a **Datos** > **Segmentos**.

1. Seleccione **Novo segmento**.

1. Na **Biblioteca de recursos**, escolla o atributo polo que quere filtrar. Actualmente só pode crear segmentos baseados en dimensións.

1. Escolla un operador e un valor para o atributo seleccionado. As seguintes operacións son compatibles.
   - **é**: require unha coincidencia exacta para incluír valores. Usa **igual que** para un único valor ou **calquera de** para incluír varios valores.
   - **non é**: require unha coincidencia exacta para excluír valores. Usa **igual que** para un único valor ou **calquera de** para incluír varios valores.
   - **comeza por**: unha cadea coa que comezan os valores coincidentes.
   - **finaliza en**: unha cadea coa que rematan os valores coincidentes.
   - **contén**: unha cadea contida nos valores coincidentes.

1. Para engadir máis condicións a un grupo, pode usar dous operadores lóxicos. Os atributos proxectados téñense en conta cando se usan operadores de definición.
   - Operador **AND**: as dúas condicións deben cumprirse como parte do proceso de segmentación. Esta opción é máis útil cando define condicións entre diferentes entidades.
   - Operador **OR**: calquera das condicións debe ser cumprida como parte do proceso de segmentación. Esta opción é máis útil cando define varias condicións para a mesma entidade.

1. Seleccione **Gardar** e nomee o segmento. 

O segmento aparecerá na páxina Segmentos e pode aplicalo a todos os informes e funís da área de traballo.

## <a name="use-a-segment-in-a-report-or-funnel"></a>Usar un segmento nun informe ou funil

Pode aplicar segmentos a un informe ou funil para filtralos en función das condicións do segmento. Non obstante, non pode aplicar segmentos ao informe de uso en tempo real.

:::image type="content" source="media/segment-reports-filter.png" alt-text="Un informe de visualizacións de páxina cunha lista despregable expandida para escoller os segmentos que aplicar.":::

Para aplicar un segmento, abra o informe ou o funil. Seleccione **Engadir condición** e elixa **Filtrar por segmento**. Escolla o segmento que quere aplicar da lista. O segmento aplicarase ao informe. Se unha gráfica non admite o segmento, mostra un erro.
 
Pode aplicar *ata tres segmentos* a un informe ou funil.

## <a name="edit-a-segment"></a>Editar un segmento

1. Vaia a **Datos** > **Segmentos**.
1. Seleccione o segmento da lista para abrilo. 
1. Cambie ou engada valores segundo sexa necesario.
1. Seleccione **Gardar** para aplicar as modificacións.

## <a name="change-the-name-of-a-segment"></a>Cambiar o nome dun segmento

1. Vaia a **Datos** > **Segmentos**.
1. Na lista de segmentos, seleccione **Máis [...]**. 
1. Escolla **Editar nome** da lista despregable.
1. Introduza o novo nome e seleccione **Renomear**.

## <a name="delete-a-segment"></a>Eliminar un segmento

1. Vaia a **Datos** > **Segmentos**.
1. Na lista de segmentos, seleccione **Máis [...]**. 
1. Escolla **Eliminar** da lista despregable.
1. Seleccione **Eliminar** para confirmar.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
