---
title: Conectar cunha conta de Azure Data Lake Storage empregando unha entidade de servizo de Azure
description: Use unha entidade de servizo de Azure para conectar co seu propio lago de datos.
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: eba10068c48db5c147100c25a397bcc13b014784
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304195"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Conectar cunha conta de Azure Data Lake Storage empregando unha entidade de servizo de Azure

Dynamics 365 Customer Insights ofrece unha opción para conectarse a un Azure Data Lake Storage conta mediante un principal de servizo de Azure en lugar de claves de conta de almacenamento.

As ferramentas automatizadas que usan os servizos de Azure deben ter permisos restrinxidos. En lugar de ter aplicacións iniciadas como un usuario totalmente privilexiado, Azure ofrece entidades de seguranza do servizo. Use os principais servizos de forma segura [engadir ou editar un cartafol do modelo de datos común como orixe de datos](connect-common-data-model.md) ou [crear ou actualizar un entorno](create-environment.md).

## <a name="prerequisites"></a>Requisitos previos

- A conta de Data Lake Storage que utilizará o principal do servizo debe ser Gen2. As contas de almacenamento de Azure Data Lake Gen1 non son compatibles.
- A conta de Data Lake Storage ten [espazo de nomes xerárquico activado](/azure/storage/blobs/data-lake-storage-namespace).
- Permisos de administrador para o teu arrendatario de Azure, se tes que crear un novo principal de servizo.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Crear unha entidade de servizo de Azure para Customer Insights

Antes de crear un novo principal de servizo para Customer Insights, comprobe se xa existe na súa organización. Na maioría dos casos, xa existe.

### <a name="look-for-an-existing-service-principal"></a>Buscar unha entidade de seguranza do servizo existente

1. Vaia ao [Portal de administración de Azure](https://portal.azure.com) e inicie sesión na súa organización.

2. En **Servizos de Azure**, seleccione **Azure Active Directory**.

3. Baixo **Xestionar**, seleccione **Aplicación Microsoft**.

4. Engade un filtro para **O ID da aplicación comeza por**`0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` ou buscar o nome `Dynamics 365 AI for Customer Insights`.

5. Se atopa un rexistro coincidente, significa que a entidade de servizo xa existe. [Conceder permisos](#grant-permissions-to-the-service-principal-to-access-the-storage-account) para que o principal do servizo acceda á conta de almacenamento.

   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Captura de pantalla que mostra unha entidade de servizo existente.":::

6. Se non se devolve ningún resultado, [crear un novo principal de servizo](#create-a-new-service-principal).

### <a name="create-a-new-service-principal"></a>Crear unha entidade de seguranza do servizo nova

1. Instale a versión máis recente de Azure Active Directory PowerShell para Graph. Para obter máis información, vaia a [Instalar Azure Active Directory PowerShell para Graph](/powershell/azure/active-directory/install-adv2).

   1. No seu PC, prema a tecla Windows do teclado e busque **Windows PowerShell** e selecciona **Executar como administrador**.

   1. Na xanela de PowerShell que se abre, introduza `Install-Module AzureAD`.

2. Cree a entidade de servizo para Customer Insights co módulo de Azure AD PowerShell.

   1. Na xanela de PowerShell que se abre, introduza `Connect-AzureAD -TenantId "[your Directory ID]" -AzureEnvironmentName Azure`. Substituír *[ID do teu directorio]* co ID de directorio real da túa subscrición de Azure onde queres crear o principal do servizo. O parámetro de nome do ambiente, `AzureEnvironmentName`, é opcional.
  
   1. Introduza `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Este comando crea o principal de servizo para Customer Insights na subscrición de Azure seleccionada.

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Conceder permisos á entidade de seguranza do servizo para acceder á conta de almacenamento

Para conceder permisos ao principal do servizo para a conta de almacenamento que quere usar en Customer Insights, debe asignarse un dos seguintes roles á conta de almacenamento ou ao contedor:

|Credencial|Requirimentos|
|----------|------------|
|Usuario conectado actualmente|**Papel** : Storage Blob Data Reader, Storage Blob Contributor ou Storage Blob Owner.<br>**Nivel** : permisos concedidos na conta de almacenamento ou no contedor.</br>|
|Director do servizo de información do cliente -<br>Usando Azure Data Lake Storage como orixe de datos</br>|Opción 1<ul><li>**Papel** : Storage Blob Data Reader, Storage Blob Data Contributor ou Storage Blob Data Owner.</li><li>**Nivel** : permisos concedidos na conta de almacenamento.</li></ul>Opción 2 *(sen compartir o acceso principal do servizo á conta de almacenamento)*<ul><li>**Papel 1** : Storage Blob Data Reader, Storage Blob Data Contributor ou Storage Blob Data Owner.</li><li>**Nivel** : Permisos concedidos ao contedor.</li><li>**Papel 2** : Delegador de datos de Blob de almacenamento.</li><li>**Nivel** : permisos concedidos na conta de almacenamento.</li></ul>|
|Director do servizo de información do cliente - <br>Usando Azure Data Lake Storage como saída ou destino</br>|Opción 1<ul><li>**Papel** : Colaborador de datos de blob de almacenamento ou propietario do blob de almacenamento.</li><li>**Nivel** : permisos concedidos na conta de almacenamento.</li></ul>Opción 2 *(sen compartir o acceso principal do servizo á conta de almacenamento)*<ul><li>**Papel** : Colaborador de datos de blob de almacenamento ou propietario do blob de almacenamento.</li><li>**Nivel** : Permisos concedidos ao contedor.</li><li>**Papel 2** : Delegador de Blob de almacenamento.</li><li>**Nivel** : permisos concedidos na conta de almacenamento.</li></ul>|

1. Vaia ao [Portal de administración de Azure](https://portal.azure.com) e inicie sesión na súa organización.

1. Abre a conta de almacenamento á que queres que teña acceso o principal do servizo para Customer Insights.

1. No panel esquerdo, seleccione **Control de acceso (IAM)** e, a continuación, seleccione **Engadir** > **Engadir atribución de roles**.

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Captura de pantalla que mostra o portal de Azure mentres se engade unha atribución de roles.":::

1. No panel **Engadir atribución de roles**, estableza as seguintes propiedades:
   - **Papel** : Storage Blob Data Reader, Storage Blob Contributor ou Storage Blob Owner en función das credenciais indicadas anteriormente.
   - **Asignar acceso a** :**Usuario, grupo ou principal de servizo**
   - **Seleccione** membros: **Dynamics 365 AI para Customer Insights** (o [principal do servizo](#create-a-new-service-principal) buscaches anteriormente neste procedemento)

1. Seleccione **Revisar + asignar**.

Pode tardar ata 15 minutos en propagar os cambios.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-customer-insights"></a>Introduza o ID do recurso de Azure ou os detalles da subscrición de Azure no anexo da conta de almacenamento de Customer Insights

Achegue unha conta de Data Lake Storage en Customer Insights a [almacenar datos de saída](manage-environments.md) ou [utilízao como orixe de datos](connect-dataverse-managed-lake.md). Elixe entre a [baseado en recursos](#resource-based-storage-account-connection) ou a [baseado en subscrición](#subscription-based-storage-account-connection) achegarse e seguir eses pasos.

### <a name="resource-based-storage-account-connection"></a>Conexión de conta de almacenamento baseada en recursos

1. Vaia ao [Portal de administración de Azure](https://portal.azure.com), inicie sesión na súa subscrición e abra a conta de almacenamento.

1. No panel esquerdo, vai a **Configuración** > **Puntos finais**.

1. Copie o valor do ID do recurso da conta de almacenamento.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Copie o ID do recurso da conta de almacenamento.":::

1. En Customer Insights, insira o ID do recurso no campo do recurso que aparece na pantalla de conexión da conta de almacenamento.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Insira a información do ID do recurso da conta de almacenamento.":::

1. Continúa cos pasos restantes en Customer Insights para anexar a conta de almacenamento.

### <a name="subscription-based-storage-account-connection"></a>Conexión de conta de almacenamento baseada na subscrición

1. Vaia ao [Portal de administración de Azure](https://portal.azure.com), inicie sesión na súa subscrición e abra a conta de almacenamento.

1. No panel esquerdo, vaia a **Configuración** > **Propiedades**.

1. Revisa o **Subscrición**, **de recursos**, e o **Nome** da conta de almacenamento para asegurarse de que selecciona os valores correctos en Customer Insights.

1. En Customer Insights, escolla os valores dos campos correspondentes ao anexar a conta de almacenamento.

1. Continúa cos pasos restantes en Customer Insights para anexar a conta de almacenamento.

[!INCLUDE [footer-include](includes/footer-banner.md)]
