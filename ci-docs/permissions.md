---
title: Atribuír permisos de usuario
description: Máis información acerca de permisos e roles de usuario.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
searchScope:
- ci-permissions
- ci-system-security
- customerInsights
ms.openlocfilehash: a59a672b6f7e1e67c2162ea14bb9860df0d551aa
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245417"
---
# <a name="assign-user-permissions"></a>Atribuír permisos de usuario

O acceso a Customer Insights está restrinxido aos usuarios da túa organización que un administrador engade á aplicación. Un administrador pode engadir, editar ou eliminar usuarios. Un usuario pode ser un único usuario, grupo ou aplicación. Hai tres tipos de roles que pode ter un usuario:

## <a name="viewer"></a>Espectador

- Explore información e segmentos dentro das páxinas **Inicio** e **Segmentos**.
- Busque e filtre os perfís de clientes mediante a páxina **Clientes**. Os campos deben poder buscarse.
- Visualice e explore a páxina **Enriquecemento**.
- Explore e exporte as entidades usando a páxina **Entidades**.
- Visualice o estado dos procesos do sistema mediante a páxina **Sistema**.
- Ver exportacións na páxina **Exportacións**.
- Instale e use o panel de **Power BI Customer Insights**.

## <a name="contributor"></a>Colaborador

- Todos os permisos dispoñibles para o espectador.
- Cargue e transforme datos usando a páxina **Orixes de datos**.
- Completa **Unificación de datos** que dan como resultado a entidade de perfil de cliente unificada.
- Defina **Relacións** e **Actividades**.
- Cree segmentos usando a páxina **Segmentos**.
- Crear medidas empregando a páxina **Medidas**.
- Xestione a configuración e enriqueza os perfís de clientes desde a páxina **Enriquecemento** (só para enriquecementos de primeiras partes).
- Xestionar e crear exportacións en base a [conexións compartidas cos colaboradores](connections.md#allow-contributors-to-use-a-connection-for-exports).

## <a name="admin"></a>Administración

- Todos os permisos dispoñibles para o colaborador.
- Cambiar a configuración en **Sistema** páxina, incluíndo o idioma de traballo, os programas de actualización dos procesos do seu sistema e a exportación de rexistros de diagnóstico.
- Cambiar a configuración en **Seguridade** páxina, incluíndo usuarios, claves API, ligazóns privadas e bóveda de claves.
- Estableza as definicións de busca e filtro para a páxina de clientes mediante a páxina **Índice de busca e filtro** (accesible a través da páxina **Clientes**).
- Xestione as conexións e permítaas para outras funcións de usuario na páxina **Conexións**.
- Xestione a configuración e enriqueza os perfís de clientes desde a páxina **Enriquecemento** (para todos os enriquecementos).
- Xestione e cree exportacións na páxina **Exportacións**.
- Instale e use o **complemento do cartón do cliente**.
- Engada e use o **conector de Power Apps**.
- Active o uso das [API de Customer Insights](apis.md).
- [Asignar a propiedade do medio](manage-environments.md#change-the-owner-of-an-environment) a outro administrador.

## <a name="admin-owner"></a>Administrador (propietario)

- Todos os permisos dispoñibles para o administrador.
- [Restablecer e eliminar](manage-environments.md#reset-an-existing-environment-preview) o medioambiente.

## <a name="add-users"></a>Engadir usuarios

1. Ir a **Admin** > **Seguridade** e selecciona o **Usuarios** ficha.

1. Seleccione **Engadir usuarios** para abrir o panel **Engadir/editar permisos**.

1. Usa o **Busca** campo para atopar o Azure Active Directory usuario ou grupo que quere engadir. Seleccione un **Papel** para asignar a ese usuario ou grupo.

1. Seleccione **Gardar**. O entorno actual compártese automaticamente co usuario ou os membros do grupo. Os usuarios poden acceder á aplicación Customer Insights e traballar de acordo co seu papel especificado.

## <a name="view-current-permissions"></a>Ver permisos actuais

Ir a **Admin** > **Seguridade** e selecciona o **Usuarios** para ver a lista de usuarios activos e as súas funcións asignadas. Pode ordenar a lista de usuarios por calquera columna ou utilizar a caixa de busca para atopar un usuario concreto.

## <a name="manage-current-users"></a>Xestionar usuarios actuais

Ir a **Admin** > **Seguridade** e selecciona o **Usuarios** ficha. Podes ordenar a lista de usuarios por calquera columna ou usar a caixa de busca para atopar o usuario que queres xestionar.

Seleccione un usuario para ver as accións dispoñibles.

- **Editar** para editar a función do usuario en Customer Insights. Seleccione **Gardar** para confirmar o cambio.
- **Quitar** para eliminar que o usuario teña acceso a Customer Insights. Para confirmar a eliminación, seleccione **Eliminar**.

[!INCLUDE [footer-include](includes/footer-banner.md)]
