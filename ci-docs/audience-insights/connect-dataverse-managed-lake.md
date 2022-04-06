---
title: Conectarse con táboas en Microsoft Dataverse
description: Importar datos dun lago de datos xestionado de Microsoft Dataverse.
ms.date: 03/18/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: mhart
searchScope:
- ci-dataverse
- customerInsights
ms.openlocfilehash: 81412ea8259e690eb839676d82ab31847854a97e
ms.sourcegitcommit: a8e99cf8b23ccc00d76c1dee22afd808a160a5c8
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 03/22/2022
ms.locfileid: "8464064"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Conectar cos datos dun lago de datos xestionado de Microsoft Dataverse

Este artigo ofrece información sobre como Dataverse os usuarios poden conectarse rapidamente a entidades analíticas nun Microsoft Dataverse lago xestionado. 

> [!NOTE]
> Debes ser administrador do Dataverse organización para continuar e ver a lista de entidades dispoñibles no lago xestionado.

## <a name="important-considerations"></a>Consideracións importantes

1. Os datos almacenados nos servizos en liña como Azure Data Lake Storage poden almacenarse nunha localización diferente a onde se procesaron ou almacenaron os datos en Dynamics 365 Customer Insights.Ao importar ou conectarse a datos almacenados nos servizos en liña, acepta que os datos se poidan transferir e almacenar con Dynamics 365 Customer Insights . [Máis información no Microsoft Trust Center](https://www.microsoft.com/trust-center).
2. Só Dataverse entidades con [seguimento de cambios](/power-platform/admin/enable-change-tracking-control-data-synchronization) habilitados son visibles. Estas entidades pódense exportar ao Dataverse -lago de datos xestionado e usado en Customer Insights. Fóra de caixa Dataverse As táboas teñen o seguimento de cambios activado por defecto. Debes activar o seguimento de cambios nas táboas personalizadas. Para comprobar se a Dataverse a táboa está habilitada para o seguimento de cambios, vaia a [Power Apps](https://make.powerapps.com) > **Datos** > **Táboas**. Busca a táboa do teu interese e selecciónaa. Ir a **Configuración** > **Opcións avanzadas** e revisa o **Rastrexa os cambios** configuración.

## <a name="connect-to-a-dataverse-managed-lake"></a>Conectarse a un lago xestionado por Dataverse

1. Na información do público, vaia a **Datos** > **Orixes de datos**.

2. Seleccione **Engadir orixe de datos**.

3. Seleccione **Microsoft Dataverse** e selecciona **A continuación**.

4. Escriba un **Nome** para a orixe de datos e seleccione **Seguinte**. 

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
