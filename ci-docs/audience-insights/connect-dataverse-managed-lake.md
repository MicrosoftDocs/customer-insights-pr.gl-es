---
title: Conectarse con táboas en Microsoft Dataverse
description: Importar datos dun lago de datos xestionado de Microsoft Dataverse.
ms.date: 07/23/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: mhart
ms.openlocfilehash: f92d64723e6a4d2fcebdbb3758519d4bfd4aeaf4
ms.sourcegitcommit: 8cc70f30baaae13dfb9c4c201a79691f311634f5
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 07/30/2021
ms.locfileid: "6692572"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Conectar cos datos dun lago de datos xestionado de Microsoft Dataverse

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Este artigo ofrece información sobre como os usuarios de Dataverse poden conectarse rapidamente coas súas entidades analíticas nun lago xestionado de Dataverse. Debe ser administrador na organización de Dataverse para continuar e ver a lista de entidades dispoñibles no lago xestionado.

## <a name="important-considerations"></a>Consideracións importantes

Os datos almacenados nos servizos en liña como Azure Data Lake Storage poden almacenarse nunha localización diferente a onde se procesaron ou almacenaron os datos en Dynamics 365 Customer Insights. Ao importar ou conectarse a datos almacenados en servizos en liña, acepta que os datos poden ser transferidos a e almacenados con Dynamics 365 Customer Insights. [Obteña máis información no Centro de confianza de Microsoft.](https://www.microsoft.com/trust-center)

## <a name="connect-to-a-dataverse-managed-lake"></a>Conectarse a un lago xestionado por Dataverse

1. Na información do público, vaia a **Datos** > **Orixes de datos**.

2. Seleccione **Engadir orixe de datos**.

3. Seleccione **Conectar cun lago xestionado de Microsoft Dataverse** e seleccione **Seguinte**.

4. Escriba un **Nome** para a orixe de datos e seleccione **Seguinte**. Dea nome ás instrucións: 
   - Comece por unha letra.
   - Use só letras e números. Non se permiten caracteres especiais nin espazos.
   - Empregue entre 3 e 64 caracteres.

5. Proporcione o **Enderezo do servidor** para a organización de Dataverse e seleccione **Iniciar sesión**.

   :::image type="content" source="media/ingest-dataverse-server-address.png" alt-text="Pantalla no paso de inxestión de datos onde un usuario pode introducir o URL do ambiente de Dataverse.":::

6. Seleccione as táboas que desexa inxerir como entidades para a información do público na lista dispoñible.    

   > [!NOTE]
   > Se algunhas táboas xa están seleccionadas, poden ser usadas por outras aplicacións de Dynamics 365 (como Dynamics 365 Sales Insights ou Customer Service Insights). Non se pode cambiar a selección. Estas táboas estarán dispoñibles como entidades unha vez que se crea a orixe de datos.

   :::image type="content" source="media/select-dataverse-entities.png" alt-text="Caixa de diálogo que mostra unha lista de entidades no ambiente de Dataverse.":::

7. Garde a selección para comezar a sincronizar as táboas seleccionadas de Dataverse. Atopará a conexión acabada de engadir na páxina **Orixes de datos**. Porase na fila para actualizar e mostrará o número de entidades como 0 ata que se sincronicen todas as táboas seleccionadas.

Só unha orixe de datos dun ambiente pode usar ao mesmo tempo o mesmo lago xestionado de Dataverse.

## <a name="edit-a-dataverse-managed-lake-data-source"></a>Editar unha orixe de datos de lago xestionado por Dataverse

Só edita a selección da entidades despois de crear a orixe de datos. Por exemplo, se se engadiron entidades adicionais a Dataverse e tamén quere importalos.    
Para conectarse a outro lago de datos de Dataverse, [cree unha nova orixe de datos](#connect-to-a-dataverse-managed-lake).

1. Na información do público, vaia a **Datos** > **Orixes de datos**.

2. A carón da orixe de datos que desexa actualizar, seleccione os tres puntos.

3. Seleccione a opción **Editar** da lista.

4. Seleccione entidades adicionais da lista de entidades dispoñibles e seleccione **Gardar**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]