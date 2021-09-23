---
title: Xestionar áreas de traballo e ambientes
description: Como crear, renomear e eliminar áreas de traballo e ambientes.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 09/09/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: a5b48db5ae23ea65bf608d67348d493bfdc7678f
ms.sourcegitcommit: 0ceb46c4f57ab49d3a2ebb1c8a816bbafe979e3d
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 09/09/2021
ms.locfileid: "7486033"
---
# <a name="manage-environments-and-workspaces"></a>Xestionar ambientes e espazos de traballo

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

## <a name="overview"></a>Visión xeral

Unha área de traballo é un espazo para almacenar e xestionar eventos e informes. É o lugar no que pode ver a actividade dos usuarios en tempo real. Cando crea unha área de traballo, selecciona o tipo de datos que se enviarán a esta. Actualmente, admítense datos web e aplicacións móbiles.

Un ambiente é un espazo onde xestiona as súas áreas de traballo e conexións. A forma de usar os ambientes depende da súa organización e do seu caso de uso. Por exemplo, pode crear:

-   Un único ambiente.
-   Ambientes separados para probas e produción.
-   Ambientes separados para equipos ou departamentos específicos da súa organización que conteñan eventos relevantes para cada público.
-   Ambientes separados para diferentes ramificacións globais da súa empresa.
-   Conexións coa capacidade de información do público de Customer Insights.

## <a name="choose-an-environment-and-create-a-workspace"></a>Elixir un ambiente e crear unha área de traballo 

Todas as áreas de traballo teñen que estar nun ambiente. Pode seleccionar un ambiente preexistente ou crear un novo cando cree unha área de traballo. Pode optar por engadir membros da área de traballo e comezar a recompilar datos.

**Para crear a súa primeira área de traballo:**

1. Na información de interacción, seleccione **Novo** no conmutador de áreas de traballo. 

   :::image type="content" source="media/New-workspace.png" alt-text="Selector de áreas de traballo da páxina de Customer Insights.":::

1. Escolla un ambiente da lista ou seleccione **Crear novo ambiente**.

1. Introduza un nome no campo **Nome da área de traballo**. 

1. Seleccione o tipo de ambiente que desexa crear, dependendo se desexa medir o que acontece nun sitio web ou nunha aplicación móbil. 

1. Pode engadir membros e atribuír o seu nivel de permiso desde a lista de **roles**. Despois seleccione **Finalizar** para crear a área de traballo ou **Seguinte** para instalar o código. 

1. Instale o fragmento de código para comezar a recibir datos e seleccione **Feito**. 

## <a name="manage-a-workspace"></a>Xestionar unha área de traballo

Pode manter varias áreas de traballo simultaneamente nun ambiente. O seu [rol](user-roles.md) determina como pode traballar nelas. 

 - Para xestionar a área de traballo debe ser administrador de ambientes ou administrador de áreas de traballo.
 - Como administrador de áreas de traballo, pode renomear ou eliminar as áreas existentes. 

### <a name="edit-a-workspace-name"></a>Editar o nome dunha área de traballo

1. Vaia a **Administración** > **Área de traballo** e seleccione **Configuración**.

1. Na caixa do **nome da área de traballo**, introduza un novo nome.

1. Seleccione **Gardar** para aplicar as modificacións.

### <a name="delete-a-workspace"></a>Eliminar unha área de traballo

Ao eliminar unha área de traballo, eliminarase permanentemente todo o seu contido, os datos, a configuración e os permisos. Isto non se pode desfacer.

1. Vaia a **Administración** > **Área de traballo** e seleccione **Configuración**.

1. Seleccione **Eliminar área de traballo**. 

1. No diálogo **Eliminar área de traballo**, introduza **CONFIRMAR ELIMINACIÓN**. 

1. Seleccione **Eliminar** para eliminar a área de traballo permanentemente.

### <a name="manage-workspace-members"></a>Xestionar os membros dunha área de traballo

1. Vaia a **Administración** > **Área de traballo** e seleccione **Membros**.

1. Seleccione **Engadir membros** para dar acceso e [atribuír roles](user-roles.md). Actualmente só está dispoñible o rol de **Administrador de áreas de traballo**.

1. Seleccione **Engadir membros** para engadilos á súa área de traballo.

## <a name="manage-an-environment"></a>Xestionar un ambiente

Como Administrador de ambientes, pode acceder a un ambiente desde o panel de navegación esquerdo. Pode configurar axustes de contorno, outros administradores de contorno e espazos de traballo. Seleccione os separadores para moverse entre as distintas áreas do centro de administración.

:::image type="content" source="media/New-environment.png" alt-text="Centro de administración do ambiente.":::

### <a name="create-an-environment"></a>Crear un ambiente

1. No selector de áreas de traballo, seleccione **+Novo**.

1. Na experiencia guiada, abra o menú despregable **Ambiente** e seleccione **Crear novo ambiente**. 

1. Proporcione un **Nome do ambiente**.

   :::image type="content" source="media/create-environment.png" alt-text="Paso na experiencia guiada para especificar os detalles do ambiente.":::

1. Escolla a **Rexión** e seleccione **Seguinte**. 

1. Proporcione un nome de área de traballo e escolla que tipo de área de traballo desexa crear. 

1.  Opcionalmente, o proceso de creación complétase engadindo membros e copiando o fragmento de código.

### <a name="rename-an-environment"></a>Renomear un ambiente

1. Vaia a **Administración** > **Ambiente** e seleccione **Configuración**.

1. Actualice o campo do **nome do ambiente** e seleccione **Gardar** para aplicar as modificacións.

### <a name="manage-environment-members"></a>Xestionar os membros dun ambiente

1. Vaia a **Administración** > **Ambiente** e seleccione **Membros**.

1. Seleccione **Engadir membros** para actualizar os membros e [atribuír roles](user-roles.md). Actualmente só está dispoñible o rol de **Administrador de ambientes**.

1. Seleccione **Engadir membros** para engadilos ao seu ambiente.

### <a name="delete-an-environment"></a>Eliminar un ambiente

Os administradores de ambientes poden eliminar ambientes. Antes de poder eliminar un ambiente, debe eliminar todas as áreas de traballo que se atopan nel.

1. Vaia a **Administración** > **Ambiente** e seleccione **Configuración**.

1. Seleccione **Eliminar ambiente**. 

1. No diálogo **Eliminar área de traballo**, introduza **CONFIRMAR ELIMINACIÓN**. 

1. Seleccione **Eliminar** para eliminar o ambiente permanentemente.

## <a name="manage-connections"></a>Xestionar conexións

Establecer conexións coa información do público permítelle ver informes na información de interacción baseados en perfís de clientes unificados. 

Para obter máis información, consulte [Crear unha ligazón entre a información do público e a información de interacción](integrate-audience-insights-engagement-insights.md).

## <a name="manage-personal-data"></a>Xestionar os datos persoais

Para protexer os datos persoais dos seus clientes, pode eliminar ou exportar os datos de identificación do usuario final.

Para obter máis información, consulte [Eliminar e exportar datos de eventos que conteñan información persoal](delete-export-personal-data.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
