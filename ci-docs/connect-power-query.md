---
title: Inxerir datos a través de a Power Query conector (contén vídeo)
description: Conectores para fontes de datos baseados en Power Query.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: 50258365c3134c588aa79ec72c66d0de329e0ff1
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642663"
---
# <a name="connect-to-a-power-query-data-source"></a>Conectar a a Power Query orixe de datos

Power Query ofrece un amplo conxunto de conectores para inxerir datos. A maioría destes conectores son compatibles con Dynamics 365 Customer Insights. 

Engadir fontes de datos baseadas en Power Query conectores xeralmente segue os pasos descritos nesta sección. Non obstante, dependendo do conector que use, é necesaria unha información diferente. Para obter máis información, consulte a documentación sobre conectores individuais na páxina [Power Query referencia do conector](/power-query/connectors/).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6EK]

## <a name="create-a-new-data-source"></a>Crear unha nova orixe de datos

1. Vaia a **Datos** > **Orixes de datos**.

1. Seleccione **Engadir orixe de datos**.

1. Seleccione **Microsoft Power Query**.

1. Escriba un **Nome** para a orixe de datos e seleccione **Seguinte** para crear o orixe de datos.

1. Escolla un dos [conectores dispoñibles](#available-power-query-data-sources). Neste exemplo, seleccionamos o **Texto/CSV** conector.

1. Introduza os detalles requiridos na **Configuración de conexión** para o conector seleccionado e seleccione **Seguinte** para ver unha previsualización dos datos.

1. Seleccione **Transformar datos**. Neste paso, engadirá entidades á súa orixe de datos. As entidades son conxuntos de datos. Se ten unha base de datos que inclúe varios conxuntos de datos, cada conxunto de datos é a súa propia entidade.

1. O **Power Query - Editar consultas** diálogo permítelle revisar e refinar os datos. As entidades que os sistemas identificaron na orixe de datos seleccionada aparecen no panel esquerdo.

   > [!div class="mx-imgBorder"]
   > ![Diálogo Editar consultas.](media/data-manager-configure-edit-queries.png "Editar diálogo de consultas")

1. Tamén pode transformar os seus datos. Seleccione unha entidade para editar ou transformar. Use as opcións do Power Query xanela para aplicar transformacións. Cada transformación aparece na lista **Pasos aplicados**. Power Query ofrece numerosas opcións de transformación predefinidas. Para obter máis información, consulte [Power Query Transformacións](/power-query/power-query-what-is-power-query#transformations).

   Recomendamos que use as seguintes transformacións:

   - Se está inxerindo datos dun ficheiro CSV, a primeira fila a miúdo contén cabeceiras. Ir a **Transformar** e selecciona **Use a primeira fila como cabeceiras**.
   - Asegúrese de que o tipo de datos está configurado correctamente. Por exemplo, para os campos de data, seleccione un tipo de data.

1. Para engadir entidades adicionais ao teu orixe de datos no **Editar consultas** diálogo, vai a **Casa** e selecciona **Obter datos**.

1. Seleccione **Gardar** na parte inferior do Power Query ventá para gardar as transformacións. Despois de gardar, atopará o seu orixe de datos en **Datos** > **Orixes de datos**.

1. Na páxina **Orixes de datos**, notarás que o novo orixe de datos está en estado **Actualizando**.

## <a name="available-power-query-data-sources"></a>Dispoñible Power Query fontes de datos

Vexa o [Power Query referencia do conector](/power-query/connectors/) para obter unha lista de conectores que pode usar para importar datos a Customer Insights. 

Conectores cunha marca de verificación no **Información do cliente (fluxos de datos)** columnas están dispoñibles para crear novas fontes de datos baseadas Power Query. Revise a documentación dun conector específico para obter máis información sobre os seus requisitos previos, limitacións e outros detalles.

## <a name="edit-power-query-data-sources"></a>Editar Power Query fontes de datos

> [!NOTE]
> É posible que non se poidan facer cambios nas fontes de datos que se están empregando actualmente nun dos procesos da aplicación (*segmentación*, *coincidencia* ou *combinación*, por exemplo). 
>
> No **Configuración** páxina, pode seguir o progreso de cada un dos procesos activos. Cando se complete un proceso, pode volver á páxina **Orixes de datos** e facer os seus cambios.

1. Vaia a **Datos** > **Orixes de datos**.

2. Seleccione os puntos suspensivos verticais xunto á orixe de datos que desexa cambiar e seleccione **Editar** do menú despregable.

   > [!div class="mx-imgBorder"]
   > ![Opción editar.](media/edit-option-data-sources.png "Editar opción")

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]
   
3. Aplica os teus cambios e transformacións no **Power Query - Editar consultas** diálogo como se describe no [Crea un novo orixe de datos](#create-a-new-data-source) sección.

4. Seleccione **Gardar** en Power Query despois de completar as súas edicións para gardar os seus cambios.


[!INCLUDE [footer-include](includes/footer-banner.md)]
