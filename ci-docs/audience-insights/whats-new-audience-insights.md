---
title: Funcionalidades novas e futuras
description: Información sobre novas funcións, melloras e corrección de erros.
ms.date: 08/31/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: midevane
manager: shellyha
ms.openlocfilehash: fcc45c24e9d89516dba9964ee16f57caf439eff0
ms.sourcegitcommit: 2abe9b661b8c3c01e9730c629e383402e3f6a655
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 08/31/2021
ms.locfileid: "7465203"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a>Novidades na capacidade de información do público de Dynamics 365 Customer Insights

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Comprácenos anunciar as nosas últimas actualizacións! Este artigo resume as funcionalidades de previsualización pública, as melloras de dispoñibilidade xeral e as actualizacións de funcións. Para ver os plans de funcionalidades a longo prazo, vexa os [plans de versións de Dynamics 365 e Power Platform](/dynamics365/release-plans/).

Lanzamos as actualizacións rexión por rexión. Así, certas rexións poden ver as funcionalidades antes que outras. A menos que se especifique o contrario, non é necesario que realice ningunha acción e actualizaremos a aplicación automaticamente sen tempo de inactividade.

> [!TIP]
> Para enviar e votar solicitudes de funcionalidades e suxestións de produtos, vaia ao [Portal de ideas da aplicación Dynamics 365](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).

## <a name="august-2021-updates"></a>Actualizacións de agosto de 2021

As actualizacións de xullo e agosto de 2021 inclúen unha nova función, actualizacións de rendemento e corrección de erros.

### <a name="extensibility"></a>Extensibilidade

- **Exportar segmentos a Klaviyo** Ampliamos os nosos [destinos de exportación para incluír Klaviyo](export-klaviyo.md). Agora pode exportar segmentos para crear campañas, levar a cabo márketing por correo electrónico e usar grupos específicos de clientes con Klaviyo. 


## <a name="june-2021-updates"></a>Actualizacións de xuño de 2021

As actualizacións de xuño de 2021 inclúen varias características, actualizacións de rendemento e correccións de erros.

### <a name="data-ingestion"></a>Inxestión de datos

- **Actualizacións de progreso da unificación de datos mellorado** Agora pode ver actualizacións de estado dinámicas, melloradas e máis detalladas nos pasos do [proceso de unificación de datos](data-unification.md). Esta función permítelle rastrexar o progreso detallado para comprender o fluxo do proceso e tomar medidas se algún paso precisa atención.

### <a name="extensibility"></a>Extensibilidade

- **Exportar segmentos e outros datos a Salesforce Marketing Cloud** Ampliamos os nosos destinos de exportación para incluír [Salesforce Marketing Cloud](export-salesforce.md). Agora pode exportar segmentos e outros tipos de datos a Salesforce Marketing Cloud a través dunha exportación SFTP con marca. A importación de datos pódese automatizar completamente en Salesforce e empregarse para crear campañas de márketing máis eficaces.  
 
- **Exportar segmentos a ActiveCampaign** Ampliamos os nosos destinos de exportación para incluír [Active Campaign](export-active-campaign.md). Agora pode exportar segmentos para xerar campañas, levar a cabo márketing por correo electrónico e traballar con grupos específicos de clientes en ActiveCampaign.
 
- **Exportar segmentos a Sendinblue** Ampliamos os nosos destinos de exportación para incluír [Sendinblue](export-sendinblue.md). Agora pode exportar segmentos para xerar campañas, levar a cabo márketing por correo electrónico e traballar con grupos específicos de clientes con Sendinblue.
 
### <a name="ux-updates"></a>Actualizacións de UX 

- **Páxina de clientes e páxina de detalles do perfil novas e melloradas** Redeseñamos a páxina de clientes e as páxinas de detalles do perfil para mellorar a experiencia do usuario e obter un mellor desempeño. Estes cambios permiten ver, ordenar, buscar e filtrar clientes. Agora os filtros están representados no URL para compartir os resultados da busca con outros usuarios sen problemas. Os resultados da busca tamén se poden gardar como un segmento.    
  A páxina de detalles dos perfís de clientes agora agrupa datos en varias subseccións, como datos demográficos, ID e outros atributos de perfil para unha mellor lexibilidade. Outras seccións da páxina de detalles do perfil agora son máis interactivas. Por exemplo, a sección de actividades agora permite filtrar e ordenar.


## <a name="may-2021-updates"></a>Actualizacións de maio de 2021

As actualizacións de maio de 2021 inclúen varias funcións, actualizacións de rendemento e corrección de erros.

### <a name="data-ingestion"></a>Inxestión de datos

- **Ver ou modificar a definición das entidades ou os metadatos ao anexar datos de Azure Data Lake Storage** Agora pode ver e editar a definición das entidades ou os metadatos na información do público ao anexar datos dun cartafol de Common Data Model en Azure Data Lake Storage. Esta capacidade proporciona comentarios, validación do modelo e comprobación de erros en tempo real. Permite editar tanto o ficheiro model.json como o manifest.json sen problemas.

### <a name="extensibility"></a>Extensibilidade

- **Exportacións de segmentos, programación personalizada e duplicación melloradas** Agora pode [ver todas as exportacións dun segmento específico](export-destinations.md#view-exports-and-export-details) nunha lista. Esta nova vista axuda a xestionar como se usa un segmento específico e a adaptar as exportacións existentes ou crear outras novas.    
  Pode [definir programacións de actualización personalizadas](export-destinations.md#schedule-and-run-exports) para exportacións individuais ou varias exportacións á vez. Ata agora, todas as exportacións executábanse con cada actualización do sistema.    
  En vez de crear unha nova exportación desde cero, pode comezar a partir dunha existente para aforrar tempo.

- **Exportar segmentos a Microsoft Advertising** Ampliamos os nosos destinos de exportación para incluír Microsoft Advertising. Cree públicos de Coincidencia de clientes en Microsoft Advertising cos datos de perfil de cliente unificado e use estes públicos para as campañas de publicidade. Para obter máis información, consulte [Exportar segmentos a Microsoft Advertising](export-microsoft-advertising.md).

- **Exportar segmentos a LinkedIn Ads** Ampliamos os nosos destinos de exportación para incluír LinkedIn Ads e permitirlle desbloquear a orientación aos contactos e ás empresa en LinkedIn exportando os datos dos perfís de clientes unificados. Para obter máis información, consulte [Exportar segmentos a LinkedIn Ads](export-linkedin-ads.md).


- **Exportar segmentos a Omnisend** Ampliamos os nosos destinos de exportación para incluír Omnisend. Use os segmentos creados na información do público para xerar campañas, proporcionar márketing por correo electrónico e usar grupos específicos de clientes con Omnisend. Para obter máis información, consulte [Exportar segmentos a Omnisend](export-omnisend.md)

### <a name="predictions"></a>Predicións

- **Informe de usabilidade dos datos de entrada** O informe de usabilidade dos datos de entrada ofrece unha visión consolidada dos erros e advertencias que poden xerar as predicións listas para utilizar. Tamén ofrece recomendacións sobre como mellorar o desempeño do modelo.    
  O informe estará dispoñible despois de que un modelo finalice o seu proceso de adestramento. Créase para cada modelo por separado, independentemente de se se completou correctamente ou non.
  Actualmente esta funcionalidade só está dispoñible para o modelo de abandono da transacción. Para máis información, consulte [Informe de usabilidade dos datos de entrada](manage-predictions.md#input-data-usability-report).

### <a name="relationships"></a>Relacións

- **Visualizador de relacións** A vista do visualizador de relacións permítelle ver todas as relacións existentes entre entidades e a súa cardinalidade. Agora as relacións organízanse en grupos: relacións creadas polo usuario, relacións do sistema e relacións herdadas. Tamén pode exportar unha vista como imaxe. Para obter máis información, consulte [Ver relacións](relationships.md#view-relationships). 

## <a name="april-2021-updates"></a>Actualizacións de abril de 2021

As actualizacións de abril de 2021 inclúen varias funcións, actualizacións de rendemento e corrección de erros.

### <a name="data-unification"></a>Unificación de datos
 
- **Experiencia de combinación mellorada para a unificación de datos**    
  
   Agora contamos cunha experiencia de usuario mellorada na configuración da combinación do proceso de unificación de datos. As modificacións inclúen unha orde intuitiva dos campos combinados e estatísticas detalladas sobre campos combinados e singleton.

- **Reordenación de entidades e configuración de todos os rexistros de orixe na entidade Cliente**  
      
   Agora pode reordenar e eliminar entidades dun plan de combinación existente no proceso de unificación de datos. Dá flexibilidade para reordenar as entidades no proceso de busca de coincidencias segundo as necesidades da empresa. Ademais, activamos a inclusión de todos os rexistros non coincidentes na entidade *Cliente* final, o que permite establecer a definición do conxunto de datos dos perfís de clientes.

### <a name="enrichments"></a>Enriquecementos

 - **Novo enriquecemento: enderezos mellorados**    
  
   Estamos encantados de presentar un novo enriquecemento para mellorar os enderezos nos datos dos seus clientes. Os enderezos dos seus datos poden estar sen estruturar, incompletos ou ser incorrectos. Esta funcionalidade usa os modelos de Microsoft para normalizar e enriquecer os seus enderezos en formato Common Data Model para unha mellor precisión e información.
 
   Para obter máis información, consulte [Enriquecemento dos perfís de clientes con enderezos mellorados](enrichment-enhanced-addresses.md).

- **Experiencia de configuración guiada para os enriquecementos**    
  
   Corriximos a experiencia de configuración dos enriquecementos cunha experiencia sinxela e guiada. Agora ten un proceso paso a paso claro para crear e editar enriquecementos.
 
   Ademais, separamos a configuración das conexións para enriquecementos de terceiros a fin de permitir que a mesma conexión poida ser utilizada por varios enriquecementos. Só os administradores poden configurar novas conexións, pero as conexións creadas están dispoñibles tanto para administradores como para colaboradores.    

   Para obter máis información, consulte [Visión xeral das conexións](connections.md).

- **Enriquecementos múltiples do mesmo tipo**    
  
   Agora permitímoslles aos usuarios crear e xestionar múltiples enriquecementos do mesmo tipo. Por exemplo, agora pode crear dous enriquecementos de enderezos distintos para enriquecer dous segmentos de clientes diferentes. Os límites aplícanse ao número de enriquecementos do mesmo tipo que se poden crear e varían segundo o tipo de enriquecemento.
  
   Para obter máis información, consulte [Enriquecemento dos perfís de clientes](enrichment-hub.md).

## <a name="march-2021-updates"></a>Actualizacións de marzo de 2021

As actualizacións de marzo de 2021 inclúen varias funcións, actualizacións de rendemento e corrección de erros.

### <a name="activities"></a>Actividades

- **Asistente de actividades e tipos semánticos**

   Melloramos e actualizamos a nosa experiencia de asignación de actividades para guiar e simplificar a creación de asignación de actividades. Nesta nova experiencia, os usuarios obteñen unha experiencia guiada para axudar a completar cada paso do proceso. No paso de asignación de actividades, ademais de escoller entre moitos tipos de actividade, o usuario pode escoller asignar semánticamente datos de *Subscrición* e/ou *SalesOrderLine* aos esquemas estándar da industria, que se poden usar para o consumo de baixada.   

   Para obter máis información, consulte [Actividades do cliente](activities.md).

### <a name="data-ingestion"></a>Inxestión de datos

- **Conectarse ás fontes de datos locais usando fluxos de datos e pasarelas de Power Platform** Comprácenos anunciar a versión preliminar de fluxos de datos de Power Platform e conectividade local usando pasarelas en Customer Insights cun ambiente de Power Platform ou Dataverse asociado. Calquera nova fonte de datos creada nun contorno Customer Insights cun ambiente de Dataverse ligado establecerase por defecto en fluxos de datos de Power Platform que achegan a conectividade de datos local e un rico conxunto de conectores e capacidades de transformación.

### <a name="extensibility"></a>Extensibilidade

- **Exportacións organizadas en conexións e exportacións** Cambiamos o nome da páxina **Exportar destinos** a **Conexións** e engadimos unha páxina separada para **Exportacións**. Como parte desta actualización, faremos unha transición das exportacións existentes a pares dunha conexión e unha exportación mediante esa conexión. Os administradores agora teñen máis claridade sobre os datos de saída na páxina **Conexións**. Todos os roles de usuario teñen acceso á páxina **Exportacións**, pero só os administradores poden optar por permitir aos colaboradores editar exportacións específicas con conexións compartidas.     
  Para obter máis información, consulte [Descrición xeral das conexións](connections.md) e [Descrición xeral das exportacións](export-destinations.md).

- **Exportar segmentos a Campaign Monitor** Ampliamos os nosos destinos de exportación para incluír Campaign Monitor. Agora pode exportar segmentos de Customer Insights a listas de Campaign Monitor e utilizalos como base para as súas campañas de mercadotecnia.    
   Para obter máis información, consulte [Exportar a Campaign Monitor](export-campaign-monitor.md).

- **Exportar segmentos a Constant Contact** Ampliamos os nosos destinos de exportación para incluír Constant Contact. Agora pode exportar segmentos de Customer Insights a listas de Constant Contact e utilizalos como base para as súas campañas de mercadotecnia.   
   Para obter máis información, consulte [Exportar a Constant Contact](export-constant-contact.md).

- **Exportar segmentos a RollWorks** Ampliamos os nosos destinos de exportación para incluír RollWorks. Agora pode exportar segmentos de Customer Insights a públicos de RollWorks e utilizalos como base para as súa publicidade B2B.    
   Para obter máis información, consulte [Exportar a RollWorks](export-rollworks.md).

- **Exportar segmentos a Snapchat** Ampliamos os nosos destinos de exportación para incluír Snapchat. Agora pode exportar segmentos de Customer Insights a públicos de Snapchat e utilizalos como base para as súa publicidade.     
   Para obter máis información, consulte [Exportar a Snapchat](export-snapchat.md).

### <a name="predictions"></a>Predicións

- **Utilizar filtros de produtos en recomendacións predictivas de produtos** Engadimos a capacidade de usar filtros de produtos no noso modelo de recomendación de produtos. Agora pode crear unha predición que use só un subconxunto dos seus produtos.    
   Para obter máis información, consulte [Configurar filtros de produtos](predict-product-recommendation.md#configure-product-filters).

- **Crear segmentos a partir de predicións de modelos** Engadimos un xeito rápido de crear segmentos usando os resultados dun modelo de predición. Desde a páxina de resultados do modelo, pode crear facilmente un novo segmento seleccionando a nova opción **Crear segmento**.    
  Para obter máis información, consulte [Crear un segmento baseado nun modelo de predición](prediction-based-segment.md).

- **Explicacións das recomendacións de produtos** Engadimos información que explica os factores clave aprendidos polo modelo de IA para xerar recomendacións de produtos e o grao en que eses factores contribúen ás recomendacións de produtos. Esta información engádese á pantalla de resultados do modelo.    
   Para obter máis información, consulte [Revisar o estado e os resultados dunha predición](predict-product-recommendation.md#review-a-prediction-status-and-results).

## <a name="february-2021-updates"></a>Actualizacións de febreiro de 2021

As actualizacións de febreiro de 2021 inclúen varias características, actualizacións de rendemento e correccións de erros.

#### <a name="extensibility"></a>Extensibilidade

- **Exportar segmentos a AdRoll**

  Ampliamos os nosos destinos de exportación para incluír AdRoll. Agora pode exportar segmentos de Customer Insights a públicos de AdRoll e usalos como base para a súa publicidade. Para obter máis información, consulte [Conector para AdRoll](export-adroll.md).

#### <a name="segments"></a>Segmentos
 
- **Duplicar un segmento**
  
  Para crear un novo segmento baseado nun xa existente, agora pode duplicar un segmento e editalo para melloralo. 

- **Engadir atributos adicionais a un segmento**

  Agora pode incluír atributos na saída do seu segmento, aínda que estes atributos non formen parte do perfil do cliente. Por exemplo, inclúa ID de subscrición nun segmento aínda que formen parte da entidade de subscrición que ten unha relación M: 1 coa entidade cliente. Sempre que o atributo pertenza a unha entidade relacionada coa entidade cliente, agora pode incluír estes atributos.  

#### <a name="predictions"></a>Predicións

- **Crear recomendacións preditivas de produtos**

  Comprender o que os clientes están interesados en mercar é un dos primeiros pasos necesarios para mellorar os ingresos empresariais e fidelizar aos clientes a través da personalización e o compromiso. Proporcionar recomendacións para produtos que non están aliñados cos intereses do seu cliente pode crear unha sensación de desconexión entre o cliente e a súa empresa e, en definitiva, limitar os ingresos e a experiencia potencial para un cliente. 

  Usando os seus propios datos, agora pode crear predicións sobre os produtos que probablemente adquirirán os seus clientes no futuro. Para obter máis información, consulte [Predición da recomendación de produto](predict-product-recommendation.md).

#### <a name="system-administration"></a>Administración do sistema

- **O contorno de copia admite máis tipos de fontes de datos**

  Os administradores poden copiar as configuracións de contorno a un novo contorno da mesma organización. Esta función amplía a funcionalidade do ambiente de copia para casos en que se usan as orixes de datos baseadas nun lago de datos xestionado de Microsoft Dataverse ou nun cartafol de Common Data Model.

## <a name="january-2021-updates"></a>Actualizacións de xaneiro de 2021

As actualizacións de xaneiro de 2021 inclúen varias características, actualizacións de rendemento e correccións de erros.

#### <a name="extensibility"></a>Extensibilidade

- **Funcionalidade estendida e rendemento mellorado para a exportación de SFTP** Agora pode exportar todas as entidades de saída desde Customer Insights a un servidor SFTP. Anteriormente, a exportación limitábase a entidades de segmento. Ademais, o rendemento da exportación SFTP permite máis volume de datos en menos tempo, dependendo do rendemento do seu servidor SFTP.    
  Para obter máis información, consulte [Conector para SFTP (versión preliminar)](export-sftp.md).  

#### <a name="segments"></a>Segmentos

- **Segmentos suxeridos con tecnoloxía de aprendizaxe automática para mellorar as métricas** Hai un novo xeito de descubrir e crear segmentos. O sistema usa un modelo IA para suxerir segmentos que poden axudar a mellorar un KPI (medida) que xa está seguindo. Amosamos a influencia dos atributos que selecciona nunha medida ou noutro atributo principal. Esta información axuda a atopar segmentos potenciais que presenten oportunidades.    
  Para obter máis información, consulte [Segmentos suxeridos (versión preliminar)](suggested-segments.md).

#### <a name="data-unification"></a>Unificación de datos

- **Experiencia de busca de coincidencias mellorada** Na área de unificación de datos, actualizouse a experiencia de busca de coincidencias. Permite configurar e ver as regras de coincidencia, incluídas estatísticas detalladas para explicar máis como funciona a coincidencia. Hai opcións para desactivar unha regra de coincidencia, polo que xa non está activa mentres conserva a configuración, arrastra e solta as regras de coincidencia e moito máis.
  Para obter máis información, consulte [Buscar coincidencias de entidades](match-entities.md).

- **A saída de duplicación do proceso de coincidencia está dispoñible como entidade** A saída do proceso de desduplicación do proceso de correspondencia agora escríbese nunha entidade separada para unha posterior análise. Esta entidade está composta polos campos utilizados no proceso de desduplicación e o rexistro gañador e os correspondentes rexistros alternativos que se combinan co rexistro gañador.
  Para obter máis información, consulte [Saída de desduplicación como entidade](match-entities.md#deduplication-output-as-an-entity).

#### <a name="system-administration"></a>Administración do sistema

- **Comparta datos sen problemas con Microsoft Dataverse** Agora pode compartir a saída de Customer Insights con aplicacións de Microsoft Dataverse que usan o Data Lake xestionado de Microsoft Dataverse. Unha vez asociado o ambiente de Dataverse a Customer Insights, ten a opción de habilitar o uso compartido de datos.
  Para obter máis información, consulte [Xestionar ambientes](manage-environments.md).




[!INCLUDE[footer-include](../includes/footer-banner.md)]