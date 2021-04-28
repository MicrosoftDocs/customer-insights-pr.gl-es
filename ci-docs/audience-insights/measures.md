---
title: Crear e xestionar medidas
description: Defina medidas para analizar e reflectir o rendemento da súa empresa.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 9a94a32a04f2a8beb661c27271fe96f23d998722
ms.sourcegitcommit: d89b19b2a3497722b78362aeee688ae7e94915d9
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "5887938"
---
# <a name="define-and-manage-measures"></a>Definir e xestionar medidas

As medidas axudan a comprender mellor os comportamentos dos clientes e o rendemento empresarial. Miran valores relevantes de [perfís unificados](data-unification.md). Por exemplo, unha empresa quere ver o *gasto total por cliente* para comprender o historial de compras de cada cliente ou medir as *vendas totais da empresa* para comprender os ingresos agregados de todo o negocio.  

As medidas créanse usando o creador de medidas, unha plataforma de consulta de datos con varios operadores e sinxelas opcións de asignación. Permite filtrar os datos, agrupar resultados, detectar [camiños de relación de entidade](relationships.md) e previsualizar os resultados.

Use o creador de medidas para planificar actividades comerciais consultando datos de clientes e extraendo información. Por exemplo, crear unha medida de *gasto total por cliente* e *devolución total por cliente* axuda a identificar un grupo de clientes cun gasto elevado pero cunha devolución elevada. Pode [crear un segmento](segments.md) para impulsar as accións subseguintes máis axeitadas. 

## <a name="build-your-own-measure-from-scratch"></a>Compilar a súa propia medida desde cero

Esta sección móstralle como crear unha nova medida desde cero. Pode construír unha medida con atributos de datos de entidades de datos que teñen unha relación configurada para conectarse coa entidade Cliente. 

1. Na información do público, vaia a **Medidas**.

1. Seleccione **Nova** e elixa **Construír unha propia**.

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

1. Se hai valores nos seus datos que debe substituír por un número enteiro, por exemplo, substituír *cero* por *0*, seleccione **Regras**. Configure a regra e asegúrese de que escolle só números enteiros como substitutos.

1. Se hai varias rutas entre a entidade de datos que asignou e a entidade *Cliente*, ten que escoller un dos [camiños de relación de entidade](relationships.md) identificados. Os resultados das medidas poden variar dependendo do camiño seleccionado. 
   1. Seleccione **Preferencias de datos** e elixa o camiño da entidade que se debería empregar para identificar a súa medida. Se só hai un único camiño cara á entidade *Cliente*, este control non se amosará.
   1. Seleccione **Feito** para aplicar a súa selección. 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Seleccione o camiño da entidade para a medida.":::

1. Para engadir máis cálculos para a medida, seleccione **Novo cálculo**. Só pode usar entidades na mesma ruta de entidade para novos cálculos. Máis cálculos mostraranse como columnas novas na entidade de saída de medida.

1. Seleccione **...** sobre o cálculo para **Duplicar**, **Cambiar o nome** ou **Quitar** un cálculo dunha medida.

1. Na área **Vista previa**, verá o esquema de datos da entidade de saída de medida, incluídos filtros e dimensións. A vista previa reacciona dinamicamente aos cambios na configuración.

1. Seleccione **Executar** para calcular os resultados da medida configurada. Seleccione **Gardar e pechar** se quere manter a configuración actual e executar a medida máis tarde.

1. Vaia a **Medidas** para ver na lista a medida recentemente creada.

## <a name="use-a-template-to-build-a-measure"></a>Usar un modelo para construír unha medida

Pode usar modelos predefinidos de medidas de uso común para crealas. As descricións detalladas dos modelos e unha experiencia guiada axúdanlle a crear medidas eficientes. Os modelos baséanse en datos asignados da entidade *Actividade unificada*. Asegúrese de que configurou [actividades do cliente](activities.md) antes de crear unha medida a partir dun modelo.

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

O seguinte procedemento describe os pasos para construír unha nova medida mediante un modelo.

1. Na información do público, vaia a **Medidas**.

1. Seleccione **Novo** e logo seleccione **Escoller un modelo**.

   :::image type="content" source="media/measure-use-template.png" alt-text="Captura de pantalla do menú despregable cando se crea unha nova medida con fincapé no modelo.":::

1. Busque o modelo que se adapte ás súas necesidades e seleccione **Escoller modelo**.

1. Revise os datos requiridos e seleccione **Comezar** se ten todos os datos no seu lugar.

1. No panel **Editar nome**, estableza o nome da medida e a entidade de saída. 

1. Seleccione **Feito**.

1. Na sección **Establecer o período de tempo**, defina o período de tempo dos datos que se van usar. Escolla se desexa que a nova medida abranga todo o conxunto de datos seleccionando **Todo o tempo**. Ou se quere que a medida se centre nun **Período de tempo específico**.

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Captura de pantalla que mostra a sección do período de tempo ao configurar unha medida a partir dun modelo.":::

1. Na seguinte sección, seleccione **Engadir datos** para escoller as actividades e asignar os datos correspondentes da súa entidade *Actividade unificada*.

    1. Paso 1 de 2: en **Tipo de actividade**, escolla o tipo de entidade que desexa empregar. Para **Actividades**, seleccione as entidades que desexa asignar.
    1. Paso 2 de 2: escolla o atributo da entidade *Actividade unificada* para o compoñente requirido pola fórmula. Por exemplo, para o valor medio da transacción, é o atributo que representa o valor da transacción. Para **Marca de tempo da actividade**, escolla o atributo da entidade de actividade unificada que representa a data e hora da actividade.
   
1. Unha vez que a asignación de datos teña éxito, pode ver o estado como **Completo** e o nome das actividades e atributos asignados.

   :::image type="content" source="media/measure-template-configured.png" alt-text="Captura de pantalla dunha configuración do modelo de medida completa.":::

1. Agora pode seleccionar **Executar** para calcular os resultados da medida. Para refinalo máis tarde, selecciona **Gardar borrador**.

## <a name="manage-your-measures"></a>Xestionar as súas medidas

Pode atopar a lista de medidas na páxina **Medidas**.

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