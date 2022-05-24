---
title: Xestiona as regras de consentimento predeterminadas nos segmentos
description: Coa capacidade de xestión de consentimento, pode desactivar ou cambiar as regras de consentimento predeterminadas se as anulacións están activadas.
ms.date: 12/01/2021
ms.topic: how-to
author: anubhav-t
ms.author: antando
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 764eeca9d99c95a34d9bd4c11d79f8b8e90701e2
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755214"
---
# <a name="disable-or-change-default-consent-rules"></a>Desactivar ou cambiar as regras de consentimento predeterminadas

Se as súas organizacións usan o [capacidade de xestión do consentimento](consent-management/overview.md) con Dynamics 365 Customer Insights,[os administradores poden facer cumprir as regras de consentimento](activate-consent.md) para segmentos. 

Coas regras de consentimento obrigadas na área do segmento, cada segmento informa sobre o estado da comprobación do consentimento e as regras. Se se permiten substitucións, desactivaranse as regras de consentimento predeterminadas para segmentos específicos. Cada creador dun segmento pode engadir máis regras de consentimento ademais das regras predeterminadas a un segmento. 

## <a name="for-administrators"></a>Para administradores

:::image type="content" source="consent-management/media/consent-rules-segment.png" alt-text="Creador de segmentos con opcións de regras de consentimento.":::

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
1. [Crea o segmento](segments.md) en Customer Insights e gárdao. 

1. Comparte o nome do segmento co teu administrador e pídelles que o fagan [activa substitucións para o teu segmento](activate-consent.md). 

1. Abre de novo os teus segmentos. No **Regras de consentimento** notificación, seleccione **Ver detalles** e engade as regras de consentimento que queres aplicar. Entón, **Gardar** e **Corre** o teu segmento.



[!INCLUDE [footer-include](includes/footer-banner.md)] 
