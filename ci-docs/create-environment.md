---
title: Crear contornos en Customer Insights
description: Pasos para crear ambientes cunha subscrición con licenza para Dynamics 365 Customer Insights.
ms.date: 04/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: c64ac94a7e0e743d3c13e32e394cc5d409420622
ms.sourcegitcommit: c00441bc60b978e25f930b06c9d97b46fe462538
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 05/05/2022
ms.locfileid: "8712900"
---
# <a name="create-an-environment-in-customer-insights"></a>Crea un ambiente en Customer Insights

Este artigo explica como crear un novo ambiente despois de que a súa organización compre unha subscrición de Dynamics 365 Customer Insights. 

As organizacións poden crear varios ambientes para cada licenza de Customer Insights. Se a súa organización compra máis dunha licenza, [póñase en contacto co noso equipo de asistencia](https://go.microsoft.com/fwlink/?linkid=2079641) para aumentar o número de contornos dispoñibles. Para obter máis información sobre a capacidade e a capacidade complementaria, consulte a páxina [Guía de licenzas de Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

> [!NOTE]
> Se busca probar o servizo, consulte [Configurar un ambiente de proba](trial-signup.md).

## <a name="create-a-new-environment"></a>Crear un novo ambiente

Despois de comprar unha licenza de subscrición para Customer Insights, o administrador global do Microsoft 365 o inquilino recibe un correo electrónico que o invita a crear o ambiente. Vaia a [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start) para comezar. 

Unha experiencia guiada axúdalle nos pasos para recompilar toda a información necesaria para un novo contorno. Precisas [permisos de administrador](permissions.md) en Customer Insights para crear ou xestionar ambientes.

1. Abre o selector de ambiente e selecciona **+ Novo**.
  
   :::image type="content" source="media/environment-picker.png" alt-text="Seleccione o selector de ambientes.":::

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

No **Almacenamento de datos** paso, escolla onde almacenar os datos de Customer Insights.

Terá dúas opcións: **Almacenamento de Customer Insights** (un Azure Data Lake xestionado polo equipo de Customer Insights) e **Azure Data Lake Storage** (o seu propio Azure Data Lake Storage). Por defecto, a opción de almacenamento de Customer Insights está seleccionada.

:::image type="content" source="media/data-storage-environment.png" alt-text="Escolle o Azure Data Lake Storage para almacenar os seus datos.":::

Gardando datos en Azure Data Lake Storage, acepta que os datos serán transferidos e almacenados na situación xeográfica correspondente para esa conta de almacenamento de Azure. Esta situación pode diferir de onde se almacenan os datos en Dynamics 365 Customer Insights. Obteña máis información no [Centro de confianza de Microsoft](https://www.microsoft.com/trust-center).

> [!NOTE]
> Customer Insights actualmente admite o seguinte:  
> - As contas de Azure Data Lake Storage da mesma rexión de Azure que seleccionou ao crear o ambiente.
> - Azure Data Lake Storage contas que son Gen2 e teñen *espazo de nomes xerárquico* activado. Non se admiten as contas de almacenamento de Azure Data Lake Gen1.

Para a opción Azure Data Lake Storage, pode escoller entre unha opción baseada en recursos e unha opción baseada na subscrición para a autenticación. Para obter máis información, consulte [Conectar cunha conta de Azure Data Lake Storage mediante unha entidade de servizo de Azure](connect-service-principal.md). Un recipiente chamado`customerinsights` ten que existir na conta de almacenamento.

Cando se completan os procesos do sistema, como a inxestión de datos, o sistema crea os cartafoles correspondentes na conta de almacenamento que especificou. Os ficheiros de datos e os ficheiros *model.json* créanse e engádense aos cartafoles en función do nome do proceso.

Se crea varios contornos de Customer Insights e elixe gardar as entidades de saída deses ambientes na súa conta de almacenamento, Customer Insights crea cartafoles separados para cada ambiente con `ci_environmentID` no recipiente.

### <a name="step-3-connect-to-microsoft-dataverse"></a>Paso 3: Conectar con Microsoft Dataverse
   
O paso **Microsoft Dataverse** permítelle conectar Customer Insights co seu ambiente de Dataverse.

Proporciona o teu propio Microsoft Dataverse ambiente para compartir datos (perfís e coñecementos) con aplicacións empresariais baseadas Dataverse, como Dynamics 365 Marketing ou aplicacións baseadas en modelos Power Apps. Deixa este campo baleiro se non tes o teu Dataverse medio ambiente e proporcionaremos un para ti.

Conectando ao teu Dataverse ambiente tamén che permite [inxerir datos de fontes de datos local usando Power Platform fluxos de datos e pasarelas](data-sources.md#add-data-from-on-premises-data-sources).

> [!IMPORTANT]
> 1. Información do cliente e Dataverse deben estar na mesma rexión para poder compartir datos.
> 1. Debes ter un rol de administrador global no Dataverse ambiente. Comproba se isto [Dataverse ambiente está asociado](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) a determinados grupos de seguranza e asegúrese de que se engade a eses grupos de seguranza.
> 1. Xa non hai ningún ambiente de Customer Insights asociado con iso Dataverse ambiente. Aprende como [eliminar unha conexión existente a a Dataverse ambiente](manage-environments.md#remove-an-existing-connection-to-a-dataverse-environment).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="compartición de datos con Microsoft Dataverse habilitado automaticamente para novas instancias netas.":::

Para obter máis información sobre como activar o uso compartido de datos con Microsoft Dataverse do teu propio Azure Data Lake Storage, Ver [Conectar a Microsoft Dataverse](manage-environments.md#connect-to-microsoft-dataverse).

Customer Insights non é compatible cos seguintes escenarios de uso compartido dos datos:
- Se activa o uso compartido de datos con Dataverse, non poderá [crear valores preditos ou que faltan nunha entidade](predictions.md).

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