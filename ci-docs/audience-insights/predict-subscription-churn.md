---
title: Predición de abandono de subscricións
description: Fai a predición de se un cliente está en risco por deixar de usar os produtos ou servizos da subscrición da súa empresa.
ms.date: 08/19/2020
ms.reviewer: zacook
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 03178fc1bfe611b1b0ced08bbbef876035875825
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643726"
---
# <a name="subscription-churn-prediction-preview"></a>Predición da renovación da subscrición (vista previa)

A predición da renovación da subscrición axuda a prever se un cliente está en risco por deixar de usar os produtos ou servizos da subscrición da súa empresa. Pode crear unha nova predición da renovación da subscrición na páxina **Intelixencia** > **Predicións**. Seleccione **As miñas predicións** para ver outras predicións que creou.

> [!TIP]
> Probe o tutorial de predición do abandono da subscrición usando datos de mostra: [Guía de mostra de predición do abandono da subscrición](sample-guide-predict-subscription-churn.md).

## <a name="prerequisites"></a>Requisitos previos

- Polo menos [Permisos de colaborador](permissions.md).
- Coñecemento empresarial para comprender o que significa a renovación para a súa empresa. Apoiamos as definicións de renovación baseadas no tempo, é dicir, considérase que un cliente renovou por un período de tempo despois da finalización da súa subscrición.
- Datos sobre as súas subscricións e o seu historial:
    - Identificadores de subscrición para distinguir subscricións.
    - Identificadores de clientes para identificar subscricións cos seus clientes.
    - Datas do evento de subscrición, que definen as datas de inicio, as datas de finalización e as datas en que ocorreron os eventos de subscrición.
    - Información da subscrición para definir se é unha subscrición recorrente e cantas veces se renova.
    - O esquema de datos semánticos para as subscricións require a seguinte información:
        - **ID de subscrición:** un identificador único dunha subscrición.
        - **Data de finalización da subscrición:** a data na que expira a subscrición para o cliente.
        - **Data de inicio da subscrición:** a data na que se inicia a subscrición para o cliente.
        - **Data da transacción:** data na que se produciu o cambio da subscrición. Por exemplo, un cliente que compra ou cancela unha subscrición.
        - **É unha subscrición recorrente:** un campo booleano verdadeiro/falso que determina se a subscrición renovarase co mesmo ID de subscrición sen a intervención do cliente
        - **Frecuencia de recorrencia (en meses):** para subscricións recorrentes, é o período polo que se renovará a subscrición. Está representado en meses. Por exemplo, unha subscrición anual que se renova automaticamente para un cliente cada ano por outro ano ten o valor de 12.
        - (Opcional) **Importe da subscrición:** a cantidade de moeda que un cliente paga pola renovación da subscrición. Pode axudar a identificar padróns para diferentes niveis de subscricións.
- Datos sobre as actividades do cliente:
    - Identificadores de actividades para distinguir actividades do mesmo tipo.
    - Identificadores de clientes para atribuír actividades aos seus clientes.
    - Información da actividade que contén o nome e a data da actividade.
    - O esquema de datos semánticos para as actividades do cliente inclúe:
        - **Clave principal:** un identificador único para unha actividade. Por exemplo, unha visita a un sitio web ou un rexistro de uso que mostra ao cliente que viu un episodio dun programa de televisión.
        - **Marca de tempo:** a data e a hora do evento identificadas pola clave principal.
        - **Evento:** o nome do evento que desexa usar. Por exemplo, un campo chamado "UserAction" nun servizo de vídeo en streaming podería ter o valor de "Visualizado".
        - **Detalles:** información detallada sobre o evento. Por exemplo, un campo chamado "ShowTitle" nun servizo de vídeo en streaming podería ter o valor dun vídeo visualizado por un cliente.
   > [!NOTE]
   > Necesitará polo menos dous rexistros de actividade para o 50% dos clientes para os que quere calcular a renovación.

## <a name="create-a-subscription-churn-prediction"></a>Crear unha predición da renovación dunha subscrición

1. Na información do público, vaia a **Intelixencia** > **Predicións**.
1. Seleccione o mosaico **Modelo de renovación de subscrición (vista previa)** e seleccione **Usar este modelo**.
   > [!div class="mx-imgBorder"]
   > ![Mosaico de modelo de renovación de subscrición co botón Utilizar este modelo](media/subscription-churn-usethismodel.PNG "Mosaico de modelo de renovación de subscrición co botón Utilizar este modelo")

### <a name="name-model"></a>Dar nome ao modelo

1. Proporcione un nome para o modelo para distinguilo doutros modelos.
1. Proporcione un nome para a entidade de saída usando só letras e números, sen espazos. Ese é o nome que empregará a entidade do modelo. despois, seleccione **Seguinte**.

### <a name="define-customer-churn"></a>Definir abandono de clientes

1. Insira o número de **Días desde que rematou a subscrición** que a súa empresa considera que un cliente está nun estado renovado. Este período normalmente gusta para as actividades empresariais como ofertas ou outros esforzos de mercadotecnia que intentan evitar a perda do cliente.
1. Introduza o número de **Días para investigar o futuro para predicir a renovación** para configurar unha xanela para predicir a renovación. Por exemplo, para predicir o risco de renovación dos seus clientes nos próximos 90 días para axustarse aos seus esforzos de retención de marketing. A predición do risco de renovación durante períodos de tempo máis longos ou máis curtos pode facer máis difícil abordar os factores do seu perfil de risco de abandono, pero isto depende moito dos requisitos específicos da súa empresa. Seleccione **Seguinte** para continuar
   >[!TIP]
   > Pode seleccionar **Gardar e pechar** en calquera momento para gardar a predición como borrador. Atopará o borrador de predición no separador **As miñas previsións** para continuar.

### <a name="add-required-data"></a>Engadir datos necesarios

1. Seleccione **Engadir datos** para **Historial de subscricións** e escolla a entidade que fornece a información do historial de subscricións tal e como se describe nos [requisitos previos](#prerequisites).
1. Se os campos a continuación non se enchen, configure a relación desde a entidade do seu historial de subscricións na entidade de Cliente.
    1. Seleccione a **Entidade do historial de subscricións**.
    1. Seleccione o **Campo** que identifica ao cliente na entidade do historial de subscricións. Debe relacionarse coa identificación de cliente principal da súa entidade de cliente.
    1. Seleccione a **Entidade de cliente** que se corresponde coa súa entidade de cliente principal.
    1. Escriba un nome que describa a relación.
       > [!div class="mx-imgBorder"]
       > ![Páxina do historial de subscricións que mostra a creación dunha relación co cliente](media/subscription-churn-subscriptionhistoryrelationship.PNG "Páxina do historial de subscricións que mostra a creación dunha relación co cliente")
1. Seleccione **Seguinte**.
1. Asigne os campos semánticos aos atributos da súa entidade do historial de subscricións e seleccione **Gardar**. Para obter descricións dos campos, bótelle unha ollada aos [requisitos previos](#prerequisites).
   > [!div class="mx-imgBorder"]
   > ![Páxina do historial de subscricións que mostra atributos semánticos que se asignan a campos da entidade do historial de subscricións seleccionado](media/subscription-churn-subscriptionhistorymapping.PNG "Páxina do historial de subscricións que mostra atributos semánticos que se asignan a campos da entidade do historial de subscricións seleccionado")
1. Seleccione **Engadir datos** para **Actividades de cliente** e escolla a entidade que fornece a información da actividade do cliente tal e como se describe nos requisitos previos.
1. Seleccione un tipo de actividade que coincida co tipo de actividade do cliente que está configurando.  Seleccione **Crear novo** e indique un nome se non ve unha opción que coincida co tipo de actividade que precisa.
1. Deberá configurar a relación desde a entidade de actividade de cliente na entidade de cliente.
    1. Seleccione o campo que identifica ao cliente na táboa de actividade do cliente, que pode estar directamente relacionado coa identificación de cliente principal da súa entidade de cliente.
    1. Seleccione a entidade de cliente que se corresponde coa súa entidade de Cliente principal
    1. Escriba un nome que describa a relación.
1. Seleccione **Seguinte**.
1. Asigne os campos semánticos aos atributos da súa entidade de actividade de cliente e seleccione **Gardar**. Para obter descricións dos campos, bótelle unha ollada aos [requisitos previos](#prerequisites).
1. (Opcional) Se ten algunha outra actividade de cliente que desexe incluír, repita os pasos anteriores.
   > [!div class="mx-imgBorder"]
   > ![Definir a relación da entidade](media/subscription-churn-customeractivitiesmapping.PNG "Páxina de actividades de clientes que mostra atributos semánticos que se asignan a campos da entidade da actividade do cliente seleccionada")
1. Seleccione **Seguinte**.

### <a name="set-schedule-and-review-configuration"></a>Establecer a programación e revisar a configuración

1. Estableza unha frecuencia para volver formar o modelo. Esta configuración é importante para actualizar a precisión das predicións a medida que se inxiren novos datos na información do público. A maioría das empresas poden volverse formar unha vez ao mes e obter unha boa precisión para a súa predición.
1. Seleccione **Seguinte**.
1. Revise a configuración. Pode volver a calquera parte da configuración da predición seleccionando **Editar** no valor amosado. Tamén pode seleccionar un paso de configuración no indicador de progreso.
1. Se todos os valores están configurados correctamente, seleccione **Gardar e executar** para comezar o proceso de predición. No separador **As miñas predicións**, pode ver o estado das súas predicións. O proceso pode levar varias horas en función da cantidade de datos empregados na predición.

## <a name="review-a-prediction-status-and-results"></a>Revise o estado da predición e os resultados

1. Vaia ao separador **As miñas predicións** en **Intelixencia** > **Predicións**.
   > [!div class="mx-imgBorder"]
   > ![Vista da páxina As miñas predicións](media/subscription-churn-mypredictions.PNG "Vista da páxina As miñas predicións")
1. Seleccione a predición que desexa revisar.
   - **Nome da predición:** o nome da predición indicado ao creala.
   - **Tipo de predición:** o tipo de modelo empregado para a predición
   - **Entidade de saída:** nome da entidade para almacenar a saída da predición. Pode atopar unha entidade con este nome en **Datos** > **Entidades**.
   - **Campo previsto:** este campo está completado só para algúns tipos de predicións e non se usa na predición da renovación de subscricións.
   - **Estado:** o estado actual da execución da predición.
        - **En cola:** a predición está actualmente á espera de que se executen outros procesos.
        - **Actualización:** a predición está a executar a fase de "puntuación" do procesamento de para producir resultados que fluirán na entidade de saída.
        - **Fallo:** a predición fallou. Seleccione **Rexistros** para obter máis detalles.
        - **Correcto:** a predición fíxose correctamente. Seleccione **Ver** nos tres puntos verticais para revisar a predición
   - **Editado:** a data na que se modificou a configuración da predición.
   - **Última actualización:** a data na que a predición actualizou resultados na entidade de saída.
1. Seleccione os tres puntos verticais xunto á predición da que desexa revisar os resultados e seleccione **Ver**.
   > [!div class="mx-imgBorder"]
   > ![Vista de opcións no menú de tres puntos verticais para obter unha predición, incluída a edición, actualización, vista, rexistros e eliminación](media/subscription-churn-verticalellipses.PNG "Vista de opcións no menú de tres puntos verticais para obter unha predición, incluída a edición, actualización, vista, rexistros e eliminación")
1. Hai tres seccións principais de datos dentro da páxina de resultados:
    1. **Desempeño do modelo de formación:** A, B ou C son posibles puntuacións. Esta puntuación indica o rendemento da predición e pode axudalo a tomar a decisión de usar os resultados almacenados na entidade de saída.
        - As puntuacións determínanse segundo as regras seguintes:
            - **A** cando o modelo predixo con precisión polo menos o 50 % do total de predicións e cando a porcentaxe de prediccións precisas para os clientes que abandonaron é maior que a taxa de abandono media histórica en polo menos un 10 % da taxa media de abandono histórica.
            - **B** cando o modelo predixo con precisión polo menos o 50 % do total de predicións e cando a porcentaxe de prediccións precisas para os clientes que abandonaron é ata un 10 % maior que a taxa de abandono media histórica da taxa media de abandono histórica.
            - **C** cando o modelo predixo con precisión menos do 50 % do total de predicións ou cando a porcentaxe de prediccións precisas para os clientes que abandonaron é inferior á taxa de abandono media histórica.
               > [!div class="mx-imgBorder"]
               > ![Vista do resultado do rendemento do modelo](media/subscription-churn-modelperformance.PNG "Vista do resultado do rendemento do modelo")
    1. **Probabilidade de renovación (número de clientes):** grupos de clientes en función do risco previsto de renovación. Estes datos poden axudalo máis tarde se quere crear un segmento de clientes con alto risco de renovación. Estes segmentos axudan a comprender onde debe estar o seu corte para a subscrición a segmentos.
       > [!div class="mx-imgBorder"]
       > ![Gráfico que mostra a distribución dos resultados da renovación, divididos en rangos do 0 ao 100%](media/subscription-churn-resultdistribution.PNG "Gráfico que mostra a distribución dos resultados da renovación, divididos en rangos do 0 ao 100%")
    1. **Factores máis influentes:** hai moitos factores que se teñen en conta á hora de crear a súa predición. Cada un dos factores ten calculada a súa importancia para as predicións agregadas que crea un modelo. Pode usar estes factores para axudar a validar os resultados da súa predición. Ou pode usar esta información máis tarde para [crear segmentos](segments.md) que poderían axudalo a influír no risco de renovación dos clientes.
       > [!div class="mx-imgBorder"]
       > ![Lista que mostra factores influentes e a súa importancia para predicir o resultado da renovación](media/subscription-churn-influentialfactors.PNG "Lista que mostra factores influentes e a súa importancia para predicir o resultado da renovación")

## <a name="fix-a-failed-prediction"></a>Corrixir unha predición fallida

1. Vaia ao separador **As miñas predicións** en **Intelixencia** > **Predicións**.
1. Seleccione a predición para a que desexa ver os rexistros de erros e seleccione **Rexistros**.
   > [!div class="mx-imgBorder"]
   > ![Vista da barra do menú de resultados, incluídos os botóns de peche, modelo de edición e rexistros](media/subscription-churn-logsbutton.PNG "Vista da barra do menú de resultados, incluídos os botóns de peche, modelo de edición e rexistros")
1. Revise todos os erros. Existen varios tipos de erros que poden ocorrer e describen que problema causou o erro. Por exemplo, un erro de que non ten datos suficientes para predicir con precisión resólvese normalmente cargando datos adicionais.

## <a name="refresh-a-prediction"></a>Actualizar unha predición

As predicións actualizaranse automaticamente no mesmo [programa que actualiza os seus datos](system.md#schedule-tab) tal e como se configura nos axustes.

1. Vaia ao separador **As miñas predicións** en **Intelixencia** > **Predicións**.
1. Seleccione os tres puntos verticais xunto á predición que quere actualizar.
1. Seleccione **Actualizar**.

## <a name="delete-a-prediction"></a>Eliminar unha predición

1. Vaia ao separador **As miñas predicións** en **Intelixencia** > **Predicións**.
1. Seleccione os tres puntos verticais xunto á predición que quere eliminar.
1. Seleccione **Eliminar**.

> [!NOTE]
> Se elimina unha predición eliminarase a súa entidade de saída.
