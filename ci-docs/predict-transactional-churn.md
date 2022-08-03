---
title: Churn de transaccións predición (contén vídeo)
description: Prediga se un cliente está en risco de deixar de comprar os seus servizos ou produtos.
ms.date: 01/13/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: b8216b5a739964fdfff8cad7e6d6d7ce3f5308b5
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 07/18/2022
ms.locfileid: "9171093"
---
# <a name="transaction-churn-prediction"></a>Predición do abandono de transaccións

A predición do abandono transaccional axuda a predicir se un cliente deixará de mercar os seus produtos ou servizos nunha xanela de tempo determinada. Pode crear novas predicións de abandono en **Intelixencia** > **Predicións**. Seleccione **As miñas predicións** para ver outras predicións que creou. 

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6Eg]

Para contornos baseados en contas empresariais, podemos predicir o cambio transaccional dunha conta e tamén unha combinación de conta e outro nivel de información como a categoría de produto. Engadir unha dimensión pode axudar a descubrir a probabilidade de que a conta "Contoso" deixe de mercar a categoría de produtos "papelería de oficina". Ademais, para as contas empresariais, tamén podemos empregar a IA para xerar unha lista de posibles motivos polos que é probable que unha conta cambie unha categoría de información de nivel secundario.

> [!TIP]
> Proba o tutorial para unha transacción churn predición usando datos de mostra: [Guía de exemplo de abandono de transaccións predición](sample-guide-predict-transactional-churn.md).

## <a name="prerequisites"></a>Requisitos previos

# <a name="individual-consumers-b-to-c"></a>[Consumidores individuais (B2C)](#tab/b2c)

- Polo menos [Permisos de colaborador](permissions.md) en Customer Insights.
- Coñecemento empresarial para comprender o que significa a renovación para a súa empresa. Admitimos as definicións de abandono baseadas no tempo, o que significa que se considera que un cliente abandonou despois dun período sen compras.
- Datos sobre as súas transaccións/compras e o seu historial:
    - Identificadores de transaccións para distinguir compras/transaccións.
    - Identificadores de clientes para facer coincidir as transaccións cos seus clientes.
    - Datas de eventos de transacción, que definen as datas en que se produciu a transacción.
    - O esquema de datos semánticos para compras/transaccións require a seguinte información:
        - **ID de transacción:** Un identificador único dunha compra ou transacción.
        - **Data da transacción:** A data da compra ou transacción.
        - **Valor da transacción**: O importe da moeda/valor numérico da transacción/elemento.
        - (Opcional) **ID de produto único**: O ID do produto ou servizo adquirido se os seus datos están a un nivel de elemento de liña.
        - (Opcional) **Se esta transacción foi unha devolución**: Un campo verdadeiro/falso que identifica se a transacción foi ou non unha devolución. Se o **Valor da transacción** é negativo, tamén usaremos esta información para inferir un retorno.
- (Opcional) Datos sobre actividades do cliente:
    - Identificadores de actividades para distinguir actividades do mesmo tipo.
    - Identificadores de clientes para atribuír actividades aos seus clientes.
    - Información da actividade que contén o nome e a data da actividade.
    - O esquema de datos semánticos para as actividades do cliente inclúe:
        - **Clave principal:** un identificador único para unha actividade. Por exemplo, unha visita ao sitio web ou un rexistro de uso que mostra que o cliente probou unha mostra do seu produto.
        - **Marca de tempo:** a data e a hora do evento identificadas pola clave principal.
        - **Evento:** o nome do evento que desexa usar. Por exemplo, un campo chamado "UserAction" nunha tenda de ultramarinos pode ser un cupón utilizado polo cliente.
        - **Detalles:** información detallada sobre o evento. Por exemplo, un campo chamado "CouponValue" nunha tenda de alimentación pode ser o valor en moeda do cupón.

# <a name="business-accounts-b-to-b"></a>[Contas empresariais (B2B)](#tab/b2b)

- Polo menos [Permisos de colaborador](permissions.md) en Customer Insights.
- Coñecemento empresarial para comprender o que significa a renovación para a súa empresa. Admitimos as definicións de abandono baseadas no tempo, o que significa que se considera que un cliente abandonou despois dun período sen compras.
- Datos sobre as súas transaccións/compras e o seu historial:
    - Identificadores de transaccións para distinguir compras/transaccións.
    - Identificadores de clientes para facer coincidir as transaccións cos seus clientes.
    - Datas de eventos de transacción, que definen as datas en que se produciu a transacción.
    - O esquema de datos semánticos para compras/transaccións require a seguinte información:
        - **ID de transacción:** Un identificador único dunha compra ou transacción.
        - **Data da transacción:** A data da compra ou transacción.
        - **Valor da transacción**: O importe da moeda/valor numérico da transacción/elemento.
        - (Opcional) **ID de produto único**: O ID do produto ou servizo adquirido se os seus datos están a un nivel de elemento de liña.
        - (Opcional) **Se esta transacción foi unha devolución**: Un campo verdadeiro/falso que identifica se a transacción foi ou non unha devolución. Se o **Valor da transacción** é negativo, tamén usaremos esta información para inferir un retorno.
- (Opcional) Datos sobre actividades do cliente:
    - Identificadores de actividades para distinguir actividades do mesmo tipo.
    - Identificadores de clientes para atribuír actividades aos seus clientes.
    - Información da actividade que contén o nome e a data da actividade.
    - O esquema de datos semánticos para as actividades do cliente inclúe:
        - **Clave principal:** un identificador único para unha actividade. Por exemplo, unha visita ao sitio web ou un rexistro de uso que mostra que o cliente probou unha mostra do seu produto.
        - **Marca de tempo:** a data e a hora do evento identificadas pola clave principal.
        - **Evento:** o nome do evento que desexa usar. Por exemplo, un campo chamado "UserAction" nunha tenda de ultramarinos pode ser un cupón utilizado polo cliente.
        - **Detalles:** información detallada sobre o evento. Por exemplo, un campo chamado "CouponValue" nunha tenda de alimentación pode ser o valor en moeda do cupón.
- (Opcional) Datos sobre os seus clientes:
    - Estes datos deben aliñarse cara a atributos máis estáticos para garantir que o modelo funcione mellor.
    - O esquema de datos semánticos para os datos do cliente inclúe:
        - **CustomerID:** Un identificador único para un cliente.
        - **Data de creación:** A data en que se engadiu inicialmente o cliente.
        - **Estado ou provincia:** a situación do estado ou provincia dun cliente.
        - **País:** o país dun cliente.
        - **Sector:** O tipo de sector dun cliente. Por exemplo, un campo chamado "Sector" nun torrador de café pode indicar se o cliente vendía polo miúdo.
        - **Clasificación:** a clasificación dun cliente para o seu negocio. Por exemplo, un campo chamado "ValueSegment" nun torrador de café pode ser o nivel do cliente en función do tamaño do cliente.

---

- Características datos suxeridas:
    - Datos históricos suficientes: datos de transaccións durante polo menos o dobre da xanela de tempo seleccionada. Preferiblemente, de dous a tres anos do historial de transaccións. 
    - Compras múltiples por cliente: idealmente polo menos dúas transaccións por cliente.
    - Número de clientes: polo menos 10 perfís clientes, preferentemente máis de 1.000 clientes únicos. O modelo fallará con menos de 10 clientes e con datos históricos insuficientes.
    - Integridade dos datos: menos do 20 % dos valores que faltan no campo de datos da entidade proporcionada.

> [!NOTE]
> Para unha empresa con alta frecuencia de compra de clientes (cada poucas semanas), recoméndase seleccionar unha ventá predición máis curta e definir o abandono. Para unha frecuencia de compra baixa (cada poucos meses ou unha vez ao ano), elixa unha fiestra máis longa de predición e defina o abandono.

## <a name="create-a-transaction-churn-prediction"></a>Crear unha predición do abandono da transacción

1. En Customer Insights, diríxase a **Intelixencia** > **Predicións**.

1. Seleccione o **Modelo de abandono de clientes** mosaico e selecciona **Use este modelo**.

1. No panel **Modelo de abandono de clientes**, escolla **Transacción** e seleccione **Comezar**.

:::image type="content" source="media/select-transaction-churn.PNG" alt-text="Captura de pantalla coa opción de transacción seleccionada no panel do modelo de abandono de clientes.":::
 
### <a name="name-model"></a>Dar nome ao modelo

1. Proporcione un nome para o modelo para distinguilo doutros modelos.

1. Proporcione un nome para a entidade de saída usando só letras e números, sen espazos. Ese é o nome que empregará a entidade do modelo. 

1. Seleccione **Seguinte**.

### <a name="define-customer-churn"></a>Definir renovación do cliente

1. Establece o **predición xanela**. Por exemplo, predicir o risco de abandono dos seus clientes durante os próximos 90 días para alinearse cos seus esforzos de retención de mercadotecnia. A predición do risco de abandono por un período de tempo máis longo ou máis curto pode facer máis difícil abordar os factores do seu perfil de risco de abandono, pero depende das necesidades específicas do seu negocio.
   >[!TIP]
   > Podes seleccionar **Garda o borrador** en calquera momento para gardar o predición como borrador. Atopará o borrador de predición no separador **As miñas previsións** para continuar.

1. Introduza o número de días para definir o abandono **Definición de churn** campo. Por exemplo, se un cliente non realizou compras nos últimos 30 días, é posible que a súa empresa considere que abandonou. 

1. Seleccione **Seguinte** para continuar.

### <a name="add-required-data"></a>Engadir datos obrigatorios

1. Seleccione **Engadir datos** e escolla o tipo de actividade no panel lateral que contén a información de transacción ou historial de compras requirida.

1. Baixo **Selecciona actividades**, escolla as actividades específicas do tipo de actividade seleccionado no que desexa que se centre o cálculo.

   :::image type="content" source="media/transaction-churn-select-activity.PNG" alt-text="Panel lateral que mostra a elección de actividades específicas baixo o tipo semántico.":::

   Se aínda non asignou a actividade a un tipo semántico, seleccione **Editar** facelo. Ábrese a experiencia guiada para asignar actividades semánticas. Asigne os seus datos aos campos correspondentes do tipo de actividade seleccionada.

1. Asigne os atributos semánticos aos campos necesarios para executar o modelo. Se os campos de abaixo non se enchen, configure a relación da súa entidade do historial de compras á entidade *Cliente*. Seleccione **Gardar**.

1. No **Engade os datos necesarios** paso, seleccione **A continuación** para continuar se non queres engadir máis actividades.


# <a name="individual-consumers-b-to-c"></a>[Consumidores individuais (B2C)](#tab/b2c)

### <a name="add-additional-data-optional"></a>Engadir datos adicionais (opcional)

Configure a relación da entidade de actividade do cliente coa entidade *Cliente*.

1. Seleccione o campo que identifica ao cliente na entidade de actividade do cliente. Pode estar directamente relacionada co ID de cliente principal da súa entidade *Cliente*.

1. Seleccione a entidade que sexa a súa entidade principal de *Cliente*.

1. Escriba un nome que describa a relación.

#### <a name="customer-activities"></a>Actividades do cliente

1. Opcionalmente, seleccione **Engadir datos** para **Actividades do cliente**.

1. Seleccione o tipo de actividade semántica que contén os datos que desexa usar e, a continuación, seleccione unha ou máis actividades na sección **Actividades**.

1. Seleccione un tipo de actividade que coincida co tipo de actividade do cliente que está configurando. Seleccione **Crear novo** e elixa un tipo de actividade dispoñible ou cree un novo tipo.

1. Seleccione **Seguinte** e, a continuación, **Gardar**.

1. Se ten algunha outra actividade do cliente que desexa incluír, repita os pasos anteriores.

# <a name="business-accounts-b-to-b"></a>[Contas empresariais (B2B)](#tab/b2b)

### <a name="select-prediction-level"></a>Seleccionar nivel de predición

A maioría das predicións créanse a nivel de cliente. Nalgunhas situacións, é posible que non sexa o suficientemente detallado para atender ás necesidades da súa empresa. Pode usar esta función para predicir o abandono dunha sucursal dun cliente, por exemplo, en lugar de para o cliente no seu conxunto.

1. Para crear unha predición a un nivel máis detallado que o cliente, seleccione **Seleccionar a entidade para un nivel secundario**. Se a opción non está dispoñible, asegúrese de ter completado a sección anterior.

1. Amplíe as entidades das que desexa escoller o nivel secundario ou use a caixa de filtro de busca para filtrar as opcións seleccionadas.

1. Escolla o atributo que desexa usar como nivel secundario e logo seleccione **Engadir**.

1. Seleccione **Seguinte**.

> [!NOTE]
> As entidades dispoñibles nesta sección móstranse porque teñen unha relación coa entidade que escolleu na sección anterior. Se non ve a entidade que quere engadir, asegúrese de que ten unha relación válida en **Relacións**. Só son válidas para esta configuración as relacións de un a un e de moitos a un.

### <a name="add-additional-data-optional"></a>Engadir datos adicionais (opcional)

Configure a relación da entidade de actividade do cliente coa entidade *Cliente*.

1. Seleccione o campo que identifica ao cliente na entidade de actividade do cliente. Pode estar directamente relacionada co ID de cliente principal da súa entidade *Cliente*.

1. Seleccione a entidade que sexa a súa entidade principal de *Cliente*.

1. Escriba un nome que describa a relación.

#### <a name="customer-activities"></a>Actividades do cliente

1. Opcionalmente, seleccione **Engadir datos** para **Actividades do cliente**.

1. Seleccione o tipo de actividade semántica que contén os datos que desexa usar e, a continuación, seleccione unha ou máis actividades na sección **Actividades**.

1. Seleccione un tipo de actividade que coincida co tipo de actividade do cliente que está configurando. Seleccione **Crear novo** e elixa un tipo de actividade dispoñible ou cree un novo tipo.

1. Seleccione **Seguinte** e, a continuación, **Gardar**.

1. Se ten algunha outra actividade do cliente que desexa incluír, repita os pasos anteriores.

#### <a name="customers-data"></a>Datos dos clientes

1. Tamén pode seleccionar **Engadir datos** para **Datos dos clientes**.

1. Asigne os atributos semánticos aos campos dos datos dos seus propios clientes segundo se identifican. Os datos dos campos empregados non deben cambiar con frecuencia para garantir o mellor rendemento do modelo. Por exemplo, seleccionar un campo para "Clasificación" que cambiaba cada mes só tería o último valor empregado na predición, aínda que historicamente o mesmo valor pode non aplicarse ao cliente cando constrúe os padróns de predición.

1. Seleccione **Seguinte**.

### <a name="provide-an-optional-list-of-benchmark-accounts"></a>Proporcione unha lista opcional de contas de referencia

Engada unha lista de clientes e contas da súa empresa que queira usar como puntos de referencia. Obterá [detalles destas contas de referencia](#review-a-prediction-status-and-results) incluíndo a súa puntuación de abandono e as características máis importantes que afectaron á súa predición de abandonos.

1. Seleccione **+ Engadir clientes**.

1. Escolla os clientes que actúan como punto de referencia.

1. Seleccione **Seguinte** para continuar.

---

### <a name="set-schedule-and-review-configuration"></a>Establecer a programación e revisar a configuración

1. Estableza unha frecuencia para volver formar o modelo. Esta configuración é importante para actualizar a precisión das predicións a medida que se inxiren novos datos. A maioría das empresas poden volverse formar unha vez ao mes e obter unha boa precisión para a súa predición.

1. Seleccione **Seguinte**.

1. Revise a configuración da predición. Pode volver aos pasos anteriores seleccionando **Editar** no valor mostrado. Tamén pode seleccionar un paso de configuración no indicador de progreso.

1. Se todos os valores están configurados correctamente, seleccione **Gardar e executar** para comezar o proceso de predición. No separador **As miñas predicións**, pode ver o estado das súas predicións. O proceso pode levar varias horas en función da cantidade de datos empregados na predición.

## <a name="review-a-prediction-status-and-results"></a>Revise o estado da predición e os resultados

1. Vaia a **Intelixencia** > **Predicións** e seleccione o separador **As miñas predicións**.

1. Seleccione a predición que desexa revisar.
   - **Nome da predición**: Nome da predición proporcionado ao creala.
   - **Tipo de predición**: Tipo de modelo usado para a predición
   - **Entidade de saída**: nome da entidade para almacenar os resultados da predición. Pode atopar unha entidade con este nome en **Datos** > **Entidades**.
     Na entidade de saída, *ChurnScore* é a probabilidade prevista de abandono e *IsChurn* é unha etiqueta binaria baseada en *ChurnScore* cun limiar de 0,5. É posible que o limiar predeterminado non funcione no seu escenario. [Cree un novo segmento](segments.md#create-a-segment) co seu limiar preferido.
     Non todos os clientes son necesariamente clientes activos. É posible que algúns deles non tivesen ningunha actividade durante moito tempo e xa se consideran perdidos, segundo a definición de abandono. Non é útil predicir o risco de abandono para os clientes que xa abandonaron porque non son o público de interese.
   - **Campo previsto**: Este campo só se completa con algúns tipos de predicións e non se usa na predición do abandono.
   - **Estado**: Estado da execución da predición.
        - **En cola**: a predición está á espera de que se executen outros procesos.
        - **Actualizando**: a predición está executándose actualmente para producir resultados que fluirán cara á entidade de saída.
        - **Fallou**: Fallou a execución da predición. Para obter máis detalles, [revise os rexistros](manage-predictions.md#troubleshoot-a-failed-prediction).
        - **Con éxito**: a predición tivo éxito. Seleccione **Ver** nos tres puntos verticais para revisar a predición
   - **Editado**: a data na que se modificou a configuración da predición.
   - **Última actualización**: a data na que a predición actualizou os resultados na entidade de saída.

1. Seleccione os tres puntos verticais xunto á predición da que desexa revisar os resultados e seleccione **Ver**.

   :::image type="content" source="media/model-subs-view.PNG" alt-text="Control de visualización para ver os resultados dunha predición.":::

# <a name="individual-consumers-b-to-c"></a>[Consumidores individuais (B2C)](#tab/b2c)

1. Hai tres seccións principais de datos dentro da páxina de resultados:
   - **Desempeño do modelo de formación**: A, B ou C son posibles puntuacións. Esta puntuación indica o rendemento da predición e pode axudalo a tomar a decisión de usar os resultados almacenados na entidade de saída. As puntuacións determínanse segundo as regras seguintes: 
        - **A** cando o modelo predixo con precisión polo menos o 50 % das predicións totais e cando a porcentaxe de predicións precisas para os clientes que abandonaron é superior á taxa de referencia nun 10 % como mínimo.
            
        - **B** cando o modelo predixo con precisión polo menos o 50 % das predicións totais e cando a porcentaxe de predicións precisas para os clientes que abandonaron é ata un 10 % superior á referencia.
            
        - **C** cando o modelo predixo con precisión menos do 50 % das predicións totais ou cando a porcentaxe de predicións precisas para os clientes que abandonaron é inferior á referencia.
               
        - A **referencia** toma a entrada da fiestra de tempo da predición para o modelo (por exemplo, un ano) e o modelo crea diferentes fraccións de tempo dividíndoo entre 2 ata alcanzar un mes ou menos. Utiliza estas fraccións para crear unha regra de negocio para clientes que non compraron neste período de tempo. Considérase que estes clientes abandonaron. Elíxese como modelo de referencia a regra de negocio baseada no tempo con maior capacidade para predicir quen é susceptible de abandonar.
            
    - **Probabilidade de renovación (número de clientes)**: grupos de clientes en función do risco previsto de renovación. Estes datos poden axudalo máis tarde se quere crear un segmento de clientes con alto risco de renovación. Estes segmentos axudan a comprender onde debe estar o seu corte para a subscrición a segmentos.
       
    - **Factores máis influentes**: hai moitos factores que se teñen en conta á hora de crear a súa predición. Cada un dos factores ten a súa importancia calculada para as predicións agregadas que crea un modelo. Pode usar estes factores para axudar a validar os seus resultados de predicións ou pode usar esta información máis tarde para [crear segmentos](segments.md) que poderían axudar a influír no risco de abandono dos clientes.


# <a name="business-accounts-b-to-b"></a>[Contas empresariais (B2B)](#tab/b2b)

1. Hai tres seccións principais de datos dentro da páxina de resultados:
   - **Desempeño do modelo de formación**: A, B ou C son posibles puntuacións. Esta puntuación indica o rendemento da predición e pode axudalo a tomar a decisión de usar os resultados almacenados na entidade de saída. As puntuacións determínanse segundo as regras seguintes: 
        - **A** cando o modelo predixo con precisión polo menos o 50 % das predicións totais e cando a porcentaxe de predicións precisas para os clientes que abandonaron é superior á taxa de referencia nun 10 % como mínimo.
            
        - **B** cando o modelo predixo con precisión polo menos o 50 % das predicións totais e cando a porcentaxe de predicións precisas para os clientes que abandonaron é ata un 10 % superior á referencia.
            
        - **C** cando o modelo predixo con precisión menos do 50 % das predicións totais ou cando a porcentaxe de predicións precisas para os clientes que abandonaron é inferior á referencia.
               
        - A **referencia** toma a entrada da fiestra de tempo da predición para o modelo (por exemplo, un ano) e o modelo crea diferentes fraccións de tempo dividíndoo entre 2 ata alcanzar un mes ou menos. Utiliza estas fraccións para crear unha regra de negocio para clientes que non compraron neste período de tempo. Considérase que estes clientes abandonaron. Elíxese como modelo de referencia a regra de negocio baseada no tempo con maior capacidade para predicir quen é susceptible de abandonar.
            
    - **Probabilidade de renovación (número de clientes)**: grupos de clientes en función do risco previsto de renovación. Estes datos poden axudalo máis tarde se quere crear un segmento de clientes con alto risco de renovación. Estes segmentos axudan a comprender onde debe estar o seu corte para a subscrición a segmentos.
       
    - **Factores máis influentes**: hai moitos factores que se teñen en conta á hora de crear a súa predición. Cada un dos factores ten a súa importancia calculada para as predicións agregadas que crea un modelo. Pode usar estes factores para axudar a validar os seus resultados de predicións ou pode usar esta información máis tarde para [crear segmentos](segments.md) que poderían axudar a influír no risco de abandono dos clientes.


1. Para as contas de empresas, atopará unha páxina de información de **Análise de funcións importantes**. Contén catro seccións de datos:

    - O elemento seleccionado no panel dereito determina o contido desta páxina. Seleccione un elemento desde **Os mellores clientes** ou **Clientes de referencia**. Ambas listas están ordenadas por valor decrecente da puntuación de abandono, xa sexa a puntuación só para o cliente ou unha puntuación combinada para os clientes e un nivel secundario como a categoría de produto.
        
        - **Os mellores clientes**: lista de 10 clientes con maior risco de abandono e menor risco de abandono segundo as súas puntuacións. 
        - **Clientes de referencia**: Lista de ata 10 clientes seleccionados durante a configuración do modelo.
 
    - **Puntuación de abandono:** Mostra a puntuación de abandono para o elemento seleccionado no panel dereito.
    
    - **Distribución do risco de abandono:** Mostra a distribución do risco de abandono entre os clientes e a porcentaxe na que se atopa o cliente seleccionado. 
    
    - **Principais características que aumentan e diminúen o risco de abandono:** Para o elemento seleccionado no panel dereito, aparecen as cinco características principais que aumentaron e diminuíron o risco de abandono. Para cada función influínte, atopará o valor da función para ese elemento e a súa influencia na puntuación de abandono. Tamén se mostra o valor medio de cada función en segmentos de clientes baixos, medios e altos. Axuda a contextualizar mellor os valores das funcións máis influentes do elemento seleccionado e os compara con segmentos de clientes baixos, medios e altos.

       - Baixo: contas ou combinacións de contas e nivel secundario cunha puntuación de abandono entre 0 e 0,33
       - Medio: contas ou combinacións de contas e niveis secundarios cunha puntuación de abandono entre 0,33 e 0,66
       - Alto: contas ou combinacións de contas e niveis secundarios cunha puntuación de abandono superior a 0,66
    
       Cando se predi o abandono a nivel de conta, considéranse todas as contas ao derivar os valores medios das funcións para os segmentos de abandono. Para as predicións de abandono no nivel secundario de cada conta, a derivación de segmentos de abandono depende do nivel secundario do elemento seleccionado no panel lateral. Por exemplo, se un elemento ten un nivel secundario de categoría de produto = material de oficina, entón só se consideran os artigos que teñan material de oficina como categoría de produto cando se derivan os valores medios de característica para os segmentos de abandono. Esta lóxica aplícase para garantir unha comparación xusta dos valores de características do elemento cos valores medios en segmentos baixos, medios e altos.

       Nalgúns casos, o valor medio dos segmentos de abandono baixos, medios ou altos está baleiro ou non está dispoñible porque non hai elementos que pertenzan aos segmentos de abandono correspondentes segundo a definición anterior.
       
       > [!NOTE]
       > A interpretación dos valores baixo as columnas media baixa, intermedia e alta é diferente para características categóricas como o país ou a industria. Dado que a noción de valor da característica "medio" non se aplica ás características categóricas, os valores destas columnas son a proporción de clientes en segmentos de abandono baixo, intermedio ou alto que teñen o mesmo valor da característica categórica en comparación co artigo seleccionado no panel lateral.

---

## <a name="manage-predictions"></a>Xestionar predicións

É posible optimizar, solucionar problemas, actualizar ou eliminar predicións. Revise un informe de usabilidade dos datos de entrada para saber como facer unha predición máis rápido e máis fiable. Para obter máis información, vaia a [Xestionar predicións](manage-predictions.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
