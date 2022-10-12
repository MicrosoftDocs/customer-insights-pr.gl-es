---
title: Visión xeral de predicións
description: Os escenarios e opcións de predición cubertos pola aplicación de Dynamics 365 Customer Insights.
ms.date: 09/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: overview
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: f8c61d7530126890d26ce482a27a0f97a39e836c
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610188"
---
# <a name="predictions-overview"></a>Visión xeral de predicións

Dynamics 365 Customer Insights inclúe unha variedade de opcións que aproveitan a IA e a aprendizaxe automática para predicir datos.

## <a name="out-of-box-models"></a>Modelos listos para utilizar

O xeito máis sinxelo de comezar coa predición de datos é cos modelos predefinidos, a miúdo denominados modelos listos para usar. Só requiren determinados datos e unha determinada estrutura para xerar información rapidamente. Os seguintes modelos están dispoñibles:

# <a name="individual-consumers-b-to-c"></a>[Consumidores individuais (B2C)](#tab/b2c)

- [Valor de duración do cliente](predict-customer-lifetime-value.md): predí os ingresos potenciais dun cliente ao longo de toda a interacción cunha empresa.
- [Recomendación de produtos](predict-product-recommendation.md): suxire conxuntos de recomendacións preditivas de produtos baseadas no comportamento de compra e en clientes con padróns de compra similares.
- [Renovación da subscrición](predict-subscription-churn.md): predí se un cliente está en risco de deixar de usar os servizos ou produtos da subscrición da empresa.
- [Churn transaccional](predict-transactional-churn.md) : predice se un cliente individual deixará de comprar os seus produtos ou servizos nun período de tempo determinado.
- [Análise de sentimentos](sentiment-analysis.md) : Analiza o sentimento dos comentarios dos clientes e identifica os aspectos comerciais que se mencionan con frecuencia.

# <a name="business-accounts-b-to-b"></a>[Contas empresariais (B2B)](#tab/b2b)

- [Churn transaccional](predict-transactional-churn.md) : predí se unha conta de cliente deixará de comprar os seus produtos ou servizos nun período de tempo determinado.

---

> [!TIP]
> Recomendámosche que actualices regularmente os modelos prefabricados con datos actualizados para asegurarte de que informen con precisión o teu caso de uso empresarial. Os datos actualízanse ad hoc cando o sistema inxire fontes de datos novas ou actualizadas. Non obstante, os modelos só repuntarán neste caso e seguirán utilizando os datos de adestramento existentes.
>
> Configurar un **Actualizar horario** configurando o programa de reciclaxe do modelo durante a configuración. O modelo volverá adestrar e recalificarase nesta programación, que podes cambiar en calquera momento.

## <a name="azure-machine-learning-integration"></a>Integración da Aprendizaxe automática de Azure

Se unha organización xa usa escenarios de aprendizaxe automática baseados en experimentos da Aprendizaxe automática de Azure, a función de modelos personalizados en Customer Insights axuda a conectar os puntos. Cree fluxos de traballo que lle axuden a escoller os datos dos que quere xerar información e asigne os resultados aos perfís de clientes unificados. Para obter máis información, consulte [Modelos de aprendizaxe automática personalizados](custom-models.md).

## <a name="manage-existing-predictions"></a>Xestionar as predicións existentes

Vaia ao **Intelixencia** > **Predicións** páxina. No **As miñas predicións** pestana, consulta as predicións que creaches, o seu tipo de predición, o nome da entidade de saída, o estado, a última vez que se editou o predición e a última vez que se actualizaron os datos. Podes ordenar a lista de predicións por calquera columna.

Selecciona un predición para ver as accións dispoñibles.

:::image type="content" source="media/predictions.png" alt-text="A miña páxina de predicións.":::

- **Editar** o predición para cambiar as súas propiedades.
- [**Actualizar**](#refresh-a-prediction) o predición para incluír os datos máis recentes.
- **Ver** os detalles de predición.
- [**Informe de usabilidade dos datos de entrada**](#view-the-input-data-usability-report) para ver erros, avisos e recomendacións.
- **Eliminar** o predición.

### <a name="refresh-a-prediction"></a>Actualizar unha predición

As previsións pódense actualizar nunha programación automática ou actualizar manualmente baixo demanda. Para actualizar manualmente todas as predicións, selecciona **Actualiza todo**. Para actualizar manualmente un predición, selecciónao e selecciónao **Actualizar**. Para [programar unha actualización automática](schedule-refresh.md), Ir a **Admin** > **Sistema** > **Horario**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

### <a name="view-the-input-data-usability-report"></a>Ver informe de usabilidade dos datos de entrada

O informe de usabilidade dos datos de entrada ofrece unha visión consolidada dos erros e advertencias que poden xerar as predicións listas para utilizar. Tamén ofrece recomendacións sobre como mellorar o rendemento do modelo.

O informe estará dispoñible despois de que un modelo finalice o seu proceso de adestramento. Créase para cada modelo por separado, independentemente de se completou o adestramento con éxito ou non.

No **As miñas predicións** pestana, seleccione o predición e escolla **Informe de usabilidade dos datos de entrada**. Ou desde a vista de detalles predición, seleccione **Informe de usabilidade dos datos de entrada**.

:::image type="content" source="media/input-data-usability-report.png" alt-text="Exemplo dun informe de usabilidade dos datos de entrada que mostra unha táboa con erros, avisos e recomendacións.":::

O informe inclúe:

- **Nome:** Nome descritivo do erro, aviso ou recomendación.
- **Paso:** Fase do modelo, tren ou puntuación, a que fai referencia a información.
- **Estado:** Gravidade da información (erro, aviso, recomendación).
- **Nome da columna:** Columna nunha entidade que se debe modificar para mellorar o rendemento do modelo.
- **Nome da entidade:** Nome da entidade que se debe modificar para mellorar o rendemento do modelo.
- **Detalles:** Detalles sobre o erro, aviso ou recomendación.

[!INCLUDE [footer-include](includes/footer-banner.md)]
