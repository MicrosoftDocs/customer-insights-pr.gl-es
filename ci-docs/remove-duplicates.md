---
title: Elimina os duplicados antes de unificar os datos
description: O segundo paso do proceso de unificación é seleccionar que rexistro manter cando se atopen duplicados.
recommendations: false
ms.date: 08/01/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-map
- ci-match
- customerInsights
ms.openlocfilehash: 7f4829cfc14af623f724c6594e834f3fac1c15a9
ms.sourcegitcommit: 10dcfc32eaf8ec0903be96136dca7bb4e250276a
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 08/01/2022
ms.locfileid: "9213625"
---
# <a name="remove-duplicates-before-unifying-data"></a>Elimina os duplicados antes de unificar os datos

Este paso opcional na unificación permítelle configurar regras para eliminar rexistros duplicados **dentro** unha entidade. A deduplicación identifica varios rexistros para un cliente e selecciona o mellor rexistro para manter (en función das preferencias básicas de fusión) ou fusiona os rexistros nun só (en base ás preferencias de fusión avanzadas). Os rexistros de orixe vincúlanse co rexistro combinado con ID alternativos. Se as regras non están configuradas, aplícanse as regras definidas polo sistema.

## <a name="default-deduplication"></a>Desduplicación predeterminada

As regras definidas polo sistema aplícanse se non se engaden regras de deduplicación.

- A chave primaria está desduplicada.
  Para calquera rexistro coa mesma clave principal, o rexistro **Máis cheo** (o que ten menos valores nulos) é o gañador.
- Calquera regra de coincidencia entre entidades aplícase á entidade.
  Por exemplo: no paso de coincidencia, se a entidade A coincide coa entidade B activada *Nome completo* e *Data de nacemento*, entón a entidade A tamén é deduplicada por *Nome completo* e *Data de nacemento*. Porque *Nome completo* e *Data de nacemento* son claves válidas para identificar un cliente na entidade A, estas claves tamén son válidas para identificar clientes duplicados na entidade A.

## <a name="include-enriched-entities-preview"></a>Incluír entidades enriquecidas (vista previa)

Se enriqueceches as entidades no nivel orixe de datos para axudar a mellorar os teus resultados de unificación, selecciónaas. Para obter máis información, consulte [Enriquecemento das fontes de datos](data-sources-enrichment.md).

1. No **Rexistros duplicados** páxina, seleccione **Usa entidades enriquecidas** na parte superior da páxina.

1. Dende **Usa entidades enriquecidas** panel, escolla unha ou máis entidades enriquecidas.

1. Seleccione **Feito**.

## <a name="define-deduplication-rules"></a>Definir regras de deduplicación

1. No **Rexistros duplicados** páxina, seleccione unha entidade e seleccione **Engadir regra** para definir as regras de deduplicación.

   :::image type="content" source="media/m3_duplicates_showmore.png" alt-text="Captura de pantalla das páxinas de rexistros duplicados con Mostrar máis resaltado":::

   1. No **Engadir regra** panel, introduza a seguinte información:
      - **Seleccione campo** : Escolla entre a lista de campos dispoñibles da entidade que quere comprobar se hai duplicados. Escolla campos que probablemente sexan únicos para cada cliente. Por exemplo, un enderezo de correo electrónico ou a combinación de nome, cidade e número de teléfono.
      - **Normalizar**: seleccione unha das seguintes opcións de normalización para os atributos seleccionados.
        - **Os números** : converte outros sistemas numéricos, como números romanos, en números arábigos. *VIII* pasa a ser *8*.
        - **Símbolos** : Elimina todos os símbolos e caracteres especiais. *Head&Shoulder* convértese en *HeadShoulder*.
        - **Texto en minúsculas: converte todos os caracteres en minúsculas**. *MAIÚSCULAS e maiúscula inicial de palabra* convértese en *maiúsculas e maiúscula inicial de palabra*.
        - **Tipo (teléfono, nome, enderezo, organización)** : Normaliza nomes, títulos, números de teléfono, enderezos, etc.
        - **Unicode a ASCII** : converte a notación Unicode en caracteres ASCII. */u00B2* convértese en *2*.
        - **Espazo en branco** : Elimina todos os espazos. *Ola Mundo* convértese en *HelloWorld*.
      - **Precisión**: define o nivel de precisión para aplicar a esta condición.
        - **Básico** : Escolle entre *Baixo (30%)*, *(60%)*, *(80%)*, e *Exacto (100%)*. Seleccione **Exacto** para coincidir só con rexistros que coincidan co 100 por cento.
        - **Personalizado**: defina unha porcentaxe coa que deben coincidir os rexistros. O sistema só atopará a coincidencia cos rexistros que superen este limiar.
      - **Nome** : Nome da regra.

      :::image type="content" source="media/m3_duplicates_add.png" alt-text="Captura de pantalla do panel Engadir regra para eliminar duplicados.":::

   1. Opcionalmente, seleccione **Engadir** > **Engadir condición** para engadir máis condicións á regra. As condicións están conectadas cun operador AND lóxico e, polo tanto, só se executan se se cumpren todas as condicións.

   1. Opcionalmente, **Engadir** > **Engadir excepción** a [engadir excepcións á regra](match-entities.md#add-exceptions-to-a-rule). As excepcións úsanse para tratar casos raros de falsos positivos e falsos negativos.

   1. Seleccione **Feito** para crear a regra.

1. Tamén pode [engadir máis regras](#define-deduplication-rules).

1. Seleccione unha entidade e despois **Edita as preferencias de combinación**.

1. No **Combina preferencias** panel:
   1. Escolla unha das tres opcións para determinar que rexistro gardar se se atopa un duplicado:
      - **Máis cheo**: identifica o rexistro con máis campos de atributos cubertos como o rexistro gañador. É a opción de combinación predefinida.
      - **Máis recente**: Identifica o rexistro gañador en función da data máis recente. Require unha data ou un campo numérico para definir a actualidade.
      - **Menos recente**: Identifica o rexistro gañador en función da data menos recente. Require unha data ou un campo numérico para definir a actualidade.
      
      En caso de empate, o récord de gañador é o que ten o MAX(PK) ou o valor de clave principal maior.
      
   1. Opcionalmente, para definir preferencias de combinación en atributos individuais dunha entidade, seleccione **Avanzado** na parte inferior do panel. Por exemplo, pode escoller manter o correo electrónico máis recente E o enderezo máis completo de diferentes rexistros. Amplíe a entidade para ver todos os seus atributos e defina que opción usar para atributos individuais. Se escolle unha opción baseada na recensión, tamén debe especificar un campo de data/hora que defina a recente.

      :::image type="content" source="media/m3_adv_merge.png" alt-text="Panel de preferencias de combinación avanzada que mostra o correo electrónico recente e o enderezo completo":::

   1. Seleccione **Feito** para aplicar as súas preferencias de combinación.

1. Despois de definir as regras de deduplicación e as preferencias de combinación, seleccione **A continuación**.
  
> [!div class="nextstepaction"]
> [Seguinte paso para unha única entidade: unificar campos](merge-entities.md)

> [!div class="nextstepaction"]
> [Seguinte paso para varias entidades: Condicións coincidentes](match-entities.md)

## <a name="deduplication-output-as-an-entity"></a>Saída de desduplicación como entidade

O proceso de deduplicación crea unha nova entidade deduplicada para cada unha das entidades de orixe. Estas entidades pódense atopar xunto con **ConflationMatchPairs:CustomerInsights** na sección **Sistema** da páxina **Entidades**, co nome **Deduplication_DataSource_Entity**.

Unha entidade de saída de desduplicación contén a seguinte información:

- Identificadores ou claves
  - Campos de clave primaria e ID alternativo. O campo de ID alternativo consta de todos os ID alternativos identificados para un rexistro.
  - O campo Deduplication_GroupId mostra o grupo ou clúster identificado dentro dunha entidade que agrupa todos os rexistros similares en función dos campos de desduplicación especificados. Úsase con fins de procesamento do sistema. Se non hai regras de desduplicación manual especificadas e se aplican regras de desduplicación definidas polo sistema, é posible que non atope este campo na entidade de saída da desduplicación.
  - Deduplication_WinnerId: este campo contén o ID gañador dos grupos ou clústeres identificados. Se o Deduplication_WinnerId é o mesmo que o valor da clave primaria para un rexistro, significa que o rexistro é o rexistro gañador.
- Campos empregados para definir as regras de desduplicación.
- Campos Regra e Puntuación para indicar cal das regras de desduplicación se aplicou e a puntuación devolta polo algoritmo de correspondencia.

[!INCLUDE[footer-include](includes/footer-banner.md)]
