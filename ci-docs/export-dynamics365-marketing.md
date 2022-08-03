---
title: Exportar segmentos a Dynamics 365 Marketing (vista previa)
description: Aprenda a configurar a conexión e exportar a Dynamics 365 Marketing.
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
ms.openlocfilehash: 123b565421a7d096e7341a8f600f91e59aefe8d0
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196622"
---
# <a name="export-segments-to-dynamics-365-marketing-preview"></a>Exportar segmentos a Dynamics 365 Marketing (vista previa)

Use [segmentos](segments.md) para xerar campañas e contactar con grupos específicos de clientes [Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments).

Se está a empregar as novas capacidades de Dynamics 365 Marketing para a orquestración de viaxes dos clientes en tempo real nunha organización de Dataverse, non precisa crear unha exportación estándar a Dynamics 365 Marketing. Os contactos e os segmentos de Customer Insights están dispoñibles directamente en Dynamics 365 Marketing despois de conectar Marketing e Customer Insights. Antes de eliminar as exportacións existentes, revise a documentación sobre [como conectar a orquestración de Customer Insights e Dynamics 365 Marketing viaxe do cliente](/dynamics365/marketing/real-time-marketing-ci-profile).

## <a name="prerequisite"></a>Requisito previo

Os rexistros de contacto deben estar presentes en Dynamics 365 Marketing antes de poder exportar un segmento de Customer Insights a Marketing. Lea máis sobre como inxerir contactos en [Dynamics 365 Marketing usando Microsoft Dataverse](connect-dataverse-managed-lake.md).

> [!NOTE]
> A exportación de segmentos de Customer Insights a Marketing non creará novos rexistros de contactos nas instancias de Marketing. Os rexistros de contactos de Marketing deben inxerirse en Customer Insights e utilizarse como orixe de datos. Tamén deben incluírse na entidade de cliente unificada para asignar os ID de clientes a ID de contacto antes de que os segmentos poidan ser exportados.

## <a name="set-up-connection-to-marketing"></a>Configurar conexión a Marketing

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vaia a **Administrar** > **Conexións**.

1. Seleccione **Engadir conexión** e escolle **Dynamics 365 Marketing**.

1. Déalle á conexión un nome recoñecible no campo **Nome para mostrar**. O nome e o tipo de conexión describen esta conexión. Recomendamos escoller un nome que explique o propósito e o destino da conexión.

1. Escolla quen pode usar esta conexión. Por defecto, só son os administradores. Para obter máis información, consulte [Permitir aos colaboradores usar unha conexión para as exportacións](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Insira o URL de mercadotecnia da súa organización no campo **Enderezo do servidor**.

1. Na sección **Conta de administrador do servidor**, seleccione **Iniciar sesión** e escolla unha conta de Dynamics 365 Marketing.

1. Asigne o campo Contact ID da entidade Cliente ao Contact ID de Dynamics 365.

1. Revisa o [privacidade e cumprimento dos datos](connections.md#data-privacy-and-compliance) e selecciona **Estou de acordo**.

1. Seleccione **Gardar** para completar a conexión.

## <a name="configure-an-export"></a>Configurar unha exportación

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vaia a **Datos** > **Exportacións**.

1. Seleccione **Engadir exportación**.

1. No campo **Conexión da exportación** escolla unha conexión da sección Dynamics 365 Marketing. Póñase en contacto cun administrador se non hai conexión dispoñible.

1. Introduza un nome para a exportación.

1. Seleccione o campo Contact ID na entidade Cliente que coincida co Contact ID de Dynamics 365.

1. Seleccione os segmentos que desexa exportar.

1. Seleccione **Gardar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
