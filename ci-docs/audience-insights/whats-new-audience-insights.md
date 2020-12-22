---
title: Funcionalidades novas e futuras
description: Información sobre novas funcións, melloras e corrección de erros.
ms.date: 11/02/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: midevane
manager: shellyha
ms.openlocfilehash: 07b4bee0445f9cd7d53a37cd405af839feb07ae3
ms.sourcegitcommit: 4004eadac7a65e50e0a409cb925958523c2b6348
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 11/30/2020
ms.locfileid: "4650002"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a>Novidades na capacidade de información do público de Dynamics 365 Customer Insights

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Comprácenos anunciar as nosas últimas actualizacións! Este artigo resume as funcionalidades de previsualización pública, as melloras de dispoñibilidade xeral e as actualizacións de funcións. Para ver os plans de funcionalidades a longo prazo, vexa os [plans de versións de Dynamics 365 e Power Platform](https://docs.microsoft.com/dynamics365/release-plans/).

Tamén pode ver o seguinte vídeo para obter máis información sobre as capacidades previstas nos últimos seis meses.

> [!VIDEO https://www.youtube.com/embed/jQh-7pscH30]

Lanzamos as actualizacións rexión por rexión. Así, certas rexións poden ver as funcionalidades antes que outras. A menos que se especifique o contrario, non é necesario que realice ningunha acción e actualizaremos a aplicación automaticamente sen tempo de inactividade.

> [!TIP]
> Para enviar e votar solicitudes de funcionalidades e suxestións de produtos, vaia ao [Portal de ideas da aplicación Dynamics 365](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).

## <a name="november-2020-updates"></a>Actualizacións de novembro de 2020

As actualizacións de novembro de 2020 inclúen varias funcións, actualizacións de rendemento e correccións de erros.

### <a name="new-and-updated-features-in-november-2020"></a>Funcións novas e actualizadas en novembro de 2020

#### <a name="data-enrichment"></a>Enriquecemento de información

- **Traia os seus propios datos de enriquecemento a través da importación personalizada co protocolo de transferencia de ficheiros segura (SFTP)**
  
  A importación personalizada SFTP permítelle importar datos de enriquecemento que non teñen que pasar polo proceso de unificación de datos. Máis información acerca da importación personalizada SFTP.

  Para obter máis información, consulte [Enriquecer os perfís de clientes con datos personalizados (vista previa)](enrichment-SFTP-custom-import.md).
 
- **Enriquece os seus datos de clientes con datos de localización de HERE Technologies**

  Cos servizos de enriquecemento de datos de HERE Technologies, pode construír unha comprensión máis precisa da situación dos seus clientes coa normalización de enderezos, a extracción de latitude e lonxitude e moito máis. Obteña máis información sobre o enriquecemento con HERE Technologies.

  Para obter máis información, consulte [Enriquecer perfís de clientes con HERE Technologies](enrichment-here.md).

#### <a name="data-unification"></a>Unificación de datos

- **Flexibilidade para habilitar a creación de perfís de datos en entidades e campos seleccionados da súa conta de almacenamento**

  Pode indicar que entidades de datos e campos dunha carpeta de Common Data Model na súa conta de almacenamento de Azure Data Lake desexa habilitar a creación de perfís de datos como parte do proceso de inxestión de datos.

  Para obter máis información, consulte [Conectarse a un cartafol de Common Data Model](connect-common-data-model.md#connect-to-a-common-data-model-folder).

#### <a name="extensibility"></a>Extensibilidade

- **Activar os seus segmentos a través de Google Ads**

  Exporte segmentos desde a listas de público de Google Ads e utilíceas para anunciarse na Busca de Google, na Rede de Display de Google, YouTube e Gmail. Obteña máis información sobre como activar os seus segmentos a través de Google Ads.

  Para obter máis información, consulte [Conector para Google Ads](export-google-ads.md).

- **Activar os seus segmentos a través de Marketo**

  Exporte segmentos a públicos de Marketo e utilice estes públicos para a automatización de márketing. Obteña máis información sobre como activar os seus segmentos a través de Marketo. 

  Para obter máis información, consulte [Conector para Marketo](export-marketo.md).

- **Activar os seus segmentos a través de DotDigital**

  Exporte segmentos a DotDigital e utilíceos para fins de márketing. Obteña máis información sobre como activar os seus segmentos a través de DotDigital. 

  Para obter máis información, consulte [Conector para DotDigital](export-dotdigital.md).

#### <a name="predictions"></a>Predicións

- **Predicir o abandono transaccional**

  A función de predición do abandono de transaccións permítelle, sen a axuda dun científico de datos, predicir a probabilidade de que un cliente deixe de mercar produtos ou servizos.  Usando a puntuación da predición, pode combinar outra información sobre os seus clientes, como o valor do cliente, para crear segmentos de clientes con alto risco de abandono ou clientes de alto valor. Utilice este segmento para dirixirse directamente aos clientes a través de actividades de mercadotecnia, asistencia ao cliente e outros escenarios para reducir o risco de abandono.
 
  Configure a definición de abandono como unha fiestra baseada no tempo específica para a súa empresa e defina cando se considera que os clientes abandonaron. Por exemplo, unha tenda de comestibles pode querer considerar que un cliente abandonou se non comprou nada nos últimos 30 días.
 
  Mentres sigue creando a predición, indicarémoslle que datos son necesarios e permitirémoslle asignar datos sobre a súa empresa aos campos necesarios para predicir o abandono dos seus clientes. Tamén pode establecer unha programación para readestrar o modelo en función da nova información do seu sistema para adaptarse ás circunstancias comerciais cambiantes.
 
  Para obter máis información, consulte [Predición de abandono transaccional (vista previa)](predict-transactional-churn.md).

#### <a name="system-administration"></a>Administración do sistema

- **Restablecer o ambiente**

  Restableza todo nun contorno dunha instancia seleccionada para comezar de novo.

  Para obter máis información, consulte [Restablecer un ambiente existente](manage-environments.md#reset-an-existing-environment).


- **Conectarse á súa conta de almacenamento de Azure Data Lake usando unha entidade principal de seguranza do servizo**

  Escriba a saída de datos e lea os datos da súa conta de almacenamento usando unha entidade principal de seguranza do servizo de Azure. As conexións da conta de almacenamento existentes poden seguir usando a clave da conta. Tamén ofrecen unha opción de actualización para usar a entidade principal de seguranza do servizo. As novas conexións basearanse no método de autenticación da entidade principal de seguranza do servizo para a súa conta de almacenamento.

  Para obter máis información, consulte [Conectarse a unha conta de Azure Data Lake Storage Gen2 cunha entidade principal de seguranza do servizo de Azure para obter información sobre o público](connect-service-principal.md).

## <a name="october-2020-updates"></a>Actualizacións de octubre de 2020

As actualizacións de outubro de 2020 inclúen varias funcións, actualizacións de rendemento e correccións de erros.

### <a name="new-and-updated-features-in-october-2020"></a>Funcións novas e actualizadas en outubro de 2020

#### <a name="extensibility"></a>Extensibilidade

- **Exportar a MailChimp**

Exporte segmentos a listas de audiencia existentes en Mailchimp para proporcionar unha experiencia de correo electrónico personalizada aos seus clientes.

Para obter máis información, consulte [Conector para Mailchimp](export-mailchimp.md).

#### <a name="data-enrichment"></a>Enriquecemento de información

- **Desduplicar os rexistros fonte nunha entidade de coincidencia**

Especifique regras de desduplicación nas entidades utilizadas no proceso de busca de coincidencias para identificar rexistros duplicados. Combíneos nun rexistro e vincule todos os rexistros de orixe con este rexistro combinado. Este rexistro desduplicado utilizarase entón no proceso de busca de coincidencias entre entidades.

Para obter máis información, consulte [Definir a desduplicación nunha entidade de coincidencia](match-entities.md#define-deduplication-on-a-match-entity).

#### <a name="system-administration"></a>Administración do sistema

- **Orquestación: nova opción de actualización en Combinar**

Ata hoxe, cando executaba o proceso de combinación, o sistema executaba todos os procesos descendentes que dependen da combinación e os procesos posteriores. Agora pode verificar a saída do proceso de combinación (a entidade de cliente unificada) antes de usala no procesamento descendente como segmentos ou medidas.
Na páxina de combinación, agora pode optar por executar só o paso de combinación e executar só este proceso. Para actualizar tamén todos os procesos descendentes, pode escoller executar procesos de combinación e descendentes. 

## <a name="september-2020-updates"></a>Actualizacións de setembro de 2020

As actualizacións de setembro de 2020 inclúen varias funcionalidades, actualizacións de rendemento e correccións de erros.

### <a name="new-and-updated-features-in-september-2020"></a>Funcionalidades novas e actualizadas en setembro de 2020

#### <a name="activities"></a>Actividades

- **Predición intelixente de semántica de atributos**

Esta nova funcionalidade predice os tipos semánticos de atributos de entrada que se transmiten ao proceso de unificación de datos. Usa modelos de aprendizaxe automática que melloran a precisión e aforran tempo.

#### <a name="enrichments"></a>Enriquecementos

- **Enriquecemento de datos demográficos de Experian**

O enriquecemento de datos demográficos de Experian xa está dispoñible en previsualización. Experian é líder mundial en servizos de márketing e informes de crédito para consumidores e empresas. Cos [servizos de enriquecemento de datos de Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage), pode adquirir unha comprensión máis profunda dos seus clientes enriquecendo os perfís dos seus clientes con datos demográficos como o tamaño do fogar, os ingresos e moito máis.

Para usar esta función, debes ter unha subscrición a Experian activa.

Para obter máis información, consulte [Enriquecer os perfís de clientes con datos demográficos de Experian](enrichment-experian.md)


#### <a name="system-administration"></a>Administración do sistema

- **Panel de detalles de tarefas**

O panel de detalles de tarefas permítelle ver detalles sobre as tarefas que executa o sistema. É un xeito práctico de identificar problemas coa configuración e atopar solucións.
Revise as mensaxes de erro para ver como aborda posibles problemas.
 
- **Información de procesamento engadida a páxinas adicionais**

Esta mellora engade información sobre o estado das súas entidades na páxina **Entidades** e **Clientes**.
 
Ademais, pode atopar detalles sobre o progreso dos procesos, xunto cos detalles da tarefa, en ambas as páxinas.

- **Melloras na páxina de estado do sistema**

Melloramos a estrutura da táboa de detalles do estado en **Sistema** > **Estado** ao revisar as exportacións de datos.
 
Ademais, os erros na columna **Detalles** agora son máis detallados e procesables. 
 
- **Cancelar devolve o traballo ao estado anterior**

Cando cancela unha tarefa, por exemplo, no proceso de coincidencia, volverá ao seu último estado. Por exemplo, se o proceso coincidencia finalizou onte e o cancela hoxe, volverá ao estado correcto de onte.


## <a name="august-2020-updates"></a>Actualizacións de agosto de 2020

As actualizacións de agosto de 2020 inclúen varias funcionalidades, actualizacións de rendemento e correccións de erros.

### <a name="new-and-updated-features-in-august-2020"></a>Funcionalidades novas e actualizadas en agosto de 2020

#### <a name="data-unification"></a>Unificación de datos

- **Experiencia mellorada para a etapa do mapa durante a unificación de datos**

  A experiencia na etapa do mapa no proceso de unificación de datos permítelle seleccionar entidades, atributos e definir a semántica dun xeito máis sinxelo.

  As modificacións inclúen:
  
  - menos interaccións necesarias para engadir entidades e campos
  - melloraron as capacidades de busca na páxina do mapa
  - identificación visual e sinxela do tipo de campo suxerido

#### <a name="enrichment"></a>Enriquecemento

- **Enriquecemento de afinidades de interese dispoñible en mercados adicionais**

  Estendemos a dispoñibilidade do enriquecemento de afinidades de interese máis alá dos Estados Unidos a cinco mercados adicionais: Canadá, Australia, Reino Unido, Francia e Alemaña. Con esta extensión, pode enriquecer os seus datos de clientes con intereses adicionais aplicables a estes mercados. Tamén enriqueremos os seus perfís de clientes que se atopan nestes mercados utilizando datos propietarios locais de Microsoft Graph.
  Para obter máis información, consulte [Enriquecer os perfís de clientes con afinidades de marca e intereses](enrichment-microsoft-graph.md)


## <a name="july-2020-updates"></a>Actualizacións de xullo de 2020

As actualizacións de xullo de 2020 inclúen varias características, actualizacións de rendemento e correccións de erros.

### <a name="new-and-updated-features-in-july-2020"></a>Funcións novas e actualizadas en xullo de 2020

#### <a name="extensibility"></a>Extensibilidade

- **Desencadeador de Power Automate para o proceso de unificación rematado**

  Ampliamos os nosos desencadeadores para Power Automate e permítenlle crear unha notificación ou acción cando se complete unha actualización do proceso de unificación (asignación, coincidencia, combinación).    
  Para obter máis información, consulte [Conector de Power Automate](export-power-automate.md)

#### <a name="enrichment"></a>Enriquecemento

- **Enriquecemento de afinidades de marca dispoñible en mercados adicionais**

  Estendemos a dispoñibilidade do enriquecemento das afinidades da marca máis alá dos Estados Unidos a cinco mercados adicionais: Canadá, Australia, Reino Unido, Francia e Alemaña. Con esta extensión, pode enriquecer os seus datos de clientes con marcas locais nestes mercados. Tamén enriqueremos os seus perfís de clientes que se atopan nestes mercados utilizando datos propietarios locais de Microsoft Graph.
  Para obter máis información, consulte [Enriquecer os perfís de clientes con afinidades de marca e intereses](enrichment-microsoft-graph.md)

## <a name="june-2020-updates"></a>Actualizacións de xuño de 2020

As actualizacións de xuño de 2020 inclúen varias características, actualizacións de rendemento e correccións de erros.

### <a name="new-and-updated-features-in-june-2020"></a>Funcións novas e actualizadas en xuño de 2020

#### <a name="enrichment"></a>Enriquecemento

- **Enriquecemento con datos da compañía de Leadspace**
  
  Defina campos nos perfís de clientes unificados que se empregan para buscar datos relacionados coa empresa de Leadspace. Despois de executar o proceso de enriquecemento, os perfís B2B enriquécense con atributos adicionais, incluído o tamaño da empresa, a localización, a industria e moito máis.    
  Esta colaboración permítelle mellorar a calidade dos seus datos coa entrada de servizos de terceiros. Para usar este enriquecemento, necesitará unha licenza de Leadspace para acceder aos seus datos de compañía B2B. O sistema utilizará esa licenza para manter os seus datos enriquecidos continuamente.    
  Para obter máis información, consulte [Enriquecemento de perfís de empresas con Leadspace](enrichment-leadspace.md).

- **Páxina da plataforma común de enriquecemento**

  Todos os enriquecementos de datos dispoñibles dos provedores de enriquecemento de primeiras e terceiras partes configúranse no mesmo lugar. A configuración do enriquecemento de datos é unha experiencia fluída que se xestiona desde un lugar común.    
  Para obter máis información, consulte [Enriquecemento dos perfís de clientes](enrichment-hub.md).

- **Enriquecemento de afinidade de marca e interese por separado**

  As afinidades de marcas e intereses están dispoñibles agora como dous enriquecementos independentes. Os enriquecementos separados proporcionan flexibilidade para configuralos e xestionalos individualmente, segundo os seus requirimentos ou necesidades empresariais.    
  Para obter máis información, consulte [Enriquecer os perfís de clientes con afinidades de marca e intereses](enrichment-microsoft-graph.md).

#### <a name="extensibility"></a>Extensibilidade

- **URL clicables para actividades unificadas no complemento de tarxeta de cliente de Dynamics 365**

  As actividades unificadas no complemento de tarxeta de cliente agora amosan URL que se poden premer se se definiron durante a configuración das actividades.    
  Para obter máis información, consulte [Complemento de tarxeta de cliente](customer-card-add-in.md).

- **Afinidades de marca e intereses dispoñibles no complemento de tarxeta de cliente de Dynamics 365**

  Un novo control do complemento de tarxeta de cliente de Dynamics 365 permítelle mostrar enriquecementos de marca e intereses nos seus contactos en aplicacións de interacción cos clientes de Dynamics 365.    
  Para obter máis información, consulte [Complemento de tarxeta de cliente](customer-card-add-in.md).

- **Desencadeadores de Power Automate adicionais**

  Ampliamos os nosos desencadeadores para Power Automate e engadimos os seguintes desencadeadores:
  - Reciba unha notificación ou realice unha acción cando se complete unha actualización automatizada (fontes de datos, unificación, segmentos, medidas, exportacións)
  - Defina un limiar para unha medida empresarial. Por exemplo, pode crear unha notificación que se envía cando se pasa o limiar definido. Ademais, o disparador trae información que lle permite crear fluxos de traballo máis complexos en Power Automate.    
  Para obter máis información, consulte [Conector de Power Automate](export-power-automate.md)

- **Exportar ao Xestor de anuncios de Facebook**
  
  Esta capacidade permítelle exportar segmentos ao Xestor de anuncios de Facebook. Os segmentos expórtanse como públicos personalizados para usar perfís de clientes unificados en campañas e anuncios de mercadotecnia de Facebook. Os públicos personalizados tamén se poden usar para crear campañas en Instagram a través do Xestor de anuncios de Facebook.    
  Para obter máis información, consulte [Conector para o Xestor de anuncios de Facebook](export-facebook.md).

#### <a name="predictions"></a>Predicións

- **Predición de abandono de subscricións**

  Siga unha experiencia guiada para crear unha predición de abandono en áreas de subscrición como servizos na nube, afiliación de clientes e outros sectores. 

  A función de predición de abandono de subscricións permite predicir a probabilidade de que un cliente deixe de usar produtos ou servizos baseados nunha subscrición sen involucrar a un científico de datos. Usando a puntuación de predición, pode combinar outra información sobre os seus clientes para crear segmentos de alto risco de abandono. Coa axuda deste segmento, pode dirixirse directamente a clientes en mercadotecnia, atención ao cliente e outros escenarios para reducir o risco de abandono de clientes específicos para mellorar os ingresos e reducir os custos.

  Dentro da experiencia, pode configurar a definición de abandono como unha xanela baseada no tempo específica para a súa empresa. Por exemplo, un negocio de retransmisión de vídeos que ten un proceso de subscrición mensual quizais queira considerar que un cliente abandonou aos 15 días da caducidade da súa subscrición.

  Mentres continúa a través de predición, guíarémolo polos datos que se precisan e permitiremos asignar datos sobre a súa empresa aos campos necesarios para predecir un abandono para os seus clientes. A medida que a información empresarial cambia, tamén pode configurar unha programación para volver adestrar con información nova no seu sistema para adaptarse ás circunstancias empresariais cambiantes.    
  Para obter máis información, consulte [Predición de abandono de subscricións (vista previa)](predict-subscription-churn.md).

#### <a name="segments"></a>Segmentos

- **Buscar clientes semellantes**
  
  Busque clientes similares na súa base de clientes mediante intelixencia artificial. Un modelo de aprendizaxe automática de clasificación binaria asigna unha puntuación de semellanza aos clientes do segmento expandido. A puntuación baséase na semellanza con clientes do segmento de orixe. Dependendo da puntuación de semellanza, engádense perfís de clientes a un segmento de nova creación.

  Ás veces chamado modelo de similitude en mercadotecnia dixital, usa un modelo de IA para axudar a atopar clientes semellantes a outro segmento dos seus clientes mediante a factorización de atributos adicionais. Non só permite escoller os atributos, senón que tamén permite especificar o número máximo de clientes que deberían estar neste novo segmento. O modelo de IA computará entón puntuacións de semellanza para cada cliente en función dos atributos seleccionados e atopará clientes con puntuación de semellanza media máis alta. O segmento resultante incluirá clientes que se parezan ao cliente no seu segmento orixinal.    
  Para obter máis información consulte, [Clientes similares](find-similar-customer-segments.md).

- **Superposición e diferenciadores dos segmentos**

  A superposición de segmentos permítelle ver cantos e que clientes son comúns a dous ou máis segmentos. Por exemplo, como un segmento de maiores gastadores se solapa cun segmento de clientes con alta satisfacción ou como un segmento de clientes que abandonaron se superpón cun segmento de clientes con pouca satisfacción. Ademais, pode analizar como cambia a superposición en función dun atributo adicional que elixise.

  Os diferenciadores de segmentos revelan o que diferencia un segmento do resto dos seus clientes ou doutro segmento. Todo o que cómpre facer é identificar un segmento e o sistema identificará os atributos e medidas do perfil que distinguen o segmento en forma de lista clasificada de diferenciadores: do diferenciador máis forte ao máis débil.    
  [Para obter información, consulte Información de segmentos (previsualización)](segment-insights.md).

- **Vida do segmento**
  
  Defina unha programación para activar ou desactivar un segmento.    
  Para obter máis información, consulte [Xestionar segmentos existentes](segments.md#manage-existing-segments).

## <a name="may-2020-updates"></a>Actualizacións de maio de 2020

As actualizacións de maio de 2020 inclúen varias funcionalidades, actualizacións de rendemento e correccións de erros.

### <a name="new-and-updated-features-in-may-2020"></a>Funcións novas e actualizadas en maio de 2020

#### <a name="data-ingestion"></a>Inxestión de datos

- **Inxestión de datos en tempo real: vistas do historial**

  Ao usar a nosa API para inxerir actualizacións en tempo real, pode ver ata 30 días de historial agregado destas actualizacións. Ten acceso aos datos agregados de todas as chamadas da API exitosas ou fallidas, incluído o resultado, o sistema fonte e outros metadatos útiles.    
  Para obter máis información, consulte [Incorporación de datos en tempo real](real-time-data-ingestion.md).

- **Inxestión de datos en tempo real: actualizacións de perfil**

  Esta extensión da inxestión de datos en tempo real permítelle ver, en segundos, cambios en campos do perfil de usuario específicos.    
  Ademais da funcionalidade en tempo real das actividades, o sistema admite actualizacións de baixa latencia nos campos do perfil. As actualizacións en tempo real dos campos de perfil teñen un tempo de caducidade e, polo tanto, non son un substituto para as actualizacións programadas.    
  Para obter máis información, consulte [Incorporación de datos en tempo real](real-time-data-ingestion.md).

#### <a name="extensibility"></a>Extensibilidade

- **Cronoloxía e paxinación actualizadas no complemento de tarxeta de cliente**

  A cronoloxía da solución de complemento de tarxeta de cliente coincide coa cronoloxía da actividade. A paxinación da liña de tempo mellorouse, e agora mostra ata 50 actividades á vez. Tamén permite cargar actividades adicionais na liña de tempo.    
  Para obter máis información, consulte [Complemento de tarxeta de cliente](customer-card-add-in.md).

- **Desencadeador de Power Automate para cambios de segmento**

  Os desencadeadores de Power Automate definen os elementos desde os que pode crear un fluxo. O desencadeador engadido recentemente permítelle definir un limiar para un segmento. Por exemplo, pode crear unha notificación que se envía cando se pasa o limiar definido.    
  Para obter máis información, consulte [Conector de Power Automate](export-power-automate.md).

- **Soporte multiempresa para modelos personalizados**

  Configure fluxos de traballo para modelos personalizados cun servizo web dun arrendatario de Azure Machine Learning diferente. Pode iniciar sesión no inquilino de Azure Machine Learning ao crear un novo fluxo de traballo para modelos personalizados. Esta capacidade é un complemento á capacidade existente para integrarse co seu propio servizo web personalizado de Azure Machine Learning.    
  Para obter máis información, consulte [Modelos de aprendizaxe automática personalizados](custom-models.md).

#### <a name="segments"></a>Segmentos

- **Automatización de rutas da entidade**

  Ao crear un segmento, os usuarios precisan definir o camiño da entidade. Esta capacidade dá un primeiro paso na automatización da definición do camiño da entidade para que poida centrarse nos criterios de segmentación que teña en mente.    
  Se a entidade pola que desexa segmentar os seus clientes está directamente relacionada coa entidade de cliente unificada, xa non necesitará definir a ruta da entidade. Non obstante, se hai máis dunha posible ruta da entidade, aínda deberá definila manualmente.

- **Accións en varios segmentos**
  
  Os usuarios poden seleccionar varios segmentos e realizar accións sobre eles, como actualizar os segmentos cun só clic.    

- **Actualizar os segmentos**

  Os usuarios poden actualizar un único segmento ou seleccionar só os segmentos que desexan actualizar.    

  
- **Melloras dos segmentos compostos**

  Os usuarios poden crear, editar e eliminar segmentos baseados noutros segmentos. Por exemplo, un segmento construído sobre outro segmento que foi construído sobre un terceiro segmento.    

- **Páxina de lista de segmentos**

  O novo deseño da páxina de segmentos usa un formato de lista que lle permite ver máis segmentos á vez. Engádese un campo de busca para atopar segmentos rapidamente. Os usuarios agora poden aplicar accións como descargar ou eliminar en varios segmentos á vez. Introdúcese unha nova experiencia de tendencia para identificar rapidamente cambios significativos nos segmentos.    
  Para ver máis información, consulte: [Creación e xestión de segmentos](segments.md).

#### <a name="system-administration"></a>Administración do sistema

- **Customer Insights dispoñible en Microsoft Dynamics 365 Online Government**

  Con cada vez máis canles para interaccións, os datos dos cidadáns espállanse por numerosos sistemas, o que conleva datos separados en silos e unha vista fragmentada da información sobre as interaccións dos cidadáns. Sen unha visión completa das interaccións de cada cidadán a través das canles é imposible que os gobernos se modernicen a escala. Microsoft comprometeuse a apoiar as necesidades tecnolóxicas da administración pública para estar á altura das expectativas dos cidadáns en canto a experiencias coherentes e con capacidade de resposta.    
  Coa onda 1 do lanzamento de 2020, Dynamics 365 Customer Insights estará dispoñible para Government Community Cloud (GCC), un ambiente construído para satisfacer as necesidades de maior cumprimento das axencias gobernamentais dos Estados Unidos. As axencias obteñen unha visión unificada dos cidadáns e usan IA preconstruída para obter información que mellore as interaccións, capacite aos empregados e transforme as comunidades, ao tempo que reducen a complexidade das TI e cumpren cos estándares de seguridade e cumprimento dos Estados Unidos. Dynamics 365 Government cumpre os requisitos esixentes do Programa Federal de Xestión de Riscos e Autorizacións (FedRAMP) dos Estados Unidos, permitindo ás axencias federais dos Estados Unidos beneficiarse do aforro de custos e da seguridade rigorosa de Microsoft Cloud.

## <a name="april-2020-updates"></a>Actualizacións de abril de 2020

As actualizacións de abril de 2020 inclúen varias funcionalidades, actualizacións de rendemento e correccións de erros.

### <a name="new-and-updated-features-in-april-2020"></a>Funcións novas e actualizadas en abril de 2020

#### <a name="activities"></a>Actividades

- **Asignar a entidade de actividade ao tipo de actividade estándar**
  
  A configuración e o almacenamento de actividades están baseados actualmente nun deseño estático para visualizalos nunha liña de tempo. O significado semántico das actividades, que ten potencial para múltiples casos de uso nos modelos de IA, non se utiliza plenamente neste momento. Planificamos facer a liña de tempo de actividades máis dinámica, en función do tipo de actividade e unha mellor comprensión semántica das actividades. Esta funcionalidade pretende identificar o tipo de actividade tal e como se define no modelo de datos comúns de calquera actividade inxerida.
  Para obter máis información, consulte [Actividades do cliente](activities.md).

#### <a name="data-ingestion"></a>Inxestión de datos

- **Inxestión de datos en tempo real: actividades**
  
  A inxestión de datos en tempo real proporciona datos inmediatamente para o consumo, ata que a actualización programada posterior extrae estes datos da orixe de datos.    
  Para obter máis información, consulte [Incorporación de datos en tempo real](real-time-data-ingestion.md).

- **Melloras na preparación de datos**
  
  Máis información sobre os datos inxeridos nunha entidade. Co resumo de datos, pode comprender as características de calidade dos datos que poden axudar a tomar as medidas adecuadas.    
  Para obter máis información, consulte [Explorar os datos da entidade](entities.md#exploring-a-specific-entitys-data).

- **Inxerir datos analíticos de Dynamics 365 con Common Data Service**
  
  Common Data Service está dispoñible como forma de crear fontes de datos. Os clientes de Dynamics 365 existentes poden inxerir entidades analíticas de Common Data Service a Customer Insights. Unha única orixe de datos pode usar ao mesmo tempo o mesmo lago administrado de Common Data Service nun ambiente de Customer Insights.    
  Para obter máis información, consulte [Conectarse aos datos nun lago de datos xestionado de Common Data Service](connect-common-data-service-lake.md).

#### <a name="extensibility"></a>Extensibilidade

- **Exportar a LiveRamp**

  Active os seus datos en LiveRamp® para conectarse con máis de 500 plataformas en ecosistemas dixitais, sociais e de televisión. Aproveite os seus datos en LiveRamp para orientar, suprimir e personalizar campañas publicitarias.    
  Para obter máis información, consulte [Conector de LiveRamp&reg;](export-liveramp.md).

- **Complemento de Teams de Customer Insights**
  
  O bot ofrece capacidades de busca para perfís de clientes unificados. Amosará unha tarxeta con ata 15 campos do perfil de cliente resultante. As coincidencias múltiples devolven unha lista de resultados onde pode seleccionar un perfil.    
  Para obter máis información, consulte [Bot de Teams para Customer Insights](export-teams-bot.md).

#### <a name="measures"></a>Medidas

- **Páxina de lista de medidas**
  
  As melloras na páxina de medidas inclúen soporte para accións nunha soa medida e sobre varias medidas á vez. Ademais, atopará un campo de busca para buscar e rastrexar medidas rapidamente.    
  Para ver máis información, consulte: [Creación e xestión de segmentos](segments.md).

- **Melloras das medidas compostas**
  
  Os usuarios poden crear, editar e eliminar medidas baseadas noutras medidas. Por exemplo, unha medida construída sobre outra medida que foi construída sobre unha terceira medida.

#### <a name="segments"></a>Segmentos

- **Operador adicional**
  
  O operador de conxunto permite a segmentación de clientes por varios valores posibles de cadea. Antes de engadir este operador, tivo que construír estes segmentos con múltiples condicións de tipo OU. O operador de conxunto permítelle facelo cunha única condición.    
  Para ver máis información, consulte: [Creación e xestión de segmentos](segments.md).

#### <a name="system-administration"></a>Administración do sistema

- **Copiar as opcións de configuración nun novo ambiente**
  
  Copie a súa configuración dun ambiente a outro. Mentres se crea un novo ambiente, pode seleccionar un ambiente existente desde o que desexa copiar a configuración. Actualmente admitimos fontes de datos, unificación de datos, relacións, medidas e segmentos para copiar. Non se copian as credenciais de orixe de datos nin os datos reais.    
  Para obter máis información, consulte [Xestionar ambientes](manage-environments.md).
