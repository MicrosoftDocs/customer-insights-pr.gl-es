---
title: Conector de Power Apps
description: Conecte con Power Apps e Power Automate.
ms.date: 08/21/2020
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b6ec103e29e218b2f27bfc1193300ea793a6b30b
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405695"
---
# <a name="microsoft-power-apps-connector-preview"></a>Conector de Microsoft Power Apps (vista previa)

Consiga perfís de clientes unificados ás súas aplicacións personalizadas con Power Apps.

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>Conectar Power Apps e Dynamics 365 Customer Insights

Customer Insights é unha das moitas [orixes dispoñibles para datos en Power Apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/working-with-data-sources).

Consulte a documentación de Power Apps para aprender a [engadir unha conexión de datos a unha aplicación](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-data-connection). Recomendamos que revise tamén [como Power Apps usa a delegación para xestionar grandes conxuntos de datos en aplicacións de lenzo](https://docs.microsoft.com/powerapps/maker/canvas-apps/delegation-overview).

## <a name="available-entities"></a>Entidades dispoñibles

Despois de engadir Customer Insights como conexión de datos, pode escoller as seguintes entidades en Power Apps:

- Cliente: para usar datos do [perfil de cliente unificado](customer-profiles.md).
- Actividade de clientes unificada: para mostrar a [liña de tempo da actividade](activities.md) na aplicación.

## <a name="limitations"></a>Limitacións

### <a name="retrievable-entities"></a>Entidades recuperables

Só pode recuperar as entidades **Cliente**, **UnifiedActivity** e **Segmentos** a través do conector Power Apps. Amósanse outras entidades porque o conector subxacente as admite a través de desencadeadores en Power Automate.  

### <a name="delegation"></a>Delegación

A delegación funciona para a entidade de cliente e a entidade UnifiedActivity. 

- Delegación para a entidade **Cliente**: para usar a delegación para esta entidade, os campos deben indexarse en [Buscar e filtrar o índice](search-filter-index.md).  

- Delegación para **UnifiedActivity**: a delegación para esta entidade só funciona para os campos **ActivityId** e **ID de cliente**.  

- Para obter máis información sobre a delegación, consulte [Funcións e operacións delegables de Power Apps](https://docs.microsoft.com/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps). 

## <a name="example-gallery-control"></a>Exemplo de control de galería

Por exemplo, engada perfís de clientes a un [control da galería](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-gallery).

1. Engada un control de **Galería** a unha aplicación que estea a crear.

> [!div class="mx-imgBorder"]
> ![Engadir un elemento da galería](media/connector-powerapps9.png "Engadir un elemento da galería")

1. Seleccione **Cliente** como orixe de datos para os elementos.

    > [!div class="mx-imgBorder"]
    > ![Seleccionar unha orixe de datos](media/choose-datasource-powerapps.png "Seleccionar unha orixe de datos")

1. Pode cambiar o panel de datos da dereita para seleccionar que campo debe mostrar a entidade do cliente na galería.

1. Se desexa mostrar algún campo do cliente seleccionado na galería, encha a propiedade Texto dunha etiqueta: **{Name_of_the_gallery}.Seleccionado.{property_name}**

    Exemplo: Gallery1.Selected.address1_city

1. Para mostrar a liña de tempo unificada para un cliente, engada un elemento de galería e a propiedade Elementos: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**

    Exemplo: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)
