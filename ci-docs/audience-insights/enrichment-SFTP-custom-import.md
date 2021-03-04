---
title: Enriquecemento con importación personalizada de SFTP
description: Información xeral sobre o enriquecemento con importación personalizada de SFTP.
ms.date: 11/18/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jdahl
ms.author: mhart
manager: shellyha
ms.openlocfilehash: f25dcc08d96d36507e47af0d7b184003ae095819
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269604"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a><span data-ttu-id="9124c-103">Enriquecer perfís de clientes con datos personalizados (vista previa)</span><span class="sxs-lookup"><span data-stu-id="9124c-103">Enrich customer profiles with custom data (preview)</span></span>

<span data-ttu-id="9124c-104">A importación personalizada co protocolo seguro de transferencia de ficheiros (SFTP) permítelle importar datos que non teñen que pasar polo proceso de unificación de datos.</span><span class="sxs-lookup"><span data-stu-id="9124c-104">Secure File Transfer Protocol(SFTP) custom import enables you to import data that doesn't have to go through the process of data unification.</span></span> <span data-ttu-id="9124c-105">É un xeito flexible, seguro e sinxelo de incorporar os seus datos.</span><span class="sxs-lookup"><span data-stu-id="9124c-105">It's a flexible, secure, and easy way to bring in your data.</span></span> <span data-ttu-id="9124c-106">A importación personalizada de SFTP pode usarse en combinación coa [exportación de SFTP](export-sftp.md) que lle permite exportar os datos do perfil do cliente necesarios para o enriquecemento.</span><span class="sxs-lookup"><span data-stu-id="9124c-106">SFTP custom import can be used in combination with [SFTP export](export-sftp.md) that lets you export the customer profile data that is needed for enrichment.</span></span> <span data-ttu-id="9124c-107">Os datos pódense procesar, enriquecer e a importación personalizada de SFTP pode usarse para devolver os datos enriquecidos á capacidade de información de audiencia de Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="9124c-107">The data can then be processed, enriched, and SFTP custom import can be used to bring the enriched data back to the audience insights capability of Dynamics 365 Customer Insights.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9124c-108">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="9124c-108">Prerequisites</span></span>

<span data-ttu-id="9124c-109">Para configurar a importación personalizada de SFTP, deben cumprirse os seguintes requisitos previos:</span><span class="sxs-lookup"><span data-stu-id="9124c-109">To configure SFTP custom import, the following prerequisites must be met:</span></span>

- <span data-ttu-id="9124c-110">Ten credenciais de usuario (nome de usuario e contrasinal) para a localización de SFTP de onde se van importar os datos.</span><span class="sxs-lookup"><span data-stu-id="9124c-110">You have user credentials (user name and password) for the SFTP location where the data that is going to be imported from.</span></span>
- <span data-ttu-id="9124c-111">Ten o URL e o número de porto (normalmente 22) para o servidor STFP.</span><span class="sxs-lookup"><span data-stu-id="9124c-111">You have the URL and port number (usually 22) for the STFP host.</span></span>
- <span data-ttu-id="9124c-112">Ten o nome e a localización do ficheiro que se vai importar no servidor SFTP.</span><span class="sxs-lookup"><span data-stu-id="9124c-112">You have the filename and location of the file to be imported on the SFTP host.</span></span>
- <span data-ttu-id="9124c-113">Hai un ficheiro *model.json* que especifica o esquema dos datos que se van importar.</span><span class="sxs-lookup"><span data-stu-id="9124c-113">There's a *model.json* file that specifies the schema for the data that are to be imported.</span></span> <span data-ttu-id="9124c-114">Este ficheiro debe estar no mesmo directorio que o ficheiro que se vai importar.</span><span class="sxs-lookup"><span data-stu-id="9124c-114">This file must be in the same directory as the file to import.</span></span>
- <span data-ttu-id="9124c-115">Ten permiso de [administrador](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="9124c-115">You have [Administrator](permissions.md#administrator) permission.</span></span>

## <a name="configuration"></a><span data-ttu-id="9124c-116">Configuración</span><span class="sxs-lookup"><span data-stu-id="9124c-116">Configuration</span></span>

1. <span data-ttu-id="9124c-117">Vaia a **Datos** > **Enriquecemento** e seleccione o separador **Descubrir**.</span><span class="sxs-lookup"><span data-stu-id="9124c-117">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="9124c-118">No **mosaico de importación personalizada de SFTP**, seleccione **Enriquecer os meus datos**.</span><span class="sxs-lookup"><span data-stu-id="9124c-118">On the **SFTP custom import tile**, select **Enrich my data**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9124c-119">![Mosaico de importación personalizada de SFTP](media/SFTP_Custom_Import_tile.png "Mosaico de importación personalizada de SFTP")</span><span class="sxs-lookup"><span data-stu-id="9124c-119">![SFTP Custom Import tile](media/SFTP_Custom_Import_tile.png "SFTP Custom Import tile")</span></span>

1. <span data-ttu-id="9124c-120">Seleccione **Comezar** e proporcione as credenciais e o enderezo do servidor SFTP.</span><span class="sxs-lookup"><span data-stu-id="9124c-120">Select **Get started** and provide the credentials and the address for the SFTP server.</span></span> <span data-ttu-id="9124c-121">Por exemplo, sftp://mysftpserver.com:22.</span><span class="sxs-lookup"><span data-stu-id="9124c-121">For example, sftp://mysftpserver.com:22.</span></span>

1. <span data-ttu-id="9124c-122">Introduza o nome do ficheiro que contén os datos e a ruta ao ficheiro no servidor SFTP se non está no cartafol raíz.</span><span class="sxs-lookup"><span data-stu-id="9124c-122">Enter the name of the file that contains the data and path to the file on the SFTP server if it's not in the root folder.</span></span>

1. <span data-ttu-id="9124c-123">Confirme todas as entradas seleccionando **Conectar coa importación personalizada**.</span><span class="sxs-lookup"><span data-stu-id="9124c-123">Confirm all inputs by selecting **Connect to Custom Import**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9124c-124">![Control flotante de configuración da importación personalizada de SFTP](media/SFTP_Custom_Import_Configuration_flyout.png "Control flotante de configuración da importación personalizada de SFTP")</span><span class="sxs-lookup"><span data-stu-id="9124c-124">![SFTP Custom Import Configuration flyout](media/SFTP_Custom_Import_Configuration_flyout.png "SFTP Custom Import Configuration flyout")</span></span>

## <a name="defining-field-mappings"></a><span data-ttu-id="9124c-125">Definir asignacións de campos</span><span class="sxs-lookup"><span data-stu-id="9124c-125">Defining field mappings</span></span> 

<span data-ttu-id="9124c-126">O directorio que contén o ficheiro que se vai importar no servidor SFTP tamén debe conter un ficheiro *model.json*.</span><span class="sxs-lookup"><span data-stu-id="9124c-126">The directory that contains the file to be imported on the SFTP server must also contain a *model.json* file.</span></span> <span data-ttu-id="9124c-127">Este ficheiro define o esquema que se vai usar para importar os datos.</span><span class="sxs-lookup"><span data-stu-id="9124c-127">This file defines the schema to use for importing the data.</span></span> <span data-ttu-id="9124c-128">O esquema ten que empregar [Common Data Model](https://docs.microsoft.com/common-data-model/) para especificar a asignación de campos.</span><span class="sxs-lookup"><span data-stu-id="9124c-128">The schema has to use [the Common Data Model](https://docs.microsoft.com/common-data-model/) to specify the field mapping.</span></span> <span data-ttu-id="9124c-129">Un exemplo sinxelo de ficheiro model.json ten este aspecto:</span><span class="sxs-lookup"><span data-stu-id="9124c-129">A simple example of a model.json file looks like this:</span></span>

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

## <a name="enrichment-results"></a><span data-ttu-id="9124c-130">Resultados de enriquecemento</span><span class="sxs-lookup"><span data-stu-id="9124c-130">Enrichment results</span></span>

<span data-ttu-id="9124c-131">Para iniciar o proceso de enriquecemento, seleccione **Executar** na barra de comandos.</span><span class="sxs-lookup"><span data-stu-id="9124c-131">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="9124c-132">Tamén pode deixar que o sistema execute o enriquecemento automaticamente como parte dunha [actualización programada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="9124c-132">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="9124c-133">O tempo de procesamento dependerá do tamaño dos datos que se van importar e da conexión co servidor SFTP.</span><span class="sxs-lookup"><span data-stu-id="9124c-133">The processing time will depend on the size of the data to be imported and the connection to the SFTP server.</span></span>

<span data-ttu-id="9124c-134">Despois de completar o proceso de enriquecemento, pode revisar os seus datos de enriquecemento personalizados recentemente importados en **Os meus enriquecementos**.</span><span class="sxs-lookup"><span data-stu-id="9124c-134">After the enrichment process completes, you can review your newly imported custom enrichment data under **My enrichments**.</span></span> <span data-ttu-id="9124c-135">Ademais, atopará a hora da última actualización e o número de perfís enriquecidos.</span><span class="sxs-lookup"><span data-stu-id="9124c-135">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="9124c-136">Pode acceder a unha vista detallada de cada perfil enriquecido seleccionando **Ver datos enriquecidos**.</span><span class="sxs-lookup"><span data-stu-id="9124c-136">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="9124c-137">Pasos seguintes</span><span class="sxs-lookup"><span data-stu-id="9124c-137">Next steps</span></span>

<span data-ttu-id="9124c-138">Crear sobre os seus datos enriquecidos de clientes.</span><span class="sxs-lookup"><span data-stu-id="9124c-138">Build on top of your enriched customer data.</span></span> <span data-ttu-id="9124c-139">Cree [segmentos](segments.md), [medidas](measures.md) e [exporte os datos](export-destinations.md) para ofrecer experiencias personalizadas aos seus clientes.</span><span class="sxs-lookup"><span data-stu-id="9124c-139">Create [segments](segments.md), [measures](measures.md), and [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>




[!INCLUDE[footer-include](../includes/footer-banner.md)]