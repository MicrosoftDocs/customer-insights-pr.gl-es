---
title: Inxerir datos de Azure Synapse Analytics
description: Usa unha base de datos en Azure Synapse como orixe de datos en Dynamics 365 Customer Insights.
ms.date: 02/24/2022
ms.reviewer: v-wendysmith
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 7c758dccf7ea34dd7b8f80d05eff1ed12030526f
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642653"
---
# <a name="connect-an-azure-synapse-data-source-preview"></a>Conectar un Azure Synapse orixe de datos (vista previa)

Azure Synapse Analytics é un servizo de análise empresarial que acelera o tempo para obter información en almacéns de datos e sistemas de big data. Azure Synapse Analytics reúne o mellor das tecnoloxías SQL utilizadas no almacenamento de datos empresarial, tecnoloxías Spark usadas para big data, Data Explorer para análise de rexistros e series de tempo, Pipelines para a integración de datos e ETL/ELT e unha profunda integración con outros servizos de Azure, como Power BI,Cosmos DB e AzureML.

Para obter máis información, consulte [Azure Synapse visión xeral](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Requisitos previos

Débense cumprir os seguintes requisitos previos para configurar a conexión desde Dynamics 365 Customer Insights a Azure Synapse.

> [!IMPORTANT]
> Asegúrese de configurar todas as **atribucións de roles** segundo se describe.  

## <a name="prerequisites-in-customer-insights"></a>Requisitos previos en Customer Insights

* Tes un **Administrador** papel en Customer Insights. Máis información sobre [permisos de usuario en Customer Insights](permissions.md#assign-roles-and-permissions).

En Azure: 

- Unha subscrición de Azure activa.

- Se utiliza un novo Azure Data Lake Storage Conta Gen2, o *principal de servizo para Customer Insights* necesidades **Colaborador de datos de Blob de almacenamento** permisos. Máis información sobre [conectando a un Azure Data Lake Storage cun principal de servizo para Customer Insights](connect-service-principal.md). Data Lake Storage Gen2 **debe ter o** [espazo de nomes xerárquico](/azure/storage/blobs/data-lake-storage-namespace) activado.

- No grupo de recursos o Azure Synapse o espazo de traballo está situado, o *principal do servizo* e o *usuario de Customer Insights* debe ser asignado polo menos **Lector** permisos. Para obter máis información, consulte [Atribuír roles de Azure no portal de Azure](/azure/role-based-access-control/role-assignments-portal).

- O *usuario* precisa permisos de **colaborador de datos de BLOB de almacenamento** na conta de Azure Data Lake Storage Gen2 na que se atopan os datos ligados á área de traballo de Azure Synapse. Obteña máis información acerca do [uso do portal de Azure para atribuír un rol de Azure para o acceso aos datos de BLOB e fila](/azure/storage/common/storage-auth-aad-rbac-portal) e dos [permisos do colaborador de datos de BLOB de almacenamento](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- A *[identidade xestionada da área de traballo de Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* precisa permisos de **colaborador de datos de BLOB de almacenamento** na conta de Azure Data Lake Storage Gen2 na que se atopan os datos ligados á área de traballo de Azure Synapse. Obteña máis información acerca do [uso do portal de Azure para atribuír un rol de Azure para o acceso aos datos de BLOB e fila](/azure/storage/common/storage-auth-aad-rbac-portal) e dos [permisos do colaborador de datos de BLOB de almacenamento](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- No Azure Synapse espazo de traballo, o *principal de servizo para Customer Insights* necesidades **Administrador de Synapse** rol asignado. Para obter máis información, consulte [Como configurar o control de acceso para a súa área de traballo de Synapse](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="connect-to-data-lake-databases-in-azure-synapse-analytics"></a>Conéctese ás bases de datos de Data Lake en Azure Synapse Analytics

1. Vaia a **Datos** > **Orixes de datos**.

1. Seleccione **Engadir orixe de datos**.

1. Escolle o **Azure Synapse Analytics (Vista previa)** método.

1. Escriba un **Nome** para a orixe de datos e seleccione **Seguinte** para crear o orixe de datos. 

1. Escolle un [conexión dispoñible](connections.md) a Azure Synapse Analytics ou crear un novo.

1. Escolle a **Base de datos do lago** desde o espazo de traballo conectado no seleccionado Azure Synapse Analytics conexión e seleccione **A continuación**.

1. Seleccione as entidades a inxerir da base de datos conectada. 

1. Opcionalmente, escolla as entidades de datos para permitir o perfil de datos. 

1. Seleccione **Gardar** para aplicar a túa selección e iniciar a inxestión dos datos do teu recén creado orixe de datos ligado ás táboas da base de datos de Lake en Azure Synapse Analytics.
