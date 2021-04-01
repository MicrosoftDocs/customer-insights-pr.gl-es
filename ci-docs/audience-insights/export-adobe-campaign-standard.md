---
title: Exportar datos de Customer Insights a Adobe Campaign Standard
description: Coñeza como usar segmentos de información de público en Adobe Campaign Standard.
ms.date: 02/26/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: a5d0154c3d7c473dcba03fac0847bafcf97de2f2
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596313"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a>Utilice segmentos de Customer Insights en Adobe Campaign Standard (versión preliminar)

Como usuario Insights for Dynamics 365 Customer Insights de audiencia é posible que crease segmentos para facer máis eficientes as súas campañas de márketing dirixíndose a públicos relevantes. Para usar un segmento de información de audiencia en Adobe Experience Platform e aplicacións como Adobe Campaign Standard, cómpre seguir algúns pasos descritos neste artigo.

:::image type="content" source="media/ACS-flow.png" alt-text="Diagrama de proceso dos pasos descritos neste artigo.":::

## <a name="prerequisites"></a>Requisitos previos

-   LIcenza de Dynamics 365 Customer Insights
-   Licenza de Adobe Campaign Standard
-   Conta de Azure Blob Storage

## <a name="campaign-overview"></a>Visión xeral da campaña

Para comprender mellor como pode usar segmentos de información do público en Adobe Experience Platform, vexamos unha mostra de campaña ficticia.

Supoñamos que a súa empresa ofrece un servizo mensual baseado na subscrición aos seus clientes nos Estados Unidos. Identifique os clientes cuxas subscricións deben renovarse nos próximos oito días pero aínda non renovaron a súa subscrición. Para manter estes clientes, pode enviarlles unha oferta promocional por correo electrónico mediante Adobe Campaign Standard.

Neste exemplo, debemos executar a campaña de correo electrónico promocional unha vez. Este artigo non cubre o caso de uso de realizar a campaña máis dunha vez. Non obstante, a información do público e Adobe Campaign Standard pódense configurar para que funcionen tamén nun escenario de campaña periódica.

## <a name="identify-your-target-audience"></a>Identificar o seu público obxectivo

No noso escenario, supoñemos que os enderezos de correo electrónico dos clientes están dispoñibles en información de audiencia e as súas preferencias promocionais analizáronse para identificar os membros do segmento.

O [segmento que definiu nas estatísticas do público](segments.md) chámase **ChurnProneCustomers** e planea enviar a estes clientes a promoción por correo electrónico.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Captura de pantalla da páxina de segmentos co segmento ChurnProneCustomers creado.":::

O correo electrónico de oferta que desexa enviar conterá o nome, apelidos e a data de finalización da subscrición do cliente. Informa aos clientes sobre o desconto que obterán se renovan a subscrición antes de que remate.

## <a name="export-your-target-audience"></a>Exportar o seu público obxectivo

Co noso público obxectivo identificado, podemos configurar a exportación desde a información de audiencia a unha conta de Azure Blob Storage.

1. Na información do público, vaia a **Administrar** > **Destinos de exportación**.

1. No mosaico de **Campaña de Adobe**, seleccione **Configurar**.

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Mosaico de configuración para Adobe Campaign Standard.":::

1. Proporcione un **Nome para mostrar** para este novo destino de exportación e despois introduza o **Nome da conta**, **Clave da conta** e **Contedor** da conta de Azure Blob Storage a onde desexa exportar o segmento.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Captura de pantalla da configuración da conta de almacenamento. "::: 

   - Para obter máis información sobre como atopar o nome da conta de almacenamento BLOB de Azure e a clave da conta, consulte [Xestionar a configuración da conta de almacenamento no portal de Azure](/azure/storage/common/storage-account-manage).

   - Para obter máis información acerca de como crear un contedor, consulte [Crear un contedor](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Seleccione **Seguinte**.

1. Escolla o segmento que quere exportar. Neste exemplo, é **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Captura de pantalla da interface de usuario de selección de segmento co segmento ChurnProneCustomers seleccionado.":::

1. Seleccione **Seguinte**.

1. Agora asignamos os campos **Orixe** do segmento de información do público aos nomes do campo **Obxectivo** no esquema de perfil Adobe Campaign Standard.

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Asignación de campo para o conector Adobe Campaign Standard.":::

   Se desexa engadir máis atributos, seleccione **Engadir atributo**. O nome de destino pode ser diferente do nome do campo de orixe, de xeito que aínda pode asignar a saída de segmentos de información de audiencia a Adobe Campaign Standard se os campos non teñen o mesmo nome nos dous sistemas.

   > [!NOTE]
   > O enderezo de correo electrónico úsase como campo de identidade, pero pode usar calquera outro identificador do perfil de cliente de información de público para asignar datos a Adobe Campaign Standard.

1. Seleccione **Gardar**.

Despois de gardar o destino da exportación, atoparao en **Administrador** > **Exportacións** > **Os meus destinos de exportación**.

:::image type="content" source="media/export-destination-adobe-campaign-standard.png" alt-text="Captura de pantalla coa lista de exportacións e segmento de mostra resaltado.":::

Xa pode [exportar o segmento baixo demanda](export-destinations.md#export-data-on-demand). A exportación tamén se executará con todas as [actualizacións programadas](system.md).

> [!NOTE]
> Asegúrese de que o número de rexistros do segmento exportado estea dentro do límite permitido da súa licenza de Adobe Campaign Standard.

Os datos exportados almacénanse no contedor de almacenamento de Azure Blob que configurou anteriormente. A seguinte ruta de cartafol créase automaticamente no seu contedor:

*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*

Exemplo: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>Configurar Adobe Campaign Standard

Cando se exporta un segmento de información de audiencia, contén as columnas que seleccionou ao definir o destino da exportación no paso anterior. Estes datos pódense empregar para [crear perfís en Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).

Para usar o segmento en Adobe Campaign Standard, necesitamos ampliar o esquema de perfís en Adobe Campaign Standard para incluír dous campos adicionais. Aprenda a [ampliar o recurso do perfil](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) con novos campos en Adobe Campaign Standard.

No noso exemplo, estes campos son *Nome do segmento e data do segmento (opcional).*

Usaremos estes campos para identificar os perfís de Adobe Campaign Standard aos que queremos orientar esta campaña.

Se non hai outros rexistros en Adobe Campaign Standard, ademais do que vai importar, pode omitir este paso.

## <a name="import-data-into-adobe-campaign-standard"></a>Importar datos a Adobe Campaign Standard

Agora que todo está no seu lugar, necesitamos importar os datos de audiencia preparados da información da audiencia a Adobe Campaign Standard para crear perfís. Aprenda [como importar perfís en Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) usando un fluxo de traballo.

O fluxo de traballo de importación da seguinte imaxe configurouse para executarse cada 8 horas e busca segmentos de información de audiencia exportados (ficheiro .csv en Azure Blob Storage). O fluxo de traballo extrae o contido do ficheiro .csv nunha orde de columna especificada. Este fluxo de traballo creouse para realizar un tratamento básico de erros e garantir que cada rexistro teña un enderezo de correo electrónico antes de hidratar os datos en Adobe Campaign Standard. O fluxo de traballo tamén extrae o nome do segmento do nome do ficheiro antes de introducilo nos datos do perfil de ACS.

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Captura de pantalla dun fluxo de traballo de importación na interface de usuario de Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>Recuperar o público en Adobe Campaign Standard

Unha vez importados os datos a Adobe Campaign Standard, [pode crear un fluxo de traballo](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) e [consultar](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) os clientes en función do *Nome do segmento* e a *Data do segmento* para seleccionar os perfís identificados para a nosa campaña de mostra.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Crear e enviar o correo electrónico usando Adobe Campaign Standard

Cree o contido do correo electrónico e logo [probe e envíe](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) o seu correo electrónico.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Mostra de correo electrónico con oferta de renovación de Adobe Campaign Standard.":::