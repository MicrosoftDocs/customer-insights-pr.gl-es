---
title: Conectar a a Power Query orixe de datos (contén vídeo)
description: Inxerir datos a través de a Power Query conector (contén vídeo).
ms.date: 09/29/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: 4cc7e57dfb0f8d050e91adc441c24e849882f5d8
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609888"
---
# <a name="connect-to-a-power-query-data-source"></a>Conectar a a Power Query orixe de datos

Power Query ofrece un amplo conxunto de conectores para inxerir datos. A maioría destes conectores son compatibles con Dynamics 365 Customer Insights.

Engadir fontes de datos baseadas en Power Query conectores xeralmente segue os pasos descritos nesta sección. Non obstante, dependendo do conector que use, é necesaria unha información diferente. Para obter máis información, consulte a documentación sobre conectores individuais na páxina [Power Query referencia do conector](/power-query/connectors/).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6EK]

## <a name="create-a-new-data-source"></a>Crear unha nova orixe de datos

1. Vaia a **Datos** > **Orixes de datos**.

1. Seleccione **Engadir orixe de datos**.

1. Seleccione **Microsoft Power Query**.

1. Proporcionar a **Nome** e un opcional **Descrición** para o orixe de datos e seleccione **A continuación**.

1. Escolla un dos [conectores dispoñibles](#available-power-query-data-sources). Neste exemplo, seleccionamos o **Texto/CSV** conector.

1. Introduza os detalles requiridos na **Configuración de conexión** para o conector seleccionado e seleccione **Seguinte** para ver unha previsualización dos datos.

1. Seleccione **Transformar datos**.

1. Revisa e perfecciona os teus datos na páxina **Power Query - Editar consultas** páxina. As entidades que os sistemas identificaron na orixe de datos seleccionada aparecen no panel esquerdo.

   :::image type="content" source="media/data-manager-configure-edit-queries.png" alt-text="Editar diálogo de consultas":::

1. Transforma os teus datos. Seleccione unha entidade para editar ou transformar. Use as opcións do Power Query xanela para aplicar transformacións. Cada transformación está listada en **Pasos aplicados**. Power Query ofrece numerosos [transformación preconstruída](/power-query/power-query-what-is-power-query#transformations) opcións.

   > [!IMPORTANT]
   > Recomendamos que use as seguintes transformacións:
   >
   > - Se está inxerindo datos dun ficheiro CSV, a primeira fila a miúdo contén cabeceiras. Ir a **Transformar** e selecciona **Use a primeira fila como cabeceiras**.
   > - Asegúrese de que o tipo de datos estea configurado correctamente e coincida cos datos. Por exemplo, para os campos de data, seleccione un tipo de data.

1. Para engadir entidades adicionais ao teu orixe de datos no **Editar consultas** diálogo, vai a **Casa** e selecciona **Obter datos**. Repita os pasos 5-10 ata engadir todas as entidades para este orixe de datos. Se ten unha base de datos que inclúe varios conxuntos de datos, cada conxunto de datos é a súa propia entidade.

1. Seleccione **Gardar**. O **Fontes de datos** ábrese a páxina mostrando o novo orixe de datos en **Refrescante** estado.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

A carga de datos pode levar moito tempo. Despois dunha actualización exitosa, os datos inxeridos pódense revisar desde o [**Entidades**](entities.md) páxina.

> [!CAUTION]
>
> - Un orixe de datos baseado en Power Query crea a [fluxo de datos en Dataverse](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365). Non cambies o nome dun fluxo de datos no ficheiro Power Platform centro de administración que se usa en Customer Insights. Cambiar o nome dun fluxo de datos provoca problemas coas referencias entre Customer Insights orixe de datos e Dataverse fluxo de datos.
> - Avaliacións concorrentes para Power Query as fontes de datos en Customer Insights teñen o mesmo [límites de actualización como Dataflows en PowerBI.com](/power-query/power-query-online-limits#refresh-limits). Se unha actualización de datos falla porque alcanzou o límite de avaliación, recomendámosche que axustes a programación de actualización para cada fluxo de datos para garantir que as fontes de datos non se procesen ao mesmo tempo.

### <a name="available-power-query-data-sources"></a>Dispoñible Power Query fontes de datos

Vexa o [Power Query referencia do conector](/power-query/connectors/) para obter unha lista de conectores que pode usar para importar datos a Customer Insights.

Conectores cunha marca de verificación **Información do cliente (fluxos de datos)** columnas están dispoñibles para crear novas fontes de datos baseadas Power Query. Revisa a documentación dun conector específico para obter máis información sobre os seus requisitos previos, [limitacións de consulta](/power-query/power-query-online-limits), e outros detalles.

## <a name="add-data-from-on-premises-data-sources"></a>Engadir datos de fontes de datos locais

Admítese a inxestión de datos das fontes de datos local en función de Microsoft Power Platform fluxos de datos (PPDF). Podes activar fluxos de datos en Customer Insights mediante [proporcionando o Microsoft Dataverse URL do entorno](create-environment.md) ao configurar o ambiente.

Fontes de datos que se crean despois de asociar a Dataverse ambiente co uso de Customer Insights [Power Platform fluxos de datos](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) por defecto. Os fluxos de datos admiten conectividade local mediante a pasarela de datos. Pode eliminar e recrear fontes de datos que existían antes de a Dataverse ambiente estaba asociado [usando pasarelas de datos local](/data-integration/gateway/service-gateway-app).

Pasarelas de datos dun existente Power BI ou Power Apps o ambiente estará visible e poderás reutilizalos en Customer Insights se a pasarela de datos e o ambiente Customer Insights están na mesma rexión de Azure. A páxina de fontes de datos mostra ligazóns para ir ao ambiente de Microsoft Power Platform onde pode ver e configurar pasarelas de datos locais.

> [!IMPORTANT]
> Asegúrate de que as túas pasarelas estean actualizadas á última versión. Pode instalar unha actualización e reconfigurar unha pasarela desde unha solicitude que se mostra na pantalla da pasarela directamente ou [descarga a última versión](https://powerapps.microsoft.com/downloads/). Se non utilizas a última versión da pasarela, a actualización do fluxo de datos falla con mensaxes de erro como **Non se admite a palabra clave: propiedades de configuración. Nome do parámetro: palabra clave**.
>
> Os erros coas pasarelas de datos local en Customer Insights adoitan producirse por problemas de configuración. Para obter máis información sobre a resolución de problemas de pasarelas de datos, consulte [Soluciona problemas coa pasarela de datos local](/data-integration/gateway/service-gateway-tshoot).

## <a name="edit-power-query-data-sources"></a>Editar Power Query fontes de datos

> [!NOTE]
> É posible que non se poidan realizar cambios nas fontes de datos que se están a utilizar actualmente nun dos procesos da aplicación (por exemplo, a segmentación ou a unificación de datos).
>
> No **Configuración** páxina, pode seguir o progreso de cada un dos procesos activos. Cando se complete un proceso, pode volver á páxina **Orixes de datos** e facer os seus cambios.

1. Vaia a **Datos** > **Orixes de datos**.

1. A carón do orixe de datos que queres actualizar, selecciona **Editar**.

1. Aplica os teus cambios e transformacións no **Power Query - Editar consultas** diálogo como se describe no [Crea un novo orixe de datos](#create-a-new-data-source) sección.

1. Seleccione **Gardar** para aplicar os seus cambios e volver ao **Fontes de datos** páxina.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="common-reasons-for-ingestion-errors-or-corrupt-data"></a>Motivos comúns para erros de inxestión ou datos corruptos

### <a name="data-type-does-not-match-data"></a>O tipo de datos non coincide cos datos

A discrepancia de tipos de datos máis común ocorre cando un campo de data non está configurado co formato de data correcto.

Os datos pódense fixar na orixe e reinxerirse. Ou corrixa a transformación en Customer Insights. Para corrixir a transformación:

1. Vaia a **Datos** > **Orixes de datos**.

1. A carón do orixe de datos cos datos danados, selecciona **Editar**.

1. Seleccione **Seguinte**.

1. Seleccione cada unha das consultas e busque as transformacións aplicadas dentro de "Pasos aplicados" que sexan incorrectas ou as columnas de data que non se transformaron cun formato de data.

   :::image type="content" source="media/PQ_corruped_date.png" alt-text="Power Query- Editar que mostra un formato de data incorrecto":::

1. Cambia o tipo de datos para que coincidan correctamente cos datos.

1. Seleccione **Gardar**. Ese orixe de datos actualízase.

## <a name="troubleshoot-ppdf-power-query-based-data-source-refresh-issues"></a>Solucionar problemas de PPDF Power Query problemas de actualización baseados en orixe de datos

Se os datos están obsoletos ou recibe erros despois dunha actualización orixe de datos, siga os seguintes pasos:

1. Navegue a [Power Platform](https://make.powerapps.com).

1. Seleccione o **Medio ambiente** para a súa instancia de Customer Insights.

1. Navega ata **Fluxos de datos**.

1. Para o fluxo de datos que corresponde ao orixe de datos en Customer Insights, seleccione os puntos suspensivos verticais (&vellip;) e, a continuación, seleccione **Mostrar o historial de actualización**.

1. Se o **Estado** do fluxo de datos é **Éxito**, a propiedade do Power Query -based orixe de datos podería ter cambiado:

   1. Revisa a programación de actualización a partir do historial de actualización.
   1. Establece a programación do novo propietario e garda a configuración.

1. Se o **Estado** do fluxo de datos é **Fallou**:

   1. Descarga o ficheiro do historial de actualización.
   1. Revisa o ficheiro descargado para coñecer o motivo do fallo.
   1. Se o erro non se pode resolver, seleccione **?** Para abrir un ticket de soporte. Inclúe o ficheiro do historial de actualización descargado.


[!INCLUDE [footer-include](includes/footer-banner.md)]
