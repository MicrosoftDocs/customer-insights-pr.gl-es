---
title: Conectar cunha conta de Azure Data Lake Storage Gen2 cunha entidade de seguranza do servizo
description: Use unha entidade de seguranza do servizo de Azure para obter información sobre a audiencia para conectarse ao seu propio lago de datos ao anexalo á información sobre a audiencia.
ms.date: 11/24/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: c2fae278d34fa02b9168ac70dfa8dd351653245e
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644086"
---
# <a name="connect-to-an-azure-data-lake-storage-gen2-account-with-an-azure-service-principal-for-audience-insights"></a>Conectarse a unha conta de Azure Data Lake Storage Gen2 cunha entidade principal de seguranza do servizo de Azure para obter información sobre o público

As ferramentas automatizadas que utilizan servizos de Azure sempre deben ter permisos restrinxidos. En lugar de ter aplicacións iniciadas como un usuario totalmente privilexiado, Azure ofrece entidades de seguranza do servizo. Siga a ler para aprender a conectar as estatísticas do público cunha conta de Azure Data Lake Storage Gen2 usando unha entidade de seguranza do servizo de Azure en lugar de claves da conta de almacenamento. 

Pode usar a entidade de seguranza do servizo para, de forma segura, [engadir ou editar un cartafol de Common Data Model como orixe de datos](connect-common-data-model.md) ou [crear un novo ambiente ou actualizar un existente](manage-environments.md#create-an-environment-in-an-existing-organization).

Precisa permisos de administrador para a súa subscrición a Azure para crear a entidade de seguranza do servizo.

## <a name="create-azure-service-principal-for-audience-insights"></a>Crear a entidade de seguranza do servizo de Azure para obter información sobre o público

Antes de crear unha nova entidade de seguranza do servizo para obter información sobre o público, comprobe se xa existe na súa organización.

### <a name="look-for-an-existing-service-principal"></a>Buscar unha entidade de seguranza do servizo existente

1. Vaia ao [Portal de administración de Azure](https://portal.azure.com) e inicie sesión na súa organización.

2. Seleccione **Azure Active Directory** dos servizos de Azure.

3. En **Xestionar**, seleccione **Aplicacións empresariais**.

4. Busque o ID da aplicación interna de información sobre o público `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` ou o nome `Dynamics 365 AI for Customer Insights`.

5. Se atopa un rexistro coincidente, significa que existe a entidade de seguranza do servizo de información sobre o público. Non é necesario volvela crear.
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Captura de pantalla que mostra a entidade de seguranza do servizo existente.":::
   
6. Se non se devolven resultados, cree unha nova entidade de seguranza do servizo.

### <a name="create-a-new-service-principal"></a>Crear unha entidade de seguranza do servizo nova

1. Instale a última versión de **Azure Active Directory PowerShell para Graph**. Para obter máis información, consulte [Instalar Azure Active Directory PowerShell para Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).
   - No seu PC, seleccione a tecla Windows do teclado e busque **Windows PowerShell** e **Executar como administrador**.
   
   - Na xanela de PowerShell que se abre, introduza `Install-Module AzureAD`.

2. Cree a entidade de seguranza do servizo para obter información sobre o público co módulo Azure AD PowerShell.
   - Na xanela de PowerShell que se abre, introduza `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`. Substitúa "o seu identificador de arrendatario" polo ID real do seu arrendatario onde desexa crear a entidade de seguranza do servizo. O parámetro de nome do ambiente `AzureEnvironmentName` é opcional.
  
   - Introduza `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Este comando crea a entidade de seguranza do servizo para obter información sobre o público no inquilino seleccionado.  

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Conceder permisos á entidade de seguranza do servizo para acceder á conta de almacenamento

Vaia ao portal de Azure para conceder permisos á entidade de seguranza do servizo para a conta de almacenamento que desexa empregar para a información da audiencia.

1. Vaia ao [Portal de administración de Azure](https://portal.azure.com) e inicie sesión na súa organización.

1. Abra a conta de almacenamento á que desexa que teña acceso a entidade de seguranza do servizo para que teña acceso a información sobre o público.

1. Seleccione **Control de acceso (IAM)** no panel de navegación e seleccione **Engadir** > **Engadir asignación de funcións**.
   
   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Captura de pantalla que mostra o portal de Azure mentres se engade unha asignación de funcións.":::
   
1. No panel **Engadir asignación de funcións**, estableza as seguintes propiedades:
   - Función: *Colaborador de datos do BLOB de almacenamento*
   - Asignar acceso a: *Usuario, grupo ou entidade de seguranza do servizo*
   - Seleccione: *Dynamics 365 AI for Customer Insights* (a [entidade de seguranza do servizo que creou](#create-a-new-service-principal))

1.  Seleccione **Gardar**.

Pode tardar ata 15 minutos en propagar os cambios.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a>Introduza o ID de recurso de Azure ou os detalles da subscrición a Azure no anexo da conta de almacenamento para a información do público.

Anexe unha conta de almacenamento de Azure Data Lake na información sobre a audiencia para [almacenar datos de saída](manage-environments.md) ou [úsea como orixe de datos](connect-common-data-service-lake.md). Escoller a opción Azure Data Lake permítelle escoller entre un enfoque baseado en recursos ou baseado nunha subscrición.

Siga os pasos seguintes para proporcionar a información requirida sobre o enfoque seleccionado.

### <a name="resounce-based-storage-account-connection"></a>Conexión de conta de almacenamento baseada en recursos

1. Vaia ao [Portal de administración de Azure](https://portal.azure.com), inicie sesión na súa subscrición e abra a conta de almacenamento.

1. Vaia a **Configuración** > **Propiedades** no panel de navegación.

1. Copie o valor do ID do recurso da conta de almacenamento.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Copie o ID do recurso da conta de almacenamento.":::

1. En estatísticas de audiencia, insira o ID do recurso no campo do recurso mostrado na pantalla de conexión da conta de almacenamento.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Insira a información do ID do recurso da conta de almacenamento.":::   
   
1. Continúe cos pasos restantes nas estatísticas do público para anexar a conta de almacenamento.

### <a name="subscription-based-storage-account-connection"></a>Conexión de conta de almacenamento baseada na subscrición

1. Vaia ao [Portal de administración de Azure](https://portal.azure.com), inicie sesión na súa subscrición e abra a conta de almacenamento.

1. Vaia a **Configuración** > **Propiedades** no panel de navegación.

1. Revise a **Subscrición**, o **Grupo de recursos** e o **Nome** da conta de almacenamento para asegurarse de que selecciona os valores correctos nas estatísticas do público.

1. En estatísticas de audiencia, escolla os valores ou os campos correspondentes ao anexar a conta de almacenamento.

   :::image type="content" source="media/ADLS-SP-SubscriptionConnection.png" alt-text="Insira a información do ID do recurso da conta de almacenamento.":::
   
1. Continúe cos pasos restantes nas estatísticas do público para anexar a conta de almacenamento.
