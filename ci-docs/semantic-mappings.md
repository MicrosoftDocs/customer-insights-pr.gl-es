---
title: Asignacións semánticas (versión preliminar)
description: Visión xeral das asignacións semánticas e como usalas.
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.reviewer: v-wendysmith
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
searchScope:
- ci-semantic-mapping
- customerInsights
ms.openlocfilehash: 8780c11c8b091717349f0fd75a36b99c3a63ab49
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 08/16/2022
ms.locfileid: "9303874"
---
# <a name="semantic-mappings-preview"></a>Asignacións semánticas (versión preliminar)

> [!NOTE]
> O **Mapeos semánticos** a páxina só está dispoñible para contornas empresariais (B-to-B) onde xa se crearon perfís de contactos usando esta páxina. Podes seguir creando e xestionando os perfís de contacto individuais usando o **Mapeos semánticos** páxina. Ou, [unificar os seus datos de contacto](data-unification-contacts.md) para eliminar duplicados, identificar coincidencias entre entidades e crear un perfil de contacto unificado. Despois podes usar o perfil de contacto unificado para crear actividades a nivel de contacto.

As asignacións semánticas permítenlle asignar os seus datos sen actividade a esquemas predefinidos. Estes esquemas axudan a Customer Insights a comprender mellor os atributos dos teus datos. As cartografías semánticas e os datos proporcionados permiten obter novos coñecementos e funcións en Customer Insights. Para asignar os datos da súa actividade aos esquemas, revise a documentación [actividades](activities.md).

## <a name="define-a-contactprofile-semantic-entity-mapping"></a>Definir unha asignación de entidades semánticas ContactProfile

1. Ir a **Datos** > **Mapeamentos semánticos (vista previa)**.

1. Seleccione **Engadir asignación semántica** para comezar a experiencia guiada.

1. No paso **Datos da entidade**, configure os valores para os seguintes campos:

   - **Nome de asignación de entidades semánticas** : Nome para a súa asignación de entidades semánticas.
   - **Entidade fonte** : Entidade que inclúe datos de contacto.
   - **Chave primaria** : campo que identifica de forma única un rexistro de contacto. Non debe conter ningún valor duplicado, valores baleiros ou valores non atopados.

   :::image type="content" source="media/Semantic_Mapping_Wizard1.png" alt-text="Configure a asignación de entidades semánticas co nome, a entidade de orixe e a clave primaria.":::

1. Seleccione **Seguinte**.

1. No paso **Relacións**, configure os detalles para conectar os seus datos de contacto cos datos da conta correspondente. Este paso visualiza a conexión entre entidades.  

   Hai dous tipos de camiños de relación que se poden implementar: **Relacións directas** e **Relacións indirectas**. Para obter máis información, vaia a [camiños de relación directa e indirecta](relationships.md#relationship-paths).

   1. Seleccione **Engadir relación** para configurar a relación.
   1. Escolla o atributo da súa entidade de orixe que conecta a súa entidade de contacto con outra entidade.
   1. Escolla a entidade coa que conectar a súa entidade de contacto. Escolle unha entidade entre o **Entidades contables** ou o **Entidade intermedia** sección. Se selecciona unha entidade intermedia, defina unha segunda relación para conectar coa entidade da súa conta de destino.

      :::image type="content" source="media/Semantic_Mapping_Wizard2.png" alt-text="Seleccione unha entidade de conta ou unha entidade intermedia.":::

   1. Proporcione un **Nome de relación**. Se xa existe unha relación entre as súas entidades, o nome da relación só é de lectura. Se non existe ningunha relación, crearase unha nova relación co nome que proporcione.
   1. Seleccione **Aplicar** para rematar a configuración da relación.

   > [!NOTE]
   > Pode configurar máis relacións entre a entidade de contacto e outras entidades de conta con entidades intermedias.
   
     :::image type="content" source="media/Semantic_Mapping_Wizard4.png" alt-text="A visualización de varias relacións conecta as entidades de contacto coas entidades da conta.":::

1. Seleccione **Seguinte**.

1. No paso **Definir o tipo semántico**, elixa un **Tipo semántico**. Actualmente, hai un **Tipo semántico** chamado *ContactProfile*.

1. Asigne o seu ID de contacto ao *Perfil de contacto* tipo semántico **ID de contacto**. Opcionalmente, asigna outros campos como nome, apelidos, xénero ou correo electrónico.

   :::image type="content" source="media/Semantic_Mapping_Wizard5.png" alt-text="Asigne os atributos dos seus datos de contacto aos campos obrigatorios e opcionais proporcionados.":::

1. Seleccione **Seguinte**.

1. No **Revisión** paso, revise a configuración do mapeo semántico. Para facer cambios, seleccione **Editar** para o apartado correspondente.

1. Seleccione **Gardar**.

1. Para procesar a asignación semántica, seleccione **Corre**. Ou selecciona **Pechar** para gardar a súa asignación semántica sen procesala. Para executalo máis tarde, seleccione a asignación semántica e seleccione **Actualizar**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="manage-existing-semantic-mappings"></a>Xestionar asignacións semánticas existentes

Ir a **Datos** > **Asignacións semánticas (vista previa)** para ver as túas asignacións semánticas gardadas, a súa entidade de orixe, o tipo semántico, o tipo de asignación e o estado.

:::image type="content" source="media/semantic-mapping-options.png" alt-text="Opcións para xestionar asignacións semánticas.":::

Seleccione a asignación semántica para ver as accións dispoñibles.
- **Editar** a configuración actual. Seleccione **Gardar** e **Executar** para procesar as modificacións.
- **Actualizar** o mapeo semántico para incluír os datos máis recentes. Actualizar calquera asignación semántica actualizará todas as asignacións semánticas do mesmo tipo.
- **Cambiar o nome** a cartografía semántica. Seleccione **Gardar**.
- **Eliminar** a cartografía semántica. Para eliminar máis dunha asignación semántica á vez, seleccione as asignacións semánticas e a icona de eliminación. Para confirmar a eliminación, seleccione **Eliminar**.

[!INCLUDE [footer-include](includes/footer-banner.md)]
