---
title: Destinos de exportación
description: Exportar datos e xestionar os destinos de exportación.
ms.date: 07/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 63caa2ebdd7d637d14ac9c9cc7972095803aee2f
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477131"
---
# <a name="export-destinations-preview-overview"></a>Visión xeral dos destinos de exportación (versión preliminar)

A páxina **Exportar destinos** móstralle todas as situacións que configurou ás que exportar datos. Tamén pode engadir novos destinos para a exportación. Ademais, mostra as opcións de exportación dispoñibles actualmente. Obteña unha visión xeral rápida e descrición e descubra o que pode facer con cada opción de extensibilidade. Exporte perfís, medidas e segmentos unificados a aplicacións compatibles relevantes para a súa empresa.

Vaia a **Administrador** > **Exportar destinos** para atopar as seguintes opcións de extensibilidade:

- [Complemento do cartón de Dynamics 365 Customer](customer-card-add-in.md)
- [Conector do xestor de anuncios de Facebook](export-facebook.md)
- [Conector de Power Automate](export-power-automate.md)
- [Conector de Power Apps](export-power-apps.md)
- [Conector de Power BI](export-power-bi.md)
- [Autopilot](export-autopilot.md)
- [DotDigital](export-dotdigital.md)
- [Dynamics 365 Sales](export-dynamics365-sales.md)
- [Dynamics 365 Marketing](export-dynamics365-marketing.md)
- [Almacenamento de BLOB de Azure](export-azure-blob-storage.md)
- [Azure Data Lake Storage Gen2](export-azure-data-lake-storage-gen2.md)
- [SendGrid](export-sendgrid.md)
- [Conector de LiveRamp&reg;](export-liveramp.md)
- [Bot para Microsoft Teams](export-teams-bot.md)
- [Mailchimp](export-mailchimp.md)
- [API de Customer Insights](apis.md)

## <a name="add-a-new-export-destination"></a>Engadir un novo destino de exportación

Para engadir destinos de exportación, ten [permisos de administrador](permissions.md). Se exporta a servizos Microsoft, supoñemos que ambos servizos están na mesma organización.

1. Vaia a **Administrador** > **Exportar destinos**.

1. Cambie ao separador **Os meus destinos de exportación**.

1. Seleccione **Engadir destino** para crear un novo destino de exportación.

1. No panel **Engadir destino**, seleccione o **Tipo** de destino de exportación na lista despregable.

1. Proporcione os detalles necesarios e seleccione **Seguinte** para crear o destino de exportación.

Tamén pode seleccionar **Configurar** nun mosaico do separador **Descubrir**.

## <a name="view-export-destinations"></a>Ver destinos de exportación

Despois de crear destinos de exportación, atoparalos nunha táboa do separador **Os meus destinos de exportación**. Esta táboa ten tres columnas:

- **Nome para mostrar**: o nome que introduciu ao crear o destino.
- **Tipo**: o tipo de destino de exportación que establece ao crear o destino.
- **Data de creación**: a data na que se creou o destino.

## <a name="edit-an-export-destination"></a>Editar un destino de exportación

1. Seleccione os tres puntos verticais para o destino de exportación que desexa editar.

   > [!div class="mx-imgBorder"]
   > ![Tres puntos verticais](media/export-destinations-page-ellipsis.png "Tres puntos verticais")

1. Seleccione **Editar** no menú despregable.

1. Cambie os valores que requiren actualización e seleccione **Gardar**.

## <a name="export-data-on-demand"></a>Exportar datos baixo demanda

Despois de configurar un conector para un destino de exportación, as exportacións executaranse con todas as [actualizacións programadas](system.md#schedule-tab).

Para exportar datos sen agardar unha actualización programada, diríxase ao separador **Os meus destinos de exportación** en **Administrador** > **Destinos de exportación**.

> [!div class="mx-imgBorder"]
> ![Tres puntos verticais](media/export-destinations-page-ellipsis.png "Tres puntos verticais")

- Seleccione **Exportar** enriba da lista para executar a exportación a todos os destinos de exportación simultaneamente.
- Seleccione os tres puntos (...) despois dun elemento da lista e logo escolla a opción **Exportar** para executar a exportación para un único destino de exportación.

## <a name="remove-an-export-destination"></a>Eliminar un destino de exportación

Para eliminar un destino de exportación, comece pola páxina **Destinos de exportación** principal.

1. Seleccione os tres puntos verticais para o destino de exportación que desexa eliminar.

   > [!div class="mx-imgBorder"]
   > ![Tres puntos verticais](media/export-destinations-page-ellipsis.png "Tres puntos verticais")

2. Seleccione **Eliminar** do menú despregable.

3. Confirme a eliminación seleccionando **Eliminar** na pantalla de confirmación.


[!INCLUDE[footer-include](../includes/footer-banner.md)]