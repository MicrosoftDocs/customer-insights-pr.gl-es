---
title: Prever o abandono da subscrición (contén vídeo)
description: Fai a predición de se un cliente está en risco por deixar de usar os produtos ou servizos da subscrición da súa empresa.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 7464707864c418bfcc625ddfd245622131434b33
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610234"
---
# <a name="predict-subscription-churn"></a>Prever a renovación de subscricións

Fai a predición de se un cliente está en risco por deixar de usar os produtos ou servizos da subscrición da súa empresa. Os datos de subscrición inclúen subscricións activas e inactivas para cada cliente, polo que hai varias entradas por ID de cliente.

Debes ter coñecementos comerciais para entender o que significa churn para a túa empresa. Admitimos definicións de abandono baseadas no tempo, o que significa que considérase que un cliente produciu un período de tempo despois de que finalice a súa subscrición.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWOKNQ]

> [!TIP]
> Proba o churn de subscrición predición usando datos de mostra: [Guía de exemplo de eliminación de subscricións predición](sample-guide-predict-subscription-churn.md).

## <a name="prerequisites"></a>Requisitos previos

- Polo menos [Permisos de colaborador](permissions.md).
- Polo menos 10 perfís de clientes, preferiblemente máis de 1.000 clientes únicos.
- Identificador de cliente, un identificador único para facer coincidir as subscricións cos teus clientes.
- Datos de subscrición para polo menos o dobre da xanela de tempo seleccionada. Preferiblemente, de dous a tres anos de datos de subscrición. O historial de subscrición debe incluír:
  - **ID da subscrición:** Identificador único dunha subscrición.
  - **Data de finalización da subscrición:** Data de caducidade da subscrición para o cliente.
  - **Data de inicio da subscrición:** Data de inicio da subscrición para o cliente.
  - **Data da transacción:** Data de cambio de subscrición. Por exemplo, un cliente que compra ou cancela unha subscrición.
  - **É unha subscrición recorrente:** Campo booleano verdadeiro/falso que determina se a subscrición se renovará co mesmo ID de subscrición sen intervención do cliente.
  - **Frecuencia de recorrencia (en meses):** Para as subscricións recorrentes, o mes que se renovará. Por exemplo, unha subscrición anual que se renova automaticamente para un cliente cada ano por outro ano ten o valor de 12.
  - **Importe da subscrición** : Cantidade de moeda que paga un cliente pola renovación da subscrición. Pode axudar a identificar padróns para diferentes niveis de subscricións.
- Polo menos dous rexistros de actividade para o 50 % dos clientes para os que queres calcular o abandono. As actividades dos clientes deben incluír:
  - **Chave primaria:** Identificador único para unha actividade. Por exemplo, unha visita a un sitio web ou un rexistro de uso que mostra ao cliente que viu un episodio dun programa de televisión.
  - **Marca de tempo:** Data e hora do evento identificado pola chave primaria.
  - **Evento:** Nome do evento que queres usar. Por exemplo, un campo chamado "UserAction" nun servizo de vídeo en streaming podería ter o valor de "Visualizado".
  - **Detalles:** información detallada sobre o evento. Por exemplo, un campo chamado "ShowTitle" nun servizo de vídeo en streaming podería ter o valor dun vídeo visualizado por un cliente.
- Faltan menos do 20 % de valores no campo de datos da entidade proporcionada.

## <a name="create-a-subscription-churn-prediction"></a>Crear unha predición da renovación dunha subscrición

Seleccione **Garda o borrador** en calquera momento para gardar o predición como borrador. O borrador predición móstrase no **As miñas predicións** ficha.

1. Ir a **Intelixencia** > **Predicións**.

1. No **Crear** ficha, seleccione **Usa modelo** no **Modelo de abandono de clientes** tella.

1. Seleccione **Subscrición** para o tipo de churn e despois **Comezar**.

1. **Poña nome a este modelo** e o **Nome da entidade de saída** para distinguilos doutros modelos ou entidades.

1. Seleccione **Seguinte**.

### <a name="define-customer-churn"></a>Definir renovación do cliente

1. Insira o número de **Días desde que rematou a subscrición** que a súa empresa considera que un cliente está nun estado renovado. Este período adoita estar ligado a actividades comerciais como ofertas ou outros esforzos de mercadotecnia que intentan evitar a perda do cliente.

1. Introduza o número de **Días para investigar o futuro para prever o abandono**. Por exemplo, predicir o risco de abandono dos seus clientes durante os próximos 90 días para alinearse cos seus esforzos de retención de mercadotecnia. A predición do risco de abandono por períodos de tempo máis longos ou máis curtos pode facer máis difícil abordar os factores do seu perfil de risco de abandono, dependendo das necesidades específicas da súa empresa.

1. Seleccione **Seguinte**.

### <a name="add-required-data"></a>Engadir datos obrigatorios

1. Seleccione **Engadir datos** para **Historial de subscricións**.

1. Seleccione o tipo de actividade semántica **Subscrición** que conteña a información necesaria do historial de subscrición. Se a actividade non está configurada, seleccione **aquí** e crealo.

1. Baixo **Actividades**, se os atributos da actividade foron mapeados semanticamente cando se creou a actividade, escolla os atributos ou a entidade específicos nos que desexa que se centre o cálculo. Se non se produciu a asignación semántica, seleccione **Editar** e mapea os teus datos.
  
   :::image type="content" source="media/subscription-churn-required.png" alt-text="Engade os datos necesarios para o modelo de subscrición":::

1. Seleccione **A continuación** e revise os atributos necesarios para este modelo.

1. Seleccione **Gardar**.

1. Seleccione **Engadir datos** para **Actividades do cliente**.

1. Seleccione o tipo de actividade semántica que proporciona a información da actividade do cliente. Se a actividade non está configurada, seleccione **aquí** e crealo.

1. Baixo **Actividades**, se os atributos da actividade foron mapeados semanticamente cando se creou a actividade, escolla os atributos ou a entidade específicos nos que desexa que se centre o cálculo. Se non se produciu a asignación semántica, seleccione **Editar** e mapea os teus datos.

1. Seleccione **A continuación** e revise os atributos necesarios para este modelo.

1. Seleccione **Gardar**.

1. Engade máis actividades ou selecciona **A continuación**.

### <a name="set-update-schedule"></a>Definir programación de actualizacións

1. Escolle a frecuencia para reciclar o teu modelo. Esta configuración é importante para actualizar a precisión das predicións a medida que se inxiren novos datos en Customer Insights. A maioría das empresas poden volverse formar unha vez ao mes e obter unha boa precisión para a súa predición.

1. Seleccione **Seguinte**.

### <a name="review-and-run-the-model-configuration"></a>Revisar e executar a configuración do modelo

O **Revisa e corre** O paso mostra un resumo da configuración e ofrece a oportunidade de facer cambios antes de crear o predición.

1. Seleccione **Editar** en calquera dos pasos para revisar e facer calquera cambio.

1. Se estás satisfeito coas túas seleccións, selecciona **Garda e executa** para comezar a executar o modelo. Seleccione **Feito**. O **As miñas predicións** aparece a pestana mentres se crea o predición. O proceso pode levar varias horas en función da cantidade de datos empregados na predición.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Ver os resultados de predición

1. Ir a **Intelixencia** > **Predicións**.

1. No **As miñas predicións** pestana, seleccione o predición que quere ver.

Hai tres seccións principais de datos dentro da páxina de resultados:

- **Rendemento do modelo de adestramento** : As notas A, B ou C indican o rendemento do predición e poden axudarche a tomar a decisión de usar os resultados almacenados na entidade de saída.
  
  :::image type="content" source="media/subscription-churn-modelperformance.PNG" alt-text="Imaxe da caixa de información da puntuación do modelo coa cualificación A.":::

  As cualificacións determínanse en función das seguintes regras:
  - **A** cando o modelo predixo con precisión polo menos o 50 % das previsións totais, e cando a porcentaxe de predicións precisas para os clientes que produciron é superior en polo menos un 10 % á media histórica.
  - **B** cando o modelo predixo con precisión polo menos o 50 % das previsións totais, e cando a porcentaxe de predicións precisas para os clientes que produciron é ata un 10 % superior á taxa de abandono media histórica.
  - **C** cando o modelo predixo con precisión menos do 50 % das previsións totais, ou cando a porcentaxe de predicións precisas para os clientes que produciron é menor que a taxa de abandono media histórica.
  
- **Probabilidade de renovación (número de clientes)**: grupos de clientes en función do risco previsto de renovación. Opcionalmente, [crear segmentos de clientes](prediction-based-segment.md) con alto risco de rotación. Estes segmentos axudan a comprender onde debe estar o seu corte para a subscrición a segmentos.  

  :::image type="content" source="media/subscription-churn-resultdistribution.PNG" alt-text="Gráfico que mostra a distribución dos resultados da renovación, divididos en rangos do 0 ao 100%":::

- **Factores máis influentes:** hai moitos factores que se teñen en conta á hora de crear a súa predición. Cada un dos factores ten a súa importancia calculada para as predicións agregadas que crea un modelo. Use estes factores para axudar a validar os seus resultados predición. Ou use esta información máis tarde para [crear segmentos](.//prediction-based-segment.md) que poderían axudar a influír no risco de abandono dos clientes.

  :::image type="content" source="media/subscription-churn-influentialfactors.PNG" alt-text="Lista que mostra factores influentes e a súa importancia para predicir o resultado da renovación.":::

> [!NOTE]
> Na entidade de saída para este modelo, *ChurnScore* é a probabilidade prevista de churn e *IsChurn* é unha etiqueta binaria baseada en *ChurnScore* cun limiar de 0,5. Se este limiar predeterminado non funciona para o teu escenario, [crear un novo segmento](segments.md) co seu limiar preferido. Para ver a puntuación de churn, vai a **Datos** > **Entidades** e ver a pestana de datos para a entidade de saída que definiu para este modelo.

[!INCLUDE [footer-include](includes/footer-banner.md)]
