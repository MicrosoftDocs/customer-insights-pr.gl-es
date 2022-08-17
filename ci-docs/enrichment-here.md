---
title: Enriquece os perfís de clientes con HERE Technologies (vista previa)
description: Información xeral sobre o enriquecemento de terceiros de HERE Technologies.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 86a070342193dd7afda38823d90f4bd28c8b862e
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 08/08/2022
ms.locfileid: "9237856"
---
# <a name="enrich-customer-profiles-with-here-technologies-preview"></a>Enriquece os perfís de clientes con HERE Technologies (vista previa)

HERE Technologies é unha empresa de plataformas de localización que ofrece servizos e datos centrados na situación. Os servizos de enriquecemento de datos de HERE Technologies melloran a precisión da información de localización dos teus clientes. Ofrece normalización de enderezos, extracción de latitude e lonxitude e moito máis.

## <a name="prerequisites"></a>Requisitos previos

- Unha subscrición activa a HERE Technologies. Para obter unha subscrición, [rexístrate aquí](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) ou [contacte AQUÍ Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directamente. [Obteña máis información sobre o enriquecemento de localización de HERE Technologies.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- A AQUÍ [conexión](connections.md) é [configurado](#configure-the-connection-for-here-technologies) por un administrador.

## <a name="configure-the-connection-for-here-technologies"></a>Configurar a conexión para HERE Technologies

Debes ser un [administrador](permissions.md#admin) en Customer Insights e ten unha clave activa HERE Technologies API.

1. Seleccione **Engadir conexión** ao configurar un enriquecemento ou vaia a **Admin** > **Conexións** e selecciona **Montar** no mosaico HERE Technologies.

1. Introduza un nome para a conexión e unha clave válida da API de HERE Technologies.

1. Revisa o [privacidade e cumprimento dos datos](connections.md#data-privacy-and-compliance) e selecciona **Estou de acordo**.

1. Seleccione **Verificar** para validar a configuración e, a continuación, seleccione **Gardar**.

   :::image type="content" source="media/enrichment-HERE-connection.png" alt-text="Páxina de configuración da conexión de HERE Technologies.":::

## <a name="configure-the-enrichment"></a>Configurar o enriquecemento

1. Vaia a **Datos** > **Enriquecemento** e seleccione o separador **Descubrir**.

1. Seleccione **Enriquece os meus datos** no **Localización** da tella de AQUÍ Technologies.

   :::image type="content" source="media/HERE-tile.png" alt-text="Mosaico de HERE Technologies.":::

1. Revisa a vista xeral e, a continuación, selecciona **A continuación**.

1. Seleccione a conexión. Póñase en contacto cun administrador se non hai conexión dispoñible.

1. Seleccione **Seguinte**.

1. Seleccione o **Conxunto de datos do cliente** e escolle o perfil ou segmento que queres enriquecer con datos de HERE Technologies. O *Cliente* a entidade enriquece todos os seus perfís de clientes mentres que un segmento enriquece só os perfís de clientes contidos nese segmento.

1. Define que tipo de campos dos teus perfís unificados usar para a correspondencia: o enderezo principal e/ou secundario. Pode especificar unha asignación de campos para ambos os enderezos e enriquecer os perfís de ambos os enderezos por separado. Por exemplo, para un enderezo de casa e un enderezo de empresa. Seleccione **Seguinte**.

1. Asigne os seus campos aos datos de HERE Technologies. Os campos **Rúa 1** e **Código postal** son obrigatorios para o enderezo primario e/ou secundario seleccionado. Para unha maior precisión de coincidencia, engade máis campos.

1. Seleccione **Seguinte** para concluír a asignación do campo.

1. Proporcionar a **Nome** para o enriquecemento e o **Nome da entidade de saída**.

1. Seleccione **Gardar enriquecemento** despois de revisar as súas opcións.

1. Seleccione **Corre** para iniciar o proceso de enriquecemento ou pechar para volver ao **Enriquecementos** páxina.

## <a name="view-enrichment-results"></a>Ver resultados de enriquecemento

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

O **Número de clientes enriquecidos por campo** proporciona un detalle da cobertura de cada campo enriquecido.

## <a name="next-steps"></a>Pasos seguintes

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
