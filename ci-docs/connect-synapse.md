---
title: Conectar un Azure Synapse orixe de datos (vista previa)
description: Usa unha base de datos en Azure Synapse como orixe de datos en Dynamics 365 Customer Insights.
ms.date: 03/25/2022
ms.reviewer: v-wendysmith
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: c4ae65613a02df38a30f907dae72d413bf1a702f
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "9052697"
---
# <a name="connect-an-azure-synapse-analytics-data-source-preview"></a>Conectar un Azure Synapse Analytics orixe de datos (vista previa)

Azure Synapse Analytics é un servizo de análise empresarial que acelera o tempo para obter información en almacéns de datos e sistemas de big data. Azure Synapse Analytics reúne o mellor das tecnoloxías SQL utilizadas no almacenamento de datos empresarial, tecnoloxías Spark usadas para big data, Data Explorer para análise de rexistros e series de tempo, Pipelines para a integración de datos e ETL/ELT e unha profunda integración con outros servizos de Azure, como Power BI,Cosmos DB e AzureML.

Para obter máis información, consulte [Azure Synapse visión xeral](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Requisitos previos

> [!IMPORTANT]
> Asegúrese de configurar todas as **atribucións de roles** segundo se describe.  

**En Customer Insights**:

* Tes un **Administrador** papel en Customer Insights. Máis información sobre [permisos de usuario en Customer Insights](permissions.md#assign-roles-and-permissions).

**En Azure**:

- Unha subscrición de Azure activa.

- Se utiliza un novo Azure Data Lake Storage Conta Gen2, o *principal de servizo para Customer Insights* necesidades **Colaborador de datos de Blob de almacenamento** permisos. Máis información sobre [conectando a un Azure Data Lake Storage cun principal de servizo para Customer Insights](connect-service-principal.md). Data Lake Storage Gen2 **debe ter o** [espazo de nomes xerárquico](/azure/storage/blobs/data-lake-storage-namespace) activado.

- No grupo de recursos o Azure Synapse o espazo de traballo está situado, o *principal do servizo* e o *usuario de Customer Insights* debe ser asignado polo menos **Lector** permisos. Para obter máis información, consulte [Atribuír roles de Azure no portal de Azure](/azure/role-based-access-control/role-assignments-portal).

- O *usuario* precisa permisos de **colaborador de datos de BLOB de almacenamento** na conta de Azure Data Lake Storage Gen2 na que se atopan os datos ligados á área de traballo de Azure Synapse. Obteña máis información acerca do [uso do portal de Azure para atribuír un rol de Azure para o acceso aos datos de BLOB e fila](/azure/storage/common/storage-auth-aad-rbac-portal) e dos [permisos do colaborador de datos de BLOB de almacenamento](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- A *[identidade xestionada da área de traballo de Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* precisa permisos de **colaborador de datos de BLOB de almacenamento** na conta de Azure Data Lake Storage Gen2 na que se atopan os datos ligados á área de traballo de Azure Synapse. Obteña máis información acerca do [uso do portal de Azure para atribuír un rol de Azure para o acceso aos datos de BLOB e fila](/azure/storage/common/storage-auth-aad-rbac-portal) e dos [permisos do colaborador de datos de BLOB de almacenamento](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- No Azure Synapse espazo de traballo, o *principal de servizo para Customer Insights* necesidades **Administrador de Synapse** rol asignado. Para obter máis información, consulte [Como configurar o control de acceso para a súa área de traballo de Synapse](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="connect-to-the-data-lake-database-in-azure-synapse-analytics"></a>Conéctese á base de datos do lago de datos en Azure Synapse Analytics

1. Vaia a **Datos** > **Orixes de datos**.

1. Seleccione **Engadir orixe de datos**.

1. Escolle o **Azure Synapse Analytics (Vista previa)** método.

   :::image type="content" source="media/data_sources_synapse.png" alt-text="Cadro de diálogo para conectarse aos datos de Synapse Analytics":::
  
1. Introduza a **Nome** para o orixe de datos e un opcional **Descrición**.

1. Escolle un [conexión dispoñible](connections.md) a Azure Synapse Analytics ou crear un novo.

1. Escolle a **Base de datos** desde o espazo de traballo conectado no seleccionado Azure Synapse Analytics conexión e seleccione **A continuación**. Actualmente, só admitimos o tipo de base de datos *Base de datos do lago*.

1. Seleccione as entidades a inxerir da base de datos conectada e seleccione **A continuación**.

1. Opcionalmente, escolla as entidades de datos para permitir o perfil de datos.

1. Seleccione **Gardar** para aplicar a túa selección e iniciar a inxestión dos datos do teu recén creado orixe de datos ligado ás táboas da base de datos de Lake en Azure Synapse Analytics. O **Fontes de datos** ábrese a páxina mostrando o novo orixe de datos en **Refrescante** estado.
