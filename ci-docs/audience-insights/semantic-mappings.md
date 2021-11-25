---
title: Asignacións semánticas (versión preliminar)
description: Visión xeral das asignacións semánticas e como usalas.
ms.date: 11/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
ms.openlocfilehash: f23c622572ff9f967eca07de7898419d1ffc18b0
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 11/02/2021
ms.locfileid: "7731941"
---
# <a name="semantic-mappings"></a>Asignacións semánticas

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


[!INCLUDE[footer-include](../includes/footer-banner.md)]
