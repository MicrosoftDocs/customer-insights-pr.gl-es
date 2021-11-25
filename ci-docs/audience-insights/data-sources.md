---
title: Usar fontes de datos para inxerir datos
description: Aprenda a importar datos de varias orixes.
ms.date: 11/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 27cbd0346b1219c7812f4b90327dd27b645c2b8e
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 11/02/2021
ms.locfileid: "7732140"
---
# <a name="data-sources-overview"></a>Visión xeral de orixes de datos

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

A capacidade de información sobre a audiencia en Dynamics 365 Customer Insights conéctase a datos dun amplo conxunto de fontes. Conectarse a unha orixe de datos a miúdo chámase proceso de *inxestión de datos*. Despois de inxerir os datos, pode [unificar](data-unification.md) e tomar medidas ao respecto.

## <a name="add-a-data-source"></a>Engadir unha orixe de datos

Consulte os artigos detallados sobre como engadir unha orixe de datos, dependendo da opción que escolla.

Podes engadir unha orixe de datos de tres xeitos principais:

- [A través de decenas de conectores Power Query](connect-power-query.md)
- [Desde un cartafol de Common Data Model](connect-common-data-model.md)
- [Do teu propio lago Microsoft Dataverse](connect-dataverse-managed-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a>Engadir datos de fontes de datos locais

A inxestión de datos das fontes de datos local nas estatísticas de audiencia é compatible en función dos fluxos de datos Microsoft Power Platform. Os fluxos de datos pódense activar en Customer Insights mediante [proporcionando o URL do entorno Microsoft Dataverse](create-environment.md) ao configurar o ambiente.

As fontes de datos que se crean despois de asociar un ambiente Dataverse con Customer Insights utilizarán [Power Platform fluxos de datos](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) por defecto. Os fluxos de datos admiten conectividade local mediante a pasarela de datos. Elimina e recrea fontes de datos que existían antes de que se asociase un ambiente Dataverse [use as pasarelas de datos local](/data-integration/gateway/service-gateway-app).

As pasarelas de datos dun contorno existente Power BI ou Power Apps estarán visibles e podes reutilizalas en Customer Insights. A páxina de fontes de datos mostra ligazóns para ir ao ambiente Microsoft Power Platform onde podes ver e configurar pasarelas de datos local.

## <a name="review-ingested-data"></a>Revisa os datos inxeridos

Verá o nome de cada orixe de datos inxerida, o seu estado e a última vez que se actualizaron os datos para esa orixe. Pode ordenar a lista de fontes de datos por cada columna.

> [!div class="mx-imgBorder"]
> ![Orixe de datos engadida.](media/configure-data-datasource-added.png "Orixe de datos engadida")

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

A carga de datos pode levar moito tempo. Despois dunha actualización con éxito, os datos inxeridos poden revisarse desde a páxina **Entidades**. Para obter máis información, consulte [Entidades](entities.md).

## <a name="refresh-a-data-source"></a>Actualizar unha orixe de datos

As fontes de datos pódense actualizar de xeito automático ou actualizarse manualmente a demanda. 

Vaia a **Administrar** > **Sistema** > [**Programar**](system.md#schedule-tab) para configurar actualizacións programadas de todas as fontes de datos inxeridas.

Para actualizar unha orixe de datos baixo demanda, siga estes pasos:

1. Na información do público, vaia a **Datos** > **Orixes de datos**.

2. Seleccione os puntos suspensivos verticais xunto á orixe de datos que desexa actualizar e seleccione **Actualizar** da lista despregable.

3. A orixe de datos agora está activada para unha actualización manual. Actualizar unha orixe de datos actualizá tanto o esquema de entidade como os datos de todas as entidades especificadas na orixe de datos.

4. Seleccione **Deixar de actualizar** se quere cancelar unha actualización existente e a orixe de datos volverá ao seu último estado de actualización.

## <a name="delete-a-data-source"></a>Eliminar unha orixe de datos

1. Na información do público, vaia a **Datos** > **Orixes de datos**.

2. Seleccione os puntos suspensivos verticais xunto á orixe de datos que desexa eliminar e seleccione **Eliminar** do menú despregable.

3. Confirme a eliminación.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
