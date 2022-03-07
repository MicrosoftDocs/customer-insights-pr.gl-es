---
title: Ver informes de datos
description: Use os informes dispoñibles para ver a actividade en tempo real no seu sitio.
author: darrinw-docs
ms.reviewer: mhart
ms.author: darrinw
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 03b0b4bab0d5d9c2ae641c85aac8174ec1668d45
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 02/16/2022
ms.locfileid: "8229738"
---
# <a name="view-reports"></a>Visualizar informes

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Un informe é unha colección de visualizacións de datos, que utiliza os datos recollidos a través do SDK, que lle axuda a medir e comprender o comportamento dos usuarios. A información de interacción de Dynamics 365 Customer Insights inclúe informes listos para usar (OOB) para proxectos web e móbiles.  

## <a name="web-reports"></a>Informes web

Pode acceder aos informes web en **Descubrir** no panel de navegación esquerdo.

:::image type="content" source="media/report-menu.png" alt-text="Navegación que mostra a lista de informes dispoñibles.":::

### <a name="real-time-usage-report"></a>Informe de uso en tempo real

O informe de **uso en tempo real** ofrece unha visión xeral da actividade actual no seu sitio que se actualiza automaticamente cada minuto. Empregue o uso en tempo real para monitorar o impacto das campañas de márketing, eventos de prensa e outros escenarios no tráfico do seu sitio.

### <a name="key-metrics-reports"></a>Informes de métricas clave

- **Páxinas vistas** lista as vistas de páxinas individuais xunto co número de páxinas vistas totais no período de tempo seleccionado.

- **Visitas** amosa información sobre o número de visitas e a duración da visita.

- **Visitantes** informa sobre visitantes únicos novos e retornados ao seu sitio.

### <a name="content-reports"></a>Informes de contido

- **Ligazóns** amosa información sobre o número e o tipo de clics.

- **Saír das páxinas** lista as ligazóns nas que os visitantes fixeron clic para saír do seu sitio.

### <a name="traffic-sources-reports"></a>Informes de orixes de tráfico

- **Referenciadores** lista os dominios e os URL que derivaron aos visitantes ao seu sitio.

- **Códigos de seguimento** proporciona detalles sobre os códigos de seguimento nas ligazóns que levaron aos visitantes ao seu sitio.

### <a name="visitor-profiles-reports"></a>Informes de perfís de visitantes

- **Dispositivos** lista os dispositivos físicos que se usaron para acceder ao seu sitio.

- **Sistema operativo e exploradores** fornece información sobre os sistemas operativos e exploradores que se estaban executando ao acceder ao seu sitio.

- **Localizacións** amosa información sobre visitantes por país, rexión e cidade.

- **Idiomas** lista as vistas de páxinas polos idiomas preferidos polo visitante.

## <a name="mobile-reports"></a>Informes móbiles

Os informes móbiles agrúpanse en categorías de uso en tempo real, aplicacións e usuarios. Pode acceder aos informes móbiles en **Descubrir** no panel de navegación esquerdo.   

:::image type="content" source="media/mobile-reports.png" alt-text="Interfaz de usuario de información de interacción que mostra o informe de uso en tempo real que representa datos en gráficos e listas.":::   

### <a name="real-time-usage"></a>Uso en tempo real

**Uso en tempo real** ofrece unha visión xeral da actividade actual na súa aplicación para móbil que se actualiza automaticamente cada minuto. Utilice o uso en tempo real para controlar o número de usuarios e sesións activos actualmente na súa aplicación e as vistas da pantalla principais.

### <a name="app-reports"></a>Informes de aplicación

- **Vistas de pantalla** lista as vistas de pantalla para pantallas individuais nunha aplicación e o número total de vistas de pantalla nun período de tempo seleccionado. Pode ver as visualizacións de pantalla por nome de pantalla ou por título de pantalla.

- **Sesións** amosa información sobre o número de sesións e a duración da sesión.

- **Frecuencia de retorno** agrupa os recontos de sesións polo número de días desde a última sesión.

- **Usuarios** amosa usuarios novos e retornados na súa aplicación móbil.

- **Eventos** lista todos os eventos recollidos na súa aplicación, mais o reconto total de cada evento.

### <a name="user-reports"></a>Informes dos usuarios

- **Versións da aplicación** lista as versións da súa aplicación móbil que utiliza a súa base de usuarios.

- **Dispositivos e versións do sistema operativo** ofrece información sobre os dispositivos e sistemas operativos que executan a súa aplicación móbil.

- **Localizacións** amosa información sobre os usuarios da aplicación por país, rexión e cidade.

## <a name="filter-by-time-or-date-range"></a>Filtrar por hora ou intervalo de datas

Pode seleccionar o intervalo temporal ou de datas nun informe web ou móbil para centrarse nun valor ou período de tempo. 

- Para seleccionar un intervalo temporal, na esquina superior dereita da vista do informe, seleccione un valor na lista despregable do informe. Tamén pode escoller un **Intervalo de datas fixado**. 

  :::image type="content" source="media/filter-by-time.png" alt-text="Filtrar por hora ou intervalo de datas.":::   

- Para a maioría dos informes, seleccione un valor nun gráfico ou lista para filtrar o informe.

> [!NOTE]
> A selección do intervalo temporal está desactivada para un informe de uso en tempo real; o intervalo temporal para un informe de uso en tempo real é "now".


[!INCLUDE[footer-include](../includes/footer-banner.md)]
