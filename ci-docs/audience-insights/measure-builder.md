---
title: Crea novas medidas co creador de medidas
description: Crea medidas desde cero para analizar métricas clave sobre a túa empresa.
ms.date: 02/28/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-measure-builder
- customerInsights
ms.openlocfilehash: 5329aea240ba40ec8698b3ddeb67fb5f21c62bbd
ms.sourcegitcommit: cf6a0ed44915908a44c70889a2dd199a9d0d4798
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 02/28/2022
ms.locfileid: "8359947"
---
# <a name="use-measure-builder-to-create-measures-from-scratch"></a>Usa o creador de medidas para crear medidas desde cero

Este artigo explica como crear un novo [medida](measures.md) dende cero. O creador de medidas permíteche definir cálculos mediante operadores matemáticos, funcións de agregación e filtros. Podes construír unha medida con atributos de entidades relacionadas co unificado *Cliente* entidade. 

A creación de medidas en ambientes B-to-C e B-to-B funciona do mesmo xeito. Non obstante, se es un ambiente B-to-B [utiliza contas con xerarquías](relationships.md#set-up-account-hierarchies), pode optar por agregar a medida en subcontas relacionadas.

Tamén pode crear rapidamente unha medida escollendo entre un conxunto de medidas de uso habitual e predefinidas. Para obter máis información, consulte [Use un modelo para construír unha medida](measure-templates.md).

# <a name="individual-consumers-b-to-c"></a>[Consumidores individuais (B2C)](#tab/b2c)

Podes crear medidas a nivel de clientes individuais (atributo de cliente, medida de cliente) ou a nivel de empresa/organización (medida de negocio). O atributo do cliente e a medida do cliente son dous tipos que che permiten facer un seguimento do rendemento por cliente. Por exemplo, o gasto total de cada cliente. As medidas empresariais permítenche facer un seguimento do rendemento por empresa. Por exemplo, os ingresos totais da empresa.

- Atributo do cliente: xera a saída como un novo atributo, que se garda como unha nova columna na entidade xerada polo sistema chamada *Medida_cliente*. Ao actualizar un atributo de cliente, todos os outros atributos de cliente no *Medida_cliente* actualizar a entidade simultaneamente. Ademais, os atributos do cliente móstranse na tarxeta do perfil do cliente. Unha vez executado ou gardado, o atributo de cliente non pode cambialo a unha medida de cliente.

- Medida do cliente: xera saída como a súa propia entidade e non pode cambiala a un atributo de cliente unha vez executada ou gardada. As medidas do cliente non aparecen na tarxeta do perfil do cliente.

- Medida empresarial: xera resultados como a súa propia entidade e móstrase na páxina de inicio do seu contorno de Customer Insights.

1. Ir a **Medidas**.

1. Seleccione **Nova** e elixa **Construír unha propia**.

   :::image type="content" source="media/measure-b2c.png" alt-text="Pantalla de configuración baleira para unha medida B-to-C.":::

1. Seleccione **Editar nome** e proporcione un **Nome** para a medida. 

1. Na área de configuración, escolla a función de agregación de **Seleccione a función** menú despregable. As funcións de agregación inclúen: 
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

1. Seleccione **Engadir atributo** para seleccionar os datos que precisa para crear esta medida.
   
   1. Seleccione o separador **Atributos**. 
   1. Entidade de datos: escolla a entidade que inclúe o atributo que desexa medir. 
   1. Atributo de datos: escolla o atributo que desexa usar na función de agregación para calcular a medida. Só pode seleccionar un atributo de cada vez.
   1. Tamén pode seleccionar un atributo de datos dunha medida existente seleccionando o separador **Medidas** ou pode buscar un nome de entidade ou medida. 
   1. Seleccione **Engadir** para engadir o atributo seleccionado á medida.

1. Para construír medidas máis complexas, pode engadir máis atributos ou usar operadores matemáticos na súa función de medida.

1. Para engadir filtros, seleccione o **Filtro** na área de configuración. Ao aplicar filtros só se utilizarán os rexistros que coincidan cos filtros para calcular a medida.
  
   1. Na sección **Engadir atributo** do panel **Filtros**, seleccione o atributo que desexa usar para crear filtros.
   1. Configure os operadores de filtros para definir o filtro para cada atributo seleccionado.
   1. Seleccione **Aplicar** para engadir os filtros á medida.

1. Seleccione **Dimensión** para escoller máis campos que se engaden como columnas á entidade de saída da medida.
 
   1. Seleccione **Editar dimensións** para engadir atributos de datos polos que desexa agrupar os valores da medida. Por exemplo, cidade ou sexo. Por defecto, a dimensión *CustomerID* seleccionouse para crear *medidas a nivel de cliente*. Pode eliminar a dimensión predeterminada se quere crear *medidas a nivel empresarial*.
   1. Seleccione **Feito** para engadir as dimensións á medida.

1. Se hai valores nos seus datos que debe substituír por un enteiro, seleccione **Regras**. Configure a regra e asegúrese de que escolle só números enteiros como substitutos. Por exemplo, substitúa *nulo* por *0*.

1. Se hai varias rutas entre a entidade de datos que asignou e a entidade *Cliente*, ten que escoller un dos [camiños de relación de entidade](relationships.md) identificados. Os resultados das medidas poden variar dependendo do camiño seleccionado. 
   
   1. Seleccione **Camiño de relación** e elixa o camiño da entidade que se debería empregar para identificar a súa medida. Se só hai un único camiño cara á entidade *Cliente*, este control non se amosará.
   1. Seleccione **Feito** para aplicar a súa selección. 

1. Para engadir máis cálculos para a medida, seleccione **Novo cálculo**. Só pode usar entidades na mesma ruta de entidade para novos cálculos. Máis cálculos mostraranse como columnas novas na entidade de saída de medida.

1. Seleccione **...** sobre o cálculo para **Duplicar**, **Cambiar o nome** ou **Quitar** un cálculo dunha medida.

1. Na área **Vista previa**, verá o esquema de datos da entidade de saída de medida, incluídos filtros e dimensións. A vista previa reacciona dinamicamente aos cambios na configuración.

1. Seleccione **Executar** para calcular os resultados da medida configurada. Seleccione **Gardar e pechar** se quere manter a configuración actual e executar a medida máis tarde.

1. Vaia a **Medidas** para ver na lista a medida recentemente creada.

# <a name="business-accounts-b-to-b"></a>[Contas empresariais (B2B)](#tab/b2b)


Podes crear medidas a nivel de contas individuais (medida do cliente) ou a nivel de todas as contas (medida empresarial). 

- Medida do cliente: xera saída como entidade propia. As medidas do cliente non aparecen na tarxeta do perfil do cliente.

- Medida empresarial: xera resultados como a súa propia entidade e móstrase na páxina de inicio do seu contorno de Customer Insights.

1. Ir a **Medidas**.

1. Seleccione **Nova**.

   :::image type="content" source="media/measure-b2b.png" alt-text="Pantalla de configuración baleira para unha medida B-to-B.":::

1. Seleccione **Editar nome** e proporcione un **Nome** para a medida. 

1. Na área de configuración, escolla a función de agregación de **Seleccione a función** menú despregable. As funcións de agregación inclúen: 
   - **Suma**
   - **Media**
   - **Número total**
   - **Número único**
   - **Máx.**
   - **Min**
   - **Primeiro**: toma o primeiro valor do rexistro de datos
   - **Último**: toma o último valor que se engadiu ao rexistro de datos

1. Seleccione **Engadir atributo** para seleccionar os datos que precisa para crear esta medida.
   
   1. Seleccione o separador **Atributos**. 
   1. Entidade de datos: escolla a entidade que inclúe o atributo que desexa medir. 
   1. Atributo de datos: escolla o atributo que desexa usar na función de agregación para calcular a medida. Só pode seleccionar un atributo de cada vez.
   1. Tamén pode seleccionar un atributo de datos dunha medida existente seleccionando o separador **Medidas** ou pode buscar un nome de entidade ou medida. 
   1. Seleccione **Engadir** para engadir o atributo seleccionado á medida.

1. Para construír medidas máis complexas, pode engadir máis atributos ou usar operadores matemáticos na súa función de medida.

1. Para engadir filtros, seleccione o **Filtro** na área de configuración. Ao aplicar filtros só se utilizarán os rexistros que coincidan cos filtros para calcular a medida.
  
   1. Na sección **Engadir atributo** do panel **Filtros**, seleccione o atributo que desexa usar para crear filtros.
   1. Configure os operadores de filtros para definir o filtro para cada atributo seleccionado.
   1. Seleccione **Aplicar** para engadir os filtros á medida.

1. Seleccione **Dimensión** para escoller máis campos que se engaden como columnas á entidade de saída da medida.
 
   1. Seleccione **Editar dimensións** para engadir atributos de datos polos que desexa agrupar os valores da medida. Por exemplo, cidade ou sexo. Por defecto, a dimensión *CustomerID* seleccionouse para crear *medidas a nivel de cliente*. Pode eliminar a dimensión predeterminada se quere crear *medidas a nivel empresarial*.
   1. Seleccione **Feito** para engadir as dimensións á medida.

1. Se hai valores nos seus datos que debe substituír por un enteiro, seleccione **Regras**. Configure a regra e asegúrese de que escolle só números enteiros como substitutos. Por exemplo, substitúa *nulo* por *0*.

1. Pode usar **Inscribir subcontas** se [usa contas con xerarquías](relationships.md#set-up-account-hierarchies).
   - Se está fixado en **Desactivado**, a medida calcúlase para cada conta. Cada conta faise obtén o seu propio resultado.
   - Se está fixado en **Activado**, seleccione **Editar** para escoller a xerarquía de contas segundo as xerarquías inxeridas. A medida só producirá un resultado porque se agrega con subcontas.

1. Se hai varias rutas entre a entidade de datos que asignou e a entidade *Cliente*, ten que escoller un dos [camiños de relación de entidade](relationships.md) identificados. Os resultados das medidas poden variar dependendo do camiño seleccionado. 
   
   1. Seleccione **Camiño de relación** e elixa o camiño da entidade que se debería empregar para identificar a súa medida. Se só hai un único camiño cara á entidade *Cliente*, este control non se amosará.
   1. Seleccione **Feito** para aplicar a súa selección. 

1. Seleccione **...** sobre o cálculo para **Duplicar**, **Cambiar o nome** ou **Quitar** un cálculo dunha medida.

1. Na área **Vista previa**, verá o esquema de datos da entidade de saída de medida, incluídos filtros e dimensións. A vista previa reacciona dinamicamente aos cambios na configuración.

1. Seleccione **Executar** para calcular os resultados da medida configurada. Seleccione **Gardar e pechar** se quere manter a configuración actual e executar a medida máis tarde.

1. Vaia a **Medidas** para ver na lista a medida recentemente creada.

---