---
title: Ver perfís de clientes
description: Consulta os datos unificados dos teus clientes, incluíndo a busca e o filtro
ms.date: 06/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
searchScope:
- ci-customers-page
- ci-customer-card
- ci-activities
- ci-activities-wizard
- customerInsights
ms.openlocfilehash: 6cdf47e6997f230811dcb0f2cf5542f3a6db2367
ms.sourcegitcommit: c45c3e044034bf866b0662f80a59166cee4ababe
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 07/22/2022
ms.locfileid: "9188091"
---
# <a name="view-customer-profiles"></a>Ver perfís de clientes

Os perfís de clientes están dispoñibles unha vez que vostede [crear o unificado *Cliente* entidade](data-unification.md). A vista combinada dos seus perfís de cliente unificados móstrase no **Clientes** páxina. Os clientes poden ser persoas ou organizacións.

Vaia ao **Clientes** páxina para ver os seus clientes e os seus perfís. Cada perfil de cliente está representado por un mosaico. Use os controis de paxinación para obter máis rexistros. A tarxeta mostra campos da entidade *Cliente* definida no **Índice de busca e filtro**. A orde dos campos dentro de cada tarxeta é escollida polo sistema.

> [!NOTE]
> Se non podes ver as fichas cando seleccionas **Clientes**, o teu administrador ten que facelo [definir polo menos un atributo buscable](search-filter-index.md) no **Índice de busca e filtro**.

:::image type="content" source="media/customers-page-result-tiles-B2C.png" alt-text="Páxina de clientes que mostra mosaicos de resultados.":::

Seleccione calquera das seguintes accións:
- [Ver os detalles do cliente](#view-customer-details)
- [Xestiona o índice de busca e filtro](search-filter-index.md) (só administradores)
- [Filtrar clientes](#filter-customers)
- **Expande tarxetas** ou **Contraer tarxetas** para ampliar ou contraer a información mostrada no mosaico do cliente
- **Ordenar por** un atributo particular
- [Buscar clientes](#search-for-customers)

  > [!NOTE]
  > Para usar a busca e o filtro, un administrador debe configurar os atributos que se poden buscar e definir os campos filtrables mediante o índice de busca e filtro.

## <a name="search-for-customers"></a>Buscar clientes

Busca clientes introducindo un nome ou algún outro atributo **Busca clientes**. Os atributos que se poden buscar son definidos polo administrador e proceden do unificado *Cliente* entidade.

> [!NOTE]
> **Corda** é o único tipo de datos que se inclúe na busca. Usalo en **Busca clientes** campo da páxina Clientes para buscar clientes.

## <a name="filter-customers"></a>Filtrar clientes

Filtra os clientes polo *Cliente* campos da entidade. Os campos filtrables son definidos polo administrador.

1. No **Clientes** páxina, seleccione **Mostrar filtros**. Aparece o panel Filtro.

1. Marque as caixas situadas xunto aos atributos polos que desexa filtrar os clientes.

1. Elimina todos os filtros seleccionando **Borrar filtros** ou desmarque unha caixa de verificación situada xunto a un atributo seleccionado.

1. Seleccione **Ocultar filtros** para pechar o panel do filtro.

1. Para gardar os resultados do filtro como a [segmento](segments.md), seleccione **Garda os filtros como segmento**.
   1. Introduza un nome para o segmento.
   1. Seleccione **Gardar** para gardar o segmento.
   1. Escolle se queres executar o segmento agora seleccionando **Activar** ou executalo **Máis tarde**.

## <a name="view-customer-details"></a>Ver os detalles do cliente

No **Clientes** páxina, seleccione un mosaico de cliente para ver os detalles do cliente seleccionado.

:::image type="content" source="media/customers-details-B2C.png" alt-text="Páxina de detalles do cliente.":::

Os detalles do cliente inclúen:

**Ficha do perfil do cliente** mostra os diferentes valores do unificado *Cliente* entidade. Se un campo non ten ningún valor para o perfil de cliente seleccionado, non se mostrará excepto o campo do enderezo. O mosaico estrutúrase en seccións:

- A primeira sección mostra un conxunto predefinido de campos seguidos de todos os campos que forman parte do índice de busca e filtro. Todos os campos relacionados co enderezo combínanse nunha única liña, que amosa aínda que o perfil non conteña información sobre o enderezo.
- **Contactos para este cliente** mostrar en contornos para contas empresariais. Cada contacto móstrase cos seus campos. Os campos baleiros están ocultos.
- **Campos adicionais** mostra os campos restantes do cliente seleccionado, excepto os ID.
- **ID** enumera todos os ID baixo o seu nome de entidade correspondente. Os campos identifícanse como ID pola súa semántica.

**Cronograma da actividade** mostra os datos se o configuraches [actividades](activities.md). A vista de cronoloxía contén actividades ordenadas cronoloxicamente polo cliente seleccionado, comezando pola actividade máis recente.

**Conclusións**:

- **Medidas** mostrar se o configuraches [medidas de atributos do cliente](measures.md). Inclúen KPI calculados arredor dos seus clientes a nivel de cliente individual.

- **Intereses potenciais, marcas potenciais** mostrar se configuraches a [enriquecemento da afinidade de marca ou interese](enrichment-microsoft.md). Representa posibles intereses e afinidades para as marcas baseadas noutros clientes cuxo perfil é similar ao perfil de cliente seleccionado.

Para volver ao **Clientes** páxina, seleccione **Volver a Clientes**.

## <a name="next-steps"></a>Pasos seguintes

[Engada máis orixes de datos](data-sources.md), [enriqueza perfís unificados](enrichment-hub.md) ou [cree segmentos](segments.md) para traballar con perfís de clientes unificados noutras aplicacións.

[!INCLUDE [footer-include](includes/footer-banner.md)]
