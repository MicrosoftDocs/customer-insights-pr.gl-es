---
title: Enriquecer os perfís de clientes con datos de localización de Azure Maps
description: Información xeral sobre o enriquecemento propio de Azure Maps.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: a806b2d0c791972c967c90694527608b4def9f3f
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 06/13/2022
ms.locfileid: "8953626"
---
# <a name="enrichment-of-customer-profiles-with-azure-maps-preview"></a>Enriquecemento de perfís de clientes con Azure Maps (vista previa)

Azure Maps ofrece datos e servizos centrados na localización para ofrecer experiencias baseadas en datos xeoespaciais con intelixencia de localización integrada. Os servizos de enriquecemento de datos de Azure Maps melloran a precisión da información de localización dos seus clientes. Trae capacidades como a normalización de enderezos e a extracción de latitude e lonxitude a Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Requisitos previos

- Unha subscrición activa a Azure Maps. Para obter unha subscrición, [rexístrate ou obtén unha proba gratuíta](https://azure.microsoft.com/services/azure-maps/).

- Un Azure Maps [conexión](connections.md) é [configurado](#configure-the-connection-for-azure-maps) por un administrador.

## <a name="configure-the-connection-for-azure-maps"></a>Configurar a conexión para Azure Maps

Debes ser un [administrador](permissions.md#admin) en Customer Insights e ten unha clave de API de Azure Maps activa.

1. Seleccione **Engadir conexión** ao configurar un enriquecemento ou vaia a **Administrar** > **Conexións** e seleccione **Configurar** no mosaico de Azure Maps.

   :::image type="content" source="media/enrichment-azure-maps-connection.png" alt-text="Páxina de configuración de conexión de Azure Maps.":::

1. Introduza un nome para a conexión e unha clave de API de Azure Maps válida.

1. Revise e proporcione o seu consentimento para a [Privacidade e cumprimento de datos](#data-privacy-and-compliance) seleccionando **Estou de acordo**.

1. Seleccione **Verificar** para validar a configuración e, a continuación, seleccione **Gardar**.

### <a name="data-privacy-and-compliance"></a>Cumprimento e privacidade dos datos

Cando permite a Dynamics 365 Customer Insights transmitir datos a Azure Maps, permite a transferencia de datos fóra do límite de cumprimento de Dynamics 365 Customer Insights, incluíndo datos potencialmente confidenciais como os datos persoais. Microsoft transferirá eses datos segundo as túas instrucións, pero ti es responsable de garantir que Azure Maps cumpra as obrigas de privacidade ou seguridade que poidas ter. Para obter máis información, vaia a [Declaración de privacidade de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
O administrador de Dynamics 365 Customer Insights pode eliminar este enriquecemento en calquera momento para interromper o uso desta funcionalidade.

## <a name="configure-the-enrichment"></a>Configurar o enriquecemento

1. Vaia a **Datos** > **Enriquecemento** e seleccione o separador **Descubrir**.

1. Seleccione **Enriquece os meus datos** no **Localización** dende Microsoft Azure Mosaico de mapas.

   :::image type="content" source="media/azure-maps-tile.png" alt-text="Mosaico de Azure Maps.":::

1. Revisa a vista xeral e, a continuación, selecciona **A continuación**.

1. Seleccione a conexión. Póñase en contacto cun administrador se non hai conexión dispoñible.

1. Seleccione **Seguinte**.

1. Seleccione o **Conxunto de datos do cliente** e escolle o perfil ou segmento que queres enriquecer con datos de Microsoft. O *Cliente* a entidade enriquece todos os seus perfís de clientes mentres que un segmento enriquece só os perfís de clientes contidos nese segmento.

1. Define que tipo de campos dos teus perfís unificados queres usar para a correspondencia: o enderezo principal e/ou secundario. Pode especificar unha asignación de campos para ambos os enderezos e enriquecer os perfís de ambos os enderezos por separado. Por exemplo, para un enderezo de casa e un enderezo de empresa. Seleccione **Seguinte**.

1. Asigne os seus campos aos datos de localización de Azure Maps. Os campos **Rúa 1** e **Código postal** son obrigatorios para o enderezo primario e/ou secundario seleccionado. Para unha maior precisión de coincidencia, engade máis campos.

   :::image type="content" source="media/enrichment-azure-maps-attributes.png" alt-text="Mapeo de atributos de Azure Maps.":::

1. Seleccione **Seguinte** para concluír a asignación do campo.

1. Revisión **Configuración avanzada** que ofrecen a máxima flexibilidade para manexar casos de uso avanzados. Non obstante, normalmente non é necesario cambiar os seguintes valores predeterminados.

   - **Tipo de enderezos** : devolve a mellor coincidencia de enderezos aínda que estea incompleta. Para obter só enderezos completos&mdash;por exemplo, enderezos que inclúen o número da casa&mdash;desmarque todas as caixas de verificación excepto **Enderezos puntuais**.
   - **Lingua** : os enderezos volven no idioma en función da rexión do enderezo. Para aplicar un idioma de enderezo normalizado, seleccione o idioma no menú despregable. Por exemplo, seleccionando **inglés** volve **Copenhague, Dinamarca** en vez de **Copenhague, Dinamarca**.
   - **Número máximo de resultados** : Número de resultados por enderezo.

1. Seleccione **Seguinte**.

1. Proporcionar a **Nome** para o enriquecemento e o **Nome da entidade de saída**.

1. Seleccione **Gardar enriquecemento** despois de revisar as súas opcións.

1. Seleccione **Corre** para iniciar o proceso de enriquecemento ou pechar para volver ao **Enriquecementos** páxina.

## <a name="enrichment-results"></a>Resultados de enriquecemento

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

O **Número de clientes enriquecidos por campo** proporciona un detalle da cobertura de cada campo enriquecido.

## <a name="next-steps"></a>Pasos seguintes

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
