---
title: Crear e xestionar medidas
description: Defina medidas para analizar e reflectir o rendemento da súa empresa.
ms.date: 02/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 202ea22d290be04e54ce9676b6b693162354607f
ms.sourcegitcommit: d3eb07dcc72624a2d5cfc95c7ea9faaa2c1b6001
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 03/16/2021
ms.locfileid: "5654730"
---
# <a name="define-and-manage-measures"></a>Definir e xestionar medidas

As medidas axudan a comprender mellor o comportamento dos clientes e o rendemento empresarial recuperando valores relevantes de [perfís unificados](data-unification.md). Por exemplo, unha empresa quere ver o *gasto total por cliente* para comprender o historial de compras de cada cliente. Ou medir as *vendas totais da empresa* para comprender os ingresos a nivel agregado en todo o negocio.  

As medidas créanse usando o creador de medidas, unha plataforma de consulta de datos con varios operadores e sinxelas opcións de asignación. Permite filtrar os datos, agrupar resultados, detectar [camiños de relación de entidade](relationships.md) e previsualizar os resultados.

Use o creador de medidas para planificar actividades comerciais consultando datos de clientes e extraendo información. Por exemplo, crear unha medida de *gasto total por cliente* e *devolución total por cliente* axuda a identificar un grupo de clientes cun gasto elevado pero cunha devolución elevada. Pode [crear un segmento](segments.md) para impulsar as accións subseguintes máis axeitadas. 

## <a name="create-a-measure"></a>Crear unha medida

Esta sección móstralle como crear unha nova medida desde cero. Pode construír unha medida con atributos de datos de entidades de datos que teñen unha relación configurada para conectarse coa entidade Cliente. 

1. Na información do público, vaia a **Medidas**.

1. Seleccione **Nova**.

1. Seleccione **Editar nome** e proporcione un **Nome** para a medida. 
   > [!NOTE]
   > Se a súa nova configuración de medida ten só dous campos, por exemplo, CustomerID e un cálculo, o resultado engadirase como nova columna á entidade xerada polo sistema chamada Customer_Measure. E poderá ver o valor da medida no perfil de cliente unificado. Outras medidas xerarán as súas propias entidades.

1. Na área de configuración, escolla a función de agregación no menú despregable **Seleccionar función**. As funcións de agregación inclúen: 
   - **Suma**
   - **Media**
   - **Número total**
   - **Número único**
   - **Máx.**
   - **Min**
   - **Primeiro**: toma o primeiro valor do rexistro de datos
   - **Último**: toma o último valor que se engadiu ao rexistro de datos

   :::image type="content" source="media/measure-operators.png" alt-text="Operadores para cálculos de medidas.":::

1. Seleccione **Engadir atributo** para seleccionar os datos que precisa para crear esta medida.
   
   1. Seleccione o separador **Atributos**. 
   1. Entidade de datos: escolla a entidade que inclúe o atributo que desexa medir. 
   1. Atributo de datos: escolla o atributo que desexa usar na función de agregación para calcular a medida. Só pode seleccionar un atributo de cada vez.
   1. Tamén pode seleccionar un atributo de datos dunha medida existente seleccionando o separador **Medidas**. Ou pode buscar un nome de entidade ou medida. 
   1. Seleccione **Engadir** para engadir o atributo seleccionado á medida.

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Seleccione un atributo para usar nos cálculos.":::

1. Para construír medidas máis complexas, pode engadir máis atributos ou usar operadores matemáticos na súa función de medida.

   :::image type="content" source="media/measure-math-operators.png" alt-text="Cree unha medida complexa con operadores matemáticos.":::

1. Para engadir filtros, seleccione o **Filtro** na área de configuración. 
  
   1. Na sección **Engadir atributo** do panel **Filtros**, seleccione o atributo que desexa usar para crear filtros.
   1. Configure os operadores de filtros para definir o filtro para cada atributo seleccionado.
   1. Seleccione **Aplicar** para engadir os filtros á medida.

1. Para engadir dimensións, seleccione **Dimensión** na área de configuración. As dimensións mostraranse como columnas na entidade de saída de medida.
   1. Seleccione **Editar dimensións** para engadir atributos de datos polos que desexa agrupar os valores da medida. Por exemplo, cidade ou sexo. Por defecto, a dimensión *CustomerID* seleccionouse para crear *medidas a nivel de cliente*. Pode eliminar a dimensión predeterminada se quere crear *medidas a nivel empresarial*.
   1. Seleccione **Feito** para engadir as dimensións á medida.

1. Se hai varias rutas entre a entidade de datos que asignou e a entidade *Cliente*, ten que escoller un dos [camiños de relación de entidade](relationships.md) identificados. Os resultados das medidas poden variar dependendo do camiño seleccionado. 
   1. Seleccione **Preferencias de datos** e elixa o camiño da entidade que se debería empregar para identificar a súa medida. Se só hai un único camiño cara á entidade *Cliente*, este control non se amosará.
   1. Seleccione **Feito** para aplicar a súa selección. 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Seleccione o camiño da entidade para a medida.":::

1. Para engadir máis cálculos para a medida, seleccione **Novo cálculo**. Só pode usar entidades na mesma ruta de entidade para novos cálculos. Máis cálculos mostraranse como columnas novas na entidade de saída de medida.

1. Seleccione **...** sobre o cálculo para **Duplicar**, **Cambiar o nome** ou **Quitar** un cálculo dunha medida.

1. Na área **Vista previa**, verá o esquema de datos da entidade de saída de medida, incluídos filtros e dimensións. A vista previa reacciona dinamicamente aos cambios na configuración.

1. Seleccione **Executar** para calcular os resultados da medida configurada. Seleccione **Gardar e pechar** se quere manter a configuración actual e executar a medida máis tarde.

1. Vaia a **Medidas** para ver na lista a medida recentemente creada.

## <a name="manage-your-measures"></a>Xestionar as súas medidas

Despois de [crear unha medida](#create-a-measure), verá unha lista de medidas na páxina **Medidas**.

Atopará información sobre o tipo de medida, o creador, a data de creación, o estado e o estado. Cando selecciona unha medida da lista, pode previsualizar a saída e descargar un ficheiro .CSV.

Para actualizar todas as túas medidas ao mesmo tempo, seleccione **Actualizar todo** sen seleccionar unha medida específica.

> [!div class="mx-imgBorder"]
> ![Accións para xestionar medidas individuais](media/measure-actions.png "Accións para xestionar medidas individuais")

Seleccione unha medida da lista para as seguintes opcións:

- Seleccione o nome da medida para ver os seus detalles.
- **Editar** a configuración da medida.
- **Actualizar** a medida segundo os últimos datos.
- **Cambiar o nome** da medida.
- **Eliminar** a medida.
- **Activar** ou **Desactivar**. As medidas inactivas non se actualizarán durante unha [actualización programada](system.md#schedule-tab).

> [!TIP]
> Existen [seis tipos de estado](system.md#status-types) para as tarefas ou os procesos. Ademais, a maioría dos procesos [dependen doutros procesos descendentes](system.md#refresh-policies). Pode seleccionar o estado dun proceso para ver detalles sobre o progreso de todo o traballo. Despois de seleccionar **Ver detalles** para unha das tarefas do traballo, atopará información adicional: o tempo de procesamento, a última data de procesamento e todos os erros e avisos asociados á tarefa.

## <a name="next-step"></a>Seguinte paso

Utilice as medidas existentes para crear [un segmento de clientes](segments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]