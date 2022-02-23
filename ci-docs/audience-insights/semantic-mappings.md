---
title: Asignacións semánticas (versión preliminar)
description: Visión xeral das asignacións semánticas e como usalas.
ms.date: 12/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
ms.openlocfilehash: 08b257b97704b219bb3277042516e00deb886a49
ms.sourcegitcommit: 58651d33e0a7d438a2587c9ceeaf7ff58ae3b648
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 12/02/2021
ms.locfileid: "7881828"
---
# <a name="semantic-mappings-preview"></a>Asignacións semánticas (versión preliminar)

As asignacións semánticas permítenlle asignar os seus datos sen actividade a esquemas predefinidos. Estes esquemas axudan á información do público a comprender mellor os seus atributos de datos. A asignación semántica e os datos proporcionados permiten novas ideas e funcións nas estatísticas do público. Para asignar os datos da súa actividade aos esquemas, revise a documentación [actividades](activities.md).

**As asignacións semánticas están actualmente habilitadas para contornos baseados en contas empresariais**. *ContactProfile* é o único tipo de asignación semántica dispoñible actualmente en estatísticas de audiencia.

## <a name="define-a-contactprofile-semantic-entity-mapping"></a>Definir unha asignación de entidades semánticas ContactProfile

1. Na información do público, vaia a **Datos** > **Asignacións semánticas (vista previa)**.

1. Seleccione **Engadir asignación semántica** para comezar a experiencia guiada.

1. No paso **Datos da entidade**, configure os valores para os seguintes campos:

   - **Nome da asignación de entidades semánticas**: proporcione un nome para a asignación de entidades semánticas.
   - **Entidade de orixe**: seleccione unha entidade que inclúa datos de contacto.
   - **Clave principal**: seleccione o campo que identifica un rexistro de contacto de forma única. Non debe conter ningún valor duplicado, valores baleiros ou valores non atopados.

   :::image type="content" source="media/Semantic_Mapping_Wizard1.png" alt-text="Configure a asignación de entidades semánticas co nome, a entidade de orixe e a clave primaria.":::

1. Seleccione **Seguinte** para continuar.

1. No paso **Relacións**, configure os detalles para conectar os seus datos de contacto cos datos da conta correspondente. Este paso visualiza a conexión entre entidades.  

   Hai dous tipos de camiños de relación que se poden implementar: **Relacións directas** e **Relacións indirectas**. Para obter máis información, vaia a [camiños de relación directa e indirecta](relationships.md#relationship-paths).

   1. Seleccione **Engadir relación** e configure a relación.
   1. Escolla o atributo da súa entidade de orixe que conecta a súa entidade de contacto con outra entidade.
   1. Escolla a entidade coa que conectar a súa entidade de contacto. Pode escoller unha entidade na sección **Entidades de conta** ou o **Entidade intermedia**. Se selecciona unha entidade intermedia, deberá definir unha segunda relación para conectarse á entidade de conta de destino.

      :::image type="content" source="media/Semantic_Mapping_Wizard2.png" alt-text="Seleccione unha entidade de conta ou unha entidade intermedia.":::

   1. Proporcione un **Nome de relación**. Se xa existe unha relación entre as súas entidades, o nome da relación só é de lectura. Se non existe ningunha relación, crearase unha nova relación co nome que proporcione.
   1. Seleccione **Aplicar** para rematar a configuración da relación.

   > [!NOTE]
   > Pode configurar máis relacións entre a entidade de contacto e outras entidades de conta con entidades intermedias.
   >  :::image type="content" source="media/Semantic_Mapping_Wizard4.png" alt-text="A visualización de varias relacións conecta as entidades de contacto coas entidades da conta.":::

1. Seleccione **Seguinte** cando remate a configuración da relación.

1. No paso **Definir o tipo semántico**, elixa un **Tipo semántico**. Actualmente, hai un **Tipo semántico** chamado *ContactProfile*.

1. Asigne os seus datos a *Tipo semántico* **ContactProfile** para os campos amosados.
   - Campo requirido: ID de contacto
   - Campos opcionais: nome, apelidos, data de nacemento, sexo, correo electrónico principal e teléfono principal

   :::image type="content" source="media/Semantic_Mapping_Wizard5.png" alt-text="Asigne os atributos dos seus datos de contacto aos campos obrigatorios e opcionais proporcionados.":::

1. Seleccione **Seguinte** para continuar.

1. No paso **Revisión**, bótelle un ollo á configuración da asignación semántica. Seleccione **Editar** para que a sección correspondente faga cambios.

1. Seleccione **Gardar** para gardar a súa nova **Asignación semántica**.

1. Despois de gardar, pode seleccionar o proceso **Executar** da asignación semántica ou pode seleccionar **Pechar** para gardar a súa asignación semántica sen procesala.

1. Para executar unha asignación semántica nun punto posterior, seleccione a asignación semántica e seleccione **Actualizar**.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="manage-existing-semantic-mappings"></a>Xestionar asignacións semánticas existentes

En **Datos** > **Asignacións semánticas (vista previa)**, pode ver todas as asignacións semánticas gardadas e xestionalas. Cada asignación semántica está representada por unha fila separada. Atopará detalles sobre a entidade de orixe, o tipo semántico, o tipo de asignación e o seu estado.

:::image type="content" source="media/semantic-mapping-options.png" alt-text="Opcións para xestionar asignacións semánticas.":::

- **Editar**: abre a configuración da asignación semántica no paso de revisión. Pode cambiar a configuración actual. Seleccione **Gardar** e **Executar** para procesar as modificacións.

- **Actualizar**: actualiza a asignación semántica seleccionada cos datos máis actualizados das entidades que forman parte da súa configuración. Actualizar calquera asignación semántica actualizará todas as asignacións semánticas do mesmo tipo.

- **Cambiar o nome**: abre un diálogo onde pode introducir un nome diferente para a asignación semántica seleccionada. Seleccione **Gardar** para aplicar as modificacións.

- **Eliminar**: abre un diálogo para confirmar a eliminación da asignación semántica seleccionada. Tamén pode eliminar máis dunha asignación semántica á vez seleccionando as asignacións semánticas e a icona de eliminación. Para confirmar a eliminación, seleccione **Eliminar**.

## <a name="use-a-contactprofile-semantic-entity-mapping-to-create-contact-level-activities"></a>Use unha asignación de entidades semánticas ContactProfile para crear actividades a nivel de contacto

Despois de crear un *Perfil de contacto* mapeo de entidades semánticas, pode capturar actividades dos contactos. Permítelle ver na cronoloxía da actividade dunha conta que contacto foi o responsable de cada actividade. A maioría dos pasos seguen a configuración típica de mapeo de actividade.

   > [!NOTE]
   > Para que as actividades de contacto funcionen, debes ter as dúas **ID da conta** e **ContactID** atributos para cada rexistro dentro dos seus datos de actividade.

1. [Definir a *Perfil de contacto* mapeamento de entidades semánticas.](#define-a-contactprofile-semantic-entity-mapping) E executa o mapeo semántico.

1. Na información do público, vaia a **Datos** > **Actividades**.

1. Seleccione **Engadir actividade** para crear unha nova actividade.

1. Ponlle un nome á actividade, seleccione a entidade de actividade de orixe e seleccione a chave principal da entidade de actividade.

1. No **Relacións** paso, cree unha relación indirecta entre os datos da fonte da actividade e as contas, utilizando os seus datos de contacto como entidade intermediaria. Para obter máis información, consulte [vías de relación directa e indirecta](relationships.md#relationship-paths).
   - Relación de exemplo para unha actividade chamada *Compras*:
      - **Datos da actividade fonte de compras** > **Datos de contacto** sobre o atributo **ContactID**
      - **Datos de contacto** > **Datos da conta** sobre o atributo **ID da conta**

   :::image type="content" source="media/Contact_Activities1.png" alt-text="Exemplo de configuración de relación.":::

1. Despois de configurar as relacións, seleccione **A continuación** e complete a configuración do mapa de actividade. Para ver os pasos detallados sobre a creación de actividades, consulte [definir unha actividade](activities.md).

1. Executa os teus mapas de actividade.

1. As túas actividades a nivel de contacto agora estarán visibles na cronoloxía do teu cliente.

   :::image type="content" source="media/Contact_Activities2.png" alt-text="Resultado final despois de configurar as actividades de contacto":::

### <a name="contact-level-activity-timeline-filtering"></a>Filtrado da cronoloxía da actividade a nivel de contacto

Despois de configurar un mapeo de actividade a nivel de contacto e executalo, o cronograma de actividade dos teus clientes actualizarase. Inclúe os seus ID ou nomes, dependendo do teu *Perfil de contacto* configuración, para as actividades nas que actuaron. Podes filtrar actividades por contactos na liña de tempo para ver os contactos específicos que che interesen. Ademais, podes ver todas as actividades que non están asignadas a un contacto específico seleccionando **Actividades non asignadas a un contacto**.

   :::image type="content" source="media/Contact_Activities3.png" alt-text="Opcións de filtrado dispoñibles para actividades a nivel de contacto.":::

[!INCLUDE[footer-include](../includes/footer-banner.md)]
