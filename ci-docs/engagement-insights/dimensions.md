---
title: Ver e crear dimensións
description: Como crear, editar e eliminar dimensións.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 06/09/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: b575c5e84197d76f53a722bac60c5af928c917f9671720ede1de38c4a7478be4
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033995"
---
# <a name="view-and-create-dimensions"></a>Ver e crear dimensións

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Unha dimensión é un atributo dun evento que pode describir, filtrar ou agrupar datos. Se está a realizar unha promoción de márketing no seu sitio web, pode usar dimensións para ordenar os visitantes por usuarios novos e recorrentes.  

A información de interacción inclúe dimensións listas para usar para as propiedades dos eventos. Os exemplos inclúen:

- Nome do explorador
- Nome de Páxina
- Modelo do dispositivo
- Sistema operativo
- País

## <a name="view-dimensions"></a>Ver dimensións

As dimensións baséanse nas propiedades dos eventos existentes. Cando usa o código de rastrexo para a información de interacción, as dimensións do sistema créanse automaticamente.

1. Vaia a **Datos** no panel de navegación esquerdo. 
1. Seleccione **Dimensións** para ver unha lista de todas as dimensións na área de traballo. 
   > [!NOTE]
   > As dimensións xeradas polo sistema son só de lectura. Non pode editalas. Só pode crear e editar dimensións personalizadas.

## <a name="create-a-dimension"></a>Crear unha dimensión

Ademais das dimensións xeradas polo sistema, os administradores de ambientes e áreas de traballo poden crear dimensións personalizadas. As dimensións personalizadas baséanse nas propiedades predefinidas dos eventos base ou poden usar as [propiedades personalizadas dun evento](advanced-SDK-implementation.md).

1. Vaia a **Datos** > **Dimensións**.
1. Seleccione **Engadir unha dimensión**.

   :::image type="content" source="media/add-dimension.png" alt-text="Engadir unha dimensión a un evento.":::

1. No panel **Crear unha dimensión**, seleccione unha propiedade para que a dimensión se basee nela. A lista de propiedades amosará todas as propiedades da área de traballo non atribuídas a unha dimensión.
1. Introduza un nome na caixa **Nome para mostrar**. Opcionalmente, pode engadir unha descrición.
1. Seleccione **Crear** para gardar a dimensión. Pode pasar até un minuto antes de que poida usar a dimensión nun [informe personalizado](custom-reports.md) ou [segmento](segments.md). 

## <a name="edit-a-dimension"></a>Editar unha dimensión

Pode modificar o nome e a descrición dunha dimensión.

1. Vaia a **Datos** > **Dimensións**.
1. Seleccione a dimensión que quere eliminar.
1. No panel **Editar dimensión**, actualice a dimensión.
1. Seleccione **Aplicar** para gardar as modificacións.

## <a name="delete-a-dimension"></a>Eliminar unha dimensión

Só pode eliminar as dimensións creadas polo usuario, pero non pode eliminar as dimensións do sistema.

A eliminación dunha dimensión é permanente. Os informes e segmentos que usen unha dimensión eliminada deixarán de funcionar. 

1. Vaia a **Datos** > **Dimensións**.
1. Seleccione a dimensión que quere eliminar.
1. No panel **Editar dimensión**, seleccione **Eliminar dimensión**.

   :::image type="content" source="media/delete-dimension.png" alt-text="Eliminar unha dimensión dun evento.":::

1. Introduza **CONFIRMAR ELIMINACIÓN** (en maiúsculas) para confirmar a eliminación. 
1. Seleccione **Eliminar**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
