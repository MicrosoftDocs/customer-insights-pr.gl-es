---
title: Exportar datos a hosts SFTP (vista previa) (contén vídeo)
description: Aprenda a configurar a conexión e exportar a unha localización de SFTP.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b12d25ecbd2e5fb31d7d5a6bb775dc3e7c1bf007
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 07/28/2022
ms.locfileid: "9207227"
---
# <a name="export-data-to-sftp-hosts-preview"></a>Exportar datos a hosts SFTP (vista previa)

Use os datos dos seus clientes en aplicacións de terceiros exportándoos a unha localización do protocolo de transferencia de ficheiros segura (SFTP).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO94X]

## <a name="prerequisites"></a>Requisitos previos

- Dispoñibilidade dun servidor SFTP e as credenciais correspondentes.

## <a name="known-limitations"></a>Limitacións coñecidas

- Os destinos SFTP detrás dos cortalumes non son compatibles actualmente.
- O tempo de execución dunha exportación depende do rendemento do seu sistema. Recomendamos dous núcleos de CPU e 1 Gb de memoria como configuración mínima do seu servidor.
- Ata 100 millóns de perfís de clientes, o que pode levar 90 minutos cando se utiliza a configuración mínima recomendada de dous núcleos de CPU e 1 Gb de memoria.
- Se usa unha clave SSH para a autenticación, asegúrese de que [crea a túa clave privada](/azure/virtual-machines/linux/create-ssh-keys-detailed#basic-example) como formato PEM ou SSH.COM. Se estás a usar Putty, converte a túa clave privada exportándoa como Open SSH. Admítense os seguintes formatos de clave privada:
  - RSA en OpenSSL PEM e formato ssh.com
  - DSA en formato OpenSSL PEM e ssh.com
  - ECDSA 256/384/521 en formato OpenSSL PEM
  - ED25519 e RSA en formato de chave OpenSSH

## <a name="set-up-connection-to-sftp"></a>Configurar conexión a SFTP

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vaia a **Administrar** > **Conexións**.

1. Seleccione **Engadir conexión** e escolle **SFTP**.

1. Déalle á conexión un nome recoñecible no campo **Nome para mostrar**. O nome e o tipo de conexión describen esta conexión. Recomendamos escoller un nome que explique o propósito e o destino da conexión.

1. Escolla quen pode usar esta conexión. Por defecto, só son os administradores. Para obter máis información, consulte [Permitir aos colaboradores usar unha conexión para as exportacións](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Escolla se desexa autenticarse mediante SSH ou nome de usuario/contrasinal para a súa conexión e proporcione os detalles necesarios. Se usa unha clave SSH para a autenticación, asegúrese de que [crea a túa clave privada](/azure/virtual-machines/linux/create-ssh-keys-detailed#basic-example) como formato PEM ou SSH.COM. Se estás a usar Putty, converte a túa clave privada exportándoa como Open SSH. Admítense os seguintes formatos de clave privada:
   - RSA en OpenSSL PEM e formato ssh.com
   - DSA en formato OpenSSL PEM e ssh.com
   - ECDSA 256/384/521 en formato OpenSSL PEM
   - ED25519 e RSA en formato de chave OpenSSH

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

> [!TIP]
> A exportación de entidades que conteñen unha gran cantidade de datos pode levar a varios ficheiros CSV no mesmo cartafol para cada exportación. A división das exportacións ocorre por motivos de rendemento para minimizar o tempo que tarda en completarse unha exportación.

[!INCLUDE [footer-include](includes/footer-banner.md)]
