---
title: Predicir valor de duración do cliente (VDC)
description: Prediga o potencial de ingresos para os clientes activos no futuro.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-predictions
- ci-create-prediction
- ci-custom-models
- customerInsights
ms.openlocfilehash: f27462ac327027e50e23387ac9f75a671db9a86d
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610372"
---
# <a name="predict-customer-lifetime-value-clv"></a>Predicir valor de duración do cliente (VDC)

Prediga o valor potencial (ingresos) que os clientes activos individuais aportarán á súa empresa a través dun período de tempo futuro definido. Este predición axúdache a:

- Identifica clientes de alto valor e procesa esta información.
- Crea segmentos estratéxicos de clientes en función do seu valor potencial para realizar campañas personalizadas con vendas, mercadotecnia e esforzos de apoio dirixidos.
- Orienta o desenvolvemento de produtos centrándose nas funcións que aumentan o valor do cliente.
- Optimice a estratexia de vendas ou de mercadotecnia e asigne o orzamento de forma máis precisa para a atención ao cliente.
- Recoñece e premia aos clientes de alto valor mediante programas de fidelización ou recompensas.

Determine o que significa CLV para a súa empresa. Admitimos CLV baseado en transaccións predición. O valor previsto dun cliente baséase no historial das transaccións comerciais. Considera crear varios modelos con diferentes preferencias de entrada e compara os resultados do modelo para ver cal é o escenario do modelo que mellor se adapta ás necesidades da túa empresa.

> [!TIP]
> Proba o CLV predición usando datos de mostra: [Valor de vida útil do cliente (CLV) predición guía de exemplo](sample-guide-predict-clv.md).

## <a name="prerequisites"></a>Requisitos previos

- Polo menos [Colaborador](permissions.md) permisos
- Polo menos 100 clientes únicos, preferiblemente máis de 10.000 clientes
- Identificador de cliente, un identificador único para relacionar transaccións cun cliente individual
- Polo menos un ano de historial de transaccións, preferiblemente de dous a tres anos. Idealmente, polo menos dúas ou tres transaccións por ID de cliente, preferiblemente en varias datas. O historial de transaccións debe incluír:
  - **ID de transacción**: identificador único de cada transacción
  - **Data da transacción** : selo de data ou hora de cada transacción
  - **Importe da transacción**: valor monetario (por exemplo, ingresos ou marxe de beneficio) de cada transacción
  - **Etiqueta asignada ás devolucións** : valor booleano verdadeiro/falso que indica se a transacción é un retorno
  - **ID do produto** : ID do produto implicado na transacción
- Datos sobre as actividades do cliente:
  - **Chave primaria** : identificador único dunha actividade
  - **Selo de tempo** : Data e hora do evento identificado pola chave primaria
  - **Evento (nome da actividade)** : Nome do evento que quere usar
  - **Detalles (importe ou valor)**: detalles sobre a actividade do cliente
- Datos adicionais como:
  - Actividades web: historial de visitas ao sitio web ou historial de correo electrónico
  - Actividades de fidelización: acumulación de puntos de recompensa de fidelidade e historial de rescate
  - Servizo de atención ao cliente rexistro: historial de chamadas de servizo, reclamacións ou devolucións
  - Información do perfil do cliente
- Faltan menos do 20 % de valores nos campos obrigatorios

> [!NOTE]
> Só se pode configurar unha entidade do historial de transaccións. Se hai varias entidades de compra ou transacción, combínaas Power Query antes da inxestión de datos.

## <a name="create-a-customer-lifetime-value-prediction"></a>Crear unha predición do valor de duración do cliente

Seleccione **Garda o borrador** en calquera momento para gardar o predición como borrador. O borrador predición móstrase no **As miñas predicións** ficha.

1. Ir a **Intelixencia** > **Predicións**.

1. No **Crear** ficha, seleccione **Usa modelo** no **Valor de vida do cliente** tella.

1. Seleccione **Comezar**.

1. **Poña nome a este modelo** e o **Nome da entidade de saída** para distinguilos doutros modelos ou entidades.

1. Seleccione **Seguinte**.

### <a name="define-model-preferences"></a>Definir preferencias do modelo

1. Estableza un **período de tempo de predición** para definir ata onde desexa predicir o VDC no futuro. Por defecto, a unidade defínese como meses.

   > [!TIP]
   > Para prever con precisión o CLV para o período de tempo establecido, é necesario un período comparable de datos históricos. Por exemplo, se queres prever o CLV para os próximos 12 meses, ten polo menos 18 – 24 meses de datos históricos.

1. Estableza o intervalo temporal no que un cliente debe ter polo menos unha transacción para considerarse activo. O modelo só prevé CLV para **Clientes activos**.
   - **Permitir que o modelo calcule o intervalo de compra (recomendado)** : o modelo analiza os teus datos e determina un período de tempo en función das compras históricas.
   - **Establecer o intervalo manualmente** : Período de tempo para a súa definición de cliente activo.

1. Define o percentil de **Cliente de alto valor**.
    - **Cálculo do modelo (recomendado)** : O modelo usa a regra 80/20. A porcentaxe de clientes que contribuíu ao 80 % de ingresos acumulados da súa empresa no período histórico considéranse clientes de alto valor. Normalmente, menos do 30-40 % dos clientes contribúen ao 80 % dos ingresos acumulados. Non obstante, este número pode variar dependendo da súa empresa e industria.
    - **Porcentaxe dos principais clientes activos** : Percentil específico para un cliente de alto valor. Por exemplo, introduza **25** definir os clientes de alto valor como o 25% dos futuros clientes que pagan.

    Se a súa empresa define clientes de alto valor dun xeito diferente, [avísenos, xa que nos encantaría escoitalo](https://go.microsoft.com/fwlink/?linkid=2074172).

1. Seleccione **Seguinte**.

### <a name="add-required-data"></a>Engadir datos obrigatorios

1. Seleccione **Engadir datos** para **Historial de transaccións do cliente**.

1. Seleccione o tipo de actividade semántica, **Pedido de venda** ou **Liña de pedidos de vendas**, que contén o historial de transaccións. Se a actividade non está configurada, seleccione **aquí** e crealo.

1. Baixo **Actividades**, se os atributos da actividade foron mapeados semanticamente cando se creou a actividade, escolla os atributos ou a entidade específicos nos que desexa que se centre o cálculo. Se non se produciu a asignación semántica, seleccione **Editar** e mapea os teus datos.
  
   :::image type="content" source="media/CLV-add-required.PNG" alt-text="Engadir os datos necesarios para o modelo CLV":::

1. Seleccione **A continuación** e revise os atributos necesarios para este modelo.

1. Seleccione **Gardar**.

1. Engade máis actividades ou selecciona **A continuación**.

### <a name="add-optional-activity-data"></a>Engade datos de actividade opcionais

Os datos que reflicten as interaccións clave dos clientes (como rexistros de webs, servizos de atención ao cliente e eventos) engaden contexto aos rexistros de transaccións. Se se atopan máis padróns nos datos de actividade dos seus clientes pode mellorar a precisión das predicións.

1. Seleccione **Engadir datos** baixo **Mellora a información do modelo con datos de actividade adicionais**.

1. Seleccione un tipo de actividade que coincida co tipo de actividade do cliente que está engadindo. Se a actividade non está configurada, seleccione **aquí** e crealo.

1. Baixo **Actividades**, se os atributos da actividade foron mapeados cando se creou a actividade, escolla os atributos ou a entidade específicos nos que desexa que se centre o cálculo. Se non se produciu o mapeo, seleccione **Editar** e mapea os teus datos.

1. Seleccione **A continuación** e revise os atributos necesarios para este modelo.

1. Seleccione **Gardar**.

1. Seleccione **Seguinte**.

1. [Engade datos opcionais do cliente](#add-optional-customer-data) ou seleccione **A continuación** e vai a [Establece o calendario de actualizacións](#set-update-schedule).

### <a name="add-optional-customer-data"></a>Engade datos opcionais do cliente

Seleccione entre 18 atributos de perfil de cliente de uso habitual para incluír como entrada ao modelo. Estes atributos poden dar lugar a resultados de modelos máis personalizados, relevantes e accionables para os teus casos de uso empresarial.

Por exemplo: Contoso Coffee quere predecir o valor de vida do cliente para orientarse a clientes de alto valor cunha oferta personalizada relacionada co lanzamento da súa nova máquina de café expreso. Contoso usa o modelo CLV e engade os 18 atributos do perfil do cliente para ver que factores inflúen nos seus clientes de maior valor. Consideran que a localización do cliente é o factor máis influente para estes clientes.
Con esta información, organizan un evento local para o lanzamento da máquina de espresso e colaboran con vendedores locais para ofrecer ofertas personalizadas e unha experiencia especial no evento. Sen esta información, Contoso só podería enviar correos electrónicos de mercadotecnia xenérico e perder a oportunidade de personalizar este segmento local dos seus clientes de alto valor.

1. Seleccione **Engadir datos** baixo **Aumente aínda máis a información do modelo con datos adicionais de clientes**.

1. Para **Entidade**, escolle **Cliente: CustomerInsights** para seleccionar o perfil de cliente unificado que se asigna aos datos de atributos do cliente. Para **ID de cliente**, escolle **Sistema.Customer.CustomerId**.

1. Asigne máis campos se os datos están dispoñibles nos seus perfís de clientes unificados.

   :::image type="content" source="media/clv-optional-customer-profile-mapping.png" alt-text="Exemplo de campos mapeados para os datos do perfil do cliente.":::

1. Seleccione **Gardar**.

1. Seleccione **Seguinte**.

### <a name="set-update-schedule"></a>Definir programación de actualizacións

1. Escolle a frecuencia para volver adestrar o teu modelo en función dos datos máis recentes. Esta opción de configuración é importante para actualizar a precisión das predicións a medida que se inxiren novos datos en Customer Insights. A maioría das empresas poden volverse formar unha vez ao mes e obter unha boa precisión para a súa predición.

1. Seleccione **Seguinte**.

### <a name="review-and-run-the-model-configuration"></a>Revisar e executar a configuración do modelo

O **Revisa e corre** O paso mostra un resumo da configuración e ofrece a oportunidade de facer cambios antes de crear o predición.

1. Seleccione **Editar** en calquera dos pasos para revisar e facer calquera cambio.

1. Se estás satisfeito coas túas seleccións, selecciona **Garda e executa** para comezar a executar o modelo. Seleccione **Feito**. O **As miñas predicións** aparece a pestana mentres se crea o predición. O proceso pode levar varias horas en función da cantidade de datos empregados na predición.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Ver os resultados de predición

1. Ir a **Intelixencia** > **Predicións**.

1. No **As miñas predicións** pestana, seleccione o predición que quere ver.

Hai tres seccións principais de datos dentro da páxina de resultados.

- **Rendemento do modelo de adestramento** : As notas A, B ou C indican o rendemento do predición e poden axudarche a tomar a decisión de usar os resultados almacenados na entidade de saída.
  
  :::image type="content" source="media/clv-model-score.png" alt-text="Imaxe da caixa de información da puntuación do modelo coa cualificación A.":::

  Customer Insights avalía o rendemento do modelo de IA á hora de predicir os clientes de alto valor en comparación cun modelo de referencia.

  As cualificacións determínanse en función das seguintes regras:
  - **A**: cando o modelo predixo con precisión polo menos un 5 % máis de clientes de alto valor en comparación co modelo de referencia.
  - **B**: cando o modelo predixo con precisión entre un 0-5 % máis de clientes de alto valor en comparación co modelo de referencia.
  - **C**: cando o modelo predixo con precisión menos clientes de alto valor en comparación co modelo de referencia.
  
  Seleccione [**Máis información sobre esta puntuación**](#learn-about-the-score) para abrir o **Valoración do modelo** panel que mostra máis detalles sobre o rendemento do modelo de IA e o modelo de referencia. Axudarache a comprender mellor as métricas de rendemento do modelo subxacente e como se obtivo a nota final de rendemento do modelo. O modelo de base utiliza un enfoque non baseado na IA para calcular o valor da duración do cliente baseado principalmente nas compras históricas realizadas polos clientes.

- **Valor dos clientes por percentil** : Os clientes de baixo e alto valor móstranse nun gráfico. Pasa o rato sobre as barras do histograma para ver o número de clientes de cada grupo e o CLV medio dese grupo. Opcionalmente, [crear segmentos de clientes](prediction-based-segment.md) baseándose nas súas predicións CLV.
  
   :::image type="content" source="media/CLV-value-percent.png" alt-text="Valor dos clientes por percentil para o modelo CLV":::

- **Factores máis influentes**: Considéranse varios factores ao crear a súa predición do VDC en función dos datos de entrada proporcionados ao modelo IA. Cada un dos factores ten calculada a súa importancia para as predicións agregadas que crea un modelo. Use estes factores para axudar a validar os seus resultados predición. Estes factores tamén ofrecen máis información sobre os factores máis influentes que contribuíron á predición do VDC en todos os seus clientes.
  
   :::image type="content" source="media/CLV-influence-factors.png" alt-text="Factores máis influentes para o modelo CLV":::

### <a name="learn-about-the-score"></a>Coñece a puntuación

A fórmula estándar empregada para calcular o VDC polo modelo de base:

 _**CLV para cada cliente** = Media de compra mensual realizada polo cliente na xanela activa do cliente * Número de meses no período CLV predición * Taxa de retención global de todos os clientes_

O modelo IA compárase co modelo de base baseado en dúas métricas de rendemento do modelo.
  
- **Taxa de éxito ao predicir os clientes valiosos**

  Vexa a diferenza na predición de clientes de alto valor mediante o modelo IA en comparación co modelo de base. Por exemplo, unha da taxa de éxito do 84 % significa que de todos os clientes de alto valor dos datos de adestramento, o modelo IA foi capaz de captar con precisión o 84 %. Despois comparamos esta taxa de éxito coa taxa de éxito do modelo de base para informar do cambio relativo. Este valor úsase para asignar unha cualificación ao modelo.

- **Métricas de erro**

  Consulta o rendemento global do modelo en termos de erro ao prever valores futuros. Usamos a métrica global de erro do valor cuadrático medio (RMSE) para avaliar este erro. O RMSE é un xeito estándar de medir o erro dun modelo na predición de datos cuantitativos. O RMSE do modelo AI compárase co RMSE do modelo de base e infórmase da diferenza relativa.

O modelo IA prioriza a clasificación precisa dos clientes segundo o valor que aportan ao seu negocio. Polo tanto, só se usa a taxa de éxito de predición de clientes de alto valor para obter a nota do modelo final. A métrica do RMSE é sensible aos valores atípicos. Nos escenarios nos que teña unha pequena porcentaxe de clientes con valores de compra extraordinariamente altos, a métrica do RMSE xeral pode non dar a imaxe completa do rendemento do modelo.

[!INCLUDE [footer-include](includes/footer-banner.md)]
