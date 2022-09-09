---
title: Ver a configuración do sistema
description: Obteña información acerca da configuración do sistema en Dynamics 365 Customer Insights.
ms.date: 08/09/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-status
- ci-system-about
- ci-system-general
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: 6e60bf7c18939a29f660e06989e262deeb59a39b
ms.sourcegitcommit: d7054a900f8c316804b6751e855e0fba4364914b
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 09/02/2022
ms.locfileid: "9395999"
---
# <a name="view-system-configuration"></a>Ver a configuración do sistema

Consulta a información do sistema, o estado do sistema e o uso da API.

## <a name="view-api-usage"></a>Ver o uso da API

Consulta detalles sobre o uso da API en tempo real e consulta que eventos sucederon nun período de tempo determinado.

1. Ir a **Admin** > **Sistema** e selecciona o **Uso da API** ficha.

1. **Seleccione un período de tempo** para ver.

   O **Uso da API** páxina contén tres seccións:

   - **Chamadas API**: un gráfico que visualiza o número agregado de chamadas á API no período de tempo seleccionado.
   - **Transferencia de datos**: un gráfico que mostra a cantidade de datos que se transferiron a través da API no período de tempo seleccionado.
   - **Operacións**: unha táboa con filas para cada operación da API dispoñible e detalles sobre o uso das operacións. Seleccione un nome de operación ao que ir [a referencia da API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).

## <a name="view-system-information"></a>Ver información do sistema

Consulta o nome de visualización do ambiente, o ID, a rexión, o tipo e o ID da sesión.

1. Ir a **Admin** > **Sistema** e selecciona o **Sobre** ficha.

1. Para ver o idioma e o país/rexión, seleccione **Xeral** ficha.

### <a name="update-preferred-language-or-countryregion"></a>Actualiza o idioma ou o país/rexión preferido

Insights do cliente [admite moitos idiomas](/dynamics365/get-started/availability). A aplicación usa a súa preferencia de idioma para mostrar elementos como o menú, o texto da etiqueta e as mensaxes do sistema no seu idioma preferido.

Os datos importados e a información que introduciu manualmente non se traducen.

1. Ir a **Admin** > **Sistema** e selecciona o **Xeral** ficha.

1. Para cambiar o idioma preferido, escolla o **Idioma** no menú despregable.

1. Para cambiar o formato preferido de datas, hora e números, use o menú despregable **Formato de país/rexión**. Móstrase unha vista previa do formato. O sistema suxire automaticamente unha selección cando escolle un novo idioma.

1. Seleccione **Gardar**.

## <a name="view-system-status"></a>Ver o estado do sistema

Rastrexa o progreso das tarefas, a inxestión de datos, as exportacións de datos e outros procesos importantes do produto. Revisa a información para garantir a integridade das túas tarefas e procesos activos.

1. Ir a **Admin** > **Sistema** e selecciona o **Estado** ficha.

   Visualización de estado e información de procesamento para varios procesos. Ver o **Nome** da tarefa, o **Estado** da súa carreira máis recente, e cando foi **Última actualización**.

1. Para ver os detalles das últimas execucións, seleccione a tarefa ou o nome do proceso.

1. Para ver os detalles do progreso dunha tarefa, seleccione o estado. O **Detalles do progreso** pantallas de paneis.

   :::image type="content" source="media/system-progress-details.png" alt-text="Panel de detalles do progreso do sistema":::

1. Para ver os detalles do progreso de todas as tarefas, seleccione **Todo o fluxo de traballo**.

### <a name="status-definitions"></a>Definicións de estado

O sistema utiliza os seguintes estados para tarefas e procesos:

|Progresión  |Definición  |
|---------|---------|
|Cancelado |O usuario cancelou a tarefa ou proceso antes de que rematase.   |
|Ero   |A tarefa ou o proceso tivo erros.         |
|Erro  |Produciuse un erro na tarefa ou proceso.  |
|Sen iniciar   |Orixe de datos aínda non ten datos inxeridos ou a tarefa aínda está en modo borrador.         |
|Procesando  |A tarefa ou proceso está en curso.  |
|Actualizando    |A tarefa ou proceso está en curso. Para cancelar esta operación, seleccione **Refrescante** e **Cancelar traballo**. Ao deter a actualización dunha tarefa ou proceso volverá ao seu último estado de actualización.       |
|Omitido  |Saltouse a tarefa ou o proceso. Un ou máis dos procesos descendentes dos que depende esta tarefa están fallando ou se omitiron.|
|Correcto  |Tarefa ou proceso completouse correctamente. Para as fontes de datos, indica que os datos se inxeriron correctamente se se menciona un momento no **Actualizado** columna.|
|Na fila | O procesamento está en cola e comezará unha vez que se completen todas as tarefas e procesos anteriores. Para obter máis información, consulte [Procesos de actualización](#refresh-processes).|

### <a name="refresh-processes"></a>Procesos de actualización

A actualización de tarefas e procesos execútase segundo o [horario configurado](schedule-refresh.md).

|Procesar  |Descripción  |
|---------|---------|
|Actividade  |Funciona manualmente (actualización única). Depende do proceso de fusión. A información depende do seu procesamento.|
|Ligazón de análises |Funciona manualmente (actualización única). Depende dos segmentos.  |
|Preparación de análises |Funciona manualmente (actualización única). Depende dos segmentos.  |
|Preparación dos datos   |Necesita unha entidade para funcionar. As entidades orixe de datos dependen da inxestión. As entidades enriquecidas dependen dos enriquecementos. A entidade Cliente depende da fusión.  |
|Orixes de datos   |Non depende de ningún outro proceso. A coincidencia depende do éxito deste proceso.  |
|Enriquecementos   |Funciona manualmente (actualización única). Depende do proceso de fusión. |
|Destinos de exportación |Funciona manualmente (actualización única). Depende dos segmentos.  |
|Conclusións |Funciona manualmente (actualización única). Depende dos segmentos.  |
|Intelixencia   |Depende da fusión.   |
|Buscar coincidencias |Depende do procesamento das orixes de datos utilizadas na definición da coincidencia.      |
|Medidas  |Funciona manualmente (actualización única). Depende do proceso de fusión.  |
|Combinación   |Depende da finalización do proceso de coincidencia. Os segmentos, medidas, enriquecemento, busca, actividades, predicións e preparación de datos dependen da correcta finalización deste proceso.   |
|Perfís   |Funciona manualmente (actualización única). Depende do proceso de fusión. |
|Buscar   |Funciona manualmente (actualización única). Depende do proceso de fusión. |
|Segmentos  |Funciona manualmente (actualización única). Depende do proceso de fusión. A información depende do seu procesamento.|
|Sistema   |Depende da finalización do proceso de coincidencia. Os segmentos, medidas, enriquecemento, busca, actividades, predicións e preparación de datos dependen da correcta finalización deste proceso.   |
|User  |Funciona manualmente (actualización única). Depende das entidades.  |

Seleccione o estado dun proceso para ver os detalles do progreso de todo o traballo no que estaba. Os procesos de actualización anteriores poden axudar a comprender o que podes facer para abordar a **Omitido** ou **En cola** tarefa ou proceso.


[!INCLUDE [footer-include](includes/footer-banner.md)]
