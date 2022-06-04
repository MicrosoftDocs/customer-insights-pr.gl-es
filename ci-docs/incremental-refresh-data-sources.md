---
title: Actualización incremental para Power Query fontes de datos baseadas
description: Actualiza datos novos e actualizados para fontes de datos grandes baseados en Power Query.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
searchScope:
- ci-system-schedule
- customerInsights
ms.openlocfilehash: 3d21baf9804f300802b066df0183fc8f01abba9a
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642806"
---
# <a name="incremental-refresh-for-data-sources-based-on-power-query"></a>Actualización incremental para fontes de datos baseada en Power Query

Este artigo explica como configurar a actualización incremental para fontes de datos baseadas en Power Query.

A actualización incremental para as orixes de datos ofrece as seguintes vantaxes:

- **Actualizacións máis rápidas** - Só se actualizan os datos que cambiaron. Por exemplo, pode actualizar só os últimos cinco días dun conxunto de datos histórico.
- **Fiabilidade aumentada** - Con actualizacións máis frecuentes, non necesita manter conexións a sistemas de orixes volátiles durante tanto tempo, reducindo o risco de problemas de conexión.
- **Consumo de recursos reducido** - Actualizar só un subconxunto dos seus datos totais implica un uso máis eficiente dos recursos informáticos e diminúe a pegada ambiental.

## <a name="configure-incremental-refresh"></a>Configurar a actualización incremental

Customer Insights permite a actualización incremental das fontes de datos importadas Power Query que admiten a inxestión incremental. Por exemplo, as bases de datos de Azure SQL con campos de data e hora, que indican cando se actualizaron por última vez os rexistros de datos.

1. [Crea un novo orixe de datos baseado en Power Query](connect-power-query.md).

1. Proporcionar a **Nome** para o orixe de datos.

1. Seleccione un orixe de datos que admita a actualización incremental, como [Base de datos Azure SQL](/power-query/connectors/azuresqldatabase).

1. Seleccione as entidades ou táboas para inxerir.

1. Complete os pasos de transformación e seleccione **Seguinte**.

1. Na caixa de diálogo **Configurar actualización incremental**, seleccione **Configurar** para abrir a **Configuración de actualización incremental**. Se selecciona **Saltar**, a orixe de datos actualizará todo o conxunto de datos.
   > [!TIP]
   > Tamén pode aplicar a actualización incremental máis tarde editando un orixe de datos existente.

1. Na **Configuración de actualización incremental**, configurará a actualización incremental para todas as entidades que seleccionou ao crear a orixe de datos.

   :::image type="content" source="media/incremental-refresh-settings.png" alt-text="Configurar as entidades dunha orixe de datos para a actualización incremental.":::

1. Seleccione unha entidade e proporcione os seguintes detalles:

   - **Definir a clave principal**: seleccione unha clave principal para a entidade ou táboa.
   - **Definir o campo "última actualización"**: este campo só mostrará atributos de data ou hora. Seleccione un atributo que indique cando se actualizaron os rexistros por última vez. Utilizarase para identificar os rexistros que se atopan dentro do intervalo temporal de actualización incremental.
   - **Comprobar se hai actualizacións cada**: especifique o tempo que quere que dure o período de actualización incremental.

1. Seleccione **Gardar** para completar a creación da orixe de datos. A actualización de datos inicial será unha actualización completa. Despois, a actualización de datos incremental producirase como se configurou no paso anterior.


[!INCLUDE [footer-include](includes/footer-banner.md)]