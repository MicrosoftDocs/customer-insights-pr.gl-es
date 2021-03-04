---
title: Enriquecer os perfís de clientes con Microsoft Graph
description: Use datos de propietario de Microsoft Graph para enriquecer os seus datos de clientes con afinidades de marca e intereses.
ms.date: 12/10/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 2c95369c778f592bc1460799aca0fa8cff813d68
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269328"
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

Para seleccionar un país, abra **Enriquecemento de marcas** ou **Enriquecemento de intereses** e seleccione **Cambiar** xunto a **País/Rexión**. No panel **Configuración do país/rexión**, escolla unha opción e seleccione **Solicitar**.

### <a name="implications-related-to-country-selection"></a>Implicacións relacionadas coa selección do país

- Cando [escolla as súas propias marcas](#define-your-brands-or-interests), o sistema ofrece suxestións en función do país ou rexión seleccionado.

- Cando [escolla unha industria](#define-your-brands-or-interests), obterá as marcas ou intereses máis relevantes en función do país ou rexión seleccionado.

- Cando [enriqueza perfís](#refresh-enrichment), enriqueceremos todos os perfís de clientes dos que obtemos datos das marcas e intereses seleccionados. Incluír perfís que non están no país ou rexión seleccionados. Por exemplo, se seleccionou Alemaña, enriqueremos os perfís situados nos Estados Unidos se temos datos de Microsoft Graph dispoñibles para as marcas e intereses seleccionados nos Estados Unidos.

## <a name="configure-enrichment"></a>Configurar o enriquecemento

### <a name="define-your-brands-or-interests"></a>Definir as marcas ou os intereses

Seleccione unha das seguintes opcións:

- **Sector**: o sistema identifica as principais marcas ou intereses relevantes para a súa industria e enriquece os datos dos seus clientes con elas.
- **Elixa o seu**: seleccione ata cinco elementos da lista de marcas ou intereses máis relevantes para a súa organización.

Para engadir unha marca ou interese, introdúzaa na área de entrada para obter suxestións baseadas nos termos correspondentes. Se non enumeramos unha marca ou interese que está a buscar, envíenos comentarios usando a ligazón **Suxerir**.

### <a name="review-enrichment-preferences"></a>Revisar preferencias de enriquecemento

Revise as súas preferencias de enriquecemento predeterminadas e actualíceas segundo sexa necesario.

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Captura de pantalla da xanela de preferencias de enriquecemento.":::

### <a name="select-entity-to-enrich"></a>Seleccionar entidade para enriquecer

Seleccione **Entidade enriquecida** e escolla o conxunto de datos que desexa enriquecer cos datos da empresa de Microsoft Graph. Pode seleccionar a entidade Cliente para enriquecer todos os seus perfís de clientes ou seleccione unha entidade de segmento para enriquecer só os perfís de clientes contidos nese segmento.

### <a name="map-your-fields"></a>Asignar os campos

Asigne campos da súa entidade cliente unificada para definir o segmento demográfico que desexa que use o sistema para enriquecer os datos dos seus clientes. Asigne o País/Rexión e polo menos os atributos Data de nacemento ou Sexo. Ademais, debe asignar polo menos un código de cidade (e estado/provincia) ou codigo postal. Seleccione **Editar** definir a asignación dos campos e seleccionar **Aplicar** cando remate. Seleccione **Gardar** para completar a asignación de campos.

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


[!INCLUDE[footer-include](../includes/footer-banner.md)]