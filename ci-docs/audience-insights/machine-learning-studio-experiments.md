---
title: Experimentos de Machine Learning Studio (clásico)
description: Use modelos de Machine Learning Studio (clásico) en Dynamics 365 Customer Insights.
ms.date: 12/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: ameetj
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: b979dd177b7c6de1971c02a69748006d041e4d2c3e49a3639dba03212bd7acf9
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033721"
---
# <a name="use-models-based-on-azure-machine-learning-studio-classic"></a>Usar modelos baseados en Azure Machine Learning Studio (clásico)

Os datos unificados en Dynamics 365 Customer Insights son unha fonte para construír modelos de aprendizaxe automática que poden xerar información comercial adicional. Customer Insights intégrase con Machine Learning Studio (clásico) para usar os seus propios modelos personalizados. Para ver como os modelos desenvolvidos en Azure Machine Learning se integran con Customer Insights, consulte [Experimentos de Azure Machine Learning](azure-machine-learning-experiments.md).

## <a name="prerequisites"></a>Requisitos previos

- Acceder a Customer Insights
- Activar unha subscrición de Azure Enterprise
- [Perfís de cliente unificados](data-unification.md)
- Configuración de [exportación de entidades a Azure Blob Storage](export-azure-blob-storage.md)

## <a name="set-up-machine-learning-studio-classic"></a>Configurar Machine Learning Studio clásico

Nun primeiro paso, necesitamos crear un espazo de traballo para Machine Learning Studio (clásico) e abrilo.

1. Vaia a[https://www.portal.azure.com](https://www.portal.azure.com/) e inicie sesión.

1. Seleccione **Crear un recurso**.

1. Busque o **Espazo de traballo de Machine Learning Studio** e seleccione **Crear**.

1. Insira os detalles necesarios para [crear o espazo de traballo](/azure/machine-learning/studio/create-workspace). Escolla o **Nivel de prezos do plan de servizos web** en función da cantidade de datos que pretende importar. Para ter o mellor rendemento, seleccione a **Localización** que está xeograficamente máis preto de vostede.

1. Despois de crear o recurso, aparecerá o panel o espazo de traballo de Machine Learning Studio. Seleccione **Lanzar Machine Learning Studio**.

   ![Interface de usuario de Azure Machine Learning Studio.](media/azure-machine-learning-studio.png)

## <a name="work-with-azure-machine-learning-studio"></a>Traballar con Azure Machine Learning Studio

Agora pode crear un novo experimento ou importar un modelo de experimento existente dende a galería de mostras. Hai experimentos de mostra para tres escenarios estándar:

- [Predición de abandono](#churn-analysis)

- [Valor de duración do cliente](#customer-lifetime-value-prediction)

- [Recomendación de produtos ou seguinte mellor acción](#productrecommendation-or-next-best-action)

1. Se crea un novo experimento ou usa un modelo de experimento da galería, necesitará configurar as propiedades de **Importar datos**. Use a experiencia guiada ou proporcione directamente detalles para acceder ao Azure Blob Storage que contén os seus datos.  

   ![Experimento de Azure Machine Learning Studio.](media/azure-machine-learning-studio-experiment.png)

1. Agora pode construír unha canle de procesamento personalizada para limpar e preprocesar os datos, extraer funcións e adestrar un modelo adecuado.

1. Probe e optimice o rendemento do modelo.

1. Cando estea satisfeito coa calidade dun modelo, seleccione **Configurar o servizo web** > **Servizo web preditivo**. Esta opción importa o modelo adestrado e a canle de caracterización do experimento de adestramento a un servizo de predición. O servizo de predición pode tomar outro conxunto de datos de entrada co esquema empregado no experimento de adestramento para facer predicións.

   ![Configurar un servizo web preditivo.](media/predictive-webservice-control.png)

1. Unha vez que o experimento de servizo web preditivo ten éxito, pode implementalo para a programación automática. Para que o servizo web funcione con Customer Insights, seleccione **Implementar o servizo web** > **Implementar vista previa do [novo] servizo web**. [Máis información acerca do despregamento dun servizo web](/azure/machine-learning/studio/deploy-a-machine-learning-web-service).

   ![Despregar un servizo web preditivo.](media/predictive-webservice-deploy.png)

## <a name="sample-models-from-the-gallery"></a>Modelos de mostra da galería

Empregaremos un escenario ficticio de Contoso Hotel para os modelos deste artigo. Contoso Hotel recolle os seguintes datos:

- Datos de CRM consistentes na actividade de estadías no hotel. O conxunto de datos inclúe información sobre as datas de estadía de cada cliente rexistrado. Tamén contén información sobre a reserva, tipos de cuarto, detalles do gasto etc. Os datos abarcan catro anos, desde xaneiro de 2014 a xaneiro de 2018.
- Perfís de cliente dos hóspedes. Estes perfís conteñen información sobre cada cliente, incluído o seu nome, data de nacemento, enderezo postal, xénero e número de teléfono.
- Uso de servizos ofrecidos polo hotel, como o balneario, lavandería, wifi ou mensaxería. Esta información rexístrase para cada cliente rexistrado. Normalmente, o uso de servizos está ligado á estadía. Nalgúns casos, os servizos poden ser empregados polos clientes sen aloxarse no hotel.

## <a name="churn-analysis"></a>Análise de abandono

A análise de abandono aplícase a diferentes áreas comerciais. Neste exemplo, imos analizar o abandono de servizos, especialmente no contexto dos servizos hoteleiros como se describe máis arriba. Ofrece un exemplo funcional dun modelo de canalización de extremo a extremo que se pode empregar como punto de partida para calquera outro tipo de modelo de abandono.

### <a name="definition-of-churn"></a>Definición de abandono

A definición de abandono pode variar en función do escenario. Neste exemplo, un hóspede que non visitou o hotel o ano pasado debe ser etiquetado como perdido.  

O modelo de experimento pódese importar da galería. En primeiro lugar, asegúrese de importar os datos de **Actividade de estadía no hotel**, **Datos do cliente** e **Datos de uso do servizo** de Azure Blob Storage.

   ![Importar datos para o modelo de abandono.](media/import-data-azure-blob-storage.png)

### <a name="featurization"></a>Caracterización

A partir da definición de abandono, primeiro identificamos as características en bruto que influirán na etiqueta. A continuación, procesamos estas características en bruto en características numéricas que se poden usar con modelos de aprendizaxe automática. A integración de datos ocorre en Customer Insights para que poidamos unir estas táboas usando o *ID de cliente*.

   ![Unir datos importados.](media/join-imported-data.png)

A caracterización da construción do modelo para a análise do abandono pode ser un pouco complicada. Os datos son unha función de tempo coa nova actividade hoteleira rexistrada a diario. Durante a caracterización queremos xerar características estáticas a partir dos datos dinámicos. Neste caso, xeramos múltiples funcións da actividade hoteleira cunha xanela deslizante dun ano. Tamén ampliamos as características categóricas como o tipo de cuarto ou o tipo de reserva a funcións separadas mediante a codificación one-hot.  

Lista final de características:

| **Número**  | **Original_Column**          | **Características derivadas**                                                                                                                      |
|-------------|------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|
| 1           | Tipo de cuarto                    | RoomTypeLargeCount, RoomTypeSmallCount                                                                                                    |
| 2           | Tipo de reserva                 | BookingTypeOnlineCount, BookingTypePhoneCallCount                                                                                         |
| 3           | Categoría de viaxe              | TravelCategoryBusinessCount, TravelCategoryLeisureCount                                                                                   |
| 4           | Dólares gastados                | TotalDollarSpent                                                                                                                          |
| 5           | Datas de entrada e de saída  | StayDayCount, StayDayCount2016, StayDayCount2015, StayDayCount2014, StayCount, StayCount2016. StayCount2015, StayCount2014                |
| 6           | Uso dos servizos                | UsageTenure, ConciergeUsage, CourierUsage, DryCleaningUsage, GymUsage, PhoneUsage, RestaurantUsage, SpaUsage, TelevisionUsage, WifiUsage  |

### <a name="model-selection"></a>Selección do modelo

Agora necesitamos escoller o algoritmo óptimo para usar. Neste caso, a maioría das funcións están baseadas en características categóricas. Normalmente, os modelos baseados na árbore de decisión funcionan ben. Se só hai características numéricas, as redes neuronais poderían ser unha mellor opción. A máquina vectorial de soporte (SVM) tamén é un bo candidato en tales situacións; non obstante, necesita un pouco de axuste para extraer o mellor rendemento. Eliximos a **Árbore de decisión impulsada de dúas clases** como primeiro modelo de elección seguido da **SVM de dúas clases** como segundo modelo. Azure Machine Learning Studio permítelle facer probas A/B, polo que é beneficioso comezar con dous modelos en vez dun.

A seguinte imaxe mostra a canle de formación e avaliación do modelo de Azure Machine Learning Studio:

![Modelo de abandono en Azure Machine Learning Studio.](media/azure-machine-learning-model.png)

Tamén aplicamos unha técnica chamada **Importancia das características de permutación**, un aspecto importante da optimización de modelos. Os modelos incorporados teñen pouca ou ningunha información sobre o impacto de calquera característica específica na predición final. A calculadora de importancia das características usa un algoritmo personalizado para calcular a influencia das características individuais sobre o resultado dun modelo específico. A importancia da característica normalízase entre +1 e -1. Unha influencia negativa significa que a función correspondente ten unha influencia contraintuitiva no resultado e debe ser eliminada do modelo. Unha influencia positiva indica que a característica está a contribuír bastante cara a predición. Estes valores non son coeficientes de correlación porque son diferentes métricas. Para obter máis información, consulte [Importancia das características de permutación](/azure/machine-learning/studio-module-reference/permutation-feature-importance).

Todo o [experimento de abandono está dispoñible en Azure AI Gallery](https://gallery.azure.ai/Experiment/Hotel-Churn-Predictive-Exp).

## <a name="customer-lifetime-value-prediction"></a>Predición do valor de duración do cliente

O cálculo do valor de duración do cliente (CLTV) é unha das medidas clave que unha empresa pode utilizar para avaliar e segmentar os seus clientes. Para a hostalería, é fundamental coñecer os seus clientes. Por exemplo, comprender os factores que conforman os bos clientes é información crucial. Axuda á administración do hotel a valorar en que características deben centrarse e mellorar para satisfacer aos clientes que máis pagan. Estas decisións poden ter un impacto directo sobre as vendas e as ganancias.  

### <a name="definition-of-cltv"></a>Definición de CLTV

Para este exemplo, definimos o CLTV dun cliente como o importe total en dólares que se espera que o cliente gaste nos próximos 365 días. Empregaremos os últimos tres anos de datos de todos os clientes para predecir este valor.

### <a name="featurization"></a>Caracterización

Neste caso, a caracterización parecerase bastante ao escenario de abandono. Non obstante, as etiquetas e os valores previstos son diferentes do definido anteriormente.

### <a name="model-selection"></a>Selección do modelo

Predicir o CLTV é un problema de regresión xa que o valor previsto é unha variable continua positiva valorada. En función das propiedades das características, seleccionamos a **Regresión da árbore de decisión reforzada** como algoritmo e a **Regresión da rede neuronal** como outro algoritmo para adestrar o modelo.

## <a name="product-recommendation-or-next-best-action"></a>Recomendación de produtos ou seguinte mellor acción

A recomendación de produtos nun escenario hoteleiro interprétase como a recomendación de servizos ofrecidos polo hotel aos clientes. O obxectivo é escoller os servizos axeitados para os clientes para que se maximice o seu uso. É semellante ás recomendacións de películas para usuarios de servizos de emisión de vídeo.

### <a name="definition-of-product-recommendation-or-next-best-action"></a>Definición de recomendación de produtos ou seguinte mellor acción

Definimos o obxectivo como maximizar a cantidade en dólares do uso do servizo ofrecendo os mellores servizos correspondentes aos clientes do hotel segundo o seu interese.

### <a name="featurization"></a>Caracterización

Do mesmo xeito que o modelo de abandono, unimos o ServiceCustomerID do hotel co CustomerID para poder construír recomendacións de xeito coherente por CustomerID.

![Caracterización do modelo de recomendación.](media/azure-machine-learning-model-featurization.png)

Os datos proveñen de tres entidades diferentes e deles derivan as funcións. A caracterización do problema da recomendación é diferente en comparación cos escenarios de abandono ou de CLTV. O modelo de recomendación necesita datos de entrada en forma de tres conxuntos de características.

### <a name="model-selection"></a>Selección do modelo

Predecimos produtos ou servizos empregando o algoritmo chamado **Train Matchbox Recommender** para adestrar o modelo de recomendacións.

![Algoritmo de recomendación de produtos.](media/azure-machine-learning-model-recommendation-algorithm.png)

Os tres portos de entrada do modelo **Train Matchbox Recommender** collen os datos de uso do servizo de adestramento, a descrición do cliente (opcional) e a descrición do servizo. Hai tres xeitos diferentes de puntuar o modelo. Un é para a avaliación do modelo no que se calcula unha puntuación de ganancia acumulada normalizada con desconto (NDCG) para clasificar os elementos valorados. Neste experimento, a puntuación de NDCG foi de 0,97. As outras dúas opcións son a puntuación do modelo en todo o catálogo de servizos recomendables ou a puntuación só en elementos que os usuarios non utilizaron antes.

Mirando máis para a distribución das recomendacións en todo o catálogo de servizos, notamos que o teléfono, o wifi e a mensaxería son os servizos máis recomendados. Isto é coherente co que atopamos a partir das distribucións dos datos de consumo de servizos:

![Resultado do modelo de recomendación.](media/azure-machine-learning-model-output.png)

Todo o [experimento de recomendación de produtos pódese acceder en Azure AI Gallery.](https://gallery.azure.ai/Experiment/Recommendation-4)

## <a name="integrate-custom-models"></a>Integrar modelos personalizados

Para usar estas predicións en Customer Insights, cómpre **exportar** as predicións xunto cos ID de cliente. [Expórteos á mesma localización de almacenamento de Azure Blob](/azure/storage/common/storage-import-export-data-from-blobs) á que exporta os datos de orixe. O servizo web preditivo pode programarse para que funcione regularmente e actualice as puntuacións.

Os datos xerados polo modelo personalizado pódense empregar para enriquecer aínda máis os seus datos dos clientes. Para obter máis información, consulte [Modelos de aprendizaxe automática personalizados](custom-models.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]