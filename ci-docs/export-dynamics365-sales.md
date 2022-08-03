---
title: Exportar segmentos a Dynamics 365 Sales (vista previa)
description: Aprenda a configurar a conexión e exportar a Dynamics 365 Sales.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- customerInsights
ms.openlocfilehash: c3497f4625cada49ae33c6987e58994a15536f9b
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195979"
---
# <a name="export-segments-to-dynamics-365-sales-preview"></a>Exportar segmentos a Dynamics 365 Sales (vista previa)

Use os datos dos clientes para crear listas de márketing, realizar o seguimento de fluxos de traballo e enviar promocións con Dynamics 365 Sales.

## <a name="prerequisites"></a>Requisitos previos

Os rexistros de contacto deben estar presentes en Dynamics 365 Sales antes de poder exportar un segmento de Customer Insights a Sales. Lea máis información sobre como inxerir contactos desde [Dynamics 365 Sales usando Microsoft Dataverse](connect-dataverse-managed-lake.md).

   > [!NOTE]
   > A exportación de segmentos de Customer Insights a Sales non creará novos rexistros de contactos nas instancias de Sales. Os rexistros de contactos de Sales deben inxerirse en Customer Insights e utilizarse como orixe de datos. Tamén deben incluírse na entidade de cliente unificada para asignar os ID de clientes a ID de contacto antes de que os segmentos poidan ser exportados.

## <a name="known-limitations"></a>Limitacións coñecidas

As exportacións a Dynamics 365 Sales están limitadas a 100.000 por segmento, o que pode tardar ata 3 horas en completarse.

## <a name="set-up-connection-to-sales"></a>Configura a conexión con Sales

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vaia a **Administrar** > **Conexións**.

1. Seleccione **Engadir conexión** e escolle **Dynamics 365 Sales**.

1. Déalle á conexión un nome recoñecible no campo **Nome para mostrar**. O nome e o tipo de conexión describen esta conexión. Recomendamos escoller un nome que explique o propósito e o destino da conexión.

1. Escolla quen pode usar esta conexión. Por defecto, só son os administradores. Para obter máis información, consulte [Permitir aos colaboradores usar unha conexión para as exportacións](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Insira o URL de Vendas da súa organización no campo **Enderezo do servidor**.

1. Na sección **Conta de administrador do servidor**, seleccione **Iniciar sesión** e escolla unha conta de Dynamics 365 Sales.

1. Asigne un campo de ID de cliente ao ID de contacto de Dynamics 365.

1. Revisa o [privacidade e cumprimento dos datos](connections.md#data-privacy-and-compliance) e selecciona **Estou de acordo**.

1. Seleccione **Gardar** para completar a conexión.

## <a name="configure-an-export"></a>Configurar unha exportación

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vaia a **Datos** > **Exportacións**.

1. Seleccione **Engadir exportación**.

1. No campo **Conexión da exportación** escolla unha conexión da sección Dynamics 365 Sales. Póñase en contacto cun administrador se non hai conexión dispoñible.

1. Introduza un nome para a exportación.

1. Seleccione o campo Contact ID na entidade Cliente que coincida co Contact ID de Dynamics 365.

1. Seleccione os segmentos que desexa exportar.

1. Seleccione **Gardar**

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
