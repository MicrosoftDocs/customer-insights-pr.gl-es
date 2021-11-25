---
title: Inxerir datos a través dun conector de Power Query
description: Conectores para orixes de datos baseados en Power Query.
ms.date: 11/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.openlocfilehash: 5d54d33c235e646644e8874e5b0c28898dcff11a
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 11/02/2021
ms.locfileid: "7732216"
---
# <a name="connect-to-a-power-query-data-source"></a>Conéctarse a unha orixe de datos Power Query

Power Query ofrece un amplo conxunto de conectores para inxerir datos. A maioría destes conectores son compatibles con Dynamics 365 Customer Insights. Engadir orixes de datos baseadas nos conectores Power Query xeralmente segue os pasos descritos na seguinte sección. Non obstante, dependendo do conector que use, é necesaria unha información diferente. Para obter máis información, consulte a documentación sobre conectores individuais na [referencia de conectores Power Query](/power-query/connectors/).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6EK]

## <a name="create-a-new-data-source"></a>Crear unha nova orixe de datos

1. Na información do público, vaia a **Datos** > **Orixes de datos**.

1. Seleccione **Engadir orixe de datos**.

1. Escolla o método de **Importar datos** e seleccione **Seguinte**.

1. Escriba un **Nome** para a orixe de datos e seleccione **Seguinte** para crear o orixe de datos. Dea nome ás instrucións: 
   - Comece por unha letra.
   - Use só letras e números. Non se permiten caracteres especiais nin espazos.
   - Empregue entre 3 e 64 caracteres.

1. Escolla un dos [conectores dispoñibles](#available-power-query-data-sources). Para este exemplo, seleccionamos o conector **Texto / CSV**.

1. Introduza os detalles requiridos na **Configuración de conexión** para o conector seleccionado e seleccione **Seguinte** para ver unha previsualización dos datos.

1. Seleccione **Transformar datos**. Neste paso, engadirá entidades á súa orixe de datos. As entidades son conxuntos de datos. Se ten unha base de datos que inclúe varios conxuntos de datos, cada conxunto de datos é a súa propia entidade.

1. O diálogo **Power Query - Editar consultas** permítelle revisar e refinar os datos. As entidades que os sistemas identificaron na orixe de datos seleccionada aparecen no panel esquerdo.

   > [!div class="mx-imgBorder"]
   > ![Diálogo Editar consultas.](media/data-manager-configure-edit-queries.png "Editar diálogo de consultas")

1. Tamén pode transformar os seus datos. Seleccione unha entidade para editar ou transformar. Use as opcións da ventá de Power Query para aplicar transformacións. Cada transformación aparece na lista **Pasos aplicados**. Power Query ofrece numerosas opcións de transformación predefinidas. Para obter máis información, consulte [Transformacións de Power Query](/power-query/power-query-what-is-power-query#transformations).

1. Pode engadir entidades adicionais á súa orixe de datos seleccionando **Obter datos** na caixa de diálogo **Editar consultas**.

   Estas transformacións son moi recomendables:

   - Se está inxerindo datos dun ficheiro CSV, a primeira fila a miúdo contén cabeceiras. Vaia a **Transformar táboa** e seleccione **Usar cabeceiras como primeira fila**.
   - Asegúrese de que o tipo de datos está configurado correctamente.

1. Seleccione **Gardar** na parte inferior da ventá de Power Query para gardar as transformacións. Despois de gardar, atopará o seu orixe de datos en **Datos** > **Orixes de datos**.

1. Na páxina **Orixes de datos**, notarás que o novo orixe de datos está en estado **Actualizando**.

## <a name="available-power-query-data-sources"></a>Orixes de datos de Power Query dispoñibles

Consulte a [Referencia de conectores Power Query](/power-query/connectors/) para obter unha lista actualizada de conectores que pode seleccionar para importar datos a Customer Insights. 

Os conectores cunha marca de verificación na columna **Customer Insights (fluxos de datos)** están dispoñibles para crear novas orixes de datos baseadas en Power Query. Revise a documentación dun conector específico para obter máis información sobre os seus requisitos previos, limitacións e outros detalles.

## <a name="edit-power-query-data-sources"></a>Editar orixes de datos de Power Query

> [!NOTE]
> É posible que non se poidan facer cambios nas fontes de datos que se están empregando actualmente nun dos procesos da aplicación (*segmentación*, *coincidencia* ou *combinación*, por exemplo). 
>
> Usando a páxina **Configuración**, pode rastrexar o progreso de cada un dos procesos activos. Cando se complete un proceso, pode volver á páxina **Orixes de datos** e facer os seus cambios.

1. Na información do público, vaia a **Datos** > **Orixes de datos**.

2. Seleccione os puntos suspensivos verticais xunto á orixe de datos que desexa cambiar e seleccione **Editar** do menú despregable.

   > [!div class="mx-imgBorder"]
   > ![Opción editar.](media/edit-option-data-sources.png "Editar opción")

   [!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]
   
3. Aplique os seus cambios e transformacións no diálogo **Power Query - Editar consultas** como se describe na sección [Crea unha nova orixe de datos](#create-a-new-data-source).

4. Seleccione **Gardar** en Power Query despois de completar as edicións para gardar os cambios.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
