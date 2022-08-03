---
title: Exportar segmentos a Adobe Experience Platform (vista previa)
description: Aprende a usar os segmentos de Customer Insights en Adobe Experience Platform.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: fcb43e0956c6d1f0ef36b222dd2b718906364244
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195288"
---
# <a name="export-segments-to-adobe-experience-platform-preview"></a>Exportar segmentos a Adobe Experience Platform (vista previa)

Exporta segmentos dirixidos a públicos relevantes a Adobe Experience Platform.

:::image type="content" source="media/AEP-flow.png" alt-text="Diagrama de proceso dos pasos descritos neste artigo.":::

## <a name="prerequisites"></a>Requisitos previos

- An Adobe Experience Platform licenza.
- An Adobe Licenza estándar de campaña.
- An [Conta de Azure Blob Storage](/azure/storage/blobs/create-data-lake-storage-account) nome e clave de conta. Para atopar o nome e a chave, consulte [Xestione a configuración da conta de almacenamento no Azure Portal](/azure/storage/common/storage-account-manage).
- An [Contedor Azure Blob Storage](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="campaign-overview"></a>Visión xeral da campaña

Para comprender mellor como podes usar os segmentos de Customer Insights en Adobe Experience Platform, vexamos unha campaña de mostra ficticia.

Supoñamos que a súa empresa ofrece un servizo mensual baseado na subscrición aos seus clientes nos Estados Unidos. Identifique os clientes cuxas subscricións deben renovarse nos próximos oito días pero aínda non renovaron a súa subscrición. Para conservar estes clientes, desexa enviarlles unha oferta promocional por correo electrónico mediante Adobe Experience Platform.

Neste exemplo, debemos executar a campaña de correo electrónico promocional unha vez. Este artigo non cubre o caso de uso de realizar a campaña máis dunha vez.

## <a name="identify-your-target-audience"></a>Identificar o seu público obxectivo

No noso escenario, asumimos que os enderezos de correo electrónico dos clientes están dispoñibles en Customer Insights e analizáronse as súas preferencias promocionais para identificar os membros do segmento.

O [segmento que definiu en Customer Insights](segments.md) chámase **ChurnProneCustomers** e pensas enviar a estes clientes a promoción por correo electrónico.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Captura de pantalla da páxina de segmentos co segmento ChurnProneCustomers creado.":::

O correo electrónico de oferta que desexa enviar conterá o nome, apelidos e a data de finalización da subscrición do cliente. Informa aos clientes sobre o desconto que obterán se renovan a subscrición antes de que remate.

## <a name="export-your-target-audience"></a>Exportar o seu público obxectivo

Configuraremos a exportación de Customer Insights a unha conta de Azure Blob Storage.

### <a name="set-up-connection-to-azure-blob-storage"></a>Configura a conexión con Azure Blob Storage

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vaia a **Administrar** > **Conexións**.

1. Seleccione **Engadir conexión** e escolle **Azure Blob Storage**.

1. Déalle á conexión un nome recoñecible no campo **Nome para mostrar**. O nome e o tipo de conexión describen esta conexión. Recomendamos escoller un nome que explique o propósito e o destino da conexión.

1. Escolla quen pode usar esta conexión. Por defecto, só son os administradores. Para obter máis información, consulte [Permitir aos colaboradores usar unha conexión para as exportacións](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Insira o **Nome da conta**, a **Clave da conta** e o **Envase** da súa conta de Blob Storage a onde desexa exportar o segmento.  

   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Captura de pantalla da configuración da conta de almacenamento. ":::

1. Revisa o [privacidade e cumprimento dos datos](connections.md#data-privacy-and-compliance) e selecciona **Estou de acordo**.

1. Seleccione **Gardar** para completar a conexión.

### <a name="configure-an-export"></a>Configurar unha exportación

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vaia a **Datos** > **Exportacións**.

1. Seleccione **Engadir exportación**.

1. No campo **Conexión da exportación** escolla unha conexión da sección Azure Blob Storage. Póñase en contacto cun administrador se non hai conexión dispoñible.

1. Introduza un nome para a exportación.

1. Escolla o segmento que quere exportar. Neste exemplo, é **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Captura de pantalla da interface de usuario de selección de segmento co segmento ChurnProneCustomers seleccionado.":::

1. Seleccione **Gardar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

> [!NOTE]
> Asegúrese de que o número de rexistros no segmento exportado está dentro do límite permitido da licenza de Adobe Campaign Standard.

Os datos exportados almacénanse no contedor de Azure Blob Storage que configuraches. As seguintes rutas de cartafol créanse automaticamente no seu contedor:

- Para entidades de orixe e entidades xeradas polo sistema:  

  *%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*

  Exemplo: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv

- O *model.json* das entidades exportadas reside a nivel de *%ExportDestinationName%*.

  Exemplo: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a>Definir o modelo de datos de experiencia (XDM) en Adobe Experience Platform

Antes, os datos exportados de Customer Insights pódense usar dentro Adobe Experience Platform, definir o esquema do modelo de datos da experiencia e [configurar os datos para o perfil de cliente en tempo real](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).

Aprenda [que é XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) e os [conceptos básicos da composición do esquema](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).

## <a name="import-data-into-adobe-experience-platform"></a>Importar datos a Adobe Experience Platform

Importe os datos de audiencia preparados desde Customer Insights a Adobe Experience Platform.

1. [Cree unha conexión de orixe de Azure Blob Storage](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).

1. [Configurar un fluxo de datos](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) para unha conexión por lotes de almacenamento na nube para importar a saída do segmento de Customer Insights Adobe Experience Platform.

## <a name="create-an-audience-in-adobe-campaign-standard"></a>Crear un público en Adobe Campaign Standard

Para enviar o correo electrónico desta campaña, usaremos Adobe Campaign Standard.

1. [Crea unha audiencia](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) en Adobe Campaña estándar usando os datos en Adobe Experience Platform.

1. [Usa o creador de segmentos](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) en Adobe Estándar de campaña para definir unha audiencia baseada nos datos Adobe Experience Platform.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Crear e enviar o correo electrónico usando Adobe Campaign Standard

Cree o contido do correo electrónico e logo [probe e envíe](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) o seu correo electrónico.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Mostra de correo electrónico con oferta de renovación de Adobe Campaign Standard.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
