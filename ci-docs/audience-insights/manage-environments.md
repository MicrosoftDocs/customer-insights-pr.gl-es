---
title: Crear e xestionar ambientes
description: Aprenda a rexistrarse no servizo e a xestionar contornos.
ms.date: 07/22/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 2f115269b9d07dd118ec18cc48b55de8aea9b5bb
ms.sourcegitcommit: 98267da3f3eddbdfbc89600a7f54e5e664a8f069
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 07/28/2021
ms.locfileid: "6683471"
---
# <a name="manage-environments"></a>Xestionar ambientes

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

## <a name="switch-environments"></a>Cambiar ambientes

Seleccione o control **Ambiente** na esquina superior dereita da páxina para cambiar ambientes.

:::image type="content" source="media/home-page-environment-switcher.png" alt-text="Captura de pantalla do control para cambiar de ambiente.":::

Os administradores poden [crear](get-started-paid.md) e xestionar ambientes.

## <a name="edit-an-existing-environment"></a>Editar un ambiente existente

Pode editar algúns detalles dos contornos existentes.

1.  Seleccione o selector de **ambiente** na cabeceira da aplicación.

2.  Seleccione a icona de **edición**.

3. Na caixa **Editar contorno**, pode actualizar o **Nome de visualización** do contorno, pero non pode cambiar a **Rexión** nin o **Tipo**.

4. Se un ambiente está configurado para almacenar datos en Azure Data Lake Storage, pode actualizar a **Clave da conta**. Non obstante, non podes cambiar o **Nome da conta** nin o nome do **Contedor**.

5. Opcionalmente, pode actualizar desde unha conexión baseada na clave de conta a unha conexión baseada en recursos ou baseada nunha subscrición. Unha vez actualizado, non poderá volver á clave da conta despois da actualización. Para obter máis información, consulte [Conectar información do público a unha conta de Azure Data Lake Storage Gen2 cunha entidade principal de seguranza do servizo de Azure](connect-service-principal.md). Non pode cambiar a información do **contedor** ao actualizar a conexión.

6. Opcionalmente, pode proporcionar un URL do contorno de Microsoft Dataverse en **Configurar o uso compartido de datos con Microsoft Dataverse e habilitar capacidades adicionais**. Estas capacidades inclúen o uso compartido de datos con aplicacións e solucións baseadas en Microsoft Dataverse, inxestión de datos de orixes de datos locais ou o uso de [predicións](predictions.md). Seleccione **Activar o uso compartido de datos** para compartir os datos de saída de Customer Insights cun Data Lake xestionado de Microsoft Dataverse.

   > [!NOTE]
   > - Compartir datos cun Data Lake xestionado Microsoft Dataverse actualmente non é compatible cando garda todos os datos no seu propio Azure Data Lake Storage.
   > - A [predición de valores que faltan nunha entidade](predictions.md) e os informes incorporados de PowerBI na información do público (se están activados no seu ambiente) non son compatibles actualmente cando activa o uso compartido de datos co lago de datos xestionado de Microsoft Dataverse.

   Despois de activar o uso compartido de datos con Microsoft Dataverse, comeza a actualización completa das orixes de datos e outros procesos. Se actualmente se están executando procesos, non ve a opción para habilitar o uso compartido de datos con Microsoft Dataverse. Espere a que estes procesos finalicen ou cancéleos para habilitar o uso compartido de datos. 
   
   :::image type="content" source="media/datasharing-with-DataverseMDL.png" alt-text="Opcións de configuración para habilitar o uso compartido de datos con Microsoft Dataverse.":::
   
   Cando execute procesos, como a inxestión de datos ou a creación de segmentos, crearanse os cartafoles correspondentes na conta de almacenamento que especificou anteriormente. Os ficheiros de datos e os ficheiros model.json crearanse e engadiranse ás respectivas subcarpetas, dependendo do proceso que execute.

## <a name="copy-the-environment-configuration"></a>Copiar a configuración dun ambiente

Cando crea un novo ambiente, pode escoller copiar a configuración dun ambiente existente. 

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Captura de pantalla das opcións de configuración na configuración do ambiente.":::

Verá unha lista de todos os ambientes dispoñibles da súa organización de onde pode copiar datos.

Copiaranse os seguintes axustes de configuración:

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

*Non* se copian os seguintes datos:

- Perfís de clientes.
- Credenciais da orixe de datos. Deberá proporcionar as credenciais para cada orixe de datos e actualizar as fontes de datos manualmente.
- Fontes de datos do cartafol de Common Data Model e Data Lake xestionado de Dataverse. Terá que crear esas orixes de datos manualmente co mesmo nome que no ambiente de orixe.

Cando copie un ambiente, verá unha mensaxe de confirmación de que se creou o novo contorno. Seleccione **Ir a orixes de datos** para ver a lista de orixes de datos.

Todas as orixes de datos mostrarán o estado **Credenciais requiridas**. Edite as orixes de datos e insira as credenciais para actualizalas.

:::image type="content" source="media/data-sources-copied.png" alt-text="Lista de orixes de datos que se copiaron e precisan autenticación.":::

Despois de actualizar as orixes de datos, diríxase a **Datos** > **Unificar**. Aquí atopará a configuración do ambiente de orixe. Edíteos segundo sexa necesario ou seleccione **Executar** para iniciar o proceso de unificación de datos e crear a entidade de cliente unificada.

Cando a unificación de datos estea completa, diríxase a **Medidas** e **Segmentos** para actualizalos tamén.

## <a name="reset-an-existing-environment"></a>Restablecer ambiente existente

Como administrador, pode restablecer un ambiente a un estado baleiro se quere eliminar todas as configuracións e eliminar os datos inxeridos.

1.  Seleccione o selector de **ambiente** na cabeceira da aplicación. 

2.  Seleccione o ambiente que desexa restablecer e seleccione os puntos suspensivos (**...**). 

3. Escolla a opción **Restablecer**. 

4.  Para confirmar a eliminación, introduza o nome do contorno e seleccione **Restablecer**.

## <a name="delete-an-existing-environment"></a>Eliminar un ambiente existente

Como administrador, pode eliminar un ambiente que administra.

1.  Seleccione o selector de **ambiente** na cabeceira da aplicación.

2.  Seleccione o ambiente que desexa restablecer e seleccione os puntos suspensivos (**...**). 

3. Escolla a opción **Eliminar**. 

4.  Para confirmar a eliminación, insira o nome do ambiente e seleccione **Eliminar**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
