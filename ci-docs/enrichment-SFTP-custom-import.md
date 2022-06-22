---
title: Enriquecemento con importación personalizada de SFTP
description: Información xeral sobre o enriquecemento con importación personalizada de SFTP.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 657afb6fcb68429680eb677734b4115e69769008
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 06/13/2022
ms.locfileid: "8953717"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a>Enriquecer perfís de clientes con datos personalizados (vista previa)

A importación personalizada co protocolo seguro de transferencia de ficheiros (SFTP) permítelle importar datos que non teñen que pasar polo proceso de unificación de datos. É un xeito flexible, seguro e sinxelo de incorporar os seus datos. A importación personalizada de SFTP pode usarse en combinación coa [exportación de SFTP](export-sftp.md) que lle permite exportar os datos do perfil do cliente necesarios para o enriquecemento. Despois pódense procesar e enriquecer os datos e utilizar a importación personalizada SFTP para devolver os datos enriquecidos a Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Requisitos previos

- Coñécese o nome do ficheiro e a localización (camiño) do ficheiro que se vai importar no servidor SFTP.

- A *modelo.json* está dispoñible un ficheiro que especifica o esquema do modelo de datos común para os datos que se van importar. Este ficheiro debe estar no mesmo directorio que o ficheiro que se vai importar.

- Un SFTP [conexión](connections.md) é [configurado](#configure-the-connection-for-sftp-custom-import).

## <a name="file-schema-example"></a>Exemplo de esquema de ficheiros

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
                    "friendlyName": "Client ID",
                    "dataType": "string"
                },
                {
                    "name": "PreferredCity",
                    "friendlyName": "Preferred city for vacation",
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

## <a name="configure-the-connection-for-sftp-custom-import"></a>Configure a conexión da importación personalizada de SFTP

Debes ser un [administrador](permissions.md#admin) en Customer Insights e ten as credenciais de usuario, o URL e o número de porto para a localización SFTP desde onde queres importar os datos.

1. Seleccione **Engadir conexión** ao configurar un enriquecemento ou ir a **Admin** > **Conexións** e selecciona **Montar** no mosaico Importación personalizada.

   :::image type="content" source="media/enrichment-SFTP-connection.png" alt-text="Páxina de configuración de conexión de importación personalizada.":::

1. Introduza un nome para a conexión.

1. Introduza un nome de usuario, contrasinal e URL de servidor válidos para o servidor SFTP no que residen os datos que se van importar.

1. Revise e proporcione o seu consentimento para a [Privacidade e cumprimento de datos](#data-privacy-and-compliance) seleccionando **Estou de acordo**.

1. Seleccione **Verificar** para validar a configuración e, a continuación, seleccione **Gardar**.

### <a name="data-privacy-and-compliance"></a>Cumprimento e privacidade dos datos

Cando habilitas Dynamics 365 Customer Insights para transmitir datos mediante Importación personalizada, permite a transferencia de datos fóra do límite de conformidade Dynamics 365 Customer Insights, incluíndo datos potencialmente sensibles, como os datos persoais. Microsoft transferirá eses datos segundo as súas instrucións, pero vostede é responsable de asegurarse de que os datos cumpran coas obrigas de privacidade ou de seguridade que poida ter. Para obter máis información, consulte a [Declaración de privacidade de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
O administrador de Dynamics 365 Customer Insights pode eliminar este enriquecemento en calquera momento para interromper o uso desta funcionalidade.

## <a name="configure-the-import"></a>Configurar a importación

1. Vaia a **Datos** > **Enriquecemento** e seleccione o separador **Descubrir**.

1. Seleccione **Enriquece os meus datos** no **Importación personalizada SFTP** tella.

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="Mosaico de importación personalizada de SFTP.":::

1. Revisa a vista xeral e, a continuación, selecciona **A continuación**.

1. Seleccione a conexión. Póñase en contacto cun administrador se non está dispoñible.

1. Seleccione o **Conxunto de datos do cliente** e escolle o perfil ou segmento que queres enriquecer. O *Cliente* a entidade enriquece todos os seus perfís de clientes mentres que un segmento enriquece só os perfís de clientes contidos nese segmento.

1. Seleccione **Seguinte**.

1. Introduza o **Camiño** e **Nome de arquivo** do ficheiro de datos que quere importar.

1. Seleccione **Seguinte**.

1. Proporcionar a **Nome** para o enriquecemento e o **Nome da entidade de saída**.

1. Seleccione **Gardar enriquecemento** despois de revisar as súas opcións.

1. Seleccione **Corre** para iniciar o proceso de enriquecemento ou pechar para volver ao **Enriquecementos** páxina.

## <a name="enrichment-results"></a>Resultados de enriquecemento

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

## <a name="next-steps"></a>Pasos seguintes

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
