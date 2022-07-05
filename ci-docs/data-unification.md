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
ms.openlocfilehash: 0dbc3b2c75365e94758a1b6330e8cb557e6bd768
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082216"
---
# <a name="data-unification-overview"></a>Descrición xeral da unificación de datos

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Despois de [configurar as fontes de datos](data-sources.md), pode unificar os datos. A unificación de datos permíteche unificar fontes de datos distintas nun único conxunto de datos mestre que ofrece unha vista unificada deses datos. Para os consumidores individuais (B-to-C) nos que os datos se centran en persoas, a unificación ofrece unha visión unificada dos seus clientes. Para as contas empresariais (B-to-B) onde os datos se centran en contas, a unificación ofrece unha vista unificada das túas contas.

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
