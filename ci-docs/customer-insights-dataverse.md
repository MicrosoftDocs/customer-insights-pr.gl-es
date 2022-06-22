---
title: Traballar con datos de Customer Insights en Microsoft Dataverse
description: Aprende a conectar Customer Insights e Microsoft Dataverse e comprender as entidades de saída que se exportan a Dataverse.
ms.date: 05/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 252723b8c174cb1ec488388c26fd2a1d398e9002
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011518"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Traballar con datos de Customer Insights en Microsoft Dataverse

Customer Insights ofrece a opción de facer as entidades de saída dispoñibles como [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). Esta integración permite compartir datos sinxelos e desenvolvemento personalizado a través dun enfoque de código baixo/sen código. O [entidades de saída](#output-entities) están dispoñibles como táboas en a Dataverse ambiente. Podes usar os datos para calquera outra aplicación baseada en Dataverse táboas. Estas táboas permiten escenarios como fluxos de traballo automatizados Power Automate ou crear aplicacións con Power Apps.

Conectando ao teu Dataverse ambiente tamén che permite [inxerir datos de fontes de datos local usando Power Platform fluxos de datos e pasarelas](connect-power-query.md#add-data-from-on-premises-data-sources).

## <a name="prerequisites"></a>Requisitos previos

- Información do cliente e Dataverse os ambientes deben estar aloxados na mesma rexión.
- Debes ter un rol de administrador global no Dataverse ambiente. Comproba se isto [Dataverse ambiente está asociado](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) a determinados grupos de seguranza e asegúrate de que estás engadido a eses grupos de seguranza.
- Ningún outro ambiente de Customer Insights xa está asociado co Dataverse ambiente que quere conectar. Aprende como [eliminar unha conexión existente a a Dataverse ambiente](#remove-an-existing-connection-to-a-dataverse-environment).
- A Microsoft Dataverse O ambiente só pode conectarse a unha única conta de almacenamento. Aplícase só se configura o ambiente para [usa o teu Azure Data Lake Storage](own-data-lake-storage.md).

## <a name="connect-a-dataverse-environment-to-customer-insights"></a>Conectar a Dataverse ambiente para Customer Insights

O **Microsoft Dataverse** paso permíteche conectar Customer Insights co teu Dataverse ambiente mentres [creando un ambiente de Customer Insights](create-environment.md).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="compartición de datos con Microsoft Dataverse habilitado automaticamente para novos entornos nets.":::

Os administradores poden configurar Customer Insights para conectar un existente Dataverse ambiente. Ao proporcionar o URL ao Dataverse ambiente, está unido ao seu novo ambiente de Customer Insights.

Se non queres utilizar un existente Dataverse ambiente, o sistema crea un novo ambiente para os datos de Customer Insights no seu inquilino. [Power Platform os administradores poden controlar quen pode crear ambientes](/power-platform/admin/control-environment-creation). Cando está a configurar un novo ambiente de Customer Insights e o administrador desactivou a creación de Dataverse ambientes para todos, excepto os administradores, é posible que non poidas crear un novo ambiente.

**Activa o uso compartido de datos** con Dataverse seleccionando a caixa de verificación para compartir datos.

Se estás a usar a túa propia conta de Data Lake Storage, tamén necesitas o **Identificador de permisos**. Para obter máis información sobre como obter o identificador de permisos, consulte a seguinte sección.

## <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Activa o uso compartido de datos con Dataverse do teu propio Azure Data Lake Storage (Vista previa)

Activando o uso compartido de datos con Microsoft Dataverse cando o teu ambiente [utiliza o seu propio Azure Data Lake Storage conta](own-data-lake-storage.md) precisa algunha configuración adicional. O usuario que configura o ambiente de Customer Insights debe ter polo menos **Lector de datos de Blob de almacenamento** permisos no *CustomerInsights* recipiente no Azure Data Lake Storage conta.

1. Crea dous grupos de seguranza na túa subscrición de Azure: un **Lector** grupo de seguridade e un **Colaborador** grupo de seguridade e configure o Microsoft Dataverse servizo como propietario de ambos os grupos de seguridade.
2. Xestiona a Lista de control de acceso (ACL) no contedor CustomerInsights da túa conta de almacenamento a través destes grupos de seguranza. Engade o Microsoft Dataverse servizo e calquera Dataverse aplicacións empresariais baseadas en Dynamics 365 Marketing to the **Lector** grupo de seguridade con **só lectura** permisos. Engadir *só* a aplicación Customers Insights ao **Colaborador** grupo de seguridade para conceder ambos **Ler e escribir** permisos para escribir perfís e información.

### <a name="limitations"></a>Limitacións

Hai dúas limitacións ao usar Dataverse co teu propio Azure Data Lake Storage conta:

- Hai un mapeo un a un entre a Dataverse organización e an Azure Data Lake Storage conta. Unha vez a Dataverse organización está conectada a unha conta de almacenamento, non pode conectarse a outra conta de almacenamento. Esta limitación impide que a Dataverse non enche varias contas de almacenamento.
- O uso compartido de datos non funcionará se se necesita unha configuración de Azure Private Link para acceder ao teu Azure Data Lake Storage conta porque está detrás dun firewall. Dataverse actualmente non admite a conexión a puntos finais privados mediante Private Link.

### <a name="set-up-powershell"></a>Configura PowerShell

Para executar os scripts de PowerShell, primeiro debes configurar PowerShell en consecuencia.

1. Instala a última versión de [Azure Active Directory PowerShell para Graph](/powershell/azure/active-directory/install-adv2).
   1. No seu PC, seleccione a tecla Windows do teclado e busque **Windows PowerShell** e seleccione **Executar como administrador**.
   1. Na xanela de PowerShell que se abre, introduza `Install-Module AzureAD`.
2. Importar tres módulos.
    1. Na xanela de PowerShell, introduza`Install-Module -Name Az.Accounts` e segue os pasos.
    1. Repita para`Install-Module -Name Az.Resources` e `Install-Module -Name Az.Storage`.

### <a name="configuration-steps"></a>Pasos de configuración

1. Descarga os dous scripts de PowerShell que necesitas para executar desde o noso enxeñeiro [repositorio de GitHub](https://github.com/trin-msft/byol).
    1. `CreateSecurityGroups.ps1`
       - Precisas *administrador inquilino* permisos para executar este script de PowerShell.
       - Este script de PowerShell crea dous grupos de seguranza na túa subscrición de Azure. Un para o grupo Lector e outro para o grupo Colaborador e fará Microsoft Dataverse servizo como propietario destes dous grupos de seguridade.
       - Executa este script de PowerShell en Windows PowerShell proporcionando o ID de subscrición de Azure que contén o teu Azure Data Lake Storage. Abra o script de PowerShell nun editor para revisar información adicional e a lóxica implementada.
       - Garda os dous valores de ID de grupo de seguranza xerados por este script porque os usaremos no`ByolSetup.ps1` guión.

        > [!NOTE]
        > A creación de grupos de seguranza pódese desactivar no teu inquilino. Nese caso, sería necesaria unha configuración manual e o seu Azure AD o administrador tería que facelo [habilitar a creación de grupos de seguridade](/azure/active-directory/enterprise-users/groups-self-service-management).

    2. `ByolSetup.ps1`
        - Precisas *Propietario de datos do blob de almacenamento* permisos a nivel de conta de almacenamento/contedor para executar este script ou este script creará un para ti. A túa asignación de funcións pódese eliminar manualmente despois de executar correctamente o script.
        - Este script de PowerShell engade o control de acceso baseado en tole (RBAC) necesario para o Microsoft Dataverse servizo e calquera Dataverse aplicacións empresariais baseadas. Tamén actualiza a Lista de control de acceso (ACL) no contedor CustomerInsights para os grupos de seguranza creados co`CreateSecurityGroups.ps1` guión. O grupo Colaborador terá *rwx* permiso e o grupo Lectores terá *rx* só permiso.
        - Executa este script de PowerShell en Windows PowerShell proporcionando o ID de subscrición de Azure que contén o teu Azure Data Lake Storage, o nome da conta de almacenamento, o nome do grupo de recursos e os valores de ID do grupo de seguranza do lector e do colaborador. Abra o script de PowerShell nun editor para revisar información adicional e a lóxica implementada.
        - Copia a cadea de saída despois de executar correctamente o script. A cadea de saída ten o seguinte aspecto:`https://DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`

2. Introduza a cadea de saída copiada desde arriba no ficheiro **Identificador de permisos** campo do paso de configuración do entorno para Microsoft Dataverse.

:::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Opcións de configuración para activar a compartición de datos dende o teu Azure Data Lake Storage con Microsoft Dataverse .":::

### <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>Eliminar unha conexión existente a un Dataverse ambiente

Ao conectarse a un Dataverse ambiente, a mensaxe de erro **Esta organización de CDS xa está asociada a outra instancia de Customer Insights** significa que o Dataverse o ambiente xa se usa nun ambiente de Customer Insights. Pode eliminar a conexión existente como administrador global no Dataverse ambiente. Pode tardar un par de horas en completar os cambios.

1. Vaia a [Power Apps](https://make.powerapps.com).
1. Seleccione o ambiente no selector de ambiente.
1. Ir a **Solucións**
1. Desinstale ou elimine a solución nomeada **Dynamics 365 Customer Insights Complemento da tarxeta de cliente (vista previa)**.

ou

1. Abre o teu Dataverse ambiente.
1. Ir a **Configuración avanzada** > **Solucións**.
1. Desinstale o **CustomerInsightsCustomerCard** solución.

Se a eliminación da conexión falla debido a dependencias, tamén debes eliminar as dependencias. Para obter máis información, consulte [Eliminación de dependencias](/power-platform/alm/removing-dependencies).

## <a name="output-entities"></a>Entidades de saída

Algunhas entidades de saída de Customer Insights están dispoñibles como táboas Dataverse. As seccións seguintes describen o esquema esperado destas táboas.

- [CustomerProfile](#customerprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Enriquecemento](#enrichment)
- [Predición](#prediction)
- [Segmento de pertenza](#segment-membership)

### <a name="customerprofile"></a>CustomerProfile

Esta táboa contén o perfil de cliente unificado de Customer Insights. O esquema para un perfil de cliente unificado depende das entidades e atributos utilizados no proceso de unificación de datos. Un esquema de perfil de cliente normalmente contén un subconxunto dos atributos da [definición de Common Data Model de CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile).

### <a name="alternatekey"></a>AlternateKey

A táboa AlternateKey contén as claves das entidades que participaron no proceso de unificación.

|Column  |Tipo  |Descripción  |
|---------|---------|---------|
|DataSourceName    |String         | Nome da orixe de datos. Por exemplo: `datasource5`        |
|EntityName        | String        | Nome da entidade en Customer Insights. Por exemplo: `contact1`        |
|AlternateValue    |String         |ID alternativo que está asignado ao ID de cliente. Exemplo: `cntid_1078`         |
|KeyRing           | Texto de varias liñas        | Valor JSON  </br> Exemplo: [{"dataSourceName":" datasource5 ",</br>"entityName":" contact1",</br>"preferredKey":" cntid_1078",</br>"keys":[" cntid_1078"]}]       |
|CustomerId         | String        | ID do perfil de cliente unificado.         |
|AlternateKeyId     | GUID         |  GUID determinista de AlternateKey baseado en msdynci_identifier       |
|msdynci_identifier |   String      |   `DataSourceName|EntityName|AlternateValue`  </br> Exemplo: `testdatasource|contact1|cntid_1078`    |

### <a name="unifiedactivity"></a>UnifiedActivity

Esta táboa contén actividades dos usuarios dispoñibles en Customer Insights.

| Column            | Tipo        | Descripción                                                                              |
|-------------------|-------------|------------------------------------------------------------------------------------------|
| CustomerId        | String      | ID do perfil do cliente                                                                      |
| ActivityId        | String      | ID interno da actividade do cliente (clave principal)                                       |
| SourceEntityName  | String      | Nome da entidade de orixe                                                                |
| SourceActivityId  | String      | Clave principal da entidade de orixe                                                       |
| ActivityType      | String      | Tipo de actividade semántica ou nome da actividade personalizada                                        |
| ActivityTimeStamp | DATAHORA    | Marca de hora da actividade                                                                      |
| Título             | String      | Título ou nome da actividade                                                               |
| Descripción       | String      | Descrición da actividade                                                                     |
| Enderezo URL               | String      | Ligazón a un URL externo específico da actividade                                         |
| SemanticData      | Cadea JSON | Inclúe unha lista de pares clave-valor para campos de asignación semántica específicos do tipo de actividade |
| RangeIndex        | String      | Marca de hora de Unix empregada para ordenar a liña de tempo da actividade e as consultas de alcance efectivas |
| mydynci_unifiedactivityid   | GUID | ID interno da actividade do cliente (ActivityId) |

### <a name="customermeasure"></a>CustomerMeasure

Esta táboa contén os datos de saída das medidas baseadas en atributos do cliente.

| Column             | Tipo             | Descripción                 |
|--------------------|------------------|-----------------------------|
| CustomerId         | String           | ID do perfil do cliente        |
| Medidas           | Cadea JSON      | Inclúe unha lista de pares clave-valor para o nome e os valores da medida para o cliente indicado | 
| msdynci_identifier | String           | `Customer_Measure|CustomerId` |
| msdynci_customermeasureid | GUID      | ID do perfil do cliente |


### <a name="enrichment"></a>Enriquecemento

Esta táboa contén a saída do proceso de enriquecemento.

| Column               | Tipo             |  Descripción                                          |
|----------------------|------------------|------------------------------------------------------|
| CustomerId           | String           | ID do perfil do cliente                                 |
| EnrichmentProvider   | String           | Nome do fornecedor do enriquecemento                                  |
| EnrichmentType       | String           | Tipo de enriquecemento                                      |
| Valores               | Cadea JSON      | Lista de atributos producidos polo proceso de enriquecemento |
| msdynci_enrichmentid | GUID             | GUID determinista xerado a partir de msdynci_identifier |
| msdynci_identifier   | String           | `EnrichmentProvider|EnrichmentType|CustomerId`         |

### <a name="prediction"></a>Predición

Esta táboa contén a saída das predicións do modelo.

| Column               | Tipo        | Descripción                                          |
|----------------------|-------------|------------------------------------------------------|
| CustomerId           | String      | ID do perfil do cliente                                  |
| ModelProvider        | String      | Nome do fornecedor do modelo                                      |
| Modelo                | String      | Nome do modelo                                                |
| Valores               | Cadea JSON | Lista de atributos producidos polo modelo |
| msdynci_predictionid | GUID        | GUID determinista xerado a partir de msdynci_identifier | 
| msdynci_identifier   | String      |  `Model|ModelProvider|CustomerId`                      |

### <a name="segment-membership"></a>Segmento de pertenza

Esta táboa contén información sobre a pertenza ao segmento dos perfís de clientes.

| Column        | Tipo | Descripción                        |
|--------------------|--------------|-----------------------------|
| CustomerId        | String       | ID do perfil do cliente        |
| SegmentProvider      | String       | Aplicación que publica os segmentos.      |
| SegmentMembershipType | String       | Tipo de cliente deste segmento rexistro de pertenza. Admite varios tipos, como Cliente, Contacto ou Conta. Valor predeterminado: cliente  |
| Segmentos       | Cadea JSON  | Lista de segmentos únicos dos que é membro o perfil do cliente      |
| msdynci_identifier  | String   | Identificador único do rexistro de pertenza ao segmento. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| msdynci_segmentmembershipid | GUID      | GUID determinista xerado a partir de`msdynci_identifier`          |

<!--
## FAQ: Update existing environments to use Microsoft Dataverse

Between mid-May 2022 and June 13, 2022, administrators can update the environment settings with a Dataverse environment that Customer Insights can use. On June 13, 2022, your environment will be updated automatically and we'll create a Dataverse environment on your tenant for you.

1. My environment uses my own Azure Data Lake Storage account. Do I still need to update?

   If there's already a Dataverse environment configured in your environment, the update isn't required. If no Dataverse is environment configured, the **Update now** button will create a Dataverse environment and update from the Customer Insights database to a Dataverse database.

1. Will we get extra Dataverse capacity, or will the update use my existing Dataverse capacity?

   - If there's already a Dataverse environment configured in your Customer Insights environment, or connected with other Dynamics 365 or Power Apps applications, the capacity remains unchanged.
   - If the Dataverse environment is new, it will add new storage and database capacity. The capacity added varies per environment and entitlements. You'll get 3 GB for trial and sandbox environment. Production environments get 15 GB.

1. I proceeded with the update and it seems like nothing happened. Is the update complete?

   If the notification in Customer Insights doesn't show anymore, the update is complete. You can check the status of the update by reviewing your environment settings.

1. Why do I still see the banner after completing the update steps?

   It can happen due to an upgrade or refresh failure. Contact support.

1. I received a "Failed to provision Dataverse environment" error after starting the update. What happened?

   It can happen due to an upgrade or refresh failure. Contact support.
   Common causes:
    - Insufficient capacity. There's no more capacity to create more environments. For more information, see [Manage capacity action](/power-platform/admin/capacity-storage#actions-to-take-for-a-storage-capacity-deficit).
    - Region mismatch between tenant region and Customer Insights environment region in the Australia and India regions.
    - Insufficient privileges to provision Dataverse. The users starting the update needs a Dynamics 365 admin role.
    - -->
