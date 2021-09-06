---
title: Crear e configurar unha proba de Customer Insights
description: Pasos para obter unha subscrición de proba para Dynamics 365 Customer Insights e configurala.
ms.date: 07/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: f038dedd369ac9e623146b66528efa87c47a8c23769037d8709fa9b804a0b723
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035413"
---
# <a name="set-up-a-trial-environment"></a>Configurar un ambiente de proba 

Unha proba de Dynamics 365 Customer Insights permítelle revisar a capacidade clave e obter máis información sobre as distintas funcións. Unha subscrición de proba elimínase despois de caducar. Os ambientes de proba son creados por usuarios individuais que se converten en administradores do seu ambiente de proba. Poden invitar a máis usuarios á súa proba e configurar as distintas funcións.

## <a name="create-a-trial-environment"></a>Crear un ambiente de proba

Pode rexistrarse para unha proba na [páxina de rexistro de proba](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights). 

1. Escolla a opción **Rexistrarse para unha proba gratuíta** e seleccione **Rexistrarse agora**.

1. Proporcione o seu enderezo de correo electrónico laboral ou escolar, cóntenos máis sobre vostede e seleccione **Comezar**.

   :::image type="content" source="media/trial-signup-dialog.png" alt-text="Digálogo para inscribirse para unha instancia gratuíta":::

1. Revise os termos e condicións e seleccione **Continuar** para confirmar.

1. Indique un **Nome** para o seu novo ambiente. 

1. Estableza o **Tipo** de ambiente como **Proba**.

1. No campo **Seleccionar unha demostración de sector**, opcionalmente pode escoller un conxunto de datos específico do sector. Tamén pode [cambiar a unha demostración de sector](#use-industry-specific-demo-data-sets-in-audience-insights) máis tarde e comezar co conxunto de datos predefinido.

1. Escolla a **Rexión** para o seu ambiente.

1. Opcionalmente, se é o administrador dunha organización de Dynamics 365: seleccione **Configuración avanzada** e proporcione o URL da súa organización para empregar funcións de predición, como a predición de renovación do cliente. 

1. Seleccione **Crear**. 

A configuración do ambiente tarda uns minutos en completarse. Unha vez completada, será redirixido ao ambiente de demostración ou á demostración do sector que escolla no paso anterior. Agora pode explorar a aplicación con datos de demostración só de lectura. Para engadir os seus propios datos ao ambiente, consulte [Crear datos de demostración específicos do escenario no seu propio ambiente](#create-scenario-specific-demo-data-in-your-own-environment).

:::image type="content" source="media/trial-environment.png" alt-text="Captura de pantalla dun ambiente de proba creado recentemente.":::

## <a name="use-industry-specific-demo-data-sets-in-audience-insights"></a>Usar conxuntos de datos de demostración específicos do sector na información do público

A conexión de orixes de datos reais é un dos pasos críticos no uso da eficacia de Customer Insights. Para probar funcións sen interferir cos seus propios datos, pode usar datos de demostración específicos do sector. Hai un par de conxuntos de datos de demostración dispoñibles para os seguintes sectores: 

-   Automoción
-   Banca
-   Bens de consumo
-   Administración pública
-   Saúde
-   Hostalería
-   Empresa aseguradora
-   Fabricación
-   Servizos profesionais
-   Venda polo miúdo

### <a name="see-industry-specific-demo-data-in-trials"></a>Ver datos de demostración específicos do sector nas probas

Para unha versión só de lectura de Customer Insights, adaptada a un sector ou escenario específico, comece no ambiente de demostración. 
 
1.  Na información do público, escolla o ambiente de **demostración** no selector de ambientes.

2.  En **Inicio**, escolla unha opción no menú despregable Seleccionar unha demostración de sector.

:::image type="content" source="media/trial-select-industry-demo.png" alt-text="Escoller un sector para o ambiente de proba.":::

### <a name="create-scenario-specific-demo-data-in-your-own-environment"></a>Crear datos de demostración específicos do escenario no seu propio ambiente

Como administrador, seleccione o selector de ambientes na cabeceira da aplicación para crear un novo ambiente. No novo ambiente, pode configurar as súas propias orixes de datos e configurar a aplicación segundo os seus requisitos. 

1.  Na información do público, vaia a **Datos** > **Orixes de datos**.

2.  Para importar as súas propias orixes de datos, vaia á [guía sobre a inxestión de datos](data-sources.md).     
   Se prefire traballar con datos de mostra que lle permitan probar a inxestión de datos, pode inxerir os datos de demostración do sector no seu ambiente. Escolla a opción **Importar da plataforma común de datos** e siga os pasos seguintes.

3.  Seleccione o cartón de industria que se adapte ao seu escenario. 

4.  Revise e actualice opcionalmente o nome suxerido da orixe de datos. 

5.  Selecciona **Seguinte** para inxerir os datos de mostra. 

Agora pode usar os datos inxeridos para adaptar Customer Insights ao seu escenario. Para ver un ambiente específico para os datos de demostración inxeridos, escolla a opción **Demostración de <Industry>** no selector de ambientes.

## <a name="limitations-in-trials"></a>Limitacións nas probas

- As probas están activas durante 30 días por defecto. Non obstante, pode amplialas despois do día 23 ao iniciar sesión na proba.
- Non pode usar a súa propia conta de Azure Data Lake Storage para almacenar datos de saída durante unha proba. Non obstante, pode inxerir datos dunha conta de Azure Data Lake Storage.
- Pode almacenar ata 3 GB de datos no ambiente de Dataverse que se fornece automaticamente ao iniciar unha proba de Customer Insights.

## <a name="copy-data-from-a-trial-to-a-paid-subscription"></a>Copiar datos dunha subscrición de proba a unha de pago

Xeralmente, recomendamos comezar de novo cos seus propios datos ao actualizar á versión de pago de Customer Insights. 

Opcionalmente, pode copiar os seus datos desde un ambiente de proba se compra Customer Insights. Debe ser o administrador da proba de Customer Insights e o administrador global do seu arrendatario de Microsoft 365 ou o administrador de Dynamics 365 da súa organización para migrar a configuración dun ambiente de proba a un ambiente de pago. 

Despois de iniciar sesión na súa instancia de pago de Customer Insights por primeira vez, solicítaselle que cree un novo ambiente. Neste proceso, pode optar por copiar a configuración desde un ambiente existente e migrar a maioría das opcións de configuración. Se ten os permisos mencionados anteriormente, o ambiente de proba mostrarase nesta lista. Para obter máis información, consulte [Copiar a configuración dun ambiente](manage-environments.md#copy-the-environment-configuration).

## <a name="next-steps"></a>Pasos seguintes

Revise os seguintes artigos para axudalo a comezar a configurar Customer Insights. 

- [Engadir máis usuarios e atribuír permisos](permissions.md).
- [Inxerir as orixes de datos](data-sources.md) e executalas mediante o [proceso de unificación de datos](data-unification.md) para obter [perfís de clientes unificados](customer-profiles.md).
- [Enriquecer os perfís de clientes unificados](enrichment-hub.md) ou [executar modelos preditivos](predictions-overview.md).
- Crear [segmentos](segments.md) para agrupar clientes e [medidas](measures.md) para revisar os KPI.
- Configurar [conexións](connections.md) e [exportacións](export-destinations.md) para procesar subconxuntos de datos noutras aplicacións.