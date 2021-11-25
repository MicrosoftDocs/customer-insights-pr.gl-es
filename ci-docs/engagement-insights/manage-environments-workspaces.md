---
title: Xestionar áreas de traballo e ambientes
description: Como crear, renomear e eliminar áreas de traballo e ambientes.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 09cb3ddf0f8b4507b7eae6668ea3dad08cfcea29
ms.sourcegitcommit: 31985755c7c973fb1eb540c52fd1451731d2bed2
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 10/22/2021
ms.locfileid: "7673788"
---
# <a name="manage-environments-and-workspaces"></a>Xestionar ambientes e espazos de traballo

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

## <a name="overview"></a>Visión xeral

Este tema trata sobre como xestionar espazos de traballo e contornos unha vez creados. 

- Unha *área de traballo* é un espazo para almacenar e xestionar eventos e informes. É o lugar no que pode ver a actividade dos usuarios en tempo real. Cando crea unha área de traballo, selecciona o tipo de datos que se enviarán a esta. Actualmente, admítense datos web e aplicacións móbiles. Para obter máis información, consulte [Crea un novo espazo de traballo e engade membros](create-workspace.md).

- Un *ambiente* é un espazo onde xestiona as súas áreas de traballo e conexións. Para obter máis información, consulte [Crear un novo contorno](create-new-environment.md).

## <a name="manage-an-existing-workspace"></a>Xestionar unha área de traballo existente

Pode manter varias áreas de traballo simultaneamente nun ambiente. O seu [rol](user-roles.md) determina como pode traballar nelas. 

 - Para xestionar a área de traballo debe ser administrador de ambientes ou administrador de áreas de traballo.
 - Como administrador de áreas de traballo, pode renomear ou eliminar as áreas existentes. 

:::image type="content" source="media/workspace-edit.png" alt-text="Centro de administrador da área de traballo.":::

### <a name="edit-a-workspace-name"></a>Editar o nome dunha área de traballo

1. Vaia a **Administración** > **Área de traballo** e seleccione **Configuración**.

1. Na caixa do **nome da área de traballo**, introduza un novo nome.

1. Seleccione **Gardar** para aplicar as modificacións.

### <a name="delete-a-workspace"></a>Eliminar unha área de traballo

Ao eliminar un espazo de traballo elimina permanentemente todo o seu contido, datos, configuración e permisos. Isto non se pode desfacer.

1. Vaia a **Administración** > **Área de traballo** e seleccione **Configuración**.

1. Seleccione **Eliminar área de traballo**. 

1. No diálogo **Eliminar espazo de traballo**, introduza **CONFIRMAR BORRADO** todo en maiúsculas. 

1. Seleccione **Eliminar** para eliminar a área de traballo permanentemente.

### <a name="manage-workspace-members"></a>Xestionar os membros dunha área de traballo

1. Vaia a **Administración** > **Área de traballo** e seleccione **Membros**.

1. Seleccione **Engadir membros** para dar acceso e [atribuír roles](user-roles.md). Actualmente só está dispoñible o rol de **Administrador de áreas de traballo**.

1. Seleccione **Engadir membros** para engadilos á súa área de traballo.

## <a name="manage-an-existing-environment"></a>Xestionar un ambiente existente

Como Administrador de contornos, pode acceder a un ambiente desde o panel de navegación esquerdo. Pode configurar axustes de contorno, outros administradores de contorno e espazos de traballo. Seleccione os separadores para moverse entre as distintas áreas do centro de administración.

:::image type="content" source="media/environment-edit.png" alt-text="Centro de administración do ambiente.":::

### <a name="edit-an-environment-name"></a>Edita o nome dun entorno

1. Vaia a **Administración** > **Ambiente** e seleccione **Configuración**.

1. Actualice o campo do **nome do ambiente** e seleccione **Gardar** para aplicar as modificacións.

### <a name="delete-an-environment"></a>Eliminar un ambiente

Os administradores de ambientes poden eliminar ambientes. Antes de poder eliminar un ambiente, debe eliminar todas as áreas de traballo que se atopan nel.

1. Vaia a **Administración** > **Ambiente** e seleccione **Configuración**.

1. Seleccione **Eliminar ambiente**. 

1. No diálogo **Eliminar espazo de traballo**, introduza **CONFIRMAR BORRADO** todo en maiúsculas. 

1. Seleccione **Eliminar** para eliminar o ambiente permanentemente.

### <a name="manage-environment-members"></a>Xestionar os membros dun ambiente

1. Vaia a **Administración** > **Ambiente** e seleccione **Membros**.

1. Seleccione **Engadir membros** para actualizar os membros e [atribuír roles](user-roles.md). Actualmente só está dispoñible o rol de **Administrador de ambientes**.

1. Seleccione **Engadir membros** para engadilos ao seu ambiente.

## <a name="manage-connections"></a>Xestionar conexións

Establecer conexións coa información do público permítelle ver informes na información de interacción baseados en perfís de clientes unificados. 

Para obter máis información, consulte [Crear unha ligazón entre a información do público e a información de interacción](integrate-audience-insights-engagement-insights.md).

## <a name="manage-personal-data"></a>Xestionar os datos persoais

Para protexer os datos persoais dos seus clientes, pode eliminar ou exportar os datos de identificación do usuario final.

Para obter máis información, consulte [Eliminar e exportar datos de eventos que conteñan información persoal](../dsr-rights-requests.md#deleting-and-exporting-event-data-containing-end-user-identifiable-information).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
