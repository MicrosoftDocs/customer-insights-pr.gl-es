---
title: Enriquecer os perfís de clientes con datos de localización de Azure Maps
description: Información xeral sobre o enriquecemento propio de Azure Maps.
ms.date: 08/31/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: cb1c0778a398ef6d338ce6cf9e199eae0c344a5c
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 02/16/2022
ms.locfileid: "8226447"
---
# <a name="enrichment-of-customer-profiles-with-azure-maps-preview"></a>Enriquecemento de perfís de clientes con Azure Maps (vista previa)

Azure Maps ofrece datos e servizos centrados na localización para ofrecer experiencias baseadas en datos xeoespaciais con intelixencia de localización integrada. Os servizos de enriquecemento de datos de Azure Maps melloran a precisión da información de localización dos seus clientes. Trae capacidades como a normalización de enderezos e a extracción de latitude e lonxitude a Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Requisitos previos

Para configurar o enriquecemento de datos de Azure Maps, deben cumprirse os seguintes requisitos previos:

- Debe ter unha subscrición activa de Azure Maps. Para obter unha subscrición, pode [rexistrarse ou obter unha proba gratuíta](https://azure.microsoft.com/services/azure-maps/).

- Hai unha [conexión](connections.md) a Azure Maps dispoñible *ou* ten permisos de [administrador](permissions.md#administrator) e unha clave de API de Azure Maps activa.

## <a name="configure-the-enrichment"></a>Configurar o enriquecemento

1. Vaia a **Datos** > **Enriquecemento**. 

1. No mosaico **Localización**, seleccione **Enriquecer os meus datos**.

   :::image type="content" source="media/azure-maps-tile.png" alt-text="Mosaico de Azure Maps.":::

1. Seleccione unha [conexión](connections.md) da lista despregable. Póñase en contacto cun administrador se non hai conexión de Azure Maps dispoñible. Se é administrador, pode [configurar a conexión para Azure Maps](#configure-the-connection-for-azure-maps). 

1. Seleccione **Seguinte** para confirmar a selección.

1. Escolla o **Conxunto de datos do cliente** que desexa enriquecer con datos de localización de Azure Maps. Pode seleccionar a entidade **Cliente** para enriquecer todos os perfís de clientes unificados ou seleccionar unha entidade de segmento para enriquecer só os perfís de clientes contidos nese segmento.

    :::image type="content" source="media/enrichment-azure-maps-configuration-customer-data-set.png" alt-text="Captura de pantalla ao escoller o conxunto de datos do cliente.":::

1. Escolla se desexa asignar campos ao enderezo principal e/ou secundario. Pode especificar unha asignación de campo para os dous enderezos e enriquecer os perfís dos dous enderezos por separado&mdash;por exemplo, para un enderezo particular e un enderezo de empresa. Seleccione **Seguinte**.

1. Defina que campos dos seus perfís unificados se deben empregar para buscar datos de localización coincidentes de Azure Maps. Os campos **Rúa 1** e **Código postal** son obrigatorios para o enderezo primario ou secundario seleccionado. Para unha maior precisión da coincidencia, pode engadir máis campos.

   :::image type="content" source="media/enrichment-azure-maps-configuration.png" alt-text="Páxina de configuración de enriquecemento de Azure Maps.":::

1. Seleccione **Seguinte** para concluír a asignación do campo.

1. Avalíe se quere modificar **Configuración avanzada**. Ofrécense para dar a máxima flexibilidade para manexar casos de uso avanzados, pero os valores predeterminados serán adecuados na maioría dos casos:
   - **Tipo de enderezos**: o comportamento predeterminado é que o enriquecemento devolverá a mellor coincidencia de enderezos aínda que estea incompleta. Para obter só enderezos completos&mdash;por exemplo, enderezos que inclúen o número da casa&mdash;desmarque todas as caixas de verificación excepto **Enderezos puntuais**. 
   - **Idioma**: por defecto, os enderezos devólvense no idioma da rexión á que se determinou que pertence o enderezo. Para aplicar un idioma de enderezo normalizado, seleccione o idioma no menú despregable. Por exemplo, seleccionando **Inglés** devolverase **Copenhague, Dinamarca** en vez de **København, Danmark**.

1. Proporcione un nome para o enriquecemento.

1. Revise as túas opcións e seleccione **Aforrar enriquecemento**.

## <a name="configure-the-connection-for-azure-maps"></a>Configurar a conexión para Azure Maps

Para configurar as conexións, debe ser administrador de información sobre o público. Seleccione **Engadir conexión** ao configurar un enriquecemento ou vaia a **Administrar** > **Conexións** e seleccione **Configurar** no mosaico de Azure Maps.

1. Na caixa **Nome de pantalla**, introduza un nome para a conexión.

1. Proporcione unha clave de API de Azure Maps válida.

1. Revise e proporcione o seu consentimento para a **Privacidade de datos e cumprimento** seleccionando a caixa de verificación **Estou de acordo**

1. Seleccione **Verificar** para validar a configuración.

1. Despois de completar a verificación, seleccione **Gardar**.

:::image type="content" source="media/enrichment-azure-maps-connection.png" alt-text="Páxina de configuración de conexión de Azure Maps.":::

## <a name="enrichment-results"></a>Resultados de enriquecemento

Para iniciar o proceso de enriquecemento, seleccione **Executar** na barra de comandos. Tamén pode deixar que o sistema execute o enriquecemento automaticamente como parte dunha [actualización programada](system.md#schedule-tab). O tempo de procesamento dependerá do tamaño dos datos do cliente e dos tempos de resposta da API.

Despois de completar o proceso de enriquecemento, pode consultar os datos dos perfís de clientes recentemente enriquecidos en **Os meus enriquecementos**. Ademais, atopará a hora da última actualización e o número de perfís enriquecidos.

Pode acceder a unha vista detallada de cada perfil enriquecido seleccionando **Ver datos enriquecidos**.

## <a name="next-steps"></a>Pasos seguintes

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Cumprimento e privacidade dos datos

Cando permite a Dynamics 365 Customer Insights transmitir datos a Azure Maps, permite a transferencia de datos fóra do límite de cumprimento de Dynamics 365 Customer Insights, incluíndo datos potencialmente confidenciais como os datos persoais. Microsoft transferirá estes datos segundo a súa instrución, pero vostede é responsable de asegurarse de que Azure Maps cumpre coas obrigacións de privacidade ou seguridade que poida ter. Para obter máis información, vaia a [Declaración de privacidade de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
O administrador de Dynamics 365 Customer Insights pode eliminar este enriquecemento en calquera momento para interromper o uso desta funcionalidade.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
