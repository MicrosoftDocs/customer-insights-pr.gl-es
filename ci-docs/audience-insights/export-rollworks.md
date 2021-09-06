---
title: Exportar datos de Customer Insights a RollWorks
description: Aprenda a configurar a conexión e exportar a RollWorks.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d8ce4d867835dcb7cf56c6fffff4e25d1f5c109af0e401fc0eb8b3a7427c1de4
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034588"
---
# <a name="export-segments-to-rollworks-preview"></a>Exportar segmentos a RollWorks (versión preliminar)

Exporte segmentos de perfís de clientes unificados a RollWorks e utilíceos para a publicidade. 

## <a name="prerequisites-for-a-connection"></a>Requisitos previos para unha conexión

-   Ten unha [conta de RollWorks](https://www.rollworks.com/) e as correspondentes credenciais de administrador.
-   Ten [segmentos configurados](segments.md) na información do público.
-   Os perfís de clientes unificados nos segmentos exportados conteñen un campo que representa un enderezo de correo electrónico.

## <a name="known-limitations"></a>Limitacións coñecidas

- Pode exportar ata 250.000 perfís por exportación a RollWorks.
- Non pode exportar segmentos con menos de 100 perfís a RollWorks. 
- A exportación a RollWorks está limitada a segmentos.
- A exportación de segmentos de ata 250.000 perfís a RollWorks pode tardar ata 10 minutos en finalizar. 
- O número de perfís que pode exportar a RollWorks depende e está limitado ao seu contrato con RollWorks.

## <a name="set-up-connection-to-rollworks"></a>Configurar conexión a RollWorks

1. Vaia a **Administrar** > **Conexións**.

1. Seleccione **Engadir conexión** e elixa **RollWorks** para configurar a conexión.

1. Déalle á conexión un nome recoñecible no campo **Nome para mostrar**. O nome e o tipo de conexión describen esta conexión. Recomendamos escoller un nome que explique o propósito e o destino da conexión.

1. Escolla quen pode usar esta conexión. Se non realiza ningunha acción, o valor predeterminado será Administradores. Para obter máis información, consulte [Permitir aos colaboradores usar unha conexión para as exportacións](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Seleccione **Estou de acordo** para confirmar a **Privacidade e cumprimento dos datos**.

1. Seleccione **Conectar** para iniciar a conexión a RollWorks.

1. Seleccione **Autenticarse con RollWorks** e proporcione as súas credenciais de administrador de RollWorks.

1. Seleccione **Autoengadirse como usuario de exportación** e proporcione as súas credenciais de Customer Insights.

1. Seleccione **Gardar** para completar a conexión.

## <a name="configure-an-export"></a>Configurar unha exportación

Pode configurar esta exportación se ten acceso a unha conexión deste tipo. Para obter máis información, consulte [Permisos necesarios para configurar unha exportación](export-destinations.md#set-up-a-new-export).

1. Vaia a **Datos** > **Exportacións**.

1. Seleccione **Engadir destino** para crear unha nova exportación.

1. No campo **Conexión da exportación** escolla unha conexión da sección RollWorks. Se non ve o nome desta sección, non hai conexións deste tipo dispoñibles para vostede.

1. Introduza o seu **ID de anunciante de RollWorks** [Publicidade de RollWorks](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).

3. Na sección **Coincidencia de datos**, no campo **Correo electrónico**, seleccione o campo do seu perfil de cliente unificado que representa o enderezo de correo electrónico dun cliente. É necesario exportar segmentos a RollWorks.

1. Seleccione os segmentos que desexa exportar. Seleccione un segmento cun mínimo de 100 membros. Non pode exportar segmentos máis pequenos. Ademais, o tamaño máximo dun segmento para exportar é de 250.000 membros por exportación. 

1. Seleccione **Gardar**.

Ao gardar unha exportación non se executa a exportación inmediatamente.

A exportación execútase con cada [actualización programada](system.md#schedule-tab). Tamén pode [exportar datos baixo demanda](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Cumprimento e privacidade dos datos

Cando habilita Dynamics 365 Customer Insights para transmitir datos a RollWorks, permite a transferencia de datos fóra do límite de cumprimento de Dynamics 365 Customer Insights, incluíndo datos potencialmente confidenciais como os datos persoais. Microsoft transferirá estes datos segundo a súa instrución, pero vostede é responsable de asegurarse de que RollWorks cumpra as obrigas de privacidade ou seguridade que poida ter. Para obter máis información, consulte a [Declaración de privacidade de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

O administrador de Dynamics 365 Customer Insights pode eliminar este destino de exportación en calquera momento para interromper o uso desta funcionalidade.
