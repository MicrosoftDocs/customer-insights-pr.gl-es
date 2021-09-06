---
title: Modelos de aprendizaxe automática personalizados | Microsoft Docs
description: Traballe con modelos personalizados de Azure Machine Learning en Dynamics 365 Customer Insights.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 187995cdf4d92a0609f8abb4c792e698ad4342cdb1f578744136add1bfcf3a53
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032940"
---
# <a name="custom-machine-learning-models"></a>Modelos de aprendizaxe automática personalizados

**Intelixencia** > **Modelos personalizados** permítelle xestionar fluxos de traballo baseados en modelos de Azure Machine Learning. Os fluxos de traballo axúdanlle a escoller os datos dos que queres xerar información e asignar os resultados aos datos dos seus clientes unificados. Para obter máis información sobre a creación de modelos de aprendizaxe automática personalizados, consulte [Usar modelos baseados en Azure Machine Learning](azure-machine-learning-experiments.md).

## <a name="responsible-ai"></a>IA responsable

As predicións ofrecen capacidades para crear mellores experiencias de cliente, mellorar as capacidades comerciais e os fluxos de ingresos. Recomendamos encarecidamente que equilibre o valor da súa predición co impacto que ten e os prexuízos que se poden introducir de xeito ético. Máis información sobre como Microsoft está [abordando a IA responsable](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6). Tamén pode aprender sobre [técnicas e procesos de aprendizaxe automática responsable](/azure/machine-learning/concept-responsible-ml) específicos para Azure Machine Learning.

## <a name="prerequisites"></a>Requisitos previos

- Actualmente, esta función admite servizos web publicados a través de [Machine Learning Studio (clásico)](https://studio.azureml.net) e [ canles de lotes de Azure Machine Learning](/azure/machine-learning/concept-ml-pipelines).

- Necesita unha conta de almacenamento de Azure Data Lake Gen2 asociada á súa instancia de Azure Studio para usar esta función. Para obter máis información, consulte [Crear unha conta de almacenamento de Azure Data Lake Storage Gen2](/azure/storage/blobs/data-lake-storage-quickstart-create-account).

- Para os espazos de traballo de aprendizaxe automático de Azure con canalizacións, necesitará permisos de propietario ou administrador de acceso de usuarios ao espazo de traballo de aprendizaxe automático de Azure.

   > [!NOTE]
   > Os datos transfírense entre as instancias de Customer Insights e os servizos web ou canalizacións de Azure seleccionados no fluxo de traballo. Cando transfira datos a algún servizo de Azure, asegúrese de que este estea configurado para procesar os datos co sistema e na localización necesarios para cumprir todos os requisitos legais ou normativos que se apliquen ditos datos da organización.

## <a name="add-a-new-workflow"></a>Engadir un novo fluxo de traballo

1. Vaia a **Intelixencia** > **Modelos personalizados** e seleccione **Novo fluxo de traballo**.

1. Déalle ao seu modelo personalizado un nome recoñecible no campo **Nome**.

   > [!div class="mx-imgBorder"]
   > ![Captura de pantalla do panel Fluxo de traballo novo.](media/new-workflowv2.png "Captura de pantalla do panel Fluxo de traballo novo")

1. Seleccione a organización que contén o servizo web en **Arrendatario que contén o seu servizo web**.

1. Se a súa subscrición a Azure Machine Learning está noutro arrendatario que non sexa Customer Insights, seleccione **Iniciar sesión** coas túas credenciais para a organización seleccionada.

1. Seleccione os **espazos de traballo** asociados ao seu servizo web. Enumeráronse dúas seccións, unha para Azure Machine Learning v.1 (Machine Learning Studio [clásico]) e Azure Machine Learning v.2 (Azure Machine Learning). Se non está seguro de cal é o espazo de traballo adecuado para o seu servizo web de Machine Learning Studio (clásico), seleccione **Calquera**.

1. Escolla o servizo web de Machine Learning Studio (clásico) ou a canle de Azure Machine Learning no menú despregable **Servizo web que contén o seu modelo**. despois, seleccione **Seguinte**.
   - Máis información sobre a [publicación dun servizo web en Machine Learning Studio (clásico)](/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)
   - Máis información sobre a [Publicación dunha canle en Azure Machine Learning usando o deseñador](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) ou [SDK](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk). A canle debe publicarse nun [extremo de canle](/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).

1. Para cada **Entrada do servizo web**, seleccione a **Entidade** coincidente da información sobre o público e seleccione **Seguinte**.
   > [!NOTE]
   > O fluxo de traballo do modelo personalizado aplicará a heurística para asignar os campos de entrada do servizo web aos atributos da entidade en función do nome e do tipo de datos do campo. Verá un erro se un campo de servizo web non se pode asignar a unha entidade.

   > [!div class="mx-imgBorder"]
   > ![Configurar un fluxo de traballo.](media/intelligence-screen2-updated.png "Configurar un fluxo de traballo")

1. No paso **Parámetros de saída do modelo**, configure as seguintes propiedades:
   - Machine Learning Studio (clásico)
      1. Introduza o **Nome da entidade** de saída á quere que flúan os resultados de saída do servizo web.
   - Azure Machine Learning
      1. Introduza o **Nome da entidade** de saída á quere que flúan os resultados de saída da canle.
      1. Seleccione o **nome do parámetro do almacén de datos de saída** da súa canle de lotes desde o menú despregable.
      1. Seleccione o **nome do parámetro do camiño de saída** da súa canle de lotes desde o menú despregable.

      > [!div class="mx-imgBorder"]
      > ![Panel de parámetros de saída do modelo.](media/intelligence-screen3-outputparameters.png "Panel de parámetros de saída do modelo")

1. Seleccione o atributo correspondente na lista despregable **Identificador de cliente** nos resultados que identifica os clientes e seleccione **Gardar**.

   > [!div class="mx-imgBorder"]
   > ![Relacionar resultados co panel de datos do cliente.](media/intelligence-screen4-relatetocustomer.png "Relacionar resultados co panel de datos do cliente")

1. Verá a pantalla **Fluxo de traballo gardado** con detalles sobre o fluxo de traballo.    
   Se configurou un fluxo de traballo para unha canle de Azure Machine Learning, a información do público anexarase ao espazo de traballo que contén a canle. A información do público obterá un rol de **Colaborador** no espazo de traballo de Azure.

1. Seleccione **Feito**.

1. Agora pode executar o fluxo de traballo desde a páxina **Modelos personalizados**.

## <a name="edit-a-workflow"></a>Editar un fluxo de traballo

1. Na páxina **Modelos personalizados**, seleccione os tres puntos verticais na columna **Accións** situada xunto a un fluxo de traballo creado anteriormente e seleccione **Editar**.

1. Pode actualizar o nome recoñecible do seu fluxo de traballo no campo **Nome de visualización**, pero non pode cambiar o servizo web ou a canle configurados. Seleccione **Seguinte**.

1. Para cada **Entrada do servizo web**, pode actualizar a **Entidade** coincidente da información sobre o público. despois, seleccione **Seguinte**.

1. No paso **Parámetros de saída do modelo**, configure as seguintes propiedades:
   - Machine Learning Studio (clásico)
      1. Introduza o **Nome da entidade** de saída á quere que flúan os resultados de saída do servizo web.
   - Azure Machine Learning
      1. Introduza o **Nome da entidade** de saída á quere que flúan os resultados de saída da canle.
      1. Seleccione o **Nome do parámetro do almacén de datos de saída** para a súa canle de proba.
      1. Seleccione o **Nome do parámetro do camiño de saída** para a súa canle de proba.

1. Seleccione o atributo correspondente na lista despregable **Identificador de cliente** nos resultados que identifica os clientes e seleccione **Gardar**.
   Escolla un atributo da saída de inferencia con valores similares á columna ID de cliente da entidade Cliente. Se non ten esa columna no seu conxunto de datos, escolla un atributo que identifique de xeito único a fila.

## <a name="run-a-workflow"></a>Executar un fluxo de traballo

1. Na páxina **Modelos personalizados**, seleccione os tres puntos verticais na columna **Accións** situada xunto a un fluxo de traballo creado anteriormente.

1. Seleccione **Executar**.

O seu fluxo de traballo tamén se executa automaticamente con todas as actualizacións programadas. Obteña máis información acerca de como [configurar actualizacións programadas](system.md#schedule-tab).

## <a name="delete-a-workflow"></a>Eliminar un fluxo de traballo

1. Na páxina **Modelos personalizados**, seleccione os tres puntos verticais na columna **Accións** situada xunto a un fluxo de traballo creado anteriormente.

1. Seleccione **Eliminar** e confirme a eliminación.

Eliminarase o seu fluxo de traballo. A [entidade](entities.md) que se creou cando creou o fluxo de traballo continuará e poderá verse desde a páxina **Entidades**.

## <a name="results"></a>Resultados

Os resultados dun fluxo de traballo almacénanse na entidade configurada durante a fase do parámetro de saída do modelo. Pode acceder a estes datos desde a [páxina de entidades](entities.md) ou con [Acceso á API](apis.md).

### <a name="api-access"></a>Acceso á API

Para que a consulta específica de OData obteña datos dunha entidade de modelo personalizada, use o seguinte formato:

`https://api.ci.ai.dynamics.com/v1/instances/<your instance id>/data/<custom model output entity name>%3Ffilter%3DCustomerId%20eq%20'<guid value>'`

1. Substitúa `<your instance id>` polo ID do seu contorno de Customer Insights, que se atopa na barra de enderezos do seu navegador ao acceder a Customer Insights.

1. Substitúa `<custom model output entity>` polo nome da entidade que proporcionou durante o paso Parámetros de saída do modelo da configuración do modelo personalizado.

1. Substitúa `<guid value>` polo ID de cliente do cliente para o que desexa acceder ao rexistro. Normalmente pode atopar este ID na [páxina de perfís de clientes](customer-profiles.md) no campo CustomerID.

## <a name="frequently-asked-questions"></a>Preguntas máis frecuentes

- Por que non podo ver a miña canalización ao configurar un fluxo de traballo de modelo personalizado?    
  Este problema é frecuentemente causado por un problema de configuración na canalización. Asegúrese de que [o parámetro de entrada estea configurado](azure-machine-learning-experiments.md#dataset-configuration) e que o [almacén de datos de saída e os parámetros de camiño](azure-machine-learning-experiments.md#import-pipeline-data-into-customer-insights) tamén están configurados.

- Que significa o erro "Non se puido gardar o fluxo de traballo de intelixencia"?    
  Os usuarios adoitan ver esta mensaxe de erro se non teñen privilexios de propietario ou de acceso de usuario no espazo de traballo. O usuario precisa un nivel máis alto de permisos para permitir a Customer Insights procesar o fluxo de traballo como un servizo en lugar de usar as credenciais de usuario para as posteriores execucións do fluxo de traballo.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
