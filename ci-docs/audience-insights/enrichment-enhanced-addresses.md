---
title: Enriquecemento de mellora dos enderezos
description: Enriqueza e normalice a información dos enderezos dos perfís de clientes cos modelos de Microsoft.
ms.date: 07/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: fb3fee72b3420c636d549b600c468c574ee33a662bfafd096247dfddf40150bd
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032664"
---
# <a name="enrichment-of-customer-profiles-with-enhanced-addresses"></a>Enriquecemento dos perfís de clientes con enderezos mellorados

Os enderezos dos seus datos poden estar sen estruturar, incompletos ou ser incorrectos. Use os modelos de Microsoft para normalizar e enriquecer os seus enderezos en [formato Common Data Model](/common-data-model/schema/core/applicationcommon/address) para unha mellor precisión e información.

## <a name="how-we-enhance-addresses"></a>Como melloramos os enderezos

O noso modelo pasa por un proceso de dous pasos para mellorar un enderezo. En primeiro lugar, analiza o enderezo para identificar os seus compoñentes e colócaos nun formato estruturado. Despois, empregamos a IA para corrixir, completar e estandarizar os valores do enderezo.

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

Os enderezos mellorados só funcionan cos valores que xa existen nos seus datos de enderezos inxeridos. O modelo non: 

1. Comproba se o enderezo é válido.
2. Comproba se os valores, como os códigos postais ou os nomes de rúas, son válidos.
3. Modifica os valores que non recoñece.

O modelo utiliza técnicas baseadas na aprendizaxe automática para mellorar os enderezos. Aínda que aplicamos un limiar de confianza elevado para cando o modelo cambia un valor de entrada, como con calquera modelo baseado na aprendizaxe automática, non se garante a precisión do 100 %.

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

Os enderezos deben conter un valor de país ou rexión. Non procesamos enderezos de países ou rexións que non se admitan nin enderezos nos que non se proporcione ningún país ou rexión.

## <a name="configure-the-enrichment"></a>Configurar o enriquecemento

1. Vaia a **Datos** > **Enriquecemento**.

1. Seleccione **Enriquecer os meus datos** no mosaico **Enderezos mellorados**.

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="Captura de pantalla do mosaico Enderezos mellorados.":::

1. Seleccione o **Conxunto de datos do cliente** e escolla a entidade que conteña os enderezos que quere enriquecer. Pode seleccionar a entidade *Cliente* para enriquecer enderezos en todos os seus perfís de clientes ou seleccionar unha entidade de segmento para enriquecer enderezos só nos perfís de clientes contidos nese segmento.

1. Escolla como se formatan os enderezos nos conxuntos de datos. Escolla **Enderezo cun único atributo** se os enderezos dos seus datos usan só un campo. Escolla **Enderezo con varios atributos** se os enderezos dos seus datos usan máis dun campo de datos.

   > [!NOTE]
   > O país/rexión é obrigatorio tanto nos enderezos de atributo único como de varios atributos. Os enderezos que non conteñan valores de país ou rexión válidos ou admitidos non se enriquecerán.

1.  Asigne os campos de enderezo da súa entidade de cliente unificada.

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="Páxina de asignación de campos de enderezos mellorados.":::

1. Seleccione **Seguinte** para concluír a asignación do campo.

1. Proporcione un nome para o enriquecemento e a entidade de saída.

1. Seleccione **Gardar enriquecemento** despois de revisar as súas opcións.

## <a name="enrichment-results"></a>Resultados de enriquecemento

Para iniciar o proceso de enriquecemento, seleccione **Executar** na barra de comandos. Tamén pode deixar que o sistema execute o enriquecemento automaticamente como parte dunha [actualización programada](system.md#schedule-tab). O tempo de procesamento depende do tamaño dos datos dos clientes.

Despois de completar o proceso de enriquecemento, pode consultar os datos dos perfís de clientes recentemente enriquecidos en **Os meus enriquecementos**. Ademais, atopará a hora da última actualización e o número de perfís enriquecidos.

Pode acceder a unha vista detallada de cada perfil enriquecido seleccionando **Ver datos enriquecidos**.

## <a name="next-steps"></a>Pasos seguintes

Crear sobre os seus datos enriquecidos de clientes. Cree [segmentos](segments.md) e [medidas](measures.md), e incluso [exporte os datos](export-destinations.md) para ofrecer experiencias personalizadas aos seus clientes.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
