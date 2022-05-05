---
title: Enriquecemento dos perfís de empresas con Dun & Bradstreet
description: Información xeral sobre o enriquecemento de terceiros de Dun & Bradstreet.
ms.date: 04/26/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: ecbbf2c94020bf395f4eb70a99a63cea335af2dd
ms.sourcegitcommit: cf74b8c20d88eb96e1ac86e18cd44fe27aad5ab9
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 04/28/2022
ms.locfileid: "8653781"
---
# <a name="enrichment-of-company-profiles-with-dun--bradstreet-preview"></a>Enriquecemento dos perfís da empresa con Dun & Bradstreet (vista previa)

Dun & Bradstreet ofrece datos comerciais, análises e información para empresas. Permite aos clientes con perfís de clientes unificados para empresas enriquecer os seus datos. Os enriquecementos inclúen atributos como número DUNS, tamaño da empresa, localización, industria e moito máis.

## <a name="prerequisites"></a>Requisitos previos

Para configurar un enriquecemento Dun & Bradstreet, deben cumprirse os seguintes requisitos previos:

- Tes un activo [Dun & Bradstreet](https://www.dnb.com/marketing/media/give-your-data-a-boost.html?source=microsoft_audience_insights) licenza.
- Ten [perfís de clientes unificados](customer-profiles.md) para empresas.
- A Dun & Bradstreet [conexión](connections.md) está configurado por un administrador. Podes crealo se tes [administrador](permissions.md#admin) permisos e as credenciais de Dun & Bradstreet Connect. 

## <a name="setting-up-your-dun--bradstreet-project"></a>Configurando o teu proxecto Dun & Bradstreet

Como usuario con licenza de Dun & Bradstreet, podes configurar un proxecto en [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights). 


1. Iniciar sesión en [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights). Para recuperar as credenciais, [restaura o teu contrasinal](https://sso.dnb.com/signin/forgot-password?lead_source=microsoft_audienceinsights).

1. Descargar [o noso ficheiro de modelo csv](https://c360devenrichment.blob.core.windows.net/mapping/DnBCIdatamapping.csv) que se utilizará para mapear os campos de información sobre a audiencia cos campos correspondentes de Dun & Bradstreet. 

1. Cargue o ficheiro no **Cargar datos** paso da experiencia de creación de proxectos Dun & Bradstreet. 

1. Seleccione os puntos horizontais debaixo dos correspondentes **fonte** no proxecto Dun & Bradstreet recentemente creado para ver as opcións dispoñibles.

   :::image type="content" source="media/enrichment-dnb-dots.png" alt-text="Captura de pantalla de puntos nun proxecto Dun & Bradstreet.":::

1. Escolle **Obter detalles de S3**. Garda esta información nun lugar seguro. Vai necesitalo [establecer a conexión para o enriquecemento](#configure-a-connection-for-dun--bradstreet) nas perspectivas da audiencia. 

   :::image type="content" source="media/enrichment-dnb-s3info.png" alt-text="Captura de pantalla da selección de información s3 nun proxecto Dun & Bradstreet.":::



## <a name="configure-the-enrichment"></a>Configurar o enriquecemento

1. Na información do público, vaia a **Datos** > **Enriquecemento**.

1. Seleccione **Enriquece os meus datos** no mosaico de Dun & Bradstreet e selecciona **Comezar**.

   :::image type="content" source="media/enrichment-dnb-tile.png" alt-text="Captura de pantalla do mosaico de Dun & Bradstreet.":::

1. Seleccione unha [conexión](connections.md) da lista despregable. Póñase en contacto cun administrador se non hai conexión dispoñible. Se es administrador, podes crear unha conexión. Seleccione **Engadir conexión** e escolle **Dun & Bradstreet**. 

1. Seleccione **Conéctate a Dun & Bradstreet** para confirmar a conexión.

1. Seleccione **A continuación** e escolle o **Conxunto de datos do cliente** queres enriquecer cos datos da empresa de Dun & Bradstreet. Podes seleccionar o **Cliente** entidade para enriquecer todos os seus perfís de clientes ou seleccione unha entidade de segmento para enriquecer só os perfís de clientes unificados contidos nese segmento.

1. Seleccione **A continuación** e define que campos dos teus perfís unificados se usan para buscar datos coincidentes da empresa de Dun & Bradstreet. Calquera cousa **Número DUNS** ou **Nome da empresa** e **País** campos son obrigatorios. O campo do país apoia [códigos de país de dúas ou tres letras](https://www.iso.org/iso-3166-country-codes.html), nome do país en inglés, nome do país na lingua nativa e prefixo de teléfono. Algunhas variantes de países comúns inclúen:

   * EE.UU.: Estados Unidos de América, Estados Unidos, Estados Unidos, América.
   * CA: Canadá.
   * GB: Reino Unido, Reino Unido, Gran Bretaña, GB, Reino Unido de Gran Bretaña e Irlanda do Norte, Reino Unido de Gran Bretaña.
   * AU: Australia, Commonwealth de Australia.
   * FR: Francia, República Francesa.
   * DE: Alemaña, alemán, Deutschland, Allemagne, República Federal de Alemaña, República de Alemaña.

   :::image type="content" source="media/enrichment-dnb-mapping.png" alt-text="Panel de mapas de campos de Dun & Bradstreet.":::

1. Seleccione **Seguinte** para concluír a asignación do campo.

1. Indique un nome para o enriquecemento e seleccione **Gardar enriquecemento** despois de revisar as súas opcións.


## <a name="configure-a-connection-for-dun--bradstreet"></a>Configura unha conexión para Dun & Bradstreet 

Debe ser administrador para configurar as conexións. Seleccione **Engadir conexión** ao configurar un enriquecemento *ou* Ir a **Admin** > **Conexións** e selecciona **Montar** no azulexo de Dun & Bradstreet.

1. Seleccione **Comezar**. 

1. Introduza un nome para a conexión na caixa **Nome de visualización**.

1. Proporcione credenciais válidas de Dun & Bradstreet e detalles do proxecto Dun & Bradstreet *Rexión, ruta do cartafol de soltar e nome do cartafol de soltar*. Ti [obtén esta información](#setting-up-your-dun--bradstreet-project) do proxecto Dun & Bradstreet.

1. Revise e proporcione o seu consentimento para a **Privacidade e cumprimento de datos** seleccionando **Estou de acordo**.

1. Seleccione **Verificar** para validar a configuración.

1. Despois de completar a verificación, seleccione **Gardar**.
   
   :::image type="content" source="media/enrichment-dnb-connection.png" alt-text="Páxina de configuración de conexión Dun & Bradstreet.":::

## <a name="enrichment-results"></a>Resultados de enriquecemento

Despois de actualizar o enriquecemento, pode revisar os datos da empresa enriquecidos recentemente en [Os meus enriquecementos](enrichment-hub.md). Pode atopar a hora da última actualización e o número de perfís enriquecidos.

Pode acceder a unha vista detallada de cada perfil enriquecido seleccionando **Ver datos enriquecidos**.

## <a name="next-steps"></a>Pasos seguintes

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Cumprimento e privacidade dos datos

Cando habilitas Dynamics 365 Customer Insights para transmitir datos a Dun & Bradstreet, permite a transferencia de datos fóra dos límites de conformidade Dynamics 365 Customer Insights, incluíndo datos potencialmente sensibles, como os datos persoais. Microsoft transferirá eses datos segundo as súas instrucións, pero vostede é responsable de asegurarse de que Dun & Bradstreet cumpra as obrigas de privacidade ou seguridade que poida ter. Para obter máis información, consulte a [Declaración de privacidade de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
O administrador de Dynamics 365 Customer Insights pode eliminar este enriquecemento en calquera momento para interromper o uso desta funcionalidade.


[!INCLUDE[footer-include](includes/footer-banner.md)]
