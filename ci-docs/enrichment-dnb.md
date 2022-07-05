---
title: Enriquece os perfís da empresa con Dun & Bradstreet (versión previa)
description: Información xeral sobre o enriquecemento de terceiros de Dun & Bradstreet.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 51f2e4e46aa25d10502d0feb5ea42eb7d2d637b9
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082552"
---
# <a name="enrich-company-profiles-with-dun--bradstreet-preview"></a>Enriquece os perfís da empresa con Dun & Bradstreet (versión previa)

Dun & Bradstreet ofrece datos comerciais, análises e información para empresas. Permite aos clientes con perfís de clientes unificados para empresas enriquecer os seus datos. Os enriquecementos inclúen atributos como número DUNS, tamaño da empresa, localización, industria e moito máis.

## <a name="prerequisites"></a>Requisitos previos

- Un activo [Dun & Bradstreet](https://www.dnb.com/marketing/media/give-your-data-a-boost.html?source=microsoft_audience_insights) licenza.
- [Perfís de clientes unificados](customer-profiles.md) para empresas.
- A Dun & Bradstreet [proxecto](#set-up-your-dun--bradstreet-project) está configurado.
- A Dun & Bradstreet [conexión](connections.md) é [configurado](#configure-a-connection-for-dun--bradstreet) por un administrador.

## <a name="set-up-your-dun--bradstreet-project"></a>Configura o teu proxecto Dun & Bradstreet

Como usuario con licenza de Dun & Bradstreet, podes configurar un proxecto en [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights).

1. Iniciar sesión en [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights). Para recuperar as credenciais, [restaura o teu contrasinal](https://sso.dnb.com/signin/forgot-password?lead_source=microsoft_audienceinsights).

1. Descargar [o noso ficheiro de modelo csv](https://c360devenrichment.blob.core.windows.net/mapping/DnBCIdatamapping.csv) que se utilizará para mapear os campos de Customer Insights cos campos correspondentes de Dun & Bradstreet.

1. Cargue o ficheiro no **Cargar datos** paso da experiencia de creación de proxectos Dun & Bradstreet.

1. Seleccione os puntos horizontais debaixo dos correspondentes **fonte** no proxecto Dun & Bradstreet recentemente creado para ver as opcións dispoñibles.

   :::image type="content" source="media/enrichment-dnb-dots.png" alt-text="Captura de pantalla de puntos nun proxecto Dun & Bradstreet.":::

1. Escolle **Obter detalles de S3**. Garda esta información nun lugar seguro. Vai necesitalo [establecer a conexión para o enriquecemento](#configure-a-connection-for-dun--bradstreet) en Customer Insights.

   :::image type="content" source="media/enrichment-dnb-s3info.png" alt-text="Captura de pantalla da selección de información s3 nun proxecto Dun & Bradstreet.":::

## <a name="configure-a-connection-for-dun--bradstreet"></a>Configura unha conexión para Dun & Bradstreet

Debes ser un [administrador](permissions.md#admin) en Customer Insights e ten as credenciais de Dun & Bradstreet Connect.

1. Seleccione **Engadir conexión** ao configurar un enriquecemento ou ir a **Admin** > **Conexións** e selecciona **Montar** no azulexo de Dun & Bradstreet.

1. Introduza un nome para a conexión.

1. Proporcione credenciais válidas de Dun & Bradstreet e detalles do proxecto Dun & Bradstreet *Rexión, ruta do cartafol de soltar e nome do cartafol de soltar*. Ti [obtén esta información](#set-up-your-dun--bradstreet-project) do proxecto Dun & Bradstreet.

1. Revise e proporcione o seu consentimento para a [Privacidade e cumprimento de datos](#data-privacy-and-compliance) seleccionando **Estou de acordo**.

1. Seleccione **Verificar** para validar a configuración e, a continuación, seleccione **Gardar**.

   :::image type="content" source="media/enrichment-dnb-connection.png" alt-text="Páxina de configuración de conexión Dun & Bradstreet.":::

### <a name="data-privacy-and-compliance"></a>Cumprimento e privacidade dos datos

Cando habilitas Dynamics 365 Customer Insights para transmitir datos a Dun & Bradstreet, permite a transferencia de datos fóra dos límites de conformidade Dynamics 365 Customer Insights, incluíndo datos potencialmente sensibles, como os datos persoais. Microsoft transferirá eses datos segundo as súas instrucións, pero vostede é responsable de asegurarse de que Dun & Bradstreet cumpra as obrigas de privacidade ou seguridade que poida ter. Para obter máis información, consulte a [Declaración de privacidade de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
O administrador de Dynamics 365 Customer Insights pode eliminar este enriquecemento en calquera momento para interromper o uso desta funcionalidade.

## <a name="supported-countries-or-regions"></a>Países ou rexións admitidos

Actualmente admitimos as seguintes opcións de país/rexión: Canadá (inglés) ou Estados Unidos (inglés).

## <a name="configure-the-enrichment"></a>Configurar o enriquecemento

1. Vaia a **Datos** > **Enriquecemento** e seleccione o separador **Descubrir**.

1. Seleccione **Enriquece os meus datos** no **Datos da empresa** para azulexos Dun & Bradstreet.

   :::image type="content" source="media/enrichment-dnb-tile.png" alt-text="Captura de pantalla da tella de Dun & Bradstreet.":::

1. Revisa a vista xeral e, a continuación, selecciona **A continuación**.

1. Seleccione a conexión e confirme. Póñase en contacto cun administrador se non está dispoñible.

1. Seleccione **Seguinte**.

1. Seleccione o **Conxunto de datos do cliente** e escolle o perfil ou segmento que queres enriquecer cos datos da empresa de Dun & Bradstreet. O *Cliente* a entidade enriquece todos os seus perfís de clientes mentres que un segmento enriquece só os perfís de clientes contidos nese segmento.

1. Define que tipo de campos dos teus perfís unificados usar para facer coincidir os datos da empresa de Dun & Bradstreet. Polo menos un dos campos **Nome e enderezo**, **Teléfono** ou **Correo electrónico** é requerido.

1. Seleccionar **Seguinte**

1. Asigne os seus campos aos datos da empresa de Dun & Bradstreet. Calquera cousa **Número DUNS** ou **Nome da empresa** e **País** campos son obrigatorios.

      :::image type="content" source="media/enrichment-dnb-mapping.png" alt-text="Panel de mapas de campos de Dun & Bradstreet.":::

1. Seleccione **Seguinte** para concluír a asignación do campo.

1. Proporcionar a **Nome** para o enriquecemento e o **Nome da entidade de saída**.

1. Seleccione **Gardar enriquecemento** despois de revisar as súas opcións.

1. Seleccione **Corre** para iniciar o proceso de enriquecemento ou pechar para volver ao **Enriquecementos** páxina.

## <a name="view-enrichment-results"></a>Ver resultados de enriquecemento

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

## <a name="next-steps"></a>Pasos seguintes

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](includes/footer-banner.md)]
