---
title: Actividades do cliente
description: Defina as actividades dos clientes e visualíceas nunha liña de tempo nos perfís dos clientes.
ms.date: 07/22/2022
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
searchScope:
- ci-entities
- ci-customer-card
- ci-relationships
- ci-activities
- ci-activities-wizard
- ci-measures
- ci-segment-suggestions
- customerInsight
ms.openlocfilehash: cc21b0eeb368156437e60d851c2d144f3974c066
ms.sourcegitcommit: c45c3e044034bf866b0662f80a59166cee4ababe
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 07/22/2022
ms.locfileid: "9188137"
---
# <a name="customer-activities"></a>Actividades do cliente

As actividades dos clientes son accións ou eventos realizados polos clientes. Por exemplo, transaccións, duración da chamada de asistencia, revisións de sitios web, compras ou devolucións. Estas actividades están contidas nunha ou máis fontes de datos. Con Customers Insights, consolide as actividades dos seus clientes a partir destes [fontes de datos](data-sources.md) e asocialos con perfís de clientes. Estas actividades aparecen cronoloxicamente nunha liña de tempo no perfil do cliente. Inclúa a liña de tempo nas aplicacións de Dynamics 365 co [Complemento da tarxeta de cliente](customer-card-add-in.md) solución.

## <a name="define-an-activity"></a>Definir unha actividade

Unha entidade debe ter polo menos un atributo de tipo **Data** para ser incluído nun cronograma do cliente. O control **Engadir actividade** está desactivado se non se atopa tal entidade.

1. Ir a **Datos** > **Actividades**.

1. Seleccione **Engadir actividade** para comezar a experiencia guiada.

1. No **Datos da actividade** paso, introduza a seguinte información:

   - **Nome da actividade** : Nome da súa actividade.
   - **Entidade da actividade** : Entidade que inclúe datos de transacción ou actividade.
   - **Chave primaria** : campo que identifica de forma única un rexistro. Non debe conter ningún valor duplicado, valores baleiros ou valores non atopados.

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Configure os datos da actividade co nome, a entidade e a clave primaria.":::

1. Seleccione **Seguinte**.

1. No **Relación** paso, seleccione **Engadir relación** para conectar os datos da túa actividade ao rexistro de clientes correspondente. Este paso visualiza a conexión entre entidades.  

   - **Chave estranxeira da entidade** : Campo da túa entidade de actividade que se utilizará para establecer unha relación con outra entidade.
   - **Ao nome da entidade** : Entidade cliente fonte correspondente coa que estará en relación a súa entidade de actividade. Só pode relacionar con entidades de cliente de orixe que se usan no proceso de unificación de datos.
   - **Nome da relación** : Nome que identifica a relación entre entidades. Se xa existe unha relación entre esta entidade de actividade e a entidade cliente de orixe seleccionada, o nome da relación é de só lectura.

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="Defina a relación da entidade.":::

   > [!TIP]
   > En contornos B-a-B, pode seleccionar entre entidades de conta e outras entidades. Se selecciona unha entidade de conta, o camiño da relación establécese automaticamente. Para outras entidades, ten que definir o camiño de relación entre unha ou varias entidades intermedias ata chegar a unha entidade de conta.

1. Seleccione **Solicitar** para crear a relación.

1. Seleccione **Seguinte**.

1. No paso **Unificación da actividade**, elixa o evento da actividade e a hora de inicio da súa actividade.
   - **Campos obrigatorios**
      - **Actividade do evento**: Campo que é o evento desta actividade.
      - **Marca de tempo**: Campo que representa a hora de inicio da súa actividade.

   - **Campos opcionais**
      - **Detalle adicional**: Campo con información relevante para esta actividade.
      - **Icona**: Icona que mellor representa este tipo de actividade.
      - **Enderezo web**: Campo que contén un URL con información sobre esta actividade. Por exemplo, o sistema transaccional que fornece esta actividade. Este URL pode ser calquera campo do orixe de datos ou pode construírse como un campo novo usando un Power Query transformación. Os datos do URL gardaranse na entidade *Actividade unificada*, que se pode consumir de forma descendente usando as [API](apis.md).

   - **Mostrar na liña de tempo**
      - Escolla se desexa amosar esta actividade na visualización da liña de tempo dos perfís dos clientes. Seleccione **Si** para amosar a actividade na liña do tempo ou **Non** para ocultala.

      :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="Especifique os datos de actividade do cliente nunha entidade de actividade unificada.":::

1. Seleccione **A continuación** para escoller o tipo de actividade ou seleccionar **Remata e repasa** para gardar a actividade co tipo de actividade definido como **Outra**.

1. No paso **Tipo de actividade**, elixa o tipo de actividade e opcionalmente seleccione se quere asignar semanticamente algúns dos tipos de actividade para usalos noutras áreas de Customer Insights. Actualmente, *Comentarios*, *·*, *de venda*, *de pedidos de vendas*, e *Subscrición* os tipos de actividade admiten a semántica despois de aceptar mapear os campos. Se un tipo de actividade non é relevante para a nova actividade, pode escoller *Outro* ou *Crear novo* para un tipo de actividade personalizada.

1. Seleccione **Seguinte**.

1. No paso **Revisión**, verifique as súas seleccións. Volva a calquera dos pasos anteriores e actualice a información se é necesario.

1. Seleccione **Gardar actividade** para aplicar os seus cambios e seleccione **Feito** para volver a **Datos** > **Actividades**. Móstrase a actividade creada.

1. Despois de crear todas as túas actividades, selecciona **Corre** para procesalas.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="manage-existing-activities"></a>Xestionar actividades existentes

Ir a **Datos** > **Actividades** para ver as súas actividades gardadas, a súa entidade de orixe, o tipo de actividade e se están incluídas na cronoloxía do cliente. Podes ordenar a lista de actividades por calquera columna ou utilizar a caixa de busca para atopar a actividade que queres xestionar.

Seleccione unha actividade para ver as accións dispoñibles.

- **Editar** a actividade para cambiar a súa configuración. A configuración ábrese no paso de revisión. Despois de cambiar a configuración, seleccione **Gardar actividade** e logo seleccione **Executar** para procesar os cambios.
- **Cambiar o nome** a actividade. Seleccione **Gardar** para aplicar as modificacións.
- **Eliminar** a actividade. Para eliminar máis dunha actividade á vez, seleccione as actividades e despois **Eliminar**. Confirme a eliminación.

## <a name="view-activity-timelines-on-customer-profiles"></a>Ver cronoloxías de actividade nos perfís de clientes

1. Se seleccionaches **Mostrar na cronoloxía da actividade** na configuración da actividade, vaia a **Clientes** e seleccione un perfil de cliente para ver as actividades do cliente no **Cronograma da actividade** sección.

   :::image type="content" source="media/Activity_Timeline1.PNG" alt-text="Consulte actividades configuradas en Perfís de clientes.":::

1. Para filtrar actividades na cronoloxía das actividades:

   - Seleccione unha ou máis das iconas de actividade para refinar os seus resultados e incluír só os tipos seleccionados.

     :::image type="content" source="media/Activity_Timeline2.PNG" alt-text="Filtre as actividades por tipo usando as iconas.":::

   - Seleccione **Filtro** para abrir un panel de filtros para configurar os filtros da liña de tempo. Filtrar por *Tipo de actividade* e/ou *Data*. Seleccione **Aplicar**.

     :::image type="content" source="media/Activity_Timeline3.PNG" alt-text="Use o panel de filtros para configurar as condicións do filtro.":::

1. Para eliminar filtros, seleccione **Borrar filtros** ou seleccione **Filtro** e desmarque a caixa de verificación do filtro.

> [!NOTE]
> Os filtros de actividade elimínanse cando sae dun perfil de cliente. Tes que aplicalos cada vez que abras un perfil de cliente.

[!INCLUDE [footer-include](includes/footer-banner.md)]
