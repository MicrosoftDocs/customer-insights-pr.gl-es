---
title: Exportar datos de Customer Insights a Azure Synapse Analytics
description: Obteña información acerca da configuración da conexión a Azure Synapse Analytics.
ms.date: 04/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 822082d661863e737ea3d3a749a6c878db766967
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 05/04/2021
ms.locfileid: "5977375"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a>Exportar datos a Azure Synapse Analytics (versión preliminar)

Azure Synapse é un servizo de análise que acelera o tempo para obter información en almacéns e grandes sistemas de datos. Pode inxerir e usar os seus datos de Customer Insights en [Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Requisitos previos

Os seguintes requisitos previos deben cumprirse para configurar a conexión de Customer Insights a Azure Synapse.

> [!NOTE]
> Asegúrese de configurar todas as **atribucións de roles** segundo se describe.  

## <a name="prerequisites-in-customer-insights"></a>Requisitos previos en Customer Insights

* Ten un rol de **Administrador** na información do público. Obteña máis información acerca da [definición dos permisos do usuarios na información do público](permissions.md#assign-roles-and-permissions)

En Azure: 

- Unha subscrición de Azure activa.

- Se usa unha conta nova de Azure Data Lake Storage Gen2, a *entidade de servizo para a información do público* precisa permisos de **colaborador de datos de BLOB de almacenamento**. Obteña máis información acerca da [conexión a unha conta de Azure Data Lake Storage Gen2 coa entidade de servizo de Azure para a información do público](connect-service-principal.md). Data Lake Storage Gen2 **debe ter o** [espazo de nomes xerárquico](/azure/storage/blobs/data-lake-storage-namespace) activado.

- No grupo de recursos onde se atopa a área de traballo de Azure Synapse, hai que atribuírlle á *entidade de servizo* e ao *usuario da información do público* como mínimo permisos de **Lector**. Para obter máis información, consulte [Atribuír roles de Azure no portal de Azure](/azure/role-based-access-control/role-assignments-portal).

- O *usuario* precisa permisos de **colaborador de datos de BLOB de almacenamento** na conta de Azure Data Lake Storage Gen2 na que se atopan os datos ligados á área de traballo de Azure Synapse. Obteña máis información acerca do [uso do portal de Azure para atribuír un rol de Azure para o acceso aos datos de BLOB e fila](/azure/storage/common/storage-auth-aad-rbac-portal) e dos [permisos do colaborador de datos de BLOB de almacenamento](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- A *[identidade xestionada da área de traballo de Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* precisa permisos de **colaborador de datos de BLOB de almacenamento** na conta de Azure Data Lake Storage Gen2 na que se atopan os datos ligados á área de traballo de Azure Synapse. Obteña máis información acerca do [uso do portal de Azure para atribuír un rol de Azure para o acceso aos datos de BLOB e fila](/azure/storage/common/storage-auth-aad-rbac-portal) e dos [permisos do colaborador de datos de BLOB de almacenamento](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Na área de traballo de Azure Synapse, a *entidade de servizo para a información do público* precisa ter atribuído o rol de **administrador de Synapse**. Para obter máis información, consulte [Como configurar o control de acceso para a súa área de traballo de Synapse](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="set-up-the-connection-and-export-to-azure-synapse"></a>Configurar a conexión e exportar a Azure Synapse

### <a name="configure-a-connection"></a>Configurar unha conexión

1. Vaia a **Administrar** > **Conexións**.

1. Seleccione **Engadir conexión** e elixa **Azure Synapse Analytics** ou seleccione a opción **Configurar** no mosaico **Azure Synapse Analytics** para configurar a conexión.

1. Déalle á conexión un nome recoñecible no campo Nome para mostrar. O nome e o tipo de conexión describen esta conexión. Recomendamos escoller un nome que explique o propósito e o destino da conexión.

1. Escolla quen pode usar esta conexión. Se non realiza ningunha acción, o valor predeterminado será Administradores. Para obter máis información, consulte [Permitir aos colaboradores usar unha conexión para as exportacións](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Seleccione ou busque a subscrición na que quere empregar os datos de Customer Insights. Cando seleccione unha subscrición, tamén pode seleccionar **Área de traballo**, **Conta de almacenamento** e **Contedor**.

1. Seleccione **Gardar** para gardar a conexión.

### <a name="configure-an-export"></a>Configurar unha exportación

Pode configurar esta exportación se ten acceso a unha conexión deste tipo. Para obter máis información, consulte os [permisos necesarios para configurar unha exportación](export-destinations.md#set-up-a-new-export).

1. Vaia a **Datos** > **Exportacións**.

1. Seleccione **Engadir exportación** para crear unha nova exportación.

1. No campo **Conexión da exportación**, escolla unha conexión da sección **Azure Synapse Analytics**. Se non ve o nome desta sección, non hai [conexións](connections.md) deste tipo dispoñibles para vostede.

1. Proporcione un **Nome para mostrar** recoñecible para a exportación e un **Nome da base de datos**.

1. Seleccione as entidades que quere exportar a Azure Synapse Analytics.

1. Seleccione **Gardar**.

Ao gardar unha exportación non se executa a exportación inmediatamente.

A exportación execútase con cada [actualización programada](system.md#schedule-tab). Tamén pode [exportar datos baixo demanda](export-destinations.md#run-exports-on-demand).

### <a name="update-an-export"></a>Actualizar unha exportación

1. Vaia a **Datos** > **Exportacións**.

1. Seleccione **Editar** na exportación que queira editar.

   - **Engadir** ou **Eliminar** entidades da selección. Se se eliminan entidades da selección, non se eliminarán da base de datos de Synapse Analytics. Non obstante, as futuras actualizacións de datos non actualizarán as entidades eliminadas desa base de datos.

   - **Cambiar o nome da base de datos** crea unha nova base de datos de Synapse Analytics. A base de datos co nome configurado anteriormente non se actualizará en futuras actualizacións.
