---
title: Conectar cunha conta de Azure Data Lake Storage empregando unha entidade de servizo
description: Use unha entidade de servizo de Azure para conectar co seu propio lago de datos.
ms.date: 12/06/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 1af01e5579f85d7c8bc8976a003f53ef2dd280d1
ms.sourcegitcommit: b7189b8621e66ee738e4164d4b3ce2af0def3f51
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 02/03/2022
ms.locfileid: "8088145"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Conectar cunha conta de Azure Data Lake Storage empregando unha entidade de servizo de Azure

Este artigo explica como conectarse Dynamics 365 Customer Insights cunha Azure Data Lake Storage conta mediante un principal de servizo de Azure en lugar de claves de conta de almacenamento. 

As ferramentas automatizadas que utilizan servizos de Azure sempre deben ter permisos restrinxidos. En lugar de ter aplicacións iniciadas como un usuario totalmente privilexiado, Azure ofrece entidades de seguranza do servizo. Podes utilizar os principais servizos de forma segura [engadir ou editar un cartafol do modelo de datos común como orixe de datos](connect-common-data-model.md) ou [crear ou actualizar un entorno](create-environment.md).

> [!IMPORTANT]
> - A conta de Data Lake Storage que utilizará o principal do servizo debe ser Gen2 e ter [espazo de nomes xerárquico activado](/azure/storage/blobs/data-lake-storage-namespace). Non se admiten as contas de almacenamento de Azure Data Lake Gen1.
> - Necesitas permisos de administrador para a túa subscrición a Azure para crear un principal de servizo.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Crear unha entidade de servizo de Azure para Customer Insights

Antes de crear un novo principal de servizo para Customer Insights, comprobe se xa existe na súa organización.

### <a name="look-for-an-existing-service-principal"></a>Buscar unha entidade de seguranza do servizo existente

1. Vaia ao [Portal de administración de Azure](https://portal.azure.com) e inicie sesión na súa organización.

2. En **Servizos de Azure**, seleccione **Azure Active Directory**.

3. En **Xestionar**, seleccione **Aplicacións empresariais**.

4. Busque o ID da aplicación de Microsoft:
   - Información do público: `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` co nome `Dynamics 365 AI for Customer Insights`
   - Información de interacción: `ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd` co nome `Dynamics 365 AI for Customer Insights engagement insights`

5. Se atopa un rexistro coincidente, significa que a entidade de servizo xa existe. 
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Captura de pantalla que mostra unha entidade de servizo existente.":::
   
6. Se non se devolven resultados, cree unha nova entidade de seguranza do servizo.

>[!NOTE]
>Para usar todo a potencia de Dynamics 365 Customer Insights, suxerímoslle que engada ambas aplicacións á entidade de servizo.

### <a name="create-a-new-service-principal"></a>Crear unha entidade de seguranza do servizo nova

1. Instale a versión máis recente de Azure Active Directory PowerShell para Graph. Para obter máis información, vaia a [Instalar Azure Active Directory PowerShell para Graph](/powershell/azure/active-directory/install-adv2).

   1. No seu PC, seleccione a tecla Windows do teclado e busque **Windows PowerShell** e seleccione **Executar como administrador**.
   
   1. Na xanela de PowerShell que se abre, introduza `Install-Module AzureAD`.

2. Cree a entidade de servizo para Customer Insights co módulo de Azure AD PowerShell.

   1. Na xanela de PowerShell que se abre, introduza `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`. Substitúa *[o seu identificador de arrendatario]* polo ID real do seu arrendatario onde desexa crear a entidade de seguranza do servizo. O parámetro de nome do ambiente, `AzureEnvironmentName`, é opcional.
  
   1. Introduza `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Este comando crea a entidade de seguranza do servizo para obter información sobre o público no inquilino seleccionado. 

   1. Introduza `New-AzureADServicePrincipal -AppId "ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd" -DisplayName "Dynamics 365 AI for Customer Insights engagement insights"`. Este comando crea a entidade de servizo da información de interacción no arrendatario seleccionado.

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Conceder permisos á entidade de seguranza do servizo para acceder á conta de almacenamento

Vaia ao portal de Azure para conceder permisos á entidade de seguranza do servizo para a conta de almacenamento que desexa empregar para a información da audiencia.

1. Vaia ao [Portal de administración de Azure](https://portal.azure.com) e inicie sesión na súa organización.

1. Abra a conta de almacenamento á que desexa que teña acceso a entidade de seguranza do servizo para que teña acceso a información sobre o público.

1. No panel esquerdo, seleccione **Control de acceso (IAM)** e, a continuación, seleccione **Engadir** > **Engadir atribución de roles**.

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Captura de pantalla que mostra o portal de Azure mentres se engade unha atribución de roles.":::

1. No panel **Engadir atribución de roles**, estableza as seguintes propiedades:
   - Función: **Colaborador de datos do BLOB de almacenamento**
   - Asignar acceso a: **Usuario, grupo ou entidade de seguranza do servizo**
   - Seleccione: **Dynamics 365 AI for Customer Insights** e **Dynamics 365 AI for Customer Insights engagement insights** (as dúas [entidades de servizo](#create-a-new-service-principal) que creou anteriormente neste procedemento)

1.  Seleccione **Gardar**.

Pode tardar ata 15 minutos en propagar os cambios.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a>Introduza o ID de recurso de Azure ou os detalles da subscrición a Azure no anexo da conta de almacenamento para a información do público

Pode anexar unha conta de Data Lake Storage na información do público para [almacenar datos de saída](manage-environments.md) ou [usala como orixe de datos](connect-common-data-service-lake.md). Esta opción permítelle escoller entre un enfoque baseado en recursos ou baseado en subscricións. Dependendo do enfoque que escolla, siga o procedemento nunha das seguintes seccións.

### <a name="resource-based-storage-account-connection"></a>Conexión de conta de almacenamento baseada en recursos

1. Vaia ao [Portal de administración de Azure](https://portal.azure.com), inicie sesión na súa subscrición e abra a conta de almacenamento.

1. No panel esquerdo, vaia a **Configuración** > **Propiedades**.

1. Copie o valor do ID do recurso da conta de almacenamento.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Copie o ID do recurso da conta de almacenamento.":::

1. Na información do público, insira o ID do recurso no campo do recurso mostrado na pantalla de conexión da conta de almacenamento.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Insira a información do ID do recurso da conta de almacenamento.":::   

1. Continúe cos pasos restantes nas estatísticas do público para anexar a conta de almacenamento.

### <a name="subscription-based-storage-account-connection"></a>Conexión de conta de almacenamento baseada na subscrición

1. Vaia ao [Portal de administración de Azure](https://portal.azure.com), inicie sesión na súa subscrición e abra a conta de almacenamento.

1. No panel esquerdo, vaia a **Configuración** > **Propiedades**.

1. Revise a **Subscrición**, o **Grupo de recursos** e o **Nome** da conta de almacenamento para asegurarse de que selecciona os valores correctos nas estatísticas do público.

1. Na información do público, escolla os valores para os campos correspondentes ao anexar a conta de almacenamento.

1. Continúe cos pasos restantes nas estatísticas do público para anexar a conta de almacenamento.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
