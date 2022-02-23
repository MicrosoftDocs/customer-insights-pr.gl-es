---
title: Actividades do cliente
description: Defina as actividades dos clientes e visualíceas nunha liña de tempo nos perfís dos clientes.
ms.date: 11/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
ms.openlocfilehash: c99ec2e7d5e4bf32a509bbe4c0c53999129b2305
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 11/02/2021
ms.locfileid: "7732446"
---
# <a name="customer-activities"></a>Actividades do cliente

Combina as actividades dos clientes desde [diversas fontes de datos](data-sources.md) en Dynamics 365 Customer Insights para crear unha liña de tempo que enumera as actividades cronoloxicamente. Inclúa a liña de tempo nas aplicacións de Dynamics 365 co [Complemento da tarxeta de cliente](customer-card-add-in.md) solución ou nun panel Power BI.

## <a name="define-an-activity"></a>Definir unha actividade

As súas fontes de datos poden incluír entidades con datos de transaccións e actividades de varias fontes de datos. Identifique estas entidades e seleccione as actividades que desexa ver na liña de tempo do cliente. Escolla a entidade que inclúe a súa actividade ou actividades de destino.

Unha entidade debe ter polo menos un atributo de tipo **Data** para incluír nunha liña de tempo de cliente e non pode engadir entidades sen campos **Data**. O control **Engadir actividade** está desactivado se non se atopa tal entidade.

1. Na información do público, vaia a **Datos** > **Actividades**.

1. Seleccione **Engadir actividade** para iniciar a experiencia guiada para o proceso de configuración da actividade.

1. No paso **Datos de actividade**, configure os valores para os seguintes campos:

   - **Nome da actividade**: Seleccione un nome para a súa actividade.
   - **Entidade**: seleccione unha entidade que inclúa datos transaccionais ou de actividade.
   - **Clave principal**: seleccione o campo que identifica un rexistro de cliente de forma única. Non debe conter ningún valor duplicado, valores baleiros ou valores non atopados.

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Configure os datos da actividade co nome, a entidade e a clave primaria.":::

1. Seleccione **Seguinte** para ir ao seguinte paso.

1. No paso **Relación**, configure os detalles para conectar os datos da súa actividade co rexistro de cliente correspondente. Este paso visualiza a conexión entre entidades.  

   - **Primeiro**: Campo estranxeiro da súa entidade de actividade que se usará para establecer unha relación con outra entidade.
   - **Segundo**: Entidade cliente fonte correspondente coa que estará relacionada a súa entidade de actividade. Só pode relacionar con entidades de cliente de orixe que se usan no proceso de unificación de datos.
   - **Terceiro**: Se xa existe unha relación entre esta entidade de actividade e a entidade de cliente fonte seleccionada, o nome da relación estará en modo de só lectura. Se non existe tal relación, crearase unha nova relación co nome que proporcione nesta caixa.

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="Defina a relación da entidade.":::

   > [!TIP]
   > En contornos B-a-B, pode seleccionar entre entidades de conta e outras entidades. Se selecciona unha entidade de conta, o camiño da relación establécese automaticamente. Para outras entidades, ten que definir o camiño de relación entre unha ou varias entidades intermedias ata chegar a unha entidade de conta.

1. Seleccione **Seguinte** para ir ao seguinte paso. 

1. No paso **Unificación da actividade**, elixa o evento da actividade e a hora de inicio da súa actividade. 
   - **Campos obrigatorios**
      - **Actividade do evento**: Campo que é o evento desta actividade.
      - **Marca de tempo**: Campo que representa a hora de inicio da súa actividade.

   - **Campos opcionais**
      - **Detalle adicional**: Campo con información relevante para esta actividade.
      - **Icona**: Icona que mellor representa este tipo de actividade.
      - **Enderezo web**: Campo que contén un URL con información sobre esta actividade. Por exemplo, o sistema transaccional que fornece esta actividade. Este URL pode ser calquera campo desde orixe de datos ou pode construírse como un campo novo usando unha transformación Power Query. Os datos do URL gardaranse na entidade *Actividade unificada*, que se pode consumir de forma descendente usando as [API](apis.md).

   - **Mostrar na liña de tempo**
      - Escolla se desexa amosar esta actividade na visualización da liña de tempo dos perfís dos clientes. Seleccione **Si** para amosar a actividade na liña do tempo ou **Non** para ocultala.

      :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="Especifique os datos de actividade do cliente nunha entidade de actividade unificada.":::

1. Seleccione **Seguinte** para ir ao seguinte paso. Pode seleccionar **Rematar e revisar** para gardar a actividade agora co tipo de actividade configurado en **Outro**. 

1. No paso **Tipo de actividade**, elixa o tipo de actividade e opcionalmente seleccione se quere asignar semanticamente algúns dos tipos de actividade para usalos noutras áreas de Customer Insights. Actualmente, os tipos de actividade *Comentarios*, *Fidelidade*, *SalesOrder*, *SalesOrderLine* e *Subscrición* pódense asignar semanticamente despois de acordar asignar os campos. Se un tipo de actividade non é relevante para a nova actividade, pode escoller *Outro* ou *Crear novo* para un tipo de actividade personalizada.

1. Seleccione **Seguinte** para ir ao seguinte paso. 

1. No paso **Revisión**, verifique as súas seleccións. Volva a calquera dos pasos anteriores e actualice a información se é necesario.

   :::image type="content" source="media/Activity_Wizard5.PNG" alt-text="Revise os campos especificados para unha actividade.":::
   
1. Seleccione **Gardar actividade** para aplicar os seus cambios e seleccione **Feito** para volver a **Datos** > **Actividades**. Aquí verá que actividades están configuradas para mostrarse na liña do tempo. 

1. Na páxina **Actividades**, seleccione **Executar** para procesar a actividade. 

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="manage-existing-activities"></a>Xestionar actividades existentes

En **Datos** > **Actividades**, pode ver todas as actividades gardadas e xestionalas. Cada actividade está representada por unha fila que tamén inclúe detalles sobre a fonte, a entidade e o tipo de actividade.

As seguintes accións están dispoñibles cando selecciona unha actividade. 

- **Editar**: Abre a configuración da actividade no paso de revisión. Pode cambiar calquera ou toda a configuración actual desde este paso. Despois de cambiar a configuración, seleccione **Gardar actividade** e logo seleccione **Executar** para procesar os cambios.

- **Cambiar o nome**: Abre un diálogo onde pode introducir un nome diferente para a actividade seleccionada. Seleccione **Gardar** para aplicar as modificacións.

- **Eliminar**: Abre un diálogo para confirmar a eliminación da actividade seleccionada. Tamén pode eliminar máis dunha actividade á vez seleccionando as actividades e logo seleccionando a icona de eliminación. Para confirmar a eliminación, seleccione **Eliminar**.

## <a name="view-activity-timelines-on-customer-profiles"></a>Ver cronoloxías de actividade nos perfís de clientes

Despois de configurar as actividades do cliente, seleccione **Mostrar na cronoloxía da actividade** na configuración da actividade para atopar todas as actividades dos seus clientes no seu perfil de cliente.

Para abrir a cronoloxía dun cliente, vaia a **Clientes** e escolla o perfil de cliente que desexa ver.

Se un cliente participou nunha actividade que configurou, atoparaa na sección **Cronoloxía da actividade**.

:::image type="content" source="media/Activity_Timeline1.PNG" alt-text="Consulte actividades configuradas en Perfís de clientes.":::

Hai varias formas de filtrar actividades na liña de tempo da actividade:

- Pode seleccionar unha ou varias das iconas de actividade para refinar os resultados para incluír só os tipos seleccionados.

  :::image type="content" source="media/Activity_Timeline2.PNG" alt-text="Filtre as actividades por tipo usando as iconas.":::

- Pode seleccionar **Filtrar** para abrir un panel de filtros para configurar os filtros da súa liña de tempo.

   1. Pode filtrar por *ActivityType* e *Data*
   1. Seleccione **Aplicar** para usar os filtros na cronoloxía da actividade.

   :::image type="content" source="media/Activity_Timeline3.PNG" alt-text="Use o panel de filtros para configurar as condicións do filtro.":::

Para eliminar filtros, seleccione **x** xunto a cada filtro aplicado á liña do tempo ou seleccione **Borrar filtros**.


> [!NOTE]
> Os filtros de actividade elimínanse cando sae dun perfil de cliente. Ten que aplicalos cada vez que abra un perfil de cliente.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
