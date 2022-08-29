---
title: Crear unha vista unificada dos seus clientes
description: Percorre o proceso de unificación de datos cos teus datos para crear un único conxunto de datos mestre de contas ou perfís de clientes.
ms.date: 08/12/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: overview
author: Scott-Stabbert
ms.author: sstabbert
manager: shellyha
searchScope:
- ci-map
- customerInsights
ms.openlocfilehash: c2a81776eab147c4b5209a6fbf89c0f4c9853d1d
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304425"
---
# <a name="data-unification-overview"></a>Descrición xeral da unificación de datos

Despois de [configurar as fontes de datos](data-sources.md), pode unificar os datos. A unificación de datos permíteche unificar fontes de datos distintas nun único conxunto de datos mestre que ofrece unha vista unificada deses datos.

Para os consumidores individuais (B-to-C) nos que os datos se centran en persoas, a unificación ofrece unha visión unificada dos seus clientes. Para as contas empresariais (B-to-B) nas que os datos se centran en contas, a unificación ofrece unha vista unificada das túas contas. [Unificación de contactos (vista previa)](data-unification-contacts.md) permite que os contactos desas contas estean unificados e asociados por separado ás contas.

Os datos pódense unificar nunha única entidade ou en varias entidades.

# <a name="individual-consumers-b-to-c"></a>[Consumidores individuais (B2C)](#tab/b2c)

O proceso de unificación mapea os datos dos clientes das túas fontes de datos, elimina os duplicados, fai coincidir os datos entre as entidades e crea un perfil unificado. A unificación realízase na seguinte orde:

1. [Campos de orixe](map-entities.md) (anteriormente chamado Mapa): no paso dos campos de orixe, seleccione entidades e campos para incluír no proceso de unificación. Asigne os campos a un tipo semántico común que describa o propósito do campo.

1. [Rexistros duplicados](remove-duplicates.md) (anteriormente formaba parte de Coincidir): no paso de rexistros duplicados, defina opcionalmente regras para eliminar os rexistros de clientes duplicados de cada entidade.

1. [Condicións de coincidencia](match-entities.md) (anteriormente chamado Coincidir): no paso de condicións de coincidencia, defina regras que coincidan con rexistros de clientes entre entidades. Cando un cliente se atopa en dúas ou máis entidades, créase un único rexistro consolidado con todas as columnas e os datos de cada entidade.

1. [Campos de clientes unificados](merge-entities.md) (anteriormente chamado Combinar): no paso de campos de cliente unificados, determine que campos de orixe se deben incluír, excluír ou combinar nun perfil de cliente unificado.  

1. [Revisión](review-unification.md) e crea o perfil unificado.

# <a name="business-accounts-b-to-b"></a>[Contas empresariais (B2B)](#tab/b2b)

O proceso de unificación mapea os datos da conta das túas fontes de datos, elimina os duplicados, fai coincidir os datos entre as entidades e crea un perfil unificado. A unificación realízase na seguinte orde:

1. [Campos de orixe](map-entities.md) (anteriormente chamado Mapa): no paso dos campos de orixe, seleccione entidades e campos para incluír no proceso de unificación da conta. Asigne os campos a un tipo semántico común que describa o propósito do campo.

1. [Rexistros duplicados](remove-duplicates.md) (anteriormente formaba parte de Coincidir): no paso de rexistros duplicados, defina opcionalmente regras para eliminar os rexistros de conta duplicados de cada entidade.

1. [Condicións de coincidencia](match-entities.md) (anteriormente chamado Coincidir): no paso de condicións de coincidencia, defina regras que coincidan con rexistros de conta entre entidades. Cando se atopa unha conta en dúas ou máis entidades, créase un único rexistro consolidado con todas as columnas e os datos de cada entidade.

1. [Campos de clientes unificados](merge-entities.md) (anteriormente chamado Combinar): no paso de campos de cliente unificados, determine que campos de orixe se deben incluír, excluír ou combinar nun perfil de cliente unificado.  

1. [Revisión](review-unification.md) e crea o perfil unificado.

Despois de unificar as contas, podes opcionalmente [unificar contactos (vista previa)](data-unification-contacts.md) para esas contas e vincular os contactos unificados ás contas unificadas.

---

Despois de completar a unificación de datos, pode opcionalmente:

- [Establecer relacións entre entidades](relationships.md) para crear segmentos sofisticados.
- [Enriquece os teus datos](enrichment-hub.md) para obter unha gama máis ampla de información sobre os seus clientes.
- [Definir actividades](activities.md) a partir dalgúns dos atributos inxeridos.
- [Construír medidas](measures.md) para comprender mellor os comportamentos dos clientes e o rendemento empresarial.

[!INCLUDE [footer-include](includes/footer-banner.md)]
