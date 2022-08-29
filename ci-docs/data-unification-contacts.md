---
title: Crear un perfil de contacto unificado (vista previa)
description: Pasa polo proceso de unificación de datos para crear un único conxunto de datos mestre de contactos.
ms.date: 08/12/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: overview
author: Scott-Stabbert
ms.author: sstabbert
manager: shellyha
searchScope:
- ci-map
- ci-match
- ci-merge
- customerInsights
ms.openlocfilehash: 721f47563582a94b5b8244ca5d5d7d1350695512
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 08/16/2022
ms.locfileid: "9305063"
---
# <a name="create-a-unified-contact-profile-preview"></a>Crear un perfil de contacto unificado (vista previa)

Despois [unificando contas empresariais](map-entities.md), pode opcionalmente unificar contactos para esas contas e vincular os contactos unificados ás contas unificadas. O proceso de unificación de contactos mapea os datos de contactos de varias fontes de datos, elimina os duplicados, fai coincidir os datos entre as entidades, configura o mapeo semántico, crea relacións entre contactos e contas e, a continuación, crea un perfil de contacto unificado.

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

Os primeiros pasos son idénticos aos pasos de unificación de contas.

## <a name="prerequisites"></a>Requisitos previos

Os rexistros da conta e dos contactos deben ter unha clave única (chamada clave externa) que os conecte. Por exemplo, un ID de conta que existe no rexistro da conta e no rexistro de contacto que vincula a conta e o contacto.

## <a name="preview-limitations"></a>Limitacións da vista previa

- Os contactos sen unha ligazón a unha conta son eliminados.
- Se se desduplica unha conta, identifícase un rexistro gañador en función das preferencias de combinación. Os rexistros de perdedores non se seleccionan e, polo tanto, bótanse. Os contactos asociados cos rexistros perdidos son eliminados.
- Unha conta pode ter varios contactos, pero un contacto está ligado a unha única conta.
- Os atributos de contacto asignados no paso de asignación semántica son os únicos atributos que se poden mostrar na tarxeta do Cliente. Non obstante, hai 17 atributos dispoñibles.

## <a name="select-source-fields"></a>Seleccione os campos de orixe

1. Baixo **Unificar contactos (vista previa)**, seleccione **Comezar**.

1. [Seleccione as entidades e os campos](map-entities.md) para as fontes de datos de contacto, incluídas as claves primarias e os tipos de atributos.

1. Seleccione **Seguinte**.

## <a name="remove-duplicate-records"></a>Eliminar rexistros duplicados

1. Opcionalmente, [definir regras de deduplicación](remove-duplicates.md) para as entidades seleccionadas.

1. Seleccione **Seguinte**.

## <a name="match-conditions"></a>Condicións do partido

1. [Define a orde e as regras de xogo](match-entities.md) para a correspondencia entre entidades.

1. Seleccione **Seguinte**.

## <a name="unify-contact-fields"></a>Unifica os campos de contacto

1. [Combina e excluír campos de contacto](merge-entities.md).

1. Seleccione **Seguinte**.

## <a name="define-the-semantic-fields-for-unified-contacts"></a>Definir campos semánticos para contactos unificados

Este paso do proceso de unificación asigna os teus campos de contacto unificados a tipos semánticos. En B-to-B, as tarxetas de clientes mostran contas. Cando se selecciona a tarxeta, móstranse todos os contactos asociados á conta. Os campos que mapeas neste paso son os campos que se mostrarán nas tarxetas.

1. Seleccione o tipo semántico que corresponde a cada campo unificado. Seleccione **Ningún** se non hai un tipo semántico dispoñible.

   :::image type="content" source="media/semantic_mapping.png" alt-text="Captura de pantalla da páxina Campos semánticos para definir os tipos semánticos." lightbox="media/semantic_mapping.png":::

1. Despois de mapear todos os campos unificados, seleccione **A continuación**.

## <a name="set-the-relationship-between-contacts-and-accounts"></a>Establece a relación entre contactos e contas

Este paso do proceso de unificación conecta os teus datos de contacto cos datos da conta correspondente.

1. Para cada entidade, introduza a seguinte información:

   - **Chave estranxeira da entidade de contacto** : Escolla o atributo que conecta a súa entidade de contacto coa conta.
   - **A entidade de contas** : Escolla a entidade da conta asociada ao contacto.

   :::image type="content" source="media/contact_relationship.png" alt-text="Captura de pantalla da páxina de relación para conectar as entidades de contacto e conta.":::

1. Seleccione **Seguinte**.

## <a name="review-contact-unification"></a>Revisa a unificación de contactos

Revisa o resumo dos cambios, crea o perfil unificado e revisa os resultados.

### <a name="review-and-create-contact-profiles"></a>Revisar e crear perfís de contacto

Este último paso do proceso de unificación mostra un resumo dos pasos do proceso e ofrece a oportunidade de facer cambios antes de crear o perfil de contacto unificado.

:::image type="content" source="media/b2b_review_contacts.png" alt-text="Captura de pantalla de Revisar e crear perfís de contacto.":::

1. Seleccione **Editar** en calquera dos pasos de unificación de contactos para revisar e facer calquera cambio.

1. Se estás satisfeito coas túas seleccións, selecciona **Crea perfís de contacto**. O **Unificar** móstrase a páxina mentres se crea o perfil de contacto unificado.
  
   :::image type="content" source="media/b2b_unify_refreshing.png" alt-text="Captura de pantalla da páxina Unify Contacts con mosaicos que mostran En cola ou Actualizando.":::

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

O algoritmo de unificación tarda en completarse e non podes cambiar a configuración ata que se complete.

### <a name="view-the-results-of-contact-unification"></a>Consulta os resultados da unificación de contactos

Despois de completar a unificación, o **Datos** > **Unificar** a páxina mostra o número de perfís de contacto unificados. Os resultados de cada paso do proceso de unificación móstranse en cada ficha. Por exemplo, **Campos de orixe** mostra o número de atributos mapeados (campos) e **Rexistros duplicados** mostra o número de rexistros duplicados atopados.

:::image type="content" source="media/unified_contacts.png" alt-text="Captura de pantalla da páxina Data Unify despois de que os contactos estean unificados.":::

> [!TIP]
> O **Condicións de coincidencia** O mosaico só se mostra se se seleccionaron varias entidades.

Recomendamos que revise os resultados, especialmente a calidade dos seus [regras de coincidencia](data-unification-update.md#manage-match-rules) e refinalos se é necesario.

Cando sexa necesario, [facer cambios na configuración de unificación de contactos](data-unification-update.md) e reexecute o perfil unificado.

### <a name="verify-output-entities-from-data-unification"></a>Verifique as entidades de saída da unificación de datos

Ir a **Datos** > **Entidades** para verificar as entidades de saída.

Chamou a entidade do perfil de contacto unificado *Perfil de contacto*, móstrase no **Entidades semánticas** sección. A primeira execución exitosa de unificación crea o unificado *Perfil de contacto* entidade. Todas as execucións posteriores amplían esa entidade.

O *ContactosCliente* créase a entidade (vista previa) e móstrase no ficheiro **Perfís** sección. Esta entidade contén os datos de contacto sen as ligazóns ás contas. Esta entidade úsase como entrada nos pasos de mapeo semántico e relación de unificación de contactos.

As entidades de deduplicación e combinación créanse e móstranse no ficheiro **Sistema** sección. Co nome créase unha entidade deduplicada para cada unha das entidades fonte **Deduplication_DataSource_Entity**. O **ContactosConflationMatchPairs** a entidade contén información sobre coincidencias entre entidades.

Unha entidade de saída de desduplicación contén a seguinte información:
- Identificadores ou claves
  - Campos de clave primaria e ID alternativo. O campo de ID alternativo está formado por todos os ID alternativos identificados para un rexistro.
  - O campo Deduplication_GroupId mostra o grupo ou clúster identificado dentro dunha entidade que agrupa todos os rexistros similares en función dos campos de desduplicación especificados. Úsase con fins de procesamento do sistema. Se non hai regras de desduplicación manual especificadas e se aplican regras de desduplicación definidas polo sistema, é posible que non atope este campo na entidade de saída da desduplicación.
  - Deduplication_WinnerId: este campo contén o ID gañador dos grupos ou clústeres identificados. Se o Deduplication_WinnerId é o mesmo que o valor da clave primaria para un rexistro, significa que o rexistro é o rexistro gañador.
- Campos empregados para definir as regras de desduplicación.
- Campos Regra e Puntuación para indicar cal das regras de desduplicación se aplicou e a puntuación devolta polo algoritmo de correspondencia.

## <a name="next-step"></a>Seguinte paso

Configurar [actividades](activities.md),[enriquecemento](enrichment-hub.md), ou [relacións](relationships.md) para obter máis información sobre os teus contactos.
