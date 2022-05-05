---
title: Activa as regras de consentimento para os segmentos
description: Siga estes pasos para vincular os datos de consentimento e activar as comprobacións de consentimento en Dynamics 365 Customer Insights. Un administrador tamén pode desactivar as comprobacións de consentimento.
ms.date: 11/12/2021
ms.subservice: audience-insights
ms.topic: how-to
author: smithy7
ms.author: smithc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: bfa03f4b7b56b300a74ebd04721cd64b893879f1
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642526"
---
# <a name="activate-consent-rules"></a>Activar regras de consentimento

O [Centro de consentimento (vista previa)](consent-management/overview.md) axúdache a harmonizar os datos de consentimento de varias fontes. Usa o unificado *Consentimento* entidade para aplicar comprobacións de consentimento predeterminadas. Despois de importar os datos de consentimento no Centro de consentimento e de configurar as regras para os datos, o *Consentimento* a entidade sincronízase automaticamente con Dynamics 365 Customer Insights.

## <a name="enable-consent-checks"></a>Activar as comprobacións de consentimento

Cos datos de consentimento importados ao Centro de consentimento (vista previa) e as regras configuradas, podes activar as comprobacións de consentimento. 

:::image type="content" source="consent-management/media/enable-consent-checks.png" alt-text="Pestana de consentimento na configuración de Customer Insights cos datos de consentimento activados.":::

1. En Customer Insights, diríxase a **Administrador** > **Sistema**.

1. Seleccione o **Consentimento (vista previa)** ficha.

1. No **Activa as comprobacións de consentimento** sección, configure o interruptor en **Activado** para todas as áreas que quere activar.

1. Seleccione o **Permitir a anulación das regras de consentimento predeterminadas** caixa de verificación para eliminar as comprobacións de consentimento predeterminadas aplicadas a un segmento concreto. 

1. No menú despregable, selecciona onde queres permitir substitucións.     

1. No **Vincular o consentimento aos perfís de clientes** sección, escolla o atributo que se utiliza como identificador para vincular os datos de consentimento aos datos do cliente. Probablemente será un número de teléfono ou enderezo de correo electrónico. 

1. Seleccione **Gardar** para aplicar a súa configuración.

## <a name="disable-consent-checks"></a>Desactivar as comprobacións de consentimento

Para deixar de usar os datos de consentimento en Customer Insights, un administrador ten que actualizar a configuración do sistema en consecuencia.

1. En Customer Insights, diríxase a **Administrador** > **Sistema**.

1. Seleccione o **Consentimento (vista previa)** ficha.

1. No **Activa as comprobacións de consentimento** sección, configure o interruptor en **Desactivado**.

> [!TIP]
> Para deixar de usar a capacidade de xestión do consentimento, consulte [Configuración do sistema no Centro de consentimento (vista previa)](consent-management/system-settings.md).
