---
title: Conectarse a entidades do lago xestionado de Common Data Service
description: Importar datos dun lago de datos xestionado de Common Data Service.
ms.date: 09/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.reviewer: adkuppa
ms.openlocfilehash: 029857e2bbb5f6357a5c01138ceaad78887b7518
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643396"
---
# <a name="connect-to-data-in-a-common-data-service-managed-data-lake"></a>Conectar cos datos dun lago de datos xestionado de Common Data Service

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Este artigo ofrece información sobre como os clientes existentes de Dynamics 365 poden conectarse rapidamente ás súas entidades analíticas no lago xestionado de Common Data Service. Debe ser administrador na organización de Common Data Service para continuar e ver a lista de entidades dispoñibles no lago xestionado.

## <a name="important-considerations"></a>Consideracións importantes

Os datos almacenados nos servizos en liña como Azure Data Lake Storage poden almacenarse nunha localización diferente a onde se procesaron ou almacenaron os datos en Dynamics 365 Customer Insights. Ao importar ou conectarse a datos almacenados en servizos en liña, acepta que os datos poden ser transferidos a e almacenados con Dynamics 365 Customer Insights. [Obteña máis información no Centro de confianza de Microsoft.](https://www.microsoft.com/trust-center)

## <a name="connect-to-a-common-data-service-managed-lake"></a>Conectarse a un lago xestionado por Common Data Service

1. Na información do público, vaia a **Datos** > **Orixes de datos**.

2. Seleccione **Engadir orixe de datos**.

3. Seleccione **Conectar a Common Data Service** e seleccione **Seguinte**.

4. Escriba un **Nome** para a orixe de datos e seleccione **Seguinte**.

5. Proporcione o **Enderezo do servidor** da súa organización de Common Data Service e seleccione **Iniciar sesión**.

   > [!div class="mx-imgBorder"]
   > ![Caixa de diálogo para inserir o enderezo do servidor de Common Data Service](media/enter-CDS-org-details.png)

6. Seleccione as entidades que desexa inxerir na lista dispoñible.    

   > [!NOTE]
   > Se algunhas entidades xa están seleccionadas, poderían ser empregadas por outras aplicacións de Dynamics 365 (como Dynamics 365 Sales Insights ou Customer Service Insights). Non se pode cambiar a selección. Estas entidades estarán dispoñibles unha vez que se cree a orixe de datos.

   > [!div class="mx-imgBorder"]
   > ![Caixa de diálogo que mostra unha lista de entidades na organización Common Data Service](media/select-analytical-entities.png)

7. Garde a selección para comezar a sincronizar as entidades seleccionadas no lago xestionado por Common Data Service. Atopará a conexión acabada de engadir na páxina **Orixes de datos**. Porase en cola para actualizar e mostrar o reconto de entidades como 0 ata que se sincronicen todas as entidades.

Só unha orixe de datos dun ambiente pode usar ao mesmo tempo o mesmo lago xestionado de Common Data Service.

## <a name="edit-a-common-data-service-managed-lake-data-source"></a>Editar unha orixe de datos de lago xestionado por Common Data Service

Só edita a selección da entidades despois de crear a orixe de datos. Por exemplo, se se engadiron entidades adicionais a Common Data Service e tamén quere importalos.    
Para conectar cun Common Data Service diferente, [cree unha orixe de datos nova](#connect-to-a-common-data-service-managed-lake).

1. Na información do público, vaia a **Datos** > **Orixes de datos**.

2. A carón da orixe de datos que desexa actualizar, seleccione os tres puntos.

3. Seleccione a opción **Editar** da lista.

4. Seleccione entidades adicionais da lista de entidades dispoñibles e seleccione **Gardar**.
