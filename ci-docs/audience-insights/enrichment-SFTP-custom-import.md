---
title: Enriquecemento con importación personalizada de SFTP
description: Información xeral sobre o enriquecemento con importación personalizada de SFTP.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: a2d450635c19432bdd88db74b61c17febdeb568d
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896279"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a><span data-ttu-id="82798-103">Enriquecer perfís de clientes con datos personalizados (vista previa)</span><span class="sxs-lookup"><span data-stu-id="82798-103">Enrich customer profiles with custom data (preview)</span></span>

<span data-ttu-id="82798-104">A importación personalizada do protocolo de transferencia de ficheiros seguro (SFTP) permítelle importar datos que non teñen que pasar polo proceso de unificación de datos.</span><span class="sxs-lookup"><span data-stu-id="82798-104">Secure File Transfer Protocol (SFTP) custom import enables you to import data that does not have to go through the process of data unification.</span></span> <span data-ttu-id="82798-105">É un xeito flexible, seguro e sinxelo de incorporar os seus datos.</span><span class="sxs-lookup"><span data-stu-id="82798-105">It's a flexible, secure, and easy way to bring in your data.</span></span> <span data-ttu-id="82798-106">A importación personalizada de SFTP pode usarse en combinación coa [exportación de SFTP](export-sftp.md) que lle permite exportar os datos do perfil do cliente necesarios para o enriquecemento.</span><span class="sxs-lookup"><span data-stu-id="82798-106">SFTP custom import can be used in combination with [SFTP export](export-sftp.md) that lets you export the customer profile data that is needed for enrichment.</span></span> <span data-ttu-id="82798-107">Os datos pódense procesar, enriquecer e a importación personalizada de SFTP pode usarse para devolver os datos enriquecidos á capacidade de información de audiencia de Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="82798-107">The data can then be processed, enriched, and SFTP custom import can be used to bring the enriched data back to the audience insights capability of Dynamics 365 Customer Insights.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="82798-108">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="82798-108">Prerequisites</span></span>

<span data-ttu-id="82798-109">Para configurar a importación personalizada de SFTP, deben cumprirse os seguintes requisitos previos:</span><span class="sxs-lookup"><span data-stu-id="82798-109">To configure SFTP custom import, the following prerequisites must be met:</span></span>

- <span data-ttu-id="82798-110">Ten o nome do ficheiro e a localización (ruta) do ficheiro que se vai importar no servidor SFTP.</span><span class="sxs-lookup"><span data-stu-id="82798-110">You have the filename and location (path) of the file to be imported on the SFTP host.</span></span>
- <span data-ttu-id="82798-111">Existe un ficheiro *model.json* que especifica [o esquema do modelo de datos común](/common-data-model/) para que os datos se importen.</span><span class="sxs-lookup"><span data-stu-id="82798-111">There is a *model.json* file that specifies [the Common Data Model schema](/common-data-model/) for the data to be imported.</span></span> <span data-ttu-id="82798-112">Este ficheiro debe estar no mesmo directorio que o ficheiro que se vai importar.</span><span class="sxs-lookup"><span data-stu-id="82798-112">This file must be in the same directory as the file to import.</span></span>
- <span data-ttu-id="82798-113">Un administrador configurou xa unha conexión SFTP *ou* ten permisos de [administrador](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="82798-113">An SFTP connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="82798-114">Necesitará as credenciais de usuario, o URL e o número de porto para a localización de SFTP de onde quere importar datos.</span><span class="sxs-lookup"><span data-stu-id="82798-114">You'll need the user credentials, URL, and port number for the SFTP location where you want to import data from.</span></span>


## <a name="configure-the-import"></a><span data-ttu-id="82798-115">Configurar a importación</span><span class="sxs-lookup"><span data-stu-id="82798-115">Configure the import</span></span>

1. <span data-ttu-id="82798-116">Vaia a **Datos** > **Enriquecemento** e seleccione o separador **Descubrir**.</span><span class="sxs-lookup"><span data-stu-id="82798-116">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="82798-117">No **mosaico de importación personalizada de SFTP**, seleccione **Enriquecer os meus datos** e logo seleccione **Comezar**.</span><span class="sxs-lookup"><span data-stu-id="82798-117">On the **SFTP custom import tile**, select **Enrich my data** and then select **Get started**.</span></span>

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="Mosaico de importación personalizada de SFTP.":::

1. <span data-ttu-id="82798-119">Seleccione unha [conexión](connections.md) da lista despregable.</span><span class="sxs-lookup"><span data-stu-id="82798-119">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="82798-120">Póñase en contacto cun administrador se non hai conexión dispoñible.</span><span class="sxs-lookup"><span data-stu-id="82798-120">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="82798-121">Se é administrador, pode crear unha conexión seleccionando **Engadir conexión** e escollendo **Importación personalizada de SFTP** desde o menú despregable.</span><span class="sxs-lookup"><span data-stu-id="82798-121">If you are an administrator, you can create a connection by selecting **Add connection** and choosing **SFTP Custom Import** from the drop-down.</span></span>

1. <span data-ttu-id="82798-122">Seleccione **Conectar coa importación personalizada** para confirmar a conexión seleccionada.</span><span class="sxs-lookup"><span data-stu-id="82798-122">Select **Connect to Custom Import** to confirm the selected connection.</span></span>

1.  <span data-ttu-id="82798-123">Seleccione **Seguinte** e introduza o **Nome de arquivo** e o **Camiño** do ficheiro de datos que desexa importar.</span><span class="sxs-lookup"><span data-stu-id="82798-123">Select **Next** and enter the **Filename** and **Path** of the data file that you want to import.</span></span>

    :::image type="content" source="media/enrichment-SFTP-path-and-filename.png" alt-text="Captura de pantalla ao introducir a localización de datos.":::

1. <span data-ttu-id="82798-125">Seleccione **Seguinte** e proporcione un nome para o enriquecemento e un nome para a entidade de saída.</span><span class="sxs-lookup"><span data-stu-id="82798-125">Select **Next** and provide a name for the enrichment and a name for the output entity.</span></span> 

1. <span data-ttu-id="82798-126">Seleccione **Gardar enriquecemento** despois de revisar as súas opcións.</span><span class="sxs-lookup"><span data-stu-id="82798-126">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-sftp-custom-import"></a><span data-ttu-id="82798-127">Configure a conexión da importación personalizada de SFTP</span><span class="sxs-lookup"><span data-stu-id="82798-127">Configure the connection for SFTP Custom Import</span></span> 

<span data-ttu-id="82798-128">Debe ser administrador para configurar as conexións.</span><span class="sxs-lookup"><span data-stu-id="82798-128">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="82798-129">Seleccione **Engadir conexión** ao configurar un enriquecemento *ou* vaia a **Administrar** > **Conexións** e seleccione **Configurar** no mosaico de importación personalizada.</span><span class="sxs-lookup"><span data-stu-id="82798-129">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Custom Import tile.</span></span>

1. <span data-ttu-id="82798-130">Introduza un nome para a conexión na caixa **Nome de visualización**.</span><span class="sxs-lookup"><span data-stu-id="82798-130">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="82798-131">Introduza un nome de usuario, contrasinal e URL de servidor válidos para o servidor STFP no que residen os datos que se van importar.</span><span class="sxs-lookup"><span data-stu-id="82798-131">Enter valid user name, password, and host URL for the STFP server the data to be imported resides on.</span></span>

1. <span data-ttu-id="82798-132">Revise e proporcione o seu consentimento para a **Privacidade e cumprimento dos datos** seleccionando a caixa de verificación **Estou de acordo**.</span><span class="sxs-lookup"><span data-stu-id="82798-132">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="82798-133">Seleccione **Verificar** para validar a configuración.</span><span class="sxs-lookup"><span data-stu-id="82798-133">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="82798-134">Unha vez finalizada a verificación, pódese gardar a conexión facendo clic en **Gardar**.</span><span class="sxs-lookup"><span data-stu-id="82798-134">Once the verification has completed, the connection can be saved by clicking **Save**.</span></span>

> [!div class="mx-imgBorder"]
   > <span data-ttu-id="82798-135">![Páxina de configuración da conexión de Experian](media/enrichment-SFTP-connection.png "Páxina de configuración da conexión de Experian")</span><span class="sxs-lookup"><span data-stu-id="82798-135">![Experian connection configuration page](media/enrichment-SFTP-connection.png "Experian connection configuration page")</span></span>


## <a name="defining-field-mappings"></a><span data-ttu-id="82798-136">Definir asignacións de campos</span><span class="sxs-lookup"><span data-stu-id="82798-136">Defining field mappings</span></span> 

<span data-ttu-id="82798-137">O directorio que contén o ficheiro que se vai importar no servidor SFTP tamén debe conter un ficheiro *model.json*.</span><span class="sxs-lookup"><span data-stu-id="82798-137">The directory that contains the file to be imported on the SFTP server must also contain a *model.json* file.</span></span> <span data-ttu-id="82798-138">Este ficheiro define o esquema que se vai usar para importar os datos.</span><span class="sxs-lookup"><span data-stu-id="82798-138">This file defines the schema to use for importing the data.</span></span> <span data-ttu-id="82798-139">O esquema ten que empregar [Common Data Model](/common-data-model/) para especificar a asignación de campos.</span><span class="sxs-lookup"><span data-stu-id="82798-139">The schema has to use [the Common Data Model](/common-data-model/) to specify the field mapping.</span></span> <span data-ttu-id="82798-140">Un exemplo sinxelo de ficheiro model.json ten este aspecto:</span><span class="sxs-lookup"><span data-stu-id="82798-140">A simple example of a model.json file looks like this:</span></span>

```
{
    "name": "EnrichmentFromMicrosoft",
    "description": "Model containing data enrichment",
    "entities": [
        {
            "name": "CustomImport",
            "attributes": [
                {
                    "name": "CustomerId",
                    "friendlyName": "Client id",
                    "dataType": "string"
                },
                {
                    "name": "PreferredCity",
                    "friendlyName": "Preferred City for vacation",
                    "dataType": "string"
                },
                {
                    "name": "PreferredTransportation",
                    "friendlyName": "Preferred transportation",
                    "dataType": "string"
                }
            ],
            "annotations": [
                {
                    "name": "c360:PrimaryKey",
                    "value": "CustomerId"
                }
            ]
        }
    ],
    "modifiedTime": "2020-01-02T12:00:00+08:00",
    "annotations": [
        {
            "name": "testAnnotation",
            "value": "testValue"
        }
    ]
}
```

## <a name="enrichment-results"></a><span data-ttu-id="82798-141">Resultados de enriquecemento</span><span class="sxs-lookup"><span data-stu-id="82798-141">Enrichment results</span></span>

<span data-ttu-id="82798-142">Para iniciar o proceso de enriquecemento, seleccione **Executar** na barra de comandos.</span><span class="sxs-lookup"><span data-stu-id="82798-142">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="82798-143">Tamén pode deixar que o sistema execute o enriquecemento automaticamente como parte dunha [actualización programada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="82798-143">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="82798-144">O tempo de procesamento dependerá do tamaño dos datos que se van importar e da conexión co servidor SFTP.</span><span class="sxs-lookup"><span data-stu-id="82798-144">The processing time will depend on the size of the data to be imported and the connection to the SFTP server.</span></span>

<span data-ttu-id="82798-145">Despois de completar o proceso de enriquecemento, pode revisar os seus datos de enriquecemento personalizados recentemente importados en **Os meus enriquecementos**.</span><span class="sxs-lookup"><span data-stu-id="82798-145">After the enrichment process completes, you can review your newly imported custom enrichment data under **My enrichments**.</span></span> <span data-ttu-id="82798-146">Ademais, atopará a hora da última actualización e o número de perfís enriquecidos.</span><span class="sxs-lookup"><span data-stu-id="82798-146">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="82798-147">Pode acceder a unha vista detallada de cada perfil enriquecido seleccionando **Ver datos enriquecidos**.</span><span class="sxs-lookup"><span data-stu-id="82798-147">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="82798-148">Pasos seguintes</span><span class="sxs-lookup"><span data-stu-id="82798-148">Next steps</span></span>

<span data-ttu-id="82798-149">Crear sobre os seus datos enriquecidos de clientes.</span><span class="sxs-lookup"><span data-stu-id="82798-149">Build on top of your enriched customer data.</span></span> <span data-ttu-id="82798-150">Cree [segmentos](segments.md), [medidas](measures.md) e [exporte os datos](export-destinations.md) para ofrecer experiencias personalizadas aos seus clientes.</span><span class="sxs-lookup"><span data-stu-id="82798-150">Create [segments](segments.md), [measures](measures.md), and [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
