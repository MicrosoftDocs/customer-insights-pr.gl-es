---
title: Crear e xestionar segmentos
description: Cree segmentos de clientes para agrupalos en función de varios atributos.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: jimsonc
manager: shellyha
ms.openlocfilehash: 6931110c2ae93cd2792d319aa5a34f0df3088552
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405745"
---
# <a name="create-and-manage-segments"></a>Crear e xestionar segmentos

Os segmentos permiten agrupar aos seus clientes en función de atributos demográficos, transaccionais ou de comportamento. Pode usar segmentos para ter como obxectivo campañas promocionais, actividades de venda e accións de asistencia ao cliente para alcanzar os obxectivos da súa empresa.

Pode definir filtros complexos arredor da entidade de Perfil do cliente e das entidades relacionadas. Cada segmento, despois do procesamento, crea un conxunto de rexistros de clientes que pode exportar e nos que pode tomar medidas. Algúns [límites de servizo](service-limits.md) aplican.

A non ser que se indique o contrario, todos os segmentos son **Segmentos dinámicos**, que se actualizan nunha programación recorrente.

O seguinte exemplo ilustra a capacidade de segmentación. Definimos un segmento para clientes que solicitaron polo menos 500 $ de mercadorías nos últimos 90 días *e* que estiveron involucrados nunha chamada de servizo de atención ao cliente que se escalou.

> [!div class="mx-imgBorder"]
> ![Múltiples grupos](media/segmentation-group1-2.png "Múltiples grupos")

## <a name="create-a-new-segment"></a>Crear un segmento novo

Os segmentos xestionanse na páxina **Segmentos**.

1. Na información do público, vaia á páxina **Segmentos**.

2. Seleccione **Novo** > **Segmento en branco**.

3. No panel **Novo segmento**, escolla un tipo de segmento e proporcione un **Nome**.

   Tamén pode proporcionar un nome para mostrar e unha descrición que axude a identificar o segmento.

4. Seleccione **Seguinte** para chegar á páxina **Construtor de segmentos** onde pode definir un grupo. Un grupo é un conxunto de clientes.

5. Escolla a entidade que inclúe o atributo polo que desexa segmentar.

6. Escolla o atributo polo que segmentar. Este atributo pode ter un dos catro tipos de valor seguintes: numérico, cadea, data ou booleano.

7. Escolla un operador e un valor para o atributo seleccionado.

   > [!div class="mx-imgBorder"]
   > ![Filtro de grupo personalizado](media/customer-group-numbers.png "Filtro de grupo de clientes")

   |Número |Definición  |
   |---------|---------|
   |1     |Entidad          |
   |2     |Atributo          |
   |3    |Operador         |
   |4    |Valor         |

8. Se a entidade está conectada á entidade de cliente unificada mediante [relacións](relationships.md), necesita definir o camiño da relación para crear un segmento válido. Engada as entidades do camiño da relación ata que poida seleccionar a entidade **Cliente: CustomerInsights** no menú despregable. A continuación, elixa **Todos os rexistros** para cada condición.

   > [!div class="mx-imgBorder"]
   > ![Camiño de relación durante a creación do segmento](media/segments-multiple-relationships.png "Camiño de relación durante a creación do segmento")

9. Seleccione **Gardar** para gardar o segmento. O teu segmento gardarase e procesarase se todos os requisitos están validados. Se non, gardarase como borrador.

10. Seleccione **Volver a segmentos** para volver á páxina **Segmentos**.

## <a name="manage-existing-segments"></a>Xestionar os segmentos existentes

Na páxina **Segmentos**, pode ver todos os seus segmentos gardados e xestionalos.

Cada segmento está representado por unha fila que inclúe información adicional sobre o segmento.

Pode clasificar os segmentos nunha columna seleccionando a cabeceira da columna.

Use a caixa **Buscar** na esquina superior dereita para filtrar os segmentos.

> [!div class="mx-imgBorder"]
> ![Opcións para xestionar un segmento existente](media/segments-selected-segment.png "Opcións para xestionar un segmento existente")

A seguinte acción está dispoñible cando selecciona un segmento:

- **Visualice** os detalles do segmento, incluída a tendencia do total de membros e unha vista previa dos membros do segmento.
- **Edite** o segmento para cambiar as súas propiedades.
- **Actualice** o segmento para incluír os últimos datos.
- **Active** ou **desactive** o segmento. Os segmentos teñen dous estados posibles: activo ou inactivo. Estes estados son útiles cando se edita un segmento. Para os segmentos inactivos, existe a definición do segmento, pero aínda non contén ningún cliente. Cando activa un segmento, o seu estado cambia de "inactivo" a "activo" e comeza a buscar clientes que coincidan coa definición do segmento. Se a [actualización programada](system.md#schedule-tab) está configurada, os segmentos inactivos teñen o **Estado** indicado como **Omitido**, o que indica que nin sequera se intentou actualizar. Cando se activa un segmento inactivo, actualizarase e incluirase nas actualizacións programadas.
  Alternativamente, pode usar a funcionalidade **Programar máis tarde** no menú despregable **Activar/Desactivar** para especificar unha data e hora futuras para a activación e desactivación dun determinado segmento.
- **Renomee** o segmento.
- **Descargue** a lista de membros como ficheiro .CSV.
- A opción **Engadir a** envía a lista de ID de clientes no segmento para o seu procesamento noutra aplicación.
- **Elimine** o segmento.

## <a name="refresh-segments"></a>Actualizar os segmentos

Pode actualizar todos os segmentos á vez seleccionando **Actualizar todo** na páxina **Segmentos** ou pode actualizar un ou varios segmentos cando os seleccione e elixir **Actualizar** desde as opcións. Tamén pode configurar unha actualización recorrente en **Administrador** > **Sistema** > **Programar**.

> [!TIP]
> Existen [seis tipos de estado](system.md#status-types) para as tarefas ou os procesos. Ademais, a maioría dos procesos [dependen doutros procesos descendentes](system.md#refresh-policies). Pode seleccionar o estado dun proceso para ver detalles sobre o progreso de todo o traballo. Despois de seleccionar **Ver detalles** para unha das tarefas do traballo, atopará información adicional: o tempo de procesamento, a última data de procesamento e todos os erros e avisos asociados á tarefa.

## <a name="download-and-export-segments"></a>Descargar e exportar segmentos

Pode descargar os seus segmentos a un ficheiro CSV ou exportalos a Dynamics 365 Sales.

### <a name="download-segments-to-a-csv-file"></a>Descargar segmentos a un ficheiro CSV

1. Na información do público, vaia á páxina **Segmentos**.

2. Seleccione os tres puntos no mosaico dun segmento específico.

3. Seleccione **Descargar como CSV** da lista despregable de accións.

### <a name="export-segments-to-dynamics-365-sales"></a>Exportar segmentos a Dynamics 365 Sales

Antes de exportar segmentos a Dynamics 365 Sales, un administrador precisa [crear o destino de exportación](export-destinations.md) para Dynamics 365 Sales.

1. Na información do público, vaia á páxina **Segmentos**.

2. Seleccione os tres puntos no mosaico dun segmento específico.

3. Seleccione **Engadir a** na lista despregable de accións e seleccione o destino de exportación ao que desexa enviar os datos.

## <a name="draft-mode-for-segments"></a>Modo de borrador para segmentos

Se non se cumpren todos os requisitos para procesar un segmento, pode gardar o segmento como borrador e acceder a el desde a páxina **Segmentos**.

Gardarase como segmento inactivo e non se poderá activar ata que sexa válido.

## <a name="add-more-conditions-to-a-group"></a>Engadir máis condicións a un grupo

Para engadir máis condicións a un grupo, pode usar dous operadores lóxicos:

- Operador **AND**: as dúas condicións deben cumprirse como parte do proceso de segmentación. Esta opción é máis útil cando define condicións entre diferentes entidades.

- Operador **OR**: calquera das condicións debe ser cumprida como parte do proceso de segmentación. Esta opción é máis útil cando define varias condicións para a mesma entidade.

   > [!div class="mx-imgBorder"]
   > ![Operador OR onde se debe cumprir calquera das dúas condicións](media/segmentation-either-condition.png "Operador OR onde se debe cumprir calquera das dúas condicións")

Actualmente é posible aniñar un operador **OR** baixo un operador **AND**, pero non ao revés.

## <a name="combine-multiple-groups"></a>Combinar varios grupos

Cada grupo produce un conxunto específico de clientes. Pode combinar estes grupos para incluír os clientes necesarios para a súa empresa.

1. Na información do público, vaia á páxina **Segmentos** e seleccione un segmento.

2. Seleccione **Engadir grupo**.

   > [!div class="mx-imgBorder"]
   > ![Grupo de engadir grupo de clientes](media/customer-group-add-group.png "Grupo de engadir grupo de clientes")

3. Seleccione un dos seguintes operadores de conxunto: **Unión**, **Intersección** ou **Excepto**.

   > [!div class="mx-imgBorder"]
   > ![Unión de engadir grupo de clientes](media/customer-group-union.png "Unión de engadir grupo de clientes")

   Seleccione un operador definido para definir un novo grupo. Garde diferentes grupos para determinar que datos se reteñen:

   - **Unión** une os dous grupos.

   - **Intersección** solapa os dous grupos. Só datos que *son comúns* a ambos os grupos mantéñense no grupo unificado.

   - **Excepto** combina os dous grupos. Só datos do grupo A que *non son comúns* aos datos do grupo B mantéñense.

## <a name="view-processing-history-and-segment-members"></a>Ver o historial de procesamento e os membros do segmento

Pode ver datos consolidados sobre un segmento revisando os seus detalles.

Na páxina **Segmentos**, seleccione o segmento que desexe revisar.

A parte superior da páxina inclúe un gráfico de tendencias que mostra os cambios no total de membros. Pase o punteiro sobre os puntos de datos para ver o total de membros dunha data específica.

Pode actualizar o intervalo temporal da visualización.

> [!div class="mx-imgBorder"]
> ![Intervalo de tempo do segmento](media/segment-time-range.png "Intervalo de tempo do segmento")

A parte inferior contén unha lista dos membros do segmento.

> [!NOTE]
> Os campos que aparecen nesta lista baséanse nos atributos das entidades do seu segmento.
>
>A lista é unha vista previa dos membros do segmento correspondentes e mostra os primeiros 100 rexistros do seu segmento para que poida avalialo rapidamente e revisar as súas definicións se é necesario. Para ver todos os rexistros coincidentes, cómpre [exportar o segmento](export-destinations.md).

## <a name="quick-segments"></a>Segmentos rápidos

Ademais do creador de segmentos, hai outro camiño para crear segmentos. Os segmentos rápidos permítenlle construír segmentos sinxelos cun único operador de forma rápida e con información instantánea.

1. Na páxina **Segmentos**, seleccione **Novo** > **Crear rapidamente desde**.

   - Seleccione a opción **Perfís** para construír un segmento baseado na entidade de cliente unificada.
   - Seleccione a opción **Medicións** para crear un segmento arredor de cada un dos tipos de medidas do atributo de cliente que creou anteriormente na páxina **Medicións**.
   - Seleccione a opción **Intelixencia** para construír un segmento arredor dunha das entidades de saída que xerou usando calquera das funcións de **Predicións** ou **Modelos personalizados**.

2. Na caixa de diálogo **Novo segmento rápido**, seleccione un atributo no menú despregable **Campo**.

3. O sistema proporcionará información adicional que lle axudará a crear mellores segmentos dos seus clientes.
   - Por campos categóricos, mostraremos as 10 contas máis importantes de clientes. Escolla un **Valor** e seleccione **Revisar**.

   - Para un atributo numérico, o sistema mostrará que valor de atributo está no percentil de cada cliente. Elixa un **Operador** e un **Valor** e logo seleccione **Revisar**.

4. O sistema forneceralle un **Tamaño de segmento estimado**. Pode escoller se quere xerar o segmento que definiu ou primeiro revisalo para obter un tamaño de segmento diferente.

    > [!div class="mx-imgBorder"]
    > ![Nome e estimación para un segmento rápido](media/quick-segment-name.png "Nome e estimación para un segmento rápido")

5. Proporcione un **Nome** para o segmento. Tamén pode fornecer un **nome para mostrar**.

6. Seleccione **Gardar** para crear o seu segmento.

7. Despois de que o segmento remate de procesarse, pode visualizalo como calquera outro segmento que crease.

Para as seguintes situacións, aconsellamos usar o creador de segmentos en lugar da capacidade de segmentos recomendada:

- Creación de segmentos con filtros en campos categóricos nos que o operador é diferente de **IS**
- Creación de segmentos con filtros en campos numéricos nos que o operador é diferente de **Between**, **Greater than** e **Less than**
- Creación de segmentos con filtros en campos de tipo de data

## <a name="next-steps"></a>Seguintes pasos

[Exporte un segmento](export-destinations.md) e explore a [Tarxeta de cliente](customer-card-add-in.md) e os [conectores](export-power-bi.md) para obter información sobre o nivel de cliente.
