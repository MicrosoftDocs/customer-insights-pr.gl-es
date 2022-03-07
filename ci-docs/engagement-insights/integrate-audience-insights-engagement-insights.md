---
title: Crear unha ligazón entre a información do público e a información de interacción
description: Cree unha ligazón activa entre a información do público e a información de interacción para permitir o intercambio bidireccional de datos.
ms.date: 09/08/2021
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 56adc206d83bc6e34a55f11383393b5ac66da531
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 02/16/2022
ms.locfileid: "8229870"
---
# <a name="create-a-link-between-audience-insights-and-engagement-insights"></a>Crear unha ligazón entre a información do público e a información de interacción

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

A integración entre a información do público e a información de interacción liga os ambientes de ambas as capacidades e permite compartir datos bidireccionalmente entre elas.

Utilice segmentos e perfís unificados de información do público para obter máis opcións de análise na información de interacción. Exporte eventos que teñan un alto valor empresarial desde a información de interacción. Use estes eventos para engadir datos a perfís unificados na información do público.

## <a name="prerequisites"></a>Requisitos previos

- Os perfís de información sobre o público deben almacenarse nun Azure Data Lake Storage conta que posúe ou nunha [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro)&ndash; lago de datos xestionado. 
- O seu ambiente de información do público debería ter un ambiente de Dataverse asociado. E se ese ambiente tamén o está a usar Dataverse para almacenar datos, asegúrese de comprobar a opción **Activar o uso compartido de datos** na información do público. Para obter máis información, consulte [Crear e configurar un contorno en estatísticas de público](../audience-insights/create-environment.md).
- Necesita permisos de administrador para os ambientes de información do público e información de interacción.
- Os ambientes ligados deben estar na mesma rexión xeográfica.

> [!NOTE]
> - Se a subscrición á información do público é unha proba, que utiliza un lago de datos xestionado internamente de información do público, póñase en contacto con [pirequest@microsoft.com](mailto:pirequest@microsoft.com) para obter asistencia. 
> - Se o seu ambiente de información do público utiliza o seu Azure Data Lake Storage para almacenar datos, cómpre engadir unha entidade de servizo de Azure de información de interacción á súa conta de almacenamento. Para máis detalles, vaia a [Conectarse a unha conta de Azure Data Lake Storage cunha entidade de servizo de Azure para a información do público](../audience-insights/connect-service-principal.md). 


## <a name="create-an-environment-link"></a>Crear unha ligazón de ambiente

Pode crear unha ligazón de ambiente actualizando a configuración **Administrador** > **Ambiente** na información de interacción.

**Para establecer unha ligazón activa entre a información do público e a información de interacción**

1. Na páxina **Administrador de ambientes**, seleccione o separador **Ligar ambientes**.

    :::image type="content" source="media/integrate1.png" alt-text="Configurar un ambiente.":::

1. Seleccione **Configuración de ambientes** na esquina superior esquerda ou na parte inferior da pantalla.

     :::image type="content" source="media/integrate2.png" alt-text="Seleccionar un ambiente de información do público.":::

1. Seleccione un ambiente de información do público e, a continuación, seleccione ***Seguinte** para rematar. Agora pode seleccionar funcións opcionais para os ambientes ligados.
 
## <a name="enable-audience-insights-unified-profiles-attributes-and-segments"></a>Permitir segmentos e atributos de perfís unificados de información do público

Despois de ligar os ambientes, pode seleccionar funcións opcionais para os ambientes ligados. Estas funcións permiten atributos e segmentos de perfís unificados da información do público para a análise interactiva de datos de clientes.

> [!IMPORTANT]
> Para que os segmentos de información do público aparezan na información de interacción, primeiro debe [executar procesos descendentes e de combinación](../audience-insights/merge-entities.md). Os procesos descendentes son importantes porque xeran unha táboa única que prepara os segmentos de información do público para ser compartidos coa información de interacción. (Se está programada unha actualización do sistema, incluirá automaticamente os procesos descendentes).

**Para analizar datos web na información de interacción**

1. Na páxina **Administrador de ambientes**, active a opción **Compartir datos de información do público con información de interacción** e logo seleccione **Seguinte**.

    :::image type="content" source="media/integrate4.png" alt-text="Seleccionar funcionalidades.":::

1. Seleccione os atributos dos perfís unificados que se converterán en dimensións na información de interacción. (Non todos os atributos son dimensións útiles. Por exemplo, é probable que non precise **Nome** ou **Apelidos** como atributo para a análise dos eventos do seu sitio web).

    :::image type="content" source="media/integrate5.png" alt-text="Recompilar dimensións.":::

   >[!NOTE]
   > Todos os atributos dos perfís de información do público que representan identificadores (como **ID** e **ID alternativo**) fíltranse dos atributos dispoñibles e convértense en dimensións na información de interacción.

1. Cando remate de seleccionar os atributos, selecciona **Seguinte**.
1. Engada usuarios que poidan ver as dimensións e segmentos dos perfís de información do público na información de interacción.

    :::image type="content" source="media/integrate6.png" alt-text="Xestionar acceso aos datos de cliente.":::

   > [!IMPORTANT]
   > Se non engade usuarios de xeito explícito neste paso, os datos ocultaranse aos usuarios na información de interacción.
   > Para que os segmentos de información do público aparezan na información de interacción, primeiro debe [executar procesos descendentes e de combinación](../audience-insights/merge-entities.md). Os procesos descendentes son importantes porque xeran unha táboa única que prepara os segmentos de información do público para ser compartidos coa información de interacción. (Se está programada unha actualización do sistema, incluirá automaticamente os procesos descendentes).

1. Revise a selección e logo seleccione **Rematar**.

    :::image type="content" source="media/integrate7.png" alt-text="Revisar a configuración dos datos do cliente.":::

## <a name="export-refined-events-to-audience-insights"></a>Exportar eventos refinados á información do público

Despois de crear unha ligazón entre ambientes, pode exportar eventos refinados da información de interacción á información do público e inxerilos como unha nova orixe de datos. 

Para obter máis información, vaia a [Integrar os datos web da información de interacción coa información do público](../audience-insights/integrate-engagement-insights.md).

<!--
## Share engagement insights refined events with audience insights

After you create a link between environments, a new option becomes available for you to share [refined events](refined-events.md) with audience insights.

Consider the following when creating refined events for audience insights: 

- Provide a meaningful name for the refined event. It will be used as an activity name in audience insights.
- Select at least the following properties to create an activity in audience insights: 
    - Signal.Action.Name indicates the activity details.
    - Signal.User.Id maps with the customer ID.
    - Signal.View.Uri is a web address as a basis for segments or measures.
    - Signal.Export.Id is a primary key for events.
    - Signal.Timestamp determines the date and time for the activity.

To share refined events:

1. From the engagement insights menu, select **Data** and then select the **Events** tab.
2. On the **Action** menu, select **Share as activity**.

    :::image type="content" source="media/integrate8.png" alt-text="Data shared events settings.":::

3. You can view and stop actively shared events on the **Export and Sharing** tab.
4. -- per Michael K, we need a mock here (Mukesh needs to update to reflect what happens in AUI once a user shares a refined event (i.e. no longer AUI, data wrangler needs to go discover data in the storage, the shared event is available as a DS and entity, correct?)

### Attach refined events shared as activities to unified profiles in audience insights

You can bring customer web activity data from engagement insights into audience insights. In addition to transactional, demographic, or behavioral data, you can view activities on the web in unified customer profiles. You can then use these profiles to get insights such as segments, measures, and predictions for audience activation.

Follow the steps in [data unification](../audience-insights/data-unification.md) to map, match, and merge website authentication information to unified profiles in audience insights.

You can also share refined events that are now available in audience insights, identified as data sources and entities. 

Next, you can relate event data from engagement insights as unified activities in customer profiles.

### Relate refined event data as an activity of a customer profile

After unifying the data, you can configure the activity for the customer profile. For more information, go to [Customer activities](../audience-insights/activities.md).

:::image type="content" source="media/web-event-activity.png" alt-text="Activities page with expanded Edit activity pane.":::

Next, configure the new activity by using mapping elements: 

- **Primary Key**: Signal.Export.Id, a unique ID that is available for every event record in engagement insights. This property is automatically generated.

- **Timestamp**: Signal.Timestamp in the event property.

- **Event**: Signal.Name, the event name that you want to track.

- **Web address**: Signal.View.Uri that refers to the URI of the page that created the event.

- **Details**: Signal.Action.Name to represent the information to associate with the event. The selected property in this case indicates that the event is for email promotion.

- **Activity type**: In this example, we choose the existing activity type WebLog. This selection is a useful filter option to run prediction models or create segments based on this activity type.

- **Set up relationship**: This important setting ties the activity to existing customer profiles. **Signal.User.Id** is the identifier configured in the SDK to be collected. It relates to the user ID in other data sources that are configured in audience insights. 

This example configures the relationship between Signal.User.Id and RetailCustomers:CustomerRetailId, which is the primary key that was identified in the map step of the data unification process.

After processing the activities, you can review customer records and open a customer card to see activities from engagement insights in the timeline. 

> [!TIP]
> To find a customer ID that has an engagement insights activity, go to **Entities** and preview the data for the UnifiedActivity entity. **ActivityTypeDisplay = WebLog** contains the engagement insights activity configured in the preceding example. Copy the customer ID for one of those records and search<!--note from editor: Edit okay? I couldn't quite follow this.-- > for that ID on the **Customers** page.

--> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
