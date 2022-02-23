---
title: Xestiona as regras de consentimento predeterminadas nos segmentos
description: Coa capacidade de xestión de consentimento, pode desactivar ou cambiar as regras de consentimento predeterminadas se as anulacións están activadas.
ms.date: 12/01/2021
ms.service: customer-insights
mms.topic: how-to
author: smithy7
ms.author: smithc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 28c9ea49b1f3aebd3abd7d4de58fe61e6474158b
ms.sourcegitcommit: 48d799535fad84e8b63c80aef48b5c5e87628f58
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 12/03/2021
ms.locfileid: "7884168"
---
# <a name="disable-or-change-default-consent-rules"></a>Desactivar ou cambiar as regras de consentimento predeterminadas

Se as súas organizacións usan o [capacidade de xestión do consentimento](../consent-management/overview.md) combinado con información sobre o público, [os administradores poden facer cumprir as regras de consentimento](activate-consent.md) para segmentos. 

Coas regras de consentimento obrigadas na área do segmento, cada segmento informa sobre o estado da comprobación do consentimento e as regras. Se se permiten substitucións, desactivaranse as regras de consentimento predeterminadas para segmentos específicos. Cada creador dun segmento pode engadir máis regras de consentimento ademais das regras predeterminadas a un segmento. 

## <a name="for-administrators"></a>Para administradores

:::image type="content" source="../consent-management/media/consent-rules-segment.png" alt-text="Creador de segmentos con opcións de regras de consentimento.":::

**Para desactivar as regras de consentimento predeterminadas:**

1. No **Regras de consentimento** notificación, seleccione **Ver detalles**. 

1. Establece o **Regras de consentimento predeterminadas** alternar a **Desactivado**.

**Para engadir máis regras de consentimento:**

1. No **Regras de consentimento** notificación, seleccione **Ver detalles**. 

1. Seleccione **Engadir regras de consentimento** e escolle unha regra de consentimento do **Seleccione o tipo de datos de consentimento** Despregar menú.

1. Seleccione **Gardar** para aplicar a nova regra ao segmento.

## <a name="for-contributors"></a>Para colaboradores

Para crear un segmento sen regras de consentimento obrigado, debes traballar co teu administrador para desactivalos no teu segmento. Non obstante, pode engadir as súas propias regras de consentimento aos segmentos que posúe e xestiona.

É un proceso de tres pasos: 
1. [Crea o segmento](segments.md) nas perspectivas da audiencia e gárdao. 

1. Comparte o nome do segmento co teu administrador e pídelles que o fagan [activa substitucións para o teu segmento](activate-consent.md). 

1. Abre de novo os teus segmentos. No **Regras de consentimento** notificación, seleccione **Ver detalles** e engade as regras de consentimento que queres aplicar. Entón, **Gardar** e **Corre** o teu segmento.



[!INCLUDE[footer-include](../includes/footer-banner.md)] 
