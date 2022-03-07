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
ms.openlocfilehash: fa1d4ffd9f77e128b5d804e4562e964561f4684f
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 10/08/2021
ms.locfileid: "7618680"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a>Enriquecer perfís de clientes con datos personalizados (vista previa)

A importación personalizada co protocolo seguro de transferencia de ficheiros (SFTP) permítelle importar datos que non teñen que pasar polo proceso de unificación de datos. É un xeito flexible, seguro e sinxelo de incorporar os seus datos. A importación personalizada de SFTP pode usarse en combinación coa [exportación de SFTP](export-sftp.md) que lle permite exportar os datos do perfil do cliente necesarios para o enriquecemento. Os datos pódense procesar e enriquecer e pódese usar a importación personalizada de SFTP para devolver os datos enriquecidos á capacidade de información de audiencia de Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Requisitos previos

Para configurar a importación personalizada de SFTP, deben cumprirse os seguintes requisitos previos:

- Ten o nome do ficheiro e a localización (ruta) do ficheiro que se vai importar no servidor SFTP.
- Existe un ficheiro *model.json* que especifica [o esquema do modelo de datos común](/common-data-model/) para que os datos se importen. Este ficheiro debe estar no mesmo directorio que o ficheiro que se vai importar.
- Un administrador configurou xa unha conexión SFTP *ou* ten permisos de [administrador](permissions.md#administrator). Necesitará as credenciais de usuario, o URL e o número de porto para a localización de SFTP de onde quere importar datos.


## <a name="configure-the-import"></a>Configurar a importación

1. Vaia a **Datos** > **Enriquecemento** e seleccione o separador **Descubrir**.

1. No **mosaico de importación personalizada de SFTP**, seleccione **Enriquecer os meus datos** e logo seleccione **Comezar**.

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="Mosaico de importación personalizada de SFTP.":::

1. Seleccione unha [conexión](connections.md) da lista despregable. Póñase en contacto cun administrador se non hai conexión dispoñible. Se é administrador, pode crear unha conexión seleccionando **Engadir conexión** e escollendo **Importación personalizada de SFTP** da lista despregable.

1. Seleccione **Conectar coa importación personalizada** para confirmar a conexión seleccionada.

1.  Seleccione **Seguinte** e introduza o **Camiño** e **Nome de arquivo** do ficheiro de datos que desexa importar.

    :::image type="content" source="media/enrichment-SFTP-path-and-filename.png" alt-text="Captura de pantalla ao introducir a localización de datos.":::

1. Seleccione **Seguinte** e escolla o conxunto de datos do cliente. Poden ser todos os perfís de clientes ou un segmento.

1. Seleccione **Seguinte** e proporcione un nome para o enriquecemento e un nome para a entidade de saída. 

1. Seleccione **Gardar enriquecemento** despois de revisar as súas opcións.

## <a name="configure-the-connection-for-sftp-custom-import"></a>Configure a conexión da importación personalizada de SFTP 

Debe ser administrador para configurar as conexións. Seleccione **Engadir conexión** ao configurar un enriquecemento *ou* vaia a **Administrar** > **Conexións** e seleccione **Configurar** no mosaico de importación personalizada.

1. Introduza un nome para a conexión na caixa **Nome de visualización**.

1. Introduza un nome de usuario, contrasinal e URL de servidor válidos para o servidor SFTP no que residen os datos que se van importar.

1. Revise e proporcione o seu consentimento para a **Privacidade e cumprimento dos datos** seleccionando a caixa de verificación **Estou de acordo**.

1. Seleccione **Verificar** para validar a configuración.

1. Unha vez completada a verificación, pódese gardar a conexión seleccionando **Gardar**.

   > [!div class="mx-imgBorder"]
   > ![Páxina de configuración da conexión de Experian.](media/enrichment-SFTP-connection.png "Páxina de configuración da conexión de Experian")


## <a name="defining-field-mappings"></a>Definir asignacións de campos 

O directorio que contén o ficheiro que se vai importar no servidor SFTP tamén debe conter un ficheiro *model.json*. Este ficheiro define o esquema que se vai usar para importar os datos. O esquema ten que empregar o [modelo de datos común](/common-data-model/) para especificar a asignación de campos. Un exemplo sinxelo de ficheiro model.json ten este aspecto:

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

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](../includes/footer-banner.md)]
