---
title: Actividades do cliente
description: Defina as actividades dos clientes e visualíceas na cronoloxía do cliente.
ms.date: 10/13/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: adkuppa
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: dcef8f0547009e1488f1abe91423fa0bf5b061de
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267430"
---
# <a name="customer-activities"></a>Actividades do cliente

Combine as actividades dos clientes desde [varias fontes de datos](data-sources.md) dentrode Dynamics 365 Customer Insights para crear unha liña do tempo do cliente que liste as actividades por orde cronolóxica. Pode incluír a liña de tempo nas aplicacións de interacción con clientes en Dynamics 365 a través do [complemento de tarxeta de cliente](customer-card-add-in.md) ou nun panel de Power BI.

## <a name="define-an-activity"></a>Definir unha actividade

As súas fontes de datos inclúen entidades con datos de transaccións e actividades de varias fontes de datos. Identifique estas entidades e seleccione as actividades que desexa ver na liña de tempo do cliente. Escolla a entidade que inclúe a súa actividade ou actividades de destino.

1. Na información do público, vaia a **Datos** > **Actividades**.

1. Seleccione **Engadir actividade**.

   > [!NOTE]
   > Unha entidade debe ter polo menos un atributo de tipo **Data** para incluír nunha liña de tempo de cliente e non pode engadir entidades sen campos **Data**. O control **Engadir actividade** está desactivado se non se atopa tal entidade.

1. No panel **Engadir actividade**, estableza os valores para os seguintes campos:

   - **Entidade**: seleccione unha entidade que inclúa datos transaccionais ou de actividade.
   - **Clave principal**: seleccione o campo que identifica un rexistro de cliente de forma única. Non debe conter ningún valor duplicado, valores baleiros ou valores non atopados.
   - **Marca de tempo**: seleccione o campo que representa a hora de inicio da súa actividade.
   - **Evento**: seleccione o campo que é o evento da actividade.
   - **Enderezo web**: seleccione o campo que representa un URL que fornece información adicional sobre esta actividade. Por exemplo, o sistema transaccional que fornece esta actividade. Este URL pode ser calquera campo desde orixe de datos ou pode construírse como un campo novo usando unha transformación Power Query. Estes datos de URL almacenaranse na entidade de Actividade unificada, que se pode consumir de forma descendente mediante API.
   - **Detalles**: tamén pode seleccionar o campo que se engade para obter máis detalles.
   - **Icona**: tamén pode seleccionar a icona que representa esta actividade.
   - **Tipo de actividade**: defina a referencia do tipo de actividade no Common Data Model que describa mellor a definición semántica da actividade.

1. Na sección **Establecer relación**, configure os detalles para conectar os seus datos de actividade co cliente correspondente.

    - **Campo da entidade da actividade**: seleccione o campo da súa entidade de actividade que se empregará para establecer unha relación con outra entidade.
    - **Entidade de cliente**: seleccione a entidade de cliente de orixe correspondente coa que estará en relación a súa entidade de actividade. Pode relacionarse só con aquelas entidades de cliente de orixe que se usan no proceso de unificación de datos.
    - **Campo da entidade do cliente**: este campo amosa a clave principal da entidade de cliente de orixe como seleccionada no proceso de mapa. Este campo clave principal na entidade cliente de orixe úsase para establecer unha relación coa entidade da actividade.
    - **Nome**: se xa existe unha relación entre esta entidade de actividade e a entidade cliente de orixe seleccionada, o nome da relación estará en modo de só lectura. Se non existe esa relación, crearase unha nova relación co nome indicado aquí.
   
   > [!div class="mx-imgBorder"]
   > ![Definir a relación da entidade](media/activities-entities-define.png "Definir a relación da entidade")

1. Seleccione **Gardar** para aplicar as modificacións.

1. Na páxina **Actividades**, seleccione **Executar**.

> [!TIP]
> Existen [seis tipos de estado](system.md#status-types) para as tarefas ou os procesos. Ademais, a maioría dos procesos [dependen doutros procesos descendentes](system.md#refresh-policies). Pode seleccionar o estado dun proceso para ver detalles sobre o progreso de todo o traballo. Despois de seleccionar **Ver detalles** para unha das tarefas do traballo, atopará información adicional: o tempo de procesamento, a última data de procesamento e todos os erros e avisos asociados á tarefa.

## <a name="edit-an-activity"></a>Editar unha actividade

1. Na información do público, vaia a **Datos** > **Actividades**.

2. Seleccione a entidade da actividade que desexe editar e seleccione **Editar**. Tamén pode pasar o rato sobre a fila de entidade e seleccionar a icona **Editar**.

3. Prema na icona **Editar**.

4. No panel **Editar actividade**, actualice os valores e seleccione **Gardar**.

5. Na páxina **Actividades**, seleccione **Executar**.

## <a name="delete-an-activity"></a>Eliminar unha actividade

1. Na información do público, vaia a **Datos** > **Actividades**.

2. Seleccione a entidade da actividade que desexe eliminar e seleccione **Eliminar**. Tamén pode pasar o rato sobre a fila de entidade e seleccionar a icona **Eliminar**. Tamén pode seleccionar varias entidades de actividade para eliminar dunha vez.
   > [!div class="mx-imgBorder"]
   > ![Editar ou eliminar a relación da entidade](media/activities-entities-edit-delete.png "Editar ou eliminar a relación da entidade")

3. Seleccione a icona **Eliminar**.

4. Confirme a eliminación.


[!INCLUDE[footer-include](../includes/footer-banner.md)]