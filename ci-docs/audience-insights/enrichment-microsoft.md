---
title: Enriquecer os perfís de clientes con datos de Microsoft
description: Use datos propietarios de Microsoft para enriquecer os seus datos de clientes con afinidades de marcas e intereses.
ms.date: 11/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: c25dbb7a877da2d3fccc1a4e5b219b9792bc6402
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 11/02/2021
ms.locfileid: "7732540"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a>Enriquecer os perfís de clientes con afinidades de marca e intereses (vista previa)

Use datos propietarios de Microsoft para enriquecer os seus datos de clientes con afinidades de marcas e intereses. Estas afinidades baséanse nos datos de persoas con factores demográficos similares ao dos clientes. Esta información axúdalle a comprender e segmentar mellor os seus clientes en función das súas afinidades a marcas e intereses específicos.

Para obter información do público, vaia a **Datos** > **Enriquecemento** para [configurar e ver enriquecementos](enrichment-hub.md).

Para configurar o enriquecemento de afinidades de marca, diríxase á pestana **Descubrir** e seleccione **Enriquecer os meus datos** no mosaico **Marcas**.

Para configurar o enriquecemento de afinidades de intereses, diríxase á pestana **Descubrir** e seleccione **Enriquecer os meus datos** no mosaico **Intereses**.

   > [!div class="mx-imgBorder"]
   > ![Mosaicos de marcas e intereses.](media/BrandsInterest-tile-Hub.png "Mosaicos de marcas e intereses")

## <a name="how-we-determine-affinities"></a>Como determinamos as afinidades

Usamos os datos de busca en liña de Microsoft para atopar afinidades de marcas e intereses en diversos segmentos demográficos (definidos por idade, sexo ou situación). O volume de busca en liña dunha marca ou interese determina a cantidade de afinidade que ten un segmento demográfico en comparación con outros segmentos con esa marca ou interese.

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

Seleccione **Enriquecer entidade** e escolla o conxunto de datos que quere enriquecer cos datos da empresa de Microsoft. Pode seleccionar a entidade Cliente para enriquecer todos os seus perfís de clientes ou seleccione unha entidade de segmento para enriquecer só os perfís de clientes contidos nese segmento.

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

Revise os datos enriquecidos seleccionando **Ver datos enriquecidos** no gráfico. Os datos enriquecidos para as marcas van á entidade **BrandAffinityFromMicrosoft**. Datos para intereses na entidade **InterestAffinityFromMicrosoft**. Tamén atopará estas entidades enumeradas no grupo **Enriquecemento** en **Datos** > **Entidades**.

Verá un gráfico co número de perfís de clientes enriquecidos ao longo do tempo e unha vista previa da entidade enriquecida. Seleccione **Mostrar máis** no mosaico de vista previa para abrir a entidade enriquecida.

## <a name="see-enrichment-data-on-the-customer-card"></a>Vexa datos de enriquecemento na tarxeta de cliente

As afinidades de marca e interese tamén se poden ver nas tarxetas de clientes individuais. Vaia a **Clientes** e seleccione un perfil de cliente. Na tarxeta de cliente atopará gráficos das marcas ou intereses polos que teñen afinidade os usuarios do perfil demográfico dese cliente.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Cartón de cliente con datos enriquecidos.":::

## <a name="next-steps"></a>Pasos seguintes

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]


[!INCLUDE[footer-include](../includes/footer-banner.md)]
