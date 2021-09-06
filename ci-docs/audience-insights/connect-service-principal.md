---
title: Conectar cunha conta de Azure Data Lake Storage empregando unha entidade de servizo
description: Use unha entidade de servizo de Azure para conectar co seu propio lago de datos.
ms.date: 07/23/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 845d1f55eb99f2adf9b437124addec4f6d016fec
ms.sourcegitcommit: 1c396394470df8e68c2fafe3106567536ff87194
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 08/30/2021
ms.locfileid: "7461146"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Conectar cunha conta de Azure Data Lake Storage empregando unha entidade de servizo de Azure
<!--note from editor: The Cloud Style Guide would have us just use "Azure Data Lake Storage" to mean the current version, unless the old version (Gen1) is mentioned. I've followed this guidance, even though it seems that our docs and Azure docs are all over the map on this.-->
As ferramentas automatizadas que utilizan servizos de Azure sempre deben ter permisos restrinxidos. En lugar de ter aplicacións iniciadas como un usuario totalmente privilexiado, Azure ofrece entidades de seguranza do servizo. Siga lendo para aprender a conectarse a Dynamics 365 Customer Insights cunha conta de Azure Data Lake Storage empregando unha entidade de servizo de Azure en lugar de claves de conta de almacenamento. 

Pode usar a entidade de servizo para [engadir ou editar un cartafol de Common Data Model como orixe de datos](connect-common-data-model.md) ou [crear ou actualizar un ambiente](get-started-paid.md) de forma segura.<!--note from editor: Suggested. Or it could be ", or create a new environment or update an existing one". I think "new" is implied with "create". The comma is necessary.-->

> [!IMPORTANT]
> - A conta de Data Lake Storage que usará<!--note from editor: Suggested. Or perhaps it could be "The Data Lake Storage account to which you want to give access to the service principal..."--> a entidade de servizo debe ter [activado o espazo de nomes xerárquico](/azure/storage/blobs/data-lake-storage-namespace).
> - Precisa permisos de administrador para a súa subscrición a Azure para crear a entidade de seguranza do servizo.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Crear unha entidade de servizo de Azure para Customer Insights

Antes de crear unha nova entidade de servizo para a información do público ou a información de interacción, comprobe se xa existe na súa organización.

### <a name="look-for-an-existing-service-principal"></a>Buscar unha entidade de seguranza do servizo existente

1. Vaia ao [Portal de administración de Azure](https://portal.azure.com) e inicie sesión na súa organización.

2. En **Servizos de Azure**, seleccione **Azure Active Directory**.

3. En **Xestionar**, seleccione **Aplicacións empresariais**.

4. Busque o<!--note from editor: Via Microsoft Writing Style Guide.--> ID da aplicación de Microsoft:
   - Información do público: `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` co nome `Dynamics 365 AI for Customer Insights`
   - Información de interacción: `ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd` co nome `Dynamics 365 AI for Customer Insights engagement insights`

5. Se atopa un rexistro coincidente, significa que a entidade de servizo xa existe. 
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Captura de pantalla que mostra unha entidade de servizo existente.":::
   
6. Se non se devolven resultados, cree unha nova entidade de seguranza do servizo.

>[!NOTE]
>Para usar todo a potencia de Dynamics 365 Customer Insights, suxerímoslle que engada ambas aplicacións á entidade de servizo.<!--note from editor: Using the note format is suggested, just so this doesn't get lost by being tucked up in the step.-->

### <a name="create-a-new-service-principal"></a>Crear unha entidade de seguranza do servizo nova
<!--note from editor: Some general formatting notes: The MWSG wants bold for text the user enters (in addition to UI strings and the settings users select), but there's plenty of precedent for using code format for entering text in PowerShell so I didn't change that. Note that italic should be used for placeholders, but not much else.-->
1. Instale a versión máis recente de Azure Active Directory PowerShell para Graph. Para obter máis información, vaia a [Instalar Azure Active Directory PowerShell para Graph](/powershell/azure/active-directory/install-adv2).

   1. No seu PC, seleccione a tecla Windows do teclado e busque **Windows PowerShell** e seleccione **Executar como administrador**.<!--note from editor: Or should this be something like "search for **Windows PowerShell** and, if asked, select **Run as administrator**."?-->
   
   1. Na xanela de PowerShell que se abre, introduza `Install-Module AzureAD`.

2. Cree a entidade de servizo para Customer Insights co módulo de Azure AD PowerShell.

   1. Na xanela de PowerShell que se abre, introduza `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`. Substitúa *[your tenant ID]*<!--note from editor: Edit okay? Or should the quotation marks stay in the command line, in which case it would be "Replace *[your tenant ID]* --> co ID real do arrendatario onde desexa crear a entidade de servizo. O parámetro de nome do ambiente, `AzureEnvironmentName`, é opcional.
  
   1. Introduza `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Este comando crea a entidade de seguranza do servizo para obter información sobre o público no inquilino seleccionado. 

   1. Introduza `New-AzureADServicePrincipal -AppId "ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd" -DisplayName "Dynamics 365 AI for Customer Insights engagement insights"`. Este comando crea a entidade de servizo da información de interacción<!--note from editor: Edit okay?--> no arrendatario seleccionado.

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

Pode<!--note from editor: Edit suggested only if this section is optional.--> anexar unha conta de Data Lake Storage na información do público para [almacenar datos de saída](manage-environments.md) ou [usala como orixe de datos](connect-common-data-service-lake.md). Esta opción permítelle escoller entre un enfoque baseado en recursos ou baseado en subscricións. Dependendo do enfoque que escolla, siga o procedemento nunha das seguintes seccións.<!--note from editor: Suggested.-->

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