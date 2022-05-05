---
title: Exportar datos de Customer Insights a Adobe Campaign Standard
description: Obtén información sobre como usar os segmentos de Customer Insights Adobe Estándar da campaña.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 2a62d2f889f199222eeb8cc969fce62fa89fa6f0
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642713"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a>Usar segmentos de Customer Insights en Adobe Campaign Standard (versión preliminar)

Como usuario Dynamics 365 Customer Insights, é posible que crease segmentos para facer as súas campañas de mercadotecnia máis eficientes dirixíndose a públicos relevantes. Para usar un segmento de Customer Insights en Adobe Experience Platform e aplicacións como Adobe Campaign Standard, debes seguir algúns pasos descritos neste artigo.

:::image type="content" source="media/ACS-flow.png" alt-text="Diagrama de proceso dos pasos descritos neste artigo.":::

## <a name="prerequisites"></a>Requisitos previos

-   LIcenza de Dynamics 365 Customer Insights
-   Licenza de Adobe Campaign Standard
-   Conta de Azure Blob Storage

## <a name="campaign-overview"></a>Visión xeral da campaña

Para comprender mellor como podes usar os segmentos de Customer Insights en Adobe Experience Platform, vexamos unha campaña de mostra ficticia.

Supoñamos que a súa empresa ofrece un servizo mensual baseado na subscrición aos seus clientes nos Estados Unidos. Identifique os clientes cuxas subscricións deben renovarse nos próximos oito días pero aínda non renovaron a súa subscrición. Para conservar estes clientes, desexa enviarlles unha oferta promocional por correo electrónico mediante Adobe Campaign Standard.

Neste exemplo, debemos executar a campaña de correo electrónico promocional unha vez. Este artigo non cubre o caso de uso de realizar a campaña máis dunha vez. Non obstante, Customer Insights e Adobe Campaign Standard tamén se pode configurar para funcionar nun escenario de campaña recorrente.

## <a name="identify-your-target-audience"></a>Identificar o seu público obxectivo

No noso escenario, asumimos que os enderezos de correo electrónico dos clientes están dispoñibles e que se analizaron as súas preferencias promocionais para identificar os membros do segmento.

O [segmento que definiu en Customer Insights](segments.md) chámase **ChurnProneCustomers** e pensas enviar a estes clientes a promoción por correo electrónico.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Captura de pantalla da páxina de segmentos co segmento ChurnProneCustomers creado.":::

O correo electrónico de oferta que desexa enviar conterá o nome, apelidos e a data de finalización da subscrición do cliente. Informa aos clientes sobre o desconto que obterán se renovan a subscrición antes de que remate.

## <a name="export-your-target-audience"></a>Exportar o seu público obxectivo

### <a name="configure-a-connection"></a>Configurar unha conexión

Co noso público obxectivo identificado, podemos configurar a exportación a unha conta de Azure Blob Storage.

1. En Customer Insights, vai a **Admin** > **Conexións**.

1. Seleccione **Engadir conexión** e elixa **Adobe Campaign** para configurar a conexión ou seleccione **Configurar** no mosaico **Adobe Campaign**.

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Mosaico de configuración de Adobe Campaign Standard.":::

1. Déalle á conexión un nome recoñecible no campo **Nome para mostrar**. O nome e o tipo de conexión describen esta conexión. Recomendamos escoller un nome que explique o propósito e o destino da conexión.

1. Escolla quen pode usar esta conexión. Se non realiza ningunha acción, o valor predeterminado será Administradores. Para obter máis información, consulte [Permisos necesarios para configurar unha exportación](export-destinations.md#set-up-a-new-export).

1. Insira o **Nome da conta**, a **Clave da conta** e o **Envase** da conta de Azure Blob Storage a onde desexa exportar o segmento.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Captura de pantalla da configuración da conta de almacenamento. "::: 

   - Para obter máis información sobre como atopar o nome da conta de Azure Blob Storage e a clave da conta, consulte [Xestionar a configuración da conta de almacenamento no portal de Azure](/azure/storage/common/storage-account-manage).

   - Para obter máis información acerca de como crear un contedor, consulte [Crear un contedor](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Seleccione **Gardar** para completar a conexión.

### <a name="configure-an-export"></a>Configurar unha exportación

Pode configurar esta exportación se ten acceso a unha conexión deste tipo. Para obter máis información, consulte [Permisos necesarios para configurar unha exportación](export-destinations.md#set-up-a-new-export).

1. Vaia a **Datos** > **Exportacións**.

1. Seleccione **Engadir exportación** para crear unha nova exportación.

1. No campo **Conexión para a exportación**, escolla unha conexión na sección de Adobe Campaign. Se non ve o nome desta sección, non ten ningunha conexión deste tipo dispoñible.

1. Escolla o segmento que quere exportar. Neste exemplo, é **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Captura de pantalla da interface de usuario de selección de segmento co segmento ChurnProneCustomers seleccionado.":::

1. Seleccione **Seguinte**.

1. Agora mapeamos o **Fonte** campos desde o segmento Customer Insights ata o **Obxectivo** nomes de campo no Adobe Esquema de perfil estándar da campaña.

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Asignación de campos para o conector de Adobe Campaign Standard.":::

   Se desexa engadir máis atributos, seleccione **Engadir atributo**. O nome de destino pode ser diferente do nome do campo de orixe para que poidas mapear a saída do segmento de Customer Insights a Adobe Campaign Standard se os campos non teñen o mesmo nome nos dous sistemas.

   > [!NOTE]
   > O enderezo de correo electrónico úsase como campo de identidade, pero pode usar calquera outro identificador do perfil do cliente para asignar os datos Adobe Estándar da campaña.

1. Seleccione **Gardar**.

Despois de gardar o destino de exportación, atoparao en **Datos** > **Exportacións**.

Xa pode [exportar o segmento baixo demanda](export-destinations.md#run-exports-on-demand). A exportación tamén se executará con todas as [actualizacións programadas](system.md).

> [!NOTE]
> Asegúrese de que o número de rexistros no segmento exportado está dentro do límite permitido da licenza de Adobe Campaign Standard.

Os datos exportados almacénanse no contedor de Azure Blob Storage que configurou anteriormente. A seguinte ruta de cartafol créase automaticamente no seu contedor:

*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*

Exemplo: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>Configurar Adobe Campaign Standard

Os segmentos exportados conteñen as columnas que seleccionou ao definir o destino de exportación no paso anterior. Estes datos pódense empregar para [crear perfís en Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).

Para usar o segmento en Adobe Campaign Standard, necesitamos ampliar o esquema de perfil en Adobe Campaign Standard para incluír dous campos adicionais. Aprenda a [ampliar o recurso do perfil](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) con novos campos en Adobe Campaign Standard.

No noso exemplo, estes campos son *Nome do segmento e data do segmento (opcional)*.

Usaremos estes campos para identificar os perfís de Adobe Campaign Standard aos que nos queremos dirixir para esta campaña.

Se non hai outros rexistros en Adobe Campaign Standard diferentes aos que vai importar, pode omitir este paso.

## <a name="import-data-into-adobe-campaign-standard"></a>Importar datos a Adobe Campaign Standard

Agora que todo está no seu lugar, necesitamos importar os datos de audiencia preparados desde Customer Insights Adobe Campaña estándar para crear perfís. Aprenda [a importar perfís en Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) usando un fluxo de traballo.

O fluxo de traballo de importación da imaxe seguinte configurouse para executarse cada oito horas e buscar segmentos de Customer Insights exportados (ficheiro .csv en Azure Blob Storage). O fluxo de traballo extrae o contido do ficheiro .csv nunha orde de columna especificada. Este fluxo de traballo creouse para realizar un tratamento básico de erros e garantir que cada rexistro teña un enderezo de correo electrónico antes de hidratar os datos en Adobe Campaign Standard. O fluxo de traballo tamén extrae o nome do segmento do nome do ficheiro antes de actualizalo e inserilo nos datos do perfil de Adobe Campaign Standard.

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Captura de pantalla dun fluxo de traballo de importación na interface de usuario de Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>Recuperar o público en Adobe Campaign Standard

Unha vez importados os datos a Adobe Campaign Standard, [pode crear un fluxo de traballo](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) e [consultar](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) os clientes en función do *Nome do segmento* e a *Data do segmento* para seleccionar os perfís identificados para a nosa campaña de mostra.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Crear e enviar o correo electrónico usando Adobe Campaign Standard

Cree o contido do correo electrónico e logo [probe e envíe](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) o seu correo electrónico.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Mostra de correo electrónico con oferta de renovación de Adobe Campaign Standard.":::
