---
title: Relacións entre entidades e camiños das entidades
description: Cree e xestione relacións entre entidades a partir de varias fontes de datos.
ms.date: 04/14/2020
ms.reviewer: mukeshpo
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 295c372bb452e7c40aa950506dc494d4a2de1108
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405739"
---
# <a name="relationships-between-entities"></a>Relacións entre entidades

As relacións axúdanlle a conectar entidades e a xerar un gráfico dos seus datos cando as entidades comparten un identificador común (clave estranxeira) ao que se pode facer referencia dunha entidade a outra. As entidades conectadas permiten definir segmentos e medidas en función de varias orixes de datos.

Hai dous tipos de relacións. As relacións do sistema non editables, que se crean automaticamente, e as relacións personalizadas creadas e configuradas polos usuarios.

Durante os procesos de combinación e localización de coincidencias, as relacións do sistema créanse entre bastidores baseándose nunha correspondencia intelixente. Estas relacións axudan a relacionar os rexistros do perfil de cliente con rexistros doutras entidades correspondentes. O seguinte diagrama ilustra a creación de tres relacións do sistema cando a entidade de cliente se emparella con entidades adicionais para producir a entidade de perfil de cliente final.

> [!div class="mx-imgBorder"]
> ![Creación de relacións](media/relationships-entities-merge.png "Creación de relacións")

- A **relación *CustomerToContact*** creouse entre a entidade cliente e a entidade de contacto. A entidade de cliente recibe o campo clave **Contact_contactId** para relacionarse co campo clave da entidade de contacto **contactId**.
- A **relación _CustomerToAccount_** creouse entre a entidade cliente e a entidade da conta. A entidade de cliente recibe o campo clave **Account_accountId** para relacionarse co campo clave da entidade da conta **accountId**.
- A **relación _CustomerToWebAccount_** creouse entre a entidade cliente e a entidade WebAccount. A entidade de cliente recibe o campo clave **WebAccount_webaccountId** para relacionarse co campo clave da entidade WebAccount **webaccountId**.

## <a name="create-a-relationship"></a>Crear unha relación

Defina relacións personalizadas na páxina **Relacións**. Cada relación está formada por unha entidade de Orixe (a entidade que ten a clave estranxeira) e unha entidade de Destino (a entidade á que apunta a clave estranxeira da entidade de orixe).

1. Na información do público, vaia a **Datos** > **Relacións**.

2. Seleccione **Nova relación**.

3. No panel **Engadir relación**, forneza a seguinte información:

   > [!div class="mx-imgBorder"]
   > ![Insira os detalles da relación](media/relationships-add.png "Insira os detalles da relación")

   - **Nome da relación**: nome que reflicte o propósito da relación (por exemplo, **AccountWebLogs**).
   - **Descrición**: descrición da relación.
   - **Entidade de orixe**: seleccione a entidade que se emprega como orixe na relación (por exemplo, WebLog).
   - **Cardinalidade**: selecciona a cardinalidade dos rexistros de entidades de orixe. Por exemplo, "moitos" significa que varios rexistros de Weblog están relacionados cunha WebAccount.
   - **Campo clave de orixe**: representa o campo de clave estranxeiro na entidade de orixe. Por exemplo, WebLog ten o campo de clave estranxeiro **accountId**.
   - **Entidade de destino**: seleccione a entidade que se emprega como destino na relación (por exemplo, WebAccount).
   - **Cardinalidade obxectivo**: seleccione a cardinalidade dos rexistros de entidades de destino. Por exemplo, "un" significa que varios rexistros de Weblog están relacionados cunha WebAccount.
   - **Campo clave obxectivo**: este campo representa o campo clave da entidade de destino. Por exemplo, WebAccount ten o campo de clave **accountId**.

> [!NOTE]
> Só se admiten relacións de moitos a un e dun a un. Pódense crear relacións de moitos a moitos empregando dúas relacións de moitos a un e unha entidade de ligazón (unha entidade que se usa para conectar a entidade de orixe e a entidade de destino).

## <a name="delete-a-relationship"></a>Eliminar unha relación

1. Na información do público, vaia a **Datos** > **Relacións**.

2. Marque as caixas de verificación das relacións que desexe eliminar.

3. Seleccione **Eliminar** na parte superior da táboa **Relacións**.

4. Confirme a eliminación.

## <a name="next-step"></a>Seguinte paso

As relacións do sistema e personalizadas úsanse para crear segmentos baseados en varias orixes de datos que xa non están gardadas en silos. Para obter máis información, consulte [Segmentos](segments.md).
