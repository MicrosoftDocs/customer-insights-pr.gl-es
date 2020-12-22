---
title: Ver perfís de clientes
description: Obteña unha vista combinada dos seus datos de clientes unificados.
ms.date: 12/01/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 13308c2f40cda0d7e813b4d94ab47d53b5ce2115
ms.sourcegitcommit: a6e7df90d61450e00886753eb5db116f2f35bb6c
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 12/01/2020
ms.locfileid: "4653888"
---
# <a name="customer-profiles"></a>Perfís de clientes

A páxina **Clientes** mostra unha vista combinada dos seus clientes, baseada nos datos dos perfís recompilados de [todas as fontes de datos](data-sources.md). Os perfís de clientes están dispoñibles unha vez [creada a entidade de cliente unificada](data-unification.md). Asegúrese de completar o proceso de unificación de datos para obter unha visión máis rica dos seus clientes. A páxina tamén lle permite buscar clientes.

Os clientes poden ser persoas ou organizacións (vista previa). Cada perfil de cliente ou organización está representado por un mosaico. Seleccione un mosaico para ver información adicional sobre ese cliente ou organización específico. Use os controis de paxinación do final da páxina para ver rexistros adicionais.

> [!div class="mx-imgBorder"] 
> ![Perfís de cliente B2C](media/profiles-customers.png "Perfís de cliente B2C")

Organizacións (vista previa)
> [!div class="mx-imgBorder"] 
> ![Perfís de cliente B2B](media/profile-customers-b2b.png "Perfís de cliente B2B")

> [!NOTE]
> Se non ve os mosaicos ao seleccionar **Clientes** na navegación, o seu administrador precisará [definir polo menos un atributo que se poida buscar](search-filter-index.md) no **Índice de busca e filtro**.

## <a name="search-for-customers"></a>Buscar clientes

Busque clientes introducindo un nome ou algún outro atributo na caixa de busca. A busca só funciona dentro da entidade de Perfil do cliente creada durante o proceso de unificación de datos.

Como administrador, pode configurar os atributos que se poden buscar usando a páxina **Índice de busca e filtro**. Para obter máis información, consulte [Xestionar o índice de busca e filtro](search-filter-index.md).

## <a name="filter-customers"></a>Filtrar clientes

Pode filtrar clientes polos campos de entidade de perfil do cliente. De xeito semellante á busca, o administrador primeiro deberá definir os campos como filtrables usando a páxina **Índice de busca e filtro**.

1. Na páxina **Clientes**, seleccione **Filtrar**.

2. Marque as caixas situadas xunto aos atributos polos que desexa filtrar os clientes.

   > [!div class="mx-imgBorder"] 
   > ![Perfís de clientes](media/profiles-customers3.png "Perfís de clientes")

3. Elimine os filtros seleccionando **Limpar filtros** na páxina **Clientes**.

##  <a name="customer-details-page"></a>Páxina de detalles do cliente

Seleccione calquera dos mosaicos de clientes para abrir a **Páxina de detalles do cliente**. Esta vista contén información unificada do cliente seleccionado.

Os detalles do cliente inclúen:

-   **Ficha do perfil do cliente:** Este mosaico mostra os diferentes valores da entidade de perfil de cliente unificado. Estes detalles poden incluír enderezo de correo electrónico, nome, cidade etc. 

-   **Intereses potenciais, marcas potenciais:** Mostra se configurou un enriquecemento propio. Representa posibles intereses e afinidades para as marcas que poida ter un cliente cun perfil similar a este. Para obter máis información, consulte [Enriquecer os perfís de clientes con afinidades de marca e intereses](enrichment-microsoft-graph.md).

-   **Medidas:** Mostra se configurou unha ou máis medidas dun tipo específico: medidas de atributo de cliente. Inclúen KPI calculados arredor dos seus clientes a nivel de cliente individual. Para obter máis información, consulte [Definir e xestionar medidas](measures.md).

-   **Cronoloxía da actividade:** Mostra se configurou actividades. A vista de cronoloxía contén actividades ordenadas cronoloxicamente deste cliente, comezando pola actividade máis recente. Para obter máis información, consulte [Actividades do cliente](activities.md).

Seleccione **Volver a Clientes** para volver á páxina de busca de clientes.

## <a name="next-steps"></a>Pasos seguintes

[Engada máis orixes de datos](data-sources.md) ou [cree segmentos de clientes](segments.md).
