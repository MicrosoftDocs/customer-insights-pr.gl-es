---
title: Xestiona o índice de busca e filtro para perfís de clientes
description: Busque rapidamente información sobre perfís de clientes unificados e filtre por atributos especificados.
ms.date: 07/22/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
searchScope:
- ci-search-filter
- customerInsights
ms.openlocfilehash: dfbfcbff3ffb3e4483252377e591229631d38556
ms.sourcegitcommit: c45c3e044034bf866b0662f80a59166cee4ababe
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 07/22/2022
ms.locfileid: "9187907"
---
# <a name="manage-the-search--filter-index-for-customer-profiles"></a>Xestiona o índice de busca e filtro para perfís de clientes

O resultado de unificar os datos dos seus clientes é a *Cliente* entidade que ofrece unha visión unificada da súa base total de clientes. Para que os usuarios o fagan rapidamente [buscar información sobre un cliente específico ou grupo de clientes](customer-profiles.md), un administrador debe configurar o **Busca** e **Filtro** capacidades para o **Clientes** páxina.

   :::image type="content" source="media/search-filter.png" alt-text="Buscar filtro":::

## <a name="define-searchable-attributes-and-indexed-fields"></a>Defina atributos de busca e campos indexados

Se é a primeira vez que define atributos que se poden buscar como administrador, defina primeiro os campos indexados. Suxerímoslle que escolla todos os atributos cos que os usuarios poidan buscar e filtrar clientes na páxina **Clientes**. Só os atributos que existen no *Cliente* pódese especificar a entidade creada durante o proceso de unificación de datos.

1. Ir a **Clientes** e selecciona **Índice de busca e filtro**.

1. Seleccione **+ Engadir**.

1. Seleccione os atributos da lista que quere engadir como campos indexados e prema **Solicitar**.

1. Para engadir máis atributos, selecciona **Engadir**. Para eliminar un atributo seleccionado, seleccione o atributo e despois **Eliminar**.

   :::image type="content" source="media/search-filter-index.png" alt-text="Busca e filtra páxina de índice.":::

1. Seleccione **Corre** unha vez que estea preparado para aplicar a súa configuración de busca e filtro. Despois de procesar os cambios, visualízaos na páxina [tarxetas de cliente na páxina Cliente](customer-profiles.md).

## <a name="define-filtering-options-for-a-given-attribute"></a>Defina opcións de filtrado para un atributo dado

Configure os campos que se poden usar para filtrar os clientes no **Clientes** páxina.

1. Ir a **Clientes** e selecciona **Índice de busca e filtro**.

1. Seleccione un atributo e **Engadir filtro**. Define o número de resultados e a orde na que se organizarán. Dependendo do tipo de datos do atributo, aparece un dos seguintes paneis.

   - Atributos de tipo cadea: especifique o número de resultados desexados no ficheiro **Filtro de cadea** panel e a política de orde pola que se organizarán.

   - Atributos de tipo numérico: especifique os intervalos incluídos no **Filtro de número** panel e a política de orde pola que se organizarán.

   - Atributos de tipo de data: especifique os intervalos incluídos no **Filtro de data** panel e a política de orde pola que se organizarán.

1. Seleccione **Aceptar**. Repita para todos os atributos polos que quere filtrar.

1. Seleccione **Corre** unha vez que estea preparado para aplicar a súa configuración de busca e filtro. Despois de procesar os cambios, visualízaos na páxina [tarxetas de cliente na páxina Cliente](customer-profiles.md).

## <a name="view-indexed-customer-fields"></a>Ver campos de clientes indexados

O **Índice de busca e filtrado** páxina mostra a seguinte información:

- **Nome** : Representa o nome do atributo tal e como aparece no ficheiro *Cliente* entidade.
- **Tipo de datos**: especifica se o tipo de datos é unha cadea, un número ou unha data.
- **Incluído na busca**: especifica se este atributo se pode usar para buscar clientes na páxina **Clientes** usando o campo **Buscar**.
- **Engadir filtro**: controle a definición de como se pode usar este atributo para filtrar na páxina **Clientes**.

## <a name="next-steps"></a>Pasos seguintes

Revise a [páxina de perfís unificados](customer-profiles.md) para buscar perfís ou usar os campos indexados para ver un subconxunto de todos os perfís unificados.

[!INCLUDE [footer-include](includes/footer-banner.md)]
