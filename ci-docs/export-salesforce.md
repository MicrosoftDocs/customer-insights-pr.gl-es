---
title: Exportar datos a Salesforce Marketing Cloud (vista previa)
description: Aprenda a configurar a conexión e exportar a Salesforce Marketing Cloud.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 58e76e51c18c25177f9b4551b70b25b41248b142
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 07/27/2022
ms.locfileid: "9197036"
---
# <a name="export-data-to-salesforce-marketing-cloud-preview"></a>Exportar datos a Salesforce Marketing Cloud (vista previa)

Use os datos dos seus clientes en Salesforce Marketing Cloud exportándoos a través dunha localización de protocolo de transferencia de ficheiros seguro (SFTP).

## <a name="prerequisites"></a>Requisitos previos

- An [Host SFTP para Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) e as correspondentes credenciais de administrador.

## <a name="set-up-connection-to-salesforce-marketing-cloud"></a>Configura a conexión a Salesforce Marketing Cloud

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vaia a **Administrar** > **Conexións**.

1. Seleccione **Engadir conexión** e escolle **Salesforce Marketing Cloud**.

1. Déalle á conexión un nome recoñecible no campo **Nome para mostrar**. O nome e o tipo de conexión describen esta conexión. Recomendamos escoller un nome que explique o propósito e o destino da conexión.

1. Escolla quen pode usar esta conexión. Por defecto, só son os administradores. Para obter máis información, consulte [Permitir aos colaboradores usar unha conexión para as exportacións](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Proporcione un **Nome de usuario**, **Contrasinal**, **Nome de servidor** e **Cartafol de exportación** para a súa conta de SFTP.

1. Seleccionar **Verificar** para probar a conexión.

1. Revisa o [privacidade e cumprimento dos datos](connections.md#data-privacy-and-compliance) e selecciona **Estou de acordo**.

1. Seleccione **Gardar** para completar a conexión.

## <a name="configure-an-export"></a>Configurar unha exportación

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vaia a **Datos** > **Exportacións**.

1. Seleccione **Engadir exportación**.

1. No campo **Conexión da exportación** escolla unha conexión da sección SFTP. Póñase en contacto cun administrador se non hai conexión dispoñible.

1. Introduza un nome para a exportación.

1. Escolla se desexa exportar os seus datos **Comprimidos con gzip** ou **Descomprimidos** e o **delimitador de campo** dos ficheiros exportados.

1. Seleccione as entidades, por exemplo segmentos, que quere exportar.

   > [!NOTE]
   > Cada entidade seleccionada dividirase nun máximo de cinco ficheiros de saída cando se exporte.

1. Seleccione **Gardar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a>Importar datos de Customer Insights da localización SFTP a Salesforce Marketing Cloud

1. Cree [extensións de datos en Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) para importar o ficheiro de datos de Customer Insights desde a localización SFTP.

2. [Importe os datos desde a localización SFTP](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) na extensión de datos de Salesforce Marketing Cloud.

3. Configure a automatización para importar os datos ás extensións de datos. Máis información sobre as [automatizacións ao soltar ficheiros e as automatizacións programadas](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).

   Defina unha [automatización ao soltar ficheiros](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) ou unha [automatización programada](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).

Aquí ten un exemplo dunha [automatización con SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).

[!INCLUDE [footer-include](includes/footer-banner.md)]
