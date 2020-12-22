---
title: Enriquecer os perfís de clientes con Microsoft Graph
description: Use datos de propietario de Microsoft Graph para enriquecer os seus datos de clientes con afinidades de marca e intereses.
ms.date: 09/28/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 4f93a2337815f76b98185ecb3755e08443031748
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405705"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a>Enriquecer os perfís de clientes con afinidades de marca e intereses (vista previa)

Use datos de propietario de Microsoft Graph para enriquecer os seus datos de clientes con afinidades de marca e intereses. Estas afinidades determínanse en base a datos de persoas con datos demográficos semellantes aos seus clientes. Esta información axúdalle a comprender e segmentar mellor os seus clientes en función das súas afinidades a marcas e intereses específicos.

Para obter información do público, vaia a **Datos** > **Enriquecemento** para [configurar e ver enriquecementos](enrichment-hub.md).

Para configurar o enriquecemento de afinidades de marca, diríxase á pestana **Descubrir** e seleccione **Enriquecer os meus datos** no mosaico **Marcas**.

Para configurar o enriquecemento de afinidades de intereses, diríxase á pestana **Descubrir** e seleccione **Enriquecer os meus datos** no mosaico **Intereses**.

   > [!div class="mx-imgBorder"]
   > ![Mosaicos de Marcas e intereses](media/BrandsInterest-tile-Hub.png "Mosaicos de marcas e intereses")

## <a name="about-microsoft-graph"></a>Acerca de Microsoft Graph

Usamos datos de busca en liña de Microsoft Graph para atopar afinidades para marcas e intereses en varios segmentos demográficos (definidos por idade, sexo ou localización). O volume de busca en liña dunha marca ou interese determina a cantidade de afinidade que ten un segmento demográfico en comparación con outros segmentos con esa marca ou interese.

[Máis información acerca de Microsoft Graph](https://docs.microsoft.com/graph/overview).

## <a name="affinity-score-and-confidence"></a>Puntuación de afinidade e confianza

A **puntuación de afinidade** calcúlase nunha escala de 100 puntos, co 100 que representa o segmento que ten maior afinidade por unha marca ou interese.

A **confianza da afinidade** tamén se calcula nunha escala de 100 puntos. Indica o nivel de confianza do sistema en que un segmento ten unha afinidade pola marca ou interese. O nivel de confianza baséase no tamaño do segmento e na granularidade do segmento. O tamaño do segmento está determinado pola cantidade de datos que temos para un segmento dado. A granularidade do segmento está determinada por cantos atributos (idade, sexo, localización) están dispoñibles nun perfil.

Non normalizamos as puntuacións do seu conxunto de datos. Por conseguinte, pode que non vexa todos os posibles valores de puntuación de afinidade para o seu conxunto de datos. Por exemplo, pode non haber un perfil de cliente enriquecido cunha puntuación de afinidade de 100 nos seus datos. Isto é posible se non hai clientes no segmento demográfico que obtivo 100 de puntuación por unha marca ou interese determinados.

> [!TIP]
> Ao [crear segmentos](segments.md) usando puntuacións de afinidade, revise a distribución das puntuacións de afinidade do seu conxunto de datos antes de decidir sobre os limiares de puntuación adecuados. Por exemplo, unha puntuación de afinidade de 10 pode considerarse significativa nun conxunto de datos que ten unha puntuación de afinidade máis alta de só 25 para unha determinada marca ou interese.

## <a name="supported-countriesregions"></a>Países ou rexións compatibles

Actualmente son compatibles as seguintes opcións de país ou rexión: Australia, Canadá (inglés), Francia, Alemaña, Reino Unido ou Estados Unidos (inglés).

Para seleccionar un país, abra **Enriquecemento de marcas** ou **Enriquecemento de intereses** e seleccione **Cambiar** xunto a **País/Rexión**. No panel **Configuración do país/rexión**, escolla unha opción e seleccione **Solicitar**.

### <a name="implications-related-to-country-selection"></a>Implicacións relacionadas coa selección do país

- Ao [escoller as súas propias marcas](#define-your-brands-or-interests), proporcionaremos suxestións en función do país/rexión seleccionado.

- Cando [escollemos un sector](#define-your-brands-or-interests), identificaremos as marcas ou intereses máis relevantes en función do país/rexión seleccionado.

- Ao [asignar os seus campos ](#map-your-fields), se o campo País/Rexión non se asigna, usaremos os datos de Microsoft Graph do país/rexión seleccionados para enriquecer os seus perfís de clientes. Tamén empregaremos esa selección para enriquecer os seus perfís de clientes que non teñan datos de país/rexión dispoñibles.

- Ao [enriquecer perfís](#refresh-enrichment), enriqueremos todos os perfís de clientes para os que dispoñemos de datos de Microsoft Graph para as marcas e intereses seleccionados, incluídos os perfís que non se atopan no país/rexión seleccionado. Por exemplo, se seleccionou Alemaña, enriqueremos os perfís situados nos Estados Unidos se temos datos de Microsoft Graph dispoñibles para as marcas e intereses seleccionados nos Estados Unidos.

## <a name="configure-enrichment"></a>Configurar o enriquecemento

A configuración do enriquecemento de marcas ou intereses consta de dous pasos:

### <a name="define-your-brands-or-interests"></a>Definir as marcas ou os intereses

Seleccione unha das seguintes opcións:

- **Sector**: o sistema identifica as principais marcas ou intereses relevantes para a súa industria e enriquece os datos dos seus clientes con elas.
- **Elixa o seu**: seleccione ata cinco elementos da lista de marcas ou intereses máis relevantes para a súa organización.

Para engadir unha marca ou interese, introdúzaa na área de entrada para obter suxestións baseadas nos termos correspondentes. Se non enumeramos unha marca ou interese que está a buscar, envíenos comentarios usando a ligazón **Suxerir**.

### <a name="map-your-fields"></a>Asignar os campos

Asigne campos desde a súa entidade de cliente unificada a polo menos dous atributos para definir o segmento demográfico que quere usar para enriquecer os seus datos de clientes. Seleccione **Editar** definir a asignación dos campos e seleccionar **Aplicar** cando remate. Seleccione **Gardar** para completar a asignación de campos.

Admítense os seguintes formatos e valores, os valores non diferencian entre maiúsculas e minúsculas:

- **Data de nacemento**: Recomendamos que a data de nacemento sexa convertida ao tipo DateTime durante a inxestión de datos. Alternativamente, pode ser unha cadea en formato [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) "aaaa-MM-dd" ou "aaaa-MM-ddTHH: mm:ssZ".
- **Sexo**: Masculino, Feminino, Descoñecido
- **Código postal**: Códigos de cinco díxitos para EUA, código postal estándar en calquera outro lugar
- **Cidade**: Nome da cidade en inglés
- **Estado/Provincia**: Abreviatura de dúas letras para Estados Unidos e Canadá. Abreviación de dúas ou tres letras para Australia. Non se aplica a Francia, Alemaña ou Reino Unido.
- **País/Rexión**:

  - EUA: Estados Unidos de América, Estados Unidos, EE. UU., EUA, EU
  - CA: Canadá, CA
  - RU: Reino Unido, RU, Gran Bretaña, GB, Reino Unido de Gran Bretaña e Irlanda do Norte, Reino Unido de Gran Bretaña
  - AU: Australia, AU, Mancomunidade de Australia
  - FR: Francia, FR, República Francesa
  - DE: Alemaña, Alemán, Deutschland, Allemagne, DE, República Federal de Alemaña, República de Alemaña

## <a name="refresh-enrichment"></a>Actualizar o enriquecemento

Execute o enriquecemento despois de configurar marcas, intereses e asignación de campos para os datos demográficos. Para iniciar o proceso, seleccione **Executar** na páxina de configuración da marca ou o interese. Ademais, pode deixar que o sistema execute o enriquecemento automaticamente como parte dunha actualización programada.
Dependendo do tamaño dos datos dos seus clientes, a execución do enriquecemento pode levar uns minutos.

> [!TIP]
> Existen [seis tipos de estado](system.md#status-types) para as tarefas ou os procesos. Ademais, a maioría dos procesos [dependen doutros procesos descendentes](system.md#refresh-policies). Pode seleccionar o estado dun proceso para ver detalles sobre o progreso de todo o traballo. Despois de seleccionar **Ver detalles** para unha das tarefas do traballo, atopará información adicional: o tempo de procesamento, a última data de procesamento e todos os erros e avisos asociados á tarefa.

## <a name="enrichment-results"></a>Resultados de enriquecemento

Despois de executar o proceso de enriquecemento, vaia a **Os meus enriquecementos** para revisar o número total de clientes enriquecidos e unha subdivisión de marcas ou intereses nos perfís de clientes enriquecidos.

:::image type="content" source="media/my-enrichments.png" alt-text="Vista previa dos resultados despois de executar o proceso de enriquecemento":::

Revise os datos enriquecidos seleccionando **Ver datos enriquecidos** no gráfico. Os datos enriquecidos para as marcas van á entidade **BrandAffinityFromMicrosoft**. Datos para intereses na entidade **InterestAffinityFromMicrosoft**. Tamén atopará estas entidades enumeradas no grupo **Enriquecemento** en **Datos** > **Entidades**.

## <a name="see-enrichment-data-on-the-customer-card"></a>Vexa datos de enriquecemento na tarxeta de cliente

As afinidades de marca e interese tamén se poden ver nas tarxetas de clientes individuais. Vaia a **Clientes** e seleccione un perfil de cliente. Na tarxeta de cliente atopará gráficos das marcas ou intereses polos que teñen afinidade os usuarios do perfil demográfico dese cliente.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Tarxeta de cliente con datos enriquecidos":::

## <a name="next-steps"></a>Seguintes pasos

Crear sobre os seus datos enriquecidos de clientes. Cree [Segmentos](segments.md), [Medidas](measures.md) e incluso [exporte os datos](export-destinations.md) para ofrecer experiencias personalizadas aos seus clientes.
