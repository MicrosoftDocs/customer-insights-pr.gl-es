---
title: Enriquecer os perfís de clientes con datos de Microsoft
description: Use os datos propietarios de Microsoft para enriquecer os datos dos seus clientes con afinidades e compartición de voz.
ms.date: 11/11/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 346c79d0a4d5cd5c47e91c195a48d3a153db0dc0
ms.sourcegitcommit: 9d3c9e4eb2ce20996a4f4fb44c42e3fe020c5b48
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 11/11/2021
ms.locfileid: "7793702"
---
# <a name="enrich-customer-profiles-with-affinities-and-share-of-voice-preview"></a>Enriquece os perfís de clientes con afinidades e compartición de voz (vista previa)

Use os datos propietarios de Microsoft para enriquecer os datos dos seus clientes con afinidades de marca, afinidades de interese e compartición de voz (SoV). Estas afinidades e SoV baséanse en datos de persoas con datos demográficos similares aos dos teus clientes. Esta información axúdache a comprender e segmentar mellor os teus clientes en función das súas afinidades ou SoV con marcas e intereses específicos.

Para obter información do público, vaia a **Datos** > **Enriquecemento** para [configurar e ver enriquecementos](enrichment-hub.md).

Para configurar afinidades de marca e enriquecemento de SoV, vai a **Descubrir** ficha e seleccione **Enriquece os meus datos** no **Marcas** tella.

Para configurar afinidades de intereses e enriquecemento de SoV, vai a **Descubrir** ficha e seleccione **Enriquece os meus datos** no **Intereses** tella.

   > [!div class="mx-imgBorder"]
   > ![Mosaicos de marcas e intereses.](media/BrandsInterest-tile-Hub.png "Mosaicos de marcas e intereses")

## <a name="how-we-determine-affinities-and-sov"></a>Como determinamos afinidades e SoV

Usamos os datos de busca en liña de Microsoft para atopar afinidades e SoV para marcas e intereses en varios segmentos demográficos (definidos por idade, sexo ou localización). O volume de busca en liña dunha marca ou interese constitúe a base para determinar a afinidade ou SoV. Non obstante, cada un ofrece unha perspectiva diferente para comprender os seus clientes.

- A afinidade é unha comparativa entre segmentos demográficos. Podes utilizar esta información para identificar os segmentos demográficos que teñen a maior afinidade por unha determinada marca ou interese, en comparación con outros segmentos.

- A participación de voz é unha comparativa entre as túas marcas ou intereses seleccionados. Podes utilizar esta información para identificar que marca ou interese ten a maior cota de voz para un determinado segmento demográfico, en comparación con outras marcas ou intereses que seleccionaches.

## <a name="affinity-level-and-score"></a>Nivel e puntuación de afinidade

En cada perfil de cliente enriquecido, fornecemos dous valores relacionados: o nivel de afinidade e a puntuación de afinidade. Estes valores axúdanlle a determinar o forte que é a afinidade do segmento demográfico dese perfil, por unha marca ou interese, en comparación con outros segmentos demográficos.

O *nivel de afinidade* consta de catro niveis e a *puntuación de afinidade* calcúlase nunha escala de 100 puntos que se asigna aos niveis de afinidade.


|Nivel de afinidade |Puntuación de afinidade  |
|---------|---------|
|Moi alto     | 85-100       |
|Alto     | 70-84        |
|Mediana     | 35-69        |
|Baixo     | 1-34        |

Dependendo da granularidade que desexe para medir a afinidade, pode usar o nivel de afinidade ou a puntuación. A puntuación de afinidade ofrécelle un control máis preciso.

## <a name="share-of-voice-sov"></a>Compartir de voz (SoV)

Calculamos SoV nunha escala de 100 puntos. O SoV total de todas as marcas ou intereses para cada perfil de cliente enriquecido suma 100. A diferenza das afinidades, SoV é relativo ás marcas e intereses que seleccionas. Por exemplo, os valores de SoV para 'Microsoft' poden ser diferentes se as marcas seleccionadas son ('Microsoft', 'GitHub') fronte a ('Microsoft', 'LinkedIn').

## <a name="supported-countriesregions"></a>Países ou rexións compatibles

Actualmente son compatibles as seguintes opcións de país ou rexión: Australia, Canadá (inglés), Francia, Alemaña, Reino Unido ou Estados Unidos (inglés).

Para seleccionar un país ou rexión, abra **Enriquecemento de marcas** ou **Enriquecemento de intereses** e seleccione **Cambiar** preto de **País/Rexión**. No panel **Configuración do país/rexión**, escolla unha opción e seleccione **Solicitar**.

### <a name="implications-related-to-country-selection"></a>Implicacións relacionadas coa selección do país

- Cando [escolla as súas propias marcas](#define-your-brands-or-interests), o sistema ofrece suxestións en función do país ou rexión seleccionado.

- Cando [escolla unha industria](#define-your-brands-or-interests), obterá as marcas ou intereses máis relevantes en función do país ou rexión seleccionado.

- Ao [enriquecer perfís](#refresh-enrichment), enriqueceremos todos os perfís de clientes dos que obteñamos datos das marcas e intereses seleccionados, incluídos os perfís que non están no país ou rexión seleccionados. Por exemplo, se seleccionou Alemaña, enriqueceremos os perfís situados nos Estados Unidos se temos datos dispoñibles para as marcas e os intereses seleccionados nos Estados Unidos.

## <a name="configure-enrichment"></a>Configurar o enriquecemento

Unha experiencia guiada axúdalle a configurar os enriquecementos. 

### <a name="define-your-brands-or-interests"></a>Definir as marcas ou os intereses

Escolla ata cinco marcas ou intereses usando unha ou as dúas opcións seguintes:

- **Industria**: Seleccione a súa industria na lista despregable e logo escolla entre as mellores marcas ou intereses desa industria.
- **Escoller os seus propios**: insira unha marca ou interese que sexa relevante para a súa organización e logo escolla entre as suxestións coincidentes. Se non enumeramos unha marca ou interese que está a buscar, envíenos comentarios usando a ligazón **Suxerir**.

### <a name="review-enrichment-preferences"></a>Revisar preferencias de enriquecemento

Revise as súas preferencias de enriquecemento predeterminadas e actualíceas segundo sexa necesario.

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Captura de pantalla da xanela de preferencias de enriquecemento.":::

### <a name="select-entity-to-enrich"></a>Seleccionar entidade para enriquecer

Seleccione **Entidade enriquecida** e escolla o conxunto de datos que quere enriquecer con datos de Microsoft. Pode seleccionar a entidade Cliente para enriquecer todos os seus perfís de clientes ou seleccione unha entidade de segmento para enriquecer só os perfís de clientes contidos nese segmento.

### <a name="map-your-fields"></a>Asignar os campos

Asigne campos da súa entidade cliente unificada para definir o segmento demográfico que desexa que use o sistema para enriquecer os datos dos seus clientes. Asigne o País/Rexión e polo menos os atributos Data de nacemento ou Sexo. Ademais, debe asignar polo menos un código de cidade (e estado/provincia) ou codigo postal. Seleccione **Editar** definir a asignación dos campos e seleccionar **Aplicar** cando remate. Seleccione **Gardar** para completar a asignación de campos.

Admítense os seguintes formatos e valores (os valores non diferencian entre maiúsculas e minúsculas):

- **Data de nacemento**: Recomendamos que a data de nacemento sexa convertida ao tipo DateTime durante a inxestión de datos. Alternativamente, pode ser unha cadea en [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) formato "aaaa-MM-dd" ou "aaaa-MM-ddTHH:mm:ss".
- **Sexo**: Masculino, Feminino, Descoñecido.
- **Código postal**: Códigos postales de cinco díxitos para Estados Unidos, código postal estándar en calquera outro lugar.
- **Cidade**: Nome da cidade en inglés.
- **Estado/Provincia**: Abreviatura de dúas letras para Estados Unidos e Canadá. Abreviación de dúas ou tres letras para Australia. Non se aplica a Francia, Alemaña ou Reino Unido.
- **País/Rexión**:

  - EUA: Estados Unidos de América, Estados Unidos, EE. UU., EUA, EU
  - CA: Canadá, CA
  - RU: Reino Unido, RU, Gran Bretaña, GB, Reino Unido de Gran Bretaña e Irlanda do Norte, Reino Unido de Gran Bretaña
  - AU: Australia, AU, Mancomunidade de Australia
  - FR: Francia, FR, República Francesa
  - DE: Alemaña, Alemán, Deutschland, Allemagne, DE, República Federal de Alemaña, República de Alemaña

## <a name="review-and-name-the-enrichment"></a>Revisar e nomear o enriquecemento

Finalmente, pode revisar a información e proporcionar un nome para o enriquecemento.

:::image type="content" source="media/enrichment-interests-summary.png" alt-text="Revisión de intereses e nome de páxina.":::

## <a name="refresh-enrichment"></a>Actualizar o enriquecemento

Execute o enriquecemento despois de configurar marcas, intereses e asignación de campos para os datos demográficos. Para iniciar o proceso, seleccione **Executar** na páxina de configuración da marca ou o interese. Ademais, pode deixar que o sistema execute o enriquecemento automaticamente como parte dunha actualización programada.

Dependendo do tamaño dos datos dos seus clientes, a execución do enriquecemento pode levar uns minutos.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="enrichment-results"></a>Resultados de enriquecemento

Despois de executar o proceso de enriquecemento, vaia a **Os meus enriquecementos** para revisar o número total de clientes enriquecidos e unha subdivisión de marcas ou intereses nos perfís de clientes enriquecidos.

:::image type="content" source="media/my-enrichments.png" alt-text="Versión preliminar dos resultados despois de executar o proceso de enriquecemento.":::

Atoparás un gráfico co número de perfís de clientes enriquecidos ao longo do tempo e vistas previas das entidades enriquecidas. Revisa os datos enriquecidos seleccionando **Ver máis** no **Nivel de afinidade** ou **Compartir de voz** gráficos. Os datos enriquecidos das marcas van para o **BrandAffinityFromMicrosoft** e **BrandShareOfVoiceFromMicrosoft** entidades. Os datos dos intereses están no **InterestAffinityFromMicrosoft** e **InterestShareOfVoiceFromMicrosoft** entidades. Tamén atopará estas entidades enumeradas no grupo **Enriquecemento** en **Datos** > **Entidades**.

## <a name="see-enrichment-data-on-the-customer-card"></a>Vexa datos de enriquecemento na tarxeta de cliente

O SoV de marca e interese tamén se pode ver nas tarxetas de clientes individuais. Vaia a **Clientes** e seleccione un perfil de cliente. Na tarxeta do cliente, atoparás gráficos para a marca ou o SoV de interese baseados nas persoas do perfil demográfico dese cliente.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Cartón de cliente con datos enriquecidos.":::

## <a name="next-steps"></a>Pasos seguintes

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]


[!INCLUDE[footer-include](../includes/footer-banner.md)]
