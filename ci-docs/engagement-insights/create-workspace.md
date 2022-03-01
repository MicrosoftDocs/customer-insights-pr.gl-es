---
title: Crear unha nova área de traballo
description: O propósito dun espazo de traballo e como crear un novo.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 816f948331a06794c15000eb779f93cc7fdda202
ms.sourcegitcommit: 53b133a716c73cb71e8bcbedc6273cec70ceba6c
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 10/15/2021
ms.locfileid: "7645308"
---
# <a name="create-a-new-workspace-and-add-members"></a>Crear un novo espazo de traballo e engadir membros

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Unha área de traballo é unha forma de ver a actividade dos usuarios en tempo real para que comprenda mellor o seu público. É onde almacena e xestiona eventos e informes.

Ao crear unha área de traballo, selecciona o tipo de datos nos que se quere centrar. Pode engadir outros usuarios ou membros a unha área de traballo existente en calquera momento. 

## <a name="create-a-new-workspace"></a>Crear unha nova área de traballo

O proceso de creación dunha área de traballo inclúe a configuración do *ambiente* para organizala. Un ambiente é un espazo que pode conter unha ou varias áreas de traballo. Pode usar un ambiente para xestionar as súas áreas de traballo e conexións coa capacidade de información do público de Customer Insights.

1. Seleccione **Novo** desde o conmutador de áreas de traballo.

   :::image type="content" source="media/new-workspace.png" alt-text="Páxina de información do cliente con chamada no panel de navegación e descrición.":::

1. No panel **Espazo de traballo**, introduza un **Nome do espazo de traballo**.

   :::image type="content" source="media/workspace-name.png" alt-text="Escriba un nome da área de traballo.":::

1. Escolla o tipo de plataforma (web ou móbil) que desexe medir.

1. Seleccione **Mostrar configuración avanzada** para activar ou desactivar estas configuracións opcionais:

   - Axuste **Descoñecido a coñecidos** en "habilitado" para asociar eventos web con usuarios que se autenticaron previamente. Para obter máis información, consulte [Recoñecer eventos web de visitantes previamente autenticados](unknown-to-known.md)
   - Axuste **Filtrar o tráfico de bots** en "activado" para eliminar o tráfico web por bots para este espazo de traballo. 

1. Seleccione **Completar** cando remate. 

1. Instale o fragmento de código para comezar a recibir datos e logo seleccione **Rematar** para crear o espazo de traballo. Para obter máis información, consulte [Visión xeral dos recursos para programadores](developer-resources.md).

> [!NOTE]
> Agora pode engadir membros e asignar o seu nivel de permiso desde a lista **Función**. Para obter máis información, consulte [Roles e permisos](user-roles.md). 

Para obter máis información, consulte [Xestionar ambientes e áreas de traballo](manage-environments-workspaces.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
