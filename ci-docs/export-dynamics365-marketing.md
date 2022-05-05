---
title: Exportar datos de Customer Insights a Dynamics 365 Marketing
description: Aprenda a configurar a conexión e exportar a Dynamics 365 Marketing.
ms.date: 08/24/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- customerInsights
ms.openlocfilehash: 7227f3f9e7699a9b5ad546789de5e568b56da579
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642446"
---
# <a name="use-segments-in-dynamics-365-marketing-preview"></a>Usar segmentos en Dynamics 365 Marketing (versión preliminar)



Use os [segmentos](segments.md) para xerar campañas e contactar con grupos específicos de clientes con Dynamics 365 Marketing. Para obter máis información, consulte [Usar segmentos de Dynamics 365 Customer Insights con Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments).

Se está a empregar as novas capacidades de Dynamics 365 Marketing para a orquestración de viaxes dos clientes en tempo real nunha organización de Dataverse, non precisa crear unha exportación estándar a Dynamics 365 Marketing. Os contactos e os segmentos de Customer Insights están dispoñibles directamente en Dynamics 365 Marketing despois de conectar Marketing e Customer Insights. Antes de eliminar as exportacións existentes, revise a documentación sobre [como conectar a orquestración de Customer Insights e Dynamics 365 Marketing viaxe do cliente](/dynamics365/marketing/real-time-marketing-ci-profile).

## <a name="prerequisite-for-a-connection"></a>Requisito previo para unha conexión

- Os rexistros de contacto deben estar presentes en Dynamics 365 Marketing antes de poder exportar un segmento de Customer Insights a Marketing. Lea máis sobre como inxerir contactos en [Dynamics 365 Marketing usando Microsoft Dataverse](connect-dataverse-managed-lake.md).

  > [!NOTE]
  > A exportación de segmentos de Customer Insights a Marketing non creará novos rexistros de contactos nas instancias de Marketing. Os rexistros de contactos de Marketing deben inxerirse en Customer Insights e utilizarse como orixe de datos. Tamén deben incluírse na entidade de cliente unificada para asignar os ID de clientes a ID de contacto antes de que os segmentos poidan ser exportados.

## <a name="set-up-connection-to-marketing"></a>Configurar conexión a Marketing

1. Vaia a **Administrar** > **Conexións**.

1. Seleccione **Engadir conexión** e elixa **Dynamics 365 Marketing** para configurar a conexión.

1. Déalle á conexión un nome recoñecible no campo **Nome para mostrar**. O nome e o tipo de conexión describen esta conexión. Recomendamos escoller un nome que explique o propósito e o destino da conexión.

1. Escolla quen pode usar esta conexión. Se non realiza ningunha acción, o valor predeterminado será Administradores. Para obter máis información, consulte [Permitir aos colaboradores usar unha conexión para as exportacións](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Insira o URL de mercadotecnia da súa organización no campo **Enderezo do servidor**.

1. Na sección **Conta de administrador do servidor**, seleccione **Iniciar sesión** e escolla unha conta de Dynamics 365 Marketing.

1. Asigne o campo Contact ID da entidade Cliente ao Contact ID de Dynamics 365.

1. Seleccione **Gardar** para completar a conexión. 

## <a name="configure-an-export"></a>Configurar unha exportación

Pode configurar esta exportación se ten acceso a unha conexión deste tipo. Para obter máis información, consulte [Permisos necesarios para configurar unha exportación](export-destinations.md#set-up-a-new-export).

1. Vaia a **Datos** > **Exportacións**.

1. Seleccione **Engadir destino** para crear unha nova exportación.

1. No campo **Conexión da exportación** escolla unha conexión da sección Dynamics 365 Marketing. Se non ve o nome desta sección, non hai conexións deste tipo dispoñibles para vostede.

1. Escolla un ou máis segmentos.

1. Seleccione **Gardar**.

Ao gardar unha exportación non se executa a exportación inmediatamente.

A exportación execútase con cada [actualización programada](system.md#schedule-tab). Tamén pode [exportar datos baixo demanda](export-destinations.md#run-exports-on-demand). 

[!INCLUDE [footer-include](includes/footer-banner.md)]
