---
title: Entidades e conxuntos de datos
description: Vexa os datos na páxina de entidades.
ms.date: 04/16/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 383523bad5105e08e57758838e90a49e805b5f9b
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596405"
---
# <a name="entities-in-audience-insights"></a>Entidades na información sobre o público

Despois de [configurar as súas orixes de datos](data-sources.md), vaia á páxina **Entidades** para avaliar a calidade dos datos inxeridos. As entidades considéranse conxuntos de datos. Múltiples capacidades de Dynamics 365 Customer Insights constrúense arredor destas entidades. Revisalas de preto pode axudarlle a validar o resultado desas capacidades.

A páxina **Entidades** enumera entidades e inclúe varias columnas:

- **Nome**: o nome da súa entidade de datos. Se ve un símbolo de aviso xunto ao nome dunha entidade, significa que os datos da entidade non se cargaron correctamente.
- **Orixe**: tipo de orixes de datos que inxeriron a entidade
- **Creado por**: nome da persoa que creou a entidade
- **Data e hora de creación**: data e hora de creación da entidade
- **Actualizado por**: nome da persoa que actualizou a entidade
- **Última actualización**: data e hora da última actualización da entidade
- **Última actualización**: data e hora da última actualización de datos

## <a name="exploring-a-specific-entitys-data"></a>Exploración de datos dunha entidade específica

Seleccione unha entidade para explorar os diferentes campos e rexistros incluídos nela.

> [!div class="mx-imgBorder"]
> ![Seleccionar unha entidade](media/data-manager-entities-data.png "Seleccionar unha entidade")

- O separador **Datos** está seleccionado de xeito predeterminado e amosa unha táboa que mostra os detalles sobre os rexistros individuais da entidade.

> [!div class="mx-imgBorder"]
> ![Táboa de campos](media/data-manager-entities-fields.PNG "Táboa de campos")

- O separador **Campos** mostra unha táboa para revisar os detalles da entidade seleccionada, como nomes de campo, tipos de datos e tipos. A columna **Tipo** mostra os tipos asociados ao Common Data Model, identificados automaticamente polo sistema ou [mapeados manualmente](map-entities.md) polos usuarios. Trátase de tipos semánticos que poden diferir dos tipos de datos dos atributos, por exemplo, o campo *Correo electrónico* a continuación ten o tipo de datos *Texto* pero o seu tipo de Common Data Model (semántico) pode ser *Correo electrónico* ou *Enderezo de correo electrónico*.

> [!NOTE]
> As dúas táboas inclúen só unha mostra dos datos da súa entidade. Para ver o conxunto de datos completo, vaia á páxina **Orixes de datos**, seleccione unha entidade, seleccione **Editar** e, a continuación, visualice os datos desta entidade co editor Power Query como se explica en [Orixes de datos](data-sources.md).

Para saber máis sobre os datos inxeridos na entidade, a columna **Resumo** ofrécelle algunhas características importantes dos datos, como os datos nulos, valores que faltan, valores únicos, contas e distribucións, segundo corresponda aos seus datos.

Seleccione a icona de gráfico para ver o resumo dos datos.

> [!div class="mx-imgBorder"]
> ![Símbolo de resumo](media/data-manager-entities-summary.png "Táboa de resumo de datos")

### <a name="next-step"></a>Seguinte paso

Consulte o tema [Unificar](data-unification.md) para obter información acerca de como *asignar*, *atopar coincidencia* e *combinar* os datos inxeridos.


[!INCLUDE[footer-include](../includes/footer-banner.md)]