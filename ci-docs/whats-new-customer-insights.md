---
title: Funcionalidades novas e futuras
description: Información sobre novas funcións, melloras e corrección de erros.
ms.date: 05/03/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: skumm
manager: shellyha
ms.openlocfilehash: af79c8369dd608e8ce1c14c50bb9aef3a79b9029
ms.sourcegitcommit: f5af5613afd9c3f2f0695e2d62d225f0b504f033
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 06/01/2022
ms.locfileid: "8833628"
---
# <a name="whats-new-in-dynamics-365-customer-insights"></a>Novidades de Dynamics 365 Customer Insights

Comprácenos anunciar as nosas últimas actualizacións! Este artigo resume as funcionalidades de previsualización pública, as melloras de dispoñibilidade xeral e as actualizacións de funcións. Para ver os plans de funcionalidades a longo prazo, vexa os [plans de versións de Dynamics 365 e Power Platform](/dynamics365/release-plans/).

Lanzamos as actualizacións rexión por rexión. Así, certas rexións poden ver as funcionalidades antes que outras. A menos que se especifique o contrario, non é necesario que realice ningunha acción e actualizaremos a aplicación automaticamente sen tempo de inactividade.

> [!TIP]
> Para enviar e votar solicitudes de funcionalidades e suxestións de produtos, vaia ao [Portal de ideas da aplicación Dynamics 365](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).


## <a name="april-2022-updates"></a>Actualizacións de abril de 2022

As actualizacións de abril de 2022 inclúen novas funcións, melloras de rendemento e corrección de erros.

### <a name="dun--bradstreet-enrichment-preview"></a>Enriquecemento de Dun & Bradstreet (Previsualización)

Dun & Bradstreet ofrece datos comerciais, análises e información para empresas. Permite aos clientes con perfís de clientes unificados para empresas enriquecer os seus datos. Os enriquecementos inclúen atributos como número DUNS, tamaño da empresa, localización, industria e moito máis.

Para obter máis información, consulte [Enriquecemento dos perfís de empresas con Dun & Bradstreet (Previsualización)](enrichment-dnb.md).

### <a name="define-the-measure-type-when-creating-a-new-measure"></a>Defina o tipo de medida ao crear unha nova medida

Agora podes distinguir entre medidas para perfís individuais e medidas de toda a túa empresa. Mentres que as medidas comerciais aparecen na páxina de inicio de Customer Insights, as medidas dos clientes están expostas nas vistas detalladas dos clientes.

Para obter máis información, consulte [Usa o creador de medidas para crear medidas desde cero](measure-builder.md).

### <a name="consolidation-of-customer-insights-documentation"></a>Consolidación da documentación de Customer Insights

Revisamos os nosos artigos de documentación e eliminamos as mencións ás estatísticas de compromiso e as capacidades de información sobre o público. No futuro, faremos referencia coherentemente ao nome do produto Customer Insights cando escribamos sobre as funcións principais da aplicación. Este cambio tamén leva a unha reestruturación significativa da táboa de contidos, a estrutura do URL e as rutas dos ficheiros no repositorio de documentación subxacente. Todos os teus marcadores ou ligazóns existentes seguen funcionando e redirixindo aos URL actualizados.

Se queres informarnos como percibes ese cambio ou detectar que algo non funciona como esperaba, infórmanos por [enviando comentarios para esta páxina](https://github.com/MicrosoftDocs/customer-insights/issues/new?title=&body=%0A%0A%5BEnter%20feedback%20here%5D%0A%0A%0A---%0A%23%23%23%23%20Document%20Details%0A%0A%E2%9A%A0%20*Do%20not%20edit%20this%20section.%20It%20is%20required%20for%20docs.microsoft.com%20%E2%9E%9F%20GitHub%20issue%20linking.*%0A%0A*%20ID%3A%20d323ba46-f96e-1972-bc52-9b88f7d9cdfa%0A*%20Version%20Independent%20ID%3A%20d323ba46-f96e-1972-bc52-9b88f7d9cdfa%0A*%20Content%3A%20%5BNew%20and%20upcoming%20features%20-%20Dynamics%20365%20Customer%20Insights%5D(https%3A%2F%2Fdocs.microsoft.com%2Fen-us%2Fdynamics365%2Fcustomer-insights%2Fwhats-new-customer-insights)%0A*%20Content%20Source%3A%20%5Bci-docs%2Fwhats-new-customer-insights.md%5D(https%3A%2F%2Fgithub.com%2FMicrosoftDocs%2Fcustomer-insights%2Fblob%2Fmain%2Fci-docs%2Fwhats-new-customer-insights.md)%0A*%20Service%3A%20**customer-insights**%0A*%20Sub-service%3A%20**audience-insights**%0A*%20GitHub%20Login%3A%20%40m-hartmann%0A*%20Microsoft%20Alias%3A%20**mhart**).

## <a name="march-2022-updates"></a>Actualizacións de marzo de 2022

As actualizacións de marzo de 2022 inclúen novas funcións, melloras de rendemento e corrección de erros.

### <a name="liveramp-abilitec-enrichment-preview"></a>Enriquecemento LiveRamp AbiliTec (vista previa)

LiveRamp ofrece resolución de identidade e consolidación de datos dos clientes. Podes asignar os identificadores persoais dos teus datos de cliente ao gráfico de identidade de AbiliTec e recibir ID de AbiliTec. Despois podes usar estes ID para unificar mellor os datos dos teus clientes.

Para obter máis información, consulte [Enriquece os perfís de clientes con datos de identidade de LiveRamp (vista previa)](enrichment-liveramp.md).

### <a name="organize-segments-and-measures-with-tags-and-filters"></a>Organiza segmentos e medidas con etiquetas e filtros

Se a túa organización mantén moitos segmentos ou medidas, ás veces pode resultar un reto atopar o axeitado. Esta nova función permíteche organizar listas mediante etiquetas e columnas. Axuda a atopar datos de forma rápida e sinxela e a personalizar as vistas.

Para obter máis información, consulte [Traballar con etiquetas e columnas](work-with-tags-columns.md).

### <a name="enable-data-sharing-with-dataverse-when-using-your-own-storage-account"></a>Activa o uso compartido de datos con Dataverse cando use a súa propia conta de almacenamento

Se o teu ambiente usa Azure Data Lake Storage para almacenar datos de Customer Insights e compartir datos Microsoft Dataverse precisa algunha configuración adicional.
Antes, só podías activar a compartición de datos con Dataverse cando os teus datos foron almacenados no noso lago de datos xestionado.

Para obter máis información, consulte [Activa o uso compartido de datos con Dataverse do teu propio Azure Data Lake Storage (Vista previa)](customer-insights-dataverse.md#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview).

### <a name="new-export-destinations-iterable-and-braze"></a>Novos destinos de exportación: Iterable e Braze

Seguimos ampliando o noso ecosistema de destinos de exportación con novas conexións. Agora podes exportar segmentos a Iterable e Braze para usar os seus servizos de activación.

Para obter máis información, consulte [Exportar segmentos a Iterable (vista previa)](export-iterable.md) e [Exportar segmentos a Braze (vista previa)](export-braze.md).

### <a name="improvements-to-marketo-and-google-ads-export"></a>Melloras na exportación de Marketo e Google Ads

O cambio de API nos servizos conectados leva a actualizacións para que os conectores funcionen de forma fiable e sen problemas. Publicamos algunhas actualizacións para as exportacións aos servizos de Marketo e Google Ads:

- Google Ads: a nova versión do conector de exportación de Google Ads simplifica a experiencia de autenticación e agora permíteche crear novas audiencias de Google Ads automaticamente. 
- Marketo: a nova versión do conector de exportación de Marketo ofrece soporte para o ID de Marketo, o que lle permite evitar a duplicación de datos, actualizar os rexistros existentes e crear novos rexistros en Marketo. 

## <a name="february-2022-updates"></a>Actualizacións de febreiro de 2022

As actualizacións de febreiro de 2022 inclúen novas funcións, melloras de rendemento e corrección de erros.

### <a name="general-availability-for-prediction-models"></a>Dispoñibilidade xeral para os modelos predición

Modelos prefabricados predición, incluídos **churn de subscricións**, **transaccional**, e **valor de vida do cliente (CLV)** estarán dispoñibles xeralmente como parte de Customer Insights. 

Para obter máis información, consulte [Visión xeral das predicións](predictions-overview.md).

### <a name="new-data-source-integration-with-azure-synapse-analytics-preview"></a>Novo orixe de datos: integración con Azure Synapse Analytics (Vista previa)

Azure Synapse Analytics é un servizo de análise empresarial que acelera o tempo para obter información en almacéns de datos e sistemas de big data.

Organizacións que xa usan Azure Synapse Analytics pode inxerir eses datos a Customer Insights. 

Para obter máis información, consulte [Conectar un Azure Synapse orixe de datos (vista previa)](connect-synapse.md).

### <a name="liveramp-enrichment-preview"></a>Enriquecemento LiveRamp (Previsualización)

LiveRamp ofrece resolución de identidade e consolidación de datos dos clientes. Podes asignar os identificadores persoais dos teus datos de cliente ao gráfico de identidade de AbiliTec e recibir ID de AbiliTec. Despois podes usar estes ID para unificar mellor os datos dos teus clientes.

Para obter máis información, consulte [Enriquece os perfís de clientes con datos de identidade de LiveRamp (vista previa)](enrichment-liveramp.md).

### <a name="enrichment-for-data-sources-preview"></a>Enriquecemento para fontes de datos (vista previa)

Use datos de fontes como Microsoft e outros socios para enriquecer os datos dos seus clientes antes da unificación de datos. Os enriquecementos orixe de datos axudan a producir datos máis completos e de calidade que poden axudar a conseguir mellores resultados unha vez que unifiques os teus datos.

Para obter máis información, consulte [Enriquecemento para fontes de datos (vista previa)](data-sources-enrichment.md).

### <a name="change-owner-of-environment"></a>Modificar propietario do ambiente

Aínda que varios usuarios poden ter permisos de administrador en Customer Insights, só un usuario é o propietario dun ambiente. Unha experiencia mellorada permíteche cambiar de propietario dun ambiente e reclamar a propiedade se un antigo propietario deixa a organización. 

Para obter máis información, consulte [Cambiar o propietario dun ambiente](manage-environments.md#change-the-owner-of-an-environment).

### <a name="data-preparation-process-lists-corruption-reason-for-corrupted-records"></a>O proceso de preparación de datos enumera os motivos da corrupción dos rexistros danados

A preparación de datos agora mostra o motivo da corrupción de todos os campos con datos danados. A información ofrécese a nivel de rexistro individual para facilitar a identificación. 

Para obter máis información, consulte [Fontes de datos danadas](entities.md#corrupted-data-sources).

### <a name="end-of-preview-for-reporting-features-in-the-engagement-insights-capability"></a>Fin da vista previa para as funcións de informes na capacidade de información de compromiso

O Dynamics 365 Customer Insights A vista previa da capacidade de datos de compromiso finalizou o 15 de febreiro de 2022.  
Este cambio significa que a experiencia de proba de Customer Insights xa non inclúe a posibilidade de crear funis nin outras funcións de informes.

Convidámoste a explorar e avaliar outras moitas características de [Insights do cliente](https://dynamics.microsoft.com/ai/customer-insights/), a plataforma de datos de clientes de Microsoft (CDP).    
 
Durante un período de transición, os participantes existentes de vista previa aínda teñen acceso a algunhas capacidades e funcións de vista previa:

- Obter código para instrumentalizar un sitio web ou unha aplicación para móbil 
- Consulta eventos e propiedades de eventos 
- Mellora os perfís unificados con eventos inxeridos e refinados para beneficiarse do valor total dos datos dos seus clientes
  
Durante o período de transición, os eventos capturados aínda se transmiten ao Data Lake conectado. Unha vez desactivada esta función, o uso compartido de datos deterase e non se enviarán novos eventos ao almacenamento conectado.
Póñase en contacto directamente co seu equipo da conta de Microsoft se tes preguntas sobre o final da vista previa da capacidade. O equipo da túa conta manterache ao día dos próximos lanzamentos. 

## <a name="january-2022-updates"></a>Actualizacións de xaneiro de 2022

As actualizacións de xaneiro de 2022 inclúen novas funcións, melloras de rendemento e corrección de erros.

### <a name="sentiment-analysis-of-your-customers-feedback"></a>Análise de sentimentos dos comentarios dos teus clientes

Customer Insights ofrece unha nova función impulsada pola intelixencia artificial para sintetizar o sentimento dos clientes e identificar aspectos comerciais específicos como oportunidades de melloras específicas. Ao analizar os comentarios escritos dos teus clientes, podes obter información precisa a baixo custo. Análise de sentimentos impulsada por modelos de procesamento da linguaxe natural (NLP) que xeran dous coñecementos derivados para cada ID de cliente. Unha puntuación de sentimento (de –5 a 5) e unha lista de aspectos comerciais aplicables. 

Para obter máis información, consulte [Analiza o sentimento nos comentarios dos clientes (Vista previa)](sentiment-analysis.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]