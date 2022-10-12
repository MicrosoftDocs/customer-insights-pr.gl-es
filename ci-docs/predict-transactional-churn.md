---
title: Churn de transaccións predición (contén vídeo)
description: Prediga se un cliente está en risco de deixar de comprar os seus servizos ou produtos.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: fd8df0f0a168ddfab9e8ad3af9e1f1fc0bc1b7a2
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610510"
---
# <a name="predict-transaction-churn"></a>Predicir abandono de transaccións

A predición do abandono transaccional axuda a predicir se un cliente deixará de mercar os seus produtos ou servizos nunha xanela de tempo determinada.

Debes ter coñecementos comerciais para entender o que significa churn para a túa empresa. Admitimos as definicións de abandono baseadas no tempo, o que significa que se considera que un cliente abandonou despois dun período sen compras.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6Eg]

Para contornos baseados en contas empresariais, podemos predicir o cambio transaccional dunha conta e tamén unha combinación de conta e outro nivel de información como a categoría de produto. Por exemplo, engadir unha dimensión pode axudar a determinar a probabilidade de que a conta "Contoso" deixe de mercar a categoría de produto "papelería de oficina". Ademais, para as contas empresariais, tamén podemos empregar a IA para xerar unha lista de posibles motivos polos que é probable que unha conta cambie unha categoría de información de nivel secundario.

> [!TIP]
> Proba o churn de transaccións predición usando datos de mostra: [Guía de exemplo de abandono de transaccións predición](sample-guide-predict-transactional-churn.md).

## <a name="prerequisites"></a>Requisitos previos

- Polo menos [Permisos de colaborador](permissions.md).
- Polo menos 10 perfís de clientes, preferiblemente máis de 1.000 clientes únicos.
- Identificador de cliente, un identificador único para relacionar as transaccións cos seus clientes.
- Datos de transaccións para polo menos o dobre da xanela de tempo seleccionada, como dous ou tres anos de historial de transaccións. Idealmente, polo menos dúas transaccións por cliente. O historial de transaccións debe incluír:
  - **ID de transacción** : identificador único dunha compra ou transacción.
  - **Data da transacción** : Data da compra ou transacción.
  - **Valor da transacción** : importe da moeda ou valor numérico da transacción.
  - **ID de produto único** : ID do produto ou servizo adquirido se os seus datos están nun nivel de liña.
  - **Se esta transacción foi unha devolución** : un campo verdadeiro/falso que identifica se a transacción foi unha devolución ou non. Se o **Valor da transacción** é negativo, inferimos un retorno.
- Datos da actividade do cliente:
  - Identificador de cliente, un identificador único para mapear actividades aos seus clientes.
  - **Chave primaria:** Identificador único para unha actividade. Por exemplo, unha visita ao sitio web ou un rexistro de uso que mostra que o cliente probou unha mostra do seu produto.
  - **Marca de tempo:** Data e hora do evento identificado pola chave primaria.
  - **Evento:** Nome do evento que queres usar. Por exemplo, un campo chamado "UserAction" nunha tenda de ultramarinos pode ser un cupón utilizado polo cliente.
  - **Detalles:** información detallada sobre o evento. Por exemplo, un campo chamado "CouponValue" nunha tenda de alimentación pode ser o valor en moeda do cupón.
- Menos do 20% dos valores que faltan no campo de datos da entidade facilitada

Para as contas empresariais (B-to-B), engade datos de clientes aliñados a atributos máis estáticos para garantir que o modelo funcione mellor:
- **ID de cliente:** Identificador único para un cliente.
- **Data de creación:** Data na que se engadiu inicialmente o cliente.
- **Estado ou Provincia:** Localización do estado ou provincia dun cliente.
- **País:** País dun cliente.
- **Industria:** Tipo de industria dun cliente. Por exemplo, un campo chamado "Sector" nun torrador de café pode indicar se o cliente vendía polo miúdo.
- **Clasificación:** Categorización dun cliente para a súa empresa. Por exemplo, un campo chamado "ValueSegment" nun torrador de café pode ser o nivel do cliente en función do tamaño do cliente.

> [!NOTE]
> Para unha empresa con alta frecuencia de compra de clientes (cada poucas semanas), recoméndase seleccionar unha ventá predición máis curta e definir o abandono. Para unha frecuencia de compra baixa (cada poucos meses ou unha vez ao ano), elixa unha fiestra máis longa de predición e defina o abandono.

## <a name="create-a-transaction-churn-prediction"></a>Crear unha predición do abandono da transacción

1. Ir a **Intelixencia** > **Predicións**.

1. No **Crear** ficha, seleccione **Usa modelo** no **Modelo de abandono de clientes** tella.

1. Seleccione **Transacción** para o tipo de churn e despois **Comezar**.

1. **Poña nome a este modelo** e o **Nome da entidade de saída** para distinguilos doutros modelos ou entidades.

1. Seleccione **Seguinte**.

### <a name="define-customer-churn"></a>Definir renovación do cliente

Seleccione **Garda o borrador** en calquera momento para gardar o predición como borrador. O borrador predición móstrase no **As miñas predicións** ficha.

1. Establece o **predición xanela**. Por exemplo, predicir o risco de abandono dos seus clientes durante os próximos 90 días para alinearse cos seus esforzos de retención de mercadotecnia. A predición do risco de abandono por un período de tempo máis longo ou máis curto pode facer máis difícil abordar os factores do seu perfil de risco de abandono, pero depende das necesidades específicas do seu negocio.

1. Introduza o número de días para definir o abandono **Definición de churn** campo. Por exemplo, se un cliente non realizou unha compra nos últimos 30 días, é posible que se considere que a súa empresa está revertida.

1. Seleccione **Seguinte**.

### <a name="add-purchase-history"></a>Engadir historial de compra

1. Seleccione **Engadir datos** para **Historial de transaccións do cliente**.

1. Seleccione o tipo de actividade semántica, **Pedido de venda** ou **Liña de pedidos de vendas**, que contén a información do historial de transaccións. Se a actividade non está configurada, seleccione **aquí** e crealo.

1. Baixo **Actividades**, se os atributos da actividade foron mapeados semanticamente cando se creou a actividade, escolla os atributos ou a entidade específicos nos que desexa que se centre o cálculo. Se non se produciu a asignación semántica, seleccione **Editar** e mapea os teus datos.

   :::image type="content" source="media/transaction-churn-select-activity.PNG" alt-text="Panel lateral que mostra a elección de actividades específicas baixo o tipo semántico.":::

1. Seleccione **A continuación** e revise os atributos necesarios para este modelo.

1. Seleccione **Gardar**.

1. Engade máis actividades ou selecciona **A continuación**.

# <a name="individual-consumers-b-to-c"></a>[Consumidores individuais (B2C)](#tab/b2c)

### <a name="add-additional-data-optional"></a>Engadir datos adicionais (opcional)

1. Seleccione **Engadir datos** para **Actividades do cliente**.

1. Seleccione o tipo de actividade semántica que contén os datos que desexa utilizar. Se a actividade non está configurada, seleccione **aquí** e crealo.

1. Baixo **Actividades**, se os atributos da actividade foron mapeados semanticamente cando se creou a actividade, escolla os atributos ou a entidade específicos nos que desexa que se centre o cálculo. Se non se produciu a asignación semántica, seleccione **Editar** e mapea os teus datos.

1. Seleccione **A continuación** e revise os atributos necesarios para este modelo.

1. Seleccione **Gardar**.

1. Seleccionar **Seguinte**

# <a name="business-accounts-b-to-b"></a>[Contas empresariais (B2B)](#tab/b2b)

### <a name="select-prediction-level"></a>Seleccionar nivel de predición

A maioría das predicións créanse a nivel de cliente. Nalgunhas situacións, é posible que non sexa o suficientemente detallado para atender ás necesidades da súa empresa. Use esta función para predecir o abandono dunha sucursal dun cliente, por exemplo, en lugar de para o cliente no seu conxunto.

1. Seleccione **Selecciona unha entidade para un nivel secundario**. Se a opción non está dispoñible, asegúrese de ter completado a sección anterior.

1. Amplíe as entidades das que desexa escoller o nivel secundario ou use a caixa de filtro de busca para filtrar as opcións seleccionadas.

1. Escolla o atributo que desexa usar como nivel secundario e logo seleccione **Engadir**.

1. Seleccione **Seguinte**.

> [!NOTE]
> As entidades dispoñibles nesta sección móstranse porque teñen unha relación coa entidade que escolleu na sección anterior. Se non ve a entidade que quere engadir, asegúrese de que ten unha relación válida en **Relacións**. Só son válidas para esta configuración as relacións de un a un e de moitos a un.

### <a name="add-additional-data-optional"></a>Engadir datos adicionais (opcional)

1. Seleccione **Engadir datos** para **Actividades do cliente**.

1. Seleccione o tipo de actividade semántica que contén os datos que desexa utilizar. Se a actividade non está configurada, seleccione **aquí** e crealo.

1. Baixo **Actividades**, se os atributos da actividade foron mapeados semanticamente cando se creou a actividade, escolla os atributos ou a entidade específicos nos que desexa que se centre o cálculo. Se non se produciu a asignación semántica, seleccione **Editar** e mapea os teus datos.

1. Seleccione **A continuación** e revise os atributos necesarios para este modelo.

1. Seleccione **Gardar**.

1. Seleccionar **Seguinte**

1. Tamén pode seleccionar **Engadir datos** para **Datos dos clientes**.

1. Asigne os atributos semánticos aos campos dos datos dos seus propios clientes segundo se identifican. Os datos dos campos empregados non deben cambiar con frecuencia para garantir o mellor rendemento do modelo. Por exemplo, seleccionar un campo para "Clasificación" que cambiaba cada mes só tería o último valor empregado na predición, aínda que historicamente o mesmo valor pode non aplicarse ao cliente cando constrúe os padróns de predición.

1. Seleccione **Seguinte**.

### <a name="provide-an-optional-list-of-benchmark-accounts"></a>Proporcione unha lista opcional de contas de referencia

Engada unha lista de clientes e contas da súa empresa que queira usar como puntos de referencia. O [detalles para estas contas de referencia](#view-prediction-results) inclúen a súa puntuación de churn e as características máis influentes que afectaron o seu churn predición.

1. Seleccione **+ Engadir clientes**.

1. Escolla os clientes que actúan como punto de referencia.

1. Seleccione **Seguinte**.

---

### <a name="set-update-schedule"></a>Definir programación de actualizacións

1. Para o **Actualizacións de datos** paso, escolla unha frecuencia para volver adestrar o seu modelo. Esta opción de configuración é importante para actualizar a precisión das predicións a medida que se inxiren novos datos en Customer Insights. A maioría das empresas poden volverse formar unha vez ao mes e obter unha boa precisión para a súa predición.

1. Seleccione **Seguinte**.

### <a name="review-and-run-the-model-configuration"></a>Revisar e executar a configuración do modelo

O **Revisa e corre** O paso mostra un resumo da configuración e ofrece a oportunidade de facer cambios antes de crear o predición.

1. Seleccione **Editar** en calquera dos pasos para revisar e facer calquera cambio.

1. Se estás satisfeito coas túas seleccións, selecciona **Garda e executa** para comezar a executar o modelo. Seleccione **Feito**. O **As miñas predicións** aparece a pestana mentres se crea o predición. O proceso pode levar varias horas en función da cantidade de datos empregados na predición.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Ver os resultados de predición

1. Ir a **Intelixencia** > **Predicións**.

1. No **As miñas predicións** pestana, seleccione o predición que quere ver.

# <a name="individual-consumers-b-to-c"></a>[Consumidores individuais (B2C)](#tab/b2c)

Hai tres seccións principais de datos dentro da páxina de resultados:

[!INCLUDE [predict-transaction-results](includes/predict-transaction-results.md)]

# <a name="business-accounts-b-to-b"></a>[Contas empresariais (B2B)](#tab/b2b)

Hai tres seccións principais de datos dentro da páxina de resultados:

[!INCLUDE [predict-transaction-results](includes/predict-transaction-results.md)]

An **Análise de características influentes** a páxina de información contén catro seccións de datos:

- No panel dereito, seleccione un elemento de **Principais clientes** ou **Clientes de referencia**. Ambas listas están ordenadas por valor decrecente da puntuación de abandono, xa sexa a puntuación só para o cliente ou unha puntuación combinada para os clientes e un nivel secundario como a categoría de produto. O elemento seleccionado determina o contido desta páxina.

  - **Os mellores clientes**: lista de 10 clientes con maior risco de abandono e menor risco de abandono segundo as súas puntuacións.
  - **Clientes de referencia**: Lista de ata 10 clientes seleccionados durante a configuración do modelo.

- **Puntuación de abandono:** Mostra a puntuación de abandono para o elemento seleccionado no panel dereito.

- **Distribución do risco de abandono:** Mostra a distribución do risco de abandono entre os clientes e o percentil no que se atopa o cliente seleccionado.

- **As principais características que aumentan e diminúen o risco de abandono:** Lista as cinco principais características que aumentaron e diminuíron o risco de abandono do elemento seleccionado no panel dereito. Mostra o valor da característica para ese elemento e a súa influencia na puntuación de abandono de cada característica influente. Tamén se mostra o valor medio de cada función en segmentos de clientes baixos, medios e altos. Axuda a contextualizar mellor os valores das funcións máis influentes do elemento seleccionado e os compara con segmentos de clientes baixos, medios e altos.

  - Baixo: contas ou combinacións de conta e nivel secundario cunha puntuación de churn entre 0 e 0,33.
  - Medio: contas ou combinacións de contas e niveis secundarios cunha puntuación de churn entre 0,33 e 0,66.
  - Alto: contas ou combinacións de contas e niveis secundarios cunha puntuación de abandono superior a 0,66.

  Cando se predi o abandono a nivel de conta, considéranse todas as contas ao derivar os valores medios das funcións para os segmentos de abandono. Para as predicións de abandono no nivel secundario de cada conta, a derivación de segmentos de abandono depende do nivel secundario do elemento seleccionado no panel lateral. Por exemplo, se un artigo ten un nivel secundario de categoría de produto (material de oficina), só se consideran os artigos que teñen material de oficina como categoría de produto cando se derivan os valores medios das características dos segmentos de abandono. Esta lóxica aplícase para garantir unha comparación xusta dos valores de características do elemento cos valores medios en segmentos baixos, medios e altos.

  Nalgúns casos, o valor medio dos segmentos de abandono baixos, medios ou altos está baleiro ou non está dispoñible porque non hai elementos que pertenzan aos segmentos de abandono correspondentes segundo a definición anterior.

  A interpretación dos valores baixo as columnas media baixa, intermedia e alta é diferente para características categóricas como o país ou a industria. Dado que a noción de valor da característica "medio" non se aplica ás características categóricas, os valores destas columnas son a proporción de clientes en segmentos de abandono baixo, intermedio ou alto que teñen o mesmo valor da característica categórica en comparación co artigo seleccionado no panel lateral.

---

 > [!NOTE]
 > Na entidade de saída para este modelo, *ChurnScore* mostra a probabilidade prevista de churn e *IsChurn* é unha etiqueta binaria baseada en *ChurnScore* cun limiar de 0,5. Se este limiar predeterminado non funciona para o teu escenario, [crear un novo segmento](segments.md#create-a-segment) co seu limiar preferido. Non todos os clientes son necesariamente clientes activos. É posible que algúns deles non tivesen ningunha actividade durante moito tempo e xa se consideran perdidos, segundo a definición de abandono. Non é útil predicir o risco de abandono para os clientes que xa abandonaron porque non son o público de interese.
>
> Para ver a puntuación de churn, vai a **Datos** > **Entidades** e ver a pestana de datos para a entidade de saída que definiu para este modelo.

[!INCLUDE [footer-include](includes/footer-banner.md)]
