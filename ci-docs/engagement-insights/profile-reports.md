---
title: Activar os informes de perfís listos para usar
description: Como crear informes de perfís listos para usar agrupados por sexo, idade e condado ou rexión de orixe.
author: darrinw-docs
ms.reviewer: mhart
ms.author: darrinw
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: bf2ec67c9fb99918b87841d3c0b131934e31b58b
ms.sourcegitcommit: 0ceb46c4f57ab49d3a2ebb1c8a816bbafe979e3d
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 09/09/2021
ms.locfileid: "7486118"
---
# <a name="out-of-box-profile-reports"></a>Informes de perfís listos para usar

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Un informe é unha recompilación de visualizacións de datos que axudan a comprender o comportamento dos usuarios. Ao conectarse á información do público de Customer Insights, a información de interacción poden mostrar un informe con información sobre perfís de clientes unificados. Este informe inclúe o número de perfís que ten, agrupados por sexo, idade e localización xeográfica.

## <a name="prerequisites"></a>Requisitos previos

O ambiente de información do público debe almacenar os datos nunha conta de Azure Data Lake Storage xestionada polo cliente.

Se está a usar unha versión de proba da capacidade de información do público ou un ambiente nun lago de datos xestionado de Customer Insights, [póñase en contacto connosco](https://go.microsoft.com/fwlink/?linkid=2145734) para obter axuda.  


## <a name="enable-the-customer-profile-report"></a>Activar o informe de perfís de clientes

Un administrador de contornos debe [ligar información de interacción e información de público](integrate-audience-insights-engagement-insights.md).

Despois de especificar os detalles da conexión, o administrador pode conceder acceso a outras persoas da organización para ver o informe. O administrador de ambientes que configura a conexión ten acceso automaticamente ao informe. 

Despois de completar a conexión, a funcionalidade **Pefís** estará dispoñible no panel de navegación esquerdo. 

- Vaia a **Descubrir** > **Perfís** para ver o informe.

O informe de **Perfís** contén visualizacións sobre o sexo, a idade e a localización xeográfica dos perfís de clientes conectados.

:::image type="content" source="media/customer-profiles.png" alt-text="Informe de perfís de clientes.":::

[!INCLUDE[footer-include](../includes/footer-banner.md)]