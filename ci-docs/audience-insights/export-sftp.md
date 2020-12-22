---
title: Exportar datos de Customer Insights a servidores SFTP
description: Aprenda a configurar a conexión a un servidor SFTP.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c2529744d7a26a06324b79cad6a8001d75903545
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643501"
---
# <a name="connector-for-sftp-preview"></a>Conector de SFTP (vista previa)

Use os datos de cliente nas aplicacións de terceiros mediante a súa exportación a un servidor de protocolo seguro de transferencia de ficheiros (SFTP).

## <a name="prerequisites"></a>Requisitos previos

- Dispoñibilidade dun servidor SFTP e correspondentes credenciais.

## <a name="connect-to-sftp"></a>Conectar con SFTP

1. Vaia a **Administrador** > **Exportar destinos**.

1. En **SFTP**, seleccione **Configurar**.

1. Déalle ao seu destino un nome recoñecible no campo **Nome para mostrar**.

1. Proporcione un **Nome de usuario**, **Contrasinal** e **Nome de servidor** para a súa conta de SFTP. Exemplo: se o cartafol raíz do seu servidor SFTP é /root/folder e desexa que os datos se exporten a /root/folder/ci_export_destination_folder, o servidor debería ser sftp://<server_address>/ci_export_destination_folder".

1. Seleccionar **Verificar** para probar a conexión.

1. Despois de verificar con éxito, escolla se desexa exportar os seus datos **comprimidos** ou **descompromidos** e selecciona o **delimitador de campos** para os ficheiros exportados.

1. Seleccione **Estou de acordo** para confirmar a **Privacidade e cumprimento dos datos**.

1. Seleccione **Seguinte** para comezar a configurar a exportación.

## <a name="configure-the-connection"></a>Configurar a conexión

1. Seleccione os **atributos do cliente** que quere exportar. Pode exportar un ou varios atributos.

1. Seleccione **Seguinte**.

1. Seleccione os segmentos que desexa exportar.

1. Seleccione **Gardar**.

## <a name="export-the-data"></a>Exportar os datos

Pode [exportar datos baixo demanda](export-destinations.md). A exportación tamén se executará con todas as [actualizacións programadas](system.md#schedule-tab).

## <a name="data-privacy-and-compliance"></a>Cumprimento e privacidade dos datos

Cando habilita Dynamics 365 Customer Insights para transmitir datos a SFTP, permite a transferencia de datos fóra do límite de cumprimento de Dynamics 365 Customer Insights, incluíndo datos potencialmente confidenciais como os datos persoais. Microsoft transferirá estes datos segundo a súa instrución, pero vostede é responsable de garantir que o destino de exportación cumpra as obrigas de privacidade ou seguridade que poida ter. Para obter máis información, consulte a [Declaración de privacidade de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
O administrador de Dynamics 365 Customer Insights pode eliminar este destino de exportación en calquera momento para interromper o uso desta funcionalidade.
