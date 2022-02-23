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
ms.openlocfilehash: 1f8922703af506974c8b5b24086b61f05a83609d
ms.sourcegitcommit: 31985755c7c973fb1eb540c52fd1451731d2bed2
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 10/22/2021
ms.locfileid: "7673441"
---
# <a name="create-a-new-workspace-and-add-members"></a>Crear un novo espazo de traballo e engadir membros

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Unha área de traballo é unha forma de ver a actividade dos usuarios en tempo real para que comprenda mellor o seu público. É onde almacena e xestiona eventos e informes.

Ao crear unha área de traballo, selecciona o tipo de datos nos que se quere centrar. Pode engadir outros usuarios ou membros a unha área de traballo existente en calquera momento. 

## <a name="create-a-new-workspace"></a>Crear unha nova área de traballo

O proceso de creación dunha área de traballo inclúe a configuración do *ambiente* para organizala. Un ambiente é un espazo que pode conter unha ou varias áreas de traballo. Podes usar un ambiente para xestionar os teus espazos de traballo e as conexións coa capacidade de información sobre a audiencia.

1. Seleccione **+Novo** desde o selector de espazo de traballo.

   :::image type="content" source="media/new-workspace.png" alt-text="Páxina de Customer Insights con chamada no panel de navegación e descrición.":::

1. No panel **Espazo de traballo**, introduza un **Nome do espazo de traballo**.

   :::image type="content" source="media/workspace-name.png" alt-text="Escriba un nome da área de traballo.":::

1. Escolle o tipo de plataforma (web ou móbil) que queres medir.

1. Seleccione **Mostrar configuración avanzada** para activar ou desactivar estas configuracións opcionais:

   - Axuste **Descoñecido a coñecidos** en "habilitado" para asociar eventos web con usuarios que se autenticaron previamente. Para obter máis información, consulte [Recoñecer eventos web de visitantes previamente autenticados](unknown-to-known.md)
   - Axuste **Filtrar o tráfico de bots** en "activado" para eliminar o tráfico web por bots para este espazo de traballo. 

1. Seleccione **Completar** cando remate. 

1. Instale o fragmento de código para comezar a recibir datos e logo seleccione **Rematar** para crear o espazo de traballo. Para obter máis información, consulte [Visión xeral dos recursos para programadores](developer-resources.md).

> [!NOTE]
> Agora pode engadir membros e asignar o seu nivel de permiso desde a lista **Función**. Para obter máis información, consulte [Roles e permisos](user-roles.md). 

Para obter máis información, consulte [Xestionar ambientes e áreas de traballo](manage-environments-workspaces.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
