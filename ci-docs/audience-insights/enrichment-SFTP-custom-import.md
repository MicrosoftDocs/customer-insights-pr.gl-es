---
title: Enriquecemento con importación personalizada de SFTP
description: Información xeral sobre o enriquecemento con importación personalizada de SFTP.
ms.date: 11/18/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jdahl
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 59f7f05ca0825ba147e9e93f10fa3508ec3a16dd
ms.sourcegitcommit: ff824bbbd31fd666ab0da682bf48ea31580d242c
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "4568438"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a>Enriquecer perfís de clientes con datos personalizados (vista previa)

A importación personalizada co protocolo seguro de transferencia de ficheiros (SFTP) permítelle importar datos que non teñen que pasar polo proceso de unificación de datos. É un xeito flexible, seguro e sinxelo de incorporar os seus datos. A importación personalizada de SFTP pode usarse en combinación coa [exportación de SFTP](export-sftp.md) que lle permite exportar os datos do perfil do cliente necesarios para o enriquecemento. Os datos pódense procesar, enriquecer e a importación personalizada de SFTP pode usarse para devolver os datos enriquecidos á capacidade de información de audiencia de Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Requisitos previos

Para configurar a importación personalizada de SFTP, deben cumprirse os seguintes requisitos previos:

- Ten credenciais de usuario (nome de usuario e contrasinal) para a localización de SFTP de onde se van importar os datos.
- Ten o URL e o número de porto (normalmente 22) para o servidor STFP.
- Ten o nome e a localización do ficheiro que se vai importar no servidor SFTP.
- Hai un ficheiro *model.json* que especifica o esquema dos datos que se van importar. Este ficheiro debe estar no mesmo directorio que o ficheiro que se vai importar.
- Ten permiso de [administrador](permissions.md#administrator).

## <a name="configuration"></a>Configuración

1. Vaia a **Datos** > **Enriquecemento** e seleccione o separador **Descubrir**.

1. No **mosaico de importación personalizada de SFTP**, seleccione **Enriquecer os meus datos**.

   > [!div class="mx-imgBorder"]
   > ![Mosaico de importación personalizada de SFTP](media/SFTP_Custom_Import_tile.png "Mosaico de importación personalizada de SFTP")

1. Seleccione **Comezar** e proporcione as credenciais e o enderezo do servidor SFTP. Por exemplo, sftp://mysftpserver.com:22.

1. Introduza o nome do ficheiro que contén os datos e a ruta ao ficheiro no servidor SFTP se non está no cartafol raíz.

1. Confirme todas as entradas seleccionando **Conectar coa importación personalizada**.

   > [!div class="mx-imgBorder"]
   > ![Control flotante de configuración da importación personalizada de SFTP](media/SFTP_Custom_Import_Configuration_flyout.png "Control flotante de configuración da importación personalizada de SFTP")

## <a name="defining-field-mappings"></a>Definir asignacións de campos 

O directorio que contén o ficheiro que se vai importar no servidor SFTP tamén debe conter un ficheiro *model.json*. Este ficheiro define o esquema que se vai usar para importar os datos. O esquema ten que empregar [Common Data Model](https://docs.microsoft.com/common-data-model/) para especificar a asignación de campos. Un exemplo sinxelo de ficheiro model.json ten este aspecto:

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

## <a name="enrichment-results"></a>Resultados de enriquecemento

Para iniciar o proceso de enriquecemento, seleccione **Executar** na barra de comandos. Tamén pode deixar que o sistema execute o enriquecemento automaticamente como parte dunha [actualización programada](system.md#schedule-tab). O tempo de procesamento dependerá do tamaño dos datos que se van importar e da conexión co servidor SFTP.

Despois de completar o proceso de enriquecemento, pode revisar os seus datos de enriquecemento personalizados recentemente importados en **Os meus enriquecementos**. Ademais, atopará a hora da última actualización e o número de perfís enriquecidos.

Pode acceder a unha vista detallada de cada perfil enriquecido seleccionando **Ver datos enriquecidos**.

## <a name="next-steps"></a>Pasos seguintes

Crear sobre os seus datos enriquecidos de clientes. Cree [segmentos](segments.md), [medidas](measures.md) e [exporte os datos](export-destinations.md) para ofrecer experiencias personalizadas aos seus clientes.


