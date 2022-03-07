---
title: Activar regras de consentimento para segmentos
description: Sigue estes pasos para vincular os datos de consentimento e activar as comprobacións de consentimento nas estatísticas da audiencia. Un administrador tamén pode desactivar as comprobacións de consentimento.
ms.date: 11/12/2021
ms.subservice: audience-insights
ms.topic: how-to
author: smithy7
ms.author: smithc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 4b55c82229b1a6189c0dd67d145386344286df8a
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 02/16/2022
ms.locfileid: "8227491"
---
# <a name="activate-consent-rules"></a>Activar regras de consentimento

O [Centro de consentimento (vista previa)](../consent-management/overview.md) axúdache a harmonizar os datos de consentimento de varias fontes. Usa o unificado *Consentimento* entidade para aplicar comprobacións de consentimento predeterminadas. Despois de importar os datos de consentimento no Centro de consentimento e de configurar as regras para os datos, o *Consentimento* A entidade sincronizarase automaticamente coas estatísticas do público.

## <a name="enable-consent-checks"></a>Activar as comprobacións de consentimento

Cos datos de consentimento importados ao Centro de consentimento (vista previa) e as regras configuradas, podes activar as comprobacións de consentimento. 

:::image type="content" source="../consent-management/media/enable-consent-checks-audience-insights.png" alt-text="Pestana de consentimento na configuración de estatísticas de audiencia cos datos de consentimento activados.":::

1. Na información do público, vaia a **Administrar** > **Sistema**.

1. Seleccione o **Consentimento (vista previa)** ficha.

1. No **Activa as comprobacións de consentimento** sección, configure o interruptor en **Activado** para todas as áreas que quere activar.

1. Seleccione o **Permitir a anulación das regras de consentimento predeterminadas** caixa de verificación para eliminar as comprobacións de consentimento predeterminadas aplicadas a un segmento concreto. 

1. No menú despregable, selecciona onde queres permitir substitucións.     

1. No **Vincular o consentimento aos perfís de clientes** sección, escolla o atributo que se utiliza como identificador para vincular os datos de consentimento aos datos do cliente. Probablemente será un número de teléfono ou enderezo de correo electrónico. 

1. Seleccione **Gardar** para aplicar a súa configuración.

## <a name="disable-consent-checks"></a>Desactivar as comprobacións de consentimento

Para deixar de usar os datos de consentimento nas estatísticas da audiencia, un administrador ten que actualizar a configuración do sistema en consecuencia.

1. Na información do público, vaia a **Administrar** > **Sistema**.

1. Seleccione o **Consentimento (vista previa)** ficha.

1. No **Activa as comprobacións de consentimento** sección, configure o interruptor en **Desactivado**.

> [!TIP]
> Para deixar de usar a capacidade de xestión do consentimento, consulte [Configuración do sistema no Centro de consentimento (vista previa)](../consent-management/system-settings.md).
