---
title: Roles e permisos
description: Visión xeral dos roles e permisos dispoñibles para os membros dunha área de traballo.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 68e28caf1c14c23acd506da5f7b441f1e3b72e8b
ms.sourcegitcommit: 53b133a716c73cb71e8bcbedc6273cec70ceba6c
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 10/15/2021
ms.locfileid: "7645535"
---
# <a name="roles-and-permissions"></a>Roles e permisos

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Unha área de traballo é onde almacena e xestiona eventos e informes. Para obter máis información, consulte [Crear un espazo de traballo e engadir membros](create-workspace.md). 

Un espazo de traballo pode incluír os seguintes roles e permisos:

- Os roles de *membro* son usuarios que poden acceder a un espazo de traballo. Pode atribuír membros á súa área de traballo e definir os seus roles e permisos. 
- As funcións de *administrador* xestionan as áreas de traballo e ambientes e configuran a información de interacción para outros usuarios. 
- As funcións de *Colaborador* están dirixidos a analistas que non precisan configurar información de compromiso, pero que queren crear os seus propios informes, funís ou segmentos.

## <a name="permissions"></a>Permisos
  
A seguinte táboa identifica permisos para cada rol. 

| Permiso | Administrador do ambiente | Administrador da área de traballo | Colaborador do ambiente | Colaborador da área de traballo | 
|--|--|--|--|--|
| Crear ambientes (o creador convértese automaticamente en administrador do ambiente) | X* | X* | X* | X* |  
| Configurar o ambiente (membros do ambiente, eliminar o ambiente) | X |  |  |  |  
| Crear áreas de traballo | X |  |  |  |  
| Configurar áreas de traballo (membros da área de traballo, eliminar área de traballo) | X | X |  |  |  
| Configurar eventos e eventos refinados | X | X | |  |  
| Ver eventos e eventos refinados da área de traballo | X | X | |  |  
| Ver recursos da área de traballo (informes, segmentos e métricas)| X | X | X | X |  
| Crear funís e informes personalizados | X | X | X | X |  
| Crear dimensións e métricas básicas| X | X |  |  |  
| Crear segmentos| X | X | X | X |  

*Só pode crear ambientes de proba na versión preliminar. 

## <a name="add-members"></a>Engadir membros

Pode engadir e eliminar membros de áreas de traballo e ambientes. Para obter máis información, consulte [Ambientes e áreas de traballo](manage-environments-workspaces.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
