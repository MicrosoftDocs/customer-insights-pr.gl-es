---
title: Configuración do sistema en estatísticas de audiencia
description: Máis información sobre a configuración do sistema na capacidade de información do público de Dynamics 365 Customer Insights.
ms.date: 10/15/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 3ce767939b8fedf676dc569ede47104ecfe930dd
ms.sourcegitcommit: cd9f9a9d3da71c5420ef5c4c6ead91bc820d17a9
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 10/19/2021
ms.locfileid: "7651838"
---
# <a name="system-configuration"></a>Configuración do sistema

A páxina **Sistema** inclúe as seguintes pestanas:
- [Progresión](#status-tab)
- [Programar](#schedule-tab)
- [Uso de API](#api-usage-tab)
- [Sobre](#about-tab)
- [Xeral](#general-tab)
- [Seguranza](#security-tab)

:::image type="content" source="media/system-tabs.png" alt-text="Pestanas de configuración na páxina do sistema.":::

## <a name="status-tab"></a>Separador de Estado

A **pestana de estado** permítelle rastrexar o progreso da inxestión de datos, as exportacións de datos e outros procesos importantes de produtos. Revise a información desta pestana para garantir a integridade dos procesos activos.

Esta pestana inclúe táboas con información de estado e procesamento de varios procesos. Cada táboa rastrexa o **Nome** da tarefa e a súa entidade correspondente, o **Estado** da súa execución máis recente e cando foi a **Última actualización**.

Visualice os detalles das últimas execucións das tarefas seleccionando o seu nome.

### <a name="status-types"></a>Tipos de estado

Existen seis tipos de estado para as tarefas. Os seguintes tipos de estado tamén aparecen nas páxinas *Coincidir*, *Combinar*, *Orixes de datos*, *Segmentos*, *Medidas*, *Enriquecemento*, *Actividades* e *Predicións*:

- **Procesamento:** a tarefa está en curso. O estado pode cambiar a Correcto ou Incorrecto.
- **Correcto:** a tarefa completouse correctamente.
- **Omitido:** a tarefa omitiuse. Un ou máis dos procesos descendentes dos que depende esta tarefa están fallando ou se omitiron.
- **Fallo:** o procesamento da tarefa fallou.
- **Cancelado:** o procesamento foi cancelado polo usuario antes de que rematase.
- **En cola:** O procesamento está en cola e iniciarase unha vez que se completen todas as tarefas de subida. Para obter máis información, consulte [Políticas de actualización](#refresh-policies)

### <a name="refresh-policies"></a>Políticas de actualización

Esta lista mostra as políticas de actualización de cada un dos principais procesos:

- **Orixes de datos:** execútase segundo o [horario configurado](#schedule-tab). Non depende de ningún outro proceso. A coincidencia depende do éxito deste proceso.
- **Coincidencia:** execútase segundo o [horario configurado](#schedule-tab). Depende do procesamento das orixes de datos utilizadas na definición da coincidencia. A combinación depende do éxito deste proceso.
- **Combinar**: execútase segundo o [horario configurado](#schedule-tab). Depende da finalización do proceso de coincidencia. Os segmentos, medidas, enriquecemento, busca, actividades, predicións e preparación de datos dependen da correcta finalización deste proceso.
- **Segmentos**: execútase manualmente (actualización única) e segundo o [horario configurado](#schedule-tab). Depende de Combinación. A información depende do seu procesamento.
- **Medicións**: execútase manualmente (actualización única) e segundo o [horario configurado](#schedule-tab). Depende de Combinación.
- **Actividades**: execútase manualmente (actualización única) e segundo o [horario configurado](#schedule-tab). Depende de Combinación.
- **Enriquecemento**: execútase manualmente (actualización única) e segundo o [horario configurado](#schedule-tab). Depende de Combinación.
- **Busca**: execútase manualmente (actualización única) e segundo o [horario configurado](#schedule-tab). Depende de Combinación.
- **Preparación de datos:** execútase segundo o [horario configurado](#schedule-tab). Depende de Combinación.
- **Información**: execútase manualmente (actualización única) e segundo o [horario configurado](#schedule-tab). Depende de segmentos.

Seleccione o estado dunha tarefa para ver detalles sobre o progreso de todo o traballo na que estaba. As políticas de actualización anteriores poden axudar a comprender o que pode facer para abordar unha tarefa **Omitida** ou en **Cola**.

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

Customer Insights [admite varios idiomas](/dynamics365/get-started/availability). A aplicación usa a súa preferencia de idioma para mostrar elementos como o menú, o texto da etiqueta e as mensaxes do sistema no seu idioma preferido.

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

   As operacións que utilizan [inxestión de datos en tempo real](real-time-data-ingestion.md) conteñen un botón cun símbolo de binocular para ver o uso da API en tempo real. Seleccione o botón para abrir un panel lateral que conteña detalles de uso para o uso da API en tempo real no contorno actual.   
   Use a caixa **Agrupar por** no panel **Uso da API en tempo real** para escoller como presentar mellor as súas interaccións en tempo real. Pode agrupar os datos por método de API, nome cualificado de entidade (entidade inxerida), autor (orixe do evento), resultado (éxito ou fracaso) ou códigos de erro. Os datos están dispoñibles como gráfico de historial e como táboa.

## <a name="security-tab"></a>Separador de seguranza

A pestana de **Seguridade** permítell e vincular e xestionar o seu propio [Azure Key Vault](/azure/key-vault/general/basic-concepts) para o ambiente.
A key vault específica pódese usar para probar e usar segredos no límite de cumprimento dunha organización. As estatísticas do público poden usar os segredos de Azure Key Vault para [configurar conexións](connections.md) a sistemas de terceiros.

Para obter máis información, consulte [Traer o seu propio Azure Key Vault](use-azure-key-vault.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]