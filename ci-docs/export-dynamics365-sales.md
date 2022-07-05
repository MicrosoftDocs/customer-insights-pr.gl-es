---
title: Exportar segmentos a Dynamics 365 Sales (vista previa)
description: Aprenda a configurar a conexión e exportar a Dynamics 365 Sales.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- customerInsights
ms.openlocfilehash: b8e756313ca037dca41cb25587229808f0c584c9
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082384"
---
# <a name="export-segments-to-dynamics-365-sales-preview"></a>Exportar segmentos a Dynamics 365 Sales (vista previa)

Use os datos dos clientes para crear listas de márketing, realizar o seguimento de fluxos de traballo e enviar promocións con Dynamics 365 Sales.

## <a name="known-limitations"></a>Limitacións coñecidas

- As exportacións a Dynamics 365 Sales están limitadas a 100.000 membros por segmento.
- As exportacións de segmentos a Dynamics 365 Sales poden tardar ata 3 horas en completarse. 

## <a name="prerequisite-for-connection"></a>Requisito previo para a conexión

1. Os rexistros de contacto deben estar presentes en Dynamics 365 Sales antes de poder exportar un segmento de Customer Insights a Sales. Lea máis sobre como inxerir contactos desde [Dynamics 365 Sales usando Microsoft Dataverse](connect-dataverse-managed-lake.md).

   > [!NOTE]
   > A exportación de segmentos de Customer Insights a Sales non creará novos rexistros de contactos nas instancias de Sales. Os rexistros de contacto de Sales deben inxerirse en Customer Insights e utilizarse como orixe de datos. Tamén deben incluírse na entidade de cliente unificada para asignar os ID de clientes a ID de contacto antes de que os segmentos poidan ser exportados.

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

[!INCLUDE [footer-include](includes/footer-banner.md)]
