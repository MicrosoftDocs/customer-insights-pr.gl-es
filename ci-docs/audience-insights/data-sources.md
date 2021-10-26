---
title: Usar fontes de datos para inxerir datos
description: Aprenda a importar datos de varias orixes.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: de31e1f25c08d0bcb5341c5f465b1999de48acf3
ms.sourcegitcommit: 53b133a716c73cb71e8bcbedc6273cec70ceba6c
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 10/15/2021
ms.locfileid: "7645353"
---
# <a name="data-sources-overview"></a>Visión xeral de orixes de datos

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

A capacidade de información do público de Dynamics 365 Customer Insights conéctase a datos dun amplo conxunto de fontes. Conectarse a unha orixe de datos a miúdo chámase proceso de *inxestión de datos*. Despois de inxerir os datos, pode [unificar](data-unification.md) e tomar medidas ao respecto.

## <a name="add-a-data-source"></a>Engadir unha orixe de datos

Consulte os artigos detallados sobre como engadir unha orixe de datos, dependendo da opción que escolla.

Podes engadir unha orixe de datos de tres xeitos principais:

- [A través de decenas de conectores Power Query](connect-power-query.md)
- [Desde un cartafol de Common Data Model](connect-common-data-model.md)
- [Desde o seu propio lago de Microsoft Dataverse](connect-dataverse-managed-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a>Engadir datos de fontes de datos locais

Admite datos interesantes de orixes de datos locais da Información do público en función dos fluxos de datos de Microsoft Power Platform. Os fluxos de datos pódense activar en Customer Insights [proporcionando o URL do contorno de Microsoft Dataverse](create-environment.md) ao configurar o ambiente.

As fontes de datos que se creen despois de asociar un contorno de Dataverse con Customer Insights usarán [fluxos de datos e Power Platform](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) por defecto. Os fluxos de datos admiten conectividade local mediante a pasarela de datos. Elimine e volva crear as orixes de datos que existían antes de que se asociase un ambiente de Dataverse para [usar as pasarelas de datos locais](/data-integration/gateway/service-gateway-app).

As pasarelas de datos dun xa existente contorno de Power BI ou Power Apps serán visibles e pode reutilizalas en Customer Insights. A páxina de fontes de datos mostra ligazóns para ir ao ambiente de Microsoft Power Platform onde pode ver e configurar pasarelas de datos locais.

## <a name="review-ingested-data"></a>Revisa os datos inxeridos

Verá o nome de cada orixe de datos inxerida, o seu estado e a última vez que se actualizaron os datos para esa orixe. Pode ordenar a lista de fontes de datos por cada columna.

> [!div class="mx-imgBorder"]
> ![Orixe de datos engadida.](media/configure-data-datasource-added.png "Orixe de datos engadida")

|Progresión  |Descripción  |
|---------|---------|
|Correcto   |A orixe de datos inxeriuse con éxito se se menciona unha hora na columna **Actualizado**.
|Sen iniciar   |O orixe de datos aínda non ten datos inxeridos ou aínda está en modo borrador.         |
|Actualizando    |Inxestión de datos en curso. Pode cancelar esta operación seleccionando **Deixar de actualizar** na columna **Accións**. Deter a actualización dunha orixe de datos provocará que se restableza o seu estado da última actualización.       |
|Ero     |A inxestión de datos tivo erros.         |

Seleccione o valor na columna **Estado** de calquera orixe de datos para revisar máis detalles. No panel **Detalles do progreso**, expanda as **Fontes de datos**. Seleccione **Ver detalles** para ver máis información sobre o estado de actualización, incluídos os detalles de erros e as actualizacións de procesos posteriores.

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
