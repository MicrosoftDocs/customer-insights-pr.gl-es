---
title: Asignar entidades e atributos para a unificación de datos
description: Seleccione entidades, atributos, claves primarias e tipos semánticos para asignar datos ao perfil de cliente unificado.
ms.date: 10/18/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-map
ms.openlocfilehash: 8b84ed1a860e383e4eb3f7499be6d397ba3f1db1
ms.sourcegitcommit: 31985755c7c973fb1eb540c52fd1451731d2bed2
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 10/22/2021
ms.locfileid: "7673261"
---
# <a name="map-entities-and-attributes"></a>Entidades e atributos do mapa

**Asignar** é a primeira etapa do proceso de unificación de datos da información do público. A asignación consta de tres fases:

- *Selección de entidades*: identifique as entidades combinables que conducen a un conxunto de datos con información máis completa sobre os seus clientes.
- *Selección de atributos*: para cada entidade, identifique as columnas que desexa combinar e reconciliar nas fases *coincidencia* e *combinación*. Estas columnas chámanse *Atributos*.
- *Selección de clave primaria e tipo semántico*: para cada entidade, identifique un atributo que desexe definir como clave principal desa entidade e, para cada atributo, identifique un tipo semántico que describa mellor ese atributo.

Para obter máis información sobre o fluxo xeral de unificación de datos, consulte [Unificar](data-unification.md).

## <a name="select-the-first-entities"></a>Seleccionar as primeiras entidades

1. Na información do público, vaia a **Datos** > **Unificar** > **Asignar**.

2. Inicie a fase de asignación seleccionando **Seleccionar entidades**.

3. Seleccione as entidades e atributos que desexe empregar nas fases *atopar coincidencia* e *combinar*. Pode seleccionar os atributos requiridos individualmente dunha entidade ou incluír todos os atributos dunha entidade seleccionando a caixa de verificación **Incluír todos os campos** a nivel de entidade. Recomendamos seleccionar polo menos dúas entidades para beneficiarse do proceso de unificación de datos.

   > [!div class="mx-imgBorder"]
   > ![Exemplo de engadir entidades.](media/data-manager-configure-map-add-entities-example.png "Exemplo de engadir entidades")

   Neste exemplo, engadimos as entidades **eCommerceContacts** e **loyCustomers**. Se escolle estas entidades, pode obter información sobre cales dos clientes comerciais en liña son membros do programa de fidelización.
   
   Pode buscar palabras clave en todos os atributos e entidades para seleccionar os atributos requiridos que desexa asignar.
   
     > [!div class="mx-imgBorder"]
   > ![Exemplo de campos de busca.](media/data-manager-configure-map-search-fields-example.png "Exemplo de campos de busca")

4. Seleccione **Aplicar** para confirmar as súas seleccións.

## <a name="select-primary-key-and-semantic-type-for-attributes"></a>Seleccione a clave primaria e o tipo semántico para os atributos

Despois de seleccionar as súas entidades, a páxina **Mapa** enumera as entidades seleccionadas para a súa revisión. Defina a clave principal dunha entidade e identifique o tipo semántico dun atributo na entidade.

- **Clave primaria**: seleccione un atributo como clave principal para cada unha das súas entidades. Para que un atributo sexa unha clave primaria válida, non debe incluír valores duplicados, valores perdidos ou valores nulos. Os atributos de tipo de datos de cadea, número enteiro e GUID admítense como claves primarias e amosaranse nun campo onde escoller.

- **Tipo semántico de atributo**: categorías dos seus atributos, como o enderezo de correo electrónico ou o nome. Para usar modelos de IA para a predición intelixente de semántica, aforrar tempo e mellorar a precisión, configure **Asignación intelixente** en **ACTIVADO**. A asignación intelixente resalta a recomendación de semántica baseada en IA no campo **Tipo**. Se a configura en **DESACTIVADO**, verá as nosas recomendacións de asignación regular. Pode seleccionar calquera tipo semántico na lista de opcións dispoñibles e anular a selección suxerida.

> [!div class="mx-imgBorder"]
> ![Tipo de atributo e predición semántica.](media/data-manager-configure-map-add-attributes-semantic-prediction.png "Tipo de atributo e predición semántica")

Tamén é posible engadir un tipo semántico personalizado. Seleccione o campo de tipo dun atributo e escriba o seu nome de tipo semántico personalizado. Deste xeito, tamén pode cambiar os tipos de atributo que foron identificados polo sistema.

Todos os atributos para os que se identifica automaticamente un tipo semántico agrúpanse na sección **Revisa os campos asignados**. Revise estes atributos e os seus tipos semánticos porque se empregarán para combinar as súas entidades no paso de combinación da unificación de datos.

Os atributos que non se asignan automaticamente a un tipo semántico agrúpanse na sección **Definir os datos nos campos non asignados**. Seleccione o campo de tipo semántico para os atributos non asignados ou introduza o seu nome de tipo de atributo personalizado.

> [!div class="mx-imgBorder"]
> ![Clave primaria e tipo de atributo.](media/data-manager-configure-map-add-attributes.png "Clave primaria e tipo de atributo")

> [!NOTE]
> Un campo debería asignarse ao tipo semántico Person.FullName para completar o nome do cliente na tarxeta do cliente. Do contrario, os cartóns de cliente aparecerán sen nome. 

## <a name="add-and-remove-attributes-and-entities"></a>Engadir e eliminar atributos e entidades

1. En **Unificar** > **Mapa**, seleccione **Editar campos**.

2. No panel **Editar campos**, engada ou elimine atributos e entidades. Use a busca ou o desprazamento para atopar e seleccionar os seus atributos e entidades de interese. Non pode eliminar un atributo ou unha entidade se xa coincidiron.

   > [!div class="mx-imgBorder"]
   > ![Engadir ou eliminar atributos.](media/configure-data-map-edit.png "Engadir ou eliminar atributos")

3. Seleccione **Aplicar**.

## <a name="add-images-to-profiles"></a>Engadir imaxes aos perfís

Se unha entidade contén URL para imaxes ou logotipos de perfil dispoñibles publicamente, pode engadilos ao perfil de cliente unificado.

Seleccione a entidade e busque o campo que contén o URL á imaxe de perfil. No campo de entrada **Tipo**, introduza o valor seguinte manualmente: 
- Para unha persoa: Person.ProfileImage
- Para unha organización: Organization.LogoImage

Continúe cos pasos de unificación e asegúrese de que o atributo que contén o URL da imaxe tamén se engada ao paso [Combinar](merge-entities.md).

## <a name="set-attributes-for-organizations"></a>Establecer atributos para organizacións

Para organizacións (vista previa), o tipo de atributo debería asignarse a "Organization.Name"
> [!div class="mx-imgBorder"]
> ![Clave principal e tipo de atributo B-a-B.](media/configure-data-map-edit-b2b.png "Clave principal e tipo de atributo B-a-B")

## <a name="next-step"></a>Seguinte paso

Como parte do proceso de unificación de datos, diríxase á páxina **Coincidencia**. Visite [**Coincidencia**](match-entities.md) para obter información sobre esta fase.

> [!TIP]
> Consulte o seguinte vídeo: [Primeiros pasos: creación dun perfil de cliente unificado](https://youtu.be/oBfGEhucAxs).


[!INCLUDE[footer-include](../includes/footer-banner.md)]