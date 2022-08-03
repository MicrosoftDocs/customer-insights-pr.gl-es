---
title: Seleccione os campos de orixe para a unificación de datos
description: O primeiro paso do proceso de unificación é seleccionar entidades, atributos, claves primarias e tipos semánticos para asignar datos ao perfil unificado do cliente.
recommendations: false
ms.date: 04/22/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-map
- ci-match
- customerInsights
ms.openlocfilehash: a75218c996b277e00924f2b7b38ea686a1f4dc38
ms.sourcegitcommit: 3c5b0b40b2b45e420015bbdd228ce0e610245e6f
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 07/12/2022
ms.locfileid: "9139780"
---
# <a name="select-source-fields-for-data-unification"></a>Seleccione os campos de orixe para a unificación de datos

O primeiro paso na unificación é seleccionar as entidades e os campos dos teus conxuntos de datos que queres unificar. Seleccione entidades que conteñan detalles relacionados co cliente, como nome, enderezo, número de teléfono e correo electrónico. Pode seleccionar unha ou varias entidades.

## <a name="select-entities-and-fields"></a>Seleccionar entidades e campos

1. Ir a **Datos** > **Unificar**.

   :::image type="content" source="media/m3_unify_land.png" alt-text="Captura de pantalla da páxina de destino unificada para a experiencia de primeira execución con Comezar destacado.":::

1. Seleccione **Comezar**.

1. No **Campos de orixe** páxina, seleccione **Seleccione entidades e campos**. O **Seleccione entidades e campos** pantallas de paneis.

1. Selecciona polo menos unha entidade.

1. Para cada entidade seleccionada, identifique os campos que quere usar para facer coincidir os rexistros de clientes e os campos para incluír no perfil unificado. Estes campos chámanse *Atributos*. Pode seleccionar os atributos necesarios individualmente dunha entidade ou incluír todos os atributos dunha entidade seleccionando a caixa de verificación no nivel de entidade. Pode buscar palabras clave en todos os atributos e entidades para seleccionar os atributos requiridos que desexa asignar.

   :::image type="content" source="media/m3_select_entities.png" alt-text="Captura de pantalla das entidades e atributos seleccionados.":::

   Neste exemplo, estamos engadindo o **Contactos** e **Fidelidade do cliente** entidades. Se escolle estas entidades, pode obter información sobre cales dos clientes comerciais en liña son membros do programa de fidelización.

1. Seleccione **Aplicar** para confirmar as súas seleccións. Móstrase as entidades e os atributos seleccionados.

## <a name="select-primary-key-and-semantic-type-for-attributes"></a>Seleccione a clave primaria e o tipo semántico para os atributos

   :::image type="content" source="media/m3_select_primary.png" alt-text="Captura de pantalla das entidades seleccionadas coa clave principal non seleccionada." lightbox="media/m3_select_primary.png":::

Para cada entidade, realice os seguintes pasos.

1. Escolle o **Chave primaria**. A chave primaria é un atributo exclusivo da entidade. Para que un atributo sexa unha clave primaria válida, non debe incluír valores duplicados, valores perdidos ou valores nulos. Os atributos de tipo de datos de cadea, enteiro e GUID son compatibles como claves primarias.

1. Para usar modelos de IA para predición intelixente de semántica, aforra tempo e mellora a precisión, asegúrate **Cartografía intelixente** está activado. A asignación intelixente resalta a recomendación de semántica baseada en IA no campo **Tipo**. Pode anular a selección suxerida escollendo calquera tipo semántico da lista de opcións dispoñibles.

1. Para cada atributo, escolla unha semántica **Tipo** que mellor describe ese atributo, como nome, cidade ou enderezo de correo electrónico.

   > [!NOTE]
   > Un campo debe asignarse ao tipo semántico *Persoa.Nome Completo* para encher o nome do cliente na tarxeta de cliente. Do contrario, os cartóns de cliente aparecerán sen nome.

   1. Para cambiar un tipo de atributo identificado polo sistema, seleccione outro tipo. Se o tipo non existe, crea un tipo semántico personalizado seleccionando o **Tipo** campo para o atributo e introducindo o nome do seu tipo semántico personalizado.

   1. Para engadir un atributo que conteña un URL a imaxes de perfil ou logotipos dispoñibles publicamente, seleccione a entidade e o campo que contén o URL. No **Tipo** campo, introduza o seguinte:
      - Para unha persoa: Person.ProfileImage
      - Para unha organización: Organization.LogoImage

   1. Para un atributo de nome de conta, introduza "Organization.Name" no campo **Tipo** campo.

1. Revisa os atributos nos que se identifica automaticamente un tipo semántico. Estes atributos están listados en **Revisa os campos mapeados**. Só os atributos co mesmo tipo poden combinarse no **Campos de clientes unificados** paso. Os tipos semánticos utilízanse para suxerir insights automaticamente. Asegúrate de que os tipos que escolleches sexan consistentes en todas as entidades seleccionadas.

1. Para os atributos que non se asignan automaticamente a un tipo semántico, seleccione un campo de tipo semántico, introduza o seu nome de tipo de atributo personalizado ou déixaos sen asignar. Estes atributos están listados en **Defina os datos nos campos non asignados**.

1. Despois de completar os pasos para cada entidade, seleccione **Garda os campos de orixe**.

1. Seleccione **Seguinte**.

> [!div class="nextstepaction"]
> [Seguinte paso: elimina os duplicados](remove-duplicates.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
