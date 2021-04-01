---
title: Exportar datos de Customer Insights a servidores SFTP
description: Aprenda a configurar a conexión a un servidor SFTP.
ms.date: 01/27/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 9ec14fafa8f99e34b95349371298082e166535d0
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598383"
---
# <a name="connector-for-sftp-preview"></a>Conector de SFTP (vista previa)

Use os datos de cliente nas aplicacións de terceiros mediante a súa exportación a un servidor de protocolo seguro de transferencia de ficheiros (SFTP).

## <a name="prerequisites"></a>Requisitos previos

- Dispoñibilidade dun servidor SFTP e as credenciais correspondentes.

## <a name="connect-to-sftp"></a>Conectar con SFTP

1. Vaia a **Administrador** > **Exportar destinos**.

1. En **SFTP**, seleccione **Configurar**.

1. Déalle ao seu destino un nome recoñecible no campo **Nome para mostrar**.

1. Proporcione un **Nome de usuario**, **Contrasinal**, **Nome de servidor** e **Cartafol de exportación** para a súa conta de SFTP.

1. Seleccionar **Verificar** para probar a conexión.

1. Despois de verificar correctamente, escolla se desexa exportar os seus datos **Comprimidos con gzip** ou **Descomprimidos** e seleccione o **delimitador de campo** para os ficheiros exportados.

1. Seleccione **Estou de acordo** para confirmar a **Privacidade e cumprimento dos datos**.

1. Seleccione **Seguinte** para comezar a configurar a exportación.

## <a name="configure-the-export"></a>Configurar a exportación

1. Seleccione as entidades, por exemplo, segmentos que desexa exportar.

   > [!NOTE]
   > Cada entidade seleccionada terá ata cinco ficheiros de saída cando se exporten. 

1. Seleccione **Gardar**.

## <a name="export-the-data"></a>Exportar os datos

Pode [exportar datos baixo demanda](export-destinations.md). A exportación tamén se executará con todas as [actualizacións programadas](system.md#schedule-tab).

## <a name="known-limitations"></a>Limitacións coñecidas

- O tempo de execución dunha exportación depende do rendemento do seu sistema. Recomendamos dous núcleos de CPU e 1 Gb de memoria como configuración mínima do seu servidor. 
- As entidades exportadoras con ata 100 millóns de perfís de clientes poden tardar 90 minutos cando se usa a configuración mínima recomendada de dous núcleos de CPU e 1 Gb de memoria. 

## <a name="data-privacy-and-compliance"></a>Cumprimento e privacidade dos datos

Cando habilita Dynamics 365 Customer Insights para transmitir datos a SFTP, permite a transferencia de datos fóra do límite de cumprimento de Dynamics 365 Customer Insights, incluíndo datos potencialmente confidenciais como os datos persoais. Microsoft transferirá estes datos segundo a súa instrución, pero vostede é responsable de garantir que o destino de exportación cumpra as obrigas de privacidade ou seguridade que poida ter. Para obter máis información, consulte a [Declaración de privacidade de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
O administrador de Dynamics 365 Customer Insights pode eliminar este destino de exportación en calquera momento para interromper o uso desta funcionalidade.


[!INCLUDE[footer-include](../includes/footer-banner.md)]