---
title: Exportar datos de Customer Insights a Dynamics 365 Sales
description: Aprenda a configurar a conexión con Dynamics 365 Sales.
ms.date: 02/01/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0013c4e6a96401d6cdbea55ed38f85f5e10dcc56
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269006"
---
# <a name="connector-for-dynamics-365-sales-preview"></a>Conector para Dynamics 365 Sales (previsualización)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Use os datos dos clientes para crear listas de márketing, realizar o seguimento de fluxos de traballo e enviar promocións con Dynamics 365 Sales.

## <a name="prerequisite"></a>Requisito previo

1. Os rexistros de contacto deben estar presentes en Dynamics 365 Sales antes de poder exportar un segmento de Customer Insights a Sales. Lea máis sobre como inxerir contactos en [Dynamics 365 Sales usando Common Data Services](connect-power-query.md).

   > [!NOTE]
   > A exportación de segmentos de información de audiencia a Sales non creará novos rexistros de contacto nas instancias de Sales. Os rexistros de contacto de Sales deben ser inxeridos na información do público e utilizados como orixe de datos. Tamén deben incluírse na entidade de cliente unificada para asignar os ID de clientes a ID de contacto antes de que os segmentos poidan ser exportados.

## <a name="configure-the-connector-for-sales"></a>Configurar o conector para Vendas

1. Na información do público, vaia a **Administrar** > **Destinos de exportación**.

1. En **Dynamics 365 Sales**, seleccione **Configurar**.

1. Déalle ao seu destino da exploración un nome recoñecible no campo **Nome para mostrar**.

1. Insira o URL de Vendas da súa organización no campo **Enderezo do servidor**.

1. Na sección **Conta de administrador do servidor**, seleccione **Iniciar sesión** e escolla unha conta de Dynamics 365 Sales.

1. Asigne un campo de ID de cliente ao ID de contacto de Dynamics 365.

1. Seleccione **Seguinte**.

1. Escolla un ou máis segmentos.

1. Seleccione **Gardar**.

## <a name="export-the-data"></a>Exportar os datos

Pode [exportar datos baixo demanda](export-destinations.md). A exportación tamén se executará con todas as [actualizacións programadas](system.md#schedule-tab).


[!INCLUDE[footer-include](../includes/footer-banner.md)]