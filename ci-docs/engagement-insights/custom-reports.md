---
title: Acerca dos informes personalizados
description: Obteña información acerca da creación e personalización de informes.
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 3fa801bfc8b0aee65c21b90de2423a3d5d5e4e26
ms.sourcegitcommit: d9965f4bfc09391698a34042f6b44367e53819e3
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 09/30/2021
ms.locfileid: "7582875"
---
# <a name="create-and-edit-custom-reports"></a>Crear e editar informes personalizados

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Ademais de informes listos para usar (OOB), pode compilar un informe personalizado con visualizacións de táboa e gráficas para axudarlle a entender o comportamento do usuario. Este artigo explica como crear un informe cos datos que precisa usando visualizacións de gráficas e táboas. Para obter información sobre os informes de OOB, consulte [Ver informes](view-reports.md).

## <a name="create-a-custom-report"></a>Crear un informe personalizado

1. Vaia a **Analizar** > **Personalizados** para acceder á lista de informes personalizados.

1. Seleccione **Novo informe** para comezar a crear un informe personalizado.

   :::image type="content" source="media/new-custom-report.png" alt-text="Novos informes personalizados.":::

1. Decida o tipo de informe que quere crear:

    - Seleccione **Engadir elemento visual** na barra de comandos para crear unha visualización de táboa predefinida.
    - Ou seleccione unha visualización de columna, barra, liña, área, torta, anel ou táboa no panel **Editor de informes**.

1. Na sección **Datos** do panel **Editor de visualización**, seleccione unha das opcións dispoñibles (por exemplo, vistas de páxinas) desde o panel despregable de **Métricas**. Tamén pode engadir **Dimensións** (por exemplo, país) para mostrar na visualización. Para obter máis información, consulte [Ver e crear métricas](metrics.md) e [Ver e crear dimensións](dimensions.md).

   :::image type="content" source="media/page-views.png" alt-text="Escolla unha métrica para o seu informe.":::

1. Seleccione a sección **Deseño** do panel **Editor de visualización** para engadir **Texto do título** e activar e desactivar o **Título**.  Tamén pode cambiar o tipo de visualización seleccionando outro gráfico, como **gráfico circular**.

1. Para cambiar o tamaño e a posición dunha visualización:
   - Seleccione a visualización e arrastre unha das esquinas ou bordos para axustar o seu tamaño.
   - Seleccione a visualización e móvaa a unha nova posición. Tamén pode usar as teclas de frecha para cambiar a posición.
1. Para engadir outra visualización, seleccione **Engadir elemento visual** na barra de comandos.
1. Despois de engadir as visualizacións que queira para o informe, seleccione **Gardar** na barra de comandos.

1. Indique un nome para o informe personalizado e seleccione **Gardar** para crealo.
 
## <a name="filter-a-custom-report"></a>Filtrar un informe personalizado

Pode seleccionar o intervalo temporal ou de datas nun informe personalizado para centrarse nun valor ou período de tempo.

Para seleccionar un intervalo temporal, na esquina superior dereita da vista do informe, seleccione un valor na lista despregable do informe. Tamén pode escoller un **Intervalo de datas fixado*.

:::image type="content" source="media/filter-time-date-range.png" alt-text="Filtrar por hora ou intervalo de datas.":::

Para a maioría dos informes, seleccione **+ Engadir condición** para escoller unha dimensión ou un segmento para filtrar o informe. Para obter máis información, consulte [Ver e crear segmentos](segments.md).

## <a name="edit-a-custom-report"></a>Editar un informe personalizado

1. Vaia a **Analizar** > **Personalizados** para acceder á lista de informes personalizados.

1. Na lista de informes personalizados, seleccione **Máis [...]**. 

1. Escolla **Editar nome** para cambiar o nome do informe.

1. Seleccione o nome do informe e use as opcións **+ Engadir elemento visual** e **Editar** para engadir, eliminar, recolocar ou redimensionar as visualizacións.

1. Para cambiar as propiedades dunha visualización, seleccione o elemento visual, seleccione **...** e logo, **Editar elemento visual**.

   :::image type="content" source="media/edit-visual-control.png" alt-text="Edición das propiedades da gráfica de informes personalizados.":::

1. Despois de editar o informe, seleccione **Gardar** para aplicar as modificacións. 

## <a name="delete-a-custom-report"></a>Eliminar un informe personalizado

1. Vaia a **Analizar** > **Personalizados** para acceder á lista de informes personalizados.

1. Na lista de informes personalizados, seleccione **...**

1. Escolla **Eliminar** para eliminar o informe.

1. Confirme a acción para eliminar o informe permanentemente.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
