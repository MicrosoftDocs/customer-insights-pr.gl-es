---
title: Entidades e conxuntos de datos
description: Vexa os datos na páxina de entidades.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-entities
- customerInsight
ms.openlocfilehash: c1094bc2f6d137087b317ed20d0615289d6f1187
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642696"
---
# <a name="entities-in-customer-insights"></a>Entidades en Customer Insights

Despois de [configurar as súas orixes de datos](data-sources.md), vaia á páxina **Entidades** para avaliar a calidade dos datos inxeridos. As entidades considéranse conxuntos de datos. Múltiples capacidades de Dynamics 365 Customer Insights constrúense arredor destas entidades. Revisalas de preto pode axudarlle a validar o resultado desas capacidades.

O **Entidades** páxina lista entidades e inclúe estas columnas:

- **Nome** : O nome da entidade de datos. Se ve un símbolo de aviso xunto ao nome dunha entidade, significa que os datos da entidade non se cargaron correctamente.
- **Fonte** : Tipo de orixe de datos que inxeriu a entidade.
- **Actualizado** : Hora da última actualización da entidade.
- **Estado** : Detalles sobre a última actualización da entidade.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="explore-a-specific-entitys-data"></a>Explorar os datos dunha entidade específica

1. Ir a **Datos** > **Entidades**.
1. Dende **Entidades** páxina, seleccione unha entidade para abrir a páxina de detalles.  
1. Explora os diferentes campos e rexistros incluídos para esa entidade.

- O separador **Atributos** está seleccionado por defecto e mostra unha táboa para revisar os detalles da entidade seleccionada, como os nomes dos campos e os tipos, entre outros, de datos. A columna **Tipo** mostra os tipos asociados ao Common Data Model, identificados automaticamente polo sistema ou [mapeados manualmente](map-entities.md) polos usuarios. Estes tipos son tipos semánticos que poden diferir dos tipos de datos dos atributos. Por exemplo, o campo *Correo electrónico* que se mostra a continuación ten un tipo de datos *Text* pero o seu tipo (semántico) de Common Data Model pode ser *Email* ou *EmailAddress*.

> [!div class="mx-imgBorder"]
> ![Táboa de campos.](media/data-manager-entities-fields.PNG "Táboa de campos")

> [!NOTE]
> Esta páxina mostra só unha mostra dos datos da túa entidade. Para ver o conxunto de datos completo, vai a **Fontes de datos** páxina, seleccione unha entidade, seleccione **Editar**, e despois ver os datos desta entidade co Power Query editor como se explica en [Fontes de datos](data-sources.md).

Para saber máis sobre os datos inxeridos na entidade, a columna **Resumo** ofrécelle algunhas características importantes dos datos, como os datos nulos, valores que faltan, valores únicos, contas e distribucións, segundo corresponda aos seus datos. Seleccione a icona de gráfico para ver o resumo dos datos.

> [!div class="mx-imgBorder"]
> ![Símbolo de resumo.](media/data-manager-entities-summary.png "Táboa de resumo de datos")

- O separador **Datos** mostra unha táboa con detalles sobre os rexistros individuais da entidade. Os detalles indicados dependen do tipo de datos da entidade.

> [!div class="mx-imgBorder"]
> ![Selecciona unha entidade.](media/data-manager-entities-data.png "Seleccionar unha entidade")

- O **Informes** a pestana (dispoñible para algunhas entidades) permítelle visualizar os seus datos creando un informe e inclúe estas columnas:

  - **Nome do informe** : Nome do informe.
  - **Creado por** : Nome da persoa que creou a entidade.
  - **Creado** : Data e hora de creación da entidade.
  - **Editado por** : Nome da persoa que modificou a entidade.
  - **Editado** : Data e hora da modificación da entidade. 

## <a name="entity-specific-information"></a>Información específica da entidade

A seguinte sección ofrece información sobre algunhas entidades creadas polo sistema.

### <a name="corrupted-data-sources"></a>Orixes de datos danadas

Os campos dunha orixe de datos inxerida poden conter datos danados. Os rexistros con campos danados expóñense en entidades creadas polo sistema. Coñecer os rexistros danados axuda a identificar que datos hai que revisar e actualizar no sistema de orixe. Despois da seguinte actualización da orixe de datos, os rexistros corrixidos inxírense en Customer Insights e transmítense aos procesos descendentes. 

Por exemplo, unha columna "aniversario" ten o tipo de datos definido como "data". Un rexistro de cliente introduciu o seu aniversario como "01/01/19777". O sistema marcará este rexistro como danado. Agora outra persoa pode cambiar o aniversario no sistema de orixe a "1977". Despois dunha actualización automatizada das orixes de datos, o campo ten un formato válido e o rexistro eliminarase da entidade danada. 

Vaia a **Datos** > **Entidades** e busque as entidades danadas na sección **Sistema**. Esquema de nomeamento de entidades danadas: "DataSourceName_EntityName_corrupt". Seleccione unha entidade corrupta para identificar todos os campos danados e o motivo a nivel de rexistro individual.
> [!div class="mx-imgBorder"]
> ![Motivo de corrupción.](media/corruption-reason.png "Razón de corrupción")

Customer Insights aínda procesa rexistros danados. Non obstante, poden causar problemas ao traballar cos datos unificados.

As seguintes comprobacións execútanse nos datos inxeridos para expoñer rexistros danados: 

- O valor dun campo non coincide co tipo de datos da súa columna.
- Os campos conteñen caracteres que fan que as columnas non coincidan co esquema esperado. Por exemplo: comiñas con formato incorrecto, comiñas sen escape ou caracteres de nova liña.
- Se hai columnas datatime/date/datetimeoffset, o seu formato debe especificarse no modelo se non segue o formato ISO estándar.


[!INCLUDE [footer-include](includes/footer-banner.md)]
