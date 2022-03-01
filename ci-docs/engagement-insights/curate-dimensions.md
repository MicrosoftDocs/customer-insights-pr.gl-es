---
title: Usar dimensións demográficas para dividir os datos de comportamento (dimensións recompiladas)
description: Utilice dimensións recompiladas de perfís unificados para habilitar as propiedades dos perfís de clientes da información do público.
ms.date: 07/27/2021
ms.service: customer-insights
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 50bb800c9e097d03cc6f26f79819c741ab5e8baf
ms.sourcegitcommit: 1c396394470df8e68c2fafe3106567536ff87194
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 08/30/2021
ms.locfileid: "7461101"
---
# <a name="use-demographic-dimensions-for-splitting-behavioral-data"></a>Usar dimensións demográficas para dividir os datos de comportamento

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Ao usar dimensións demográficas de perfís unificados, os usuarios de información de interacción poden acceder ás propiedades dos perfís de información do público. A continuación, pode usar estas propiedades en análises interactivas de datos de comportamento, incluídos os datos capturados pola información de interacción no seu sitio web ou aplicación móbil.

>[!NOTE]
> A información de interacción inclúe dimensións listas para usar para as propiedades dos eventos. Máis información: [Ver e crear dimensións](dimensions.md)

## <a name="prerequisite"></a>Requisito previo

- Un ambiente de información de interacción no que ten datos de perfil de cliente ligados ao ambiente de información do público onde se crean os perfís de clientes. Máis información: [Crear unha ligazón entre a información do público e a información de interacción](integrate-audience-insights-engagement-insights.md)

> [!NOTE]
> Despois de crear unha ligazón entre os ambientes de información do público e información de interacción, pode que só queira datos específicos das propiedades dos perfís dos clientes, que poden ser útiles como dimensións na información de interacción. Para obter máis información, vaia a [Permitir segmentos e atributos de perfís unificados de información do público](integrate-audience-insights-engagement-insights.md#enable-audience-insights-unified-profiles-attributes-and-segments).<!--note from editor: Suggested. -->

## <a name="create-a-new-custom-report"></a>Crera un novo informe personalizado

1. No panel esquerdo, seleccione **Personalizar** > **Novo informe** e, a continuación, seleccione a métrica que desexe. (Para este exemplo, escollemos **Visualizacións de páxina por hora**.)

    :::image type="content" source="media/curated-dimensions1.png" alt-text="Seleccionar unha métrica.":::

2. No editor de visualizacións, seleccione **Dimensións** e, a continuación, seleccione **Demográfico** no menú despregable **Tipo de dimensión**.

    :::image type="content" source="media/curated-dimensions2.png" alt-text="Seleccionar Demográfico.":::

3. Seleccione unha dimensión **Signal.Customer.*xxx***. (Este exemplo mostra Signal.Customer.Country.)

    :::image type="content" source="media/curated-dimensions3.png" alt-text="Seleccionar unha dimensión.":::
  
## <a name="limitations"></a>Limitacións

Actualmente só pode usar dimensións demográficas para dividir os datos de comportamento.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
