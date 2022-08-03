---
title: Descrición xeral da unificación de datos
description: Siga o proceso de unificación de datos cos seus datos para crear un único conxunto de datos de perfís de clientes unificados.
ms.date: 05/10/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: overview
author: v-wendysmith
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-map
- customerInsights
ms.openlocfilehash: 766e688cb80c50a0d620943f87b76eb84a2fb89a
ms.sourcegitcommit: 3c5b0b40b2b45e420015bbdd228ce0e610245e6f
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 07/12/2022
ms.locfileid: "9139486"
---
# <a name="data-unification-overview"></a>Descrición xeral da unificación de datos

Despois de [configurar as fontes de datos](data-sources.md), pode unificar os datos. A unificación de datos permíteche unificar fontes de datos distintas nun único conxunto de datos mestre que ofrece unha vista unificada deses datos. Para os consumidores individuais (B-to-C) nos que os datos se centran en individuos, a unificación ofrece unha visión unificada dos seus clientes. Para as contas empresariais (B-to-B) nas que os datos se centran en contas, a unificación ofrece unha vista unificada das túas contas.

Os datos pódense unificar nunha única entidade ou en varias entidades. A unificación realízase na seguinte orde:

1. [Campos de orixe](map-entities.md) (anteriormente chamado Mapa): no paso dos campos de orixe, seleccione entidades e campos para incluír no proceso de unificación. Asigne os campos a un tipo semántico común que describa o propósito do campo.

1. [Rexistros duplicados](remove-duplicates.md) (anteriormente formaba parte de Coincidir): no paso de rexistros duplicados, defina opcionalmente regras para eliminar os rexistros de clientes duplicados de cada entidade.

1. [Condicións de coincidencia](match-entities.md) (anteriormente chamado Coincidir): no paso de condicións de coincidencia, defina regras que coincidan con rexistros de clientes entre entidades. Cando un cliente se atopa en dúas ou máis entidades, créase un único rexistro consolidado con todas as columnas e os datos de cada entidade.

1. [Campos de clientes unificados](merge-entities.md) (anteriormente chamado Combinar): no paso de campos de cliente unificados, determine que campos de orixe se deben incluír, excluír ou combinar nun perfil de cliente unificado.  

1. [Revisión](review-unification.md) e crea o perfil unificado.

Despois de completar a unificación de datos, pode opcionalmente:

- [Establecer relacións entre entidades](relationships.md) para crear segmentos sofisticados.
- [Enriquece os teus datos](enrichment-hub.md) para obter unha gama máis ampla de información sobre os seus clientes.
- [Definir actividades](activities.md) a partir dalgúns dos atributos inxeridos.
- [Construír medidas](measures.md) para comprender mellor os comportamentos dos clientes e o rendemento empresarial.

[!INCLUDE [footer-include](includes/footer-banner.md)]
