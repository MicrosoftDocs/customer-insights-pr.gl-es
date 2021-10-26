---
title: Crear e xestionar ambientes
description: Aprenda a rexistrarse no servizo e a xestionar contornos.
ms.date: 10/14/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: ce2fdd435a81bb04148057554c5958e3ab59f125
ms.sourcegitcommit: 53b133a716c73cb71e8bcbedc6273cec70ceba6c
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 10/15/2021
ms.locfileid: "7645124"
---
# <a name="manage-environments"></a>Xestionar ambientes

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

## <a name="switch-environments"></a>Cambiar ambientes

Seleccione o control **Ambiente** na esquina superior dereita da páxina para cambiar ambientes.

:::image type="content" source="media/home-page-environment-switcher.png" alt-text="Captura de pantalla do control para cambiar de ambiente.":::

Os administradores poden [crear](create-environment.md) e xestionar ambientes.

## <a name="edit-an-existing-environment"></a>Editar un ambiente existente

Pode editar algúns detalles dos contornos existentes.

1.  Seleccione o selector de **ambiente** na cabeceira da aplicación.

2.  Seleccione a icona de **edición**.

3. Na caixa **Editar contorno**, pode actualizar a configuración do contorno.

Para obter máis información sobre a configuración do contorno, consulte [Crear un novo contorno](create-environment.md).

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
