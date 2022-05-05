---
title: Buscar e filtrar perfís de clientes
description: Busque rapidamente información sobre perfís de clientes unificados e filtre por atributos especificados.
ms.date: 11/01/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
searchScope:
- ci-search-filter
- customerInsights
ms.openlocfilehash: 35bfd6530b9b80a4b0ec8ff992d9014534721907
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642766"
---
# <a name="customer-profiles-search--filter-index"></a>Perfís de clientes: índice de busca e filtro

O resultado de unificar os seus datos de clientes é unha entidade de perfil de cliente que fornece unha vista unificada na súa base de clientes total. Para [buscar información rapidamente sobre un cliente ou grupo de clientes específicos](customer-profiles.md), pode configurar as capacidades **Buscar** e **Filtrar** na páxina **Clientes**. Continúe lendo para aprender como poden os administradores editar os atributos na páxina **Índice de busca e filtro**, que están dispoñibles para os usuarios para buscar e filtrar.

   :::image type="content" source="media/search-filter.png" alt-text="Buscar filtro":::

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="add-fields-and-specify-attributes"></a>Engadir campos e especificar atributos

Se é a primeira vez que define atributos que se poden buscar como administrador, primeiro deberá definir os campos indexados. Suxerímoslle que escolla todos os atributos cos que os usuarios poidan buscar e filtrar clientes na páxina **Clientes**. Só pode especificar atributos que existen na entidade de Perfil de cliente que creou durante o proceso de unificación de datos.

1. Abra a páxina **Clientes** e seleccione **Índice de busca e filtro**.

2. Seleccione **+ Engadir** para especificar os campos indexados.

3. Seleccione os atributos da lista que desexa engadir como campos indexados. Sempre pode engadir máis atributos seleccionando **Engadir**. Tamén pode eliminar todos os atributos seleccionados seleccionando o símbolo **Quitar**.

## <a name="explore-the-indexed-customer-fields-table"></a>Explorar a táboa de campos de clientes indexados

A seguinte información preséntase na táboa.

- **Nome**: representa o nome do atributo tal e como aparece na entidade de Perfil do cliente.
- **Tipo de datos**: especifica se o tipo de datos é unha cadea, un número ou unha data.
- **Incluído na busca**: especifica se este atributo se pode usar para buscar clientes na páxina **Clientes** usando o campo **Buscar**.
- **Engadir filtro**: controle a definición de como se pode usar este atributo para filtrar na páxina **Clientes**.

## <a name="editing-filtering-options-for-a-given-attribute"></a>Edición de opcións de filtrado dun atributo dado

O menú **Filtro** da páxina **Clientes** pode incluír un número variable de niveis de atributos (por exemplo, diferentes grupos de idade polos que filtrar os clientes).

1. Seleccione **Engadir filtro** para un atributo determinado na páxina **Índice de busca e filtro**. Pode definir o número de resultados e a orde en que se organizarán. Dependendo do tipo de datos do atributo, aparecerá un dos seguintes paneis.

- Atributos do tipo de cadea: especifique o número de resultados desexados no panel **Opcións de filtro de cadeas** e a política de pedidos pola que se organizarán.

- Atributos do tipo numérico: especifique os intervalos incluídos no panel **Opcións de filtro de números** e a política de pedidos pola que se organizarán.

- Atributos do tipo de data: especifique os intervalos incluídos no panel **Opcións de filtro de datas** e a política de pedidos pola que se organizarán.

2. Seleccione **Gardar** para aplicar as modificacións.

3. Seleccione **Executar** unha vez estea listo para aplicar a súa configuración. Despois de procesar os cambios, atoparalos nas [tarxetas de cliente da páxina de Cliente](customer-profiles.md). 

## <a name="next-steps"></a>Pasos seguintes

Revise a [páxina de perfís unificados](customer-profiles.md) para buscar perfís ou usar os campos indexados para ver un subconxunto de todos os perfís unificados.


[!INCLUDE [footer-include](includes/footer-banner.md)]
