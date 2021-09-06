---
title: Buscar coincidencias de entidades para a unificación de datos
description: Busque coincidencias de entidades para crear perfís de clientes unificados.
ms.date: 02/23/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 7ad08b8b782654939c6bfc2ca330a3d31e71054a2f2c97a921971d1056b7cd38
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033675"
---
# <a name="match-entities"></a>Buscar coincidencias das entidades

A fase de coincidencia especifica como combinar os seus conxuntos de datos nun conxunto de datos de perfil de cliente unificado. Despois de completar o [paso de asignación](map-entities.md) no proceso de unificación de datos, estará listo para atopar unha coincidencia coas súas entidades. A fase de coincidencias require polo menos dúas entidades asignadas.

A páxina de coincidencia consta de tres seccións: 
- Métricas clave que resumen o número de rexistros coincidentes
- Orde de coincidencia e regras para as coincidencia entre entidades
- Regras para a eliminación de duplicados de entidades coincidentes

## <a name="specify-the-match-order"></a>Especificar a orde de coincidencia

Vaia a **Datos** > **Unificar** > **Buscar coincidencias** e seleccione **Establecer orde** para comezar a fase de busca de coincidencias.

Cada coincidencia unifica dúas ou máis entidades nunha única entidade consolidada. Ao mesmo tempo, garda os rexistros exclusivos dos clientes. Por exemplo, seleccionamos dúas entidades: **eCommerce: eCommerceContacts** como entidade primaria e **LoyaltyScheme: loyCustomers** como segunda entidade. A orde das entidades especifica en que orde tentará o sistema atopar coincidencias cos rexistros.

:::image type="content" source="media/match-page.png" alt-text="Captura de pantalla da páxina de coincidencias na área Unify do proceso de unificación de datos.":::
  
A entidade primaria *eCommerce: eCommerceContacts* coincide coa seguinte entidade *LoyaltyScheme: loyCustomers*. O conxunto de datos que resulta do primeiro paso de busca de coincidencia coincide coa seguinte entidade se ten máis de dúas entidades.

> [!IMPORTANT]
> A entidade que escolle como Primaria servirá de base para o seu conxunto de datos de perfís unificado. A esta entidade engadiranse entidades adicionais seleccionadas durante a fase de coincidencia. Isto non significa que a entidade unificada inclúa *todos* os datos incluídos nesta entidade.
>
> Hai dúas consideracións que poden axudarlle a elixir a xerarquía das súas entidades:
>
> - Escolla a entidade cos datos de perfil máis completos e fiables sobre os seus clientes como entidade principal.
> - Escolla a entidade que ten varios atributos en común con outras entidades (por exemplo, nome, número de teléfono ou enderezo de correo electrónico) como entidade principal.

Despois de especificar a orde de coincidencia, verá os pares de coincidencias definidos na sección **Detalles de rexistros coincidentes** en **Datos** > **Unify** > **Coincidencia**. As métricas clave estarán baleiras ata que finalice o proceso de coincidencia.

## <a name="define-rules-for-match-pairs"></a>Definir regras para parellas coincidentes

As regras de coincidencia especifican a lóxica coa que se combinará un par específico de entidades.

A advertencia **Precisa regras** situada xunto ao nome dunha entidade suxire que non se define ningunha regra de coincidencia para un par de coincidencias. 

:::image type="content" source="media/match-rule-add.png" alt-text="Captura de pantalla da sección Detalles do rexistro coincidente con control para engadir regras resaltadas.":::

1. Seleccione **Engadir regras** nunha entidade na sección **Detalles de rexistros coincidentes** para definir as regras de coincidencia.

1. No panel **Crear regra**, configure as condicións para a regra.

   :::image type="content" source="media/match-rule-conditions.png" alt-text="Captura de pantalla dunha regra de coincidencia aberta con condicións engadidas.":::

   - **Entidade/Campo (primeira fila)**: escolla unha entidade relacionada e un atributo para especificar unha propiedade de rexistro que probablemente sexa exclusiva dun cliente. Por exemplo, un número de teléfono ou enderezo de correo electrónico. Evite a coincidencia por atributos de tipo de actividade. Por exemplo, un ID de compra probablemente non atopará coincidencias noutros tipos de rexistros.

   - **Entidade/Campo (segunda fila)**: escolla un atributo relacionado co atributo da entidade especificado na primeira fila.

   - **Normalizar**: seleccione unha das seguintes opcións de normalización para os atributos seleccionados. 
     - Espazo en branco: elimina todos os espazos. *Ola Mundo* convértese en *HelloWorld*.
     - Símbolos: elimina todos os símbolos e caracteres especiais. *Head&Shoulder* convértese en *HeadShoulder*.
     - Texto en minúsculas: converte todos os caracteres en minúscula. *MAIÚSCULAS e maiúscula inicial de palabra* convértese en *maiúsculas e maiúscula inicial de palabra*.
     - Unicode a ASCII: converte a notación unicode en caracteres ASCII. */u00B2* convértese en *2*.
     - Numerais: converte outros sistemas numerais, como os números romanos, en números árabes. *VIII* pasa a ser *8*.
     - Tipos semánticos: estandariza nomes, títulos, números de teléfono, enderezos, etc. 

   - **Precisión**: define o nivel de precisión para aplicar a esta condición. 
     - **Básico**: escolla entre *Baixo*, *Medio*, *Alto* e *Exacto*. Seleccione **Exacto** para atopar a coincidencia só con rexistros que se corresponden ao 100 por cento. Seleccione un dos outros niveis para atopar coincidencias de rexistros que non sexan 100 por cento idénticos.
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

As regras de coincidencia representan conxuntos de condicións. Para atopar coincidencias de entidades por condicións baseadas en varios atributos, engada máis regras

1.  Vaia a **Datos** > **Unify** > **Coincidencia** e seleccione **Engadir regra** na entidade á que desexa engadir regras.

2. Siga os pasos indicados en [Definir regras para parellas de coincidencias](#define-rules-for-match-pairs).

> [!NOTE]
> A orde das regras importa. O algoritmo de coincidencias tenta atopar coincidencias baseándose na súa primeira regra e continúa coa segunda regra só se non se identificaron coincidencias coa primeira regra.

### <a name="change-the-entity-order-in-match-rules"></a>Cambiar a orde de entidades nas regras de busca de coincidencias

Pode reordenar as entidades para que as regras de busca de coincidencias cambien a orde en que se procesan. Eliminaranse as regras en conflito por mor dun cambio de orde. Ten que volver crear as regras eliminadas cunha configuración actualizada.

1. Vaia a **Datos** > **Unificar** > **Buscar coincidencias** e seleccione **Editar**.

1. No panel **Editar regra**, seleccione o control **Mover cara arriba ou cara abaixo** ou arrastre e solte as entidades para cambiar a orde.

   :::image type="content" source="media/reorder-match-rules.png" alt-text="Opcións para cambiar a orde en que se procesan as entidades na fase de busca de coincidencias.":::

1. Para gardar a regra, seleccione **Feito**.

## <a name="define-deduplication-on-a-match-entity"></a>Definir a desduplicación nunha entidade coincidente

Ademais de [regras de coincidencia entre entidades](#define-rules-for-match-pairs), tamén pode especificar regras de cancelación de duplicacións. *Cancelación de duplicación* é outro proceso ao atopar coincidencias con rexistros. Identifica rexistros duplicados e úneos nun rexistro. Os rexistros de orixe vincúlanse co rexistro combinado con ID alternativos.

Os rexistros con coincidencia duplicada utilizaranse no proceso de busca de coincidencias entre entidades. A cancelación da duplicación ocorre en entidades individuais e pódese configurar cada entidade usada en pares de coincidencias.

Non é obrigatorio especificar regras de desduplicación. Se non se configuran tales regras, aplícanse as regras definidas polo sistema. Combinan todos os rexistros nun único rexistro antes de pasar os datos da entidade á coincidencia entre entidades para obter un mellor rendemento.

### <a name="add-deduplication-rules"></a>Engadir regras de desduplicación

1. Vaia a **Datos** > **Unify** > **Coincidencia**.

1. Na sección **Combinar duplicados**, seleccione **Establecer entidades**. Se xa se crearon regras de cancelación de duplicación, seleccione **Editar**.

1. No panel **Preferencias de combinación**, escolla as entidades nas que desexa executar a cancelación da duplicación.

1. Especifique como combinar os rexistros duplicados e escolla unha das tres opcións:
   - **Máis cheo**: identifica o rexistro con máis campos de atributos cubertos como o rexistro gañador. É a opción de combinación predefinida.
   - **Máis recente**: Identifica o rexistro gañador en función da data máis recente. Require unha data ou un campo numérico para definir a actualidade.
   - **Menos recente**: Identifica o rexistro gañador en función da data menos recente. Require unha data ou un campo numérico para definir a actualidade.
 
   > [!div class="mx-imgBorder"]
   > ![Paso 1 das regras de eliminación de duplicados.](media/match-selfconflation.png "Paso 1 das regras de desduplicación")
 
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

1. Despois de [executar o proceso de busca de coincidencias](#run-the-match-process), verá as estatísticas de cancelación de duplicación nos mosaicos de métricas de claves.

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

> [!TIP]
> Despois de executar o proceso de coincidencias, seleccione o estado do proceso para abrir o panel **Detalles da tarefa**. Ofrece unha visión xeral sobre o tempo de procesamento, a última data de procesamento e todos os erros e avisos asociados á tarefa. Seleccione **Ver detalles** para ver que entidades participaron no proceso de coincidencias, que regras se lles aplicaron e se as actualizacións se publicaron correctamente.  
> Existen [seis tipos de estado](system.md#status-types) para as tarefas ou os procesos. Ademais, a maioría dos procesos [dependen doutros procesos descendentes](system.md#refresh-policies).  
> :::image type="content" source="media/process-detail-path.png" alt-text="Camiño detallado para chegar aos detalles do proceso desde a ligazón de estado da tarefa.":::

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

## <a name="specify-custom-match-conditions"></a>Especificar condicións de coincidencia personalizadas

Pode especificar condicións que determinados rexistros deben coincidir sempre ou nunca. Estas regras pódense cargar para anular o proceso de busca de coincidencias estándar. Por exemplo, se hai John Doe I e John Doe II nos nosos rexistros, o sistema pode consideralos como unha persoa. As regras de busca de coincidencia personalizadas permítenlle especificar que os seus perfís se refiren a diferentes persoas. 

1. Vaia a **Datos** > **Unify** > **Coincidencia** e selecciona **Coincidencia personalizada** na sección **Detalles de rexistros coincidentes**.

  :::image type="content" source="media/custom-match-create.png" alt-text="Captura de pantalla da sección de regras de coincidencia con Control de coincidencias personalizado resaltado.":::

1. Se non ten definidas as regras de coincidencia personalizadas, verá un novo panel **Coincidencia personalizada** con máis detalles.

1. Seleccione **Encha o modelo** para obter un ficheiro de modelo que poida especificar os rexistros cos que as entidades deben coincidir ou non coincidir nunca. Deberá cubrir por separado os rexistros de "coincidir sempre" e "nunca coincidir" en dous ficheiros diferentes.

1. O modelo contén campos para especificar a entidade e os valores de clave primarios da entidade a empregar na coincidencia personalizada. Por exemplo, se desexa a clave principal *12345* desde a entidade *Vendas* para atopar unha coincidencia sempre coa clave primaria *34567* desde a entidade *Contacto*, encha o modelo:
    - Entity1: vendas
    - Entity1Key: 12345
    - Entity2: Contacto
    - Entity2Key: 34567

   O mesmo ficheiro de modelo pode especificar rexistros de coincidencia personalizados de varias entidades.
   
   Se desexa especificar a busca de coincidencias personalizada para a desduplicación nunha entidade, proporcione a mesma entidade que Entidade1 e Entidade2 e estableza os diferentes valores da clave primaria.

1. Despois de engadir todas as substitucións que desexa aplicar, garde o ficheiro de modelo.

1. Vaia a **Datos** > **Fontes de datos** e inxira os ficheiros modelo como novas entidades. Unha vez inxeridos, pode utilizalos para especificar a configuración da coincidencia.

1. Despois de cargar os ficheiros e cando as entidades están dispoñibles, seleccione a opción **Coincidencia personalizada** de novo. Verá opcións para especificar as entidades que quere incluír. Seleccione as entidades requiridas no menú despregable.

   :::image type="content" source="media/custom-match-overrides.png" alt-text="Captura de pantalla do diálogo para escoller substitucións para un escenario de coincidencia personalizado.":::

1. Seleccione as entidades que desexa empregar para **Coincidir sempre** e **Non coincidir nunca** e seleccione **Feito**.

1. Seleccione **Gardar** na páxina **Coincidencia** para aplicar a configuración de coincidencia personalizada.

1. Seleccione **Executar** na páxina **Coincidencia** para iniciar o proceso de busca de coincidencias. Outras regras de coincidencia personalizadas son anuladas pola configuración de coincidencias personalizadas.

> [!TIP]
> Vaia a **Datos** > **Entidades** e revise a entidade **ConflationMatchPair** para confirmar que se aplican as substitucións.

## <a name="next-step"></a>Seguinte paso

Despois de completar o proceso de coincidencia durante polo menos unha par de coincidencias, pode resolver as posibles contradicións dos seus datos a través do tema [**Combinar**](merge-entities.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
