---
title: Información de segmentos para segmentos existentes
description: Obteña información sobre os segmentos existentes para ver diferenzas e aspectos comúns.
ms.date: 06/10/2020
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-segment-insights
- customerInsights
ms.openlocfilehash: 526b593ba9b038de3d3c27f6a7683ca76b3f2319
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642583"
---
# <a name="segment-insights-preview"></a>Información do segmento (previsualización)

Descubra información e ideas adicionais sobre os seus segmentos existentes. Descubra o que diferencia dous segmentos ou o que teñen en común.

## <a name="segment-overlap"></a>Superposición de segmentos

A análise do solapamento dos segmentos mostra cantos e que clientes son comúns a dous ou máis segmentos. Por exemplo, como un segmento de clientes frecuentes se solapa cun segmento que contén clientes satisfeitos co seu servizo ou produto.
Tamén pode analizar como cambia a superposición para atributos específicos.

### <a name="run-an-overlap-analysis"></a>Realizar unha análise de solapamentos

1. Vaia a **Segmentos** e seleccione o separadpr **Información (vista previa)**.

1. Seleccione **Novo** e escolla a opción **Superposición** no panel **Escoller tipo de información**.

1. Escolla os segmentos de interese e seleccione **Seguinte**.

1. Opcionalmente, escolla un ou varios campos de interese para analizar solapamentos para cada valor do campo posible e seleccione **Seguinte**.

1. Proporcione un nome para a análise de solapamentos, un nome de visualización opcional e unha descrición.

1. Seleccione **Gardar** para iniciar a análise. A análise de solapamentos está lista cando o estado cambia de Actualizar a Exitoso.

### <a name="view-and-optimize-an-overlap-analysis"></a>Ver e optimizar unha análise de solapamento

Despois de completar a análise, busque detalles sobre esta información en **Segmentos** > **Información (vista previa)**.

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-overlap.png" alt-text="Detalles da información do solapamento do segmento.":::

Seleccione unha información para ver os resultados da análise:

- Número de membros que se solapan nos segmentos seleccionados para a súa análise.
- Número de membros incluídos nun dos segmentos pero non no resto dos segmentos.
- Se seleccionou campos mentres configura a análise de solapamento, atoparáos nas pestañas correspondentes. Pode usar o menú despregable de filtros para seleccionar calquera nivel de interese de atributo e a táboa na parte inferior amosará os datos correspondentes.

## <a name="segment-differentiators"></a>Diferenciadores de segmentos

Os diferenciadores de segmentos axúdanlle a descubrir que diferencia un segmento do resto dos seus clientes ou doutro segmento. Só ten que seleccionar un segmento e o sistema identificará atributos e medidas do perfil que distinguen o segmento seleccionado.

### <a name="run-a-differentiator-analysis"></a>Realizar unha análise de diferenciadores

1. Vaia a **Segmentos** e seleccione o separadpr **Información (vista previa)**.

1. Seleccione **Novo** e escolla a opción **Superposición** no panel **Escoller tipo de información**.

1. Escolla o segmento que desexa analizar como **Segmento primario** e seleccione **Seguinte**.

1. Escolla **Todos os clientes** ou a **Segmento secundario** para comparar o seu segmento principal e seleccione **Seguinte**.

1. Opcionalmente, elixa un ou varios campos de interese para centrar a análise en atributos específicos e seleccione **Seguinte**.

1. Proporcione un nome para a análise de solapamentos, un nome de visualización opcional e unha descrición.

1. Seleccione **Gardar** para iniciar a análise. A análise de solapamentos está lista cando o estado cambia de Actualizar a Exitoso.

### <a name="view-and-optimize-a-differentiators-analysis"></a>Ver e optimizar unha análise de diferenciadores

Despois de completar a análise, busque detalles sobre esta información en **Segmentos** > **Información (vista previa)**.

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-differentiators.png" alt-text="Detalles da información de diferenciadores do segmento.":::

Seleccione unha información para ver os resultados da análise. Unha análise diferenciadora inclúe dúas lapelas. A lapela **Atributos** enumera os atributos de perfil considerados como diferenciadores. A lapela **Medidas** enumera os diferenciadores. Cada lapela inclúe os seguintes detalles:

- Lista clasificada de diferenciadores, ordenada por puntuación de diferenza.
- A **Puntuación de diferenza** para cada diferenciador. A puntuación de diferenza representa o grao de diferenza dun atributo entre dous segmentos. Canto maior sexa a puntuación de diferenza, máis os atributos difiren entre os dous segmentos. Seleccione unha puntuación para abrir o panel **Puntuación de diferenza** coas distribucións de valores para ese atributo.

## <a name="manage-segment-insights"></a>Xestionar a información do segmento

Pode empregar as seguintes opcións nos seus datos desde a barra de comandos:

- **Volver** para volver á lista de informacións
- **Actualizar** para volver executar a análise
- **Eliminar** para eliminar esta información


[!INCLUDE [footer-include](includes/footer-banner.md)]
