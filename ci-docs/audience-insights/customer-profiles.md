---
title: Ver perfís de clientes
description: Obteña unha vista combinada dos seus datos de clientes unificados.
ms.date: 09/30/2021
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
ms.openlocfilehash: 3a17716508a14020c56640c7d68f300a9d721af4
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 02/25/2022
ms.locfileid: "8354879"
---
# <a name="customer-profiles"></a>Perfís de clientes

A páxina **Clientes** mostra unha vista combinada dos perfís de clientes unificados. Os perfís dos clientes están dispoñibles unha vez que vostede [creou a entidade de cliente unificado](data-unification.md). A páxina permítelle buscar clientes e definir o índice para esa busca.

Os clientes poden ser persoas ou organizacións. Cada perfil de cliente está representado por un mosaico. Use os controis de paxinación para obter máis rexistros. A tarxeta mostra campos da entidade *Cliente* definida no **Índice de busca e filtro**. Seleccione un mosaico para ver os datos do cliente seleccionado nunha páxina dedicada chamada [Páxina de detalles do cliente](customer-profiles.md#customer-details-page).

> [!div class="mx-imgBorder"] 
> ![Páxina de clientes que mostra os mosaicos de resultados](media/customers-page-result-tiles-B2C.png "Páxina de clientes que mostra os mosaicos de resultados")

> [!NOTE]
> Se non pode ver os mosaicos cando selecciona **Clientes** na navegación, o seu administrador precisa [definir polo menos un atributo que se pode buscar](search-filter-index.md) no **Índice de busca e filtro**.

## <a name="search-for-customers"></a>Buscar clientes

Busque clientes introducindo un nome ou algún outro atributo na caixa de busca. A busca só funciona dentro da entidade de _Cliente_ creada durante o proceso de unificación de datos.

Como administrador, pode configurar os atributos que se poden buscar usando a páxina **Índice de busca e filtro**. Para obter máis información, vaia a [Xestionar o índice de busca e filtro](search-filter-index.md).

## <a name="filter-customers"></a>Filtrar clientes

Pode filtrar os clientes polos campos de entidade de _Cliente_. De xeito semellante á busca, o administrador primeiro deberá definir os campos como filtrables usando a páxina **Índice de busca e filtro**.

1. Seleccione **Mostrar filtros** na páxina **Clientes**.

1. Marque as caixas situadas xunto aos atributos polos que desexa filtrar os clientes.

1. Elimine os filtros seleccionando **Limpar filtros** na páxina **Clientes**.

## <a name="customer-details-page"></a>Páxina de detalles do cliente

Seleccione calquera dos mosaicos de clientes para abrir a **Páxina de detalles do cliente**. Esta vista contén información unificada do cliente seleccionado. Os datos do cliente inclúen o seguinte contido:

**Mosaico do perfil do cliente**: este mosaico mostra os diferentes valores da entidade de _Cliente_ unificada. Se un campo non ten valor para o perfil de cliente seleccionado, non se amosará. O mosaico estrutúrase en seccións:  
  - A primeira sección mostra un conxunto predefinido de campos seguidos de todos os campos que forman parte do índice de busca e filtro. Todos os campos relacionados co enderezo combínanse nunha única liña se o perfil contén estes campos. 
  - **Contactos para este cliente**: en contornos para contas comerciais, verá todos os contactos relacionados con este cliente como a segunda sección. Cada contacto móstrase cos seus campos. Os campos baleiros están ocultos.
  - **Campos adicionais**: mostra os campos restantes do cliente seleccionado, excepto os ID. 
  - **ID**: enumera todos os ID situados baixo o seu nome de entidade correspondente. Os campos identifícanse como ID pola súa semántica, que os ordena como tales.

**Cronoloxía da actividade**: mostra datos se configurou actividades. A vista de cronoloxía contén actividades ordenadas cronoloxicamente polo cliente seleccionado, comezando pola actividade máis recente. Para obter máis información, vaia a [Actividades de cliente](activities.md).

**Conclusións**:  
  - **Medidas**: mostra se configurou unha ou máis medidas de atributo do cliente. Inclúen KPI calculados arredor dos seus clientes a nivel de cliente individual. Para obter máis información, vaia a [Definir e xestionar medidas](measures.md).

  - **Intereses potenciais, marcas potenciais**: mostra se configurou un enriquecemento de afinidade de marca ou interese. Representa posibles intereses e afinidades para as marcas baseadas noutros clientes cuxo perfil é similar ao perfil de cliente seleccionado. Para obter máis información, vaia a [Enriquecer perfís de clientes con afinidades de marca e interese](enrichment-microsoft.md).

Para volver á páxina de busca de clientes, seleccione **Volver a Clientes**.

## <a name="next-steps"></a>Pasos seguintes

[Engada máis orixes de datos](data-sources.md), [enriqueza perfís unificados](enrichment-hub.md) ou [cree segmentos](segments.md) para traballar con perfís de clientes unificados noutras aplicacións.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
