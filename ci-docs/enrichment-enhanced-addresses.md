---
title: Enriquece os perfís de clientes con enderezos mellorados (contén vídeo)
description: Enriqueza e normalice a información dos enderezos dos perfís de clientes cos modelos de Microsoft.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
searchScope:
- ci-data-sources-enrichment
- ci-data-sources-enrichment-details
- ci-enrichments
- ci-enrichment-wizard
- customerInsights
ms.openlocfilehash: 01f1c917c75e932cc69f4c7251e57524fc859dce
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082069"
---
# <a name="enrich-customer-profiles-with-enhanced-addresses"></a>Enriquece os perfís de clientes con enderezos mellorados

Os enderezos dos seus datos poden estar sen estruturar, incompletos ou ser incorrectos. Use os modelos de Microsoft para normalizar e enriquecer os seus enderezos en [formato Common Data Model](/common-data-model/schema/core/applicationcommon/address) para unha mellor precisión e información.

Tamén podes [enriquecer enderezos en fontes de datos](data-sources-enrichment.md) para mellorar a precisión da coincidencia no proceso de unificación de datos. 

## <a name="how-we-enhance-addresses"></a>Como melloramos os enderezos

O noso modelo pasa por un proceso de dous pasos para mellorar un enderezo. En primeiro lugar, analiza o enderezo para identificar os seus compoñentes e colócaos nun formato estruturado. Despois, empregamos a IA para corrixir, completar e estandarizar os valores do enderezo.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWNewo]

### <a name="example"></a>Exemplo

A información do enderezo pode ter un formato non estándar e conter erros ortográficos. O modelo pode solucionar estes problemas e crear enderezos coherentes en perfís de clientes unificados.

```Input
4567 w main stret californa missouri 54321 us
```

```Output
- Street1: 4567 W Main St
- City: California
- StateOrProvince: MO
- ZipOrPostalCode: 54321
- CountryOrRegion: United States of America

- Address: 4567 W Main St, California, MO, 54321, United States of America
```

### <a name="limitations"></a>Limitacións

Os enderezos mellorados só funcionan cos valores que xa existen nos datos de enderezos inxeridos. O modelo non:

1. Comproba se o enderezo é válido.
2. Comproba se os valores, como os códigos postais ou os nomes de rúas, son válidos.
3. Modifica os valores que non recoñece.

O modelo utiliza técnicas baseadas na aprendizaxe automática para mellorar os enderezos. Como con calquera modelo baseado en aprendizaxe automática, non se garante unha precisión do 100 %.

## <a name="supported-countries-or-regions"></a>Países ou rexións admitidos

Actualmente admitimos enderezos enriquecidos nestes países ou rexións:

- Australia
- O Canadá
- Francia
- Alemaña
- Italia
- O Xapón
- O Reino Unido
- Os Estados Unidos

## <a name="configure-the-enrichment"></a>Configurar o enriquecemento

1. Vaia a **Datos** > **Enriquecemento** e seleccione o separador **Descubrir**.

1. Seleccione **Enriquecer os meus datos** no mosaico **Enderezos mellorados**.

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="Captura de pantalla do mosaico Enderezos mellorados.":::

1. Revisa a vista xeral e, a continuación, selecciona **A continuación**.

1. Seleccione o **Conxunto de datos do cliente** e escolle o perfil ou segmento que queres enriquecer. O *Cliente* a entidade enriquece todos os seus perfís de clientes mentres que un segmento enriquece só os perfís de clientes contidos nese segmento.

1. Escolla como se formatan os enderezos nos conxuntos de datos. Escolla **Enderezo cun único atributo** se os enderezos dos seus datos usan só un campo. Escolla **Enderezo con varios atributos** se os enderezos dos seus datos usan máis dun campo de datos.

1. Seleccione **A continuación** e mapea os campos de enderezos da túa entidade cliente unificada.

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="Páxina de asignación de campos de enderezos mellorados.":::

   > [!NOTE]
   > O país/rexión é obrigatorio tanto nos enderezos de atributo único como de varios atributos. Os enderezos que non conteñan valores de país ou rexión válidos ou admitidos non se enriquecerán.

1. Seleccione **Seguinte** para concluír a asignación do campo.

1. Proporcionar a **Nome** para o enriquecemento e o **Entidade de saída**.

1. Seleccione **Gardar enriquecemento** despois de revisar as súas opcións.

## <a name="view-enrichment-results"></a>Ver resultados de enriquecemento

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

O **Número de clientes enriquecidos por campo** proporciona un detalle da cobertura de cada campo enriquecido.

### <a name="overview-card"></a>Tarxeta xeral

O **Os clientes cambian a visión xeral** A tarxeta mostra detalles sobre a cobertura do enriquecemento:

- **Enderezos procesados e modificados** : O número de perfís de clientes con enderezos que se enriqueceron con éxito.
- **Enderezos procesados e non modificados** : O número de perfís de clientes con enderezos que foron recoñecidos pero non modificados. Normalmente ocorre cando os datos de entrada son válidos e non se poden mellorar co enriquecemento.
- **Enderezos non procesados e non modificados** : número de perfís con enderezos que non foron recoñecidos. Normalmente para datos de entrada non válidos ou non admitidos polo enriquecemento.

## <a name="next-steps"></a>Pasos seguintes

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
