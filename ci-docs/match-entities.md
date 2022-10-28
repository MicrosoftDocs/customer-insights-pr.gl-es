---
title: Coincidir as condicións para a unificación de datos
description: Busque coincidencias de entidades para crear perfís de clientes unificados.
recommendations: false
ms.date: 10/07/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-map
- customerInsights
ms.openlocfilehash: bbd2c5f441b85460250c11f02358ea67260278d6
ms.sourcegitcommit: 52ea58c872b10f1e6f9d120be93df93cca1a12dd
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 10/26/2022
ms.locfileid: "9721519"
---
# <a name="match-conditions-for-data-unification"></a>Coincidir as condicións para a unificación de datos

Este paso na unificación define a orde de coincidencia e as regras para a correspondencia entre entidades. Este paso require polo menos dúas entidades.

> [!NOTE]
> Unha vez que crees as condicións de xogo e seleccionas **A continuación**, non pode eliminar unha entidade ou atributo seleccionado. Se é necesario, seleccione **De volta** para revisar as entidades e atributos seleccionados antes de continuar.

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

## <a name="include-enriched-entities-preview"></a>Incluír entidades enriquecidas (vista previa)

Se enriqueceches as entidades no nivel orixe de datos para axudar a mellorar os teus resultados de unificación, selecciónaas. Para obter máis información, consulte [Enriquecemento das fontes de datos](data-sources-enrichment.md). Se seleccionaches entidades enriquecidas no **Rexistros duplicados** páxina, non é necesario seleccionalos de novo.

1. No **Condicións de coincidencia** páxina, seleccione **Usa entidades enriquecidas** na parte superior da páxina.

1. Dende **Usa entidades enriquecidas** panel, escolla unha ou máis entidades enriquecidas.

1. Seleccione **Feito**.

## <a name="specify-the-match-order"></a>Especificar a orde de coincidencia

Cada coincidencia unifica dúas ou máis entidades nunha única entidade consolidada. Ao mesmo tempo, garda os rexistros exclusivos dos clientes. A orde de coincidencia indica a orde na que o sistema tenta facer coincidir os rexistros.

> [!IMPORTANT]
> A primeira entidade chámase entidade principal, que serve de base para os teus perfís unificados. As entidades adicionais seleccionadas engadiranse a esta entidade.
>
> Consideracións importantes:
>
> - Escolla a entidade que teña os datos de perfil máis completos e fiables sobre os seus clientes como entidade principal.
> - Escolla a entidade que teña varios atributos en común con outras entidades (por exemplo, nome, número de teléfono ou enderezo de correo electrónico) como entidade principal.

1. No **Condicións de coincidencia** páxina, use as frechas cara arriba e cara abaixo para mover as entidades na orde que desexe ou arrástreas e soltaas. Por exemplo, seleccione **eCommerceClientes** como entidade primaria e **Clientes loy** como segunda entidade.

1. Para ter todos os rexistros da entidade como un cliente único independentemente de que se atope unha coincidencia, seleccione **Inclúe todos os rexistros**. Todos os rexistros desta entidade que non coincidan cos rexistros de ningunha outra entidade inclúense no perfil unificado. Os rexistros que non teñen coincidencia chámanse singletons.
  
A entidade primaria *Contactos: eCommerce* coincide coa seguinte entidade *Fidelidade do cliente: fidelidade*. O conxunto de datos que resulta do primeiro paso de coincidencia coincide coa seguinte entidade se tes máis de dúas entidades.

:::image type="content" source="media/m3_match.png" alt-text="Captura de pantalla da orde de coincidencia seleccionada para as entidades." lightbox="media/m3_match.png":::

## <a name="define-rules-for-match-pairs"></a>Definir regras para parellas coincidentes

As regras de coincidencia especifican a lóxica coa que se combinará un par específico de entidades. Unha regra consta dunha ou máis condicións.

A advertencia ao carón dun nome de entidade significa que non se define ningunha regra de coincidencia para un par de coincidencias.

1. Seleccione **Engadir regra** para que un par de entidades defina regras de coincidencia.

1. No **Engadir regra** panel, configure as condicións para a regra.

   :::image type="content" source="media/m3_add_rule.png" alt-text="Captura de pantalla do panel Engadir regra.":::

   - **Seleccione Entidade/Campo (primeira fila)** : Escolle unha entidade e un atributo que probablemente sexa exclusivo dun cliente. Por exemplo, un número de teléfono ou enderezo de correo electrónico. Evite a coincidencia por atributos de tipo de actividade. Por exemplo, un ID de compra probablemente non atopará coincidencias noutros tipos de rexistros.

   - **Seleccione Entidade/Campo (segunda fila)** : Escolla un atributo que se relaciona co atributo da entidade especificado na primeira fila.

   - **Normalizar**: seleccione unha das seguintes opcións de normalización para os atributos seleccionados.
     - **Os números** : converte outros sistemas numéricos, como números romanos, en números arábigos. *VIII* pasa a ser *8*.
     - **Símbolos** : Elimina todos os símbolos e caracteres especiais. *Head&Shoulder* convértese en *HeadShoulder*.
     - **Texto en minúscula** : converte todos os caracteres en minúsculas. *MAIÚSCULAS e maiúscula inicial de palabra* convértese en *maiúsculas e maiúscula inicial de palabra*.
     - **Tipo (teléfono, nome, enderezo, organización)** : estandariza nomes, títulos, números de teléfono, enderezos e organizacións.
     - **Unicode a ASCII** : converte a notación Unicode en caracteres ASCII. */u00B2* convértese en *2*.
     - **Espazo en branco** : Elimina todos os espazos. *Ola Mundo* convértese en *HelloWorld*.

   - **Precisión**: define o nivel de precisión para aplicar a esta condición.
     - **Básico** : Escolle entre *Baixo (30%)*, *(60%)*, *(80%)*, e *Exacto (100%)*. Seleccione **Exacto** para coincidir só con rexistros que coincidan co 100 por cento.
     - **Personalizado**: defina unha porcentaxe coa que deben coincidir os rexistros. O sistema só atopará a coincidencia cos rexistros que superen este limiar.

   - **Nome** : Nome da regra.

1. Para facer coincidir entidades só se os atributos cumpren varias condicións, seleccione **Engadir** > **Engadir condición** para engadir máis condicións a unha regra de coincidencia. As condicións están conectadas cun operador AND lóxico e, polo tanto, só se executan se se cumpren todas as condicións.

1. Opcionalmente, considere opcións avanzadas como [excepcións](#add-exceptions-to-a-rule) ou [condicións de coincidencia personalizadas](#specify-custom-match-conditions).

1. Seleccione **Feito** para finalizar a norma.

1. Tamén pode [engadir máis regras](#add-rules-to-a-match-pair).

1. Prema **Seguinte**.

> [!div class="nextstepaction"]
> [Seguinte paso: unificar campos](merge-entities.md)

### <a name="add-rules-to-a-match-pair"></a>Engadir regras a un par de coincidencias

As regras de coincidencia representan conxuntos de condicións. Para facer coincidir entidades por condicións baseadas en varios atributos, engade máis regras.

1. Seleccione **Engadir regra** na entidade á que desexa engadir regras.

1. Siga os pasos indicados en [Definir regras para parellas de coincidencias](#define-rules-for-match-pairs).

> [!NOTE]
> A orde das regras importa. O algoritmo de coincidencia tenta facer coincidir un determinado rexistro de cliente baseándose na súa primeira regra e continúa coa segunda regra só se non se identificou ningunha coincidencia coa primeira regra.

## <a name="advanced-options"></a>Opcións avanzadas

### <a name="add-exceptions-to-a-rule"></a>Engade excepcións a unha regra

Na maioría dos casos, a coincidencia de entidades leva a perfís de clientes únicos con datos consolidados. Para tratar casos raros de falsos positivos e falsos negativos, define excepcións para unha regra de coincidencia. As excepcións aplícanse despois de procesar as regras de coincidencia e evitar a coincidencia de todos os rexistros, que cumpren os criterios de excepción.

Por exemplo, se a túa regra de coincidencia combina apelidos, cidade e data de nacemento, o sistema identificaría os xemelgos co mesmo apelidos que viven na mesma cidade e co mesmo perfil. Podes especificar unha excepción que non coincida cos perfís se os nome das entidades que combinas non son os mesmos.

1. No **Editar regra** panel, seleccione **Engadir** > **Engadir excepción**.

1. Especifique os criterios de excepción.

1. Para gardar a regra, seleccione **Feito**.

### <a name="specify-custom-match-conditions"></a>Especificar condicións de coincidencia personalizadas

Especifique condicións que anulan a lóxica de coincidencia predeterminada. Hai catro opcións dispoñibles:

|Opción  |Descripción |Exemplo  |
|---------|---------|---------|
|Coincidir sempre     | Define os valores para as claves primarias que sempre coinciden.         |  Fai sempre coincidir a fila coa clave principal *12345* á fila coa clave principal *54321*.       |
|Non coincidir nunca     | Define valores para as chaves primarias que nunca coinciden.        | Nunca coincida a fila coa clave principal *12345* á fila coa clave principal *54321*.        |
|Omitir            | Define valores que o sistema debería ignorar sempre na fase de coincidencia. |  Ignorar os valores *11111* e *Descoñecido* durante o partido.        |
|Asignación de alias    | Definición de valores que o sistema debería considerar como o mesmo valor.         | Considera *Joe* ser igual a *Xosé*.        |

1. Seleccione **Personalizado**.

   :::image type="content" source="media/m3_match_custom.png" alt-text="Botón personalizado":::

1. Escolle o **Tipo personalizado** e selecciona **Descargar modelo**. Cambia o nome do modelo sen usar espazos. Use un modelo separado para cada opción de coincidencia.

1. Abre o ficheiro de modelo descargado e enche os detalles. O modelo contén campos para especificar a entidade e os valores de clave primarios da entidade a empregar na coincidencia personalizada. Os nomes das entidades distinguen entre maiúsculas e minúsculas. Por exemplo, se desexa a clave principal *12345* desde a entidade *Vendas* para atopar unha coincidencia sempre coa clave primaria *34567* desde a entidade *Contacto*, encha o modelo:
   - Entity1: vendas
   - Entity1Key: 12345
   - Entity2: Contacto
   - Entity2Key: 34567

   O mesmo ficheiro de modelo pode especificar rexistros de coincidencia personalizados de varias entidades.

   > [!NOTE]
   > Se desexa especificar a busca de coincidencias personalizada para a desduplicación nunha entidade, proporcione a mesma entidade que Entidade1 e Entidade2 e estableza os diferentes valores da clave primaria. Debes definir polo menos unha regra de deduplicación para a entidade para utilizar a correspondencia personalizada.

1. Despois de engadir todas as substitucións, garda o ficheiro de modelo.

1. Vaia a **Datos** > **Fontes de datos** e inxira os ficheiros modelo como novas entidades.

1. Despois de cargar os ficheiros, seleccione **Personalizado** opción de novo. Seleccione as entidades requiridas no menú despregable e seleccione **Feito**.

   :::image type="content" source="media/custom-match-overrides.png" alt-text="Captura de pantalla do diálogo para escoller substitucións para un escenario de coincidencia personalizado.":::

1. A aplicación da coincidencia personalizada depende da opción de coincidencia que queiras usar.

   - Para **Sempre coincidir** ou **Nunca coincidir**, continúe co seguinte paso.
   - Para **Bypass** ou **Mapeo de alias**, seleccione **Editar** nunha regra de coincidencia existente ou cree unha nova. No menú despregable Normalizacións, escolla **Bypass personalizado** ou **Mapeo de alias** opción e seleccione **Feito**.

1. Seleccione **Feito** no **Personalizado** panel para aplicar a configuración de coincidencia personalizada.

   Cada ficheiro de modelo inxerido é o seu propio orixe de datos. Se se descobren rexistros que precisan un tratamento especial de coincidencia, actualice o orixe de datos apropiado. A actualización utilizarase durante o seguinte proceso de unificación. Por exemplo, identificas xemelgos con case o mesmo nome que viven no mesmo enderezo que se fusionaron como unha persoa. Actualiza o orixe de datos para identificar aos xemelgos como rexistros únicos e separados.

> [!div class="nextstepaction"]
> [Seguinte paso: unificar campos](merge-entities.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
