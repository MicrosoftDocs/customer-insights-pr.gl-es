---
title: Conectar cunha conta de Azure Data Lake Storage empregando unha entidade de servizo
description: Use unha entidade de servizo de Azure para conectar co seu propio lago de datos.
ms.date: 04/26/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: 1dd99edc327bd41b0442b390f2e4f8664269f553
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642656"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Conectar cunha conta de Azure Data Lake Storage empregando unha entidade de servizo de Azure

Este artigo explica como conectarse Dynamics 365 Customer Insights cunha Azure Data Lake Storage conta mediante un principal de servizo de Azure en lugar de claves de conta de almacenamento. 

As ferramentas automatizadas que utilizan servizos de Azure sempre deben ter permisos restrinxidos. En lugar de ter aplicacións iniciadas como un usuario totalmente privilexiado, Azure ofrece entidades de seguranza do servizo. Podes utilizar os principais servizos de forma segura [engadir ou editar un cartafol do modelo de datos común como orixe de datos](connect-common-data-model.md) ou [crear ou actualizar un ambiente](create-environment.md).

> [!IMPORTANT]
> - A conta de Data Lake Storage que utilizará o principal do servizo debe ser Gen2 e ter [espazo de nomes xerárquico activado](/azure/storage/blobs/data-lake-storage-namespace). Non se admiten as contas de almacenamento de Azure Data Lake Gen1.
> - Necesitas permisos de administrador para a túa subscrición a Azure para crear un principal de servizo.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Crear unha entidade de servizo de Azure para Customer Insights

Antes de crear un novo principal de servizo para Customer Insights, comprobe se xa existe na súa organización.

### <a name="look-for-an-existing-service-principal"></a>Buscar unha entidade de seguranza do servizo existente

1. Vaia ao [Portal de administración de Azure](https://portal.azure.com) e inicie sesión na súa organización.

2. En **Servizos de Azure**, seleccione **Azure Active Directory**.

3. En **Xestionar**, seleccione **Aplicacións empresariais**.

4. Busca o ID da aplicación de Microsoft`0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` co nome `Dynamics 365 AI for Customer Insights`.

5. Se atopa un rexistro coincidente, significa que a entidade de servizo xa existe. 
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Captura de pantalla que mostra unha entidade de servizo existente.":::
   
6. Se non se devolven resultados, cree unha nova entidade de seguranza do servizo.

### <a name="create-a-new-service-principal"></a>Crear unha entidade de seguranza do servizo nova

1. Instale a versión máis recente de Azure Active Directory PowerShell para Graph. Para obter máis información, vaia a [Instalar Azure Active Directory PowerShell para Graph](/powershell/azure/active-directory/install-adv2).

   1. No seu PC, seleccione a tecla Windows do teclado e busque **Windows PowerShell** e seleccione **Executar como administrador**.
   
   1. Na xanela de PowerShell que se abre, introduza `Install-Module AzureAD`.

2. Cree a entidade de servizo para Customer Insights co módulo de Azure AD PowerShell.

   1. Na xanela de PowerShell que se abre, introduza `Connect-AzureAD -TenantId "[your Directory ID]" -AzureEnvironmentName Azure`. Substituír *[ID do teu directorio]* co ID de directorio real da túa subscrición de Azure onde queres crear o principal do servizo. O parámetro de nome do ambiente, `AzureEnvironmentName`, é opcional.
  
   1. Introduza `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Este comando crea o principal de servizo para Customer Insights na subscrición de Azure seleccionada. 

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Conceder permisos á entidade de seguranza do servizo para acceder á conta de almacenamento

Vaia ao portal de Azure para conceder permisos ao principal do servizo para a conta de almacenamento que quere usar en Customer Insights.

1. Vaia ao [Portal de administración de Azure](https://portal.azure.com) e inicie sesión na súa organización.

1. Abre a conta de almacenamento á que queres que teña acceso o principal do servizo para Customer Insights.

1. No panel esquerdo, seleccione **Control de acceso (IAM)** e, a continuación, seleccione **Engadir** > **Engadir atribución de roles**.

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Captura de pantalla que mostra o portal de Azure mentres se engade unha atribución de roles.":::

1. No panel **Engadir atribución de roles**, estableza as seguintes propiedades:
   - Función: **Colaborador de datos do BLOB de almacenamento**
   - Asignar acceso a: **Usuario, grupo ou entidade de seguranza do servizo**
   - Seleccionar membros: **Dynamics 365 AI para Customer Insights** (o [principal do servizo](#create-a-new-service-principal) creaches anteriormente neste procedemento)

1.  Seleccione **Revisar + asignar**.

Pode tardar ata 15 minutos en propagar os cambios.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-customer-insights"></a>Introduza o ID do recurso de Azure ou os detalles da subscrición de Azure no anexo da conta de almacenamento de Customer Insights

Podes anexar unha conta de Data Lake Storage en Customer Insights a [almacenar datos de saída](manage-environments.md) ou [utilízao como orixe de datos](connect-dataverse-managed-lake.md). Esta opción permítelle escoller entre un enfoque baseado en recursos ou baseado en subscricións. Dependendo do enfoque que escolla, siga o procedemento nunha das seguintes seccións.

### <a name="resource-based-storage-account-connection"></a>Conexión de conta de almacenamento baseada en recursos

1. Vaia ao [Portal de administración de Azure](https://portal.azure.com), inicie sesión na súa subscrición e abra a conta de almacenamento.

1. No panel esquerdo, vaia a **Configuración** > **Propiedades**.

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