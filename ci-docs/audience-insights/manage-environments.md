---
title: Crear e xestionar ambientes
description: Aprenda a rexistrarse no servizo e a xestionar contornos.
ms.date: 03/28/2022
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: adkuppa
ms.author: adkuppa
manager: shellyha
searchScope:
- ci-system-about
- customerInsights
ms.openlocfilehash: ba29bcd173e615e544bd10e69043f310c009eb47
ms.sourcegitcommit: ae02ac950810242e2505d7d371b80210dc8a0777
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 03/29/2022
ms.locfileid: "8491996"
---
# <a name="manage-environments"></a>Xestionar ambientes

## <a name="switch-environments"></a>Cambiar ambientes

Seleccione o control **Ambiente** na esquina superior dereita da páxina para cambiar ambientes.

:::image type="content" source="media/home-page-environment-switcher.png" alt-text="Captura de pantalla do control para cambiar de ambiente.":::

Os administradores poden [crear](create-environment.md) e xestionar ambientes.

## <a name="edit-an-existing-environment"></a>Editar un ambiente existente

Pode editar algúns detalles dos contornos existentes.

1.  Seleccione o selector de **ambiente** na cabeceira da aplicación.

2.  Seleccione a icona de **edición**.

3. Na caixa **Editar contorno**, pode actualizar a configuración do contorno.

Para obter máis información sobre a configuración do contorno, consulte [Crear un novo contorno](create-environment.md).

## <a name="connect-to-microsoft-dataverse"></a>Conectar con Microsoft Dataverse
   
O paso **Microsoft Dataverse** permítelle conectar Customer Insights co seu ambiente de Dataverse. 

Proporciona o teu propio Microsoft Dataverse ambiente para compartir datos (perfís e coñecementos) con aplicacións empresariais baseadas Dataverse, como Dynamics 365 Marketing ou aplicacións baseadas en modelos en Power Apps.

Para usar [modelos de predición listos para usar](predictions-overview.md#out-of-box-models), configure o uso compartido de datos con Dataverse. Ou pode activar a inxestión de datos desde orixes de datos locais, proporcionando o URL do contorno de Microsoft Dataverse que administra a súa organización.

Activando o uso compartido de datos con Microsoft Dataverse ao seleccionar a caixa de verificación para compartir datos, activarase unha actualización completa das súas fontes de datos e de todos os demais procesos.

> [!IMPORTANT]
> 1. Información do cliente e Dataverse deben estar na mesma rexión para poder compartir datos.
> 1. Debes ter un rol de administrador global no Dataverse ambiente. Comproba se isto [Dataverse ambiente está asociado](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) a determinados grupos de seguranza e asegúrese de que se engade a eses grupos de seguranza.
> 1. Xa non hai ningún ambiente de Customer Insights asociado con iso Dataverse ambiente. Aprende como [eliminar unha conexión existente a a Dataverse ambiente](#remove-an-existing-connection-to-a-dataverse-environment).

:::image type="content" source="media/dataverse-enable-datasharing.png" alt-text="Opcións de configuración para habilitar o uso compartido de datos con Microsoft Dataverse.":::

### <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Activa o uso compartido de datos con Dataverse do teu propio Azure Data Lake Storage (Vista previa)

Se o teu ambiente está configurado para usar o teu Azure Data Lake Storage para almacenar datos de Customer Insights, permitindo compartir datos Microsoft Dataverse precisa algunha configuración adicional.

1. Crea dous grupos de seguranza na túa subscrición de Azure: un **Lector** grupo de seguridade e un **Colaborador** grupo de seguridade e configure o Microsoft Dataverse servizo como propietario de ambos os grupos de seguridade.
2. Xestiona a Lista de control de acceso (ACL) no contedor CustomerInsights da túa conta de almacenamento a través destes grupos de seguranza. Engade o Microsoft Dataverse servizo e calquera Dataverse aplicacións empresariais baseadas en Dynamics 365 Marketing to the **Lector** grupo de seguridade con **só lectura** permisos. Engadir *só* a aplicación Customers Insights ao **Colaborador** grupo de seguridade para conceder ambos **Ler e escribir** permisos para escribir perfís e información.
   
#### <a name="prerequisites"></a>Requisitos previos

Para executar os scripts de PowerShell cómpre ter os seguintes tres módulos importados. 

1. Instala a última versión de [Azure Active Directory PowerShell para Graph](/powershell/azure/active-directory/install-adv2).
   1. No seu PC, seleccione a tecla Windows do teclado e busque **Windows PowerShell** e seleccione **Executar como administrador**.
   1. Na xanela de PowerShell que se abre, introduza `Install-Module AzureAD`.
2. Importar tres módulos.
    1. Na xanela de PowerShell, introduza`Install-Module -Name Az.Accounts` e segue os pasos. 
    1. Repita para`Install-Module -Name Az.Resources` e `Install-Module -Name Az.Storage`.

#### <a name="configuration-steps"></a>Pasos de configuración

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
        - Copia a cadea de saída despois de executar correctamente o script. A cadea de saída ten o seguinte aspecto:`https: //DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`
        
2. Introduza a cadea de saída copiada desde arriba no ficheiro **Identificador de permisos** campo do paso de configuración do entorno para Microsoft Dataverse.

:::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Opcións de configuración para activar a compartición de datos dende o teu Azure Data Lake Storage con Microsoft Dataverse .":::

Customer Insights non é compatible cos seguintes escenarios de uso compartido dos datos:
- Se activa o uso compartido de datos con Dataverse, non poderá [crear valores preditos ou que faltan nunha entidade](predictions.md).
- Se activas a compartición de datos con Dataverse, non poderás ver ningún informe opcional de PowerBI Embedded no teu ambiente de Customer Insights.

### <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>Eliminar unha conexión existente a a Dataverse ambiente

Ao conectarse a un Dataverse ambiente, a mensaxe de erro **Esta organización de CDS xa está asociada a outra instancia de Customer Insights** significa que o Dataverse o ambiente xa se usa nun ambiente de Customer Insights. Pode eliminar a conexión existente como administrador global no Dataverse ambiente. Pode tardar un par de horas en completar os cambios.

1. Vaia a [Power Apps](https://make.powerapps.com).
1. Seleccione o ambiente no selector de ambiente.
1. Ir a **Solucións**
1. Desinstale ou elimine a solución nomeada **Dynamics 365 Customer Insights Complemento da tarxeta de cliente (vista previa)**.

ou 

1. Abre o teu Dataverse ambiente.
1. Ir a **Configuración avanzada** > **Solucións**.
1. Desinstale o **CustomerInsightsCustomerCard** solución.

## <a name="copy-the-environment-configuration"></a>Copiar a configuración dun ambiente

Como administrador, pode escoller copiar a configuración dun ambiente existente cando cree un novo. 

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Captura de pantalla das opcións de configuración na configuración do ambiente.":::

Verá unha lista de todos os ambientes dispoñibles da súa organización de onde pode copiar datos.

Copiaranse os seguintes axustes de configuración:

- Fontes de datos inxeridas ou importadas
- Configuración da unificación de datos (mapa, coincidencia, combinación)
- Segmentos
- Medidas
- Relacións
- Actividades
- Buscar e filtrar índice
- Exportar destinos
- Actualización programada
- Enriquecementos
- Xestión de modelos
- Atribución de roles

## <a name="set-up-a-copied-environment"></a>Configura un ambiente copiado

Cando copia a configuración do ambiente, os seguintes datos son *non* copiado:

- Perfís de clientes.
- Credenciais da orixe de datos. Deberá proporcionar as credenciais para cada orixe de datos e actualizar as fontes de datos manualmente.
- Fontes de datos do cartafol de Common Data Model e o lago de datos xestionado de Dataverse. Terá que crear esas orixes de datos manualmente co mesmo nome que no ambiente de orixe.
- Segredos de conexión que se utilizan para exportacións e enriquecementos. Ten que reautenticar as conexións e despois reactivar os enriquecementos e as exportacións. 

Cando copie un ambiente, verá unha mensaxe de confirmación de que se creou o novo contorno. Seleccione **Ir a orixes de datos** para ver a lista de orixes de datos.

Todas as orixes de datos mostrarán o estado **Credenciais requiridas**. Edite as orixes de datos e insira as credenciais para actualizalas.

:::image type="content" source="media/data-sources-copied.png" alt-text="Lista de orixes de datos que se copiaron e precisan autenticación.":::

Despois de actualizar as orixes de datos, diríxase a **Datos** > **Unificar**. Aquí atopará a configuración do ambiente de orixe. Edíteos segundo sexa necesario ou seleccione **Executar** para iniciar o proceso de unificación de datos e crear a entidade de cliente unificada.

Cando a unificación de datos estea completa, diríxase a **Medidas** e **Segmentos** para actualizalos tamén.

Antes de reactivar as exportacións e os enriquecementos, vai a **Admin** > **Conexións** para volver a autenticar as conexións no seu novo entorno.

## <a name="change-the-owner-of-an-environment"></a>Cambiar o propietario dun ambiente

Aínda que varios usuarios poden ter permisos de administrador en Customer Insights, só un usuario é o propietario dun ambiente. Por defecto, é o administrador quen crea un ambiente inicialmente. Como administrador dun ambiente, pode asignarlle a propiedade a outro usuario con permisos de administrador.

1. Seleccione o selector de **ambiente** na cabeceira da aplicación.

1. Seleccione a icona de **edición**.

1. No **Editar entorno** caixa, vai ao **Información básica** paso.

1. No **Cambiar propietario do entorno** campo, escolla o novo propietario do entorno.  

1. Seleccione **Revisa e remata**, entón **Actualizar** para aplicar os cambios. 

## <a name="claim-ownership-of-an-environment"></a>Reivindicar a propiedade dun contorno

Se o propietario dun ambiente abandona a organización ou se elimina a súa conta de usuario, o ambiente non terá propietario. Un usuario con permisos de administrador pode reclamar a propiedade e converterse no novo propietario. Poden seguir sendo propietarios do medio ou [cambiar a propiedade a outro administrador](#change-the-owner-of-an-environment). 

Para reclamar a propiedade, selecciona **Tomar propiedade** botón que se mostra na parte superior de cada páxina en Customer Insights cando o propietario orixinal deixou a organización.

## <a name="reset-an-existing-environment"></a>Restablecer ambiente existente

Como propietario dun ambiente, pode restablecer un ambiente a un estado baleiro se quere eliminar todas as configuracións e eliminar os datos inxeridos.

1.  Seleccione o selector de **ambiente** na cabeceira da aplicación. 

2.  Seleccione o ambiente que desexa restablecer e seleccione os puntos suspensivos (**...**). 

3. Escolla a opción **Restablecer**. 

4.  Para confirmar a eliminación, introduza o nome do contorno e seleccione **Restablecer**.

## <a name="delete-an-existing-environment"></a>Eliminar un ambiente existente

Como propietario dun ambiente, pode eliminar un ambiente que administre.

1.  Seleccione o selector de **ambiente** na cabeceira da aplicación.

2.  Seleccione o ambiente que desexa restablecer e seleccione os puntos suspensivos (**...**). 

3. Escolla a opción **Eliminar**. 

4.  Para confirmar a eliminación, insira o nome do ambiente e seleccione **Eliminar**.

> [!NOTE]
> A eliminación dun ambiente non elimina a asociación a Dataverse medio ambiente.Aprende a [eliminar unha conexión existente a a Dataverse ambiente](#remove-an-existing-connection-to-a-dataverse-environment).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
