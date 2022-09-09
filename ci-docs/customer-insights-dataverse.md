---
title: Traballar con datos de Customer Insights en Microsoft Dataverse
description: Aprende a conectar Customer Insights e Microsoft Dataverse e comprender as entidades de saída que se exportan a Dataverse.
ms.date: 08/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: dfa63110fc5291f2b63aebf588d6fdd20ed4ab67
ms.sourcegitcommit: 134aac66e3e0b77b2e96a595d6acbb91bf9afda2
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 09/07/2022
ms.locfileid: "9424307"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Traballar con datos de Customer Insights en Microsoft Dataverse

Customer Insights ofrece a opción de pór dispoñibles as entidades de saída en [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). Esta integración permite compartir datos sinxelos e desenvolvemento personalizado mediante un enfoque de código baixo/sen código. O [entidades de saída](#output-entities) están dispoñibles como táboas en a Dataverse ambiente. Podes usar os datos para calquera outra aplicación baseada en Dataverse táboas. Estas táboas permiten escenarios como fluxos de traballo automatizados Power Automate ou crear aplicacións con Power Apps.

Conectando ao teu Dataverse ambiente tamén che permite [inxerir datos de fontes de datos local usando Power Platform fluxos de datos e pasarelas](connect-power-query.md#add-data-from-on-premises-data-sources).

## <a name="prerequisites"></a>Requisitos previos

- Insights de clientes e Dataverse os ambientes deben estar aloxados na mesma rexión.
- Un rol de administrador global configurado en Dataverse ambiente. Comproba se isto [Dataverse ambiente está asociado](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) a determinados grupos de seguranza e asegúrate de que estás engadido a eses grupos de seguranza.
- Non hai outro ambiente de Customer Insights xa asociado co Dataverse ambiente que quere conectar. Aprende como [eliminar unha conexión existente a a Dataverse ambiente](#remove-an-existing-connection-to-a-dataverse-environment).
- A Microsoft Dataverse ambiente conectado a unha única conta de almacenamento se configura o ambiente para [usa o teu Azure Data Lake Storage](own-data-lake-storage.md).

## <a name="dataverse-storage-capacity-entitlement"></a>Dataverse dereito á capacidade de almacenamento

Unha subscrición a Customer Insights dálle dereito a unha capacidade adicional para a existente da túa organización [Dataverse capacidade de almacenamento](/power-platform/admin/capacity-storage). A capacidade engadida depende do número de perfís que utilice a súa subscrición.

**Exemplo:**

Asumindo que obtén 15 GB de almacenamento de base de datos e 20 GB de almacenamento de ficheiros por cada 100.000 perfís de clientes. Se a túa subscrición inclúe 300.000 perfís de clientes, a túa capacidade de almacenamento total é de 45 GB (3 x 15 GB) de almacenamento de bases de datos e 60 GB de almacenamento de ficheiros (3 x 20 GB). Do mesmo xeito, se tes unha subscrición B-to-B con 30K contas, a túa capacidade de almacenamento total é de 45 GB (3 x 15 GB) de almacenamento de bases de datos e 60 GB de almacenamento de ficheiros (3 x 20 GB).

A capacidade de rexistro non é incremental e fixa para a túa organización.

Para obter máis información sobre os dereitos de capacidade detallados, consulte [Guía de licenzas de Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

## <a name="connect-a-dataverse-environment-to-customer-insights"></a>Conectar a Dataverse ambiente para Customer Insights

O **Microsoft Dataverse** paso permíteche conectar Customer Insights co teu Dataverse ambiente mentres [creando un ambiente de Customer Insights](create-environment.md).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="compartición de datos con Microsoft Dataverse habilitado automaticamente para novos ambientes.":::

1. Proporcione o URL ao seu Dataverse ambiente ou déixao en branco para crear un para ti.

   > [!NOTE]
   > Despois de establecer a conexión entre Customer Insights e Dataverse, non cambies o nome da organización para o Dataverse ambiente. O nome da organización utilízase no Dataverse O URL e un nome modificado rompen a conexión con Customer Insights.

   [Power Platform os administradores poden controlar quen pode crear un novo Dataverse ambientes](/power-platform/admin/control-environment-creation). Se estás tentando configurar un novo ambiente de Customer Insights e non podes, é posible que o administrador teña desactivado a creación de Dataverse ambientes para todos, excepto para administradores.

1. Se estás a usar a túa propia conta de Data Lake Storage:
   1. Seleccione **Activa o uso compartido de datos** con Dataverse.
   1. Introduza o **Identificador de permisos**. Para obter o identificador do permiso, [habilitar a compartición de datos con Dataverse do teu propio Azure Data Lake Storage](#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview).

## <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Activa o uso compartido de datos con Dataverse do teu propio Azure Data Lake Storage (vista previa)

En [ti mesmo Azure Data Lake Storage conta](own-data-lake-storage.md), verifique que o usuario que configure o ambiente de Customer Insights teña polo menos **Lector de datos de Blob de almacenamento** permisos sobre`customerinsights` contedor na conta de almacenamento.

### <a name="limitations"></a>Limitacións

- Só mapeamento un a un entre a Dataverse organización e an Azure Data Lake Storage conta. Unha vez a Dataverse organización está conectada a unha conta de almacenamento, non pode conectarse a outra conta de almacenamento. Esta limitación impide Dataverse de encher varias contas de almacenamento.
- O uso compartido de datos non funcionará se se necesita unha configuración de Azure Private Link para acceder ao teu Azure Data Lake Storage conta porque está detrás dun firewall. Dataverse actualmente non admite a conexión a puntos finais privados mediante Private Link.

### <a name="set-up-security-groups-on-your-own-azure-data-lake-storage"></a>Configura grupos de seguridade pola túa conta Azure Data Lake Storage

1. Crea dous grupos de seguranza na túa subscrición de Azure: un **Lector** grupo de seguridade e un **Colaborador** grupo de seguridade e configure o Microsoft Dataverse servizo como propietario de ambos os grupos de seguridade.

1. Xestionar a lista de control de acceso (ACL) no`customerinsights` contenedor na túa conta de almacenamento a través destes grupos de seguranza.
   1. Engade o Microsoft Dataverse servizo e calquera Dataverse aplicacións empresariais baseadas en Dynamics 365 Marketing to the **Lector** grupo de seguridade con **só lectura** permisos.
   1. Engadir *só* a aplicación Customers Insights ao **Colaborador** grupo de seguridade para conceder ambos **Ler e escribir** permisos para escribir perfís e información.

### <a name="set-up-powershell"></a>Configura PowerShell

Configura PowerShell para executar scripts de PowerShell.

1. Instala a última versión de [Azure Active Directory PowerShell para Graph](/powershell/azure/active-directory/install-adv2).
   1. No seu PC, seleccione a tecla Windows do teclado e busque **Windows PowerShell** e seleccione **Executar como administrador**.
   1. Na xanela de PowerShell que se abre, introduza `Install-Module AzureAD`.

1. Importa tres módulos.
   1. Na xanela de PowerShell, introduza`Install-Module -Name Az.Accounts` e segue os pasos.
   1. Repita para`Install-Module -Name Az.Resources` e `Install-Module -Name Az.Storage`.

### <a name="execute-powershell-scripts-and-obtain-the-permission-identifier"></a>Executa scripts de PowerShell e obtén o identificador de permisos

1. Descarga os dous scripts de PowerShell que necesitas para executar desde o noso enxeñeiro [repositorio de GitHub](https://github.com/trin-msft/byol).
   - `CreateSecurityGroups.ps1`: Require permisos de administrador do inquilino.
   - `ByolSetup.ps1`: Require permisos de propietario de datos de blob de almacenamento a nivel de conta/contedor de almacenamento. Este script creará o permiso para ti. A túa asignación de funcións pódese eliminar manualmente despois de executar correctamente o script.

1. Executar`CreateSecurityGroups.ps1` en Windows PowerShell proporcionando o ID de subscrición de Azure que contén o seu Azure Data Lake Storage. Abra o script de PowerShell nun editor para revisar información adicional e a lóxica implementada.

   Este script crea dous grupos de seguranza na túa subscrición de Azure: un para o grupo de lectores e outro para o grupo de colaboradores. Microsoft Dataverse service é o propietario destes dous grupos de seguridade.

1. Garda os dous valores de ID de grupo de seguranza xerados por este script para utilizalos no`ByolSetup.ps1` guión.

   > [!NOTE]
   > A creación de grupos de seguranza pódese desactivar no teu inquilino. Nese caso, sería necesaria unha configuración manual e o seu Azure AD o administrador tería que facelo [habilitar a creación de grupos de seguridade](/azure/active-directory/enterprise-users/groups-self-service-management).

1. Executar`ByolSetup.ps1` en Windows PowerShell proporcionando o ID de subscrición de Azure que contén o seu Azure Data Lake Storage, o nome da conta de almacenamento, o nome do grupo de recursos e os valores de ID do grupo de seguranza do lector e do colaborador. Abra o script de PowerShell nun editor para revisar información adicional e a lóxica implementada.

   Este script engade o control de acceso baseado en roles necesario para o Microsoft Dataverse servizo e calquera Dataverse aplicacións empresariais baseadas. Tamén actualiza a Lista de control de acceso (ACL) no`customerinsights` contenedor para os grupos de seguridade creados co`CreateSecurityGroups.ps1` guión. Ofrécese o grupo de colaboradores *rwx* se dá permiso e o grupo de lectores *rx* só permiso.

1. Copia a cadea de saída que parece:`https://DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`

1. Introduza a cadea de saída copiada no ficheiro **Identificador de permisos** campo do paso de configuración do entorno para Microsoft Dataverse.

   :::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Opcións de configuración para activar a compartición de datos dende o teu Azure Data Lake Storage con Microsoft Dataverse .":::

## <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>Eliminar unha conexión existente a un Dataverse ambiente

Ao conectarse a un Dataverse ambiente, a mensaxe de erro **Esta organización de CDS xa está asociada a outra instancia de Customer Insights** significa que o Dataverse o ambiente xa se usa nun ambiente de Customer Insights. Pode eliminar a conexión existente como administrador global no Dataverse ambiente. Pode tardar un par de horas en completar os cambios.

1. Vaia a [Power Apps](https://make.powerapps.com).
1. Seleccione o ambiente no selector de ambiente.
1. Ir a **Solucións**.
1. Desinstale ou elimine a solución nomeada **Dynamics 365 Customer Insights Complemento da tarxeta de cliente (vista previa)**.

ou

1. Abre o teu Dataverse ambiente.
1. Ir a **Configuración avanzada** > **Solucións**.
1. Desinstalar o **CustomerInsightsCustomerCard** solución.

Se a eliminación da conexión falla debido a dependencias, tamén debes eliminar as dependencias. Para obter máis información, consulte [Eliminación de dependencias](/power-platform/alm/removing-dependencies).

## <a name="output-entities"></a>Entidades de saída

Algunhas entidades de saída de Customer Insights están dispoñibles como táboas Dataverse. As seccións seguintes describen o esquema esperado destas táboas.

- [CustomerProfile](#customerprofile)
- [ContactProfile](#contactprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Enriquecemento](#enrichment)
- [Predición](#prediction)
- [Segmento de pertenza](#segment-membership)

### <a name="customerprofile"></a>CustomerProfile

Esta táboa contén o perfil de cliente unificado de Customer Insights. O esquema para un perfil de cliente unificado depende das entidades e atributos utilizados no proceso de unificación de datos. Un esquema de perfil de cliente normalmente contén un subconxunto dos atributos da [definición de Common Data Model de CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile). Para o escenario B-to-B, o perfil do cliente contén contas unificadas e o esquema adoita conter un subconxunto dos atributos do [Definición do modelo de datos común da conta](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/account).

### <a name="contactprofile"></a>ContactProfile

Un ContactProfile contén información unificada sobre un contacto. Os contactos son [individuos que están asignados a unha conta](data-unification-contacts.md) nun escenario B-to-B.

| Column                       | Tipo                | Descripción     |
| ---------------------------- | ------------------- | --------------- |
|  Data de nacemento            | DataHora       |  Data de nacemento do contacto               |
|  Localidade                 | Mensaxe de texto |  Cidade do enderezo de contacto               |
|  ContactId            | Mensaxe de texto |  ID do perfil de contacto               |
|  ContactProfileId     | Identificador único   |  GUID para o contacto               |
|  País ou rexión      | Mensaxe de texto |  País/rexión do enderezo de contacto               |
|  CustomerId           | Mensaxe de texto |  ID da conta á que está asignado o contacto               |
|  EntityName           | Mensaxe de texto |  Entidade da que proceden os datos                |
|  FirstName            | Mensaxe de texto |  Nome do contacto               |
|  Sexo               | Mensaxe de texto |  Xénero do contacto               |
|  ID                   | Mensaxe de texto |  GUID determinista baseado en`Identifier`               |
|  Identificador           | Mensaxe de texto |  ID interno do perfil de contacto:`ContactProfile|CustomerId|ContactId`               |
|  JobTitle             | Mensaxe de texto |  Denominación do traballo do contacto               |
|  LastName             | Mensaxe de texto |  Apelidos do contacto               |
|  PostalCode           | Mensaxe de texto |  Código postal do enderezo de contacto               |
|  Correo electrónico principal         | Mensaxe de texto |  Enderezo de correo electrónico do contacto               |
|  Teléfono principal         | Mensaxe de texto |  Número de teléfono do contacto               |
|  Estado ou provincia      | Mensaxe de texto |  Estado ou provincia do enderezo de contacto               |
|  Enderezo        | Mensaxe de texto |  Rúa do enderezo de contacto               |

### <a name="alternatekey"></a>AlternateKey

A táboa AlternateKey contén as claves das entidades que participaron no proceso de unificación.

|Column  |Tipo  |Descripción  |
|---------|---------|---------|
|DataSourceName    |Mensaxe de texto         | Nome da orixe de datos. Por exemplo: `datasource5`        |
|EntityName        | Mensaxe de texto        | Nome da entidade en Customer Insights. Por exemplo: `contact1`        |
|AlternateValue    |Mensaxe de texto         |ID alternativo que está asignado ao ID de cliente. Exemplo: `cntid_1078`         |
|KeyRing           | Mensaxe de texto        | Valor JSON  </br> Exemplo: [{"dataSourceName":" datasource5 ",</br>"entityName":" contact1",</br>"preferredKey":" cntid_1078",</br>"keys":[" cntid_1078"]}]       |
|CustomerId         | Mensaxe de texto        | ID do perfil de cliente unificado.         |
|AlternateKeyId     | Identificador único        |  GUID determinístico de AlternateKey baseado en`Identifier`      |
|Identificador |   Mensaxe de texto      |   `DataSourceName|EntityName|AlternateValue`  </br> Exemplo: `testdatasource|contact1|cntid_1078`    |

### <a name="unifiedactivity"></a>UnifiedActivity

Esta táboa contén actividades dos usuarios dispoñibles en Customer Insights.

| Column            | Tipo        | Descripción                                                                              |
|-------------------|-------------|------------------------------------------------------------------------------------------|
| CustomerId        | Mensaxe de texto      | ID do perfil do cliente                                                                      |
| ActivityId        | Mensaxe de texto      | ID interno da actividade do cliente (clave principal)                                       |
| SourceEntityName  | Mensaxe de texto      | Nome da entidade de orixe                                                                |
| SourceActivityId  | Mensaxe de texto      | Clave principal da entidade de orixe                                                       |
| ActivityType      | Mensaxe de texto      | Tipo de actividade semántica ou nome da actividade personalizada                                        |
| ActivityTimeStamp | DataHora    | Selo de tempo da actividade                                                                      |
| Cargo             | Mensaxe de texto      | Título ou nome da actividade                                                               |
| Descripción       | Mensaxe de texto      | Descrición da actividade                                                                     |
| Enderezo URL               | Mensaxe de texto      | Ligazón a un URL externo específico da actividade                                         |
| SemanticData      | Mensaxe de texto | Inclúe unha lista de pares clave-valor para campos de asignación semántica específicos do tipo de actividade |
| RangeIndex        | Mensaxe de texto      | Marca de hora de Unix empregada para ordenar a liña de tempo da actividade e as consultas de alcance efectivas |
| UnifiedActivityId   | Identificador único | ID interno da actividade do cliente (ActivityId) |

### <a name="customermeasure"></a>CustomerMeasure

Esta táboa contén os datos de saída das medidas baseadas en atributos do cliente.

| Column             | Tipo             | Descripción                 |
|--------------------|------------------|-----------------------------|
| CustomerId         | Mensaxe de texto           | ID do perfil do cliente        |
| Medidas           | Mensaxe de texto      | Inclúe unha lista de pares clave-valor para o nome e os valores da medida para o cliente indicado |
| Identificador | Mensaxe de texto           | `Customer_Measure|CustomerId` |
| CustomerMeasureId | Identificador único     | ID do perfil do cliente |

### <a name="enrichment"></a>Enriquecemento

Esta táboa contén a saída do proceso de enriquecemento.

| Column               | Tipo             |  Descripción                                          |
|----------------------|------------------|------------------------------------------------------|
| CustomerId           | Mensaxe de texto           | ID do perfil do cliente                                 |
| EnrichmentProvider   | Mensaxe de texto           | Nome do fornecedor do enriquecemento                                  |
| EnrichmentType       | Mensaxe de texto           | Tipo de enriquecemento                                      |
| Valores               | Mensaxe de texto      | Lista de atributos producidos polo proceso de enriquecemento |
| EnriquecementoId | Identificador único            | GUID determinista xerado a partir de`Identifier` |
| Identificador   | Mensaxe de texto           | `EnrichmentProvider|EnrichmentType|CustomerId`         |

### <a name="prediction"></a>Predición

Esta táboa contén a saída das predicións do modelo.

| Column               | Tipo        | Descripción                                          |
|----------------------|-------------|------------------------------------------------------|
| CustomerId           | Mensaxe de texto      | ID do perfil do cliente                                  |
| ModelProvider        | Mensaxe de texto      | Nome do fornecedor do modelo                                      |
| Modelo                | Mensaxe de texto      | Nome do modelo                                                |
| Valores               | Mensaxe de texto | Lista de atributos producidos polo modelo |
| Id de predición | Identificador único       | GUID determinista xerado a partir de`Identifier` |
| Identificador   | Mensaxe de texto      |  `Model|ModelProvider|CustomerId`                      |

### <a name="segment-membership"></a>Segmento de pertenza

Esta táboa contén información sobre a pertenza ao segmento dos perfís de clientes.

| Column        | Tipo | Descripción                        |
|--------------------|--------------|-----------------------------|
| CustomerId        | Mensaxe de texto       | ID do perfil do cliente        |
| SegmentProvider      | Mensaxe de texto       | Aplicación que publica os segmentos.      |
| SegmentMembershipType | Mensaxe de texto       | Tipo de cliente para o rexistro de pertenza a este segmento. Admite varios tipos, como Cliente, Contacto ou Conta. Valor predeterminado: cliente  |
| Segmentos       | Mensaxe de texto  | Lista de segmentos únicos dos que é membro o perfil do cliente      |
| Identificador  | Mensaxe de texto   | Identificador único do rexistro de pertenza ao segmento. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| Segment MembershipId | Identificador único      | GUID determinista xerado a partir de`Identifier`          |

[!INCLUDE [footer-include](includes/footer-banner.md)]
