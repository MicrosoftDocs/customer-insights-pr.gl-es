---
title: Crear un novo ambiente
description: O propósito dun contorno e como crear un novo.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 10/04/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 5e301b4ff0a7586fb143b154b773791b3bd645b7
ms.sourcegitcommit: 37182127b93b90846cc91fbeb26dd7a18cf5610a
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 10/18/2021
ms.locfileid: "7648115"
---
# <a name="create-a-new-environment"></a>Crear un novo ambiente 

## <a name="overview"></a>Visión xeral

Un ambiente é un espazo onde xestiona as súas áreas de traballo e conexións. A forma de usar os ambientes depende da súa organización e do seu caso de uso. Por exemplo, pode crear:

- Un único ambiente.
- Ambientes separados para probas e produción.
- Ambientes separados para equipos ou departamentos específicos da súa organización que conteñan eventos relevantes para cada público.
- Ambientes separados para diferentes ramificacións globais da súa empresa.
- Conexións coa capacidade de información do público de Customer Insights.

## <a name="create-a-new-environment"></a>Crear un novo ambiente

1. Na parte dereita da faixa principal, seleccione o selector de contornos e logo **+ Novo**.

   :::image type="content" source="media/environment-picker.png" alt-text="Seleccione o selector de ambientes.":::

1. No panel **Configurar**, escriba un **Nome de contorno**.

1. Escolla o **Tipo** de conta, dependendo do tipo de plan.

1. Escolla a **Rexión** e seleccione **Seguinte**. 

1. Escriba un **Nome do espazo de traballo**, que lle permite recompilar datos para sitios web específicos ou aplicacións. Para obter máis información, consulte [Crear un espazo de traballo](create-workspace.md).

1. Escolla o **tipo de espazo de traballo** (web ou móbil) que desexe crear. 

1. Seleccione **Mostrar configuración avanzada** para activar ou desactivar estas configuracións opcionais:

   - Axuste **Descoñecido a coñecidos** en "habilitado" para asociar eventos web con usuarios que se autenticaron previamente. Para obter máis información, consulte [Recoñecer eventos web de visitantes previamente autenticados](unknown-to-known.md)
   - Axuste **Filtrar o tráfico de bots** en "activado" para eliminar o tráfico web por bots para este espazo de traballo. 

1. Seleccione **Completar** cando remate. 

1. Instale o fragmento de código para comezar a recibir datos e logo seleccione **Rematar** para crear o espazo de traballo. Para obter máis información, consulte [Visión xeral dos recursos para programadores](developer-resources.md).

> [!NOTE]
> Agora pode engadir membros e asignar o seu nivel de permiso desde a lista **Función**. Para obter máis información, consulte [Roles e permisos](user-roles.md). 

Para obter máis información, consulte [Xestionar ambientes e áreas de traballo](manage-environments-workspaces.md).

## <a name="work-with-your-new-environment"></a>Traballar co seu novo ambiente

- [Cree unha área de traballo](../engagement-insights/create-workspace.md) e engada membros.
- [Engadir código ao seu sitio web](../engagement-insights/instrument-website.md) ou [aplicación móbil](../engagement-insights/developer-resources.md#capture-events-from-mobile-apps).
- Consulte un [informe en tempo real](../engagement-insights/view-reports.md) ou cree [informes personalizados](../engagement-insights/custom-reports.md).
- [Cree eventos refinados](../engagement-insights/refined-events.md) para exportar.
- [Exporte os datos](../engagement-insights/export-events.md) a Data Lake Storage.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
