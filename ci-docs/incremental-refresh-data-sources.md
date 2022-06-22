---
title: Actualización incremental para Power Query e fontes de datos de Azure Data Lake
description: Actualizar datos novos e actualizados para fontes de datos grandes en base a Power Query ou fontes de datos de Azure Data Lake.
ms.date: 05/30/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-schedule
- customerInsights
ms.openlocfilehash: bff27bf7fec2bcb741846ae76bb1f616f459136c
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 06/14/2022
ms.locfileid: "9012023"
---
# <a name="incremental-refresh-for-power-query-and-azure-data-lake-data-sources"></a>Actualización incremental para Power Query e fontes de datos de Azure Data Lake

Este artigo explica como configurar a actualización incremental para fontes de datos en función de Power Query ou Azure Data Lake.

A actualización incremental para as orixes de datos ofrece as seguintes vantaxes:

- **Actualizacións máis rápidas** - Só se actualizan os datos que cambiaron. Por exemplo, pode actualizar só os últimos cinco días dun conxunto de datos histórico.
- **Fiabilidade aumentada** - Con actualizacións máis frecuentes, non necesita manter conexións a sistemas de orixes volátiles durante tanto tempo, reducindo o risco de problemas de conexión.
- **Consumo de recursos reducido** - Actualizar só un subconxunto dos seus datos totais implica un uso máis eficiente dos recursos informáticos e diminúe a pegada ambiental.

## <a name="configure-incremental-refresh-for-data-sources-based-on-power-query"></a>Configure a actualización incremental para fontes de datos en función de Power Query

Customer Insights permite a actualización incremental das fontes de datos importadas Power Query que admiten a inxestión incremental. Por exemplo, as bases de datos de Azure SQL con campos de data e hora, que indican cando se actualizaron por última vez os rexistros de datos.

1. [Crea un novo orixe de datos baseado en Power Query](connect-power-query.md).

1. Seleccione un orixe de datos que admita a actualización incremental, como [Base de datos Azure SQL](/power-query/connectors/azuresqldatabase).

1. Seleccione as entidades ou táboas para inxerir.

1. Complete os pasos de transformación e seleccione **Seguinte**.

1. Na caixa de diálogo **Configurar actualización incremental**, seleccione **Configurar** para abrir a **Configuración de actualización incremental**. Se selecciona **Saltar**, a orixe de datos actualizará todo o conxunto de datos.
   > [!TIP]
   > Tamén pode aplicar a actualización incremental máis tarde editando un orixe de datos existente.

1. Na **Configuración de actualización incremental**, configurará a actualización incremental para todas as entidades que seleccionou ao crear a orixe de datos.

   :::image type="content" source="media/incremental-refresh-settings.png" alt-text="Configurar a configuración de actualización incremental.":::

1. Seleccione unha entidade e proporcione os seguintes detalles:

   - **Definir a clave principal**: seleccione unha clave principal para a entidade ou táboa.
   - **Definir o campo "última actualización"**: este campo só mostrará atributos de data ou hora. Seleccione un atributo que indique cando se actualizaron os rexistros por última vez. Utilizarase para identificar os rexistros que se atopan dentro do intervalo temporal de actualización incremental.
   - **Comprobar se hai actualizacións cada**: especifique o tempo que quere que dure o período de actualización incremental.

1. Seleccione **Gardar** para completar a creación da orixe de datos. A actualización de datos inicial será unha actualización completa. Despois, a actualización de datos incremental producirase como se configurou no paso anterior.

## <a name="configure-incremental-refresh-for-azure-data-lake-data-sources"></a>Configure a actualización incremental para fontes de datos de Azure Data Lake

Customer Insights permite a actualización incremental das fontes de datos conectadas Azure Data Lake Storage. Para utilizar a inxestión incremental e a actualización dunha entidade, configure esa entidade ao engadir o Azure Data Lake orixe de datos ou posteriormente ao editar o orixe de datos. O cartafol de datos da entidade debe conter os seguintes cartafoles:

- **Datos completos** : Cartafol con ficheiros de datos que conteñen rexistros iniciais
- **Datos incrementais** : Cartafol cos cartafoles da xerarquía de data/hora **aaaa/mm/dd/hh** formato que contén as actualizacións incrementais. **hh** representa a hora UTC das actualizacións e contén o **Upsers** e **Elimina** cartafoles. **Upsers** contén ficheiros de datos con actualizacións de rexistros existentes ou novos rexistros. **Elimina** contén ficheiros de datos con rexistros que se deben eliminar.

1. Ao engadir ou editar un orixe de datos, desprácese ata o **Atributos** panel para a entidade.

1. Revisa os atributos. Asegúrate de que un atributo de data de creación ou de última actualización estea configurado con a *dataHora* **Formato de datos** e a *Calendario.Data* **Tipo semántico**. Edita o atributo se é necesario e selecciona **Feito**.

1. Dende **Seleccione Entidades** panel, edita a entidade. O **Inxestión incremental** a caixa de verificación está seleccionada.

   :::image type="content" source="media/ADLS_inc_refresh.png" alt-text="Configurar as entidades dunha orixe de datos para a actualización incremental.":::

   1. Navega ata o cartafol raíz que contén os ficheiros .csv ou .parquet para obter datos completos, subidas de datos incrementais e eliminacións de datos incrementais.
   1. Introduza a extensión para os datos completos e os dous ficheiros incrementais (\. csv ou\. parqué).
   1. Seleccione **Gardar**.

1. Para **Última actualización**, seleccione o atributo de marca de data e hora.

1. Se o **Chave primaria** non está seleccionado, seleccione a chave primaria. A chave primaria é un atributo exclusivo da entidade. Para que un atributo sexa unha clave primaria válida, non debe incluír valores duplicados, valores perdidos ou valores nulos. Os atributos de tipo de datos de cadea, enteiro e GUID son compatibles como claves primarias.

1. Seleccione **Pechar** para gardar e pechar o panel.

1. Continúa engadindo ou editando o orixe de datos.

[!INCLUDE [footer-include](includes/footer-banner.md)]
