---
title: Predición de abandono transaccional
description: Prediga se un cliente está en risco de deixar de comprar os seus servizos ou produtos.
ms.date: 11/12/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 43fcd37f8dd71e2890334a4cc53d49dae97d63c6
ms.sourcegitcommit: 6d5dd572f75ba4c0303ec77c3b74e4318d52705c
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 04/16/2021
ms.locfileid: "5906854"
---
# <a name="transactional-churn-prediction-preview"></a>Predición de abandono transaccional (previsualización)

A predición do abandono transaccional axuda a predicir se un cliente deixará de mercar os seus produtos ou servizos nunha xanela de tempo determinada. Pode crear novas predicións de abandono en **Intelixencia** > **Predicións**. Seleccione **As miñas predicións** para ver outras predicións que creou.

> [!TIP]
> Probe o tutorial para obter unha predición do abandono transaccional usando datos de mostra: [Guía de mostra de predición do abandono transaccional (vista previa)](sample-guide-predict-transactional-churn.md).

## <a name="prerequisites"></a>Requisitos previos

- Polo menos [Permisos de colaborador](permissions.md) en Customer Insights.
- Coñecemento empresarial para comprender o que significa a renovación para a súa empresa. Admitimos as definicións de abandono baseadas no tempo, o que significa que se considera que un cliente abandonou despois dun período sen compras.
- Datos sobre as súas transaccións/compras e o seu historial:
    - Identificadores de transaccións para distinguir compras/transaccións.
    - Identificadores de clientes para facer coincidir as transaccións cos seus clientes.
    - Datas de eventos de transacción, que definen as datas en que se produciu a transacción.
    - O esquema de datos semánticos para compras/transaccións require a seguinte información:
        - **ID de transacción:** Un identificador único dunha compra ou transacción.
        - **Data da transacción:** A data da compra ou transacción.
        - **Valor da transacción:** O importe da moeda/valor numérico da transacción/elemento.
        - (Opcional) **ID de produto único:** O ID do produto ou servizo adquirido se os seus datos están a un nivel de elemento de liña.
        - (Opcional) **Se esta transacción foi unha devolución:** Un campo verdadeiro/falso que identifica se a transacción foi ou non unha devolución. Se o **Valor da transacción** é negativo, tamén usaremos esta información para inferir un retorno.
- (Opcional) Datos sobre actividades do cliente:
    - Identificadores de actividades para distinguir actividades do mesmo tipo.
    - Identificadores de clientes para atribuír actividades aos seus clientes.
    - Información da actividade que contén o nome e a data da actividade.
    - O esquema de datos semánticos para as actividades do cliente inclúe:
        - **Clave principal:** un identificador único para unha actividade. Por exemplo, unha visita ao sitio web ou un rexistro de uso que mostra que o cliente probou unha mostra do seu produto.
        - **Marca de tempo:** a data e a hora do evento identificadas pola clave principal.
        - **Evento:** o nome do evento que desexa usar. Por exemplo, un campo chamado "UserAction" nunha tenda de ultramarinos pode ser un cupón utilizado polo cliente.
        - **Detalles:** información detallada sobre o evento. Por exemplo, un campo chamado "CouponValue" nunha tenda de alimentación pode ser o valor en moeda do cupón.
- Características datos suxeridas:
    - Datos históricos suficientes: datos de transaccións durante polo menos o dobre da xanela de tempo seleccionada. Preferiblemente, de dous a tres anos de datos de subscrición. 
    - Compras múltiples por cliente: idealmente polo menos dúas transaccións por cliente.
    - Número de clientes: polo menos 10 perfís clientes, preferentemente máis de 1.000 clientes únicos. O modelo fallará con menos de 10 clientes e con datos históricos insuficientes.
    - Integridade dos datos: menos do 20 % dos valores que faltan no campo de datos da entidade proporcionada.

> [!NOTE]
> Para unha empresa con alta frecuencia de compra de clientes (cada poucas semanas), recoméndase seleccionar unha ventá predición máis curta e definir o abandono. Para unha frecuencia de compra baixa (cada poucos meses ou unha vez ao ano), elixa unha fiestra máis longa de predición e defina o abandono.

## <a name="create-a-transactional-churn-prediction"></a>Crear unha predición de abandono transaccional

1. En Customer Insights, diríxase a **Intelixencia** > **Predicións**.

1. Seleccione o mosaico **Modelo de abandono do cliente (vista previa)** e seleccione **Usar este modelo**.
   
1. No panel **Modelo de abandono do cliente**, escolla **Transaccional** e seleccione **Comezar**.

:::image type="content" source="media/select-transaction-churn.PNG" alt-text="Captura de pantalla coa opción transaccional seleccionada no panel do modelo de abandono do cliente.":::

### <a name="name-model"></a>Dar nome ao modelo

1. Proporcione un nome para o modelo para distinguilo doutros modelos.

1. Proporcione un nome para a entidade de saída usando só letras e números, sen espazos. Ese é o nome que empregará a entidade do modelo. 

1. Seleccione **Seguinte**.

### <a name="define-customer-churn"></a>Definir renovación do cliente

1. Estableza unha xanela de días para predicir o abandono no campo **Identificar os clientes que poidan abandonar nos seguintes**. Por exemplo, predicir o risco de abandono dos seus clientes durante os próximos 90 días para alinearse cos seus esforzos de retención de mercadotecnia. A predición do risco de abandono por un período de tempo máis longo ou máis curto pode facer máis difícil abordar os factores do seu perfil de risco de abandono, pero depende das necesidades específicas do seu negocio. 
   >[!TIP]
   > Pode seleccionar **Gardar e pechar** en calquera momento para gardar a predición como borrador. Atopará o borrador de predición no separador **As miñas previsións** para continuar.

1. Introduza o número de días para definir o abandono no campo **Un cliente abandonou se non realizou compras en:**. Por exemplo, se un cliente non realizou compras nos últimos 30 días, é posible que a súa empresa considere que abandonou. 

1. Seleccione **Seguinte** para continuar

### <a name="add-required-data"></a>Engadir datos obrigatorios

1. Seleccione **Engadir datos** para **Historial de compras** e escolla a entidade que fornece a información do historial de transaccións/compras como se describe nos [requisitos previos](#prerequisites).

1. Asigne os campos semánticos aos atributos da súa entidade do historial de compras e seleccione **Seguinte**. Para obter descricións dos campos, bótelle unha ollada aos [requisitos previos](#prerequisites).

   :::image type="content" source="media/model-map-purchase-entity.PNG" alt-text="Asignar campos semánticos da entidade de compra.":::

1. Se os campos de abaixo non se enchen, configure a relación da súa entidade do historial de compras á entidade Cliente.
    1. Seleccione a **entidade do historial de compra**.
    1. Seleccione o **Campo** que identifica ao cliente na entidade do historial de compras. Debe relacionarse coa identificación de cliente principal da súa entidade de cliente.
    1. Seleccione a **Entidade de cliente** que se corresponde coa súa entidade de cliente principal.
    1. Escriba un nome que describa a relación.

    :::image type="content" source="media/model-purchase-join.PNG" alt-text="Páxina do historial de compras que mostra a creación dunha relación co cliente.":::
   
1. Seleccione **Seguinte**.

1. Opcionalmente, seleccione **Engadir datos** para **Actividades do cliente**. Escolla a entidade que proporciona a información da actividade do cliente como se describe nos requisitos previos.

1. Asigne os campos semánticos aos atributos da súa entidade de actividade do cliente e seleccione **Seguinte**. Para obter descricións dos campos, bótelle unha ollada aos [requisitos previos](#prerequisites).

   :::image type="content" source="media/map-transaction-data-fields.png" alt-text="Asignar campos de clientes para datos transacionais.":::

1. Seleccione un tipo de actividade que coincida co tipo de actividade do cliente que está configurando. Seleccione **Crear novo** e elixa un tipo de actividade dispoñible ou cree un novo tipo.

1. Deberá configurar a relación desde a entidade de actividade de cliente na entidade de cliente.
    1. Seleccione o campo que identifica ao cliente na entidade de actividade do cliente. Pode estar directamente relacionado co ID de cliente principal da súa entidade Cliente.
    1. Seleccione a entidade de cliente que se corresponde coa súa entidade de Cliente principal
    1. Escriba un nome que describa a relación.

1. Seleccione **Gardar**.

1. Se ten algunha outra actividade do cliente que desexa incluír, repita os pasos anteriores.

1. Seleccione **Seguinte**.

### <a name="set-schedule-and-review-configuration"></a>Establecer a programación e revisar a configuración

1. Estableza unha frecuencia para volver formar o modelo. Esta configuración é importante para actualizar a precisión das predicións a medida que se inxiren novos datos. A maioría das empresas poden volverse formar unha vez ao mes e obter unha boa precisión para a súa predición.

1. Seleccione **Seguinte**.

1. Revise a configuración da predición. Pode volver aos pasos anteriores seleccionando **Editar** no valor mostrado. Tamén pode seleccionar un paso de configuración no indicador de progreso.

1. Se todos os valores están configurados correctamente, seleccione **Gardar e executar** para comezar o proceso de predición. No separador **As miñas predicións**, pode ver o estado das súas predicións. O proceso pode levar varias horas en función da cantidade de datos empregados na predición.

## <a name="review-a-prediction-status-and-results"></a>Revise o estado da predición e os resultados

1. Vaia a **Intelixencia** > **Predicións** e seleccione o separador **As miñas predicións**.

1. Seleccione a predición que desexa revisar.
   - **Nome da predición:** Nome da predición proporcionado ao creala.
   - **Tipo de predición:** Tipo de modelo usado para a predición
   - **Entidade de saída:** nome da entidade para almacenar a saída da predición. Pode atopar unha entidade con este nome en **Datos** > **Entidades**.    
     Na entidade de saída, *ChurnScore* é a probabilidade prevista de abandono e *IsChurn* é unha etiqueta binaria baseada en *ChurnScore* cun limiar de 0,5. É posible que o limiar predeterminado non funcione no seu escenario. [Cree un novo segmento](segments.md#create-a-new-segment) co seu limiar preferido.
     Non todos os clientes son necesariamente clientes activos. É posible que algúns deles non tivesen ningunha actividade durante moito tempo e xa se consideran perdidos, segundo a definición de abandono. Non é útil predicir o risco de abandono para os clientes que xa abandonaron porque non son o público de interese.
   - **Campo previsto:** Este campo só se completa con algúns tipos de predicións e non se usa na predición do abandono.
   - **Estado:** Estado da execución da predición.
        - **En cola:** a predición está á espera de que se executen outros procesos.
        - **Actualizando:** a predición está executándose actualmente para producir resultados que fluirán cara á entidade de saída.
        - **Fallou:** Fallou a execución da predición. Para obter máis detalles, [revise os rexistros](#troubleshoot-a-failed-prediction).
        - **Con éxito:** a predición tivo éxito. Seleccione **Ver** nos tres puntos verticais para revisar a predición
   - **Editado:** a data na que se modificou a configuración da predición.
   - **Última actualización:** a data na que a predición actualizou resultados na entidade de saída.

1. Seleccione os tres puntos verticais xunto á predición da que desexa revisar os resultados e seleccione **Ver**.

   :::image type="content" source="media/model-subs-view.PNG" alt-text="Control de visualización para ver os resultados dunha predición.":::   

1. Hai tres seccións principais de datos dentro da páxina de resultados:
    1. **Desempeño do modelo de formación:** A, B ou C son posibles puntuacións. Esta puntuación indica o rendemento da predición e pode axudalo a tomar a decisión de usar os resultados almacenados na entidade de saída. As puntuacións determínanse segundo as regras seguintes:
         
         - **A** cando o modelo predixo con precisión polo menos o 50 % das predicións totais e cando a porcentaxe de predicións precisas para os clientes que abandonaron é superior á taxa de referencia nun 10 % como mínimo.
            
         - **B** cando o modelo predixo con precisión polo menos o 50 % das predicións totais e cando a porcentaxe de predicións precisas para os clientes que abandonaron é ata un 10 % superior á referencia.
            
         - **C** cando o modelo predixo con precisión menos do 50 % das predicións totais ou cando a porcentaxe de predicións precisas para os clientes que abandonaron é inferior á referencia.
               
         - A **referencia** toma a entrada da fiestra de tempo da predición para o modelo (por exemplo, un ano) e o modelo crea diferentes fraccións de tempo dividíndoo entre 2 ata alcanzar un mes ou menos. Utiliza estas fraccións para crear unha regra de negocio para clientes que non compraron neste período de tempo. Considérase que estes clientes abandonaron. Elíxese como modelo de referencia a regra de negocio baseada no tempo con maior capacidade para predicir quen é susceptible de abandonar.
            
    1. **Probabilidade de renovación (número de clientes):** grupos de clientes en función do risco previsto de renovación. Estes datos poden axudalo máis tarde se quere crear un segmento de clientes con alto risco de renovación. Estes segmentos axudan a comprender onde debe estar o seu corte para a subscrición a segmentos.
       
    1. **Factores máis influentes:** hai moitos factores que se teñen en conta á hora de crear a súa predición. Cada un dos factores ten a súa importancia calculada para as predicións agregadas que crea un modelo. Pode usar estes factores para axudar a validar os resultados da súa predición. Ou pode usar esta información máis tarde para [crear segmentos](segments.md) que poderían axudalo a influír no risco de renovación dos clientes.

## <a name="troubleshoot-a-failed-prediction"></a>Resolver problemas de predición fallida

1. Vaia a **Intelixencia** > **Predicións** e seleccione o separador **As miñas predicións**.

1. Seleccione os tres puntos verticais xunto á predición para a que desexa ver os rexistros de erros.

1. Seleccione **Rexistros**.

1. Revise todos os erros. Existen varios tipos de erros que poden ocorrer e describen que problema causou o erro. Por exemplo, un erro que consiste en que non hai datos suficientes para predicir con precisión adoita resolverse cargando datos adicionais en Customer Insights.

## <a name="refresh-a-prediction"></a>Actualizar unha predición

As predicións actualizaranse automaticamente no mesmo [programa que actualiza os seus datos](system.md#schedule-tab) tal e como se configura nos axustes. Tamén pode actualizalos manualmente.

1. Vaia a **Intelixencia** > **Predicións** e seleccione o separador **As miñas predicións**.

1. Seleccione os tres puntos verticais xunto á predición que quere actualizar.

1. Seleccione **Actualizar**.

## <a name="delete-a-prediction"></a>Eliminar unha predición

Eliminar unha predición tamén elimina a súa entidade de saída.

1. Vaia a **Intelixencia** > **Predicións** e seleccione o separador **As miñas predicións**.

1. Seleccione os tres puntos verticais xunto á predición que quere eliminar.

1. Seleccione **Eliminar**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
