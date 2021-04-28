---
title: Xestionar permisos de usuario
description: Máis información acerca de permisos e roles de usuario.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 8638489dba908d4504278916d2c28454e3ea9e18
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760371"
---
# <a name="user-permissions"></a>Permisos de usuario

A páxina **Permisos** é onde configurará funcións e permisos para usar información sobre o público.

Debe ter permisos de administrador para ver a páxina. Para acceder á páxina de permisos nas estatísticas do público, vaia a **Administrar** > **Permisos**.

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

## <a name="administrator"></a>Administrador

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

## <a name="assign-roles-and-permissions"></a>Atribuír roles e permisos

1. Na información do público, vaia a **Administrar** > **Permisos**.

1. Seleccione **Engadir usuarios** para abrir o panel **Engadir/editar permisos**.

1. Use o campo **Buscar** para atopar o usuario ou o grupo de Azure Active Directory cuxos permisos desexa axustar. Seleccione un **Papel** para asignar a ese usuario ou grupo.

1. Seleccione **Gardar**. O contorno actual compartirase automaticamente co usuario ou os membros do grupo cuxos permisos cambiou. Os usuarios poden acceder á aplicación Customer Insights e traballar de acordo co seu papel especificado.

## <a name="view-current-permissions"></a>Ver permisos actuais

Na información do público, vaia a **Administrar** > **Permisos** para ver que asignacións de roles están activas actualmente.

- A columna **Tipo** especifica un único usuario, grupo ou aplicación. O sistema admite usuarios e grupos individuais.
- Os roles especifícanse na columna **Papel**.
- Seleccione calquera título de columna para ordenar os resultados segundo o valor desa columna.
- Use o campo **Buscar** na parte superior da páxina para localizar usuarios específicos.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
