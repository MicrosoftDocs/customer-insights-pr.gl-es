---
title: Exportar datos a Azure Synapse Analytics (vista previa)
description: Aprende a configurar a conexión a Azure Synapse Analytics.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: f9c9ee55f2874ae1dcaf82f2ff17ed0fbbb7804d
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196392"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a>Exportar datos a Azure Synapse Analytics (vista previa)

Azure Synapse é un servizo de análise que acelera o tempo para obter información en almacéns e grandes sistemas de datos. Pode inxerir e usar os seus datos de Customer Insights en [Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Requisitos previos

> [!NOTE]
> Asegúrese de configurar todas as **atribucións de roles** segundo se describe.

- En Customer Insights, o teu Azure Active Directory A conta de usuario (AD) debe ter un [Función de administrador](permissions.md#assign-roles-and-permissions).

En Azure:

- Unha subscrición de Azure activa.

- Se utiliza un novo Azure Data Lake Storage Conta Gen2, o [principal de servizo para Customer Insights](connect-service-principal.md) ten **Colaborador de datos de Blob de almacenamento** permisos. Data Lake Storage Gen2 **debe ter o** [espazo de nomes xerárquico](/azure/storage/blobs/data-lake-storage-namespace) activado.

- No grupo de recursos onde se atopa Azure Synapse o espazo de traballo está situado, o *principal do servizo* e o *Azure AD usuario con permisos de administrador en Customer Insights* debe ser asignado polo menos **Lector**[permisos](/azure/role-based-access-control/role-assignments-portal).

- O *Azure AD usuario con permisos de administrador en Customer Insights* ten **Colaborador de datos de Blob de almacenamento** permisos sobre Azure Data Lake Storage Conta Gen2 onde se atopan os datos e están ligados ao Azure Synapse espazo de traballo. Obteña máis información acerca do [uso do portal de Azure para atribuír un rol de Azure para o acceso aos datos de BLOB e fila](/azure/storage/common/storage-auth-aad-rbac-portal) e dos [permisos do colaborador de datos de BLOB de almacenamento](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- O *[Azure Synapse Identidade xestionada do espazo de traballo](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* ten **Colaborador de datos de Blob de almacenamento** permisos sobre Azure Data Lake Storage Conta Gen2 onde se atopan os datos e están ligados ao Azure Synapse espazo de traballo. Obteña máis información acerca do [uso do portal de Azure para atribuír un rol de Azure para o acceso aos datos de BLOB e fila](/azure/storage/common/storage-auth-aad-rbac-portal) e dos [permisos do colaborador de datos de BLOB de almacenamento](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- No Azure Synapse espazo de traballo, o *principal de servizo para Customer Insights* ten **Administrador de Synapse**[papel asignado](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="set-up-connection-to-azure-synapse"></a>Configura a conexión a Azure Synapse

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vaia a **Administrar** > **Conexións**.

1. Seleccione **Engadir conexión** e escolle **Azure Synapse Analytics**.

1. Déalle á conexión un nome recoñecible no campo **Nome para mostrar**. O nome e o tipo de conexión describen esta conexión. Recomendamos escoller un nome que explique o propósito e o destino da conexión.

1. Escolla quen pode usar esta conexión. Por defecto, só son os administradores. Para obter máis información, consulte [Permitir aos colaboradores usar unha conexión para as exportacións](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Seleccione ou busque a subscrición na que quere empregar os datos de Customer Insights. Cando seleccione unha subscrición, tamén pode seleccionar **Área de traballo**, **Conta de almacenamento** e **Contedor**.

1. Revisa o [privacidade e cumprimento dos datos](connections.md#data-privacy-and-compliance) e selecciona **Estou de acordo**.

1. Seleccione **Gardar** para completar a conexión.

## <a name="configure-an-export"></a>Configurar unha exportación

[!INCLUDE [export-permission-include](includes/export-permission.md)] Para configurar a exportación cunha conexión compartida, necesita polo menos **Colaborador** permisos en Customer Insights.

1. Vaia a **Datos** > **Exportacións**.

1. Seleccione **Engadir exportación**.

1. No **Conexión para exportación** campo, escolla unha conexión entre Azure Synapse Analytics sección. Póñase en contacto cun administrador se non hai conexión dispoñible.

1. Proporcione un **Nome para mostrar** recoñecible para a exportación e un **Nome da base de datos**. A exportación creará unha nova [Azure Synapse base de datos do lago](/azure/synapse-analytics/database-designer/concepts-lake-database) no espazo de traballo definido na conexión.

1. Seleccione as entidades ás que desexa exportar Azure Synapse Analytics.
   > [!NOTE]
   > As orixes de datos baseadas nun [cartafol de Common Data Model](connect-common-data-model.md) non son compatibles.

1. Seleccione **Gardar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Para consultar os datos que se exportaron a Synapse Analytics, necesitas **Lector de datos de Blob de almacenamento** acceso ao almacenamento de destino no espazo de traballo das exportacións.

## <a name="update-an-export"></a>Actualizar unha exportación

1. Vaia a **Datos** > **Exportacións**.

1. Seleccione **Editar** na exportación que queira editar.

   - **Engadir** ou **Eliminar** entidades da selección. Se se eliminan entidades da selección, non se eliminarán da base de datos de Synapse Analytics. Non obstante, as futuras actualizacións de datos non actualizarán as entidades eliminadas desa base de datos.

   - **Cambiar o nome da base de datos** crea unha nova base de datos de Synapse Analytics. A base de datos co nome configurado anteriormente non se actualizará en futuras actualizacións.

[!INCLUDE [footer-include](includes/footer-banner.md)]
