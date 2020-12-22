---
title: Usar fontes de datos para inxerir datos
description: Aprenda a importar datos de varias orixes.
ms.date: 11/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: a720641f7499fc71ff5bceeba48d296c51f77242
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643951"
---
# <a name="overview-about-data-sources"></a>Visión xeral sobre as orixes de datos

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

A capacidade de información do público de Dynamics 365 Customer Insights conéctase a datos dun amplo conxunto de fontes. Conectarse a unha orixe de datos a miúdo chámase proceso de *inxestión de datos*. Despois de inxerir os datos, pode [unificar](data-unification.md) e tomar medidas ao respecto.

## <a name="add-a-data-source"></a>Engadir unha orixe de datos

Consulte os artigos detallados sobre como engadir unha orixe de datos, dependendo da opción que escolla.

Podes engadir unha orixe de datos de tres xeitos principais:

- [A través de decenas de conectores Power Query](connect-power-query.md)
- [Desde un cartafol de Common Data Model](connect-common-data-model.md)
- [Desde o seu propio lago de Common Data Service](connect-common-data-service-lake.md)

> [!NOTE]
> Aínda non pode engadir datos das orixes de datos locais.

## <a name="review-ingested-data"></a>Revisa os datos inxeridos

Verá o nome de cada orixe de datos inxerida, o seu estado e a última vez que se actualizaron os datos para esa orixe. Pode ordenar a lista de fontes de datos por cada columna.

> [!div class="mx-imgBorder"]
> ![Orixe de datos engadida](media/configure-data-datasource-added.png "Orixe de datos engadida")

|Estado  |Descripción  |
|---------|---------|
|Correcto   |A orixe de datos inxeriuse con éxito se se menciona unha hora na columna **Actualizado**.
|Sen iniciar   |O orixe de datos aínda non ten datos inxeridos ou aínda está en modo borrador.         |
|Actualizando    |Inxestión de datos en curso. Pode cancelar esta operación seleccionando **Deixar de actualizar** na columna **Accións**. Deter a actualización dunha orixe de datos provocará que se restableza o seu estado da última actualización.       |
|Produciuse un erro     |A inxestión de datos tivo erros.         |

Seleccione **Actualizar o estado** para revisar máis detalles sobre o estado de actualización, incluídos os detalles de erros e as actualizacións de procesos posteriores.

A carga de datos pode levar un tempo. Despois dunha actualización con éxito, os datos inxeridos poden revisarse desde a páxina **Entidades**. Para obter máis información, consulte [Entidades](entities.md).

## <a name="refresh-a-data-source"></a>Actualizar unha orixe de datos

As fontes de datos pódense actualizar de xeito automático ou actualizarse manualmente a demanda. 

Vaia a **Administrar** > **Sistema** > [**Programar**](system.md#schedule-tab) para configurar actualizacións programadas de todas as fontes de datos inxeridas.

Para actualizar unha orixe de datos baixo demanda, siga estes pasos:

1. Na información do público, vaia a **Datos** > **Orixes de datos**

2. Seleccione os puntos suspensivos verticais xunto á orixe de datos que desexa actualizar e seleccione **Actualizar** da lista despregable.

3. A orixe de datos agora está activada para unha actualización manual. Se actualiza unha orixe de datos, actualizaranse tanto o esquema de entidades como os datos de todas as entidades especificadas na orixe de datos.

4. Seleccione **Deixar de actualizar** se quere cancelar unha actualización existente e a orixe de datos volverá ao seu último estado de actualización.

## <a name="delete-a-data-source"></a>Eliminar unha orixe de datos

1. Na información do público, vaia a **Datos** > **Orixes de datos**.

2. Seleccione os tres puntos verticais xunto á orixe de datos que desexa eliminar e seleccione **Eliminar** no menú despregable.

3. Confirme a eliminación.
