---
title: Exportar datos de Customer Insights a Dynamics 365 Sales
description: Aprenda a configurar a conexión e exportar a Dynamics 365 Sales.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 328bb2f26ebcea234fb645e5225930ab12f82a8b
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976224"
---
# <a name="use-segments-in-dynamics-365-sales-preview"></a>Usar segmentos en Dynamics 365 Sales (versión preliminar)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Use os datos dos clientes para crear listas de márketing, realizar o seguimento de fluxos de traballo e enviar promocións con Dynamics 365 Sales.

## <a name="prerequisite-for-connection"></a>Requisito previo para a conexión

1. Os rexistros de contacto deben estar presentes en Dynamics 365 Sales antes de poder exportar un segmento de Customer Insights a Sales. Lea máis sobre como inxerir contactos en [Dynamics 365 Sales usando Common Data Services](connect-power-query.md).

   > [!NOTE]
   > A exportación de segmentos de información de audiencia a Sales non creará novos rexistros de contacto nas instancias de Sales. Os rexistros de contacto de Sales deben ser inxeridos na información do público e utilizados como orixe de datos. Tamén deben incluírse na entidade de cliente unificada para asignar os ID de clientes a ID de contacto antes de que os segmentos poidan ser exportados.

## <a name="set-up-the-connection-to-sales"></a>Configurar a conexión a Sales

1. Vaia a **Administrar** > **Conexións**.

1. Seleccione **Engadir conexión** e elixa **Dynamics 365 Sales** para configurar a conexión.

1. Déalle á conexión un nome recoñecible no campo **Nome para mostrar**. O nome e o tipo de conexión describen esta conexión. Recomendamos escoller un nome que explique o propósito e o destino da conexión.

1. Escolla quen pode usar esta conexión. Se non realiza ningunha acción, o valor predeterminado será Administradores. Para obter máis información, consulte [Permitir aos colaboradores usar unha conexión para as exportacións](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Insira o URL de Vendas da súa organización no campo **Enderezo do servidor**.

1. Na sección **Conta de administrador do servidor**, seleccione **Iniciar sesión** e escolla unha conta de Dynamics 365 Sales.

1. Asigne un campo de ID de cliente ao ID de contacto de Dynamics 365.

1. Seleccione **Gardar** para completar a conexión. 

## <a name="configure-an-export"></a>Configurar unha exportación

Pode configurar esta exportación se ten acceso a unha conexión deste tipo. Para obter máis información, consulte [Permisos necesarios para configurar unha exportación](export-destinations.md#set-up-a-new-export).

1. Vaia a **Datos** > **Exportacións**.

1. Seleccione **Engadir destino** para crear unha nova exportación.

1. No campo **Conexión da exportación** escolla unha conexión da sección Dynamics 365 Sales. Se non ve o nome desta sección, non hai conexións deste tipo dispoñibles para vostede.

1. Escolla un ou máis segmentos.

1. Seleccione **Gardar**

Ao gardar unha exportación non se executa a exportación inmediatamente.

A exportación execútase con cada [actualización programada](system.md#schedule-tab). Tamén pode [exportar datos baixo demanda](export-destinations.md#run-exports-on-demand). 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
