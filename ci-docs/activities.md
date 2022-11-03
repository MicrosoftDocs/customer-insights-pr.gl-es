---
title: Actividades de contacto con clientes ou empresas
description: Define as actividades de contacto de clientes ou empresas e visualízaas nunha liña de tempo nos perfís de clientes.
ms.date: 10/26/2022
ms.subservice: audience-insights
ms.reviewer: v-wendysmith
ms.topic: conceptual
author: srivas15
ms.author: shsri
manager: shellyha
searchScope:
- ci-entities
- ci-customer-card
- ci-relationships
- ci-activities
- ci-activities-wizard
- ci-measures
- ci-segment-suggestions
- customerInsights
ms.openlocfilehash: d8caa477278f04c3a0a95ced15f4bea2a22aa8cd
ms.sourcegitcommit: da6a2d189edacc8f2c0f2abedcb28245f26fe74c
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 10/27/2022
ms.locfileid: "9723779"
---
# <a name="customer-or-business-contact-activities"></a>Actividades de contacto con clientes ou empresas

As actividades dos clientes son accións ou eventos realizados por clientes ou contactos comerciais. Por exemplo, transaccións, duración da chamada de asistencia, revisións de sitios web, compras ou devolucións. Estas actividades están contidas nunha ou máis fontes de datos. Con Customers Insights, consolide as actividades dos seus clientes a partir destes [fontes de datos](data-sources.md) e asocialos con perfís de clientes. Estas actividades aparecen cronoloxicamente nunha liña de tempo no perfil do cliente. Inclúa a liña de tempo nas aplicacións de Dynamics 365 co [Complemento da tarxeta de cliente](customer-card-add-in.md) solución.

## <a name="define-a-customer-activity"></a>Definir unha actividade do cliente

Unha entidade debe ter polo menos un atributo de tipo **Data** para ser incluído nun cronograma do cliente. O control **Engadir actividade** está desactivado se non se atopa tal entidade.

1. Ir a **Datos** > **Actividades**.

1. Seleccione **Engadir actividade** para comezar a experiencia guiada.

1. No **Datos da actividade** paso, introduza a seguinte información:

   - **Nome da actividade**: Seleccione un nome para a súa actividade.
   - **Entidade da actividade** : seleccione unha entidade que inclúa datos de transacción ou actividade.
   - **Clave principal**: seleccione o campo que identifica un rexistro de cliente de forma única. Non debe conter ningún valor duplicado, valores baleiros ou valores non atopados.

     > [!NOTE]
     > A clave principal de cada fila debe permanecer coherente nas actualizacións de orixe de datos. Se a clave principal dunha fila se actualiza nunha actualización orixe de datos, crea duplicados na entidade Actividade de saída. 

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Configure os datos da actividade co nome, a entidade e a clave primaria.":::

1. Seleccione **Seguinte**.

1. No **Relación** paso, seleccione **Engadir relación** para conectar os datos da túa actividade ao rexistro de clientes correspondente. Este paso visualiza a conexión entre entidades.  

   - **Chave estranxeira** : Campo estranxeiro na súa entidade de actividade que se utilizará para establecer unha relación con outra entidade.
   - **Ao nome da entidade** : Entidade cliente fonte correspondente coa que estará en relación a súa entidade de actividade. Só pode relacionar con entidades de cliente de orixe que se usan no proceso de unificación de datos.
   - **Nome da relación** : Se xa existe unha relación entre esta entidade de actividade e a entidade cliente de orixe seleccionada, o nome da relación estará en modo de só lectura. Se non existe tal relación, crearase unha nova relación co nome que proporcione nesta caixa.

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

## <a name="manage-existing-customer-activities"></a>Xestionar as actividades existentes dos clientes

Ir a **Datos** > **Actividades** para ver as súas actividades gardadas, a súa entidade de orixe, o tipo de actividade e se están incluídas na cronoloxía do cliente. Podes ordenar a lista de actividades por calquera columna ou utilizar a caixa de busca para atopar a actividade que queres xestionar.

Seleccione unha actividade para ver as accións dispoñibles.

- **Editar** a actividade para cambiar a súa configuración. A configuración ábrese no paso de revisión. Despois de cambiar a configuración, seleccione **Gardar actividade** e logo seleccione **Executar** para procesar os cambios.
- **Cambiar o nome** a actividade. Seleccione **Gardar** para aplicar as modificacións.
- **Eliminar** a actividade. Para eliminar máis dunha actividade á vez, seleccione as actividades e despois **Eliminar**. Confirme a eliminación.

## <a name="view-activity-timelines-on-customer-profiles"></a>Ver cronoloxías de actividade nos perfís de clientes

1. Se seleccionaches **Mostrar na cronoloxía da actividade** na configuración da actividade, vaia a **Clientes** e seleccione un perfil de cliente para ver as actividades do cliente no **Cronograma da actividade** sección.

   :::image type="content" source="media/Activity_Timeline1.PNG" alt-text="Consulte actividades configuradas en Perfís de clientes.":::

1. Para filtrar actividades na cronoloxía de actividades:

   - Seleccione unha ou máis das iconas de actividade para refinar os seus resultados e incluír só os tipos seleccionados.

     :::image type="content" source="media/Activity_Timeline2.PNG" alt-text="Filtre as actividades por tipo usando as iconas.":::

   - Seleccione **Filtro** para abrir un panel de filtros para configurar os filtros da liña de tempo. Filtrar por *Tipo de actividade* e/ou *Data*. Seleccione **Aplicar**.

     :::image type="content" source="media/Activity_Timeline3.PNG" alt-text="Use o panel de filtros para configurar as condicións do filtro.":::

> [!NOTE]
> Os filtros de actividade elimínanse cando sae dun perfil de cliente. Tes que aplicalos cada vez que abras un perfil de cliente.

## <a name="define-a-contact-activity"></a>Definir unha actividade de contacto

Para contas empresariais (B-to-B), use a *Perfil de contacto* entidade para capturar actividades dos contactos. Podes ver na cronoloxía da actividade dunha conta que contacto foi o responsable de cada actividade. A maioría dos pasos seguen a configuración do mapeo da actividade do cliente.

   > [!NOTE]
   > Para definir unha actividade a nivel de contacto, a *Perfil de contacto* debe crearse a entidade, ben como a [perfil de contacto unificado](data-unification-contacts.md) ou a través [mapeo semántico](semantic-mappings.md#define-a-contactprofile-semantic-entity-mapping).
   >
   > Debes ter os dous **ID de conta** e **ContactID** atributos para cada rexistro dentro dos seus datos de actividade.
  
1. Ir a **Datos** > **Actividades**.

1. Seleccione **Engadir actividade**.

1. No **Datos da actividade** paso, introduza a seguinte información:

   - **Nome da actividade**: Seleccione un nome para a súa actividade.
   - **Entidade da actividade** : seleccione unha entidade que inclúa datos de transacción ou actividade.
   - **Clave principal**: seleccione o campo que identifica un rexistro de cliente de forma única. Non debe conter ningún valor duplicado, valores baleiros ou valores non atopados.

     > [!NOTE]
     > A clave principal de cada fila debe permanecer coherente nas actualizacións de orixe de datos. Se a clave principal dunha fila se actualiza nunha actualización orixe de datos, crea duplicados na entidade Actividade de saída. 


1. No **Relacións** paso, cree unha relación indirecta entre os datos da fonte da actividade e as contas, utilizando os seus datos de contacto como entidade intermediaria. Para obter máis información, consulte [vías de relación directa e indirecta](relationships.md#relationship-paths).
   - Relación de exemplo para unha actividade chamada *Compras*:
      - **Datos da actividade fonte de compras** > **Datos de contacto** sobre o atributo **ContactID**
      - **Datos de contacto** > **Datos da conta** sobre o atributo **ID de conta**

   :::image type="content" source="media/Contact_Activities1.png" alt-text="Exemplo de configuración de relación.":::

1. Despois de configurar as relacións, seleccione **A continuación** e complete a configuración do mapa de actividade. Para ver os pasos detallados sobre a creación de actividades, consulte [definir unha actividade do cliente](#define-a-customer-activity).

1. Executa os teus mapas de actividade.

1. As túas actividades a nivel de contacto agora estarán visibles na cronoloxía do teu cliente.

   :::image type="content" source="media/Contact_Activities2.png" alt-text="Resultado final despois de configurar as actividades de contacto":::

## <a name="contact-level-activity-timeline-filtering"></a>Filtrado da cronoloxía da actividade a nivel de contacto

Despois de configurar un mapeo de actividade a nivel de contacto e executalo, o cronograma de actividade dos teus clientes actualizarase. Inclúe os seus ID ou nomes, dependendo do teu *Perfil de contacto* configuración, para as actividades nas que actuaron. Podes filtrar actividades por contactos na liña de tempo para ver os contactos específicos que che interesen. Ademais, podes ver todas as actividades que non están asignadas a un contacto específico seleccionando **Actividades non asignadas a un contacto**.

   :::image type="content" source="media/Contact_Activities3.png" alt-text="Opcións de filtrado dispoñibles para actividades a nivel de contacto.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
