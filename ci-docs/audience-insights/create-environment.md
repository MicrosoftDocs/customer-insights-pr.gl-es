---
title: Crear contornos en Customer Insights
description: Pasos para crear ambientes cunha subscrición con licenza para Dynamics 365 Customer Insights.
ms.date: 02/24/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: c37afd5649f8cf40d5379f3d39d0cbd96cde3bd3
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 02/25/2022
ms.locfileid: "8354093"
---
# <a name="create-an-environment-in-audience-insights"></a>Crear un ambiente na información do público

Este artigo explica como crear un novo ambiente despois de que a súa organización compre unha subscrición de Dynamics 365 Customer Insights. 

As organizacións poden crear *dous* contornos para cada licenza de Customer Insights. Se a súa organización compra máis dunha licenza, [póñase en contacto co noso equipo de asistencia](https://go.microsoft.com/fwlink/?linkid=2079641) para aumentar o número de contornos dispoñibles. Para obter máis información sobre a capacidade e a capacidade do complemento, descargue a [Guía de Licenzas de Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

> [!NOTE]
> Se busca probar o servizo, consulte [Configurar un ambiente de proba](../trial-signup.md).

## <a name="create-a-new-environment"></a>Crear un novo ambiente

Despois de comprar unha licenza de subscrición para Customer Insights, o administrador global do Microsoft 365 o inquilino recibe un correo electrónico que o invita a crear o ambiente. Vaia a [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start) para comezar. 

Unha experiencia guiada axúdalle nos pasos para recompilar toda a información necesaria para un novo contorno. Precisa [permisos de administrador](permissions.md) en información do público para crear ou xestionar ambientes.

1. Nas estatísticas de audiencia, abra o selector de contornos e seleccione **+ Novo**.
  
   :::image type="content" source="../engagement-insights/media/environment-picker.png" alt-text="Seleccione o selector de ambientes.":::

1. Siga a experiencia guiada descrita nas seguintes seccións.

### <a name="step-1-provide-environment-information"></a>Paso 1: proporcionar información sobre o contorno

No paso **Información básica**, escolla se desexa crear un ambiente desde cero ou [copiar datos doutro contorno](manage-environments.md#copy-the-environment-configuration).

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Diálogo para crear un novo ambiente de Customer Insights.":::

Indique os seguintes detalles:
   - **Nome**: O nome deste ambiente. Este campo xa está cuberto se copiou un ambiente existente, pero pode cambialo.
   - **Elixa o seu negocio**: elixa o público principal para o novo contorno. Pode traballar con consumidores individuais (B-a-C) ou [contas empresariais](work-with-business-accounts.md) (B-a-B).
   - **Tipo**: seleccione se desexa crear un ambiente de produción ou de illamento de procesos. Os ambientes de illamento de procesos non permiten a actualización de datos programada e están destinados á implantación previa e ás probas. Os contornos de illamento de procesos usan o mesmo público principal que o ambiente de produción seleccionado actualmente.
   - **Rexión**: a rexión na que se despregou e aloxou o servizo.

### <a name="step-2-configure-data-storage"></a>Paso 2: configurar o almacenamento de datos

No paso **Almacenamento de datos**, elixa onde gardar os datos das estatísticas do público.

Terá dúas opcións: **Almacenamento de Customer Insights** (un Azure Data Lake xestionado polo equipo de Customer Insights) e **Azure Data Lake Storage** (o seu propio Azure Data Lake Storage). Por defecto, a opción de almacenamento de Customer Insights está seleccionada.

:::image type="content" source="media/data-storage-environment.png" alt-text="Escolla o Azure Data Lake Storage nos que almacenar os datos de información de audiencia.":::

Gardando datos en Azure Data Lake Storage, acepta que os datos serán transferidos e almacenados na situación xeográfica correspondente para esa conta de almacenamento de Azure. Esta situación pode diferir de onde se almacenan os datos en Dynamics 365 Customer Insights. Obteña máis información no [Centro de confianza de Microsoft](https://www.microsoft.com/trust-center).

> [!NOTE]
> Customer Insights actualmente admite o seguinte:
> - Entidades inxeridas de fluxos de datos de Power BI que se almacenan nun Data Lake xestionado por Microsoft Dataverse.  
> - As contas de Azure Data Lake Storage da mesma rexión de Azure que seleccionou ao crear o ambiente.
> - Azure Data Lake Storage contas que son Gen2 e teñen *espazo de nomes xerárquico* activado. Non se admiten as contas de almacenamento de Azure Data Lake Gen1.

Para a opción Azure Data Lake Storage, pode escoller entre unha opción baseada en recursos e unha opción baseada na subscrición para a autenticación. Para obter máis información, consulte [Conectar cunha conta de Azure Data Lake Storage mediante unha entidade de servizo de Azure](connect-service-principal.md). O nome **Envase** será `customerinsights` e non se pode cambiar.

Cando se completan os procesos do sistema, como a inxestión de datos, o sistema crea os cartafoles correspondentes na conta de almacenamento que especificou. Os ficheiros de datos e os ficheiros *model.json* créanse e engádense aos cartafoles en función do nome do proceso.

Se crea varios contornos de Customer Insights e elixe gardar as entidades de saída deses ambientes na súa conta de almacenamento, Customer Insights crea cartafoles separados para cada ambiente con `ci_environmentID` no recipiente.

### <a name="step-3-connect-to-microsoft-dataverse"></a>Paso 3: Conectar con Microsoft Dataverse
   
O paso **Microsoft Dataverse** permítelle conectar Customer Insights co seu ambiente de Dataverse.

Proporciona o teu propio Microsoft Dataverse ambiente para compartir datos (perfís e coñecementos) con aplicacións empresariais baseadas Dataverse, como Dynamics 365 Marketing ou aplicacións baseadas en modelos en Power Apps. Deixa este campo baleiro se non tes o teu Dataverse medio ambiente e proporcionaremos un para ti.

Conectando ao teu Dataverse ambiente tamén che permite [inxerir datos de fontes de datos local usando Power Platform fluxos de datos e pasarelas](data-sources.md#add-data-from-on-premises-data-sources). Tamén podes usar [modelos prefabricados predición](predictions-overview.md?tabs=b2c#out-of-box-models) ao conectarse a a Dataverse ambiente.

> [!IMPORTANT]
> Información do cliente e Dataverse deben estar na mesma rexión para poder compartir datos.

:::image type="content" source="media/dataverse-provisioning.png" alt-text="compartición de datos con Microsoft Dataverse habilitado automaticamente para novas instancias netas.":::

> [!NOTE]
> Customer Insights non é compatible cos seguintes escenarios de uso compartido dos datos:
> - Se garda todos os seus datos no seu Azure Data Lake Storage, non poderá activar o uso compartido de datos cun lago de datos xestionado por Dataverse.
> - Se activa o uso compartido de datos con Dataverse, non poderá [crear valores preditos ou que faltan nunha entidade](predictions.md).

### <a name="step-4-finalize-the-settings"></a>Paso 4: Finalizar a configuración

No paso **Revisión**, percorra todas as opcións especificadas. Cando todo pareza completo, seleccione **Crear** para configurar o ambiente. 

Tamén pode cambiar a maioría das opcións máis tarde. Para obter máis información, consulte [Xestionar ambientes](manage-environments.md).

## <a name="work-with-your-new-environment"></a>Traballar co seu novo ambiente

Revise os seguintes artigos para axudarlle a comezar a configurar Customer Insights: 

- [Engadir máis usuarios e atribuír permisos](permissions.md).
- [Inxerir as orixes de datos](data-sources.md) e executalas mediante o [proceso de unificación de datos](data-unification.md) para obter [perfís de clientes unificados](customer-profiles.md).
- [Enriquecer os perfís de clientes unificados](enrichment-hub.md) ou [executar modelos preditivos](predictions-overview.md).
- [Cree segmentos](segments.md) para agrupar clientes e [medidas](measures.md) para revisar os KPI.
- [Configurar conexións](connections.md) e [exportacións](export-destinations.md) para procesar subconxuntos de datos noutras aplicacións.
