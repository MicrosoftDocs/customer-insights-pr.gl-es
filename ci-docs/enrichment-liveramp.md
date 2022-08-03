---
title: Enriquece os perfís de clientes con datos de identidade de LiveRamp (vista previa)
description: Enriquece os perfís de clientes con datos de LiveRamp.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 49bf558209ca91ab9d8db945862a57adccee1f6b
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196346"
---
# <a name="enrich-customer-profiles-with-identity-data-from-liveramp-preview"></a>Enriquece os perfís de clientes con datos de identidade de LiveRamp (vista previa)

LiveRamp ofrece resolución de identidade sen conexión determinista e consolidación de datos dos clientes. Podes asignar os identificadores persoais dos teus datos de cliente ao gráfico de identidade de AbiliTec e recibir ID de AbiliTec. Despois podes usar estes ID para unificar mellor os datos dos teus clientes.

## <a name="supported-countriesregions"></a>Países ou rexións compatibles

Actualmente admitimos o enriquecemento dos perfís de clientes con datos de LiveRamp só nos Estados Unidos.

## <a name="prerequisites"></a>Requisitos previos

- Unha subscrición activa a LiveRamp. Para obter unha subscrición, póñase en contacto co seu equipo de contas LiveRamp ou a [dynamics@liveramp.com](mailto:dynamics@liveramp.com) para máis información.

- Unha subscrición activa a AbiliTec cun ID de cliente e un segredo para acceder á API. Para obter máis información, consulte [Centro de desenvolvedores de API AbiliTec](https://developers.liveramp.com/abilitec-api/).

- Un LiveRamp [conexión](connections.md) é [configurado](#configure-the-connection-for-liveramp) por un administrador.

## <a name="configure-the-connection-for-liveramp"></a>Configure a conexión para LiveRamp

Debes ser un [administrador](permissions.md#admin) en Customer Insights e ten un ID de cliente e un segredo activos de LiveRamp.

1. Seleccione **Engadir conexión** ao configurar un enriquecemento ou vaia a **Admin** > **Conexións** e selecciona **Montar** no mosaico LiveRamp.

   :::image type="content" source="media/liveramp-connection.png" alt-text="Panel de configuración para configurar a conexión co servizo LiveRamp AbiliTec.":::

1. Introduza un nome para a conexión e un ID de cliente LiveRamp válido e un segredo.

1. Revise e proporcione o seu consentimento para a [Privacidade e cumprimento de datos](#data-privacy-and-compliance) seleccionando **Estou de acordo**.

1. Seleccione **Verificar** para validar a configuración e, a continuación, seleccione **Gardar**.

### <a name="data-privacy-and-compliance"></a>Cumprimento e privacidade dos datos

Cando habilitas Dynamics 365 Customer Insights para transmitir datos a LiveRamp, permite a transferencia de datos fóra dos límites de conformidade Dynamics 365 Customer Insights, incluíndo datos potencialmente sensibles, como os datos persoais. Microsoft transferirá eses datos segundo as súas instrucións, pero vostede é responsable de asegurarse de que LiveRamp cumpra as obrigas de privacidade ou seguridade que poida ter. Para obter máis información, revise o [Declaración de privacidade de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732). O administrador de Dynamics 365 Customer Insights pode eliminar este enriquecemento en calquera momento para interromper o uso desta funcionalidade.

## <a name="configure-the-enrichment"></a>Configurar o enriquecemento

1. Vaia a **Datos** > **Enriquecemento** e seleccione o separador **Descubrir**.

1. Seleccione **Enriquece os meus datos** no **Identidade** do mosaico LiveRamp.

   :::image type="content" source="media/liveramp-tile.png" alt-text="Mosaico de identidade na páxina de descrición xeral do enriquecemento.":::

1. Revisa a vista xeral e, a continuación, selecciona **A continuación**.

1. Seleccione a conexión. Póñase en contacto cun administrador se non hai conexión dispoñible.

1. Seleccione **Seguinte**.

1. Seleccione o **Conxunto de datos do cliente** e escolle o perfil ou segmento que queres enriquecer cos datos de identidade de LiveRamp. O *Cliente* a entidade enriquece todos os seus perfís de clientes mentres que un segmento enriquece só os perfís de clientes contidos nese segmento.

1. Define que tipo de campos dos teus perfís unificados queres usar para facer coincidir os datos de identidade de LiveRamp. Polo menos un dos campos **Nome e enderezo**, **electrónico**, ou **Teléfono** é requerido. Para unha maior precisión de coincidencia, engade outros campos. Seleccione **Seguinte**.

1. Asigne os seus campos aos datos de identificación de LiveRamp.

   :::image type="content" source="media/liveramp-data-mapping.png" alt-text="Opcións de asignación de datos para o enriquecemento LiveRamp.":::

1. Seleccione **Seguinte** para concluír a asignación do campo.

1. Proporcionar a **Nome** para o enriquecemento e o **Nome da entidade de saída**.

1. Seleccione **Gardar enriquecemento** despois de revisar as súas opcións.

1. Seleccione **Corre** para iniciar o proceso de enriquecemento ou pechar para volver ao **Enriquecementos** páxina.

## <a name="view-enrichment-results"></a>Ver resultados de enriquecemento

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

O **Número de clientes enriquecidos por campo** proporciona un detalle da cobertura de cada campo enriquecido.

## <a name="next-steps"></a>Pasos seguintes

Crear sobre os seus datos enriquecidos de clientes. Use os ID de AbiliTec para consolidar os perfís dos clientes nunha vista baseada na persoa.
[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
