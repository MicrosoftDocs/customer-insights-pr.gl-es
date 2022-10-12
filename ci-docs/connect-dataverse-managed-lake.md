---
title: Conectar cos datos dun lago de datos xestionado de Microsoft Dataverse
description: Importar datos dun lago de datos xestionado de Microsoft Dataverse.
ms.date: 08/18/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: v-wendysmith
searchScope:
- ci-dataverse
- customerInsights
ms.openlocfilehash: 0d9612525344c8ac99b6e3edfe33a426dc0a474b
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609793"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Conectar cos datos dun lago de datos xestionado de Microsoft Dataverse

Microsoft Dataverse os usuarios poden conectarse rapidamente a entidades analíticas nun Microsoft Dataverse lago xestionado. Só unha orixe de datos dun ambiente pode usar ao mesmo tempo o mesmo lago xestionado de Dataverse.

> [!NOTE]
> Debes ser administrador do Dataverse organización para continuar e ver a lista de entidades dispoñibles no lago xestionado.

## <a name="prerequisites"></a>Requisitos previos

- Os datos almacenados nos servizos en liña como Azure Data Lake Storage poden almacenarse nunha localización diferente a onde se procesaron ou almacenaron os datos en Dynamics 365 Customer Insights.Ao importar ou conectarse a datos almacenados nos servizos en liña, acepta que os datos se poidan transferir e almacenar con Dynamics 365 Customer Insights . [Máis información no Microsoft Trust Center](https://www.microsoft.com/trust-center).

- Só Dataverse entidades con [seguimento de cambios](/power-platform/admin/enable-change-tracking-control-data-synchronization) habilitados son visibles. Estas entidades pódense exportar ao Dataverse -lago de datos xestionado e usado en Customer Insights. Fóra da caixa Dataverse As táboas teñen o seguimento de cambios activado por defecto. Debes activar o seguimento de cambios nas táboas personalizadas. Para comprobar se a Dataverse a táboa está habilitada para o seguimento de cambios, vaia a [Power Apps](https://make.powerapps.com) > **Datos** > **Táboas**. Busca a táboa do teu interese e selecciónaa. Ir a **Configuración** > **Opcións avanzadas** e revisa o **Rastrexa os cambios** configuración.

## <a name="connect-to-a-dataverse-managed-lake"></a>Conectarse a un lago xestionado por Dataverse

1. Vaia a **Datos** > **Orixes de datos**.

1. Seleccione **Engadir orixe de datos**.

1. Seleccione **Microsoft Dataverse**.

1. Introduza a **Nome** para o orixe de datos e un opcional **Descrición**.

1. Proporcione o **Enderezo do servidor** para a organización de Dataverse e seleccione **Iniciar sesión**.

1. Seleccione as táboas que quere inxerir como entidades a Customer Insights da lista dispoñible.

   > [!NOTE]
   > Se algunhas táboas xa están seleccionadas, poden ser usadas por outras aplicacións de Dynamics 365 (como Dynamics 365 Sales Insights ou Customer Service Insights). Non se pode cambiar a selección. Estas táboas estarán dispoñibles como entidades unha vez que se crea a orixe de datos.

    :::image type="content" source="media/select-dataverse-entities.png" alt-text="Caixa de diálogo que mostra unha lista de entidades no ambiente de Dataverse.":::

1. Garde a selección para comezar a sincronizar as táboas seleccionadas de Dataverse. Atopará a conexión acabada de engadir na páxina **Orixes de datos**. Porase na fila para actualizar e mostrará o número de entidades como 0 ata que se sincronicen todas as táboas seleccionadas.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

A carga de datos pode levar moito tempo. Despois dunha actualización exitosa, os datos inxeridos pódense revisar desde o [**Entidades**](entities.md) páxina.

## <a name="edit-a-dataverse-managed-lake-data-source"></a>Editar unha orixe de datos de lago xestionado por Dataverse

Só edita a selección da entidades despois de crear a orixe de datos. Por exemplo, se se engadiron entidades adicionais a Dataverse e tamén quere importalos.
Para conectarse a outro lago de datos de Dataverse, [cree unha nova orixe de datos](#connect-to-a-dataverse-managed-lake).

1. Vaia a **Datos** > **Orixes de datos**.

1. A carón do orixe de datos que queres actualizar, selecciona **Editar**.

1. Seleccione entidades adicionais da lista de entidades dispoñible.

1. Fai clic **Gardar** para aplicar os seus cambios e volver ao **Fontes de datos** páxina.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="common-reasons-for-ingestion-errors-or-corrupted-data"></a>Motivos comúns para erros de inxestión ou datos corruptos

As seguintes comprobacións execútanse nos datos inxeridos para expoñer rexistros danados:

- O valor dun campo non coincide co tipo de datos da súa columna.
- Os campos conteñen caracteres que fan que as columnas non coincidan co esquema esperado. Por exemplo: comiñas con formato incorrecto, comiñas sen escape ou caracteres de nova liña.
- Se hai columnas datatime/date/datetimeoffset, o seu formato debe especificarse no modelo se non segue o formato ISO estándar.

### <a name="schema-or-data-type-mismatch"></a>Incompatibilidade de esquema ou tipo de datos

Se os datos non se axustan ao esquema, os rexistros clasifícanse como corruptos. Corrixe os datos de orixe ou o esquema e volva inxerir os datos.

### <a name="datetime-fields-in-the-wrong-format"></a>Campos de data e hora nun formato incorrecto

Os campos de data e hora da entidade non están en formato ISO nin en-US. O formato de data e hora predeterminado en Customer Insights é o formato en-EU. Todos os campos de data e hora dunha entidade deben estar no mesmo formato. Customer Insights admite outros formatos sempre que as anotacións ou os trazos se fagan a nivel de orixe ou de entidade no modelo ou manifest.json. Por exemplo:

**Modelo.json**

   ```json
      "annotations": [
        {
          "name": "ci:CustomTimestampFormat",
          "value": "yyyy-MM-dd'T'HH:mm:ss:SSS"
        },
        {
          "name": "ci:CustomDateFormat",
          "value": "yyyy-MM-dd"
        }
      ]   
   ```

  Nun manifest.json, o formato de data e hora pódese especificar a nivel de entidade ou a nivel de atributo. A nivel de entidade, use "exhibitsTraits" na entidade en *.manifest.cdm.json para definir o formato de datatime. No nivel de atributo, use "appliedTraits" no atributo de entityname.cdm.json.

**Manifest.json a nivel de entidade**

```json
"exhibitsTraits": [
    {
        "traitReference": "is.formatted.dateTime",
        "arguments": [
            {
                "name": "format",
                "value": "yyyy-MM-dd'T'HH:mm:ss"
            }
        ]
    },
    {
        "traitReference": "is.formatted.date",
        "arguments": [
            {
                "name": "format",
                "value": "yyyy-MM-dd"
            }
        ]
    }
]
```

**Entity.json a nivel de atributo**

```json
   {
      "name": "PurchasedOn",
      "appliedTraits": [
        {
          "traitReference": "is.formatted.date",
          "arguments" : [
            {
              "name": "format",
              "value": "yyyy-MM-dd"
            }
          ]
        },
        {
          "traitReference": "is.formatted.dateTime",
          "arguments" : [
            {
              "name": "format",
              "value": "yyyy-MM-ddTHH:mm:ss"
            }
          ]
        }
      ],
      "attributeContext": "POSPurchases/attributeContext/POSPurchases/PurchasedOn",
      "dataFormat": "DateTime"
    }
```

[!INCLUDE [footer-include](includes/footer-banner.md)]
