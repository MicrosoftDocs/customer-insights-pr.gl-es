---
title: Enriquece os perfís das empresas con datos mellorados da empresa
description: Enriquece e normaliza os datos da empresa cos modelos de Microsoft.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 131ef3d1e123628779609ddec368cfef8f4d607e
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "9054246"
---
# <a name="enrich-company-profiles-with-enhanced-company-data"></a>Enriquece os perfís das empresas con datos mellorados da empresa

Use os modelos de Microsoft e os datos compilados da empresa para corrixir, complementar e estandarizar os perfís da súa empresa. Usaremos o [Formato do modelo de datos común](/common-data-model/schema/core/applicationcommon/account) para unha mellor precisión e coñecementos.

Tamén podes [mellorar os datos da empresa nas fontes de datos](data-sources-enrichment.md) para mellorar a precisión da coincidencia no proceso de unificación de datos.

Para as empresas públicas dos Estados Unidos, está dispoñible información como ingresos, cotización de accións, industria e moito máis.  

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

O modelo non:

- Confirmar a identidade da empresa. Non verificamos se a entrada é unha organización existente ou se unha empresa utiliza a saída como o seu nome estándar.
- Cubra amplamente as empresas a nivel mundial. Os datos da empresa compilados por Microsoft teñen cobertura global, pero ofrecen a maior parte da cobertura en Australia, Canadá, Reino Unido e Estados Unidos.
- Estandarizar os enderezos das empresas a nivel mundial. Actualmente admitimos a estandarización de enderezos nestes países ou rexións: Australia, Canadá, Francia, Alemaña, Italia, Xapón, Reino Unido e Estados Unidos.
- Garantir a precisión ou frescura dos datos. Dado que a información empresarial adoita cambiar, non podemos garantir que os datos mellorados da empresa proporcionados sexan sempre exactos ou actualizados.

## <a name="configure-the-enrichment"></a>Configurar o enriquecemento

1. Vaia a **Datos** > **Enriquecemento** e seleccione o separador **Descubrir**.

1. Seleccione **Enriquece os meus datos** no **Datos da empresa mellorados** tella.

   :::image type="content" source="media/enhanced-company-data-tile.png" alt-text="Mosaico de enriquecemento no centro de enriquecemento para os datos da empresa.":::

1. Revisa a vista xeral e, a continuación, selecciona **A continuación**.

1. Seleccione o **Conxunto de datos do cliente** e escolle o perfil ou segmento que queres enriquecer. O *Cliente* a entidade enriquece todos os seus perfís de clientes mentres que un segmento enriquece só os perfís de clientes contidos nese segmento.

1. Seleccione que tipo de campos dos perfís da súa empresa quere utilizar para a correspondencia cos datos da empresa compilados por Microsoft. Esta selección afectará aos campos de asignación aos que ten acceso no seguinte paso.

1. Seleccione **Seguinte**.

1. Asigne os campos da súa empresa aos datos da empresa de Microsoft. Para unha maior precisión de coincidencia, engade máis campos.

    :::image type="content" source="media/enhanced-company-data-mapping.png" alt-text="Paso de mapeo de datos ao configurar o enriquecemento dunha empresa.":::

1. Seleccione **Seguinte** para concluír a asignación do campo.

1. Proporcionar a **Nome** para o enriquecemento e o **Entidade de saída**.

1. Seleccione **Gardar enriquecemento** despois de revisar as súas opcións.

1. Seleccione **Corre** para iniciar o proceso de enriquecemento ou pechar para volver ao **Enriquecementos** páxina.

## <a name="view-enrichment-results"></a>Ver resultados de enriquecemento

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

### <a name="overview-card"></a>Tarxeta xeral

O **Os clientes cambian a visión xeral** mosaico mostra detalles sobre a cobertura do enriquecemento

- **Empresas procesadas e modificadas** : O número de perfís de empresas de clientes que se enriqueceron con éxito.
- **Empresas tramitadas e non modificadas** : O número de perfís de empresas de clientes que foron recoñecidos pero non modificados. Isto ocorre normalmente cando os datos de entrada son válidos e non se poden mellorar co enriquecemento.
- **Empresas non tramitadas e non modificadas** : número de perfís de empresas de clientes que non foron recoñecidos. Isto ocorre normalmente para os datos de entrada que non son válidos ou non son compatibles co enriquecemento.

## <a name="next-steps"></a>Pasos seguintes

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
