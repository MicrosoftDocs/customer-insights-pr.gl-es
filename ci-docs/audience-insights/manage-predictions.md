---
title: Tarefas compartidas para escenarios de predición
description: Aprenda a xestionar, solucionar problemas e perfeccionar as predicións.
ms.date: 11/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: 4e7e21a610564b30463b27ab703c291275725895
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 11/02/2021
ms.locfileid: "7731986"
---
# <a name="manage-predictions"></a>Xestionar predicións

Este artigo trata algunhas tarefas que comparten a maioría dos escenarios de predición.

## <a name="troubleshoot-a-failed-prediction"></a>Resolver problemas de predición fallida

1. Vaia a **Intelixencia** > **Predicións** e seleccione o separador **As miñas predicións**.

1. Seleccione os tres puntos verticais xunto á predición para a que desexa ver os rexistros de erros.

1. Seleccione **Rexistros**.

1. Revise todos os erros. Existen varios tipos de erros que poden ocorrer e describen que problema causou o erro. Por exemplo, un erro que consiste en que non hai datos suficientes para predicir con precisión adoita resolverse cargando datos adicionais en Customer Insights.

## <a name="input-data-usability-report"></a>Informe de usabilidade dos datos de entrada

O informe de usabilidade dos datos de entrada ofrece unha visión consolidada dos erros e advertencias que poden xerar as predicións listas para utilizar. Tamén ofrece recomendacións sobre como mellorar o desempeño do modelo.

O informe estará dispoñible despois de que un modelo finalice o seu proceso de adestramento. Créase para cada modelo por separado, independentemente de se se completou correctamente ou non.

### <a name="view-the-input-data-usability-report"></a>Ver informe de usabilidade dos datos de entrada

Despois de que un modelo listo para usar complete o paso de adestramento, vexa o informe:
- Seleccione os puntos suspensivos xunto ao nome do modelo e escolla **Informe de usabilidade dos datos de entrada**.
- Seleccione o estado dun modelo seleccionando **Ver informe de usabilidade dos datos de entrada** no panel lateral.
- Seleccione un dos modelos da lista e seleccione **Informe de usabilidade dos datos de entrada** na barra de comandos.
- Abra a páxina de resultados do modelo e seleccione **Informe de usabilidade dos datos de entrada** na barra de comandos.

### <a name="information-in-the-input-data-usability-report"></a>Información no informe de usabilidade dos datos de entrada

As seguintes columnas do informe conteñen información útil para mellorar os datos do modelo.

:::image type="content" source="media/input-data-usability-report.png" alt-text="Exemplo dun informe de usabilidade dos datos de entrada que mostra unha táboa con erros, avisos e recomendacións.":::

- **Nome:** Nome descritivo do erro, aviso ou recomendación.
- **Paso:** Fase do modelo, tren ou puntuación, a que fai referencia a información.
- **Estado:** Gravidade da información (erro, aviso, recomendación).
- **Nome da columna:** Columna nunha entidade que se debe modificar para mellorar o rendemento do modelo.
- **Nome da entidade:** Nome da entidade que se debe modificar para mellorar o rendemento do modelo.
- **Detalles:** Detalles sobre o erro, aviso ou recomendación.

## <a name="refresh-a-prediction"></a>Actualizar unha predición

As predicións actualizaranse automaticamente no mesmo [programa que actualiza os seus datos](system.md#schedule-tab) tal e como se configura nos axustes. Tamén pode actualizalos manualmente.

1. Vaia a **Intelixencia** > **Predicións** e seleccione o separador **As miñas predicións**.

1. Seleccione os tres puntos verticais xunto á predición que quere actualizar.

1. Seleccione **Actualizar**.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="delete-a-prediction"></a>Eliminar unha predición

Eliminar unha predición tamén elimina a súa entidade de saída.

1. Vaia a **Intelixencia** > **Predicións** e seleccione o separador **As miñas predicións**.

1. Seleccione os tres puntos verticais xunto á predición que quere eliminar.

1. Seleccione **Eliminar**.
