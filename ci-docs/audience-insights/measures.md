---
title: Crear e editar medidas
description: Definir medidas relacionadas co cliente para analizar e reflectir o rendemento de determinadas áreas comerciais.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 0e214a6eb66abd27f7292db3ce2c2a6e16a8ff33
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405736"
---
# <a name="define-and-manage-measures"></a>Definir e xestionar medidas

**Medidas** representan indicadores clave de rendemento (KPI) que reflicten o rendemento e a estado de determinadas áreas comerciais. As estadísticas do público ofrecen unha experiencia intuitiva para crear diferentes tipos de medidas, usando un creador de consultas que non require que codifique nin valide as medidas manualmente. Pode realizar un seguimento das súas medidas comerciais na páxina **Inicio**. Consulte as medidas para clientes específicos en **Tarxeta de cliente** e use medidas para definir segmentos de clientes na páxina **Segmentos**.

## <a name="create-a-measure"></a>Crear unha medida

Esta sección inclúe información detallada sobre como crear unha medida dende cero. Pode crear medidas con datos de varias orixes de datos conectadas a través da entidade de cliente. Algúns [límites de servizo](service-limits.md) aplican.

1. Na información do público, vaia a **Medidas**.

2. Seleccione **Medida nova**.

3. Elixa o **Tipo** de medida:

   - **Atributo de cliente**: un único campo por cliente que reflicte unha puntuación, valor ou estado para o cliente. Os atributos de cliente créanse como atributos nunha nova entidade xerada polo sistema chamada **Customer_Measure**.

   - **Medida do cliente**: información do comportamento do cliente con desglose por dimensións seleccionadas. Xérase unha nova entidade para cada medida, posiblemente con varios rexistros por cliente.

   - **Medida comercial**: realiza un seguimento do seu rendemento comercial e da saúde da súa empresa. As medidas comerciais poden ter dous resultados diferentes: un resultado numérico que se mostra na páxina de **Inicio** ou unha nova entidade que atopará na páxina **Entidades**.

4. Proporcione un **Nome** e un **Nome para mostrar** opcional e logo seleccione **Seguinte**.

5. Na sección **Entidades**, seleccione a primeira entidade da lista despregable. Neste momento, ten que decidir se son necesarias entidades adicionais como parte da súa definición de medida.

   > [!div class="mx-imgBorder"]
   > ![Definición da medida](media/measure-definition.png "Definición da medida")

   Para engadir máis entidades, seleccione **Engadir entidade** e seleccione as entidades que desexe usar para a medida.

   > [!NOTE]
   > Só pode seleccionar as entidades que teñen relacións coa entidade inicial. Para obter máis información acerca da definición de relacións, consulte [Relacións](relationships.md).

6. Tamén pode configurar variables. Na sección **Variables**, seleccione **Nova variable**.

   As variables son cálculos que se realizan en cada un dos rexistros seleccionados. Por exemplo, sumar o punto de venda (POS) e as vendas en liña para cada un dos rexistros dos seus clientes.

7. Proporcione un **Nome** para a variable.

8. Na zona **Expresión**, escolla un campo co que comezar o seu cálculo.

9. Escriba unha expresión na zona **Expresión** escollendo máis campos para incluír no seu cálculo.

   > [!NOTE]
   > Actualmente só se admiten expresións aritméticas. Ademais, o cálculo de variables non é compatible con entidades de diferentes [camiños de entidade](relationships.md).

10. Seleccione **Feito**.

11. Na sección **Definición da medida**, definirá como se suman as súas entidades escollidas e as variables calculadas nunha nova entidade ou atributo de medida.

12. Seleccione **Nova dimensión**. Pode pensar nunha dimensión como unha función de *agrupar por*. A saída de datos da súa entidade ou atributo de medida agruparase por parte de todas as súas dimensións definidas.

    > [!div class="mx-imgBorder"]
    > ![Elixa un ciclo agregado](media/measures-businessreport-measure-definition2.png "Elixa un ciclo agregado")

    Seleccione ou introduza a seguinte información como parte da definición da súa dimensión:

    - **Entidade**: se define unha entidade de medida, debería incluír polo menos un atributo. Se define un atributo de medida, só incluirá un atributo por defecto. Esta selección trata de escoller a entidade que inclúe ese atributo.
    - **Campo**: escolla o atributo específico que se vai incluír na súa entidade ou atributo de medida.
    - **Depósito**: escolla se desexa agregar datos a diario, mensualmente ou anualmente. É unha selección necesaria só se seleccionou un atributo de tipo Data.
    - **Como**: define o nome do seu novo campo.
    - **Nome para mostrar**: define o nome para mostrar do campo.

    > [!NOTE]
    > A súa medida comercial gardarase como unha entidade dun só número e aparecerá na páxina **Inicio** a menos que engada máis dimensións á súa medida. Despois de engadir máis dimensións, a medida *non* aparecerá na páxina **Inicio**.

13. Tamén pode engadir funcións de agregación. Calquera agregación que cree terá como resultado un novo valor dentro da súa entidade ou atributo de Medida. As funcións de agregación compatibles son: **Min**, **Max**, **Average**, **Median**, **Sum**, **Count Unique**, **First** (toma o primeiro rexistro dun valor de dimensión) e **Last** (toma o último rexistro engadido a un valor de dimensión).

14. Seleccione **Gardar** para aplicar os cambios á medida.

## <a name="manage-your-measures"></a>Xestionar as súas medidas

Despois de crear polo menos unha medida, verá unha lista de medidas na páxina **Medidas**.

Atopará información sobre o tipo de medida, o creador, a data e hora da creación, a data e hora da última edición, o estado (se a medida está activa, inactiva ou fallou) e a última data e hora de actualización. Cando seleccione unha medida da lista, poderá ver unha vista previa da súa saída.

Para actualizar todas as túas medidas ao mesmo tempo, seleccione **Actualizar todo** sen seleccionar unha medida específica.

> [!div class="mx-imgBorder"]
> ![Accións para xestionar medidas individuais](media/measure-actions.png "Accións para xestionar medidas individuais")

Tamén pode seleccionar unha medida da lista e realizar unha das seguintes accións:

- Seleccione o nome da medida para ver os seus detalles.
- **Editar** a configuración da medida.
- **Cambiar o nome** da medida.
- **Eliminar** a medida.
- Seleccione os tres puntos (...) e logo **Actualice** para iniciar o proceso de actualización para a medida.
- Seleccione os tres puntos (...) e logo **Descargar** para obter un ficheiro .CSV da medida.

> [!TIP]
> Existen [seis tipos de estado](system.md#status-types) para as tarefas ou os procesos. Ademais, a maioría dos procesos [dependen doutros procesos descendentes](system.md#refresh-policies). Pode seleccionar o estado dun proceso para ver detalles sobre o progreso de todo o traballo. Despois de seleccionar **Ver detalles** para unha das tarefas do traballo, atopará información adicional: o tempo de procesamento, a última data de procesamento e todos os erros e avisos asociados á tarefa.

## <a name="next-step"></a>Seguinte paso

Pode empregar as medidas existentes para crear o seu primeiro segmento de cliente na páxina **Segmentos**. Para obter máis información, consulte [Segmentos](segments.md).
