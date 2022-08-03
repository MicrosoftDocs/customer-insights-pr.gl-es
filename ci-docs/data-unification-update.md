---
title: Actualiza a configuración de unificación
description: Actualiza regras duplicadas, regras de coincidencia ou campos unificados na configuración de unificación.
ms.date: 06/01/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: 1af7f018abd412c833ff22b3880f0e4508ff4953
ms.sourcegitcommit: 3c5b0b40b2b45e420015bbdd228ce0e610245e6f
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 07/12/2022
ms.locfileid: "9139578"
---
# <a name="update-the-unification-settings"></a>Actualiza a configuración de unificación

Para revisar ou cambiar calquera configuración de unificación unha vez que se crea un perfil unificado, siga os seguintes pasos.

1. Ir a **Datos** > **Unificar**.

   :::image type="content" source="media/m3_unified.png" alt-text="Captura de pantalla da páxina Data Unify despois de que os datos se unifiquen.":::

   > [!TIP]
   > O **Condicións de coincidencia** O mosaico só se mostra se se seleccionaron varias entidades.

1. Escolle o que queres actualizar:
   - [Campos de orixe](#edit-source-fields) para engadir entidades ou atributos ou cambiar os tipos de atributos.
   - [Rexistros duplicados](#manage-deduplication-rules) para xestionar regras de deduplicación ou combinar preferencias.
   - [Condicións de coincidencia](#manage-match-rules) para actualizar as regras de coincidencia en dúas ou máis entidades.
   - [Campos de clientes unificados](#manage-unified-fields) para combinar ou excluír campos. Tamén pode agrupar perfís relacionados en clústeres.

1. Despois de facer os cambios, escolla a seguinte opción:

   :::image type="content" source="media/m3_run_match_merge.png" alt-text="Captura de pantalla da páxina de Unificación de datos coas opcións de Unificación destacadas.":::

   - [Executar condicións coincidentes](#run-matching-conditions) para avaliar rapidamente a calidade das súas condicións de coincidencia (desduplicación e regras de coincidencia) sen actualizar o perfil unificado. O **Executar só condicións coincidentes** a opción non se mostra para unha única entidade.
   - [Unificar os perfís de clientes](#run-updates-to-the-unified-customer-profile) para executar condicións coincidentes e actualizar a entidade unificada do perfil do cliente sen afectar as dependencias (como enriquecementos, segmentos ou medidas). Os procesos dependentes non se executan, pero actualizaranse como [definido no programa de actualización](system.md#schedule-tab).
   - [Unifica os perfís de clientes e as dependencias](#run-updates-to-the-unified-customer-profile) para executar condicións coincidentes e actualizar a entidade unificada do perfil do cliente e todas as dependencias (como enriquecementos, segmentos ou medidas). Todos os procesos reexecútanse automaticamente.

## <a name="edit-source-fields"></a>Editar campos de orixe

Non podes eliminar un atributo ou unha entidade se xa se unificaron.

1. Seleccione **Editar** no **Campos de orixe** tella.

   :::image type="content" source="media/m3_source_edit.png" alt-text="Captura de pantalla da páxina de campos de orixe que mostra o número de claves primarias, campos asignados e non asignados":::

   Mostra o número de campos asignados e sen asignar.

1. Seleccione **Seleccione entidades e campos** para engadir outros atributos ou entidades. Use a busca ou o desprazamento para atopar e seleccionar os seus atributos e entidades de interese. Seleccione **Aplicar**.

1. Opcionalmente, pode cambiar a clave principal dunha entidade, os tipos de atributos e alternar **Cartografía intelixente** on ou off. Para obter máis información, consulte [Seleccione a clave primaria e o tipo semántico para os atributos](map-entities.md#select-primary-key-and-semantic-type-for-attributes).

1. Seleccione **A continuación** para facer cambios nas regras de deduplicación ou seleccionar **Garda e pecha** e volver a [Actualiza a configuración de unificación](#update-the-unification-settings).

## <a name="manage-deduplication-rules"></a>Xestionar regras de deduplicación

1. Seleccione **Editar** no **Rexistros duplicados** tella.

   :::image type="content" source="media/m3_duplicates_edit.png" alt-text="Captura de pantalla da páxina de rexistros duplicados que mostra o número de rexistros duplicados" lightbox="media/m3_duplicates_edit.png":::

   O número de rexistros duplicados atopados móstrase debaixo **Duplicados**. O **Rexistros deduplicados** A columna mostra que entidades tiñan rexistros duplicados e a porcentaxe de rexistros duplicados.

1. Se engadiu unha entidade enriquecida, seleccione **Usa entidades enriquecidas**. Para obter máis información, consulte [Enriquecemento das fontes de datos](data-sources-enrichment.md).

1. Para xestionar as regras de deduplicación, escolla calquera das seguintes opcións:
   - **Crea unha nova regra** : Seleccionar **Engadir regra** baixo a entidade correspondente. Para obter máis información, consulte [Definir regras de deduplicación](remove-duplicates.md#define-deduplication-rules).
   - **Cambiar as condicións das regras** : Seleccione a regra e despois **Editar**. Cambiar campos, engadir ou eliminar condicións ou engadir ou eliminar excepcións.
   - **Vista previa** : Seleccione a regra e despois **Vista previa** para ver os resultados da última execución desta regra.
   - **Desactivar unha regra** : Seleccione a regra e despois **Desactivar** para manter unha regra de deduplicación ao tempo que a exclúe do proceso de coincidencia.
   - **Duplicar unha regra** : Seleccione a regra e despois **Duplicar** para crear unha regra similar con modificacións.
   - **Eliminar unha regra** : Seleccione a regra e despois **Eliminar**.

1. Para cambiar as preferencias de combinación, seleccione a entidade. Só pode cambiar as preferencias se se crea unha regra.
   1. Seleccione **Edita as preferencias de combinación** e cambia o **Rexistro para gardar** opción.
   1. Para cambiar as preferencias de combinación de atributos individuais dunha entidade, seleccione **Avanzado** e facer os cambios necesarios.

      :::image type="content" source="media/m3_adv_merge.png" alt-text="Captura de pantalla das preferencias de combinación avanzadas que mostra o correo electrónico máis recente e o enderezo máis completo":::

   1. Seleccione **Feito**.

1. Seleccione **A continuación** para facer cambios nas condicións de coincidencia ou seleccione **Garda e pecha** e volver a [Actualiza a configuración de unificación](#update-the-unification-settings).

## <a name="manage-match-rules"></a>Xestionar regras de coincidencia

Pode reconfigurar e axustar a maioría dos parámetros de coincidencia. Non podes engadir nin eliminar entidades. As regras de coincidencia non se aplican a unha única entidade.

1. Seleccione **Editar** no **Condicións de coincidencia** tella.

   :::image type="content" source="media/m3_match_edit.png" alt-text="Captura de pantalla da páxina Regras e condicións de xogo con estatísticas." lightbox="media/m3_match_edit.png":::

   A páxina mostra a orde de coincidencia e as regras definidas e as seguintes estatísticas:
   - **Rexistros de orixe únicos** mostra o número de rexistros de orixes individuais que se procesaron na última execución da busca de coincidencias.
   - **Rexistros coincidentes e non coincidentes** destaca cantos rexistros únicos quedan despois de procesar as regras de busca de coincidencias.
   - **Só rexistros coincidentes** mostra o número de coincidencias en todos os teus pares de coincidencias.

1. Para ver os resultados de todas as regras e as súas puntuacións, seleccione **Ver a última carreira**. Móstrase os resultados, incluídos os ID de contacto alternativos. Podes descargar os resultados.

1. Para ver os resultados e puntuacións dunha determinada regra, seleccione a regra e despois **Vista previa**. Móstrase os resultados. Podes descargar os resultados.

1. Para ver os resultados dunha determinada condición nunha regra, seleccione a regra e despois **Editar**. No panel Editar, seleccione **Vista previa** baixo a condición. Podes descargar os resultados.

   :::image type="content" source="media/m3_match_condition_preview.png" alt-text="Representación gráfica de rexistros non coincidentes e coincidentes, incluíndo unha lista de datos.":::

1. Se engadiu unha entidade enriquecida, seleccione **Usa entidades enriquecidas**. Para obter máis información, consulte [Enriquecemento das fontes de datos](data-sources-enrichment.md).

1. Para xestionar as regras, escolla calquera das seguintes opcións:
   - **Crea unha nova regra** : Seleccionar **Engadir regra** baixo a entidade correspondente. Para obter máis información, consulte [Definir regras para os pares de coincidencias](match-entities.md#define-rules-for-match-pairs).
   - **Cambia a orde das túas regras** se definiu varias regras: arrastre e solte as regras na orde que desexe. Para obter máis información, consulte [Especifique a orde de coincidencia](match-entities.md#specify-the-match-order).
   - **Cambiar as condicións das regras** : Seleccione a regra e despois **Editar**. Cambiar campos, engadir ou eliminar condicións ou engadir ou eliminar excepcións.
   - **Desactivar unha regra** : Seleccione a regra e despois **Desactivar** para conservar unha regra de coincidencia mentres a exclúe do proceso de coincidencia.
   - **Duplicar unha regra** : Seleccione a regra e despois **Duplicar** para crear unha regra similar con modificacións.
   - **Eliminar unha regra** : Seleccione a regra e despois **Eliminar**.

1. Seleccione **A continuación** para facer cambios nos campos unificados ou seleccionar **Garda e pecha** e volver a [Actualiza a configuración de unificación](#update-the-unification-settings).

## <a name="manage-unified-fields"></a>Xestionar campos unificados

1. Seleccione **Editar** no **Campos de clientes unificados** tella.

    :::image type="content" source="media/m3_merge_edit.png" alt-text="Captura de pantalla dos campos de clientes unificados":::

1. Revisa os campos combinados e excluídos e fai os cambios necesarios. Engade ou edite a clave CustomerID ou agrupa os perfís en clústeres. Para obter máis información, consulte [Unificar campos de clientes](merge-entities.md).

1. Seleccione **A continuación** para revisar a configuración de unificación e [actualizar o perfil unificado e as dependencias](#run-updates-to-the-unified-customer-profile), ou seleccione **Garda e pecha** e volver a [Actualiza a configuración de unificación](#update-the-unification-settings) para facer máis cambios.

## <a name="run-matching-conditions"></a>Executar condicións coincidentes

Executar condicións de coincidencia executa só a deduplicación e as regras de coincidencia e actualiza o *Deduplicación_* * e *ConflationMatchPair* entidades.

1. Dende **Datos** > **Unificar** páxina, seleccione **Executar só condicións coincidentes**.

   O **Rexistros duplicados** e **Condicións de coincidencia** mostra de azulexos **En cola** ou **Refrescante** estado.

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

1. Cando finalice o proceso de coincidencia, seleccione **Editar** no **Condicións de coincidencia** tella.

   :::image type="content" source="media/match-KPIs.png" alt-text="Captura de pantalla recortada das métricas clave da páxina de coincidencias con números e detalles.":::

1. Para facer cambios, consulte [Xestionar regras de deduplicación](#manage-deduplication-rules) ou [Xestionar as regras de xogo](#manage-match-rules).

1. Executa o proceso de coincidencia de novo ou [executar actualizacións do perfil do cliente](#run-updates-to-the-unified-customer-profile).

## <a name="run-updates-to-the-unified-customer-profile"></a>Executa actualizacións do perfil de cliente unificado

1. Dende **Datos** > **Unificar** páxina, seleccione:

   - **Unificar os perfís de clientes** : executa condicións coincidentes e actualiza a entidade unificada do perfil do cliente sen afectar as dependencias (como enriquecementos, segmentos ou medidas). Os procesos dependentes non se executan, pero actualizaranse como [definido no programa de actualización](system.md#schedule-tab).

   - **Unifica os perfís de clientes e as dependencias** : executa as condicións coincidentes e actualiza o perfil unificado e todas as dependencias. Todos os procesos reexecútanse automaticamente. Despois de que se completaron todos os procesos posteriores, o perfil do cliente reflicte os datos actualizados.

   O **Rexistros duplicados**, **de coincidencia**, e **Campos de clientes unificados** mostra de azulexos **En cola** ou **Refrescante** estado.

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Os resultados dunha execución exitosa móstranse no **Unificar** páxina que mostra o número de perfís de clientes unificados.
