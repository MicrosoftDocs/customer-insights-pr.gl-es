---
title: Buscar coincidencias de entidades para a unificación de datos
description: Busque coincidencias de entidades para crear perfís de clientes unificados.
ms.date: 10/14/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 05afd17b7f1b34f7f24a8fa8cb2dc32c1649d40f
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267476"
---
# <a name="match-entities"></a>Buscar coincidencias das entidades

Despois de completar a fase de asignación, xa está preparado para atopar a coincidencia coas súas entidades. A fase de coincidencia especifica como combinar os seus conxuntos de datos nun conxunto de datos de perfil de cliente unificado. A fase de coincidencias require polo menos [dúas entidades asignadas](map-entities.md).

## <a name="specify-the-match-order"></a>Especificar a orde de coincidencia

Vaia a **Datos** > **Unificar** > **Buscar coincidencias** e seleccione **Establecer orde** para comezar a fase de busca de coincidencias.

Cada coincidencia unifica dous ou máis entidades nunha única entidade, mentres continuará cada rexistro de cliente único. No seguinte exemplo, seleccionamos tres entidades: **ContactCSV: TestData** como entidade **Primaria**, **WebAccountCSV: TestData** como **Entidade 2** e **CallRecordSmall: TestData** como **Entidade 3**. O diagrama situado sobre as seleccións ilustra como se executará a orde de coincidencia.

> [!div class="mx-imgBorder"]
> ![Editar a orde de coincidencia de datos](media/configure-data-match-order-edit-page.png "Editar a orde de coincidencia de datos")
  
A entidade **Primaria** corresponderase coa **Entidade 2**. O conxunto de datos que resulta da primeira coincidencia correspóndese con **Entidade 3**.
Neste exemplo, só seleccionamos dúas coincidencias, pero o sistema pode soportar máis.

> [!IMPORTANT]
> A entidade que escolle como **Primaria** servirá de base para o seu conxunto de datos principal unificado. A esta entidade engadiranse entidades adicionais seleccionadas durante a fase de coincidencia. Ao mesmo tempo, isto non significa que a entidade unificada inclúa *todo* os datos incluídos nesta entidade.
>
> Hai dúas consideracións que poden axudarlle a elixir a xerarquía das súas entidades:
>
> - Que entidade considera que ten os datos máis completos e fiables sobre os seus clientes?
> - A entidade que acaba de identificar ten atributos que tamén son compartidos por outras entidades (por exemplo, nome, número de teléfono ou enderezo de correo electrónico)? De non ser así, escolla a súa segunda entidade máis fiable.

Seleccione **Feito** para gardar a súa orde de coincidencia.

## <a name="define-rules-for-your-first-match-pair"></a>Definir regras para o seu primeiro par de coincidencias

Despois de especificar a orde de coincidencia, verá as coincidencias definidas na páxina **Coincidencia**. Os mosaicos da parte superior da pantalla estarán baleiros ata que execute a orde de coincidencia.

> [!div class="mx-imgBorder"]
> ![Definir regras](media/configure-data-match-need-rules.png "Definir regras")

A advertencia **Necesita regras** suxire que non se defina ningunha regra de coincidencia para un par de coincidencias. As regras de coincidencia especifican a lóxica coa que se combinará un par específico de entidades.

1. Para definir a súa primeira regra, abra o panel **Definición da regra** seleccionando a liña de coincidencia correspondente na táboa de coincidencias (1) e logo seleccione **Crea unha nova regra** (2).

   > [!div class="mx-imgBorder"]
   > ![Crear nova regra](media/configure-data-match-new-rule2.png "Crear nova regra")

2. No panel **Editar a regra**, configure as condicións para esta regra. Cada condición está representada por dúas filas que inclúen seleccións obrigatorias.

   > [!div class="mx-imgBorder"]
   > ![Panel de Regra nova](media/configure-data-match-new-rule-condition.png "Panel de Regra nova")

   Entidade/Campo (primeiro): un atributo que se empregará para as coincidencias desde a primeira entidade de par de coincidencias. Entre os posibles exemplos poden incluírse un número de teléfono ou un enderezo de correo electrónico. Elixa un atributo que poida ser único para o cliente.

   > [!TIP]
   > Evite atopar coincidencias en función de atributos de tipo de actividade. Noutras palabras, se un atributo parece ser unha actividade, pode que sexa un criterio deficiente para atopar coincidencias.  

   Entidade/Campo (segundo): un atributo que se empregará para as coincidencias desde a segunda entidade de par de coincidencias.

   Normalizar - **Método de normalización**: dispón de varias opcións de normalización para os atributos seleccionados. Por exemplo, eliminar a puntuación ou eliminar espazos

   Para a normalización do nome da organización (vista previa), tamén pode seleccionar **Tipo (teléfono, nome, organización)**

   > [!div class="mx-imgBorder"]
   > ![Normalización-B2B](media/match-normalization-b2b.png "Normalización-B2B")

   Nivel de precisión: o nivel de precisión que se empregará para esta condición. Establecer un nivel de precisión para unha condición de coincidencia pode ter dous tipos: **Básico** e **Personalizado**.  
   - Básico: ofrécelle catro opcións para seleccionar: baixo, medio, alto e exacto. Seleccione **Exacto** para atopar a coincidencia só con rexistros que se corresponden ao 100 por cento. Seleccione un dos outros niveis para atopar coincidencias de rexistros que non sexan 100 por cento idénticos.
   - Personalizado: use o control esvaradío para definir a porcentaxe personalizada que os rexistros precisan para atopar coincidencias ou introduza un valor no campo **Personalizado**. O sistema só atopará a coincidencia cos rexistros que superen este limiar como pares de coincidencia de combinación. Os valores do cursor da barra de desprazamento están entre 0 e 1. Polo tanto, o 0,64 representa o 64 por cento.

3. Para gardar a regra, seleccione **Feito**.

### <a name="add-multiple-conditions"></a>Engadir múltiples condicións

Para atopar a coincidencia das túas entidades só se se cumpren varias condicións, engada máis condicións ligadas a través dun operador AND.

1. No panel **Editar regra**, seleccione **Engadir condición**. Tamén pode eliminar condicións seleccionando o botón eliminar situado xunto a unha condición existente.

2. Para gardar a regra, seleccione **Feito**.

## <a name="add-multiple-rules"></a>Engadir varias regras

Cada condición aplícase a un único par de atributos, mentres que as regras representan conxuntos de condicións. Para que as súas entidades coincidan con diferentes conxuntos de atributos, pode engadir máis regras.

1. Na información do público, vaia a **Datos** > **Unificar** > **Buscar coincidencias**.

2. Seleccione a entidade que desexa actualizar e seleccione **Engadir regras**.

3. Siga o procedemento segundo o exposto en [Definir regras para o seu primeiro par de coincidencias](#define-rules-for-your-first-match-pair).

> [!NOTE]
> A orde das regras é importante. O algoritmo de correspondencia intenta coincidir baseándose na súa primeira regra e continúa ata a segunda regra só se non se identificaron coincidencias coa primeira regra.

## <a name="define-deduplication-on-a-match-entity"></a>Definir a desduplicación nunha entidade coincidente

Xunto con especificar regras de busca de coincidencias de entidades cruzadas como se describe nas seccións anteriores, tamén pode especificar regras de deduplicacións. A *desduplicación* é un proceso. Identifica rexistros duplicados, combínaos nun rexistro e vincula todos os rexistros de orixe a este rexistro combinado con ID alternativos ao rexistro combinado.

Despois de identificar un rexistro desduplicado, este utilizarase no proceso de busca de coincidencias entre entidades. A desduplicación implántase a nivel de entidade e pódese aplicar a todas as entidades empregadas no proceso de busca de coincidencias.

### <a name="add-deduplication-rules"></a>Engadir regras de desduplicación

1. Na información do público, vaia a **Datos** > **Unificar** > **Buscar coincidencias**.

1. Na sección **Combinar duplicados**, seleccione **Establecer entidades**.

1. Na sección **Combinar preferencias**, seleccione as entidades ás que desexa aplicar a desduplicación.

1. Especifique como combinar os rexistros duplicados e escolla unha das tres opcións de combinación:
   - *Máis cheo*: Identifica o rexistro con máis atributos cubertos como o rexistro gañador. Esta é a opción de combinación predefinida.
   - *Máis recente*: Identifica o rexistro gañador en función da data máis recente. Require unha data ou un campo numérico para definir a actualidade.
   - *Menos recente*: Identifica o rexistro gañador en función da data menos recente. Require unha data ou un campo numérico para definir a actualidade.
 
   > [!div class="mx-imgBorder"]
   > ![Paso 1 das regras de desduplicación](media/match-selfconflation.png "Paso 1 das regras de desduplicación")
 
1. Unha vez seleccionadas as entidades e configurada a súa preferencia de combinación, seleccione **Crear nova regra** para definir as regras de desduplicación a nivel de entidade.
   - **Seleccionar campo** lista todos os campos dispoñibles desa entidade na que desexa desduplicar os datos de orixe.
   - Especifique a configuración de normalización e precisión dun xeito similar ao especificado na busca de coincidencias entre entidades.
   - Pode definir condicións adicionais seleccionando **Engadir condición**.
 
   > [!div class="mx-imgBorder"]
   > ![Paso 2 das regras de desduplicación](media/match-selfconflation-rules.png "Paso 2 das regras de desduplicación")

  Pode crear varias regras de desduplicación para unha entidade. 

1. Executar o proceso de busca de coincidencias agora agrupa os rexistros en función das condicións definidas nas regras de desduplicación. Despois de agrupar os rexistros, aplícase a política de combinación para identificar o rexistro gañador.

1. Este rexistro gañador pásase á busca de coincidencias entre entidades, xunto cos rexistros non gañadores (por exemplo, ID alternativos) para mellorar a calidade das coincidencias.

1. Calquera regra de busca de coincidencias personalizada definida para buscar coincidencias sempre e nunca invalida as regras de desduplicación. Se unha regra de desduplicación identifica rexistros coincidentes e se establece unha regra de busca de coincidencias personalizada para que nunca busque coincidencias neses rexistros, entón neses dous rexistros non se buscarán coincidencias.

1. Despois de executar o proceso de busca de coincidencias, verá as estatísticas de desduplicación.
   
> [!NOTE]
> Non é obrigatorio especificar regras de desduplicación. Se non se configuran tales regras, aplícanse as regras definidas polo sistema. Contraen todos os rexistros que comparten a mesma combinación de valores (coincidencia exacta) da clave primaria e os campos das regras de busca de coincidencias nun único rexistro antes de pasar os datos da entidade á busca de coincidencias entre entidades para un mellor rendemento e estado do sistema.

## <a name="run-your-match-order"></a>Executar a orde de coincidencias

Despois de definir as regras de busca de coincidencias, incluídas as regras de busca de coincidencias entre entidades e desduplicación, pode executar a orde de busca de coincidencias. Na páxina **Coincidencia**, seleccione **Executar** para iniciar o proceso. O algoritmo de correspondencia pode tardar algún tempo en completarse. Non pode modificar as propiedades na páxina **Coincidencia** ata que se complete o proceso de coincidencia. Atopará a entidade do perfil de cliente unificada que se creou na páxina **Entidades**. A entidade de cliente unificada chámase **ConflationMatchPairs : CustomerInsights**.

Para facer cambios adicionais e volver executar o paso, pode cancelar unha coincidencia en curso. Seleccione o texto **Actualizando...** e seleccione **Cancelar traballo** na parte inferior do panel lateral que aparece.

Cando o proceso de coincidencia estea completado, o texto **Actualizando...** cambiará a **Correcto** e poderá usar de novo todas as funcionalidades da páxina.

O primeiro proceso de coincidencia dá como resultado a creación dunha entidade principal unificada. Todas as execucións posteriores de coincidencias provocan a expansión da entidade.

> [!TIP]
> Existen [seis tipos de estado](system.md#status-types) para as tarefas ou os procesos. Ademais, a maioría dos procesos [dependen doutros procesos descendentes](system.md#refresh-policies). Pode seleccionar o estado dun proceso para ver detalles sobre o progreso de todo o traballo. Despois de seleccionar **Ver detalles** para unha das tarefas do traballo, atopará información adicional: o tempo de procesamento, a última data de procesamento e todos os erros e avisos asociados á tarefa.

## <a name="deduplication-output-as-an-entity"></a>Saída de desduplicación como entidade
Ademais da entidade principal unificada creada como parte da busca de coincidencias entre entidades, o proceso de desduplicación tamén xera unha nova entidade para cada entidade a partir da orde de busca de coincidencias para identificar os rexistros desduplicados. Estas entidades pódense atopar xunto con **ConflationMatchPairs:CustomerInsights** na sección **Sistema** da páxina **Entidades**, co nome **Deduplication_Datasource_Entity**.

Unha entidade de saída de desduplicación contén a seguinte información:
- Identificadores ou claves
  - Campo de clave primaria e o seu campo de ID alternativos. O campo ID alternativos consiste en todos os ID alternativos identificados para un rexistro.
  - O campo Deduplication_GroupId mostra o grupo ou clúster identificado dentro dunha entidade que agrupa todos os rexistros similares en función dos campos de desduplicación especificados. Isto úsase con fins de procesamento do sistema. Se non hai regras de desduplicación manual especificadas e se aplican regras de desduplicación definidas polo sistema, é posible que non atope este campo na entidade de saída da desduplicación.
  - Deduplication_WinnerId: este campo contén o ID gañador dos grupos ou clústeres identificados. Se o Deduplication_WinnerId é o mesmo que o valor da clave primaria para un rexistro, significa que o rexistro é o rexistro gañador.
- Campos empregados para definir as regras de desduplicación.
- Campos Regra e Puntuación para indicar cal das regras de desduplicación se aplicou e a puntuación devolta polo algoritmo de correspondencia.

## <a name="review-and-validate-your-matches"></a>Revisar e validar as súas coincidencias

Avalíe a calidade das súas parellas de coincidencia e refínea:

- Na páxina **Coincidencia**, atopará dous mosaicos que amosarán información inicial sobre os seus datos.

  - **Clientes únicos**: amosa o número de perfís exclusivos que o sistema identificou.
  - **Rexistros coincidentes**: amosa o número de coincidencias entre todas as súas parellas coincidentes.

- Na táboa **Orde de coincidencia**, pode avaliar os resultados de cada par de coincidencias comparando o número de rexistros que proviñan desta entidade de parella de coincidencias coa porcentaxe de rexistros combinados con éxito.

- Na sección **Regras** dunha entidade na táboa **Orde de coincidencia**, atopará a porcentaxe de rexistros coincidentes atopados con éxito a nivel de regra. Seleccionando o símbolo da táboa xunto a unha regra, pode ver todos estes rexistros a nivel de regra. Recomendamos que revise un subconxunto de rexistros para validar que se emparellaron correctamente.

- Experimente con diferentes limiares de precisión arredor das súas condicións para identificar o valor óptimo.

  1. Seleccione os tres puntos (...) da regra de parella de coincidencias que quere probar e seleccione **Editar**.

  2. Seleccione a condición coa que desexa experimentar. Cada criterio está representado por unha fila no panel **Regra de coincidencia**.

  3. O que verá na páxina **Vista previa de criterios** depende do nivel de precisión que seleccionou para unha condición. Busque o número de rexistros coincidentes e non coincidentes para a condición seleccionada.

     Coñeza os efectos dos distintos niveis de limiares diferentes. Pode comparar cantos rexistros serán coincidentes baixo cada un dos niveis de limiares e ver os rexistros baixo cada opción. Seleccione cada un dos mosaicos e revise os datos da sección da táboa.

## <a name="optimize-your-matches"></a>Optimizar as súas coincidencias

Aumente a calidade reconfigurando algúns dos parámetros da coincidencia:

- **Cambie a orde de coincidencia** seleccionando **Editar** e cambie os campos de orde de coincidencia.

  > [!div class="mx-imgBorder"]
  > ![Editar a orde de coincidencia de datos](media/configure-data-match-order-edit.png "Editar a orde de coincidencia de datos")

- **Cambie a orde das súas regras** se definiu varias regras. Pode reordenar as regras da coincidencia seleccionando as opcións **Mover cara arriba** e **Mover cara abaixo** na grade de regras de coincidencia.

  > [!div class="mx-imgBorder"]
  > ![Cambiar orde da regra](media/configure-data-change-rule-order.png "Cambiar orde da regra")

- **Duplique as súas regras** se definiu unha regra de coincidencia e quere crear unha regra similar con modificacións. Para iso, seleccione **Duplicar**.

  > [!div class="mx-imgBorder"]
  > ![Duplicar unha regra](media/configure-data-duplicate-rule.png "Duplicar unha regra")

- **Desactivar unha regra** para manter unha regra de busca de coincidencias mentres a exclúe do proceso de busca de coincidencias.

  > [!div class="mx-imgBorder"]
  > ![Desactivar unha regra](media/configure-data-deactivate-rule.png "Desactivar unha regra")

- **Edite as súas regras** seleccionando o símbolo **Editar**. Pode aplicar as seguintes modificacións:

  - Cambiar atributos para unha condición: seleccione novos atributos dentro da fila da condición específica.
  - Cambiar o limiar dunha condición: axuste o cursor da barra de desprazamento de precisión.
  - Cambiar o método de normalización dunha condición: actualizar o método de normalización.

## <a name="specify-your-custom-match-records"></a>Especificar os seus rexistros de coincidencias personalizados

Pode especificar condicións que determinados rexistros deben coincidir sempre ou nunca. Estas regras pódense cargar en masa no proceso de coincidencia.

1. Seleccione a opción **Coincidencia personalizada** na pantalla **Orde de coincidencia**.

   > [!div class="mx-imgBorder"]
   > ![Crear unha coincidencia personalizada](media/custom-match-create.png "Crear unha coincidencia personalizada")

2. Se non ten entidades cargadas, verá unha nova caixa de diálogo de **Coincidencia personalizada** que require completar algúns detalles. Se forneceu estes detalles anteriormente, pase ao paso 8.

   > [!div class="mx-imgBorder"]
   > ![Nova caixa de diálogo de coincidencia personalizada](media/custom-match-new-dialog-box.png "Nova caixa de diálogo de coincidencia personalizada")

3. Seleccione **Encha o modelo** para obter un ficheiro de modelo que poida especificar os rexistros cos que as entidades deben coincidir ou non coincidir nunca. Deberá cubrir por separado os rexistros de "coincidir sempre" e "nunca coincidir" en dous ficheiros diferentes.

4. O modelo contén campos para especificar a entidade e os valores de clave primarios da entidade a empregar na coincidencia personalizada. Por exemplo, se desexa que a clave primaria 12345 da entidade de vendas coincida sempre coa clave primaria 34567 da entidade de contacto, terá que especificar o seguinte:
    - Entity1: vendas
    - Entity1Key: 12345
    - Entity2: Contacto
    - Entity2Key: 34567

   O mesmo ficheiro de modelo pode especificar rexistros de coincidencia personalizados de varias entidades.
   
   Se desexa especificar a busca de coincidencias personalizada para a desduplicación nunha entidade, proporcione a mesma entidade que Entidade1 e Entidade2 e estableza os diferentes valores da clave primaria.

5. Despois de engadir todas as substitucións que desexa aplicar, garde o ficheiro de modelo.

6. Vaia a **Datos** > **Fontes de datos** e inxira os ficheiros modelo como novas entidades. Unha vez inxeridos, pode utilizalos para especificar a configuración da coincidencia.

7. Despois de cargar os ficheiros e cando as entidades están dispoñibles, seleccione a opción **Coincidencia personalizada** de novo. Verá opcións para especificar as entidades que quere incluír. Seleccione as entidades requiridas do menú despregable.

   > [!div class="mx-imgBorder"]
   > ![Anulacións de coincidencia personalizadas](media/custom-match-overrides.png "Anulacións de coincidencia personalizadas")

8. Seleccione as entidades que desexa empregar para **Coincidir sempre** e **Non coincidir nunca** e seleccione **Feito**.

9. Seleccione **Gardar** na páxina **Coincidir** para a configuración de coincidencia personalizada que acaba de configurar.

10. Seleccione **Executar** na páxina **Coincidencia** para iniciar o proceso de coincidencia e a configuración da coincidencia personalizada entrará en vigor. As normas que coincidan co sistema serán anuladas pola configuración establecida.

11. Cando remate a detección de coincidencias, pode verificar a entidade **ConflationMatchPair** para confirmar que as anulacións se aplican nas coincidencias de combinación.

## <a name="next-step"></a>Seguinte paso

Despois de completar o proceso de coincidencia durante polo menos unha par de coincidencias, pode resolver as posibles contradicións dos seus datos a través do tema [**Combinar**](merge-entities.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]