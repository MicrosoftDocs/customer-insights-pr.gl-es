---
title: Funcionalidades novas e futuras
description: Información sobre novas funcións, melloras e corrección de erros.
ms.date: 04/05/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: skumm
manager: shellyha
ms.openlocfilehash: 2f081306271a170cf3e250fc1a193cedb70aeec6
ms.sourcegitcommit: 0363559a1af7ae16da2a96b09d6a4a8a53a8cbb8
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 04/05/2022
ms.locfileid: "8547670"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a>Novidades na capacidade de información do público de Dynamics 365 Customer Insights

Comprácenos anunciar as nosas últimas actualizacións! Este artigo resume as funcionalidades de previsualización pública, as melloras de dispoñibilidade xeral e as actualizacións de funcións. Para ver os plans de funcionalidades a longo prazo, vexa os [plans de versións de Dynamics 365 e Power Platform](/dynamics365/release-plans/).

Lanzamos as actualizacións rexión por rexión. Así, certas rexións poden ver as funcionalidades antes que outras. A menos que se especifique o contrario, non é necesario que realice ningunha acción e actualizaremos a aplicación automaticamente sen tempo de inactividade.

> [!TIP]
> Para enviar e votar solicitudes de funcionalidades e suxestións de produtos, vaia ao [Portal de ideas da aplicación Dynamics 365](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).


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

Para obter máis información, consulte [Activa o uso compartido de datos con Dataverse do teu propio Azure Data Lake Storage (Vista previa)](manage-environments.md#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview).

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

### <a name="liveramp-enrichment-preview"></a>Enriquecemento LiveRamp (vista previa)

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

Convidámoste a explorar e avaliar outras moitas características de [Información do cliente](https://dynamics.microsoft.com/ai/customer-insights/), a plataforma de datos de clientes de Microsoft (CDP).    
 
Durante un período de transición, os participantes existentes de vista previa aínda teñen acceso a algunhas capacidades e funcións de vista previa:

- Obter código para instrumentalizar un sitio web ou unha aplicación para móbil 
- Consulta eventos e propiedades de eventos 
- Mellora os perfís unificados con eventos inxeridos e refinados para beneficiarse do valor total dos datos dos seus clientes
  
Durante o período de transición, os eventos capturados aínda se transmiten ao Data Lake conectado. Unha vez desactivada esta función, o intercambio de datos entre as estatísticas de compromiso e as estatísticas do público deterase e non se envía ningún evento novo ao almacenamento conectado.
Póñase en contacto directamente co equipo da súa conta de Microsoft se tes preguntas sobre o final da vista previa da capacidade. O equipo da túa conta manterache informado dos próximos lanzamentos. 

## <a name="january-2022-updates"></a>Actualizacións de xaneiro de 2022

As actualizacións de xaneiro de 2022 inclúen novas funcións, melloras de rendemento e corrección de erros.

### <a name="sentiment-analysis-of-your-customers-feedback"></a>Análise de sentimentos dos comentarios dos teus clientes

Customer Insights ofrece unha nova función impulsada pola intelixencia artificial para sintetizar o sentimento dos clientes e identificar aspectos comerciais específicos como oportunidades de melloras específicas. Ao analizar os comentarios escritos dos teus clientes, podes obter información precisa a baixo custo. Análise de sentimentos impulsada por modelos de procesamento da linguaxe natural (NLP) que xeran dous coñecementos derivados para cada ID de cliente. Unha puntuación de sentimento (de –5 a 5) e unha lista de aspectos comerciais aplicables. 

Para obter máis información, consulte [Analiza o sentimento nos comentarios dos clientes (Vista previa)](sentiment-analysis.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]