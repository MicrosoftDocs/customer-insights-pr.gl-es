---
title: Informes de funil
description: Como usar informes de funil para comprender a forma na que o publico toma decisións.
ms.reviewer: mhart
ms.author: kamacdon
author: kamacdon
ms.date: 09/21/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: efb10f2664630a5851d9582ff09c378c01777b96
ms.sourcegitcommit: f1e3cc51ea4cf68210eaf0210ad6e14b15ac4fe8
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 09/27/2021
ms.locfileid: "7558918"
---
# <a name="create-and-manage-funnel-reports"></a>Crear e xestionar informes de funil

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Un informe de funil recolle información sobre os pasos que se producen durante unha viaxe do cliente a través do seu sitio web ou aplicación móbil. Axúdalle a comprender como avanza un público a través dun proceso e identifica os puntos de entrega. Por exemplo, pode usar un informe de funil para identificar os camiños que seguen os seus clientes antes de facer unha compra. Un informe de funil ofrece datos para informar sobre as decisións e identificar as áreas de optimización e mellora de procesos.

## <a name="create-a-funnel-report"></a>Crear un informe de funil

Para crear o informe de funil, especifique os pasos que quere incluír e a actividade de cada paso. Unha actividade é un [evento](glossary.md) que representa o comportamento dun usuario. O informe de funil mostra o número de usuarios que completaron cada paso definido. 

1. Vaia a **Funís** e seleccione **+Novo funil** para iniciar un informe de funil.

1. No **Editor de funís**, en **Pasos** seleccione **+Engadir paso**. 

1. Introduza un nome en **Título do paso**.

   :::image type="content" source="media/new-funnel-report.png" alt-text="Novo informe de funil.":::

1. Seleccione unha **Actividade**. Unha actividade rexistra cando un usuario ve unha páxina (actividade de **visualización**) ou interactúa co contido (actividade de **acción**).

1. Use **Criterios do paso** para especificar a dimensión da actividade. As [dimensións](dimensions.md) son atributos que poden describir, filtrar ou agrupar datos.

1. Opcionalmente, pode configurar os pasos do funil con varias condicións. Seleccione **Engadir condición** para especificar máis dimensións nun paso. Os criterios adicionais deben empregar o mesmo tipo de actividade. Podes escoller se hai varias condicións conectadas cun operador E ou OU.

   :::image type="content" source="media/funnel-add-condition.png" alt-text="Editor de funil que mostra a configuración de pasos con pasos de varias condicións.":::

1. Seleccione **Engadir paso** ata completar todos os pasos que quere no informe.

1. Seleccione **Gardar**, nomee o informe e volva a **Gardar**. 

### <a name="example-fourth-coffee-company-funnel-report"></a>Exemplo: informe de funil da empresa Fourth Coffee

O seguinte escenario mostra unha forma de usar un informe de funil. Un analista da empresa Fourth Coffee quere comprender a influencia dunha promoción recente nas taxas de subscrición. O analista crea un informe de funil para identificar a actividade dos clientes. Comeza cando os clientes chegan á páxina de inicio da empresa e continúa até que utilizan o código de promoción de subscrición. A analista crea un informe de funil cos seguintes pasos:

Paso 1: Clientes que chegan á páxina de inicio   
Paso 2: Clientes que fan unha compra   
Paso 3: Clientes que usan o código de promoción para obter un desconto nunha subscrición   
Paso 4: Rexistro da subscrición   

:::image type="content" source="media/funnel-report-example.png" alt-text="exemplo de informe de funil.":::
  
Este funil permítelle ver o número de usuarios que empregaron o código de promoción despois dunha compra única para rexistrarse no programa de subscrición.

### <a name="configure-advanced-settings"></a>Configurar opcións avanzadas 

Os informes de funil permiten definir un límite no tempo que leva completar un funil. Por exemplo, pode configurar o tempo para completar o funil en catro días. Esta configuración só contará os rexistros correctos das subscricións que se producisen nos catro días seguintes a que un usuario visitase a páxina de inicio.

1. Vaia a **Funís** para abrir a **Biblioteca de funís**.

1. Seleccione un nome para abrir o informe. 

1. No panel **Editor de funil**, seleccione **Configuración avanzada**. 

1. Estableza Limitar tempo de finalización do funil en **Activado**.

   :::image type="content" source="media/funnel-limit-time.png" alt-text="Editor de funil que mostra unha configuración e opcións avanzadas para limitar o tempo para completar un funil.":::

1. Escolla o tempo no que debe completar o funil na lista despregable **Establecer límite en**.

1. Seleccione **Gardar** para aplicar as modificacións.


## <a name="cross-channel-funnel-reports"></a>Informes de funil entre canles 

A información de interacción tamén pode recompilar datos de comportamento dos clientes na súa aplicación móbil. Unha vez que instrumentou a súa aplicación móbil co [SDK de Android](get-started-android.md) ou o [SDK de iOS](get-started-ios.md) de información de interacción, pode crear informes de funil entre canles. 

### <a name="create-a-cross-channel-funnel-report"></a>Crear un informe de funil entre canles 

1. Siga os pasos para [crear un informe de funil](#create-a-funnel-report).    

1. Para controlar como os seus clientes interactúan coa súa marca tanto na súa páxina web como na aplicación móbil ou en varios sitios web, use o conmutador de espazo de traballo para crear pasos de funil con datos doutros espazos de traballo. No **Editor de funil**, baixo **Pasos** seleccione de que espazo de traballo proceden os datos do seu paso de funil.

## <a name="manage-funnel-reports"></a>Xestionar informes de funil

Pode revisar os informes de funil para analizar datos, rastrexar o rendemento e recompilar información.

> [!NOTE]
> - Os informes de funil de información de interacción actualmente admiten escenarios nos que todos os usuarios do funil son anónimos ou están autenticados. 
> - Os datos históricos dos informes de funil están dispoñibles para os últimos 30 días.

### <a name="view-funnel-reports"></a>Ver informes de funil

1. Vaia a **Funís** para abrir a **Biblioteca de funís**.
1. Seleccione un nome para abrir o informe.    

### <a name="see-the-data-collected-for-a-report"></a>Ver os datos recompilados para un informe   

Para ver información sobre unha fase:

- Sinale un paso no informe.

:::image type="content" source="media/funnel-step-data.png" alt-text="datos do funil.":::

### <a name="change-the-date-range-for-the-funnel-report"></a>Cambie o intervalo de datas para o informe de funil

1. Vaia a **Funís** para abrir a **Biblioteca de funís**.

1. Seleccione un nome para abrir o informe.

1. Abra o **intervalo temporal** e seleccione un novo período de tempo da lista ou **Intervalo de datas fixo** para especificar un intervalo de datas.

## <a name="edit-or-delete-funnel-reports"></a>Editar ou eliminar informes de funil

Pode cambiar o nome dun informe de funil, eliminalo ou modificar os pasos que inclúe.

### <a name="rename-or-delete-a-funnel-report"></a>Renomear ou eliminar un informe de funil

1. Vaia a **Funís** para abrir a **Biblioteca de funís**. 

1. Seleccione **Máis** xunto ao informe que quere modificar e escolla **Editar nome** ou **Eliminar**.

### <a name="edit-a-funnel-step"></a>Editar un paso dun funil  

1. Vaia a **Funís** para abrir a **Biblioteca de funís**. 

1. Seleccione un nome para abrir o informe.

1. Seleccione o paso que quere editar.

1. Seleccione **Editar**.

1. No **Editor de funís**, actualice a información que quere modificar.  

1. Seleccione **Gardar**.

### <a name="reorder-a-funnel-step"></a>Reordenar un paso dun funil

1. Vaia a **Funís** para abrir a **Biblioteca de funís**. 

1. Seleccione un nome para abrir o informe.

1. Seleccione o paso que quere reordenar.

1. Seleccione **Mover** e logo **Arriba**, **Abaixo**, **Até arriba** ou **Até abaixo** para mover o paso.

### <a name="delete-a-funnel-step"></a>Eliminar un paso dun funil

1. Vaia a **Funís** para abrir a **Biblioteca de funís**. 

1. Seleccione un nome para abrir o informe.

1. Seleccione o paso que quere eliminar e seleccione **Eliminar**.

## <a name="funnel-insights"></a>Estatísticas de funil 

As estatísticas de participación agora ofrecen información de funil para os clientes. Utilice información sobre o funil para obter unha visión máis profunda do comportamento do cliente sobre os pasos do informe do funil. Cando crea e garda un novo informe de funil, xéranse automaticamente información sobre o funil para o seu informe. 

:::image type="content" source="media/funnel-insights.png" alt-text="Estatísticas de funil.":::

> [!NOTE]
> As estatísticas de funil só se poden xerar para pasos de funil que **non** inclúe dimensións personalizadas. Para xerar estatísticas de funil para todos os pasos do seu funil, use dimensións listas para usar de estatísticas de compromiso para crear os pasos do funil. 

Pode ver as estatísticas do funil das seguintes categorías, tanto no nivel principal como no de paso: 

 - Taxa de conversión
 -    A taxa de conversión entre Finalización de compra e Compra é do 22%.
 - Tempo de transición 
 -    O tempo medio de transición entre o Carro da compra e a Finalización da compra é de 23 minutos. 
 - Hora de finalización 
 -    A cantidade de tempo media que tardan os clientes en finalizar o funil é de 47 minutos. 

Utilice esta información para explorar máis o comportamento dos clientes e comprender mellor os puntos de entrega e as conversións do seu informe de funil. 

Para comparar estatísticas en diferentes pasos, seleccione **Ver a división en pasos** ou **Comparar con outros pasos** desde as tarxetas de información. Amosarán un gráfico de barras que compara as métricas de cada paso do funil. 

As estatísticas do funil recalcúlanse cada 24 horas ou cando **Garda** o seu informe de funil. 

> [!NOTE]
> Para ver información sobre o funil, debe gardar o informe cada vez que faga cambios. 

