---
title: Exportar datos de Customer Insights a Salesforce Marketing Cloud
description: Aprenda a configurar a conexión e exportar a Salesforce Marketing Cloud.
ms.date: 06/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 123f8b2dbb6140785dec6c1b4164d2f513f66a53
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314609"
---
# <a name="export-segments-and-other-data-to-salesforce-marketing-cloud-preview"></a>Exportar segmentos e outros datos a Salesforce Marketing Cloud (versión preliminar)

Use os datos dos seus clientes en Salesforce Marketing Cloud exportándoos a través dunha localización de protocolo de transferencia de ficheiros seguro (SFTP).

## <a name="prerequisites-for-connection"></a>Requisitos previos para a conexión

- Dispoñibilidade dun servidor SFTP e as correspondentes credenciais de administrador. [Como configurar localizacións SFTP para Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) 

## <a name="known-limitations"></a>Limitacións coñecidas

- O tempo de execución dunha exportación depende do rendemento do seu sistema. Recomendamos dous núcleos de CPU e 1 Gb de memoria como configuración mínima do seu servidor. 
- As entidades exportadoras con ata 100 millóns de perfís de clientes poden levar 90 minutos cando se usa a configuración mínima recomendada. 

## <a name="set-up-the-connection-to-salesforce-marketing-cloud"></a>Configurar a conexión a Salesforce Marketing Cloud

1. Vaia a **Administrar** > **Conexións**.

1. Seleccione **Engadir conexión** e elixa **Salesforce Marketing Cloud** para configurar a conexión.

1. Déalle á conexión un nome recoñecible no campo **Nome para mostrar**. O nome e o tipo de conexión describen esta conexión. Recomendamos escoller un nome que explique o propósito e o destino da conexión.

1. Escolla quen pode usar esta conexión. Se non realiza ningunha acción, o valor predeterminado será Administradores. Para obter máis información, consulte [Permitir aos colaboradores usar unha conexión para as exportacións](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Proporcione un **Nome de usuario**, **Contrasinal**, **Nome de servidor** e **Cartafol de exportación** para a súa conta de SFTP.

1. Seleccionar **Verificar** para probar a conexión.

1. Seleccione **Estou de acordo** para confirmar a **Privacidade e cumprimento dos datos**.

1. Seleccione **Gardar** para completar a conexión.

## <a name="configure-an-export"></a>Configurar unha exportación

Pode configurar esta exportación se ten acceso a unha conexión deste tipo. Para obter máis información, consulte [Permisos necesarios para configurar unha exportación](export-destinations.md#set-up-a-new-export).

1. Vaia a **Datos** > **Exportacións**.

1. Seleccione **Engadir destino** para crear unha nova exportación.

1. No campo **Conexión da exportación** escolla unha conexión da sección SFTP. Se non ve o nome desta sección, non hai conexións deste tipo dispoñibles para vostede.

1. Escolla se desexa exportar os seus datos **Comprimidos con gzip** ou **Descomprimidos** e o **delimitador de campo** dos ficheiros exportados.

1. Seleccione as entidades, por exemplo, segmentos que desexa exportar.

   > [!NOTE]
   > Cada entidade seleccionada dividirase en ata cinco ficheiros de saída cando se exporte. 

1. Seleccione **Gardar**.

Ao gardar unha exportación non se executa a exportación inmediatamente.

A exportación execútase con cada [actualización programada](system.md#schedule-tab). Tamén pode [exportar datos baixo demanda](export-destinations.md#run-exports-on-demand). 

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a>Importar datos de Customer Insights da localización SFTP a Salesforce Marketing Cloud

1. Cree [extensións de datos en Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) para importar o ficheiro de datos de Customer Insights desde a localización SFTP.

2. [Importe os datos desde a localización SFTP](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) na extensión de datos de Salesforce Marketing Cloud. 

3. Configure a automatización para importar os datos ás extensións de datos. Máis información sobre as [automatizacións ao soltar ficheiros e as automatizacións programadas](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).

   Defina unha [automatización ao soltar ficheiros](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) ou unha [automatización programada](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5). 

Aquí ten un exemplo dunha [automatización con SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).

## <a name="data-privacy-and-compliance"></a>Cumprimento e privacidade dos datos

Cando habilita Dynamics 365 Customer Insights para transmitir datos a SFTP, permite a transferencia de datos fóra do límite de cumprimento de Dynamics 365 Customer Insights, incluíndo datos potencialmente confidenciais como os datos persoais. Microsoft transferirá estes datos segundo a súa instrución, pero vostede é responsable de garantir que o destino de exportación cumpra as obrigas de privacidade ou seguridade que poida ter. Para obter máis información, consulte a [Declaración de privacidade de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
O administrador de Dynamics 365 Customer Insights pode eliminar este destino de exportación en calquera momento para interromper o uso desta funcionalidade.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
