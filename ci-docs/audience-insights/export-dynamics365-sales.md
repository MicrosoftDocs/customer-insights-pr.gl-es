---
title: Exportar datos de Customer Insights a Dynamics 365 Sales
description: Aprenda a configurar a conexión con Dynamics 365 Sales.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: af0824e69dfdf620a0ac756e32a9bd3dd85e5151
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643816"
---
# <a name="connector-for-dynamics-365-sales-preview"></a>Conector para Dynamics 365 Sales (previsualización)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Use os datos dos clientes para crear listas de márketing, realizar o seguimento de fluxos de traballo e enviar promocións con Dynamics 365 Sales.

## <a name="prerequisite"></a>Requisito previo

Rexistros de contactos [de Dynamics 365 Sales inxeridos mediante Common Data Service](connect-power-query.md).

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
