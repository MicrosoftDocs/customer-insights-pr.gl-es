---
title: Exportar datos de Customer Insights á plataforma Adobe Experience
description: Aprenda a usar segmentos de información do público en Adobe Experience Platform.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 1045d0e373fd5ea8987684e51bd9a07b7b535ee3
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305522"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a>Utilice segmentos de Customer Insights na Adobe Experience Platform (versión preliminar)

Como usuario de información de audiencia en Dynamics 365 Customer Insights é posible que crease segmentos para facer máis eficientes as súas campañas de mercadotecnia dirixíndose a públicos relevantes. Para usar un segmento de información de audiencia en Adobe Experience Platform e aplicacións como Adobe Campaign Standard, cómpre seguir algúns pasos descritos neste artigo.

:::image type="content" source="media/AEP-flow.png" alt-text="Diagrama de proceso dos pasos descritos neste artigo.":::

## <a name="prerequisites"></a>Requisitos previos

-   LIcenza de Dynamics 365 Customer Insights
-   Licenza de Adobe Experience Platform
-   Licenza de Adobe Campaign Standard
-   Conta de Azure Blob Storage

## <a name="campaign-overview"></a>Visión xeral da campaña

Para comprender mellor como pode usar segmentos de información do público en Adobe Experience Platform, vexamos unha mostra de campaña ficticia.

Supoñamos que a súa empresa ofrece un servizo mensual baseado na subscrición aos seus clientes nos Estados Unidos. Identifique os clientes cuxas subscricións deben renovarse nos próximos oito días pero aínda non renovaron a súa subscrición. Para manter estes clientes, pode enviarlles unha oferta promocional por correo electrónico mediante a Adobe Experience Platform.

Neste exemplo, debemos executar a campaña de correo electrónico promocional unha vez. Este artigo non cubre o caso de uso de realizar a campaña máis dunha vez.

## <a name="identify-your-target-audience"></a>Identificar o seu público obxectivo

No noso escenario, supoñemos que os enderezos de correo electrónico dos clientes están dispoñibles en información de audiencia e as súas preferencias promocionais analizáronse para identificar os membros do segmento.

O [segmento que definiu nas estatísticas do público](segments.md) chámase **ChurnProneCustomers** e planea enviar a estes clientes a promoción por correo electrónico.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Captura de pantalla da páxina de segmentos co segmento ChurnProneCustomers creado.":::

O correo electrónico de oferta que desexa enviar conterá o nome, apelidos e a data de finalización da subscrición do cliente. Informa aos clientes sobre o desconto que obterán se renovan a subscrición antes de que remate.

## <a name="export-your-target-audience"></a>Exportar o seu público obxectivo

Co noso público obxectivo identificado, podemos configurar a exportación desde a información de audiencia a unha conta de Azure Blob Storage.

### <a name="configure-a-connection"></a>Configurar unha conexión

1. Vaia a **Administrar** > **Conexións**.

1. Seleccione **Engadir conexión** e elixa **Azure Blob Storage** ou seleccione **Configurar** no mosaico **Azure Blob Storage** para configurar a conexión.

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Mosaico de configuración para Azure Blob Storage."::: 

1. Déalle á conexión un nome recoñecible no campo **Nome para mostrar**. O nome e o tipo de conexión describen esta conexión. Recomendamos escoller un nome que explique o propósito e o destino da conexión.

1. Escolla quen pode usar esta conexión. Se non realiza ningunha acción, o valor predeterminado será Administradores. Para obter máis información, consulte [Permitir aos colaboradores usar unha conexión para as exportacións](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Insira o **Nome da conta**, a **Clave da conta** e o **Envase** da súa conta de Blob Storage a onde desexa exportar o segmento.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Captura de pantalla da configuración da conta de almacenamento. "::: 
   
    - Para obter máis información sobre como atopar o nome e a clave da conta de Blob Storage, consulte [Xestionar a configuración da conta de almacenamento no portal de Azure](/azure/storage/common/storage-account-manage).
    - Para obter máis información acerca de como crear un contedor, consulte [Crear un contedor](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Seleccione **Gardar** para completar a conexión. 

### <a name="configure-an-export"></a>Configurar unha exportación

Pode configurar esta exportación se ten acceso a unha conexión deste tipo. Para obter máis información, consulte [Permisos necesarios para configurar unha exportación](export-destinations.md#set-up-a-new-export).

1. Vaia a **Datos** > **Exportacións**.

1. Seleccione **Engadir exportación** para crear unha nova exportación.

1. No campo **Conexión da exportación** escolla unha conexión da sección Azure Blob Storage. Se non ve o nome desta sección, non ten ningunha conexión deste tipo dispoñible.

1. Escolla o segmento que quere exportar. Neste exemplo, é **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Captura de pantalla da interface de usuario de selección de segmento co segmento ChurnProneCustomers seleccionado.":::

1. Seleccione **Gardar**.

Despois de gardar o destino de exportación, atoparao en **Datos** > **Exportacións**.

Xa pode [exportar o segmento baixo demanda](export-destinations.md#run-exports-on-demand). A exportación tamén se executará con todas as [actualizacións programadas](system.md).

> [!NOTE]
> Asegúrese de que o número de rexistros do segmento exportado estea dentro do límite permitido da súa licenza de Adobe Campaign Standard.

Os datos exportados almacénanse no contedor de Azure Blob Storage que configurou anteriormente. A seguinte ruta de cartafol créase automaticamente no seu contedor:

*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*

Exemplo: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv

O *model.json* das entidades exportadas reside a nivel de *%ExportDestinationName%*.

Exemplo: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a>Definir o Experience Data Model (XDM) na Adobe Experience Platform

Para poder usar os datos exportados de estatísticas de audiencia na Adobe Experience Platform, debemos definir o esquema do Experience Data Model e [configurar os datos para o perfil de cliente en tempo real](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).

Aprenda [que é XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) e os [conceptos básicos da composición do esquema](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).

## <a name="import-data-into-adobe-experience-platform"></a>Importar datos a Adobe Experience Platform

Agora que todo está no seu lugar, necesitamos importar os datos de audiencia preparados da información da audiencia á Adobe Experience Platform.

En primeiro lugar, [cree unha conexión de orixe de Azure Blob Storage](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).    

Despois de definir a conexión de orixe, [configure un fluxo de datos](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) para que unha conexión por lotes de almacenamento na nube importe a saída do segmento de información de audiencia a Adobe Experience Platform.

## <a name="create-an-audience-in-adobe-campaign-standard"></a>Crear un público en Adobe Campaign Standard

Para enviar o correo electrónico desta campaña, usaremos Adobe Campaign Standard. Despois de importar os datos a Adobe Experience Platform, necesitamos [crear un público](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) en Adobe Campaign Standard empregando os datos da Adobe Experience Platform.


Aprenda a [usar o creador de segmentos](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) en Adobe Campaign Standard para definir un público baseado nos datos da Adobe Experience Platform.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Crear e enviar o correo electrónico usando Adobe Campaign Standard

Cree o contido do correo electrónico e logo [probe e envíe](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) o seu correo electrónico.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Mostra de correo electrónico con oferta de renovación de Adobe Campaign Standard.":::
