---
title: Usar segmentos de información do público para filtrar os informes de información de interacción
description: Use segmentos de información do público en análises interactivas de datos de comportamento capturados pola información de interacción no sitio web dun cliente.
ms.date: 07/27/2021
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 9c8c7a1a9216e04ebee100c548afbc745af396ec
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 02/16/2022
ms.locfileid: "8230484"
---
# <a name="use-audience-insights-segments-to-filter-engagement-insights-reports"></a>Usar segmentos de información do público para filtrar os informes de información de interacción

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Coa información de interacción, pode usar segmentos de información do público en análises interactivas de datos de comportamento capturados pola información de interacción no seus sitios web.

## <a name="prerequisite"></a>Requisito previo

- Un ambiente de información de interacción no que ten datos de segmentos de información do público ligados ao ambiente de información do público onde se crean os perfís de clientes e segmentos. Máis información: [Crear unha ligazón entre a información do público e a información de interacción](integrate-audience-insights-engagement-insights.md)

## <a name="create-audience-insights-segments"></a>Crear segmentos de información do público 

> [!IMPORTANT]
> Para que os segmentos de información do público aparezan na información de interacción, primeiro debe [executar procesos descendentes e de combinación](../audience-insights/merge-entities.md). Os procesos descendentes son importantes porque xeran unha táboa única que prepara os segmentos de información do público para ser compartidos coa información de interacción. (Se está programada unha actualización do sistema, incluirá automaticamente os procesos descendentes).

Pode usar segmentos de información do público en informes listos para usar de información de interacción ou informes personalizados creados por vostede. Para obter máis información, vaia a [Informes de perfís listos para usar](profile-reports.md) e [Crear e editar informes personalizados](custom-reports.md).

**Para usar segmentos de información do público nos informes de información de interacción**

1. Na páxina **Área de traballo**, seleccione **Datos** e, a continuación, seleccione o separador **Segmentos**.

    :::image type="content" source="media/integrate-audience-insights-segments1.png" alt-text="Seleccionar o separador Segmentos.":::

   >[!NOTE]
   > Se selecciona un segmento de información do público, accederá á información do público, onde pode descubrir como se creou ese segmento en termos de regras e lóxica. Para obter máis información sobre os segmentos de información do público, vaia a [Ver e crear segmentos](../audience-insights/segments.md).

2. Seleccione un informe listo para usar ou [cree un informe personalizado](custom-reports.md) e, a continuación, seleccione **Engadir condición**. (Para este exemplo, escollemos o informe **Visualizacións da páxina**).

    :::image type="content" source="media/integrate-audience-insights-segments2.png" alt-text="Engadir unha condición.":::

3. Seleccione **Filtrar por segmento**, expanda a lista **Tipo de segmento** e logo seleccione **Demográfico**.

    :::image type="content" source="media/integrate-audience-insights-segments3.png" alt-text="Seleccionar o tipo de segmento demográfico.":::

4. Expanda a lista **Nome do segmento** e, a continuación, escolla un segmento de información do público.

    :::image type="content" source="media/integrate-audience-insights-segments4.png" alt-text="Escoller un segmento.":::

5. Pode aplicar un ou máis segmentos, incluídos os segmentos de comportamento (información de interacción) e demográficos (información do público). 

    :::image type="content" source="media/integrate-audience-insights-segments6.png" alt-text="Informe de visualizacións de páxina restrinxido aos segmentos Clientes de Estados Unidos e Páxina principal.":::

Na imaxe anterior, os segmentos **Clientes de Estados Unidos** e **Páxina principal** seleccionáronse, o que restrinxe o informe **Visualizacións da páxina** para mostrar só eses dous segmentos. 


>[!NOTE]
> Pode usar segmentos de información do público para filtrar informes listos para usar, informes personalizados e funís na información de interacción. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]