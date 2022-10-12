---
title: Visión xeral de orixes de datos
description: Aprende a importar ou inxerir datos de varias fontes.
ms.date: 09/29/2022
ms.subservice: audience-insights
ms.topic: overview
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: f89da3cf5b56e367bd673740f80cd82ec0907b28
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610050"
---
# <a name="data-sources-overview"></a>Visión xeral de orixes de datos

Dynamics 365 Customer Insights proporciona conexións para traer datos dun amplo conxunto de fontes. Conectarse a unha orixe de datos a miúdo chámase proceso de *inxestión de datos*. Despois de inxerir os datos, pode [unificar](data-unification.md), xera información e activa os datos para crear experiencias personalizadas.

## <a name="add-or-edit-data-sources"></a>Engadir ou editar fontes de datos

Podes anexar ou importar fontes de datos a Customer Insights. As ligazóns seguintes ofrecen instrucións sobre como engadir e editar fontes de datos.

**Adxunta un orixe de datos**

Se tes datos preparados nun dos servizos de datos Azure de Microsoft, Customer Insights pode conectarse facilmente ao orixe de datos sen ter que volver inxerir os datos. Seleccione unha das seguintes opcións:
- [Azure Data Lake Storage(arquivos csv ou parquet nun cartafol Common Data Model)](connect-common-data-model.md)
- [Azure Synapse Analytics(bases de datos de lagos)](connect-synapse.md)
- [Microsoft Dataverse lago de datos](connect-dataverse-managed-lake.md)

**Importar e transformar**

Se utiliza fontes de datos locais, Microsoft ou datos de terceiros, importe e transforme os datos mediante Power Query conectores.
- [Power Query conectores](connect-power-query.md)

## <a name="review-data-sources"></a>Revisar fontes de datos

Se o teu ambiente estaba configurado para usar o almacenamento de Customer Insights e utilizas fontes de datos locais, utilizas Power Platform fluxos de datos. Con Power Platform fluxos de datos, pode ver fontes de datos compartidas e fontes de datos xestionadas por outros. O **Fontes de datos** A páxina enumera as fontes de datos en tres seccións:
- **Compartido** : fontes de datos que poden xestionar todos os administradores de Customer Insights. Power Platform fluxos de datos, a súa propia conta de almacenamento e anexo a un Dataverse -Managed Data Lake son exemplos de fontes de datos compartidas.
- **Xestionado por min** :Power Platform fluxos de datos creados e xestionados só por ti. Outros administradores de Customer Insights só poden ver estes fluxos de datos pero non editalos, actualizalos nin eliminalos.
- **Xestionado por outros** :Power Platform fluxos de datos creados por outros administradores. Só podes velos. Enumera o propietario do fluxo de datos co que contactar para obter asistencia.
> [!NOTE]
> Todas as entidades poden ser vistas e usadas por outros usuarios. Aínda que as fontes de datos son propiedade do usuario que as creou, as entidades resultantes da inxestión de datos poden ser utilizadas por todos os usuarios de Customer Insights.

Se o teu ambiente non usa Power Platform fluxos de datos, o **Fontes de datos** páxina contén só unha lista de todas as fontes de datos. Non se mostran seccións.

## <a name="manage-existing-data-sources"></a>Xestionar fontes de datos existentes

Ir a **Datos** > **Fontes de datos** para ver o nome de cada orixe de datos inxerido, o seu estado e a última vez que se actualizaron os datos desa fonte. Podes ordenar a lista de fontes de datos por calquera columna ou usar a caixa de busca para atopar o orixe de datos que queres xestionar.

Seleccione un orixe de datos para ver as accións dispoñibles.

:::image type="content" source="media/data_sources_showmore.png" alt-text="Orixe de datos engadida.":::

- [**Editar**](#add-or-edit-data-sources) o orixe de datos para cambiar as súas propiedades.
- [**Actualizar**](#refresh-data-sources) o orixe de datos para incluír os datos máis recentes.
- [**Enriquecer**](data-sources-enrichment.md) o orixe de datos antes da unificación.
- **Eliminar** o orixe de datos. Un orixe de datos só se pode eliminar se os datos non se usan en ningún procesamento, como unificación, información, activacións ou exportacións.

## <a name="refresh-data-sources"></a>Actualizar orixes de datos

As fontes de datos pódense actualizar de xeito automático ou actualizarse manualmente a demanda. [Fontes de datos locais](connect-power-query.md#add-data-from-on-premises-data-sources) actualizar os seus propios horarios que se configuran durante a inxestión de datos. Para obter consellos para solucionar problemas, consulte [Solucionar problemas de PPDF Power Query problemas de actualización baseados en orixe de datos](connect-power-query.md#troubleshoot-ppdf-power-query-based-data-source-refresh-issues).

Para as fontes de datos adxuntas, a inxestión de datos consome os últimos datos dispoñibles desa orixe de datos.

Ir a **Admin** > **Sistema** > [**Horario**](schedule-refresh.md) para configurar as actualizacións programadas polo sistema das fontes de datos inxeridas.

Para actualizar un orixe de datos baixo demanda:

1. Vaia a **Datos** > **Orixes de datos**.

1. Seleccione o orixe de datos que quere actualizar e seleccione **Actualizar**. A orixe de datos agora está activada para unha actualización manual. Actualizar unha orixe de datos actualizá tanto o esquema de entidade como os datos de todas as entidades especificadas na orixe de datos.

1. Seleccione o estado para abrir **Detalles do progreso** panel e ver o progreso. Para cancelar o traballo, seleccione **Cancelar traballo** na parte inferior do panel.

## <a name="corrupt-data-sources"></a>Fontes de datos corruptas

Os datos que se están inxerindo poden ter rexistros corruptos, o que pode provocar que o proceso de inxestión de datos se complete con erros ou avisos.

> [!NOTE]
> Se a inxestión de datos se completa con erros, o procesamento posterior (como a unificación ou a creación de actividade) que aproveita este orixe de datos omitirase. Se a inxestión se completa con avisos, o procesamento posterior continúa, pero é posible que non se inclúan algúns dos rexistros.

Estes erros pódense ver nos detalles da tarefa.

:::image type="content" source="media/corrupt-task-error.png" alt-text="Detalle da tarefa que mostra un erro de datos corruptos.":::

Os rexistros corruptos móstranse en entidades creadas polo sistema.

### <a name="fix-corrupt-data"></a>Corrixir datos corruptos

1. Para ver os datos corruptos, vai a **Datos** > **Entidades** e buscar as entidades corruptas no **Sistema** sección. O esquema de nomenclatura das entidades corruptas: 'DataSourceName_EntityName_corrupt'.

1. Seleccione unha entidade corrupta e despois o **Datos** ficha.

1. Identifica os campos corruptos nun rexistro e o motivo.

   :::image type="content" source="media/corruption-reason.png" alt-text="Motivo de corrupción." lightbox="media/corruption-reason.png":::

   > [!NOTE]
   > **Datos** > **Entidades** só mostra unha parte dos rexistros corruptos. Para ver todos os rexistros corruptos, exporta os ficheiros a un contedor da conta de almacenamento usando o [Proceso de exportación de Customer Insights](export-destinations.md). Se utilizaches a túa propia conta de almacenamento, tamén podes consultar o cartafol Customer Insights da túa conta de almacenamento.

1. Corrixe os datos corrompidos. Por exemplo, para fontes de datos de Azure Data Lake, [corrixa os datos no Data Lake Storage ou actualice os tipos de datos no ficheiro manifest/model.json](connect-common-data-model.md#common-reasons-for-ingestion-errors-or-corrupt-data). Para Power Query fontes de datos, corrixa os datos no ficheiro fonte e [corrixa o tipo de datos o paso de transformación](connect-power-query.md#data-type-does-not-match-data) no **Power Query - Editar consultas** páxina.

Despois da seguinte actualización da orixe de datos, os rexistros corrixidos inxírense en Customer Insights e transmítense aos procesos descendentes.

Por exemplo, unha columna "aniversario" ten o tipo de datos definido como "data". Un rexistro de cliente introduciu o seu aniversario como "01/01/19777". O sistema marca este rexistro como corrupto. Cambia o aniversario no sistema de orixe a "1977". Despois dunha actualización automática das fontes de datos, o campo ten agora un formato válido e o rexistro elimínase da entidade danada.

[!INCLUDE [footer-include](includes/footer-banner.md)]
