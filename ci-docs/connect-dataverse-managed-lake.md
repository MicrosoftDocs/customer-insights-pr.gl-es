---
title: Conectar cos datos dun lago de datos xestionado de Microsoft Dataverse
description: Importar datos dun lago de datos xestionado de Microsoft Dataverse.
ms.date: 07/26/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: v-wendysmith
searchScope:
- ci-dataverse
- customerInsights
ms.openlocfilehash: b21150a1c51bdad35250cae7fde7f38a014ec876
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 07/28/2022
ms.locfileid: "9206951"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Conectar cos datos dun lago de datos xestionado de Microsoft Dataverse

Microsoft Dataverse os usuarios poden conectarse rapidamente a entidades analíticas nun Microsoft Dataverse lago xestionado. Só unha orixe de datos dun ambiente pode usar ao mesmo tempo o mesmo lago xestionado de Dataverse.

> [!NOTE]
> Debes ser administrador do Dataverse organización para continuar e ver a lista de entidades dispoñibles no lago xestionado.

## <a name="prerequisites"></a>Requisitos previos

- Os datos almacenados nos servizos en liña como Azure Data Lake Storage poden almacenarse nunha localización diferente a onde se procesaron ou almacenaron os datos en Dynamics 365 Customer Insights.Ao importar ou conectarse a datos almacenados nos servizos en liña, acepta que os datos se poidan transferir e almacenar con Dynamics 365 Customer Insights . [Máis información no Microsoft Trust Center](https://www.microsoft.com/trust-center).

- Só Dataverse entidades con [seguimento de cambios](/power-platform/admin/enable-change-tracking-control-data-synchronization) habilitados son visibles. Estas entidades pódense exportar ao Dataverse -lago de datos xestionado e usado en Customer Insights. Fóra da caixa Dataverse As táboas teñen o seguimento de cambios activado por defecto. Debes activar o seguimento de cambios nas táboas personalizadas. Para comprobar se a Dataverse a táboa está habilitada para o seguimento de cambios, vai a [Power Apps](https://make.powerapps.com) > **Datos** > **Táboas**. Busca a táboa do teu interese e selecciónaa. Ir a **Configuración** > **Opcións avanzadas** e revisa o **Rastrexa os cambios** configuración.

## <a name="connect-to-a-dataverse-managed-lake"></a>Conectarse a un lago xestionado por Dataverse

1. Vaia a **Datos** > **Orixes de datos**.

1. Seleccione **Engadir orixe de datos**.

1. Seleccione **Microsoft Dataverse**.

1. Introduza a **Nome** para o orixe de datos e un opcional **Descrición**.

1. Proporcione o **Enderezo do servidor** para a organización de Dataverse e seleccione **Iniciar sesión**.

1. Seleccione as táboas que quere inxerir como entidades a Customer Insights da lista dispoñible.

   > [!NOTE]
   > Se algunhas táboas xa están seleccionadas, poden ser usadas por outras aplicacións de Dynamics 365 (como Dynamics 365 Sales Insights ou Customer Service Insights). Non se pode cambiar a selección. Estas táboas estarán dispoñibles como entidades unha vez que se crea a orixe de datos.

    :::image type="content" source="media/select-dataverse-entities.png" alt-text="Caixa de diálogo que mostra unha lista de entidades no ambiente de Dataverse.":::

1. Garde a selección para comezar a sincronizar as táboas seleccionadas de Dataverse. Atopará a conexión acabada de engadir na páxina **Orixes de datos**. Porase na fila para actualizar e mostrará o número de entidades como 0 ata que se sincronicen todas as táboas seleccionadas.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

A carga de datos pode levar moito tempo. Despois dunha actualización exitosa, os datos inxeridos pódense revisar desde o [**Entidades**](entities.md) páxina.

## <a name="edit-a-dataverse-managed-lake-data-source"></a>Editar unha orixe de datos de lago xestionado por Dataverse

Só edita a selección da entidades despois de crear a orixe de datos. Por exemplo, se se engadiron entidades adicionais a Dataverse e tamén quere importalos.
Para conectarse a outro lago de datos de Dataverse, [cree unha nova orixe de datos](#connect-to-a-dataverse-managed-lake).

1. Vaia a **Datos** > **Orixes de datos**.

1. A carón do orixe de datos que queres actualizar, selecciona **Editar**.

1. Seleccione entidades adicionais da lista de entidades dispoñible.

1. Fai clic **Gardar** para aplicar os seus cambios e volver ao **Fontes de datos** páxina.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
