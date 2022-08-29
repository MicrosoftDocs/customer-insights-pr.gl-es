---
title: Crear un novo ambiente
description: Pasos para crear ambientes en Dynamics 365 Customer Insights.
ms.date: 08/15/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: 0a45e2fd2bdb7b85883a536f8b42ee650e54db7e
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304241"
---
# <a name="create-a-new-environment"></a>Crear un novo ambiente

Despois [comprar unha licenza de subscrición para Dynamics 365 Customer Insights](paid-license.md), o administrador global do Microsoft 365 o inquilino recibe un correo electrónico que o invita a crear o ambiente. Vaia a [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start) para comezar. Neste escenario, comeza con [Paso 1: proporcionar información básica](#step-1-provide-basic-information).

Despois de crear o primeiro ambiente, o administrador global do Microsoft 365 inquilino pode [engadir usuarios da súa organización como administradores](permissions.md). Estes administradores poden xestionar usuarios e ambientes. Se a súa organización compra máis dunha licenza para Customer Insights, [póñase en contacto co noso equipo de soporte](https://go.microsoft.com/fwlink/?linkid=2079641) para aumentar o número de ambientes dispoñibles. Para obter máis información sobre a capacidade e a capacidade complementaria, consulte a páxina [Guía de licenzas de Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544). Unha vez que teñas a posibilidade de crear ambientes adicionais, vai a [Iniciar o proceso de creación do entorno](#start-the-environment-creation-process).

> [!TIP]
> Se busca probar o servizo, consulte [Configurar un ambiente de proba](trial-signup.md).

## <a name="prerequisites"></a>Requisitos previos

[Permisos de administrador](permissions.md) en Customer Insights

## <a name="start-the-environment-creation-process"></a>Iniciar o proceso de creación do entorno

1. Abre o selector de ambiente e selecciona **+ Novo**.
  
   :::image type="content" source="media/environment-picker.png" alt-text="Seleccione o selector de ambientes.":::

1. Siga a experiencia guiada descrita nas seguintes seccións para proporcionar toda a información necesaria para un novo ambiente.

## <a name="step-1-provide-basic-information"></a>Paso 1: proporcionar información básica

1. Escolla se quere crear un ambiente desde cero ou copiar datos doutro ambiente. [Copiando datos doutro entorno](#copy-the-environment-configuration) require pasos adicionais.

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Diálogo para crear un novo ambiente de Customer Insights.":::

1. Indique os seguintes detalles:

   - **Nome** : Nome para este ambiente. Este campo xa está cuberto se copiou un ambiente existente, pero pode cambialo.
   - **Elixe o teu negocio** : Público principal para o novo entorno: consumidores individuais (B-to-C) ou [contas empresariais](work-with-business-accounts.md) (B-a-B). Se a túa organización fai negocios principalmente con persoas, como un venda polo miúdo ou unha cafetería, elixe consumidores individuais. Se o teu público principal son outras empresas, como un fabricante de automóbiles ou unha empresa de papel, elixe contas comerciais.
   - **Tipo** : Tipo de ambiente: produción ou sandbox. Os ambientes de illamento de procesos non permiten a actualización de datos programada e están destinados á implantación previa e ás probas. Os contornos de illamento de procesos usan o mesmo público principal que o ambiente de produción seleccionado actualmente.
   - **Rexión** : Rexión na que está implantado e aloxado o servizo. Para [usa o teu propio Azure Data Lake Storage conta](own-data-lake-storage.md) ou [conectarse a un existente Microsoft Dataverse organización](customer-insights-dataverse.md), o ambiente de Customer Insights debe estar na mesma rexión.

1. Seleccione **Seguinte**.

## <a name="step-2-configure-data-storage"></a>Paso 2: configurar o almacenamento de datos

1. Escolle onde almacenar os datos de Customer Insights:

   - **Almacenamento de datos de clientes** : o almacenamento de datos xestionase automaticamente. É a opción predeterminada e, a menos que existan requisitos específicos para almacenar datos na túa propia conta de almacenamento, recomendámosche usar esta opción.
   - **Azure Data Lake Storage**: Ti mesmo Azure Data Lake Storage para almacenar os datos para que teña control total onde se almacenan os datos. Siga os pasos en [Usa o teu propio Azure Data Lake Storage conta](own-data-lake-storage.md).

   :::image type="content" source="media/data-storage-environment.png" alt-text="Escolla a opción preferida para almacenar os seus datos.":::

1. Seleccione **Seguinte**.

## <a name="step-3-connect-to-microsoft-dataverse"></a>Paso 3: Conectar con Microsoft Dataverse

Se tes un Dataverse entorno, conecte Customer Insights. Comparte datos con Dataverse para usalo con aplicacións empresariais baseadas en Dataverse, como Dynamics 365 Marketing ou aplicacións baseadas en modelos Power Apps.

1. Siga os pasos en [Traballa cos datos de Customer Insights en Microsoft Dataverse](customer-insights-dataverse.md).

   :::image type="content" source="media/dataverse-provisioning.png" alt-text="compartición de datos con Microsoft Dataverse activado automaticamente para novos entornos nets.":::

1. Seleccione **Seguinte**.

## <a name="step-4-finalize-the-settings"></a>Paso 4: Finalizar a configuración

Revise a configuración especificada. Cando todo pareza completo, seleccione **Crear** para configurar o ambiente.

Para cambiar algunhas das opcións máis tarde, consulte [Xestionar ambientes](manage-environments.md).

## <a name="work-with-your-new-environment"></a>Traballar co seu novo ambiente

Revise os seguintes artigos para axudarlle a comezar a configurar Customer Insights:

- [Engadir máis usuarios e atribuír permisos](permissions.md).
- [Inxerir as orixes de datos](data-sources.md) e executalas mediante o [proceso de unificación de datos](data-unification.md) para obter [perfís de clientes unificados](customer-profiles.md).
- [Enriquecer os perfís de clientes unificados](enrichment-hub.md) ou [executar modelos preditivos](predictions-overview.md).
- [Cree segmentos](segments.md) para agrupar clientes e [medidas](measures.md) para revisar os KPI.
- [Configurar conexións](connections.md) e [exportacións](export-destinations.md) para procesar subconxuntos de datos noutras aplicacións.

## <a name="copy-the-environment-configuration"></a>Copiar a configuración dun ambiente

Como administrador, se escolleu copiar a configuración dun ambiente existente, seleccione na lista de todos os ambientes dispoñibles na súa organización.

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Captura de pantalla das opcións de configuración na configuración do ambiente.":::

Copiaranse os seguintes axustes de configuración:

- Fontes de datos importadas mediante Power Query
- Configuración de unificación de datos
- Segmentos
- Medidas
- Relacións
- Actividades
- Buscar e filtrar índice
- Exportacións
- Programación de actualizacións
- Enriquecementos
- Modelos predición
- Atribución de roles

### <a name="set-up-a-copied-environment"></a>Configura un ambiente copiado

Cando copia a configuración do ambiente, aparece unha mensaxe de confirmación cando se creou o ambiente copiado. Siga os seguintes pasos para confirmar as credenciais.

1. Seleccione **Ir a orixes de datos** para ver a lista de orixes de datos. Mostran todas as fontes de datos **Requírese credenciais** estado.

   :::image type="content" source="media/data-sources-copied.png" alt-text="Lista de orixes de datos que se copiaron e precisan autenticación.":::

1. Edite as orixes de datos e insira as credenciais para actualizalas. Fontes de datos do cartafol Common Data Model e Dataverse debe crearse manualmente co mesmo nome que no contorno de orixe.

1. Despois de actualizar as orixes de datos, diríxase a **Datos** > **Unificar**. Aquí atopará a configuración do ambiente de orixe. Edítaos segundo sexa necesario ou selecciónaos **Unificar** > **Unifica os perfís e as dependencias dos clientes** para iniciar o proceso de unificación de datos e crear a entidade cliente unificada.

   > [!TIP]
   > Para contas e contactos, seleccione **Unificar contas** > **Unificar perfís e dependencias**.

1. Cando se complete a unificación de datos, vai a **Medidas** e **Segmentos** para refrescalos.

1. Ir a **Admin** > **Conexións** para volver a autenticar as conexións no seu novo entorno.

1. Ir a **Datos** > **Enriquecemento** e **Datos** > **Exportacións** para reactivalos.

[!INCLUDE [footer-include](includes/footer-banner.md)]
