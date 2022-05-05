---
title: Usar fontes de datos para inxerir datos
description: Aprenda a importar datos de varias orixes.
ms.date: 03/18/2022
ms.subservice: audience-insights
ms.topic: overview
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: bcc50c6fa8f8e2a66ef6164bfa9022e068c0e374
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642496"
---
# <a name="data-sources-overview"></a>Visión xeral de orixes de datos



Dynamics 365 Customer Insights conecta con datos dun amplo conxunto de fontes. Conectarse a unha orixe de datos a miúdo chámase proceso de *inxestión de datos*. Despois de inxerir os datos, pode [unificar](data-unification.md) e tomar medidas ao respecto.

## <a name="add-a-data-source"></a>Engadir unha orixe de datos

Consulta os artigos detallados para saber como engadir un orixe de datos, dependendo da opción que elixas.

Podes engadir as seguintes fontes de datos:

- [A través de decenas de Power Query conectores](connect-power-query.md)
- [Desde un cartafol de Common Data Model](connect-common-data-model.md)
- [Desde o seu propio lago de Microsoft Dataverse](connect-dataverse-managed-lake.md)
- [Dende un Azure Synapse Analytics base de datos](connect-synapse.md)

> [!NOTE]
> Se está a usar a versión de proba, a sección de métodos de importación inclúe a **Biblioteca de datos de Customer Insights** opción. Escolla esta opción para seleccionar un conxunto de datos de mostra dispoñible para varias industrias. Para obter máis información, consulte [Dynamics 365 Customer Insights xuízo](trial-signup.md).

## <a name="add-data-from-on-premises-data-sources"></a>Engadir datos de fontes de datos locais

Admítese a inxestión de datos das fontes de datos local en función de Microsoft Power Platform fluxos de datos. Podes activar os fluxos de datos en Customer Insights mediante [proporcionando o Microsoft Dataverse URL do entorno](create-environment.md) ao configurar o ambiente.

Fontes de datos que se crean despois de asociar a Dataverse ambiente co uso de Customer Insights [Power Platform fluxos de datos](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) por defecto. Os fluxos de datos admiten conectividade local mediante a pasarela de datos. Pode eliminar e recrear fontes de datos que existían antes de a Dataverse ambiente estaba asociado [usando pasarelas de datos local](/data-integration/gateway/service-gateway-app).

As pasarelas de datos dun xa existente contorno de Power BI ou Power Apps serán visibles e pode reutilizalas en Customer Insights. A páxina de fontes de datos mostra ligazóns para ir ao ambiente de Microsoft Power Platform onde pode ver e configurar pasarelas de datos locais.

> [!IMPORTANT]
> Asegúrate de que as túas pasarelas estean actualizadas á versión máis recente. Pode instalar unha actualización e reconfigurar unha pasarela a partir dunha solicitude que aparece na pantalla da pasarela directamente ou [descarga a última versión](https://powerapps.microsoft.com/downloads/). Se non utilizas a última versión da pasarela, a actualización do fluxo de datos falla con mensaxes de erro como **Non se admite a palabra clave: propiedades de configuración. Nome do parámetro: palabra clave**.

## <a name="review-ingested-data"></a>Revisa os datos inxeridos
Se o teu ambiente contén Power Platform fluxos de datos, o **Fontes de datos** páxina enumera tres seccións: 
- **Compartido** : fontes de datos que poden xestionar todos os administradores de Customer Insights. Power BI fluxos de datos, a súa propia conta de almacenamento e anexo a un Dataverse -Managed Data Lake son exemplos de fontes de datos compartidas.
- **Xestionado por min** :Power Platform fluxos de datos creados e só podes xestionalos ti. Outros administradores de Customer Insights só poden ver estes fluxos de datos pero non editalos, actualizalos nin eliminalos.
- **Xestionado por outros** :Power Platform fluxos de datos creados por outros administradores. Só podes velos. Enumera o propietario do fluxo de datos co que contactar para obter axuda.
> [!NOTE]
> Todas as entidades poden ser vistas e usadas por outros usuarios. A contextualidade do usuario aplícase só ás fontes de datos e non ás entidades que resultan destes fluxos de datos.

Se non Power Platform úsanse fluxos de datos, non verá ningún grupo ou sección. O **Fontes de datos** páxina contén só unha lista de todas as fontes de datos.

Verá o nome de cada orixe de datos inxerida, o seu estado e a última vez que se actualizaron os datos para esa orixe. Pode ordenar a lista de fontes de datos por cada columna.

> [!div class="mx-imgBorder"]
> ![Orixe de datos engadida.](media/configure-data-datasource-added.png "Orixe de datos engadida")

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

A carga de datos pode levar moito tempo. Despois dunha actualización con éxito, os datos inxeridos poden revisarse desde a páxina **Entidades**. Para obter máis información, consulte [Entidades](entities.md).

## <a name="refresh-a-data-source"></a>Actualizar unha orixe de datos

As fontes de datos pódense actualizar de xeito automático ou actualizarse manualmente a demanda. 

Vaia a **Administrar** > **Sistema** > [**Programar**](system.md#schedule-tab) para configurar actualizacións programadas de todas as fontes de datos inxeridas.

Para actualizar unha orixe de datos baixo demanda, siga estes pasos:

1. Vaia a **Datos** > **Orixes de datos**.

2. Seleccione os puntos suspensivos verticais xunto á orixe de datos que desexa actualizar e seleccione **Actualizar** da lista despregable.

3. A orixe de datos agora está activada para unha actualización manual. Actualizar unha orixe de datos actualizá tanto o esquema de entidade como os datos de todas as entidades especificadas na orixe de datos.

4. Seleccione **Deixar de actualizar** se quere cancelar unha actualización existente e a orixe de datos volverá ao seu último estado de actualización.

## <a name="delete-a-data-source"></a>Eliminar unha orixe de datos

1. Vaia a **Datos** > **Orixes de datos**.

2. Seleccione os puntos suspensivos verticais xunto á orixe de datos que desexa eliminar e seleccione **Eliminar** do menú despregable.

3. Confirme a eliminación.


[!INCLUDE [footer-include](includes/footer-banner.md)]
