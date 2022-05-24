---
title: Completar datos parciais mediante predicións
description: Utilice predicións para cubrir datos de clientes incompletos.
ms.date: 11/01/2021
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-predictions
- ci-custom-models
- customerInsights
ms.openlocfilehash: e2cace3547a0b584dbf26ae5eecf86f3b256649f
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 05/11/2022
ms.locfileid: "8740717"
---
# <a name="complete-your-partial-data-with-predictions-deprecated"></a>Completa os teus datos parciais con predicións (obsoleto)

> [!IMPORTANT]
> Esta característica será **obsoleto** a partir de **5 de novembro de 2021**. As implementacións actuais seguirán funcionando ata que se elimine a función, pero non poderás crear novas integracións usando as instrucións que aparecen a continuación.

As predicións permiten crear valores previstos facilmente que poden mellorar a comprensión dun cliente. Na páxina **Intelixencia** > **Predicións**, pode seleccionar **As miñas predicións** para ver as predicións que configurou noutras partes de Customer Insights e permitirlle seguir personalizándoas.

> [!NOTE]
> Non pode usar esta función se o seu contorno usa o almacenamento Azure Data Lake Gen 2.
>
> A función de predicións usa medios automatizados para avaliar datos e facer predicións a partir dese dato e, polo tanto, ten a capacidade de ser utilizada como método de perfilado, xa que ese termo está definido polo Regulamento xeral de protección de datos ("RXPD"). O uso desta función para o procesamento de datos por parte do cliente pode estar suxeito a RXPD ou a outras leis ou regulamentos. Vostede é responsable de garantir que o seu uso de Dynamics 365 Customer Insights, incluíndo as predicións, cumpre con todas as leis e regulamentos aplicables, incluídas as leis relacionadas coa privacidade, os datos persoais, os datos biométricos, a protección de datos e a confidencialidade das comunicacións.

## <a name="prerequisites"></a>Requisitos previos

Antes de que a súa organización poida usar a función de predicións, asegúrese de que se cumpran os seguintes requisitos previos:

1. A súa organización ten unha instancia [configurada en Microsoft Dataverse](/ai-builder/build-model#prerequisites) e está na mesma organización que Customer Insights.

2. O seu contorno de Customer Insights está anexo á súa instancia de Dataverse.

Para obter máis información, consulte [Crear un novo contorno](create-environment.md).

## <a name="create-a-prediction-in-the-customer-entity"></a>Crear unha predición na entidade de Cliente

1. Ir a **Datos** > **Entidades**.

2. Seleccione a entidade **Cliente**.

3. Na entidade **Cliente: CustomerInsights**, seleccione no separador **Campos**.

4. Atope o nome do atributo para o que desexe prever os valores e seleccione a icona **Visión xeral** na columna **Resumo**.
   > [!div class="mx-imgBorder"]
   > ![Icona de vista xeral.](media/intelligence-overviewicon.png "Icona de vista xeral")

5. Se hai unha alta taxa de valores que faltan para o seu atributo, seleccione **Prever valores que faltan** para continuar coa súa predición.
   > [!div class="mx-imgBorder"]
   > ![Vista xeral do estado con botón de predición de valores que faltan.](media/intelligence-overviewpredictmissingvalues.png "Vista xeral do estado con botón de predición de valores que faltan")

6. Proporcione un **Nome para mostrar** e un **Nome da entidade de saída** para os resultados da predición.

7. Unha lista de opcións completada previamente amosará onde pode asignar os valores a unha categoría prevista. Neste caso, as súas únicas opcións de categoría serán 0 ou 1 xa que se corresponden coa natureza real/falso ou binaria da predición. Na columna Categoría, asigne os valores de campo que desexa clasificar como "0" na predición final en "0" e os elementos que desexa clasificar como "1" na predición final en "1".
   > [!div class="mx-imgBorder"]
   > ![Exemplo que mostra os valores de campo asignados a categorías.](media/intelligence-categorymapping.png "Exemplo que mostra os valores de campo asignados a categorías")

8. Seleccione **Feito** e a predición procesarase. O procesamento levará algún tempo, dependendo do tamaño e complexidade dos datos. Os resultados estarán dispoñibles nunha nova entidade en función do **Nome da entidade de saída** da predición que creou.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="create-a-prediction-while-creating-a-segment"></a>Crear unha predición mentres se crea un segmento

Predicir os valores que faltan para un atributo específico elixido tamén é posible cando se crea un segmento. En concreto, cando crea rapidamente un segmento baseado na entidade de cliente unificada ou na entidade Customer_Measure.

Como parte deste fluxo, vostede elixe un atributo específico no que basear o seu segmento, por exemplo, a satisfacción do cliente ou o importe de compra. Despois da creación dun segmento, o sistema suxerirá un método para prever todos os valores que faltan para este atributo.

1. Ir a **Segmentos** e selecciona o **Perfís** tella.

2. Elixa un **Campo** no que crear un segmento, seleccione un **Operador** e logo seleccione **Revisar**.

3. Proporcione un **Nome** e un **Nome para mostrar** para o segmento.

4. Seleccione **Gardar**.

5. Se o segmento que acaba de crear ten datos incompletos no campo de orixe, pode optar por predicir os valores que faltan.
   > [!div class="mx-imgBorder"]
   > ![Botón de predición.](media/segments-predictoption.png "Botón de predición")

6. Proporcione un **Nome para mostrar** e un **Nome da entidade de saída** para os resultados da predición.

7. Seleccione **Feito**. A súa predición xerarase en breve e estará dispoñible nunha nova entidade co nome que indicou para o **Nome da entidade de saída**.

## <a name="view-a-prediction"></a>Ver unha predición

1. Ir a **Intelixencia** > **Predicións** > **As miñas predicións**.

2. Seleccione a predición que desexa revisar.

3. Seleccione os tres puntos na columna **Accións** e escolla **Ver**.

4. Verá varios puntos de datos na vista da súa predición.
   > [!div class="mx-imgBorder"]
   > ![Páxina de predicións.](media/intelligence-predictionsviewpage.png "Páxina de predicións")

   - **Valores preditos** mostra a asignación creada durante a fase de asignación do valor do campo coa categoría. Estes son os valores do seu conxunto de datos que foron asignados a unha categoría específica.
   -**Principais elementos con maior influencia** son os factores dentro do seu conxunto de datos que probablemente influíran na confianza da predición de que o seu valor de campo sexa atribuído a unha categoría específica.
   - **Desempeño** indica como se están a facer as predicións. Seleccione a ligazón para obter máis información.
   - **Vista previa** mostra exemplos do conxunto de datos de saída da súa predición e a probabilidade, ou a nosa confianza, do valor predito onde 0 é pouco probable e 1 é seguro.

## <a name="update-a-prediction"></a>Actualizar unha predición

1. Ir a **Intelixencia** > **Predicións** > **As miñas predicións**.

2. Seleccione a predición que desexa actualizar e seleccione a icona **Actualizar**.

3. A predición programarase para o procesamento. Pode ver a hora na que se actualizou por última vez na columna **Actualizado** da páxina **Predicións**.

## <a name="edit-a-prediction"></a>Editar unha predición

Despois de crear un predición, podes personalizar o modelo no AI Builder para aumentar a eficacia do seu modelo.  

1. Ir a **Intelixencia** > **Predicións** > **As miñas predicións**.

2. Seleccione a predición que desexa editar.

3. Seleccione os tres puntos na columna **Accións** e escolla **Ver**.

4. Seleccione **Personalizar en AI Builder**.

5. Actualiza o teu modelo no AI Builder. [Obteña máis información sobre como xestionar modelos en AI builder](/ai-builder/manage-model#retrain-and-republish-existing-models).

A seguinte execución da súa predición usará o modelo actualizado que creou.

> [!NOTE]
> Novos modelos creados en AI Builder non se mostrará en Customer Insights a menos que o modelo fose creado a partir das experiencias enumeradas anteriormente.

## <a name="remove-a-prediction"></a>Eliminar unha predición

1. Ir a **Intelixencia** > **Predicións** > **As miñas predicións**.

2. Seleccione a predición que desexe eliminar.

3. Seleccione os tres puntos na columna **Accións** e escolla **Eliminar**.

4. Confirme a eliminación.

## <a name="troubleshooting"></a>Resolución de problemas

Se non pode completar o proceso de anexar Dataverse debido a un erro, poderá tentar completar o proceso manualmente. Existen dous problemas coñecidos que poden ocorrer no proceso de anexar:

- A solución de complemento de tarxeta de cliente non está instalada.
    1. Complete as instrucións para [instalar e configurar a solución](customer-card-add-in.md).

- Non se conceden permisos de aplicacións.
    1. Vaia a [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).
    1. Seleccione **Contornos**.
    1. Seleccione os tres puntos situados xunto ao contorno ao que desexa engadir o permiso e seleccione **Configuración**.
    1. Amplíe **Usuarios + permisos** e seleccione **Usuarios**.
    1. Seleccione **+ Novo** e seleccione **Usuario**.
    1. Seleccione **Usuario da aplicación** se non está seleccionado e introduza a seguinte información:
        - **Nome do usuario:** cihelp@microsoft.com
        - **ID da aplicación:** 38c77d00-5fcb-4cce-9d93-af4738258e3c
        - **Nome:** cliente
        - **Apelido:** información
        - **Correo electrónico principal:** cihelp@microsoft.com
    1. Seleccione **Gardar e pechar**.
    1. Seleccione o usuario que acaba de crear.
    1. Seleccione **Xestionar funcións** na barra do menú superior.
    1. Seleccione **Administrador do sistema** e logo seleccione **Aceptar**.


[!INCLUDE [footer-include](includes/footer-banner.md)]
