---
title: Páxina de inicio en estatísticas do público
description: Comece a explorar a aplicación na páxina de inicio.
ms.date: 09/30/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: bd16966eabb126d9c9945ededc53273df02c3369
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405723"
---
# <a name="create-a-new-environment"></a>Crear un novo ambiente

## <a name="create-a-trial-environment"></a>Crear un ambiente de proba

Pode rexistrarse para unha proba na [páxina de rexistro de proba](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights). 

> [!NOTE]
> As probas caducan aos 30 días.

1. Escolla a opción **Rexistrarse para unha proba gratuíta** e seleccione **Rexistrarse agora**.

1. Indique o se enderezo de correo electrónico laboral ou escolar, cóntenos máis sobre vostede e seleccione **Seguinte**.

1. Indique un **Nome** para o seu novo ambiente. 

1. Seleccione o tipo de ambiente.

1. Escolla a **Rexión** para o seu ambiente.

1. Opcionalmente, para administradores dunha organización de Dynamics 365: Seleccione **Configuración avanzada** e proporcione o URL da súa organización para usar funcionalidades de predición como o abandono de clientes.

1. Seleccione **Crear**. 

Despois de crear o ambiente, verá o ambiente de **Demostración** que lle permite explorar a aplicación con datos ficticios. Pode cambiar os datos de exemplo para que coincidan co seu sector. Seleccione a icona de **Configuración** na cabeceira e seleccione **Configuración de demostración**. Ademais, pode cambiar o tema visual. 

[Cambie ao ambiente](#change-between-environments) que creou durante o proceso de rexistro para traballar cos seus propios datos.

## <a name="create-a-new-production-or-sandbox-environment"></a>Cree un novo ambiente de produción ou de illamento de procesos

No seu ambiente, seleccione a icona de **Configuración** na cabeceira e seleccione **Novo ambiente**.

Siga os pasos coma se [crease un ambiente de proba](#create-a-trial-environment). Obtén unha opción adicional ao seleccionar **Configuración avanzada** para almacenar os seus datos no seu propio Azure Data Lake. Indique o nome da súa conta e a clave da conta para establecer unha conexión co Azure Data Lake. Por defecto, os datos almacénanse no lago de datos xestionado por Customer Insights.

> [!IMPORTANT]
> Ao gardar datos no seu Azure Data Lake Storage, acepta que os datos se transfiran e almacenen na localización xeográfica adecuada para esa conta de almacenamento de Azure, que pode ser diferente á da conta na que están almacenados os datos en Dynamics 365 Customer Insights. [Obteña máis información no Centro de confianza de Microsoft.](https://www.microsoft.com/trust-center)

## <a name="explore-the-home-page"></a>Explorar a páxina de inicio

Pode [acceder ao seu entorno de Customer Insights](https://home.ci.ai.dynamics.com/) no seguinte URL: [https://home.ci.ai.dynamics.com/](https://home.ci.ai.dynamics.com/).
A páxina de **Inicio** mostra unha visión xeral da súa base de clientes e métricas clave para rastrexar o estado do seu negocio.

> [!div class="mx-imgBorder"] 
> ![Información na páxina de inicio](media/home-page-insights.png "Información na páxina de inicio")

En **Segmentos recentes**, verá grupos de clientes baseados en atributos demográficos, de comportamento ou transaccionais que definiu. [Creación de segmentos](segments.md) axúdao a orientar mellor as súas actividades empresariais.

**Medidas recentes** mostra mosaicos con [medidas](measures.md). As medidas son indicadores clave de rendemento (KPIs) que definiu. Por exemplo, a probabilidade media de desvío de clientes ou o gasto medio en liña por cliente.

A sección **Enriquecementos recentes** enumera os resultados das execucións de enriquecemento que se completaron recentemente. Os enriquecementos engaden información sobre a súa base de clientes. Por exemplo, entendendo os intereses e as marcas polas que teñen afinidade. Esta información pódese desbloquear utilizando as capacidades de [enriquecemento](enrichment-microsoft-graph.md) despois de completar as fases [mapa](map-entities.md), [coincidencia](match-entities.md) e [combinación](merge-entities.md).

## <a name="change-between-environments"></a>Cambio entre ambientes

Unha vez configuradas as [orixes de datos](data-sources.md), poderá pasar dun contorno de demostración a un ambiente en directo. O uso do ambiente de produción permítelle traballar cos seus propios datos de clientes. Seleccione o control **Ambiente** na esquina superior dereita da páxina para cambiar ambientes.

> [!div class="mx-imgBorder"] 
> ![Mudar ambiente](media/home-page-environment-switcher.png "Mudar ambiente")

Os administradores poden crear e xestionar [múltiples contornos](manage-environments.md). O mantemento de máis dun ambiente pode ser útil se, por exemplo, a súa organización opera internacionalmente e precisa segregar datos e información de diferentes xeitos.

## <a name="next-step"></a>Seguinte paso

Para ver as súas propias informacións na páxina de inicio, primeiro terá que [engadir orixes de datos](data-sources.md) e [unificar](data-unification.md) os seus datos para crear perfís de clientes.
