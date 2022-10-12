---
title: Modelos de aprendizaxe automática personalizados | Microsoft Docs
description: Traballe con modelos personalizados de Azure Machine Learning en Dynamics 365 Customer Insights.
ms.date: 09/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: zacookmsft
ms.author: zacook
manager: shellyha
searchScope:
- ci-custom-models
- customerInsights
ms.openlocfilehash: 89553b511d249fd586e36a1c4944a977513b0643
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609744"
---
# <a name="custom-machine-learning-models"></a>Modelos de aprendizaxe automática personalizados

> [!NOTE]
> O soporte para Aprendizaxe automático Studio (clásico) finalizará o 31 de agosto de 2024. Recomendamos que faga a transición a [Azure Aprendizaxe automático](/azure/machine-learning/overview-what-is-azure-machine-learning) por esa data.
>
> A partir do 1 de decembro de 2021, non poderás crear novos recursos de Aprendizaxe automático Studio (clásico). Ata o 31 de agosto de 2024, podes seguir utilizando os recursos existentes de Aprendizaxe automático Studio (clásico). Para obter máis información, consulte [Migre a Azure Aprendizaxe automático](/azure/machine-learning/migrate-overview).

Os modelos personalizados permítenche xestionar fluxos de traballo baseados nos modelos de Azure Aprendizaxe automático. Os fluxos de traballo axúdanlle a escoller os datos dos que queres xerar información e asignar os resultados aos datos dos seus clientes unificados. Para obter máis información sobre a creación de modelos de aprendizaxe automática personalizados, consulte [Usar modelos baseados en Azure Machine Learning](azure-machine-learning-experiments.md).

## <a name="prerequisites"></a>Requisitos previos

- Servizos web publicados a través de [Canalizacións por lotes de Azure Aprendizaxe automático](/azure/machine-learning/concept-ml-pipelines).
- O pipeline debe publicarse baixo a [punto final da canalización](/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).
- An [Conta de almacenamento de Azure Data Lake Gen2](/azure/storage/blobs/data-lake-storage-quickstart-create-account) asociado coa súa instancia de Azure Studio.
- Para espazos de traballo de Azure Aprendizaxe automático con canalizacións, permisos de acceso de propietario ou usuario ao espazo de traballo de Azure Aprendizaxe automático.

  > [!NOTE]
  > Os datos transfírense entre as instancias de Customer Insights e os servizos web ou canalizacións de Azure seleccionados no fluxo de traballo. Cando transfira datos a algún servizo de Azure, asegúrese de que este estea configurado para procesar os datos co sistema e na localización necesarios para cumprir todos os requisitos legais ou normativos que se apliquen ditos datos da organización.

## <a name="add-a-new-workflow"></a>Engadir un novo fluxo de traballo

1. Vaia a **Intelixencia** > **Modelos personalizados** e seleccione **Novo fluxo de traballo**.

1. Proporcionar un recoñecible **Nome**.

   :::image type="content" source="media/new-workflowv2.png" alt-text="Captura de pantalla do panel Fluxo de traballo novo.":::

1. Seleccione a organización que contén o servizo web en **Arrendatario que contén o seu servizo web**.

1. Se a súa subscrición a Azure Machine Learning está noutro arrendatario que non sexa Customer Insights, seleccione **Iniciar sesión** coas túas credenciais para a organización seleccionada.

1. Seleccione os **espazos de traballo** asociados ao seu servizo web.

1. Escolla a canalización de Azure Aprendizaxe automático no ficheiro **Servizo web que contén o teu modelo** Despregar menú. despois, seleccione **Seguinte**.
   Máis información sobre a [Publicación dunha canle en Azure Machine Learning usando o deseñador](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) ou [SDK](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).

1. Para cada **Entrada do servizo web**, seleccione a **Entidade** coincidente de Customer Insights. despois, seleccione **Seguinte**.
   > [!NOTE]
   > O fluxo de traballo do modelo personalizado aplicará a heurística para asignar os campos de entrada do servizo web aos atributos da entidade en función do nome e do tipo de datos do campo. Verá un erro se un campo de servizo web non se pode asignar a unha entidade.

   :::image type="content" source="media/intelligence-screen2-updated.png" alt-text="Configurar un fluxo de traballo.":::

1. Para **Parámetros de saída do modelo**, establece as seguintes propiedades:
   - **Nome da entidade** para os resultados da saída do pipeline
   - **Saída almacén de datos nome do parámetro** da súa canalización por lotes
   - **Nome do parámetro da ruta de saída** da súa canalización por lotes

   :::image type="content" source="media/intelligence-screen3-outputparameters.png" alt-text="Panel de parámetros de saída do modelo.":::

1. Seleccione o atributo correspondente de **ID de cliente nos resultados** que identifica clientes e selecciona **Gardar**.

   :::image type="content" source="media/intelligence-screen4-relatetocustomer.png" alt-text="Relacionar resultados co panel de datos do cliente.":::

   O **Fluxo de traballo gardado** pantalla mostra detalles sobre o fluxo de traballo. Se configurou un fluxo de traballo para unha canalización de Azure Aprendizaxe automático, Customer Insights anécese ao espazo de traballo que contén a canalización. Customer Insights recibirá un **Colaborador** rol no espazo de traballo de Azure.

1. Seleccione **Feito**. O **Modelos personalizados** visualización da páxina.

1. Seleccione os puntos suspensivos verticais (&vellip;) para o fluxo de traballo e seleccione **Corre**. O teu fluxo de traballo tamén se executa automaticamente con todos [actualización programada](schedule-refresh.md).

## <a name="manage-an-existing-workflow"></a>Xestionar un fluxo de traballo existente

Ir a **Intelixencia** > **Modelos personalizados** para ver os fluxos de traballo que creou.

Seleccione un fluxo de traballo para ver as accións dispoñibles.

- **Editar** un fluxo de traballo
- **Corre** un fluxo de traballo
- [**Eliminar**](#delete-a-workflow) un fluxo de traballo

### <a name="edit-a-workflow"></a>Editar un fluxo de traballo

1. Ir a **Intelixencia** > **Modelos personalizados**.

1. A carón do fluxo de traballo que queres actualizar, selecciona os puntos suspensivos verticais (&vellip;) e seleccione **Editar**.

1. Cambiar **Nome para mostrar** se é necesario, e selecciona **A continuación**.

1. Para cada un **Entrada do servizo web**, actualiza a coincidencia **Entidade** de Customer Insights, se é necesario. despois, seleccione **Seguinte**.

1. Para **Parámetros de saída do modelo**, cambie calquera das seguintes opcións:
   - **Nome da entidade** para os resultados da saída do pipeline
   - **Saída almacén de datos nome do parámetro** da súa canalización por lotes
   - **Nome do parámetro da ruta de saída** da súa canalización por lotes

1. Cambia o atributo coincidente de **ID de cliente nos resultados** para identificar clientes. Escolla un atributo da saída de inferencia con valores similares á columna ID de cliente da entidade Cliente. Se non tes unha columna deste tipo no teu conxunto de datos, escolla un atributo que identifique a fila de forma exclusiva.

1. Seleccione **Gardar**

### <a name="delete-a-workflow"></a>Eliminar un fluxo de traballo

1. Ir a **Intelixencia** > **Modelos personalizados**.

1. A carón do fluxo de traballo que queres eliminar, selecciona os puntos suspensivos verticais (&vellip;) e seleccione **Eliminar**.

1. Confirme a eliminación.

Eliminarase o seu fluxo de traballo. O [entidade](entities.md) que se creou cando creou o fluxo de traballo persiste e pódese ver desde o **Datos** > **Entidades** páxina.

## <a name="view-the-results"></a>Ver os resultados

Os resultados dun fluxo de traballo almacénanse no nome da entidade definido para **Parámetros de saída do modelo**. Acceda a estes datos desde o [**Datos** > **Entidades** páxina](entities.md) ou con [Acceso API](apis.md).

### <a name="api-access"></a>Acceso á API

Para que a consulta específica de OData obteña datos dunha entidade de modelo personalizada, use o seguinte formato:

`https://api.ci.ai.dynamics.com/v1/instances/<your instance id>/data/<custom model output entity name>%3Ffilter%3DCustomerId%20eq%20'<guid value>'`

1. Substituír`<your instance id>` co ID do teu contorno de Customer Insights, que se mostra na barra de enderezos do teu navegador cando accedes a Customer Insights.

1. Substituír`<custom model output entity>` co nome da entidade que proporcionou para o **Parámetros de saída do modelo**.

1. Substituír`<guid value>` co ID de cliente do cliente ao que desexa acceder. Este ID móstrase no [páxina de perfís de clientes](customer-profiles.md) no campo CustomerID.

## <a name="frequently-asked-questions"></a>Preguntas máis frecuentes

- Por que non podo ver a miña canalización ao configurar un fluxo de traballo de modelo personalizado?
  Este problema é frecuentemente causado por un problema de configuración na canalización. Asegúrese de que [o parámetro de entrada estea configurado](azure-machine-learning-experiments.md#dataset-configuration) e que o [almacén de datos de saída e os parámetros de camiño](azure-machine-learning-experiments.md#import-pipeline-data-into-customer-insights) tamén están configurados.

- Que significa o erro "Non se puido gardar o fluxo de traballo de intelixencia"? 
  Os usuarios adoitan ver esta mensaxe de erro se non teñen privilexios de propietario ou de acceso de usuario no espazo de traballo. O usuario precisa un nivel máis alto de permisos para permitir a Customer Insights procesar o fluxo de traballo como un servizo en lugar de usar as credenciais de usuario para as posteriores execucións do fluxo de traballo.

- Admítese un punto final privado ou unha ligazón privada para o meu fluxo de traballo de modelo personalizado?
  Customer Insights non admite actualmente o punto final privado para modelos personalizados listos para usar, pero hai unha solución manual dispoñible. Ponte en contacto co servizo de asistencia para obter máis detalles.

## <a name="responsible-ai"></a>IA responsable

As predicións ofrecen capacidades para crear mellores experiencias de cliente, mellorar as capacidades comerciais e os fluxos de ingresos. Recomendamos encarecidamente que equilibre o valor da súa predición co impacto que ten e os prexuízos que se poden introducir de xeito ético. Máis información sobre como Microsoft está [abordando a IA responsable](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6). Tamén pode aprender sobre [técnicas e procesos de aprendizaxe automática responsable](/azure/machine-learning/concept-responsible-ml) específicos para Azure Machine Learning.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElk]

[!INCLUDE [footer-include](includes/footer-banner.md)]
