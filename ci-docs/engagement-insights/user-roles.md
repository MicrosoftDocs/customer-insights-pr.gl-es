---
title: Roles e permisos
description: Visión xeral dos roles e permisos dispoñibles para os membros dunha área de traballo.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 07/06/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 6d7f4db4a130fc15a69b380c892538db5492d96d8e13f3c070c6a6b9bd098371
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036691"
---
# <a name="roles-and-permissions"></a>Roles e permisos

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Unha área de traballo é unha forma de almacenar e xestionar eventos e informes. Un membro é un usuario que pode acceder a unha área de traballo. Pode atribuír membros á súa área de traballo e definir os seus roles e permisos. As funcións de administrador xestionan as áreas de traballo e ambientes e configuran a información de interacción para outros usuarios. As funcións de colaboradores están dirixidas a analistas que non precisan configurar a información de interacción, pero que queren crear os seus propios informes, funís ou segmentos.

## <a name="permissions"></a>Permisos
  
A seguinte táboa identifica os permisos para cada rol. 

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
