---
title: Exportar datos de Customer Insights a Azure Synapse Analytics
description: Aprende a configurar a conexión a Azure Synapse Analytics.
ms.date: 04/11/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: e77227e1e353c02cfb13e26a8ecbe0768ba6c0fa
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642553"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a>Exportar datos a Azure Synapse Analytics (Vista previa)

Azure Synapse é un servizo de análise que acelera o tempo para obter información en almacéns e grandes sistemas de datos. Pode inxerir e usar os seus datos de Customer Insights en [Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Requisitos previos

Os seguintes requisitos previos deben cumprirse para configurar a conexión de Customer Insights a Azure Synapse.

> [!NOTE]
> Asegúrese de configurar todas as **atribucións de roles** segundo se describe.  

## <a name="prerequisites-in-customer-insights"></a>Requisitos previos en Customer Insights

* O teu Azure Active Directory (AD) conta de usuario ten un **Administrador** papel en Customer Insights. Máis información sobre [establecer permisos de usuario](permissions.md#assign-roles-and-permissions).

En Azure: 

- Unha subscrición de Azure activa.

- Se utiliza un novo Azure Data Lake Storage Conta Gen2, o *principal de servizo para Customer Insights* necesidades **Colaborador de datos de Blob de almacenamento** permisos. Obteña máis información acerca da [conexión a unha conta de Azure Data Lake Storage Gen2 coa entidade de servizo de Azure para a información do público](connect-service-principal.md). Data Lake Storage Gen2 **debe ter o** [espazo de nomes xerárquico](/azure/storage/blobs/data-lake-storage-namespace) activado.

- No grupo de recursos onde se atopa Azure Synapse o espazo de traballo está situado, o *principal do servizo* e o *Azure AD usuario con permisos de administrador en Customer Insights* deben ser asignados polo menos **Lector** permisos. Para obter máis información, consulte [Atribuír roles de Azure no portal de Azure](/azure/role-based-access-control/role-assignments-portal).

- O *Azure AD usuario con permisos de administrador en Customer Insights* necesidades **Colaborador de datos de Blob de almacenamento** permisos no Azure Data Lake Storage Conta Gen2 onde se atopan os datos e están ligados ao Azure Synapse espazo de traballo. Obteña máis información acerca do [uso do portal de Azure para atribuír un rol de Azure para o acceso aos datos de BLOB e fila](/azure/storage/common/storage-auth-aad-rbac-portal) e dos [permisos do colaborador de datos de BLOB de almacenamento](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- A *[identidade xestionada da área de traballo de Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* precisa permisos de **colaborador de datos de BLOB de almacenamento** na conta de Azure Data Lake Storage Gen2 na que se atopan os datos ligados á área de traballo de Azure Synapse. Obteña máis información acerca do [uso do portal de Azure para atribuír un rol de Azure para o acceso aos datos de BLOB e fila](/azure/storage/common/storage-auth-aad-rbac-portal) e dos [permisos do colaborador de datos de BLOB de almacenamento](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- No Azure Synapse espazo de traballo, o *principal de servizo para Customer Insights* necesidades **Administrador de Synapse** rol asignado. Para obter máis información, consulte [Como configurar o control de acceso para a súa área de traballo de Synapse](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="set-up-the-connection-and-export-to-azure-synapse"></a>Configurar a conexión e exportar a Azure Synapse

### <a name="configure-a-connection"></a>Configurar unha conexión

Para crear unha conexión, necesitan o principal do servizo e a conta de usuario en Customer Insights **Lector** permisos no *grupo de recursos* onde se atopa o espazo de traballo de Synapse Analytics. Ademais, o principal do servizo e o usuario do espazo de traballo Synapse Analytics precisan **Administrador de Synapse** permisos. 

1. Vaia a **Administrar** > **Conexións**.

1. Seleccione **Engadir conexión** e escolle **Azure Synapse Analytics** ou selecciona o **Montar** no **Azure Synapse Analytics** mosaico para configurar a conexión.

1. Déalle á conexión un nome recoñecible no campo Nome para mostrar. O nome e o tipo de conexión describen esta conexión. Recomendamos escoller un nome que explique o propósito e o destino da conexión.

1. Escolla quen pode usar esta conexión. Se non realiza ningunha acción, o valor predeterminado será Administradores. Para obter máis información, consulte [Permitir aos colaboradores usar unha conexión para as exportacións](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Seleccione ou busque a subscrición na que quere empregar os datos de Customer Insights. Cando seleccione unha subscrición, tamén pode seleccionar **Área de traballo**, **Conta de almacenamento** e **Contedor**.

1. Seleccione **Gardar** para gardar a conexión.

### <a name="configure-an-export"></a>Configurar unha exportación

Pode configurar esta exportación se ten acceso a unha conexión deste tipo. Para configurar a exportación cunha conexión compartida, necesitas polo menos **Colaborador** permisos en Customer Insights. Para obter máis información, consulte os [permisos necesarios para configurar unha exportación](export-destinations.md#set-up-a-new-export).

1. Vaia a **Datos** > **Exportacións**.

1. Seleccione **Engadir exportación** para crear unha nova exportación.

1. No **Conexión para exportación** campo, escolla unha conexión entre **Azure Synapse Analytics** sección. Se non ve o nome desta sección, non hai [conexións](connections.md) deste tipo dispoñibles para vostede.

1. Proporcione un **Nome para mostrar** recoñecible para a exportación e un **Nome da base de datos**.

1. Seleccione as entidades ás que desexa exportar Azure Synapse Analytics.
   > [!NOTE]
   > As orixes de datos baseadas nun [cartafol de Common Data Model](connect-common-data-model.md) non son compatibles.

2. Seleccione **Gardar**.

Ao gardar unha exportación non se executa a exportación inmediatamente.

A exportación execútase con cada [actualización programada](system.md#schedule-tab). Tamén pode [exportar datos baixo demanda](export-destinations.md#run-exports-on-demand).

Para consultar os datos que se exportaron a Synapse Analytics, necesitas **Lector de datos de Blob de almacenamento** acceso ao almacenamento de destino no espazo de traballo das exportacións. 

### <a name="update-an-export"></a>Actualizar unha exportación

1. Vaia a **Datos** > **Exportacións**.

1. Seleccione **Editar** na exportación que queira editar.

   - **Engadir** ou **Eliminar** entidades da selección. Se se eliminan entidades da selección, non se eliminarán da base de datos de Synapse Analytics. Non obstante, as futuras actualizacións de datos non actualizarán as entidades eliminadas desa base de datos.

   - **Cambiar o nome da base de datos** crea unha nova base de datos de Synapse Analytics. A base de datos co nome configurado anteriormente non se actualizará en futuras actualizacións.
