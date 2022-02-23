---
title: Configuración do sistema en estatísticas de audiencia
description: Obtén información sobre a configuración do sistema na capacidade de información sobre o público Dynamics 365 Customer Insights.
ms.date: 11/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 1b790106f8b9617d0c1f244e1d15a74c7ef9a82b
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 11/02/2021
ms.locfileid: "7732359"
---
# <a name="system-configuration"></a>Configuración do sistema

Para acceder ás configuracións do sistema nas estatísticas do público, selecciona na barra de navegación esquerda **Admin** > **Sistema** para ver unha lista de tarefas e procesos do sistema.

A páxina **Sistema** inclúe as seguintes pestanas:
- [Progresión](#status-tab)
- [Programar](#schedule-tab)
- [Uso de API](#api-usage-tab)
- [Sobre](#about-tab)
- [Xeral](#general-tab)
- [Seguranza](#security-tab)

:::image type="content" source="media/system-tabs.png" alt-text="Pestanas de configuración na páxina do sistema.":::

## <a name="status-tab"></a>Separador de Estado

O **Ficha de estado** permítelle seguir o progreso das tarefas, a inxestión de datos, as exportacións de datos e outros procesos importantes do produto. Revisa a información desta pestana para garantir a integridade das túas tarefas e procesos activos.

Esta pestana inclúe táboas con información de estado e procesamento de varios procesos. Cada táboa rastrexa o **Nome** da tarefa e a súa entidade correspondente, o **Estado** da súa execución máis recente e cando foi a **Última actualización**. Podes ver os detalles das últimas execucións seleccionando a tarefa ou o nome do proceso. 

Seleccione o estado a carón da tarefa ou proceso no ficheiro **Estado** columna para abrir **Detalles do progreso** panel.

   :::image type="content" source="media/system-progress-details.png" alt-text="Panel de detalles do progreso do sistema":::

### <a name="status-definitions"></a>Definicións de estado

O sistema utiliza os seguintes estados para tarefas e procesos:

|Progresión  |Definición  |
|---------|---------|
|Cancelouse |O usuario cancelou o procesamento antes de que rematase.   |
|Ero   |A inxestión de datos tivo erros.         |
|Erro  |Produciuse un erro ao procesar.  |
|Sen iniciar   |O orixe de datos aínda non ten datos inxeridos ou aínda está en modo borrador.         |
|Procesando  |A tarefa ou proceso está en curso.  |
|Actualizando    |Inxestión de datos en curso. Pode cancelar esta operación seleccionando **Deixar de actualizar** na columna **Accións**. Deter a actualización dunha orixe de datos provocará que se restableza o seu estado da última actualización.       |
|Omitido  |Saltouse a tarefa ou o proceso. Un ou máis dos procesos descendentes dos que depende esta tarefa están fallando ou se omitiron.|
|Correcto  |Tarefa ou proceso completouse correctamente. Para as fontes de datos, indica que os datos se inxeriron correctamente se se menciona un momento no **Actualizado** columna.|
|Na fila | O procesamento está en cola e comezará unha vez que se completen todas as tarefas e procesos anteriores. Para obter máis información, consulte [Procesos de actualización](#refresh-processes).|

### <a name="refresh-processes"></a>Procesos de actualización

A actualización de tarefas e procesos execútase segundo o [horario configurado](#schedule-tab). 

|Procesar  |Descripción  |
|---------|---------|
|Actividade  |Funciona manualmente (actualización única). Depende do proceso de fusión. A información depende do seu procesamento.|
|Ligazón de análises |Funciona manualmente (actualización única). Depende dos segmentos.  |
|Preparación de análises |Funciona manualmente (actualización única). Depende dos segmentos.  |
|Preparación dos datos   |Depende da fusión.   |
|Orixes de datos   |Non depende de ningún outro proceso. A coincidencia depende do éxito deste proceso.  |
|Enriquecementos   |Funciona manualmente (actualización única). Depende do proceso de fusión. |
|Destinos de exportación |Funciona manualmente (actualización única). Depende dos segmentos.  |
|Conclusións |Funciona manualmente (actualización única). Depende dos segmentos.  |
|Intelixencia   |Depende da fusión.   |
|Buscar coincidencias |Depende do procesamento das orixes de datos utilizadas na definición da coincidencia.      |
|Medidas  |Funciona manualmente (actualización única). Depende do proceso de fusión.  |
|Combinación   |Depende da finalización do proceso de coincidencia. Os segmentos, medidas, enriquecemento, busca, actividades, predicións e preparación de datos dependen da correcta finalización deste proceso.   |
|Perfís   |Funciona manualmente (actualización única). Depende do proceso de fusión. |
|Busca   |Funciona manualmente (actualización única). Depende do proceso de fusión. |
|Segmentos  |Funciona manualmente (actualización única). Depende do proceso de fusión. A información depende do seu procesamento.|
|Sistema   |Depende da finalización do proceso de coincidencia. Os segmentos, medidas, enriquecemento, busca, actividades, predicións e preparación de datos dependen da correcta finalización deste proceso.   |
|Usuario  |Funciona manualmente (actualización única). Depende das entidades.  |

Seleccione o estado dun proceso para ver os detalles do progreso de todo o traballo no que estaba. Os procesos de actualización anteriores poden axudar a comprender o que podes facer para abordar a **Omitido** ou **En cola** tarefa ou proceso.

## <a name="schedule-tab"></a>Separador de programación

Use o separador **Programar** para programar actualizacións automáticas de todas as [fontes de datos inxeridas](data-sources.md). As actualizacións automáticas axudan a asegurar que as actualizacións das súas orixes de datos se reflictan nos seus perfís de clientes unificados.

1. Na información do público, vaia a **Administrar** > **Sistema** e seleccione o separador **Programar**.

2. O estado predeterminado para a actualización programada é **Desactivado**. Para activar as actualizacións programadas, cambie o axuste na parte superior da pantalla a **Activado**.

3. Elixa entre actualizacións **Semanalmente** (predeterminado) e **Diariamente**. Se pretende programar actualizacións semanais, seleccione un ou varios días nos que desexa realizalas.

4. Estableza a súa **Zona horaria**, use o menú despregable **Tempo** para configurar o tempo de actualización. Ao concluír, seleccione **Establecer**. Se desexa programar varias actualizacións nun só día, seleccione **Engadir outra hora**.

5. Seleccione **Gardar** para aplicar as modificacións.

## <a name="about-tab"></a>Separador Acerca de

O separador **Acerca de** contén o **Nome para mostrar** da súa organización, o **ID do ambiente** activo, a **Rexión** e o teu **ID da sesión**. Se ten máis dun ambiente de traballo, debe poñer a cada un un nome de visualización facilmente identificable.

## <a name="general-tab"></a>Separador Xeral

Pode cambiar o idioma e o formato do país/rexión na pestana **Xeral**.

Información do cliente [admite moitos idiomas](/dynamics365/get-started/availability). A aplicación usa a súa preferencia de idioma para mostrar elementos como o menú, o texto da etiqueta e as mensaxes do sistema no seu idioma preferido.

Os datos importados e a información que introduciu manualmente non se traducen.

### <a name="update-the-settings"></a>Actualizar a configuración

Para cambiar o idioma preferido, escolla o **Idioma** no menú despregable.

Para cambiar o formato preferido de datas, hora e números, use o menú despregable **Formato de país/rexión**. Mostrarase unha previsualización do formato neste campo. O sistema suxerirá automaticamente unha selección cando escolla un novo idioma.

Seleccione **Gardar** para confirmar as súas seleccións.

## <a name="api-usage-tab"></a>Separador de uso da API

Busque detalles sobre o uso da API en tempo real e vexa que eventos ocorreron nun período de tempo determinado. Escolla o período de tempo no menú despregable **Seleccionar un intervalo temporal**. 

O **Uso da API** contén tres seccións: 
- **Chamadas API**: un gráfico que visualiza o número agregado de chamadas á API no período de tempo seleccionado.

- **Transferencia de datos**: un gráfico que mostra a cantidade de datos que se transferiron a través da API no período de tempo seleccionado.

-  **Operacións**: unha táboa con filas para cada operación da API dispoñible e detalles sobre o uso das operacións. Pode seleccionar un nome de operación para ir á [referencia da API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).

   Operacións que usan [inxestión de datos en tempo real](real-time-data-ingestion.md) contén un botón cun símbolo binocular para ver o uso da API en tempo real. Seleccione o botón para abrir un panel lateral que conteña detalles de uso para o uso da API en tempo real no contorno actual.   
   Use a caixa **Agrupar por** no panel **Uso da API en tempo real** para escoller como presentar mellor as súas interaccións en tempo real. Pode agrupar os datos por método de API, nome cualificado de entidade (entidade inxerida), autor (orixe do evento), resultado (éxito ou fracaso) ou códigos de erro. Os datos están dispoñibles como gráfico de historial e como táboa.

## <a name="security-tab"></a>Separador de seguranza

A pestana de **Seguridade** permítell e vincular e xestionar o seu propio [Azure Key Vault](/azure/key-vault/general/basic-concepts) para o ambiente.
A key vault específica pódese usar para probar e usar segredos no límite de cumprimento dunha organización. As estatísticas do público poden usar os segredos de Azure Key Vault para [configurar conexións](connections.md) a sistemas de terceiros.

Para obter máis información, consulte [Traer o seu propio Azure Key Vault](use-azure-key-vault.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
