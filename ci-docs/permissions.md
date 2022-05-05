---
title: Xestionar permisos de usuario
description: Máis información acerca de permisos e roles de usuario.
ms.date: 02/09/2022
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
ms.openlocfilehash: b80f07dfa734f4dd762bd711151a7045f24bed7d
ms.sourcegitcommit: cf74b8c20d88eb96e1ac86e18cd44fe27aad5ab9
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 04/28/2022
ms.locfileid: "8653566"
---
# <a name="user-permissions"></a>Permisos de usuario

O **Permisos** páxina é onde configurarás roles e permisos para usar Customer Insights.

Debe ter permisos de administrador para ver a páxina. Para acceder á páxina de permisos, vai a **Admin** > **Seguridade** > **Usuarios**.

Existen tres tipos de roles:

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
- Complete as seccións *Unificación de datos* (**Asignación**, **Coincidencia** e **Combinación**) que permiten obter unha entidade de perfil de cliente unificada.
- Defina **Relacións** e **Actividades**.
- Cree segmentos usando a páxina **Segmentos**.
- Crear medidas empregando a páxina **Medidas**.
- Xestione a configuración e enriqueza os perfís de clientes desde a páxina **Enriquecemento** (só para enriquecementos de primeiras partes).
- Xestione e cree exportacións baseadas en conexións compartidas cos colaboradores. [Máis información sobre como os administradores permiten aos colaboradores usar unha conexión para exportacións](connections.md#allow-contributors-to-use-a-connection-for-exports).

## <a name="admin"></a>Administración

- Todos os permisos dispoñibles para o colaborador.
- Cambie a configuración na páxina **Sistema**, incluído o idioma de traballo e as programacións de actualización dos procesos do sistema.
- Visualice e engada permisos usando a páxina **Permisos**.
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
- [Restablecer e eliminar](manage-environments.md#reset-an-existing-environment) o medioambiente.

## <a name="assign-roles-and-permissions"></a>Atribuír roles e permisos

1. Ir a **Admin** > **Seguridade** > **Usuarios***.

1. Seleccione **Engadir usuarios** para abrir o panel **Engadir/editar permisos**.

1. Use o campo **Buscar** para atopar o usuario ou o grupo de Azure Active Directory cuxos permisos desexa axustar. Seleccione un **Papel** para asignar a ese usuario ou grupo.

1. Seleccione **Gardar**. O contorno actual compartirase automaticamente co usuario ou os membros do grupo cuxos permisos cambiou. Os usuarios poden acceder á aplicación Customer Insights e traballar de acordo co seu papel especificado.

## <a name="view-current-permissions"></a>Ver permisos actuais

Ir a **Admin** > **Seguridade** > **Usuarios** para ver que funcións están activas actualmente.

- A columna **Tipo** especifica un único usuario, grupo ou aplicación. O sistema admite usuarios e grupos individuais.
- Os roles especifícanse na columna **Papel**.
- Seleccione calquera título de columna para ordenar os resultados segundo o valor desa columna.
- Use o campo **Buscar** na parte superior da páxina para localizar usuarios específicos.


[!INCLUDE [footer-include](includes/footer-banner.md)]
