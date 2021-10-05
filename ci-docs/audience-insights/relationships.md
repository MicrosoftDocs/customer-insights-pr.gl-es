---
title: Relacións entre entidades e camiños das entidades
description: Cree e xestione relacións entre entidades a partir de varias fontes de datos.
ms.date: 09/27/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
ms.openlocfilehash: c639cfca30cf1b57ada7d728311210b7210a37ac
ms.sourcegitcommit: f72d5b86dfdc7282c6c1918b1ab3962d7a1c9852
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 09/27/2021
ms.locfileid: "7557350"
---
# <a name="relationships-between-entities"></a>Relacións entre entidades

As relacións conectan entidades e definen un gráfico dos seus datos cando as entidades comparten un identificador común, unha clave externa. A esta clave externa pódese facer referencia desde unha entidade a outra. As entidades conectadas permiten a definición de segmentos e medidas en función de varias orixes de datos.

Hai tres tipos de relacións: 
- Relacións do sistema non editables, creadas polo sistema como parte do proceso de unificación de datos
- Relacións herdadas non editables, que se crean automaticamente a partir da inxestión de orixes de datos 
- Relacións personalizadas editables, creadas e configuradas polos usuarios

## <a name="non-editable-system-relationships"></a>Relacións do sistema non editables

Durante a unificación de datos, as relacións do sistema créanse automaticamente baseándose en coincidencias intelixentes. Estas relacións axudan a relacionar os rexistros do perfil de cliente cos correspondentes rexistros. O seguinte diagrama ilustra a creación de tres relacións baseadas no sistema. A entidade de cliente coincide con outras entidades para producir a entidade *Cliente* unificada.

:::image type="content" source="media/relationships-entities-merge.png" alt-text="Diagrama con camiños de relacións para a entidade de cliente con tres relacións 1-N.":::

- **A relación *CustomerToContact*** creouse entre a entidade *Cliente* e a entidade de *contacto*. A entidade *Cliente* recibe o campo clave **Contact_contactID** para relacionarse co campo clave da entidade de *contacto* **contactID**.
- **A relación *CustomerToAccount*** creouse entre a entidade *Cliente* e a entidade da *conta*. A entidade *Cliente* recibe o campo clave **Account_accountID** para relacionarse co campo clave da entidade da *conta* **accountID**.
- **A relación *CustomerToWebAccount*** creouse entre a entidade *Cliente* e a entidade *WebAccount*. A entidade *Cliente* recibe o campo clave **WebAccount_webaccountID** para relacionarse co campo clave da entidade *WebAccount* **webaccountID**.

## <a name="non-editable-inherited-relationships"></a>Relacións herdadas non editables

Durante o proceso de inxestión de datos, o sistema comproba as orixes de datos para as relacións existentes. Se non existe ningunha relación, o sistema créaas automaticamente. Estas relacións úsanse tamén en procesos descendentes.

## <a name="create-a-custom-relationship"></a>Crear unha relación personalizada

Unha relación consiste nunha *entidade de orixe* que contén a clave externa e a *entidade de destino* á que apunta a clave externa da entidade de orixe. 

1. Na información do público, vaia a **Datos** > **Relacións**.

2. Seleccione **Nova relación**.

3. No panel **Nova relación**, forneza a seguinte información:

   :::image type="content" source="media/relationship-add.png" alt-text="Panel lateral Nova relación con campos de entrada baleiros.":::

   - **Nome da relación**: nome que reflicte o propósito da relación. Exemplo: CustomerToSupportCase.
   - **Descrición**: descrición da relación.
   - **Entidade de orixe**: entidade que se usa como orixe na relación. Exemplo: SupportCase.
   - **Entidade de destino**: entidade que se usa como destino na relación. Exemplo: Cliente.
   - **Cardinalidade de orixe**: especifique a cardinalidade da entidade de orixe. A cardinalidade describe o número de elementos posibles nun conxunto. Sempre se relaciona coa cardinalidade de destino. Pode escoller entre **Un** e **Moitos**. Só se admiten relacións de moitos a un e dun a un.  
     - Moitos a un: varios rexistros de orixe poden relacionarse cun rexistro de destino. Exemplo: varios casos de asistencia técnica dun único cliente.
     - Un a un: un único rexistro de orixe relaciónase cun rexistro de destino. Exemplo: un ID de fidelidade para un único cliente.

     > [!NOTE]
     > Pódense crear relacións de moitos a moitos usando dúas relacións de moitos a un e unha entidade de ligazón, que conecta a entidade de orixe e a entidade de destino.

   - **Cardinalidade obxectivo**: seleccione a cardinalidade dos rexistros de entidades de destino. 
   - **Campo da clave de orixe**: o campo de clave externa na entidade de orixe. Exemplo: SupportCase podería usar CaseID como campo de clave externa.
   - **Campo da clave obxectivo**: o campo da clave da entidade de destino. Exemplo: o cliente podería usar o campo da clave **CustomerID**.

4. Seleccione **Gardar** para crear a relación personalizada.

## <a name="view-relationships"></a>Ver relacións

A páxina Relacións enumera todas as relacións que se crearon. Cada fila representa unha relación, que tamén inclúe detalles sobre a entidade de orixe, a entidade de destino e a cardinalidade. 

:::image type="content" source="media/relationships-list.png" alt-text="Lista de relacións e opcións na barra de acción da páxina Relacións.":::

Esta páxina ofrece un conxunto de opcións para as relacións novas e existentes: 
- **Nova relación**: [cree unha relación personalizada](#create-a-custom-relationship).
- **Visualizador**: [explore o visualizador de relacións](#explore-the-relationship-visualizer) para ver un diagrama de rede das relacións existentes e a súa cardinalidade.
- **Filtrar por**: elixa o tipo de relacións que se amosarán na lista.
- **Buscar relacións**: use unha busca baseada en texto sobre as propiedades das relacións.

### <a name="explore-the-relationship-visualizer"></a>Explorar o visualizador de relacións

O visualizador de relacións mostra un diagrama de rede das relacións existentes entre as entidades conectadas e a súa cardinalidade. Tamén visualiza o camiño da relación.

Para personalizar a vista, pode cambiar a posición das caixas arrastrándoas sobre o lenzo.

:::image type="content" source="media/relationship-visualizer.png" alt-text="Captura de pantalla do diagrama de rede do visualizador de relacións con conexións entre entidades relacionadas.":::

Opcións dispoñibles: 
- **Exportar como imaxe**: garde a vista actual como un ficheiro de imaxe.
- **Cambiar a deseño horizontal ou vertical**: cambie o aliñamento das entidades e das relacións.
- **Editar**: actualice as propiedades das relacións personalizadas no panel de edición e garde os cambios.

## <a name="relationship-paths"></a>Camiños da relación

Un camiño de relación describe as entidades que están conectadas con relacións entre unha entidade de orixe e unha entidade de destino. Úsase cando se crea un segmento ou unha medida que inclúe outras entidades distintas da entidade do perfil unificado e hai varias opcións para chegar á entidade do perfil unificado. 

Un camiño de relación informa ao sistema sobre cales son as relacións para acceder á entidade de perfil unificado. Diferentes camiños de relación poden dar resultados diferentes.

Por exemplo, a entidade *eCommerce_eCommercePurchases* ten as seguintes relacións coa entidade *Cliente* do perfil unificado:

- eCommerce_eCommercePurchases > Cliente
- eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > Cliente
- eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > loyaltyScheme_loyCustomers > Cliente 

Un camiño de relación determina que entidades pode usar ao crear regras para medidas ou segmentos. Escoller a opción co camiño de relación máis longo probablemente dea menos resultados, porque os rexistros coincidentes deben formar parte de todas as entidades. Neste exemplo, un cliente ten que mercar bens a través dun comercio electrónico (eCommerce_eCommercePurchases), nun punto de venda (POS_posPurchases) e participar no noso programa de fidelidade (loyaltyScheme_loyCustomers). Se escolle a primeira opción, é probable que obteña máis resultados porque os clientes só precisan existir nunha entidade adicional.

### <a name="direct-relationship"></a>Relación directa

Unha relación clasifícase como **relación directa** cando unha entidade de orixe se relaciona cunha entidade de destino cunha soa relación.

Por exemplo, se unha entidade de actividade chamada *eCommerce_eCommercePurchases* conéctase a unha entidade de destino *eCommerce_eCommerceContacts* a través de *ContactId* só, é unha relación directa.

:::image type="content" source="media/direct_Relationship.png" alt-text="A entidade de orixe conéctase directamente coa entidade de destino.":::

#### <a name="multi-path-relationship"></a>Relación de varios camiños

Unha **relación de varios camiños** é un tipo especial de relación directa que conecta unha entidade de orixe a máis dunha entidade de destino.

Por exemplo, se unha entidade de actividade chamada *eCommerce_eCommercePurchases* está relacionada con dúas entidades de destino, *eCommerce_eCommerceContacts* e *loyaltyScheme_loyCustomers*, é unha relación de varios camiños.

:::image type="content" source="media/multi-path_relationship.png" alt-text="A entidade de orixe conéctase directamente a máis dunha entidade de destino a través dunha relación de varios saltos.":::

### <a name="indirect-relationship"></a>Relación indirecta

Unha relación clasifícase como **relación indirecta** cando unha entidade de orixe se relaciona cunha ou máis entidades adicionais antes de relacionarse cunha entidade de destino.

#### <a name="multi-hop-relationship"></a>Relación de varios saltos

Unha *relación de varios saltos* é unha *relación indirecta* que lle permite conectar unha entidade de orixe a unha entidade de destino a través dunha ou máis entidades intermediarias adicionais.

Por exemplo, se unha entidade de actividade chamada *eCommerce_eCommercePurchasesWest* se conecta a unha entidade intermedia chamada *eCommerce_eCommercePurchasesEast* e logo conéctase a unha entidade de destino chamada *eCommerce_eCommerceContacts*, é unha relación de varios saltos.

:::image type="content" source="media/multi-hop_relationship.png" alt-text="A entidade de orixe conéctase directamente a unha entidade de destino cunha entidade intermedia.":::

### <a name="multi-hop-multi-path-relationship"></a>Relación de varios camiños e varios saltos

As relacións de varios saltos e varios camiños pódense usar xuntas para crear **relacións de varios saltos e varios camiños**. Este tipo especial combina as funcións de **varios saltos** e as **relacións de varios camiños**. Permite conectarse a máis dunha entidade de destino mentres usa entidades intermedias.

Por exemplo, se unha entidade de actividade chamada *eCommerce_eCommercePurchasesWest* se conecta a unha entidade intermedia chamada *eCommerce_eCommercePurchasesEast* e logo conéctase a dúas entidades de destino chamadas *eCommerce_eCommerceContacts* e *loyaltyScheme_loyCustomers*, é unha relación de varios saltos e varios camiños.

:::image type="content" source="media/multi-hop_multi-path_relationship.png" alt-text="A entidade de orixe conéctase directamente a unha entidade de destino e conéctase a outra entidade de destino a través dunha entidade intermedia.":::

## <a name="manage-existing-relationships"></a>Xestionar relacións existentes 

Na páxina Relacións, cada relación está representada por unha fila. 

Seleccione unha relación e elixa unha das seguintes opcións: 
 
- **Editar**: actualice as propiedades das relacións personalizadas no panel de edición e garde os cambios.
- **Eliminar**: elimine relacións personalizadas.
- **Ver**: vexa as relacións creadas polo sistema e herdadas. 

## <a name="next-step"></a>Seguinte paso

As relacións personalizadas e do sistema úsanse para [crear segmentos](segments.md) e [medidas](measures.md) baseándose en varias orixes de datos que xa non están en silos.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
