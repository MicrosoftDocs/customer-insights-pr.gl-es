---
title: Páxina de inicio en estatísticas do público
description: Comece a explorar a aplicación na páxina de inicio.
ms.date: 01/07/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: bf9080c564850bca0c239b7317eed2fc0f77d9f3
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597233"
---
# <a name="create-a-new-environment"></a>Crear un novo ambiente

## <a name="create-a-trial-environment"></a>Crear un ambiente de proba

Pode rexistrarse para unha proba na [páxina de rexistro de proba](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights). 

> [!NOTE]
> As probas caducan aos 30 días.

1. Escolla a opción **Rexistrarse para unha proba gratuíta** e seleccione **Rexistrarse agora**.

1. Indique o se enderezo de correo electrónico laboral ou escolar, cóntenos máis sobre vostede e seleccione **Seguinte**.

   :::image type="content" source="media/trial-signup-dialog.png" alt-text="Digálogo para inscribirse para unha instancia gratuíta":::

1. Indique un **Nome** para o seu novo ambiente. 

1. Seleccione o tipo de ambiente.

1. Escolla a **Rexión** para o seu ambiente.

1. Opcionalmente, para administradores dunha organización de Dynamics 365: Seleccione **Configuración avanzada** e proporcione o URL da súa organización para usar funcionalidades de predición como o abandono de clientes.

1. Seleccione **Crear**. 

Despois de crear o ambiente, verá o ambiente de **Demostración** que lle permite explorar a aplicación con datos ficticios. Pode cambiar os datos de exemplo para que coincidan co seu sector. Seleccione a icona de **Configuración** na cabeceira e seleccione **Configuración de demostración**. Ademais, pode cambiar o tema visual. 

[Cambie ao ambiente](#switch-environments) que creou durante o proceso de rexistro para traballar cos seus propios datos.

## <a name="create-a-new-production-or-sandbox-environment"></a>Cree un novo ambiente de produción ou de illamento de procesos

No seu contorno, seleccione o selector de **Ambientes** na cabeceira da aplicación e seleccione **Novo**.

Siga os pasos coma se [crease un ambiente de proba](#create-a-trial-environment). Por defecto, os datos almacénanse no lago de datos xestionado por Customer Insights. Obtén unha opción adicional ao seleccionar **Configuración avanzada** para almacenar os seus datos no seu propio Azure Data Lake. Indique o nome da súa conta e a clave da conta para establecer unha conexión co Azure Data Lake. 

> [!IMPORTANT]
> Ao gardar datos no seu Azure Data Lake Storage, acepta que os datos se transfiran e almacenen na localización xeográfica adecuada para esa conta de almacenamento de Azure, que pode ser diferente á da conta na que están almacenados os datos en Dynamics 365 Customer Insights. [Obteña máis información no Centro de confianza de Microsoft.](https://www.microsoft.com/trust-center)

## <a name="explore-the-home-page"></a>Explorar a páxina de inicio

Pode [acceder á información do público desde Dynamics 365 Customer Insights](https://home.ci.ai.dynamics.com/) no seguinte URL: [https://home.ci.ai.dynamics.com/](https://home.ci.ai.dynamics.com/).
A páxina de **Inicio** mostra unha visión xeral dos segmentos, as medidas e os datos de enriquecemento (se está configurado) despois de completar as fases de [asignación](map-entities.md), [busca de coincidencias](match-entities.md) e [combinación](merge-entities.md).

> [!div class="mx-imgBorder"] 
> ![Información na páxina de inicio](media/home-page-insights.png "Información na páxina de inicio")

En **Segmentos recentes**, verá grupos de clientes baseados en atributos demográficos, de comportamento ou transaccionais que definiu. A [creación de segmentos](segments.md) axúdalle a agrupar a súa base de clientes e orientar mellor as súas actividades comerciais.

As **medidas recentes** mostran os mosaicos cos [indicadores clave de rendemento (KPI)](measures.md) que definiu. Por exemplo, a probabilidade media dun cliente de abandonar ou o gasto medio en liña por cliente.

A sección **Enriquecementos recentes** enumera os resultados das execucións de enriquecemento que se completaron recentemente. Os [enriquecementos](enrichment-hub.md) engaden información sobre a súa base de clientes. Por exemplo, entendendo os intereses e as marcas polas que teñen afinidade.

## <a name="switch-environments"></a>Cambiar ambientes

Seleccione o control **Ambiente** na esquina superior dereita da páxina para cambiar ambientes.

> [!div class="mx-imgBorder"] 
> ![Mudar ambiente](media/home-page-environment-switcher.png "Mudar ambiente")

Os administradores poden crear e xestionar [múltiples contornos](manage-environments.md). O mantemento de máis dun ambiente pode ser útil se, por exemplo, a súa organización opera internacionalmente e precisa segregar datos e información de diferentes xeitos.

## <a name="next-step"></a>Seguinte paso

Para ver as súas propias informacións na páxina de inicio, primeiro terá que [engadir orixes de datos](data-sources.md) e [unificar](data-unification.md) os seus datos para crear perfís de clientes.


[!INCLUDE[footer-include](../includes/footer-banner.md)]