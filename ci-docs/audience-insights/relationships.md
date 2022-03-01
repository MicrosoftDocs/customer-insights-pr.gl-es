---
title: Relacións entre entidades e camiños das entidades
description: Cree e xestione relacións entre entidades a partir de varias fontes de datos.
ms.date: 06/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: d5b9566ec88096fec31d8e164a51598159ec26d4
ms.sourcegitcommit: ece48f80a7b470fb33cd36e3096b4f1e9190433a
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 06/03/2021
ms.locfileid: "6171162"
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

O visualizador de relacións mostra un diagrama de rede das relacións existentes entre as entidades conectadas e a súa cardinalidade.

Para personalizar a vista, pode cambiar a posición das caixas arrastrándoas sobre o lenzo.

:::image type="content" source="media/relationship-visualizer.png" alt-text="Captura de pantalla do diagrama de rede do visualizador de relacións con conexións entre entidades relacionadas.":::

Opcións dispoñibles: 
- **Exportar como imaxe**: garde a vista actual como un ficheiro de imaxe.
- **Cambiar a deseño horizontal ou vertical**: cambie o aliñamento das entidades e das relacións.
- **Editar**: actualice as propiedades das relacións personalizadas no panel de edición e garde os cambios.

## <a name="manage-existing-relationships"></a>Xestionar relacións existentes 

Na páxina Relacións, cada relación está representada por unha fila. 

Seleccione unha relación e elixa unha das seguintes opcións: 
 
- **Editar**: actualice as propiedades das relacións personalizadas no panel de edición e garde os cambios.
- **Eliminar**: elimine relacións personalizadas.
- **Ver**: vexa as relacións creadas polo sistema e herdadas. 

## <a name="next-step"></a>Seguinte paso

As relacións do sistema e personalizadas úsanse para [crear segmentos](segments.md) baseados en varias orixes de datos que xa non están gardadas en silos.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
