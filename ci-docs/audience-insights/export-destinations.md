---
title: Destinos de exportación
description: Exportar datos e xestionar os destinos de exportación.
ms.date: 07/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 5557442983f8c48cd46387009e0060beb6e764bb
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596083"
---
# <a name="export-destinations-preview-overview"></a>Visión xeral dos destinos de exportación (versión preliminar)

A páxina **Exportar destinos** móstralle todas as situacións que configurou ás que exportar datos. Tamén pode engadir novos destinos para a exportación. Ademais, mostra as opcións de exportación dispoñibles actualmente. Obteña unha visión xeral rápida e descrición e descubra o que pode facer con cada opción de extensibilidade. Exporte perfís, medidas e segmentos unificados a aplicacións compatibles relevantes para a súa empresa.

Vaia a **Administrador** > **Exportar destinos** para atopar as seguintes opcións de extensibilidade:

- [Adobe Campaign Standard](export-adobe-campaign-standard.md)
- [Plataforma Adobe Experience](export-adobe-experience-platform.md)
- [AdRoll](export-adroll.md)
- [Autopilot](export-autopilot.md)
- [Almacenamento de BLOB de Azure](export-azure-blob-storage.md)
- [Azure Data Lake Storage Gen2](export-azure-data-lake-storage-gen2.md)
- [Bot para Microsoft Teams](export-teams-bot.md)
- [API de Customer Insights](apis.md)
- [DotDigital](export-dotdigital.md)
- [Dynamics 365 Customer Service (suplemento do cartón de cliente)](customer-card-add-in.md)
- [Dynamics 365 Marketing](export-dynamics365-marketing.md)
- [Dynamics 365 Sales](export-dynamics365-sales.md)
- [Dynamics 365 Sales Hub (Suplemento do cartón de cliente)](customer-card-add-in.md)
- [Xestor de anuncios de Facebook](export-facebook.md)
- [Google Ads](export-google-ads.md)
- [LiveRamp&reg;](export-liveramp.md)
- [Mailchimp](export-mailchimp.md)
- [Marketo](export-marketo.md)
- [Power Automate](export-power-automate.md)
- [Power Apps](export-power-apps.md)
- [Power BI](export-power-bi.md)
- [SendGrid](export-sendgrid.md)
- [SFTP](export-sftp.md)

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