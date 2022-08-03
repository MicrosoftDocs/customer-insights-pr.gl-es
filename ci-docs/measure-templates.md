---
title: Crea medidas a partir de modelos
description: Definir medidas utilizando modelos para casos de uso comúns.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.author: wameng
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-measure-template
- customerInsights
ms.openlocfilehash: 6dc7fce78d10ba91de4b2abf54c6c6ab1c919d3a
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170771"
---
# <a name="create-measures-from-templates"></a>Crea medidas a partir de modelos

Use modelos predefinidos de uso habitual [medidas](measures.md) para crealos. Os modelos baséanse en datos asignados da entidade *Actividade unificada*. Asegúrese de que configurou [actividades do cliente](activities.md) antes de crear unha medida a partir dun modelo.

Os modelos de medida só se admiten en ambientes para **clientes individuais**. Para crear medidas personalizadas ou crear medidas para B-to-B, consulte [Use o creador de medidas](measure-builder.md).

Modelos de medidas dispoñibles:
- Valor medio da transacción
- Valor total das transaccións
- Ingresos medios diarios
- Ingresos medios mensuais
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

1. Seleccione **Editar detalles** xunto a Nome da medida. Proporcione un nome para a medida. Opcionalmente, engadir [etiquetas](work-with-tags-columns.md#manage-tags) á medida.

   :::image type="content" source="media/measures_edit_details.png" alt-text="Cadro de diálogo Editar detalles.":::

1. Seleccione **Feito**.

1. No **Establecer período de tempo** sección, defina o período de tempo dos datos. Escolla se desexa que a nova medida abranga todo o conxunto de datos seleccionando **Todo o tempo** ou se desexa que a medida se centre nun **Período de tempo específico**.

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Captura de pantalla que mostra a sección do período de tempo ao configurar unha medida a partir dun modelo.":::

1. Na seguinte sección, seleccione **Engadir datos** para escoller as actividades e asignar os datos correspondentes da súa entidade *Actividade unificada*.

    1. Paso 1 de 2: en **Tipo de actividade**, escolla o tipo de entidade que desexa empregar. Para **Actividades**, seleccione as entidades que desexa mapear e, a continuación, seleccione **A continuación**.
    1. Paso 2 de 2: escolla o atributo da entidade *Actividade unificada* para o compoñente requirido pola fórmula. Por exemplo, para o valor medio da transacción, é o atributo que representa o valor da transacción. Para **Marca de tempo da actividade**, escolla o atributo de *Actividade unificada* entidade que representa a data e a hora da actividade.
    1. Seleccione **Gardar**.

    Cando a asignación de datos é exitosa, móstrase o estado **Completa** e aparece o nome das actividades e atributos mapeados.

1. Seleccione **Corre** para calcular os resultados da medida. Seleccione **Garda o borrador** se quere manter a configuración actual e executar a medida máis tarde. O **Medidas** visualización da páxina.

## <a name="next-step"></a>Seguinte paso

Use as medidas existentes para crear [un segmento de clientes](segments.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
