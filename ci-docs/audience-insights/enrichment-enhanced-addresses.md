---
title: Enriquecemento de mellora de enderezos (contén vídeo)
description: Enriqueza e normalice a información dos enderezos dos perfís de clientes cos modelos de Microsoft.
ms.date: 01/19/2022
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
ms.openlocfilehash: 067757019078d3a46b224ba259d2d097dfbbe381
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 02/25/2022
ms.locfileid: "8353634"
---
# <a name="enrichment-of-customer-profiles-with-enhanced-addresses"></a>Enriquecemento dos perfís de clientes con enderezos mellorados

Os enderezos dos seus datos poden estar sen estruturar, incompletos ou ser incorrectos. Use os modelos de Microsoft para normalizar e enriquecer os seus enderezos en [formato Common Data Model](/common-data-model/schema/core/applicationcommon/address) para unha mellor precisión e información.

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

Podes ver unha mostra dos datos enriquecidos no **Vista previa de clientes enriquecidos** tella. Seleccione **Ver máis** e selecciona o **Datos** para acceder a unha vista detallada de cada perfil enriquecido.

### <a name="overview-card"></a>Tarxeta xeral

A tarxeta de visión xeral mostra detalles sobre a cobertura do enriquecemento. 

* **Enderezos procesados e modificados** : O número de perfís de clientes con enderezos que se enriqueceron con éxito.

* **Enderezos procesados e non modificados** : O número de perfís de clientes con enderezos recoñecidos pero non modificados. Normalmente ocorre cando os datos de entrada son válidos e non se poden mellorar co enriquecemento.

* **Enderezos non procesados e non modificados** : O número de perfís con enderezos que non foron recoñecidos. Normalmente para datos de entrada que non son válidos ou non admitidos polo enriquecemento.

## <a name="next-steps"></a>Pasos seguintes

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](../includes/footer-banner.md)]
