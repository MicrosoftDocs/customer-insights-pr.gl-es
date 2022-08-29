---
title: Actualiza a configuración de unificación de clientes, contas ou contactos
description: Actualiza regras duplicadas, regras de coincidencia ou campos unificados na configuración de unificación de clientes ou contas.
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: Scott-Stabbert
ms.author: sstabbert
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: f2c14c169f5973b5f400989b9eeea593eba09182
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304333"
---
# <a name="update-unification-settings"></a>Actualizar a configuración de unificación

Para revisar ou cambiar calquera configuración de unificación unha vez que se crea un perfil unificado, siga os seguintes pasos.

1. Ir a **Datos** > **Unificar**.

   Para clientes individuais (B-to-C), o **Unificar** a páxina mostra o número de perfís e mosaicos de clientes unificados para cada un dos pasos de unificación.

   :::image type="content" source="media/m3_unified.png" alt-text="Captura de pantalla da páxina Data Unify despois de que os datos se unifiquen." lightbox="media/m3_unified.png":::

   Para contas empresariais (B-to-B), o **Unificar** a páxina mostra o número de perfís de conta e mosaicos unificados para cada un dos pasos de unificación da conta. Se os contactos estaban unificados, móstrase o número de perfís e mosaicos de contactos unificados para cada un dos pasos de unificación de contactos. Escolla a tella adecuada debaixo **Unificar contas** ou **Unificar contactos (vista previa)** dependendo do que queiras actualizar.

   :::image type="content" source="media/b2b_unified.png" alt-text="Captura de pantalla da páxina de Unificación de datos despois de que se unifiquen os datos da conta e dos contactos." lightbox="media/b2b_unified.png":::

   > [!TIP]
   > O **Condicións de coincidencia** O mosaico só se mostra se se seleccionaron varias entidades.

1. Escolle o que queres actualizar:
   - [Campos de orixe](#edit-source-fields) para engadir entidades ou atributos ou cambiar os tipos de atributos.
   - [Rexistros duplicados](#manage-deduplication-rules) para xestionar regras de deduplicación ou combinar preferencias.
   - [Condicións de coincidencia](#manage-match-rules) para actualizar as regras de coincidencia en dúas ou máis entidades.
   - [Campos de clientes unificados](#manage-unified-fields) para combinar ou excluír campos. Tamén pode agrupar perfís relacionados en clústeres.
   - [Campos semánticos](#manage-semantic-fields-for-unified-contacts) para xestionar tipos semánticos para campos de contacto unificados.
   - [Relacións](#manage-contact-and-account-relationships) para xestionar a relación contacto con conta.

1. Despois de facer os cambios, escolla a seguinte opción:

   - [Executar condicións coincidentes](#run-matching-conditions) para avaliar rapidamente a calidade das súas condicións de coincidencia (desduplicación e regras de coincidencia) sen actualizar o perfil unificado. O **Executar só condicións coincidentes** a opción non se mostra para unha única entidade.
   - [Unificar perfís](#run-updates-to-the-unified-profile) para executar condicións coincidentes e actualizar a entidade do perfil unificado sen afectar as dependencias (como enriquecementos, segmentos ou medidas). Os procesos dependentes non se executan, pero actualizaranse como [definido no programa de actualización](schedule-refresh.md).
   - [Unificar perfís e dependencias](#run-updates-to-the-unified-profile) para executar condicións coincidentes, actualizar a entidade do perfil unificado e actualizar todas as dependencias (como enriquecementos, segmentos ou medidas). Todos os procesos reexecútanse automaticamente. En B-to-B, a unificación execútase tanto na conta como nas entidades de contacto que actualizan os perfís unificados.

## <a name="edit-source-fields"></a>Editar campos de orixe

Non podes eliminar un atributo ou unha entidade se xa se unificaron.

1. Seleccione **Editar** no **Campos de orixe** tella.

   :::image type="content" source="media/m3_source_edit.png" alt-text="Captura de pantalla da páxina de campos de orixe que mostra o número de claves primarias, campos asignados e non asignados":::

   Mostra o número de campos asignados e sen asignar.

1. Para engadir outros atributos ou entidades, seleccione **Seleccione entidades e campos**.

1. Opcionalmente, pode cambiar a clave principal dunha entidade, os tipos de atributos e alternar **Cartografía intelixente** on ou off. Para obter máis información, consulte [Seleccione os campos de orixe](map-entities.md).

1. Seleccione **A continuación** para facer cambios nas regras de deduplicación ou seleccionar **Garda e pecha** e volver a [Actualizar a configuración de unificación](#update-unification-settings).

## <a name="manage-deduplication-rules"></a>Xestionar regras de deduplicación

1. Seleccione **Editar** no **Rexistros duplicados** tella.

   :::image type="content" source="media/m3_duplicates_edit.png" alt-text="Captura de pantalla da páxina de rexistros duplicados que mostra o número de rexistros duplicados" lightbox="media/m3_duplicates_edit.png":::

   O número de rexistros duplicados atopados móstrase debaixo **Duplicados**. O **Rexistros deduplicados** A columna mostra que entidades tiñan rexistros duplicados e a porcentaxe de rexistros duplicados.

1. Para utilizar unha entidade enriquecida, seleccione **Usa entidades enriquecidas**. Para obter máis información, consulte [Enriquecemento das fontes de datos](data-sources-enrichment.md).

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

   1. Seleccione **Feito**.

1. Seleccione **A continuación** para facer cambios nas condicións de coincidencia ou seleccione **Garda e pecha** e volver a [Actualizar a configuración de unificación](#update-unification-settings).

## <a name="manage-match-rules"></a>Xestionar regras de coincidencia

Pode reconfigurar e axustar a maioría dos parámetros de coincidencia. Non podes engadir nin eliminar entidades. As regras de coincidencia non se aplican a unha única entidade.

1. Seleccione **Editar** no **Condicións de coincidencia** tella.

   :::image type="content" source="media/m3_match_edit.png" alt-text="Captura de pantalla da páxina Regras e condicións de xogo con estatísticas." lightbox="media/m3_match_edit.png":::

   A páxina mostra a orde de coincidencia e as regras definidas e as seguintes estatísticas:
   - **Rexistros de orixe únicos** mostra o número de rexistros de orixe individuais que se procesaron na última execución da partida.
   - **Rexistros coincidentes e non coincidentes** resaltar cantos rexistros únicos quedan despois de procesar as regras de xogo.
   - **Só rexistros coincidentes** mostra o número de coincidencias en todos os teus pares de coincidencias.

1. Para ver os resultados de todas as regras e as súas puntuacións, seleccione **Ver a última carreira**. Móstrase os resultados, incluídos os ID de contacto alternativos. Podes descargar os resultados.

1. Para ver os resultados e puntuacións dunha determinada regra, seleccione a regra e despois **Vista previa**. Os resultados aparecen. Podes descargar os resultados.

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

1. Seleccione **A continuación** para facer cambios nos campos unificados ou seleccionar **Garda e pecha** e volver a [Actualizar a configuración de unificación](#update-unification-settings).

## <a name="manage-unified-fields"></a>Xestionar campos unificados

1. Seleccione **Editar** no **Campos de clientes unificados** tella.

    :::image type="content" source="media/m3_merge_edit.png" alt-text="Captura de pantalla dos campos de clientes unificados":::

1. Revisa os campos combinados e excluídos e fai os cambios necesarios. Engade ou edite a clave CustomerID ou agrupa os perfís en clústeres. Para obter máis información, consulte [Unificar campos de clientes](merge-entities.md).

1. Para clientes ou contas, seleccione **A continuación** para revisar e [actualizar o perfil unificado e as dependencias](#run-updates-to-the-unified-profile). Ou selecciona **Garda e pecha** e volver a [Actualizar a configuración de unificación](#update-unification-settings) para facer máis cambios.

   Para os contactos, seleccione **A continuación** para xestionar campos semánticos. Ou selecciona **Garda e pecha** e volver a [Actualizar a configuración de unificación](#update-unification-settings) para facer máis cambios.

## <a name="manage-semantic-fields-for-unified-contacts"></a>Xestiona campos semánticos para contactos unificados

1. Seleccione **Editar** no **Campos semánticos** tella.

1. Para cambiar o tipo semántico dun campo unificado, seleccione un novo tipo. Para obter máis información, consulte [Defina os campos semánticos para os contactos unificados](data-unification-contacts.md#define-the-semantic-fields-for-unified-contacts).

1. Seleccione **A continuación** para xestionar a conta e a relación de contacto ou selecciona **Garda e pecha** e volver a [Actualizar a configuración de unificación](#update-unification-settings) para facer máis cambios.

## <a name="manage-contact-and-account-relationships"></a>Xestionar contactos e relacións de contas

1. Seleccione **Editar** no **Relacións** tella.

1. Para cambiar a relación de contacto e conta, cambia calquera das seguintes informacións:

   - **Chave estranxeira da entidade de contacto** : Escolla o atributo que conecta a súa entidade de contacto coa conta.
   - **A entidade de contas** : Escolla a entidade da conta asociada ao contacto.

1. Seleccione **A continuación** para revisar a configuración de unificación e [actualizar o perfil unificado e as dependencias](#run-updates-to-the-unified-profile), ou seleccione **Garda e pecha** e volver a [Actualizar a configuración de unificación](#update-unification-settings) para facer máis cambios.

## <a name="run-matching-conditions"></a>Executar condicións coincidentes

Executar condicións de coincidencia executa só a deduplicación e as regras de coincidencia e actualiza o *Deduplicación_* * e *ConflationMatchPair* entidades.

1. Dende **Datos** > **Unificar** páxina, seleccione **Executar só condicións coincidentes**.

   O **Rexistros duplicados** e **Condicións de coincidencia** mostra de azulexos **En cola** ou **Refrescante** estado.

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

1. Cando finalice o proceso de coincidencia, seleccione **Editar** no **Condicións de coincidencia** tella.

   :::image type="content" source="media/match-KPIs.png" alt-text="Captura de pantalla recortada das métricas clave da páxina de coincidencias con números e detalles.":::

1. Para facer cambios, consulte [Xestionar regras de deduplicación](#manage-deduplication-rules) ou [Xestionar as regras de xogo](#manage-match-rules).

1. Executa o proceso de coincidencia de novo ou [executar actualizacións do perfil](#run-updates-to-the-unified-profile).

## <a name="run-updates-to-the-unified-profile"></a>Executa actualizacións do perfil unificado

- Para executar condicións coincidentes e actualizar a entidade do perfil unificado *sen* dependencias que afectan (como tarxetas de clientes, enriquecementos, segmentos ou medidas), seleccione **Unificar os perfís de clientes**. Para as contas, seleccione **Unificar contas** > **Unificar perfís**. Para os contactos, seleccione **Unificar contactos (vista previa)** > **Unificar perfís**. Os procesos dependentes non se executan, pero actualizaranse como [definido no programa de actualización](schedule-refresh.md).
- Para executar condicións coincidentes, actualizar o perfil unificado e executar todas as dependencias, seleccione **Unifica os perfís de clientes e as dependencias**. Todos os procesos reexecútanse automaticamente. Para contas e contactos, seleccione **Unificar contas** > **Unificar perfís e dependencias**. As condicións coincidentes execútanse tanto para as contas como para os contactos, actualizando os perfís unificados e execútanse todas as demais dependencias.

Todas as tellas excepto **Campos de orixe** mostrar **En cola** ou **Refrescante**.

[!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Os resultados dunha execución exitosa móstranse no **Unificar** páxina que mostra o número de perfís unificados.
