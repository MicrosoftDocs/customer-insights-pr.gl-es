---
title: Enriquece os perfís de clientes con marcas e datos de intereses de Microsoft
description: Use os datos propietarios de Microsoft para enriquecer os datos dos seus clientes con afinidades e compartición de voz.
ms.date: 03/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
searchScope:
- ci-enrichments
- ci-enrichment-wizard
- customerInsights
ms.openlocfilehash: 61262980cafdcd130430e200e466ce7da6cc4d07
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 06/13/2022
ms.locfileid: "8953763"
---
# <a name="enrich-customer-profiles-with-affinities-and-share-of-voice-preview"></a>Enriquece os perfís de clientes con afinidades e compartición de voz (vista previa)

Use os datos propietarios de Microsoft para enriquecer os datos dos seus clientes con afinidades de marca, afinidades de interese e compartición de voz (SoV). Estas afinidades e SoV baséanse en datos de persoas con datos demográficos similares aos teus clientes. Esta información axúdache a comprender e segmentar mellor os teus clientes en función das súas afinidades ou SoV con marcas e intereses específicos.

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

## <a name="configure-the-enrichment"></a>Configurar o enriquecemento

1. Vaia a **Datos** > **Enriquecemento** e seleccione o separador **Descubrir**.

   - Para configurar afinidades de marca e enriquecemento de SoV, seleccione **Enriquece os meus datos** no **Marcas** tella.

   - Para configurar afinidades de interese e enriquecemento SoV, seleccione **Enriquece os meus datos** no **Intereses** tella.

   > [!div class="mx-imgBorder"]
   > ![Mosaicos de marcas e intereses.](media/BrandsInterest-tile-Hub.png "Mosaicos de marcas e intereses")

1. Revisa a vista xeral e, a continuación, selecciona **A continuación**.

1. Para cambiar o seu país ou rexión, seleccione **Cambio** preto de **País/Rexión**. No **Configuración do país/rexión** panel, escolla a [país/rexión admitido](#supported-countriesregions) e selecciona **Solicitar**.

   > [!NOTE]
   > Cando escolla as súas propias marcas, o sistema ofrece suxestións en función do país ou rexión seleccionado. Cando escolla unha industria, obterá as marcas ou intereses máis relevantes en función do país ou rexión seleccionado.

1. Escolla ata cinco marcas ou intereses usando unha ou as dúas opcións seguintes:

   - **Industria**: Seleccione a súa industria na lista despregable e logo escolla entre as mellores marcas ou intereses desa industria.
   - **Escoller os seus propios**: insira unha marca ou interese que sexa relevante para a súa organización e logo escolla entre as suxestións coincidentes. Se non enumeramos unha marca ou interese que está a buscar, envíenos comentarios usando a ligazón **Suxerir**.

1. Seleccione **A continuación** e revisa as túas preferencias de enriquecemento predeterminadas e actualízaas segundo sexa necesario.

   :::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Captura de pantalla da xanela de preferencias de enriquecemento.":::

1. Seleccione **Seguinte**.

1. Seleccione o **Conxunto de datos do cliente** e escolle o perfil ou segmento que queres enriquecer con datos de Microsoft. O *Cliente* a entidade enriquece todos os seus perfís de clientes mentres que un segmento enriquece só os perfís de clientes contidos nese segmento.

1. Seleccione **Seguinte**.

1. Asigne os seus campos desde a súa entidade cliente unificada aos datos de Microsoft.

   > [!NOTE]
   > Son necesarios polo menos os atributos Data de nacemento ou Sexo. Requírese o país/rexión e polo menos a cidade (e o estado/provincia) ou o código postal. Recomendamos que a data de nacemento se converta ao tipo DateTime durante a inxestión de datos. Alternativamente, pode ser unha cadea en [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) formato "aaaa-MM-dd" ou "aaaa-MM-ddTHH:mm:ss".

1. Seleccione **Seguinte** para concluír a asignación do campo.

1. Proporcione un nome para o enriquecemento. O **Nome da entidade de saída** se selecciona automaticamente.

   :::image type="content" source="media/enrichment-interests-summary.png" alt-text="Revisión de intereses e nome de páxina.":::

1. Seleccione **Gardar enriquecemento** despois de revisar as súas opcións.

1. Seleccione **Corre** para iniciar o proceso de enriquecemento ou pechar para volver ao **Enriquecementos** páxina.

   Ao enriquecer perfís, enriqueceremos todos os perfís de clientes dos que obteñamos datos das marcas e intereses seleccionados, incluídos os perfís que non están no país ou rexión seleccionados. Por exemplo, se seleccionou Alemaña, enriqueceremos os perfís situados nos Estados Unidos se temos datos dispoñibles para as marcas e os intereses seleccionados nos Estados Unidos.

## <a name="enrichment-results"></a>Resultados de enriquecemento

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

:::image type="content" source="media/my-enrichments.png" alt-text="Versión preliminar dos resultados despois de executar o proceso de enriquecemento.":::

Os resultados inclúen **Nivel de afinidade** ou **Compartir de voz** gráficos.

As entidades creadas a partir dos enriquecementos están listadas baixo o **Enriquecemento** grupo en **Datos** > **Entidades**. Os datos enriquecidos das marcas van para o **BrandAffinityFromMicrosoft** e **BrandShareOfVoiceFromMicrosoft** entidades. Os datos dos intereses están no **InterestAffinityFromMicrosoft** e **InterestShareOfVoiceFromMicrosoft** entidades.

## <a name="see-enrichment-data-on-the-customer-card"></a>Vexa datos de enriquecemento na tarxeta de cliente

O SoV de marca e interese tamén se pode ver nas tarxetas de clientes individuais. Vaia a **Clientes** e seleccione un perfil de cliente. Na tarxeta do cliente, atoparás gráficos para a marca ou o SoV de interese baseados nas persoas do perfil demográfico dese cliente.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Cartón de cliente con datos enriquecidos.":::

## <a name="next-steps"></a>Pasos seguintes

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]


[!INCLUDE [footer-include](includes/footer-banner.md)]
