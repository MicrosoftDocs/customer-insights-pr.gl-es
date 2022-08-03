---
title: Entidades en Customer Insights
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
ms.openlocfilehash: 0beaa46d47545ac195ced876b509dfc57821bfaf
ms.sourcegitcommit: ad74ace653db9a25fce4343adef7db1c9b0d8904
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "9183550"
---
# <a name="entities-in-customer-insights"></a>Entidades en Customer Insights

Despois de [configurar as súas orixes de datos](data-sources.md), vaia á páxina **Entidades** para avaliar a calidade dos datos inxeridos. As entidades considéranse conxuntos de datos. Múltiples capacidades de Dynamics 365 Customer Insights constrúense arredor destas entidades. Revisalas de preto pode axudarlle a validar o resultado desas capacidades.

Mentres traballa en Customer Insights enriquecendo os seus datos ou creando segmentos, medidas e actividades, as entidades que se crean a partir desas accións móstranse no **Entidades** páxina.

## <a name="view-a-list-of-entities"></a>Ver unha lista de entidades

Ir a **Datos** > **Entidades** para ver unha lista de entidades. A seguinte información móstrase para cada entidade.

- **Nome** : Nome da entidade de datos. Se ve un símbolo de aviso xunto ao nome dunha entidade, significa que os datos da entidade non se cargaron correctamente.
- **Fonte** : Tipo de orixe de datos que inxeriu a entidade.
- **Actualizado** : Hora da última actualización da entidade.
- **Estado** : Detalles sobre a última actualización da entidade.

## <a name="explore-a-specific-entitys-data"></a>Explorar os datos dunha entidade específica

1. Ir a **Datos** > **Entidades**.
1. Seleccione unha entidade para abrir a páxina de detalles.  
1. Explora os diferentes campos e rexistros incluídos para esa entidade.

- O **Atributos** a pestana está seleccionada por defecto e mostra detalles da entidade seleccionada, como nomes de campos, tipos de datos e tipos. A columna **Tipo** mostra os tipos asociados ao Common Data Model, identificados automaticamente polo sistema ou [mapeados manualmente](map-entities.md) polos usuarios. Estes tipos son tipos semánticos que poden diferir dos tipos de datos dos atributos. Por exemplo, o campo *Correo electrónico* a continuación ten un tipo de datos *Corda* pero o seu tipo (semántico) Common Data Model podería ser *Correo electrónico*, *electrónico*, ou *Identidade.Servizo.Correo electrónico*.

   :::image type="content" source="media/data-manager-entities-fields.png" alt-text="Táboa de campos.":::

   > [!NOTE]
   > Esta páxina mostra só unha mostra dos datos da túa entidade. Para ver o conxunto de datos completo, vai a **Fontes de datos** páxina, seleccione unha entidade, seleccione **Editar**, e despois ver os datos desta entidade co Power Query editor como se explica en [Fontes de datos](data-sources.md).

   Para saber máis sobre os datos inxeridos na entidade, o **Resumo** A columna proporciona algunhas características de datos importantes, como valores nulos, valores ausentes, valores únicos, recontos e distribucións, calquera que sexa aplicable aos teus datos. Seleccione a icona de gráfico para ver o resumo dos datos.

   :::image type="content" source="media/data-manager-entities-summary.png" alt-text="Táboa resumo de datos.":::

- O **Datos** mostra detalles sobre os rexistros individuais da entidade. Os detalles indicados dependen do tipo de datos da entidade.

   :::image type="content" source="media/data-manager-entities-data.png" alt-text="Selecciona unha entidade.":::

- O **Informes** pestana (dispoñible para algunhas entidades) permítelle visualizar os seus datos creando un informe, que inclúe estas columnas:

  - **Nome do informe** : Nome do informe.
  - **Creado por** : Nome da persoa que creou a entidade.
  - **Creada** : Data e hora de creación da entidade.
  - **Editado por** : Nome da persoa que modificou a entidade.
  - **Editado** : Data e hora da modificación da entidade.

## <a name="entity-specific-information"></a>Información específica da entidade

A seguinte sección ofrece información sobre algunhas entidades creadas polo sistema.

### <a name="corrupted-data-sources"></a>Orixes de datos danadas

Os campos dunha orixe de datos inxerida poden conter datos danados. Os rexistros con campos danados expóñense en entidades creadas polo sistema. Coñecer os rexistros danados axuda a identificar que datos hai que revisar e actualizar no sistema de orixe. Despois da seguinte actualización da orixe de datos, os rexistros corrixidos inxírense en Customer Insights e transmítense aos procesos descendentes. 

Por exemplo, unha columna "aniversario" ten o tipo de datos definido como "data". Un rexistro de cliente introduciu o seu aniversario como "01/01/19777". O sistema marcará este rexistro como danado. Agora outra persoa pode cambiar o aniversario no sistema de orixe a "1977". Despois dunha actualización automatizada das orixes de datos, o campo ten un formato válido e o rexistro eliminarase da entidade danada.

Vaia a **Datos** > **Entidades** e busque as entidades danadas na sección **Sistema**. Esquema de nomeamento de entidades danadas: "DataSourceName_EntityName_corrupt". Seleccione unha entidade corrupta para identificar os campos danados e o motivo a nivel de rexistro individual.

   :::image type="content" source="media/corruption-reason.png" alt-text="Motivo de corrupción.":::

Customer Insights aínda procesa rexistros danados. Non obstante, poden causar problemas ao traballar cos datos unificados.

As seguintes comprobacións execútanse nos datos inxeridos para expoñer rexistros danados:

- O valor dun campo non coincide co tipo de datos da súa columna.
- Os campos conteñen caracteres que fan que as columnas non coincidan co esquema esperado. Por exemplo: comiñas con formato incorrecto, comiñas sen escape ou caracteres de nova liña.
- Se hai columnas datatime/date/datetimeoffset, o seu formato debe especificarse no modelo se non segue o formato ISO estándar.

[!INCLUDE [footer-include](includes/footer-banner.md)]
