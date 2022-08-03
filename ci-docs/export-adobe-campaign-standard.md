---
title: Exportar segmentos de Customer Insights a Adobe Estándar de campaña (vista previa)
description: Obtén información sobre como usar os segmentos de Customer Insights Adobe Estándar da campaña.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 834880cac9c5023157983081ff2513d9b051491f
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195518"
---
# <a name="export-customer-insights-segments-to-adobe-campaign-standard-preview"></a>Exportar segmentos de Customer Insights a Adobe Estándar de campaña (vista previa)

Exporta segmentos dirixidos a públicos relevantes Adobe Estándar da campaña.

:::image type="content" source="media/ACS-flow.png" alt-text="Diagrama de proceso dos pasos descritos neste artigo.":::

## <a name="prerequisites"></a>Requisitos previos

- An Adobe Licenza estándar de campaña.
- An [Conta de Azure Blob Storage](/azure/storage/blobs/create-data-lake-storage-account) nome e clave de conta. Para atopar o nome e a chave, consulte [Xestione a configuración da conta de almacenamento no Azure Portal](/azure/storage/common/storage-account-manage).
- An [Contedor Azure Blob Storage](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="campaign-overview"></a>Visión xeral da campaña

Para comprender mellor como podes usar os segmentos de Customer Insights en Adobe Experience Platform, vexamos unha campaña de mostra ficticia.

Supoñamos que a súa empresa ofrece un servizo mensual baseado na subscrición aos seus clientes nos Estados Unidos. Identifique os clientes cuxas subscricións deben renovarse nos próximos oito días pero aínda non renovaron a súa subscrición. Para conservar estes clientes, desexa enviarlles unha oferta promocional por correo electrónico mediante Adobe Campaign Standard.

Neste exemplo, debemos executar a campaña de correo electrónico promocional unha vez. Este artigo non cubre o caso de uso de realizar a campaña máis dunha vez. Non obstante, Customer Insights e Adobe Campaign Standard tamén se pode configurar para funcionar nun escenario de campaña recorrente.

## <a name="identify-your-target-audience"></a>Identificar o seu público obxectivo

No noso escenario, asumimos que os enderezos de correo electrónico dos clientes están dispoñibles en Customer Insights e analizáronse as súas preferencias promocionais para identificar os membros do segmento.

O [segmento que definiu en Customer Insights](segments.md) chámase **ChurnProneCustomers** e pensas enviar a estes clientes a promoción por correo electrónico.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Captura de pantalla da páxina de segmentos co segmento ChurnProneCustomers creado.":::

O correo electrónico de oferta que desexa enviar conterá o nome, apelidos e a data de finalización da subscrición do cliente. Informa aos clientes sobre o desconto que obterán se renovan a subscrición antes de que remate.

## <a name="export-your-target-audience"></a>Exportar o seu público obxectivo

### <a name="set-up-connection-to-adobe-campaign"></a>Configura a conexión a Adobe Campaña

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vaia a **Administrar** > **Conexións**.

1. Seleccione **Engadir conexión** e escolle **Adobe Campaña**.

1. Déalle á conexión un nome recoñecible no campo **Nome para mostrar**. O nome e o tipo de conexión describen esta conexión. Recomendamos escoller un nome que explique o propósito e o destino da conexión.

1. Escolla quen pode usar esta conexión. Por defecto, só son os administradores. Para obter máis información, consulte [Permitir aos colaboradores usar unha conexión para as exportacións](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduza o **Nome da conta**, **da conta**, e **Envase** para a túa conta de Blob Storage.  

   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Captura de pantalla da configuración da conta de almacenamento. ":::

1. Revisa o [privacidade e cumprimento dos datos](connections.md#data-privacy-and-compliance) e selecciona **Estou de acordo**.

1. Seleccione **Gardar** para completar a conexión.

### <a name="configure-an-export"></a>Configurar unha exportación

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vaia a **Datos** > **Exportacións**.

1. Seleccione **Engadir exportación**.

1. No campo **Conexión para a exportación**, escolla unha conexión na sección de Adobe Campaign. Póñase en contacto cun administrador se non hai conexión dispoñible.

1. Introduza un nome para a exportación.

1. Escolla o segmento que quere exportar. Neste exemplo, é **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Captura de pantalla da interface de usuario de selección de segmento co segmento ChurnProneCustomers seleccionado.":::

1. Seleccione **Seguinte**.

1. Mapa o **Fonte** campos desde o segmento Customer Insights ata o **Obxectivo** nomes de campo no Adobe Esquema de perfil estándar da campaña.

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Asignación de campos para o conector de Adobe Campaign Standard.":::

   Se desexa engadir máis atributos, seleccione **Engadir atributo**. O nome de destino pode ser diferente do nome do campo de orixe para que poidas mapear a saída do segmento de Customer Insights a Adobe Campaign Standard se os campos non teñen o mesmo nome nos dous sistemas.

   > [!NOTE]
   > O enderezo de correo electrónico úsase como campo de identidade, pero pode usar calquera outro identificador do perfil do cliente para asignar os datos Adobe Estándar da campaña.

1. Seleccione **Gardar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

> [!NOTE]
> Asegúrese de que o número de rexistros no segmento exportado está dentro do límite permitido da licenza de Adobe Campaign Standard.

Os datos exportados almacénanse no contedor de Azure Blob Storage que configurou anteriormente. A seguinte ruta do cartafol créase automaticamente no teu contedor: *%ContainerName% /CustomerInsights_%instanceID% /% nome-destino-exportación%_%segmentname%_%timestamp% .csv*

Exemplo: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>Configurar Adobe Campaign Standard

Os segmentos exportados conteñen as columnas que seleccionou ao configurar a exportación. Estes datos pódense empregar para [crear perfís en Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).

Para usar o segmento en Adobe Estándar de campaña, [ampliar o esquema do perfil](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) en Adobe Estándar de campaña para incluír dous campos adicionais.

No noso exemplo, estes campos son Nome do segmento e Data do segmento. Usaremos estes campos para identificar os perfís de Adobe Campaign Standard aos que nos queremos dirixir para esta campaña.

Se non hai outros rexistros Adobe Campaign Standard, ademais do que vai importar, omita este paso.

## <a name="import-data-into-adobe-campaign-standard"></a>Importar datos a Adobe Campaign Standard

Importe os datos de audiencia preparados desde Customer Insights a Adobe Campaña estándar para [crear perfís mediante un fluxo de traballo](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences).

O fluxo de traballo de importación da imaxe seguinte configurouse para executarse cada oito horas e buscar segmentos de Customer Insights exportados (ficheiro .csv en Azure Blob Storage). O fluxo de traballo extrae o contido do ficheiro .csv nunha orde de columna especificada. Este fluxo de traballo creouse para realizar un tratamento básico de erros e garantir que cada rexistro teña un enderezo de correo electrónico antes de hidratar os datos en Adobe Campaign Standard. O fluxo de traballo tamén extrae o nome do segmento do nome do ficheiro antes de actualizalo e inserilo nos datos do perfil de Adobe Campaign Standard.

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Captura de pantalla dun fluxo de traballo de importación na interface de usuario de Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>Recuperar o público en Adobe Campaign Standard

Unha vez importados os datos Adobe estándar de campaña, [crear un fluxo de traballo](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) e [consulta](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) os clientes en función do nome do segmento e da data do segmento para seleccionar os perfís que foron identificados para a nosa campaña de mostra.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Crear e enviar o correo electrónico usando Adobe Campaign Standard

Cree o contido do correo electrónico e logo [probe e envíe](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) o seu correo electrónico.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Mostra de correo electrónico con oferta de renovación de Adobe Campaign Standard.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
