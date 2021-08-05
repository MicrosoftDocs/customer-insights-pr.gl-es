---
title: Crear e configurar unha licenza de pago de Customer Insights
description: Pasos para obter unha subscrición con licenza para Dynamics 365 Customer Insights e configurala.
ms.date: 07/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: f8cf1be97ee8af46145a450009fd278b1821f8fe
ms.sourcegitcommit: 5c9c54ffe045017c19f0042437ada2c101dcaa0f
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 07/22/2021
ms.locfileid: "6650468"
---
# <a name="get-started-with-a-paid-subscription"></a>Introdución á subscrición de pago

Este artigo explica como crear un novo ambiente despois de que a súa organización compre unha subscrición de Dynamics 365 Customer Insights. Se desexa mercar Customer Insights, as nosas opcións de contacto aparecen na [páxina web de Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/). 

Se busca probar o servizo e as funcións, consulte [Configurar un ambiente de proba](get-started-trial.md).

## <a name="create-an-environment-in-an-existing-organization"></a>Crear un ambiente nunha organización existente

Despois de mercar unha licenza de subscrición para Customer Insights, o administrador global do arrendatario de Microsoft 365 recibe un correo electrónico que o invita a crear o ambiente. Vaia a [https://home.ci.dynamics.com/start](https://home.ci.dynamics.com/start) para comezar. 

Customer Insights non ten licenzas por usuario, polo que non se amosarán na área de Licenzas. Se busca a licenza no centro de administración de Microsoft 365, vaia a **Os seus produtos**. 

> [!NOTE]
> As organizacións poden crear *dous* contornos para cada licenza de Customer Insights. Se a súa organización compra máis dunha vez unha licenza, por favor [póñase en contacto co noso equipo de asistencia](https://go.microsoft.com/fwlink/?linkid=2079641) para aumentar o número de contornos dispoñibles. Para obter máis información sobre a capacidade e a capacidade do complemento, descargue a [Guía de Licenzas de Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

Para crear un ambiente:

1. No diálogo **Crear un ambiente**, seleccione **Novo ambiente**.

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Diálogo para crear un novo ambiente de Customer Insights.":::

   Recomendamos comezar a configurar un ambiente desde cero. Non obstante, se é administrador ou membro dun ambiente de proba, podería [copiar datos doutro ambiente](manage-environments.md#copy-the-environment-configuration) escollendo **Copiar desde un ambiente existente**. Verá unha lista de todos os ambientes dispoñibles da súa organización de onde pode copiar datos.

1. Indique os seguintes detalles:
   - **Nome**: O nome deste ambiente. Este campo xa está cuberto se copiou un ambiente existente, pero pode cambialo.
   - **Rexión**: a rexión na que se despregou e aloxou o servizo.
   - **Tipo**: seleccione se desexa crear un ambiente de produción ou de illamento de procesos. Os ambientes de illamento de procesos non permiten a actualización de datos programada e están destinados á implantación previa e ás probas.
   
1. Opcionalmente, pode seleccionar **Configuración avanzada**:

   - **Gardar todos os datos en**: especifique onde desexa almacenar os datos de saída xerados de Customer Insights. Terá dúas opcións: **Almacenamento de Customer Insights** (un Azure Data Lake xestionado polo equipo de Customer Insights) e **Azure Data Lake Storage** (o seu propio Azure Data Lake Storage). Por defecto, a opción de almacenamento de Customer Insights está seleccionada.

     > [!NOTE]
     > Ao gardar datos en Azure Data Lake Storage, acepta que os datos se transfiran e almacenen na localización xeográfica adecuada para esa conta de Azure Storage, que pode ser diferente á da conta na que están almacenados os datos en Dynamics 365 Customer Insights. [Obteña máis información no Centro de confianza de Microsoft.](https://www.microsoft.com/trust-center)
     >
     > Na actualidade, as entidades inxeridas desde os fluxos de datos de Power BI sempre se almacenan en Data Lake xestionado por Microsoft Dataverse. 
     > 
     > Só admitios contas de Azure Data Lake Storage da mesma rexión de Azure que seleccionou ao crear o ambiente. 
     > 
     > Só admitimos contas de Azure Data Lake Storage que teñan activado o espazo de nomes xerárquico.


   - Para a opción Azure Data Lake Storage, pode escoller entre unha opción baseada en recursos e unha opción baseada na subscrición para a autenticación. Para obter máis información, consulte [Conectar información do público a unha conta de Azure Data Lake Storage Gen2 cunha entidade principal de seguranza do servizo de Azure](connect-service-principal.md). O nome do **Contedor** non se pode cambiar e será `customerinsights`.
   
   - Se quere utilizar [modelos listos para usar](predictions-overview.md#out-of-box-models), configure o uso compartido de datos con Microsoft Dataverse ou active a inxestión de datos desde orixes de datos locais, proporcione o URL do ambiente de Microsoft Dataverse en **Configurar o uso compartido de datos con Microsoft Dataverse e activar funcionalidades adicionais**. Seleccione **Activar o uso compartido de datos** para compartir os datos de saída de Customer Insights cun Data Lake xestionado de Microsoft Dataverse.

     > [!NOTE]
     > - Compartir datos cun Data Lake xestionado Microsoft Dataverse actualmente non é compatible cando garda todos os datos no seu propio Azure Data Lake Storage.
     > - A [predición de valores que faltan nunha entidade](predictions.md) actualmente non se admite cando habilita o uso compartido de datos cun Data Lake xestionado de Microsoft Dataverse.

     :::image type="content" source="media/Datasharing-with-DataverseMDL.png" alt-text="Opcións de configuración para habilitar o uso compartido de datos con Microsoft Dataverse.":::

   Cando se completan os procesos do sistema como a inxestión de datos, o sistema crea os cartafoles correspondentes na conta de almacenamento que especificou. Os ficheiros de datos e os ficheiros model.json créanse e engádense aos cartafoles en función do nome do proceso.

   Se crea varios contornos de Customer Insights e elixe gardar as entidades de saída deses ambientes na súa conta de almacenamento, crearanse cartafoles separados para cada contorno con ci_<environmentid> no contedor.

1. Seleccione **Crear** para configurar o ambiente. 

## <a name="configure-an-environment"></a>Configurar un ambiente

Revise os seguintes artigos para axudalo a comezar a configurar Customer Insights. 

- [Engadir máis usuarios e atribuír permisos](permissions.md).
- [Inxerir as orixes de datos](data-sources.md) e executalas mediante o [proceso de unificación de datos](data-unification.md) para obter [perfís de clientes unificados](customer-profiles.md).
- [Enriquecer os perfís de clientes unificados](enrichment-hub.md) ou [executar modelos preditivos](predictions-overview.md).
- Crear [segmentos](segments.md) para agrupar clientes e [medidas](measures.md) para revisar os KPI.
- Configurar [conexións](connections.md) e [exportacións](export-destinations.md) para procesar subconxuntos de datos noutras aplicacións.
