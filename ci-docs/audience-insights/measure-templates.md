---
title: Crea medidas a partir de modelos
description: Definir medidas utilizando modelos para casos de uso comúns.
ms.date: 02/28/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-measure-template
- customerInsights
ms.openlocfilehash: 0fe846691825b93732cbbe6d1c942a79e4a3934f
ms.sourcegitcommit: cf6a0ed44915908a44c70889a2dd199a9d0d4798
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 02/28/2022
ms.locfileid: "8359948"
---
# <a name="use-a-template-to-build-a-measure"></a>Usar un modelo para construír unha medida

Podes usar modelos predefinidos de uso habitual [medidas](measures.md) para crealos. As descricións detalladas dos modelos e unha experiencia guiada axúdanlle a crear medidas eficientes. Os modelos baséanse en datos asignados da entidade *Actividade unificada*. Asegúrese de que configurou [actividades do cliente](activities.md) antes de crear unha medida a partir dun modelo.

Para crear medidas personalizadas, consulte [Usa o creador de medidas para crear medidas desde cero](measure-builder.md).

# <a name="individual-consumers-b-to-c"></a>[Consumidores individuais (B2C)](#tab/b2c)

Modelos de medidas dispoñibles: 
- Valor medio da transacción
- Valor total das transaccións
- Ingresos medios diarios
- Ingresos medios anuais
- Número de transaccións
- Puntos de fidelidade obtidos
- Puntos de fidelidade trocados
- Saldo de puntos de fidelidade
- Período activo do cliente
- Duración da afiliación de fidelidade
- Tempo desde a última compra

## <a name="build-a-new-measure-using-a-template"></a>Constrúe unha nova medida usando un modelo

1. Ir a **Medidas**.

1. Seleccione **Novo** e logo seleccione **Escoller un modelo**.

   :::image type="content" source="media/measure-use-template.png" alt-text="Captura de pantalla do menú despregable cando se crea unha nova medida con resaltado no modelo.":::

1. Busque o modelo que se adapte ás súas necesidades e seleccione **Escoller modelo**.

1. Revise os datos requiridos e seleccione **Comezar** se ten todos os datos no seu lugar.

1. No panel **Editar nome**, estableza o nome da medida e a entidade de saída. 

1. Seleccione **Feito**.

1. Na sección **Establecer o período de tempo**, defina o período de tempo dos datos que se van usar. Escolla se desexa que a nova medida abranga todo o conxunto de datos seleccionando **Todo o tempo** ou se desexa que a medida se centre nun **Período de tempo específico**.

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Captura de pantalla que mostra a sección do período de tempo ao configurar unha medida a partir dun modelo.":::

1. Na seguinte sección, seleccione **Engadir datos** para escoller as actividades e asignar os datos correspondentes da súa entidade *Actividade unificada*.

    1. Paso 1 de 2: en **Tipo de actividade**, escolla o tipo de entidade que desexa empregar. Para **Actividades**, seleccione as entidades que desexa asignar.
    1. Paso 2 de 2: escolla o atributo da entidade *Actividade unificada* para o compoñente requirido pola fórmula. Por exemplo, para o valor medio da transacción, é o atributo que representa o valor da transacción. Para **Marca de tempo da actividade**, escolla o atributo da entidade de actividade unificada que representa a data e hora da actividade.
   
1. Unha vez que a asignación de datos teña éxito, pode ver o estado como **Completo** e o nome das actividades e atributos asignados.

1. Agora pode seleccionar **Executar** para calcular os resultados da medida. Para refinalo máis tarde, selecciona **Gardar borrador**.

# <a name="business-accounts-b-to-b"></a>[Contas empresariais (B2B)](#tab/b2b)

Esta función só está dispoñible para medidas creadas en contornos con clientes individuais como público obxectivo principal.

---
