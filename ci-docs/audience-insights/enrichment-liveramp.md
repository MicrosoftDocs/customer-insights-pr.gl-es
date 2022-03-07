---
title: Enriquecemento de datos de identidade LiveRamp
description: Enriquece os perfís de clientes con datos de LiveRamp.
ms.date: 03/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: ee65cb49447df61dd5c298a84ad21bc119ead558
ms.sourcegitcommit: bb1f9e96023490ab340c114f54200ab4dd48da78
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 03/02/2022
ms.locfileid: "8373060"
---
# <a name="enrich-customer-profiles-with-identity-data-from-liveramp-preview"></a>Enriquece os perfís de clientes con datos de identidade de LiveRamp (vista previa) 

LiveRamp ofrece resolución de identidade sen conexión determinista e consolidación de datos dos clientes. Podes asignar os identificadores persoais dos teus datos de cliente ao gráfico de identidade de AbiliTec e recibir ID de AbiliTec. Despois podes usar estes ID para unificar mellor os datos dos teus clientes. 

## <a name="prerequisites"></a>Requisitos previos 

Para configurar o enriquecemento, débense cumprir os seguintes requisitos previos: 

- Tes unha subscrición activa a LiveRamp. Para obter unha subscrición, póñase en contacto co seu equipo de contas LiveRamp ou a [dynamics@liveramp.com](mailto:dynamics@liveramp.com) para máis información.   

- Unha subscrición activa a AbiliTec cun ID de cliente e un segredo para acceder á API. Para obter máis información, consulte [Centro de desenvolvedores de API AbiliTec](https://developers.liveramp.com/abilitec-api/). 

## <a name="supported-countriesregions"></a>Países ou rexións compatibles 

Actualmente admitimos o enriquecemento dos perfís de clientes con datos de LiveRamp só nos Estados Unidos. 

## <a name="configure-the-enrichment"></a>Configurar o enriquecemento 

1. Vaia a **Datos** > **Enriquecemento** e seleccione o separador **Descubrir**. 

1. Seleccione **Enriquece os meus datos** no **Identidade** tella. 

   :::image type="content" source="media/liveramp-tile.png" alt-text="Mosaico de identidade na páxina de descrición xeral do enriquecemento.":::

1. Seleccione unha [conexión](connections.md) da lista despregable. Póñase en contacto cun administrador se non hai conexión dispoñible. Se es administrador, podes crear unha conexión seleccionando **Engadir conexión**. Escolle **LiveRamp** da lista despregable. 

1. Seleccione **A continuación** e escolle o **Conxunto de datos do cliente** quere enriquecer con datos de identidade de LiveRamp. Podes seleccionar o *Cliente* entidade para enriquecer todos os seus perfís de clientes ou seleccionar a *segmento* entidade para enriquecer só os perfís de clientes contidos nese segmento. 

1. Seleccione **A continuación** e define que tipo de campos dos teus perfís unificados se deben usar para buscar datos de identidade coincidentes de LiveRamp. Polo menos un dos campos **Nome e enderezo**, **·**, ou **Correo electrónico** é requerido. 

   > [!TIP]
   > Cantos máis identificadores de clave e campos mapees, máis probabilidade de que exista unha taxa de coincidencia máis alta 

1. Mapea os campos do teu unificado *Cliente* entidade que se utilizará para facer coincidir co gráfico AbiliTec ID de LiveRamp. 

   :::image type="content" source="media/liveramp-data-mapping.png" alt-text="Opcións de asignación de datos para o enriquecemento LiveRamp.":::

1. Seleccione **Seguinte** para concluír a asignación do campo. 

1. Proporcionar a **Nome** para o enriquecemento e o **Entidade de saída**. 

1. Seleccione **Gardar enriquecemento** despois de revisar as súas opcións. 

## <a name="configure-the-connection-for-liveramp"></a>Configure a conexión para LiveRamp 

Debes ser administrador para [configurar conexións](connections.md). Seleccione **Engadir conexión** ao configurar o enriquecemento ou ir a **Admin** > **Conexións** e selecciona **Montar** no **LiveRamp** tella. 

:::image type="content" source="media/liveramp-connection.png" alt-text="Panel de configuración para configurar a conexión co servizo LiveRamp AbiliTec.":::

1. Para **Nome para mostrar**, introduza o nome da conexión. 

1. Proporcione un ID de cliente LiveRamp válido e un segredo. 

1. Revise e proporcione o seu consentimento para a **Privacidade e cumprimento dos datos** seleccionando a caixa de verificación **Estou de acordo**. 

1. Seleccione **Verificar** para validar a configuración. 

1. Para completar a conexión, seleccione **Gardar**. 

## <a name="enrichment-results"></a>Resultados de enriquecemento 

Para iniciar o proceso de enriquecemento, seleccione Executar na barra de comandos. Tamén podes permitir que o sistema execute o enriquecemento automaticamente como parte dun [actualización programada](system.md#schedule-tab). O tempo de procesamento depende do tamaño dos datos dos clientes. 

Unha vez que se complete o proceso de enriquecemento, podes revisar os datos dos perfís de clientes recentemente enriquecidos a continuación **Os meus enriquecementos**. Ademais, atopará a hora da última actualización e o número de perfís enriquecidos. 

Podes acceder a unha vista detallada de cada perfil enriquecido seleccionando **Vista enriquecida** datos. 

## <a name="next-steps"></a>Pasos seguintes

Crear sobre os seus datos enriquecidos de clientes. Use os ID de AbiliTec para consolidar os perfís dos clientes nunha vista baseada na persoa. 
[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Cumprimento e privacidade dos datos 

Cando habilitas Dynamics 365 Customer Insights para transmitir datos a LiveRamp, permite a transferencia de datos fóra dos límites de conformidade Dynamics 365 Customer Insights, incluíndo datos potencialmente sensibles, como os datos persoais. Microsoft transferirá eses datos segundo as súas instrucións, pero vostede é responsable de asegurarse de que LiveRamp cumpra as obrigas de privacidade ou seguridade que poida ter. Para obter máis información, revise [Declaración de privacidade de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732). O administrador de Dynamics 365 Customer Insights pode eliminar este enriquecemento en calquera momento para interromper o uso desta funcionalidade. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
