---
title: Buscar coincidencias de entidades para a unificación de datos
description: Busque coincidencias de entidades para crear perfís de clientes unificados.
ms.date: 02/07/2022
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-match
ms.openlocfilehash: 20f21a6601a1a6f13d076878b10c15be947dac9f
ms.sourcegitcommit: a399bd17523c8d06afd7d78af4fc711f93c0e8be
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 02/07/2022
ms.locfileid: "8098833"
---
# <a name="match-entities"></a>Buscar coincidencias das entidades

A fase de coincidencia especifica como combinar os seus conxuntos de datos nun conxunto de datos de perfil de cliente unificado. Despois de completar o [paso de asignación](map-entities.md) no proceso de unificación de datos, estará listo para atopar unha coincidencia coas súas entidades. A fase de coincidencias require polo menos dúas entidades asignadas.

A páxina de coincidencia consta de tres seccións: 
- Métricas clave que resumen o número de rexistros coincidentes
- Orde de coincidencia e regras para as coincidencia entre entidades
- Regras para a eliminación de duplicados de entidades coincidentes

## <a name="specify-the-match-order"></a>Especificar a orde de coincidencia

Cada coincidencia unifica dúas ou máis entidades nunha única entidade consolidada. Ao mesmo tempo, garda os rexistros exclusivos dos clientes. A orde de coincidencia indica a orde na que o sistema tenta facer coincidir os rexistros.

> [!IMPORTANT]
> A entidade que escolle como Primaria servirá de base para o seu conxunto de datos de perfís unificado. A esta entidade engadiranse entidades adicionais seleccionadas durante a fase de coincidencia. Isto non significa que a entidade unificada inclúa *todos* os datos incluídos nesta entidade.
>
> Hai dúas consideracións que poden axudarlle a elixir a xerarquía das súas entidades:
>
> - Escolla a entidade cos datos de perfil máis completos e fiables sobre os seus clientes como entidade principal.
> - Escolla a entidade que teña varios atributos en común con outras entidades (por exemplo, nome, número de teléfono ou enderezo de correo electrónico) como entidade principal.

1. Vaia a **Datos** > **Unificar** > **Buscar coincidencias** e seleccione **Establecer orde** para comezar a fase de busca de coincidencias.
1. Seleccione **Orde da entidade**. Por exemplo, seleccione **Comercio electrónico: eCommerceContacts** como entidade primaria e **LoyaltyScheme:loyCustomers** como segunda entidade. 
1. Para ter todos os rexistros da entidade como un cliente único e coincidir con todas as entidades seguintes, selecciona **Inclúe todo**.
1. Seleccione **Feito**. 

Despois de especificar a orde de coincidencia, os pares de coincidencia definidos móstranse no ficheiro **Detalles dos rexistros coincidentes** sección sobre **Datos** > **Unificar** > **Partido**. As métricas clave están baleiras ata que se complete o proceso de coincidencia.

:::image type="content" source="media/match-page.png" alt-text="Captura de pantalla da páxina de coincidencias na área Unify do proceso de unificación de datos.":::
  
A entidade primaria *eCommerce: eCommerceContacts* coincide coa seguinte entidade *LoyaltyScheme: loyCustomers*. O conxunto de datos que resulta do primeiro paso de coincidencia coincide coa seguinte entidade se tes máis de dúas entidades.

## <a name="define-rules-for-match-pairs"></a>Definir regras para parellas coincidentes

As regras de coincidencia especifican a lóxica coa que se combinará un par específico de entidades.

A advertencia **Precisa regras** situada xunto ao nome dunha entidade suxire que non se define ningunha regra de coincidencia para un par de coincidencias. 

:::image type="content" source="media/match-rule-add.png" alt-text="Captura de pantalla da sección Detalles do rexistro coincidente con control para engadir regras resaltadas.":::

1. Seleccione **Engadir regra** baixo unha entidade no **Detalles dos rexistros coincidentes** sección para definir regras de coincidencia.

1. No panel **Crear regra**, configure as condicións para a regra.

   :::image type="content" source="media/match-rule-conditions.png" alt-text="Captura de pantalla dunha regra de coincidencia aberta con condicións engadidas.":::

   - **Entidade/Campo (primeira fila)**: escolla unha entidade relacionada e un atributo para especificar unha propiedade de rexistro que probablemente sexa exclusiva dun cliente. Por exemplo, un número de teléfono ou enderezo de correo electrónico. Evite a coincidencia por atributos de tipo de actividade. Por exemplo, un ID de compra probablemente non atopará coincidencias noutros tipos de rexistros.

   - **Entidade/Campo (segunda fila)**: escolla un atributo relacionado co atributo da entidade especificado na primeira fila.

   - **Normalizar**: seleccione unha das seguintes opcións de normalización para os atributos seleccionados. 
     - Numerais: converte outros sistemas numerais, como os números romanos, en números árabes. *VIII* pasa a ser *8*.
     - Símbolos: elimina todos os símbolos e caracteres especiais. *Head&Shoulder* convértese en *HeadShoulder*.
     - Texto en minúsculas: converte todos os caracteres en minúscula. *MAIÚSCULAS e maiúscula inicial de palabra* convértese en *maiúsculas e maiúscula inicial de palabra*.
     - Tipo (teléfono, nome, enderezo, organización): estandariza nomes, títulos, números de teléfono, enderezos, etc. 
     - Unicode a ASCII: converte a notación unicode en caracteres ASCII. */u00B2* convértese en *2*.
     - Espazo en branco: elimina todos os espazos. *Ola Mundo* convértese en *HelloWorld*.

   - **Precisión**: define o nivel de precisión para aplicar a esta condición. 
     - **Básico**: escolla entre *Baixo*, *Medio*, *Alto* e *Exacto*. Seleccione **Exacto** para coincidir só con rexistros que coincidan co 100 por cento. Seleccione un dos outros niveis para atopar coincidencias de rexistros que non sexan 100 por cento idénticos.
     - **Personalizado**: defina unha porcentaxe coa que deben coincidir os rexistros. O sistema só atopará a coincidencia cos rexistros que superen este limiar.

1. Proporcione un **nome** para a regra.

1. [Engada máis condicións](#add-conditions-to-a-rule) ou seleccione **Feito** para finalizar a regra.

1. Tamén pode [engadir máis regras](#add-rules-to-a-match-pair).

1. Seleccione **Gardar** para aplicar as modificacións.

### <a name="add-conditions-to-a-rule"></a>Engadir condicións a unha regra

Para atopar coincidencias con entidades só se os atributos cumpren varias condicións, engada máis condicións a unha regra de coincidencia. As condicións están conectadas cun operador AND lóxico e, polo tanto, só se executan se se cumpren todas as condicións.

1. Vaia a **Datos** > **Unify** > **Coincidencia** e seleccione **Editar** na regra á que desexa engadir condicións.

1. No panel **Editar regra**, seleccione **Engadir condición**.

1. Para gardar a regra, seleccione **Feito**.

### <a name="add-rules-to-a-match-pair"></a>Engadir regras a un par de coincidencias

As regras de coincidencia representan conxuntos de condicións. Para facer coincidir entidades por condicións baseadas en varios atributos, engade máis regras.

1.  Vaia a **Datos** > **Unify** > **Coincidencia** e seleccione **Engadir regra** na entidade á que desexa engadir regras.

2. Siga os pasos indicados en [Definir regras para parellas de coincidencias](#define-rules-for-match-pairs).

> [!NOTE]
> A orde das regras importa. O algoritmo de coincidencias tenta atopar coincidencias baseándose na súa primeira regra e continúa coa segunda regra só se non se identificaron coincidencias coa primeira regra.

### <a name="change-the-entity-order-in-match-rules"></a>Cambiar a orde de entidades nas regras de busca de coincidencias

Podes reordenar as entidades para as regras de coincidencia para cambiar a orde na que se procesan. Eliminaranse as regras en conflito por mor dun cambio de orde. Ten que volver crear as regras eliminadas cunha configuración actualizada.

1. Vaia a **Datos** > **Unificar** > **Buscar coincidencias** e seleccione **Editar**.

1. No panel **Editar regra**, seleccione o control **Mover cara arriba ou cara abaixo** ou arrastre e solte as entidades para cambiar a orde.

   :::image type="content" source="media/reorder-match-rules.png" alt-text="Opcións para cambiar a orde en que se procesan as entidades na fase de busca de coincidencias.":::

1. Para gardar a regra, seleccione **Feito**.

## <a name="define-deduplication-on-a-match-entity"></a>Definir a desduplicación nunha entidade coincidente

Ademais de [regras de coincidencia entre entidades](#define-rules-for-match-pairs), tamén pode especificar regras de cancelación de duplicacións. *Cancelación de duplicación* é outro proceso ao atopar coincidencias con rexistros. Identifica rexistros duplicados e úneos nun rexistro. Os rexistros de orixe vincúlanse co rexistro combinado con ID alternativos.

Os rexistros deduplicados úsanse no proceso de coincidencia entre entidades. A deduplicación ocorre en entidades individuais e pódese configurar para cada entidade utilizada nos pares de coincidencias.

Non é obrigatorio especificar regras de desduplicación. Se non se configuran tales regras, aplícanse as regras definidas polo sistema. Combinan todos os rexistros nun único rexistro antes de pasar os datos da entidade á coincidencia entre entidades para obter un mellor rendemento.

### <a name="add-deduplication-rules"></a>Engadir regras de desduplicación

1. Vaia a **Datos** > **Unify** > **Coincidencia**.

1. No **Detalles dos rexistros deduplicados** sección, seleccione **Establecer entidades**. Se xa se crearon regras de cancelación de duplicación, seleccione **Editar**.

1. No panel **Preferencias de combinación**, escolla as entidades nas que desexa executar a cancelación da duplicación.

   1. Especifique como combinar os rexistros duplicados e escolla unha das tres opcións:
      - **Máis cheo**: identifica o rexistro con máis campos de atributos cubertos como o rexistro gañador. É a opción de combinación predefinida.
      - **Máis recente**: Identifica o rexistro gañador en función da data máis recente. Require unha data ou un campo numérico para definir a actualidade.
      - **Menos recente**: Identifica o rexistro gañador en función da data menos recente. Require unha data ou un campo numérico para definir a actualidade.

   1. Opcionalmente, para definir regras de deduplicación en atributos individuais dunha entidade, seleccione **Avanzado**. Por exemplo, pode escoller manter o correo electrónico máis recente E o enderezo máis completo de diferentes rexistros. Amplíe a entidade para ver todos os seus atributos e defina que opción usar para atributos individuais. Se escolle unha opción baseada na recensión, tamén debe especificar un campo de data/hora que defina a recente. 
 
      > [!div class="mx-imgBorder"]
      > ![Paso 1 das regras de eliminación de duplicados.](media/match-selfconflation.png "Paso 1 das regras de desduplicación")

   1. Seleccione **Feito** para aplicar as súas preferencias de combinación para a deduplicación.
 
1. Unha vez seleccionadas as entidades e configurada a súa preferencia de combinación, seleccione **Engadir regra** para definir as regras de desduplicación a nivel de entidade.
   - **Seleccionar campo** enumera todos os campos dispoñibles desa entidade. Escolla o campo que desexe comprobar se ten duplicados. Escolla campos que probablemente sexan únicos para cada cliente. Por exemplo, un enderezo de correo electrónico ou a combinación de nome, cidade e número de teléfono.
   - Especifique a configuración de normalización e precisión.
   - Defina máis condicións adicionais seleccionando **Engadir condición**.
 
   > [!div class="mx-imgBorder"]
   > ![Paso 2 das regras de eliminación de duplicados.](media/match-selfconflation-rules.png "Paso 2 das regras de desduplicación")

  Pode crear varias regras de desduplicación para unha entidade. 

1. Executar o proceso de busca de coincidencias agora agrupa os rexistros en función das condicións definidas nas regras de desduplicación. Despois de agrupar os rexistros, aplícase a política de combinación para identificar o rexistro gañador.

1. Este rexistro gañador pásase á busca de coincidencias entre entidades, xunto cos rexistros non gañadores (por exemplo, ID alternativos) para mellorar a calidade das coincidencias.

1. Calquera regra de coincidencia personalizada definida sobrescribe regras de cancelación de duplicación. Se unha regra de desduplicación identifica rexistros coincidentes e se establece unha regra de busca de coincidencias personalizada para que nunca busque coincidencias neses rexistros, entón neses dous rexistros non se buscarán coincidencias.

1. Despois [executando o proceso de coincidencia](#run-the-match-process), verás as estatísticas de deduplicación nos mosaicos de métricas clave.

### <a name="deduplication-output-as-an-entity"></a>Saída de desduplicación como entidade

O proceso de cancelación de duplicación crea unha nova entidade para cada entidade dos pares de coincidencias para identificar os rexistros coa duplicación cancelada. Estas entidades pódense atopar xunto con **ConflationMatchPairs:CustomerInsights** na sección **Sistema** da páxina **Entidades**, co nome **Deduplication_DataSource_Entity**.

Unha entidade de saída de desduplicación contén a seguinte información:
- Identificadores ou claves
  - Campo de clave primaria e o seu campo de ID alternativos. O campo ID alternativos consiste en todos os ID alternativos identificados para un rexistro.
  - O campo Deduplication_GroupId mostra o grupo ou clúster identificado dentro dunha entidade que agrupa todos os rexistros similares en función dos campos de desduplicación especificados. Úsase con fins de procesamento do sistema. Se non hai regras de desduplicación manual especificadas e se aplican regras de desduplicación definidas polo sistema, é posible que non atope este campo na entidade de saída da desduplicación.
  - Deduplication_WinnerId: este campo contén o ID gañador dos grupos ou clústeres identificados. Se o Deduplication_WinnerId é o mesmo que o valor da clave primaria para un rexistro, significa que o rexistro é o rexistro gañador.
- Campos empregados para definir as regras de desduplicación.
- Campos Regra e Puntuación para indicar cal das regras de desduplicación se aplicou e a puntuación devolta polo algoritmo de correspondencia.
   
## <a name="run-the-match-process"></a>Executar o proceso de atopar coincidencia

Con regras de busca de coincidencias configuradas, incluídas as regras de busca de coincidencias entre entidades e desduplicación, pode executar o proceso de busca de coincidencias. 

Vaia a **Datos** > **Unify** > **Coincidencia** e seleccione **Executar** para iniciar o proceso. O algoritmo de busca de coincidencias tarda un tempo completarse e non pode cambiar a configuración ata completala. Para realizar modificacións, pode cancelar a execución. Seleccione o estado do traballo e seleccione **Cancelar traballo** no panel **Detalles do progreso**.

Atopará o resultado dunha execución con éxito, a entidade de perfil de cliente unificado, na páxina **Entidades**. Asignarase á súa entidade de cliente unificada o nome de **Clientes** na sección **Perfís**. A primeira execución da busca de coincidencias correcta crea a entidade *Cliente* unificada. Todas as execucións de buscas de correspondencias posteriores amplían esa entidade.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="review-and-validate-your-matches"></a>Revisar e validar as súas coincidencias

Vaia a **Datos** > **Unify** > **Coincidencia** para avaliar a calidade dos seus pares e melloralas se fose necesario.

Os mosaicos da parte superior da páxina mostran métricas clave, resumindo o número de rexistros e duplicados coincidentes.

:::image type="content" source="media/match-KPIs.png" alt-text="Captura de pantalla recortada das métricas clave da páxina de coincidencias con números e detalles.":::

- **Rexistros de orixe únicos** mostra o número de rexistros de orixes individuais que se procesaron na última execución da busca de coincidencias.
- **Rexistros coincidentes e non coincidentes** destaca cantos rexistros únicos quedan despois de procesar as regras de busca de coincidencias.
- **Só rexistros coincidentes** mostra o número de coincidencias en todos os teus pares de coincidencias.

Pode avaliar os resultados de cada parella coincidente e as súas regras na táboa **Detalles de rexistros coincidentes**. Compare o número de rexistros procedentes dun par coincidente coa porcentaxe de rexistros coincidentes con éxito.

Revise as regras dun par coincidente para ver a porcentaxe de rexistros coincidentes con éxito no nivel de regras. Seleccione os puntos suspensivos (...) e logo seleccione **Vista previa da coincidencia** para ver todos estes rexistros a nivel de regra. Recomendámoslle que bote unha ollada a algúns rexistros para validar que se atopou correctamente a súa coincidencia.

Probe diferentes limiares de precisión en condicións para atopar o valor óptimo.

  1. Seleccione os puntos suspensivos (...) para a regra coa que desexa experimentar e seleccione **Editar**.

  2. Cambie os valores das precisións nas condicións que desexe revisar.

  3. Seleccione **Vista previa** para ver o número de rexistros coincidentes e non coincidentes para a condición seleccionada.

## <a name="manage-match-rules"></a>Xestionar regras de coincidencia

Pode reconfigurar e axustar a maioría dos parámetros de coincidencia.

:::image type="content" source="media/match-rules-management.png" alt-text="Captura de pantalla do menú despregable con opcións de regras de coincidencia.":::

- **Cambie a orde das súas regras** se definiu varias regras. Pode reordenar as regras de coincidencia seleccionando as opcións **Mover cara arriba** e **Mover cara abaixo** ou arrastrando e soltando.

- **Cambie as condicións da regra** seleccionando **Editar** e elixa diferentes campos.

- **Desactivar unha regra** para manter unha regra de busca de coincidencias mentres a exclúe do proceso de busca de coincidencias.

- **Duplique as súas regras** se definiu unha regra de coincidencia e desexa crear unha regra similar con modificacións, seleccione **Duplicar**.

- **Elimine unha regra** seleccionando o símbolo **Eliminar**.

## <a name="advanced-options"></a>Opcións avanzadas

### <a name="add-exceptions-to-a-rule"></a>Engade excepcións a unha regra

Na maioría dos casos, a coincidencia de entidades leva a perfís de usuario únicos con datos consolidados. Para tratar de forma dinámica casos raros de falsos positivos e falsos negativos, pode definir excepcións para unha regra de coincidencia. As excepcións aplícanse despois de procesar as regras de coincidencia e evitar a coincidencia de todos os rexistros, que cumpren os criterios de excepción.

Por exemplo, se a túa regra de coincidencia combina apelidos, cidade e data de nacemento, o sistema identificaría os xemelgos co mesmo apelidos que viven na mesma cidade e co mesmo perfil. Podes especificar unha excepción que non coincida cos perfís se os nome das entidades que combinas non son os mesmos.

1. Vaia a **Datos** > **Unify** > **Coincidencia** e seleccione **Editar** na regra á que desexa engadir condicións.

1. No **Editar regra** panel, seleccione **Engadir excepción**.

1. Especifique os criterios de excepción. 

1. Para gardar a regra, seleccione **Feito**.

### <a name="specify-custom-match-conditions"></a>Especificar condicións de coincidencia personalizadas

Podes especificar condicións que anulan a lóxica de coincidencia predeterminada. Hai catro opcións dispoñibles: 

|Opción  |Descripción |Exemplo  |
|---------|---------|---------|
|Coincidir sempre     | Define valores que sempre coinciden.         |  Sempre coincidir *Mike* e *Mike R*.       |
|Non coincidir nunca     | Define valores que nunca coinciden.        | Nunca coincidir *Xoán* e *Jonathan*.        |
|Omisión personalizada     | Define valores que o sistema debería ignorar sempre na fase de coincidencia. |  Ignorar os valores *11111* e *Descoñecido* durante o partido.        |
|Asignación de alias    | Definición de valores que o sistema debería considerar como o mesmo valor.         | Considera *Joe* ser igual a *Xosé*.        |

1. Vaia a **Datos** > **Unify** > **Coincidencia** e selecciona **Coincidencia personalizada** na sección **Detalles de rexistros coincidentes**.

   :::image type="content" source="media/custom-match-create.png" alt-text="Captura de pantalla da sección de regras de coincidencia con Control de coincidencias personalizado resaltado.":::

1. No **Personalizado** panel, vai ao **Rexistros** ficha.

1. Escolla a opción de coincidencia personalizada de **Tipo personalizado** menú despregable e seleccione **Descargar modelo**. Necesitas un modelo separado para cada opción de coincidencia.

1. Abre o ficheiro de modelo descargado e enche os detalles. O modelo contén campos para especificar a entidade e os valores de clave primarios da entidade a empregar na coincidencia personalizada. Por exemplo, se desexa a clave principal *12345* desde a entidade *Vendas* para atopar unha coincidencia sempre coa clave primaria *34567* desde a entidade *Contacto*, encha o modelo:
    - Entity1: vendas
    - Entity1Key: 12345
    - Entity2: Contacto
    - Entity2Key: 34567

   O mesmo ficheiro de modelo pode especificar rexistros de coincidencia personalizados de varias entidades.
   
   Se desexa especificar a busca de coincidencias personalizada para a desduplicación nunha entidade, proporcione a mesma entidade que Entidade1 e Entidade2 e estableza os diferentes valores da clave primaria.

1. Despois de engadir todas as substitucións, garda o ficheiro de modelo.

1. Vaia a **Datos** > **Fontes de datos** e inxira os ficheiros modelo como novas entidades.

1. Despois de cargar os ficheiros e cando as entidades están dispoñibles, seleccione a opción **Coincidencia personalizada** de novo. Verá opcións para especificar as entidades que quere incluír. Seleccione as entidades requiridas no menú despregable e seleccione **Feito**.

   :::image type="content" source="media/custom-match-overrides.png" alt-text="Captura de pantalla do diálogo para escoller substitucións para un escenario de coincidencia personalizado.":::

1. A aplicación da coincidencia personalizada depende da opción de coincidencia que queiras usar. 

   - Para **Sempre coincidir** ou **Nunca coincidir**, continúe co seguinte paso.
   - Para **Bypass personalizado** ou **Mapeo de alias**, seleccione **Editar** nunha regra de coincidencia existente ou cree unha nova. No menú despregable Normalizacións, escolla **Bypass personalizado** ou **Mapeo de alias** opción e seleccione **Feito**.

1. Seleccione **Gardar** na páxina **Coincidencia** para aplicar a configuración de coincidencia personalizada.

1. Seleccione **Executar** na páxina **Coincidencia** para iniciar o proceso de busca de coincidencias. Outras regras de coincidencia personalizadas son anuladas pola configuración de coincidencias personalizadas.

#### <a name="known-issues"></a>Problemas coñecidos

- A autocombinación non mostra os datos normalizados nas entidades de deduplicación. Non obstante, aplica a normalización internamente durante a deduplicación. É por deseño para todas as normalizacións. 
- Se a configuración do tipo semántico se elimina no ficheiro **Mapa** na fase cando unha regra de coincidencia utiliza a asignación de alias ou o bypass personalizado, a normalización non se aplicará. Só ocorre se borra o tipo semántico despois de configurar a normalización na regra de coincidencia porque o tipo semántico será descoñecido.


## <a name="next-step"></a>Seguinte paso

Despois de completar o proceso de coincidencia de polo menos un par de coincidencias, continúa ata o [**Combinar**](merge-entities.md) paso.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
