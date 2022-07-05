---
title: Conectar cun cartafol de Common Data Model cunha conta de Azure Data Lake
description: Traballe con datos de Common Data Model usando Azure Data Lake Storage.
ms.date: 05/30/2022
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- ci-attach-cdm
- customerInsights
ms.openlocfilehash: b1cdcb46df17d722ad49d361ae4c7ab34c83eeb1
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082258"
---
# <a name="connect-to-data-in-azure-data-lake-storage"></a>Conectarse con datos en Azure Data Lake Storage

Inxerir datos en Dynamics 365 Customer Insights usando o teu Azure Data Lake Storage Conta Gen2. A inxestión de datos pode ser completa ou incremental.

## <a name="prerequisites"></a>Requisitos previos

- Admite a inxestión de datos Azure Data Lake Storage *Xeración 2* contas exclusivamente. Non podes usar contas de Data Lake Storage Gen1 para inxerir datos.

- O Azure Data Lake Storage conta debe ter [espazo de nomes xerárquico activado](/azure/storage/blobs/data-lake-storage-namespace). Os datos deben almacenarse nun formato de cartafol xerárquico que defina o cartafol raíz e teña subcartafoles para cada entidade. Os subcartafoles poden ter datos completos ou cartafoles de datos incrementais.

- Para autenticarse cunha entidade de seguranza do servizo de Azure, asegúrese de que está configurada no seu inquilino. Para obter máis información, consulte [Conectar a un Azure Data Lake Storage Conta Gen2 cun principal de servizo de Azure](connect-service-principal.md).

- O Azure Data Lake Storage que quere conectarse e inxerir datos ten que estar na mesma rexión de Azure que a Dynamics 365 Customer Insights ambiente. Non se admiten conexións a un cartafol de Common Data Model desde un lago de datos nunha rexión de Azure diferente. Para coñecer a rexión Azure do entorno, vai a **Admin** > **Sistema** > **Sobre** en Customer Insights.

- Os datos almacenados nos servizos en liña poden almacenarse nun lugar diferente do que se procesan ou almacenan os datos Dynamics 365 Customer Insights.Ao importar ou conectarse a datos almacenados nos servizos en liña, acepta que os datos se poidan transferir e almacenar con Dynamics 365 Customer Insights . [Máis información no Microsoft Trust Center](https://www.microsoft.com/trust-center).

- O principal do servizo de Customer Insights debe estar nun dos seguintes roles para acceder á conta de almacenamento. Para obter máis información, consulte [Conceda permisos ao principal do servizo para acceder á conta de almacenamento](connect-service-principal.md#grant-permissions-to-the-service-principal-to-access-the-storage-account).
  - Lector de datos do BLOB de almacenamento
  - Propietario dos datos do BLOB de almacenamento
  - Colaborador de datos do BLOB de almacenamento

- Os datos do almacenamento de Data Lake deben seguir o estándar do modelo de datos común para o almacenamento dos seus datos e ter o manifesto do modelo de datos común para representar o esquema dos ficheiros de datos (*.csv ou *.parquet). O manifesto debe proporcionar os detalles das entidades, como as columnas de entidades e os tipos de datos, así como a localización do ficheiro de datos e o tipo de ficheiro. Para obter máis información, consulte [Manifesto do modelo común de datos](/common-data-model/sdk/manifest). Se o manifesto non está presente, os usuarios administradores con acceso de propietario de datos de blob de almacenamento ou de colaborador de datos de blob de almacenamento poden definir o esquema ao inxerir os datos.

## <a name="connect-to-azure-data-lake-storage"></a>Conectar con Azure Data Lake Storage

1. Vaia a **Datos** > **Orixes de datos**.

1. Seleccione **Engadir orixe de datos**.

1. Seleccione **Almacenamento Azure Data Lake**.

   :::image type="content" source="media/data_sources_ADLS.png" alt-text="Cadro de diálogo para introducir detalles de conexión para Azure Data Lake." lightbox="media/data_sources_ADLS.png":::

1. Introduza a **Nome** para o orixe de datos e un opcional **Descrición**. O nome identifica de forma única o orixe de datos e faise referencia nos procesos posteriores e non se pode cambiar.

1. Escolla unha das seguintes opcións para **Conecta o teu almacenamento usando**. Para obter máis información, consulte [Conecte Customer Insights a un Azure Data Lake Storage Conta Gen2 cun principal de servizo de Azure](connect-service-principal.md).

   - **recurso Azure** : Introduza o **ID do recurso** . Opcionalmente, se quere inxerir datos dunha conta de almacenamento a través dunha ligazón privada de Azure, seleccione **Activa a ligazón privada**. Para obter máis información, consulte [Ligazóns privadas](security-overview.md#private-links-tab).
   - **Subscrición de Azure** : Seleccione o **Subscrición** e despois o **Grupo de recursos** e **Conta de almacenamento**. Opcionalmente, se quere inxerir datos dunha conta de almacenamento a través dunha ligazón privada de Azure, seleccione **Activa a ligazón privada**. Para obter máis información, consulte [Ligazóns privadas](security-overview.md#private-links-tab).
  
   > [!NOTE]
   > Necesitas un dos seguintes roles para o contedor ou para a conta de almacenamento para crear o orixe de datos:
   >
   >  - Storage Blob Data Reader é suficiente para ler desde unha conta de almacenamento e inxerir os datos a Customer Insights. 
   >  - Se queres editar os ficheiros de manifesto directamente en Customer Insights, é necesario un Colaborador ou propietario de datos de Blob de almacenamento.  
  
1. Escolla o nome do **Envase** que contén os datos e o esquema (ficheiro model.json ou manifest.json) desde os que importar os datos e seleccione **A continuación**.
   > [!NOTE]
   > Calquera ficheiro model.json ou manifest.json asociado a outra orixe de datos do contorno non aparecerá na lista. Non obstante, o mesmo ficheiro model.json ou manifest.json pode usarse para fontes de datos en múltiples contornos.

1. Para crear un novo esquema, vai a [Crea un novo ficheiro de esquema](#create-a-new-schema-file).

1. Para utilizar un esquema existente, desprácese ata o cartafol que contén o ficheiro model.json ou manifest.cdm.json. Pode buscar dentro dun directorio para atopar o ficheiro.

1. Seleccione o ficheiro json e seleccione **A continuación**. Móstrase unha lista de entidades dispoñibles.

   :::image type="content" source="media/review-entities.png" alt-text="Cadro de diálogo dunha lista de entidades a seleccionar":::

1. Seleccione as entidades que quere incluír.

   :::image type="content" source="media/ADLS_required.png" alt-text="Cadro de diálogo que mostra Requirido para a chave primaria":::

   > [!TIP]
   > Para editar as entidades nunha interface de edición JSON, seleccione **Mostrar máis** > **Editar ficheiro de esquema**. Fai cambios e selecciona **Gardar**.

1. Para as entidades seleccionadas que requiren inxestión incremental, **Obrigatorio** mostra debaixo **Actualización incremental**. Para cada unha destas entidades, véxase [Configure unha actualización incremental para fontes de datos de Azure Data Lake](incremental-refresh-data-sources.md).

1. Para as entidades seleccionadas nas que non se definiu unha chave primaria, **Obrigatorio** mostra debaixo **Chave primaria**. Para cada unha destas entidades:
   1. Seleccione **Obrigatorio**. O **Editar entidade** pantallas de paneis.
   1. Escolle o **Chave primaria**. A chave primaria é un atributo exclusivo da entidade. Para que un atributo sexa unha clave primaria válida, non debe incluír valores duplicados, valores perdidos ou valores nulos. Os atributos de tipo de datos de cadea, enteiro e GUID son compatibles como claves primarias.
   1. Opcionalmente, cambia o patrón de partición.
   1. Seleccione **Pechar** para gardar e pechar o panel.

1. Seleccione o número de **Atributos** para cada entidade incluída. O **Xestionar atributos** visualización da páxina.

   :::image type="content" source="media/dataprofiling-entities.png" alt-text="Cadro de diálogo para seleccionar o perfil de datos.":::

   1. Crea novos atributos, edita ou elimina os existentes. Pode cambiar o nome, o formato de datos ou engadir un tipo semántico.
   1. Para activar a análise e outras capacidades, seleccione **Perfil de datos** para toda a entidade ou para atributos específicos. Por defecto, ningunha entidade está habilitada para a creación de perfís de datos.
   1. Seleccione **Feito**.

1. Seleccione **Gardar**. O **Fontes de datos** ábrese a páxina mostrando o novo orixe de datos en **Refrescante** estado.

### <a name="create-a-new-schema-file"></a>Crea un novo ficheiro de esquema

1. Seleccione **Novo ficheiro de esquema**.

1. Introduza un nome para o ficheiro e seleccione **Gardar**.

1. Seleccione **Nova entidade**. O **Nova Entidade** pantallas de paneis.

1. Introduza o nome da entidade e escolla **Localización dos ficheiros de datos**.
   - **Varios ficheiros .csv ou .parquet** : navegue ata o cartafol raíz, seleccione o tipo de patrón e introduza a expresión.
   - **Ficheiros únicos .csv ou .parquet** : busque o ficheiro .csv ou .parquet e seleccióneo.

   :::image type="content" source="media/ADLS_new_entity_location.png" alt-text="Cadro de diálogo para crear unha nova entidade coa localización dos ficheiros de datos resaltada.":::

1. Seleccione **Gardar**.

   :::image type="content" source="media/ADLS_new_entity_define_attributes.png" alt-text="Cadro de diálogo para definir ou xerar automaticamente atributos.":::

1. Seleccione **definir os atributos** para engadir manualmente os atributos ou seleccionar **xeralos automaticamente**. Para definir os atributos, introduza un nome, seleccione o formato de datos e o tipo semántico opcional. Para os atributos xerados automaticamente:

   1. Despois de xerar automaticamente os atributos, seleccione **Revisar atributos**. O **Xestionar atributos** visualización da páxina.

   1. Asegúrese de que o formato de datos é correcto para cada atributo.

   1. Para activar a análise e outras capacidades, seleccione **Perfil de datos** para toda a entidade ou para atributos específicos. Por defecto, ningunha entidade está habilitada para a creación de perfís de datos.

      :::image type="content" source="media/dataprofiling-entities.png" alt-text="Cadro de diálogo para seleccionar o perfil de datos.":::

   1. Seleccione **Feito**. O **Seleccionar entidades** visualización da páxina.

1. Continúa engadindo entidades e atributos, se é o caso.

1. Despois de engadir todas as entidades, seleccione **Incluír** para incluír as entidades na inxestión orixe de datos.

   :::image type="content" source="media/ADLS_required.png" alt-text="Cadro de diálogo que mostra Requirido para a chave primaria":::

1. Para as entidades seleccionadas que requiren inxestión incremental, **Obrigatorio** mostra debaixo **Actualización incremental**. Para cada unha destas entidades, véxase [Configure unha actualización incremental para fontes de datos de Azure Data Lake](incremental-refresh-data-sources.md).

1. Para as entidades seleccionadas nas que non se definiu unha chave primaria, **Obrigatorio** mostra debaixo **Chave primaria**. Para cada unha destas entidades:
   1. Seleccione **Obrigatorio**. O **Editar entidade** pantallas de paneis.
   1. Escolle o **Chave primaria**. A chave primaria é un atributo exclusivo da entidade. Para que un atributo sexa unha clave primaria válida, non debe incluír valores duplicados, valores perdidos ou valores nulos. Os atributos de tipo de datos de cadea, enteiro e GUID son compatibles como claves primarias.
   1. Opcionalmente, cambia o patrón de partición.
   1. Seleccione **Pechar** para gardar e pechar o panel.

1. Seleccione **Gardar**. O **Fontes de datos** ábrese a páxina mostrando o novo orixe de datos en **Refrescante** estado.


## <a name="edit-an-azure-data-lake-storage-data-source"></a>Editar un Azure Data Lake Storage orixe de datos

Podes actualizar o *Conéctate á conta de almacenamento usando* opción. Para obter máis información, consulte [Conecte Customer Insights a un Azure Data Lake Storage Conta Gen2 cun principal de servizo de Azure](connect-service-principal.md). Para conectarse a un contedor diferente da súa conta de almacenamento ou cambiar o nome da conta, [cree unha nova conexión de orixe de datos](#connect-to-azure-data-lake-storage).

1. Vaia a **Datos** > **Orixes de datos**.

1. A carón do orixe de datos que queres actualizar, selecciona **Editar**.

   :::image type="content" source="media/data_sources_edit_ADLS.png" alt-text="Cadro de diálogo para editar Azure Data Lake orixe de datos.":::

1. Cambia calquera das seguintes informacións:

   - **Descripción**
   - **Conecta o teu almacenamento usando** e información de conexión. Non pode cambiar a información do **contedor** ao actualizar a conexión.
      > [!NOTE]
      > Débese asignar un dos seguintes roles á conta de almacenamento ou contedor:
        > - Lector de datos do BLOB de almacenamento
        > - Propietario dos datos do BLOB de almacenamento
        > - Colaborador de datos do BLOB de almacenamento

   - **Activa a ligazón privada** se quere inxerir datos dunha conta de almacenamento a través dunha ligazón privada de Azure. Para obter máis información, consulte [Ligazóns privadas](security-overview.md#private-links-tab).

1. Seleccione **Seguinte**.
1. Cambia calquera das seguintes opcións:
   - Navega a un ficheiro model.json ou manifest.json diferente cun conxunto de entidades diferente do contedor.
   - Para engadir entidades adicionais para inxerir, seleccione **Nova entidade**.
   - Para eliminar as entidades xa seleccionadas se non hai dependencias, seleccione a entidade e **Eliminar**.
      > [!IMPORTANT]
      > Se hai dependencias no ficheiro model.json ou manifest.json existente e no conxunto de entidades, verá unha mensaxe de erro e non poderá seleccionar un ficheiro model.json ou manifest.json diferente. Elimine esas dependencias antes de cambiar o ficheiro model.json ou manifest.json ou cree unha nova orixe de datos co ficheiro model.json ou manifest.json que desexe usar para evitar eliminar as dependencias.
   - Para cambiar a localización do ficheiro de datos ou a clave principal, seleccione **Editar**.
   - Para cambiar os datos de inxestión incremental, consulte [Configure unha actualización incremental para fontes de datos de Azure Data Lake](incremental-refresh-data-sources.md)

1. Seleccione **Atributos** para engadir ou cambiar atributos, ou para activar o perfil de datos. Seleccione **Feito**.

1. Fai clic **Gardar** para aplicar os seus cambios e volver ao **Fontes de datos** páxina.
