---
title: Exportar datos de Customer Insights a hosts SFTP (contén vídeo)
description: Aprenda a configurar a conexión e exportar a unha localización de SFTP.
ms.date: 06/09/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b56d628c8286ba6697cccc9b002f609aa929951b
ms.sourcegitcommit: 8e9f0a9693fd8d91ad0227735ff03688fef5406f
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 06/10/2022
ms.locfileid: "8947182"
---
# <a name="export-segments-and-other-data-to-sftp-preview"></a>Exportar segmentos e outros datos a SFTP (versión preliminar)

Use os datos dos seus clientes en aplicacións de terceiros exportándoos a unha localización do protocolo de transferencia de ficheiros segura (SFTP).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO94X]

## <a name="prerequisites-for-connection"></a>Requisitos previos para a conexión

- Dispoñibilidade dun servidor SFTP e as credenciais correspondentes.

## <a name="known-limitations"></a>Limitacións coñecidas

- Os destinos SFTP detrás dos cortalumes non son compatibles actualmente. 
- O tempo de execución dunha exportación depende do rendemento do seu sistema. Recomendamos dous núcleos de CPU e 1 Gb de memoria como configuración mínima do seu servidor.
- As entidades exportadoras con ata 100 millóns de perfís de clientes poden tardar 90 minutos cando se usa a configuración mínima recomendada de dous núcleos de CPU e 1 Gb de memoria.

## <a name="set-up-connection-to-sftp"></a>Configurar conexión a SFTP

1. Vaia a **Administrar** > **Conexións**.

1. Seleccione **Engadir conexión** e elixa **SFTP** para configurar a conexión.

1. Déalle á conexión un nome recoñecible no campo **Nome para mostrar**. O nome e o tipo de conexión describen esta conexión. Recomendamos escoller un nome que explique o propósito e o destino da conexión.

1. Escolla quen pode usar esta conexión. Se non realiza ningunha acción, o valor predeterminado será Administradores. Para obter máis información, consulte [Permitir aos colaboradores usar unha conexión para as exportacións](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Proporcione un **Nome de usuario**, **Contrasinal**, **Nome de servidor** e **Cartafol de exportación** para a súa conta de SFTP.

1. Seleccionar **Verificar** para probar a conexión.

1. Escolla se desexa exportar os seus datos **Comprimidos con gzip** ou **Descomprimidos** e o **delimitador de campo** dos ficheiros exportados.

1. Seleccione **Estou de acordo** para confirmar a **Privacidade e cumprimento dos datos**.

1. Seleccione **Gardar** para completar a conexión.

## <a name="configure-an-export"></a>Configurar unha exportación

Pode configurar esta exportación se ten acceso a unha conexión deste tipo. Para obter máis información, consulte [Permisos necesarios para configurar unha exportación](export-destinations.md#set-up-a-new-export).

1. Vaia a **Datos** > **Exportacións**.

1. Seleccione **Engadir destino** para crear unha nova exportación.

1. No campo **Conexión da exportación** escolla unha conexión da sección SFTP. Se non ve o nome desta sección, non hai conexións deste tipo dispoñibles para vostede.

1. Seleccione as entidades, por exemplo, segmentos que desexa exportar.

   > [!NOTE]
   > Cada entidade seleccionada dividirase en ata cinco ficheiros de saída cando se exporte.

1. Seleccione **Gardar**.

Ao gardar unha exportación non se executa a exportación inmediatamente.

A exportación execútase con cada [actualización programada](system.md#schedule-tab).
Tamén pode [exportar datos baixo demanda](export-destinations.md#run-exports-on-demand).

> [!TIP]
> A exportación de entidades que conteñen unha gran cantidade de datos pode levar a varios ficheiros CSV no mesmo cartafol para cada exportación. A división das exportacións ocorre por motivos de rendemento para minimizar o tempo que tarda en completarse unha exportación.

## <a name="data-privacy-and-compliance"></a>Cumprimento e privacidade dos datos

Cando habilita Dynamics 365 Customer Insights para transmitir datos a SFTP, permite a transferencia de datos fóra do límite de cumprimento de Dynamics 365 Customer Insights, incluíndo datos potencialmente confidenciais como os datos persoais. Microsoft transferirá estes datos segundo a súa instrución, pero vostede é responsable de garantir que o destino de exportación cumpra as obrigas de privacidade ou seguridade que poida ter. Para obter máis información, consulte a [Declaración de privacidade de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
O administrador de Dynamics 365 Customer Insights pode eliminar este destino de exportación en calquera momento para interromper o uso desta funcionalidade.

[!INCLUDE [footer-include](includes/footer-banner.md)]
