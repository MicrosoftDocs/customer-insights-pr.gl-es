---
title: Configuración do sistema en estatísticas de audiencia
description: Máis información sobre a configuración do sistema na capacidade de información do público de Dynamics 365 Customer Insights.
ms.date: 06/02/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: nimagen
manager: shellyha
ms.openlocfilehash: 7dd72e6512cd87ac70235d21667399298408db21
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405737"
---
# <a name="system-configuration"></a>Configuración do sistema

A páxina **Sistema** inclúe catro lapelas: **Estado**, **Programar**, **Acerca de** e **Xeral**.

> [!div class="mx-imgBorder"]
> ![Páxina do sistema](media/system-tabs.png "Páxina do sistema")

## <a name="status-tab"></a>Separador de Estado

O **separador Estado** permite rastrexar o progreso da inxestión de datos, exportacións de datos así como varios procesos importantes de produtos. Revise a información desta pestana para garantir a integridade dos procesos activos.

Este separador inclúe táboas de estado de **Orixes de datos**, **Procesos do sistema** e **Preparación de datos**. Cada táboa rastrexa o **Nome** da tarefa e a súa entidade correspondente, o **Estado** da súa execución máis recente e cando foi a **Última actualización**.

Visualice os detalles das últimas execucións das tarefas seleccionando o seu nome.

### <a name="status-types"></a>Tipos de estado

Existen seis tipos de estado para as tarefas. Os seguintes tipos de estado tamén aparecen nas páxinas *Coincidir*, *Combinar*, *Orixes de datos*, *Segmentos*, *Medidas*, *Enriquecemento*, *Actividades* e *Predicións*:

- **Procesamento:** a tarefa está en curso. O estado pode cambiar a Correcto ou Incorrecto.
- **Correcto:** a tarefa completouse correctamente.
- **Omitido:** a tarefa omitiuse. Un ou máis dos procesos descendentes dos que depende esta tarefa están fallando ou se omitiron.
- **Fallo:** o procesamento da tarefa fallou.
- **Cancelado:** o procesamento foi cancelado polo usuario antes de que rematase.
- **En cola:** o procesamento está en cola e iniciarase unha vez finalizadas todas as tarefas descendentes. Para obter máis información, consulte [Políticas de actualización](#refresh-policies)

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

Existen dúas opcións no separador **Xeral**, **Idioma** e **Formato de país/rexión**.

A aplicación [admite varios idiomas](supported-languages.md). Para cambiar o idioma preferido, escolla o **Idioma** no menú despregable.

Para cambiar o formato preferido de datas, hora e números, use o menú despregable **Formato de país/rexión**. Mostrarase unha previsualización do formato neste campo. O sistema suxerirá automaticamente unha selección cando escolla un novo idioma.

Seleccione **Gardar** para confirmar as súas seleccións.

## <a name="api-usage-tab"></a>Separador de uso da API

Busque detalles sobre o uso da API en tempo real e vexa os eventos que sucederon nun intervalo de tempo determinado. Para obter máis información, consulte [Incorporación de datos en tempo real](real-time-data-ingestion.md).
