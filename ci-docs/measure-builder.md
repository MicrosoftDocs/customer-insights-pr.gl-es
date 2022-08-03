---
title: Crea medidas co creador de medidas
description: Crea medidas desde cero para analizar métricas clave sobre a túa empresa.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.author: wameng
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-measure-builder
- customerInsights
ms.openlocfilehash: fac00b8a1b4ca6e09dd29abe46dfe240adcc029e
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170847"
---
# <a name="create-measures-with-measure-builder"></a>Crea medidas co creador de medidas

O creador de medidas permítelle definir cálculos mediante operadores matemáticos, funcións de agregación e filtros. Definir medidas utilizando atributos de entidades relacionadas co unificado *Cliente* entidade.

A creación de medidas en ambientes B-to-C e B-to-B funciona do mesmo xeito. Non obstante, se o teu ambiente B-to-B [usa contas con xerarquías](relationships.md#set-up-account-hierarchies), escolla se quere agregar a medida en subcontas relacionadas.

# <a name="individual-consumers-b-to-c"></a>[Consumidores individuais (B2C)](#tab/b2c)

Crear medidas a nivel de clientes individuais (atributo de cliente, medida de cliente) ou a nivel de empresa/organización (medida de negocio). Os atributos do cliente e a medida do cliente permítenche facer un seguimento do rendemento por cliente. Por exemplo, o gasto total de cada cliente. As medidas das empresas seguen o rendemento por empresa. Por exemplo, os ingresos totais da empresa.

- Atributo do cliente: xera a saída como un novo atributo, que se garda como unha nova columna na entidade xerada polo sistema chamada *Medida_cliente*. Ao actualizar un atributo de cliente, todos os outros atributos de cliente no *Medida_cliente* actualizar a entidade simultaneamente. Ademais, os atributos do cliente móstranse na tarxeta do perfil do cliente. Unha vez executado ou gardado, non podes cambiar un atributo de cliente por unha medida de cliente.

- Medida do cliente: xera a saída como a súa propia entidade e non pode cambiala a un atributo de cliente unha vez executada ou gardada. As medidas do cliente non aparecen na tarxeta do perfil do cliente.

- Medida empresarial: xera resultados como a súa propia entidade e móstrase na páxina de inicio do seu contorno de Customer Insights.

1. Ir a **Medidas**.

1. Seleccione **Novo** > **Construír o seu propio**.

   :::image type="content" source="media/measure-b2c.png" alt-text="Pantalla de configuración baleira para unha medida B-to-C." lightbox="media/measure-b2c.png":::

1. Seleccione **Editar detalles** xunto a Medida sen título. Proporcione un nome para a medida. Opcionalmente, engadir [etiquetas](work-with-tags-columns.md#manage-tags) á medida.

   :::image type="content" source="media/measures_edit_details.png" alt-text="Cadro de diálogo Editar detalles.":::

1. Seleccione **Feito**.

1. Para facer un seguimento do rendemento a nivel empresarial, alterna **Tipo de medida** a **Nivel empresarial**. **Nivel cliente** está seleccionado por defecto. **Nivel cliente** engade automaticamente o *ID de cliente* atribuír a Dimensións mentres **Nivel empresarial** elimínao automaticamente.

1. Na área de configuración, escolla a función de agregación de **Seleccione función** menú despregable. As funcións de agregación inclúen:
   - **Suma**
   - **Media**
   - **Número total**
   - **Número único**
   - **Máx.**
   - **Min**
   - **Primeiro**: toma o primeiro valor do rexistro de datos
   - **Último**: toma o último valor que se engadiu ao rexistro de datos
   - **ArgMax** : atopa o rexistro de datos que dá o valor máximo dunha función de destino
   - **ArgMin** : atopa o rexistro de datos que proporciona o valor mínimo dunha función de destino

1. Seleccione **Engadir atributo** para seleccionar os datos para crear esta medida.

   1. Seleccione o separador **Atributos**.
   1. Entidade de datos: escolla a entidade que inclúe o atributo que desexa medir.
   1. Atributo de datos: escolla o atributo que desexa usar na función de agregación para calcular a medida. Só pode seleccionar un atributo de cada vez.
   1. Opcionalmente, escolla un atributo de datos dunha medida existente seleccionando o **Medidas** ou buscar un nome de entidade ou medida.
   1. Seleccione **Engadir**.

1. Para crear medidas máis complexas, engade máis atributos ou utiliza operadores matemáticos na función de medida.

1. Para engadir filtros, seleccione o **Filtro** na área de configuración. Ao aplicar filtros só se utilizarán os rexistros que coincidan cos filtros para calcular a medida.
  
   1. Na sección **Engadir atributo** do panel **Filtros**, seleccione o atributo que desexa usar para crear filtros.
   1. Configure os operadores de filtros para definir o filtro para cada atributo seleccionado.
   1. Seleccione **Aplicar**.

1. Seleccione **Dimensión** para escoller máis campos para engadir como columnas á entidade de saída da medida.

   1. Seleccione **Editar dimensións** para engadir atributos de datos polos que desexa agrupar os valores da medida. Por exemplo, cidade ou sexo.
      > [!TIP]
      > Se seleccionaches **Nivel cliente** como o **Tipo de medida** o *ID de cliente* o atributo xa está engadido. Se eliminas o atributo, **Tipo de medida** alterna a **Nivel empresarial**.
   1. Seleccione **Feito**.

1. Se hai valores nos seus datos que deben substituírse por un número enteiro, seleccione **Regras**. Configure a regra e asegúrese de que escolle só números enteiros como substitutos. Por exemplo, substitúa *nulo* por *0*.

1. Se hai varias rutas entre a entidade de datos que mapeou e o *Cliente* entidade, escolla unha das identificadas [camiños de relación coa entidade](relationships.md). Os resultados das medidas poden variar dependendo do camiño seleccionado.

   1. Seleccione **Camiño de relación** e elixa o camiño da entidade que se debería empregar para identificar a súa medida. Se só hai un único camiño cara á entidade *Cliente*, este control non se amosará.
   1. Seleccione **Feito**.

1. Para engadir máis cálculos para a medida, seleccione **Novo cálculo**. Use só entidades na mesma ruta da entidade para novos cálculos. Máis cálculos mostraranse como columnas novas na entidade de saída de medida. Opcionalmente, seleccione **Editar nome** para crear un nome para o cálculo.

1. Seleccione os puntos suspensivos verticais (&vellip;) sobre o cálculo a **Duplicar** ou **Quitar** un cálculo a partir dunha medida.

1. Na área **Vista previa**, verá o esquema de datos da entidade de saída de medida, incluídos filtros e dimensións. A vista previa reacciona dinamicamente aos cambios na configuración.

1. Seleccione **Executar** para calcular os resultados da medida configurada. Seleccione **Gardar e pechar** se quere manter a configuración actual e executar a medida máis tarde. O **Medidas** visualización da páxina.

# <a name="business-accounts-b-to-b"></a>[Contas empresariais (B2B)](#tab/b2b)

Crear medidas a nivel de contas individuais (medida do cliente) ou a nivel de todas as contas (medida empresarial).

- Medida do cliente: xera saída como entidade propia. As medidas do cliente non aparecen na tarxeta do perfil do cliente.

- Medida empresarial: xera resultados como a súa propia entidade e móstrase na páxina de inicio do seu contorno de Customer Insights.

1. Ir a **Medidas**.

1. Seleccione **Nova**.

   :::image type="content" source="media/measure-b2b.png" alt-text="Pantalla de configuración baleira para unha medida B-to-B.":::

1. Seleccione **Editar detalles** xunto a Medida sen título. Proporcione un nome para a medida. Opcionalmente, engadir [etiquetas](work-with-tags-columns.md#manage-tags) á medida. 
   :::image type="content" source="media/measures_edit_details.png" alt-text="Cadro de diálogo Editar detalles.":::

1. Seleccione **Feito**.

1. Na área de configuración, escolla a función de agregación de **Seleccione función** menú despregable. As funcións de agregación inclúen:
   - **Suma**
   - **Media**
   - **Número total**
   - **Número único**
   - **Máx.**
   - **Min**
   - **Primeiro**: toma o primeiro valor do rexistro de datos
   - **Último**: toma o último valor que se engadiu ao rexistro de datos

1. Seleccione **Engadir atributo** para seleccionar os datos para crear esta medida.

   1. Seleccione o separador **Atributos**.
   1. Entidade de datos: escolla a entidade que inclúe o atributo que desexa medir.
   1. Atributo de datos: escolla o atributo que desexa usar na función de agregación para calcular a medida. Só pode seleccionar un atributo de cada vez.
   1. Opcionalmente, escolla un atributo de datos dunha medida existente seleccionando o **Medidas** ou buscar un nome de entidade ou medida.
   1. Seleccione **Engadir** para engadir o atributo seleccionado á medida.

1. Para crear medidas máis complexas, engade máis atributos ou utiliza operadores matemáticos na función de medida.

1. Para engadir filtros, seleccione o **Filtro** na área de configuración. Ao aplicar filtros só se utilizarán os rexistros que coincidan cos filtros para calcular a medida.
  
   1. Na sección **Engadir atributo** do panel **Filtros**, seleccione o atributo que desexa usar para crear filtros.
   1. Configure os operadores de filtros para definir o filtro para cada atributo seleccionado.
   1. Seleccione **Aplicar** para engadir os filtros á medida.

1. Seleccione **Dimensión** para escoller máis campos para engadir como columnas á entidade de saída da medida.

   1. Seleccione **Editar dimensións** para engadir atributos de datos polos que desexa agrupar os valores da medida. Por exemplo, cidade ou sexo.
      > [!TIP]
      > O *ID de cliente* xa se engadiu o atributo que indica que se trata dun tipo de medida a nivel de cliente. Se elimina o atributo, o tipo de medida cambia ao nivel empresarial.
   1. Seleccione **Feito** para engadir as dimensións á medida.

1. Se hai valores nos seus datos que deben substituírse por un número enteiro, seleccione **Regras**. Configure a regra e asegúrese de que escolle só números enteiros como substitutos. Por exemplo, substitúa *nulo* por *0*.

1. Se [utilizar contas con xerarquías](relationships.md#set-up-account-hierarchies), revisión **Agrega subcontas**.
   - Se está fixado en **Desactivado**, a medida calcúlase para cada conta. Cada conta obtén o seu propio resultado.
   - Se está fixado en **Activado**, seleccione **Editar** para escoller a xerarquía de contas segundo as xerarquías inxeridas. A medida só producirá un resultado porque está agregada a subcontas.

1. Se hai varias rutas entre a entidade de datos que mapeou e o *Cliente* entidade, escolla unha das identificadas [camiños de relación coa entidade](relationships.md). Os resultados das medidas poden variar dependendo do camiño seleccionado.

   1. Seleccione **Camiño de relación** e elixa o camiño da entidade que se debería empregar para identificar a súa medida. Se só hai un único camiño cara á entidade *Cliente*, este control non se amosará.
   1. Seleccione **Feito** para aplicar a súa selección.

1. Seleccione os puntos suspensivos verticais (&vellip;) sobre o cálculo a **Duplicar** ou **Quitar** un cálculo a partir dunha medida.

1. Na área **Vista previa**, verá o esquema de datos da entidade de saída de medida, incluídos filtros e dimensións. A vista previa reacciona dinamicamente aos cambios na configuración.

1. Seleccione **Executar** para calcular os resultados da medida configurada. Seleccione **Gardar e pechar** se quere manter a configuración actual e executar a medida máis tarde. O **Medidas** visualización da páxina.

---

## <a name="next-step"></a>Seguinte paso

Use as medidas existentes para crear [un segmento de clientes](segments.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
