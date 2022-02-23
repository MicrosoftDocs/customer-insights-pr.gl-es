---
title: Usar fontes de datos para inxerir datos
description: Aprenda a importar datos de varias orixes.
ms.date: 12/06/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: overview
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: ca979527c9cb8418e12af4a74513033047e4901c
ms.sourcegitcommit: 3807202283dd116a30f900a163d8141db621e5a8
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 01/28/2022
ms.locfileid: "8046586"
---
# <a name="data-sources-overview"></a>Visión xeral de orixes de datos



A capacidade de información do público de Dynamics 365 Customer Insights conéctase a datos dun amplo conxunto de fontes. Conectarse a unha orixe de datos a miúdo chámase proceso de *inxestión de datos*. Despois de inxerir os datos, pode [unificar](data-unification.md) e tomar medidas ao respecto.

## <a name="add-a-data-source"></a>Engadir unha orixe de datos

Consulta os artigos detallados para saber como engadir un orixe de datos, dependendo da opción que elixas.

Podes engadir as seguintes fontes de datos:

- [Power Query conectores](connect-power-query.md)
- [Common Data Model](connect-common-data-model.md)
- [Microsoft Dataverse lago](connect-dataverse-managed-lake.md)

> [!NOTE]
> Se está a usar a versión de proba, a sección de métodos de importación inclúe a **Biblioteca de datos de Customer Insights** opción. Escolla esta opción para seleccionar un conxunto de datos de mostra dispoñible para varias industrias. Para obter máis información, consulte [Dynamics 365 Customer Insights xuízo](../trial-signup.md).

## <a name="add-data-from-on-premises-data-sources"></a>Engadir datos de fontes de datos locais

Admite datos interesantes de orixes de datos locais da Información do público en función dos fluxos de datos de Microsoft Power Platform. Podes activar os fluxos de datos en Customer Insights mediante [proporcionando o Microsoft Dataverse URL do entorno](create-environment.md) ao configurar o ambiente.

Fontes de datos que se crean despois de asociar a Dataverse ambiente co uso de Customer Insights [Power Platform fluxos de datos](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) por defecto. Os fluxos de datos admiten conectividade local mediante a pasarela de datos. Pode eliminar e recrear fontes de datos que existían antes de a Dataverse ambiente estaba asociado [usando pasarelas de datos local](/data-integration/gateway/service-gateway-app).

As pasarelas de datos dun xa existente contorno de Power BI ou Power Apps serán visibles e pode reutilizalas en Customer Insights. A páxina de fontes de datos mostra ligazóns para ir ao ambiente de Microsoft Power Platform onde pode ver e configurar pasarelas de datos locais.

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
