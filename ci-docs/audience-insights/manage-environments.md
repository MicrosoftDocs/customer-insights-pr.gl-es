---
title: Crear e xestionar ambientes
description: Aprenda a rexistrarse no servizo e a xestionar contornos.
ms.date: 02/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: nimagen
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 744f0bcbf5d2700363180f44e38d6dee9bf5df63
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270110"
---
# <a name="manage-environments"></a>Xestionar ambientes

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Este artigo explica como crear unha nova organización e como fornecer un ambiente.

## <a name="sign-up-and-create-an-organization"></a>Rexistrarse e crear unha organización

1. Vaia ao sitio web [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/).

2. Seleccione **Comezar**.

3. Escolla o escenario de rexistro preferido e seleccione a ligazón correspondente.

4. Acepte os termos e condicións e seleccione **Continuar** para comezar a crear a organización.

5. Despois de crear o ambiente, redirixiráselle a [Customer Insights](https://home.ci.ai.dynamics.com).

6. Use o contorno de demostración para explorar a aplicación ou crear un novo contorno seguindo os pasos da seguinte sección.

7. Despois de especificar a configuración do ambiente, seleccione **Crear**.

8. Iniciará sesión despois de que o ambiente se cree correctamente.

## <a name="create-an-environment-in-an-existing-organization"></a>Crear un ambiente nunha organización existente

Existen dúas formas de crear un ambiente novo. Pode especificar unha configuración completamente nova ou pode copiar algúns axustes de configuración dun ambiente existente.

Para crear un ambiente:

1. Seleccione o selector de **ambiente** na cabeceira da aplicación.

1. Seleccione **Nova**.

   > [!div class="mx-imgBorder"]
   > ![Configuración de ambientes](media/environment-settings-dialog.png)

1. No diálogo **Crear novo ambiente**, seleccione **Novo ambiente**.

   Se quere [copiar datos do ambiente actual](#additional-considerations-for-copy-configuration-preview), seleccione **Copiar do ambiente existente**. Verá unha lista de todos os ambientes dispoñibles da súa organización de onde pode copiar datos.

1. Indique os seguintes detalles:
   - **Nome**: O nome deste ambiente. Este campo xa está cuberto se copiou un ambiente existente, pero pode cambialo.
   - **Rexión**: a rexión na que se despregou e aloxou o servizo.
   - **Tipo**: selecciona se desexa crear un contorno de produción ou de illamento de procesos.

2. Opcionalmente, pode seleccionar **Configuración avanzada**:

   - **Gardar todos os datos en**: especifique onde desexa almacenar os datos de saída xerados de Customer Insights. Terá dúas opcións: **Almacenamento de Customer Insights** (un Azure Data Lake xestionado polo equipo de Customer Insights) e **Azure Data Lake Storage Gen2** (o seu propio Azure Data Lake Storage). Por defecto, a opción de almacenamento de Customer Insights está seleccionada.

   > [!NOTE]
   > Ao gardar datos en Azure Data Lake Storage, acepta que os datos se transfiran e almacenen na localización xeográfica adecuada para esa conta de Azure Storage, que pode ser diferente á da conta na que están almacenados os datos en Dynamics 365 Customer Insights. [Obteña máis información no Centro de confianza de Microsoft.](https://www.microsoft.com/trust-center)
   >
   > Na actualidade, as entidades inxeridas sempre se almacenan no lago de datos xestionado por Customer Insights.
   > Só admitimos contas de almacenamento de Azure Data Lake Gen2 da mesma rexión de Azure que seleccionou ao crear o ambiente.
   > Só admitimos contas de almacenamento de Azure Data Lake Gen2 compatibles co Espazo de nomes xerárquicos (HNS).

   - Para a opción de Azure Data Lake Storage Gen2, pode escoller entre unha opción baseada en recursos e unha opción baseada na subscrición para a autenticación. Para obter máis información, consulte [Conectar información do público a unha conta de Azure Data Lake Storage Gen2 cunha entidade principal de seguranza do servizo de Azure](connect-service-principal.md). O nome do **contedor** non se pode cambiar e será "customerinsights".
   
   - Se quere usar [predicións](predictions.md) ou configurar o intercambio de datos con aplicacións e solucións baseadas en Microsoft Dataverse, forneza o URL do ambiente de Microsoft Dataverse en **Configurar o uso compartido de datos con Microsoft Dataverse e habilitar capacidades adicionais**. Seleccione **Activar o uso compartido de datos** para compartir os datos de saída de Customer Insights cun Data Lake xestionado de Microsoft Dataverse.

     > [!NOTE]
     > - Compartir datos cun Data Lake xestionado Microsoft Dataverse actualmente non é compatible cando garda todos os datos no seu propio Azure Data Lake Storage.
     > - A [predición de valores que faltan nunha entidade](predictions.md) non se admite actualmente cando habilita o uso compartido de datos cun Data Lake xestionado de Microsoft Dataverse.

     > [!div class="mx-imgBorder"]
     > ![Opcións de configuración para habilitar o uso compartido de datos con Microsoft Dataverse](media/Datasharing-with-DataverseMDL.png)

   Cando execute procesos, como a inxestión de datos ou a creación de segmentos, crearanse os cartafoles correspondentes na conta de almacenamento que especificou anteriormente. Os ficheiros de datos e os ficheiros model.json crearanse e engadiranse aos respectivos subcartafoles en función do proceso que execute.

   Se crea varios contornos de Customer Insights e elixe gardar as entidades de saída deses ambientes na súa conta de almacenamento, crearanse cartafoles separados para cada contorno con ci_<environmentid> no contedor.

### <a name="additional-considerations-for-copy-configuration-preview"></a>Consideracións adicionais para a configuración da copia (previsualización)

Copiaranse os seguintes axustes de configuración:

- Configuracións de funcións
- Fontes de datos inxeridas ou importadas
- Configuración da unificación de datos (mapa, coincidencia, combinación)
- Segmentos
- Medidas
- Relacións
- Actividades
- Buscar e filtrar índice
- Exportar destinos
- Actualización programada
- Enriquecementos
- Xestión de modelos
- Atribución de roles

*Non* se copiarán os seguintes axustes:

- Perfís de clientes.
- Credenciais da orixe de datos. Deberá proporcionar as credenciais para cada orixe de datos e actualizar as fontes de datos manualmente.
- Fontes de datos do cartafol Common Data Model e lago xestionado por Common Data Service. Terá que crear esas orixes de datos manualmente co mesmo nome que no ambiente de orixe.

Cando copie un ambiente, verá unha mensaxe de confirmación de que se creou o novo contorno. Seleccione **Ir a orixes de datos** para ver a lista de orixes de datos.

Todas as orixes de datos mostrarán o estado **Credenciais requiridas**. Edite as orixes de datos e insira as credenciais para actualizalas.

> [!div class="mx-imgBorder"]
> ![Orixes de datos copiadas](media/data-sources-copied.png)

Despois de actualizar as orixes de datos, diríxase a **Datos** > **Unificar**. Aquí atopará a configuración do ambiente de orixe. Edíteos segundo sexa necesario ou seleccione **Executar** para iniciar o proceso de unificación de datos e crear a entidade de cliente unificada.

Cando a unificación de datos estea completa, diríxase a **Medidas** e **Segmentos** para actualizalos tamén.

## <a name="edit-an-existing-environment"></a>Editar un ambiente existente

Pode editar algúns detalles dos contornos existentes.

1.  Seleccione o selector de **ambiente** na cabeceira da aplicación.

2.  Seleccione a icona de **edición**.

3. Na caixa **Editar contorno**, pode actualizar o **Nome de visualización** do contorno, pero non pode cambiar a **Rexión** nin o **Tipo**.

4. Se un ambiente está configurado para almacenar datos en Azure Data Lake Storage Gen2, pode actualizar a **Clave da conta**. Non obstante, non podes cambiar o **Nome da conta** nin o nome do **Contedor**.

5. Opcionalmente, pode actualizar desde unha conexión baseada na clave de conta a unha conexión baseada en recursos ou baseada nunha subscrición. Unha vez actualizado, non poderá volver á clave da conta despois da actualización. Para obter máis información, consulte [Conectar información do público a unha conta de Azure Data Lake Storage Gen2 cunha entidade principal de seguranza do servizo de Azure](connect-service-principal.md). Non pode cambiar a información do **contedor** ao actualizar a conexión.

## <a name="reset-an-existing-environment"></a>Restablecer ambiente existente

Como administrador, pode restablecer un ambiente a un estado baleiro se quere eliminar todas as configuracións e eliminar os datos inxeridos.

1.  Seleccione o selector de **ambiente** na cabeceira da aplicación. 

2.  Seleccione o ambiente que desexa restablecer e seleccione os puntos suspensivos **...**. 

3. Escolla a opción **Restablecer**. 

4.  Para confirmar a eliminación, introduza o nome do contorno e seleccione **Restablecer**.

## <a name="delete-an-existing-environment-available-only-for-admins"></a>Eliminar un ambiente existente (dispoñible só para administradores)

Como administrador, pode eliminar un ambiente que administra.

1.  Seleccione o selector de **ambiente** na cabeceira da aplicación.

2.  Seleccione o ambiente que desexa restablecer e seleccione os puntos suspensivos **...**. 

3. Escolla a opción **Eliminar**. 

4.  Para confirmar a eliminación, insira o nome do ambiente e seleccione **Eliminar**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]