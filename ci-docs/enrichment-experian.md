---
title: Enriqueza os perfís de clientes con datos demográficos de Experian (versión preliminar)
description: Información xeral sobre o enriquecemento de terceiros Experian.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: a30e98b06ed07590ab95cae1d8db8023e49ff7f9
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "9053019"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Enriqueza os perfís de clientes con datos demográficos de Experian (versión preliminar)

Experian é líder mundial en servizos de mercadotecnia e informes de crédito ao consumidor e ás empresas. Cos servizos de enriquecemento de datos de Experian, pode construír unha comprensión máis profunda dos seus clientes enriquecendo os perfís dos seus clientes con datos demográficos como tamaño do fogar, ingresos e moito máis.

## <a name="supported-countriesregions"></a>Países ou rexións compatibles

Actualmente admítese enriquecer perfís de clientes só nos Estados Unidos.

## <a name="prerequisites"></a>Requisitos previos

- Un activo Experian subscrición. Para obter unha subscrición, [contacte con Experian](https://www.experian.com/marketing-services/contact) directamente. [Obteña máis información acerca do enriquecementos de datos de Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).

- An Experian [conexión](connections.md) é [configurado](#configure-the-connection-for-experian) por un administrador.

- Experian ID de usuario, ID de partido e número de modelo para a túa conta de transporte seguro (ST) habilitado para SSH Experian creado para ti.

## <a name="configure-the-connection-for-experian"></a>Configurar a conexión de Experian

Debes ser un [administrador](permissions.md#admin) en Customer Insights e ten un Experian ID de usuario, ID do partido e número de modelo.

1. Seleccione **Engadir conexión** ao configurar un enriquecemento ou vaia a **Admin** > **Conexións** e selecciona **Montar** no Experian tella.

   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Experian panel de configuración da conexión.":::

1. Introduza un nome para a conexión e un ID de usuario, ID de partido e número de modelo válidos para a túa Experian Conta de transporte seguro.

1. Revise e proporcione o seu consentimento para a [Privacidade e cumprimento de datos](#data-privacy-and-compliance) seleccionando **Estou de acordo**.

1. Seleccione **Verificar** para validar a configuración e, a continuación, seleccione **Gardar**.

### <a name="data-privacy-and-compliance"></a>Cumprimento e privacidade dos datos

Cando permite a Dynamics 365 Customer Insights transmitir datos a Experian, permite a transferencia de datos fóra do límite de cumprimento de Dynamics 365 Customer Insights, incluíndo datos potencialmente confidenciais como os datos persoais. Microsoft transferirá estes datos segundo a súa instrución, pero vostede é responsable de asegurarse de que Experian cumpre coas obrigacións de privacidade ou seguridade que poida ter. Para obter máis información, consulte a [Declaración de privacidade de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732). O administrador de Dynamics 365 Customer Insights pode eliminar este enriquecemento en calquera momento para interromper o uso desta funcionalidade.

## <a name="configure-the-enrichment"></a>Configurar o enriquecemento

1. Vaia a **Datos** > **Enriquecemento** e seleccione o separador **Descubrir**.

1. Seleccione **Enriquece os meus datos** no **Demografía** dende Experian tella.

   :::image type="content" source="media/experian-tile.png" alt-text="Experian mosaico na páxina de resumo do enriquecemento.":::

1. Revisa a vista xeral e, a continuación, selecciona **A continuación**.

1. Seleccione a conexión. Póñase en contacto cun administrador se non está dispoñible.

1. Seleccione **Seguinte**.

1. Seleccione o **Conxunto de datos do cliente** e escolle o perfil ou segmento do que queres enriquecer con datos demográficos Experian. O *Cliente* a entidade enriquece todos os seus perfís de clientes mentres que un segmento enriquece só os perfís de clientes contidos nese segmento.

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Captura de pantalla ao escoller o conxunto de datos do cliente.":::

1. Define que tipo de campos dos teus perfís unificados queres usar para facer coincidir os datos demográficos Experian. Polo menos un dos campos **Nome e enderezo**, **Teléfono** ou **Correo electrónico** é requerido. Para unha maior precisión de coincidencia, engade outros campos. Seleccione **Seguinte**.

1. Asigne os seus campos aos datos demográficos de Experian.

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
