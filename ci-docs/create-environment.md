---
title: Como - Crear un novo ambiente
description: Pasos para crear ambientes con for Dynamics 365 Customer Insights.
ms.date: 05/31/2022
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
ms.openlocfilehash: 795eaa3598257f5188070f6ea02d04e4423b66eb
ms.sourcegitcommit: f5af5613afd9c3f2f0695e2d62d225f0b504f033
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 06/01/2022
ms.locfileid: "8833556"
---
# <a name="how-to-create-a-new-environment"></a>Como: Crear un novo ambiente

Despois [comprar unha licenza de subscrición para Dynamics 365 Customer Insights](paid-license.md), o administrador global do Microsoft 365 o inquilino recibe un correo electrónico que o invita a crear o ambiente. Vaia a [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start) para comezar. Neste escenario, podes ir directamente a [Paso 1: proporcionar información básica](#step-1-provide-basic-information).

Despois de crear o primeiro ambiente, o administrador global do Microsoft 365 inquilino pode [engadir usuarios da súa organización como administradores](permissions.md). En adiante, estes administradores poderán xestionar usuarios e ambientes. Se a súa organización compra máis dunha licenza para Customer Insights, [póñase en contacto co noso equipo de soporte](https://go.microsoft.com/fwlink/?linkid=2079641) para aumentar o número de ambientes dispoñibles. Para obter máis información sobre a capacidade e a capacidade complementaria, consulte a páxina [Guía de licenzas de Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

> [!TIP]
> Se busca probar o servizo, consulte [Configurar un ambiente de proba](trial-signup.md).

## <a name="prerequisites"></a>Requisitos previos

Precisas [permisos de administrador](permissions.md) en Customer Insights para crear ou xestionar ambientes.

## <a name="start-the-environment-creation-process"></a>Iniciar o proceso de creación do entorno

1. Abre o selector de ambiente e selecciona **+ Novo**.
  
   :::image type="content" source="media/environment-picker.png" alt-text="Seleccione o selector de ambientes.":::

1. Siga a experiencia guiada descrita nas seguintes seccións para proporcionar toda a información necesaria para un novo ambiente. Se configuraches un ambiente antes, tamén podes [copiar a configuración](#copy-the-environment-configuration).

## <a name="step-1-provide-basic-information"></a>Paso 1: proporcionar información básica

No paso **Información básica**, escolla se desexa crear un ambiente desde cero ou [copiar datos doutro contorno](#copy-the-environment-configuration).

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Diálogo para crear un novo ambiente de Customer Insights.":::

Indique os seguintes detalles:

- **Nome**: O nome deste ambiente. Este campo xa está cuberto se copiou un ambiente existente, pero pode cambialo.
- **Elixa o seu negocio**: elixa o público principal para o novo contorno. Pode traballar con consumidores individuais (B-a-C) ou [contas empresariais](work-with-business-accounts.md) (B-a-B). Se a túa organización fai negocios principalmente con persoas, como un venda polo miúdo ou unha cafetería, elixe consumidores individuais. No caso de que o teu público principal sexan outras empresas, como un fabricante de automóbiles ou unha empresa de papel, elixe contas empresariais.
- **Tipo**: seleccione se desexa crear un ambiente de produción ou de illamento de procesos. Os ambientes de illamento de procesos non permiten a actualización de datos programada e están destinados á implantación previa e ás probas. Os contornos de illamento de procesos usan o mesmo público principal que o ambiente de produción seleccionado actualmente.
- **Rexión**: a rexión na que se despregou e aloxou o servizo. Para [usa o teu propio Azure Data Lake Storage conta](own-data-lake-storage.md) ou [conectarse a un existente Microsoft Dataverse organización](customer-insights-dataverse.md), o ambiente de Customer Insights debe estar na mesma rexión.

## <a name="step-2-configure-data-storage"></a>Paso 2: configurar o almacenamento de datos

No **Almacenamento de datos** paso, escolla onde almacenar os datos de Customer Insights.

Hai dúas opcións nas que podes escoller:

- **Almacenamento de datos de clientes** : O equipo de Customer Insights xestiona o almacenamento de datos. É a opción predeterminada e, a menos que existan requisitos específicos para almacenar datos na túa propia conta de almacenamento, recomendámosche que utilices esta opción.
- **Azure Data Lake Storage**: Especifique o seu Azure Data Lake Storage para almacenar os datos para que teña control total onde se almacenan os datos. Para obter máis información, consulte [Usa o teu propio Azure Data Lake Storage conta](own-data-lake-storage.md).

:::image type="content" source="media/data-storage-environment.png" alt-text="Escolla a opción preferida para almacenar os seus datos.":::

## <a name="step-3-connect-to-microsoft-dataverse"></a>Paso 3: Conectar con Microsoft Dataverse

O paso **Microsoft Dataverse** permítelle conectar Customer Insights co seu ambiente de Dataverse. Comparte datos con Dataverse para usalo con aplicacións empresariais baseadas en Dataverse, como Dynamics 365 Marketing ou aplicacións baseadas en modelos Power Apps.

Deixa este campo baleiro se non tes o teu Dataverse ambiente e crearemos un para ti.

Para obter máis información, consulte [Traballa cos datos de Customer Insights en Microsoft Dataverse](customer-insights-dataverse.md).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="compartición de datos con Microsoft Dataverse habilitado automaticamente para novos entornos nets.":::

### <a name="step-4-finalize-the-settings"></a>Paso 4: Finalizar a configuración

No **Revisión** paso, pasa por todas as opcións especificadas. Cando todo pareza completo, seleccione **Crear** para configurar o ambiente.

Podes cambiar algunhas das opcións máis tarde. Para obter máis información, consulte [Xestionar ambientes](manage-environments.md).

## <a name="work-with-your-new-environment"></a>Traballar co seu novo ambiente

Revise os seguintes artigos para axudarlle a comezar a configurar Customer Insights:

- [Engadir máis usuarios e atribuír permisos](permissions.md).
- [Inxerir as orixes de datos](data-sources.md) e executalas mediante o [proceso de unificación de datos](data-unification.md) para obter [perfís de clientes unificados](customer-profiles.md).
- [Enriquecer os perfís de clientes unificados](enrichment-hub.md) ou [executar modelos preditivos](predictions-overview.md).
- [Cree segmentos](segments.md) para agrupar clientes e [medidas](measures.md) para revisar os KPI.
- [Configurar conexións](connections.md) e [exportacións](export-destinations.md) para procesar subconxuntos de datos noutras aplicacións.

## <a name="copy-the-environment-configuration"></a>Copiar a configuración dun ambiente

Como administrador, pode escoller copiar a configuración dun ambiente existente cando cree un novo.

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Captura de pantalla das opcións de configuración na configuración do ambiente.":::

Verá unha lista de todos os ambientes dispoñibles da súa organización de onde pode copiar datos.

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

## <a name="set-up-a-copied-environment"></a>Configura un ambiente copiado

Cando copies a configuración do ambiente, tes que seguir algúns pasos adicionais para confirmar as credenciais:

- Perfís de clientes. En primeiro lugar, autentica e inxerir as túas fontes de datos e executa a unificación de datos para recrear os perfís de clientes.
- Credenciais da orixe de datos. Ten que proporcionar as credenciais para cada orixe de datos para autenticar e actualizar as fontes de datos manualmente.
- Fontes de datos do cartafol Common Data Model e Dataverse. Ten que crear esas fontes de datos manualmente co mesmo nome que no contorno de orixe.
- Segredos de conexión que se utilizan para exportacións e enriquecementos. Ten que reautenticar as conexións e despois reactivar os enriquecementos e as exportacións.

Verá unha mensaxe de confirmación cando se crea o ambiente copiado. Seleccione **Ir a orixes de datos** para ver a lista de orixes de datos.

Todas as orixes de datos mostrarán o estado **Credenciais requiridas**. Edite as orixes de datos e insira as credenciais para actualizalas.

:::image type="content" source="media/data-sources-copied.png" alt-text="Lista de orixes de datos que se copiaron e precisan autenticación.":::

Despois de actualizar as orixes de datos, diríxase a **Datos** > **Unificar**. Aquí atopará a configuración do ambiente de orixe. Edíteos segundo sexa necesario ou seleccione **Executar** para iniciar o proceso de unificación de datos e crear a entidade de cliente unificada.

Cando a unificación de datos estea completa, diríxase a **Medidas** e **Segmentos** para actualizalos tamén.

Antes de reactivar as exportacións e os enriquecementos, vai a **Admin** > **Conexións** para volver a autenticar as conexións no seu novo entorno.

[!INCLUDE [footer-include](includes/footer-banner.md)]
