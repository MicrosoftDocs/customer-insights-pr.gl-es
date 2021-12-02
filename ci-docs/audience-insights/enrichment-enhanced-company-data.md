---
title: Mellora dos datos da empresa
description: Enriquece e normaliza os datos da empresa cos modelos de Microsoft.
ms.date: 11/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: d11700c87f31cedc40d32b201251d8a9e2e2c312
ms.sourcegitcommit: dfc4843cc78857f1e3ca49d7b938e3ba77969169
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 11/15/2021
ms.locfileid: "7813916"
---
# <a name="enrichment-of-company-profiles-with-enhanced-company-data"></a>Enriquecemento dos perfís da empresa con datos da empresa mellorados

Use os modelos de Microsoft e os datos compilados da empresa para corrixir, complementar e estandarizar os perfís da súa empresa. Usaremos o [Formato de modelo de datos común](/common-data-model/schema/core/applicationcommon/account) para unha mellor precisión e coñecementos.

## <a name="how-we-enhance-company-data"></a>Como melloramos os datos da empresa

O noso modelo pasa por un proceso de dous pasos para mellorar o perfil dunha empresa. En primeiro lugar, normaliza o nome da empresa. Por exemplo, *Microsoft Corp* corrixiranse e estandarizaranse para *Microsoft Corporation*. Tenta atopar unha coincidencia nos datos da empresa compilados por Microsoft. Se se atopa unha coincidencia, enriquecemos o perfil da empresa con información dos datos compilados da nosa empresa, incluído o nome da empresa.


### <a name="example"></a>Exemplo

A información da túa empresa pode non seguir un formato estandarizado e conter erros ortográficos. O modelo tenta solucionar estes problemas e crear información coherente.

```Input
Microsft
```

```Output
- AccountName: Microsoft Corporation
- MainPhoneNumber: 8006427676
- Website: https://www.microsoft.com/
- Street1: One Microsoft Way
- City: Redmond
- StateOrProvince: Washington
- County: King
- ZipOrPostalCode: 98052
- CountryOrRegion: United States
```

## <a name="limitations"></a>Limitacións

Hai algunhas limitacións cos datos mellorados. Os elementos da lista a continuación non son compatibles co modelo.

1.  Confirmar a identidade da empresa. Non verificamos se a entrada é unha organización existente ou se unha empresa utiliza a saída como o seu nome estándar.
2.  Cubra amplamente as empresas a nivel mundial. Os datos da empresa compilados por Microsoft teñen cobertura global, pero ofrecen a maior parte da cobertura en Australia, Canadá, Reino Unido e Estados Unidos.
3.  Estandarizar os enderezos das empresas a nivel mundial. Actualmente admitimos a estandarización de enderezos nestes países ou rexións: Australia, Canadá, Francia, Alemaña, Italia, Xapón, Reino Unido e Estados Unidos.
4.  Garantir a precisión ou frescura dos datos. Dado que a información empresarial adoita cambiar, non podemos garantir que os datos mellorados da empresa proporcionados sexan sempre exactos ou actualizados.

## <a name="configure-the-enrichment"></a>Configurar o enriquecemento

1. Vaia a **Datos** > **Enriquecemento**.

1. Seleccione **Enriquece os meus datos** no **Datos da empresa mellorados** tella.

   :::image type="content" source="media/enhanced-company-data-tile.png" alt-text="Mosaico de enriquecemento no centro de enriquecemento para os datos da empresa.":::

1. Seleccione o **Conxunto de datos do cliente** e escolla a entidade que conteña os enderezos que quere enriquecer. Pode seleccionar a entidade *Cliente* para enriquecer enderezos en todos os seus perfís de clientes ou seleccionar unha entidade de segmento para enriquecer enderezos só nos perfís de clientes contidos nese segmento.

1. Seleccione que tipo de campos dos perfís da súa empresa se deben usar para facer coincidir os datos da empresa compilados por Microsoft. Esta selección afectará aos campos de asignación aos que ten acceso no seguinte paso.

1.  Asigne os campos da empresa da súa entidade cliente unificada. Cantos máis identificadores de clave e campos mapees, máis probabilidade de que exista unha taxa de coincidencia máis alta.

    :::image type="content" source="media/enhanced-company-data-mapping.png" alt-text="Paso de mapeo de datos ao configurar o enriquecemento dunha empresa.":::

1. Seleccione **Seguinte** para concluír a asignación do campo.

1. Proporcione un nome para o enriquecemento e a entidade de saída.

1. Seleccione **Gardar enriquecemento** despois de revisar as súas opcións.

## <a name="enrichment-results"></a>Resultados de enriquecemento

Para iniciar o proceso de enriquecemento, seleccione **Executar** na barra de comandos. Tamén pode deixar que o sistema execute o enriquecemento automaticamente como parte dunha [actualización programada](system.md#schedule-tab). O tempo de procesamento depende do tamaño dos datos dos clientes.

Despois de completar o proceso de enriquecemento, pode consultar os datos dos perfís de clientes recentemente enriquecidos en **Os meus enriquecementos**. Ademais, atopará a hora da última actualización e o número de perfís enriquecidos.

Pode acceder a unha vista detallada de cada perfil enriquecido seleccionando **Ver datos enriquecidos**.

## <a name="next-steps"></a>Pasos seguintes

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](../includes/footer-banner.md)]