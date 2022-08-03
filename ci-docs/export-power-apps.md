---
title: Conector de Power Apps (vista previa)
description: Conecte con Power Apps e Power Automate.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 8807e82e65ea20d1a7f7dc07552229f377927eed
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196898"
---
# <a name="power-apps-connector-preview"></a>Conector de Power Apps (vista previa)

Consiga perfís de clientes unificados ás súas aplicacións personalizadas con Microsoft Power Apps.

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>Conectar Power Apps e Dynamics 365 Customer Insights

Customer Insights é unha das moitas [orixes dispoñibles para datos en Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).

Consulte a documentación de Power Apps para aprender a [engadir unha conexión de datos a unha aplicación](/powerapps/maker/canvas-apps/add-data-connection). Recomendamos que revise tamén [como Power Apps usa a delegación para xestionar grandes conxuntos de datos en aplicacións de lenzo](/powerapps/maker/canvas-apps/delegation-overview).

## <a name="available-entities"></a>Entidades dispoñibles

Despois de engadir Customer Insights como conexión de datos, escolla as seguintes entidades Power Apps:

- **Cliente**: para usar datos do [perfil de cliente unificado](customer-profiles.md).
- **UnifiedActivity**: para amosar a [cronoloxía da actividade](activities.md) na aplicación.
- **ContactProfile**: para amosar os contactos dun cliente. Esta entidade só está dispoñible nos contornos de Customer Insights para contas empresariais.

## <a name="limitations"></a>Limitacións

### <a name="retrievable-entities"></a>Entidades recuperables

Só pode recuperar as entidades **Cliente**, **UnifiedActivity**, **Segmentos** e **ContactProfile** a través do conector Power Apps. ContactProfile só está dispoñible nos contornos de Customer Insights para contas empresariais. Amósanse outras entidades porque o conector subxacente as admite a través de desencadeadores en Power Automate.

Podes facer un máximo de 100 chamadas por 60 segundos. Podes chamar ao punto final da API varias veces usando o parámetro $skip. [Obtén máis información sobre o parámetro $skip](/connectors/customerinsights/#get-items-from-an-entity).

### <a name="delegation"></a>Delegación

A delegación funciona para a entidade de **cliente** e a entidade **UnifiedActivity**.

- Delegación para **Cliente** entidade: para usar a delegación para esta entidade, os campos deben estar indexados [índice de busca e filtro](search-filter-index.md).  
- Delegación para **UnifiedActivity**: a delegación para esta entidade só funciona para os campos **ActivityId** e **ID de cliente**.  
- Delegación para **ContactProfile**: a delegación para esta entidade só funciona para os campos **ContactId** e **CustomerId**. ContactProfile só está dispoñible nos contornos de Customer Insights para contas empresariais.

Para obter máis información sobre a delegación, vaia a [funcións e operacións delegables de Power Apps](/powerapps/maker/canvas-apps/delegation-overview).

## <a name="example-gallery-control"></a>Exemplo de control de galería

Opcionalmente, engade perfís de clientes a a [control de galería](/powerapps/maker/canvas-apps/add-gallery).

1. Engada un control de **Galería** a unha aplicación que estea a crear.
  
   :::image type="content" source="media/connector-powerapps9.png" alt-text="Engadir un elemento da galería.":::

1. Seleccione **Cliente** como orixe de datos para os elementos.

   :::image type="content" source="media/choose-datasource-powerapps.png" alt-text="Seleccionar unha orixe de datos.":::

1. Cambia o panel de datos da dereita para seleccionar que campo se mostrará na galería da entidade Cliente.

1. Se desexa mostrar algún campo do cliente seleccionado na galería, encha a propiedade **Texto** dunha etiqueta usando **{Name_of_the_gallery}.Selected.{property_name}**  
    - Por exemplo: _Gallery1.Selected.address1_city_

1. Para mostrar a liña de tempo unificada para un cliente, engada un elemento de galería e a propiedade **Elementos** usando **Filter('UnifiedActivity', CustomerId = {Customer_Id})**  
    - Por exemplo: _Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)_

[!INCLUDE [footer-include](includes/footer-banner.md)]
