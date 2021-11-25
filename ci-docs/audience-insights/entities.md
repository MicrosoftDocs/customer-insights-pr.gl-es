---
title: Entidades e conxuntos de datos
description: Vexa os datos na páxina de entidades.
ms.date: 11/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 2a207a3dcad4bf192efb6ee1554195f10b19670b
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 11/02/2021
ms.locfileid: "7732078"
---
# <a name="entities-in-audience-insights"></a>Entidades na información sobre o público

Despois de [configurar as súas orixes de datos](data-sources.md), vaia á páxina **Entidades** para avaliar a calidade dos datos inxeridos. As entidades considéranse conxuntos de datos. En torno a estas entidades constrúense varias capacidades de Dynamics 365 Customer Insights. Revisalas de preto pode axudarlle a validar o resultado desas capacidades.

A páxina **Entidades** enumera entidades e inclúe varias columnas:

- **Nome**: o nome da súa entidade de datos. Se ve un símbolo de aviso xunto ao nome dunha entidade, significa que os datos da entidade non se cargaron correctamente.
- **Orixe**: tipo de orixes de datos que inxeriron a entidade
- **Creado por**: nome da persoa que creou a entidade
- **Data e hora de creación**: data e hora de creación da entidade
- **Actualizado** : Nome da persoa que actualizou a entidade
- **Estado** : Detalles sobre a última actualización da entidade

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="explore-a-specific-entitys-data"></a>Explorar os datos dunha entidade específica

Seleccione unha entidade para explorar os diferentes campos e rexistros incluídos nela.

> [!div class="mx-imgBorder"]
> ![Selecciona unha entidade.](media/data-manager-entities-data.png "Seleccionar unha entidade")

- O separador **Datos** mostra unha táboa con detalles sobre os rexistros individuais da entidade.

> [!div class="mx-imgBorder"]
> ![Táboa de campos.](media/data-manager-entities-fields.PNG "Táboa de campos")

- O separador **Atributos** está seleccionado por defecto e mostra unha táboa para revisar os detalles da entidade seleccionada, como os nomes dos campos e os tipos, entre outros, de datos. A columna **Tipo** mostra os tipos asociados ao Common Data Model, identificados automaticamente polo sistema ou [mapeados manualmente](map-entities.md) polos usuarios. Estes tipos son tipos semánticos que poden diferir dos tipos de datos dos atributos. Por exemplo, o campo *Correo electrónico* que se mostra a continuación ten un tipo de datos *Text* pero o seu tipo (semántico) de Common Data Model pode ser *Email* ou *EmailAddress*.

> [!NOTE]
> As dúas táboas inclúen só unha mostra dos datos da súa entidade. Para ver o conxunto de datos completo, vaia á páxina **Orixes de datos**, seleccione unha entidade, seleccione **Editar** e, a continuación, visualice os datos desta entidade co editor Power Query como se explica en [Orixes de datos](data-sources.md).

Para saber máis sobre os datos inxeridos na entidade, a columna **Resumo** ofrécelle algunhas características importantes dos datos, como os datos nulos, valores que faltan, valores únicos, contas e distribucións, segundo corresponda aos seus datos.

Seleccione a icona de gráfico para ver o resumo dos datos.

> [!div class="mx-imgBorder"]
> ![Símbolo de resumo.](media/data-manager-entities-summary.png "Táboa de resumo de datos")

## <a name="entity-specific-information"></a>Información específica da entidade

A seguinte sección ofrece información sobre algunhas entidades creadas polo sistema.

### <a name="corrupted-data-sources"></a>Orixes de datos danadas

Os campos dunha orixe de datos inxerida poden conter datos danados. Os rexistros con campos danados expóñense en entidades creadas polo sistema. Coñecer os rexistros danados axuda a identificar que datos hai que revisar e actualizar no sistema de orixe. Despois da seguinte actualización da orixe de datos, os rexistros corrixidos inxírense en Customer Insights e transmítense aos procesos descendentes. 

Por exemplo, unha columna "aniversario" ten o tipo de datos definido como "data". Un rexistro de cliente introduciu o seu aniversario como "01/01/19777". O sistema marcará este rexistro como danado. Agora outra persoa pode cambiar o aniversario no sistema de orixe a "1977". Despois dunha actualización automatizada das orixes de datos, o campo ten un formato válido e o rexistro eliminarase da entidade danada. 

Vaia a **Datos** > **Entidades** e busque as entidades danadas na sección **Sistema**. Esquema de nomeamento de entidades danadas: "DataSourceName_EntityName_corrupt".

Customer Insights aínda procesa rexistros danados. Non obstante, poden causar problemas ao traballar cos datos unificados.

As seguintes comprobacións execútanse nos datos inxeridos para expoñer rexistros danados: 

- O valor dun campo non coincide co tipo de datos da súa columna.
- Os campos conteñen caracteres que fan que as columnas non coincidan co esquema esperado. Por exemplo: comiñas con formato incorrecto, comiñas sen escape ou caracteres de nova liña.
- Se hai columnas datetime/date/datetimeoffset, o seu formato debe especificarse no modelo se non seguen o formato ISO estándar.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
