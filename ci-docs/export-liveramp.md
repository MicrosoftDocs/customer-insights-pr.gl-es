---
title: Exportar segmentos a LiveRamp (versión preliminar)
description: Aprenda a configurar a conexión e a exportación a LiveRamp.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 55eacea3af83f46583a3a43797d625479f56586b
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196714"
---
# <a name="export-segments-to-liverampreg-preview"></a>Exportar segmentos a LiveRamp&reg; (versión preliminar)

Active os seus datos en LiveRamp para conectar con máis de 500 plataformas dixitais, sociais e televisivas. Traballe cos seus datos en LiveRamp para orientar, suprimir e personalizar as campañas publicitarias.

## <a name="prerequisites"></a>Requisitos previos

- Unha subscrición a LiveRamp para usar este conector. Para obter unha subscrición, [contacte con LiveRamp](https://liveramp.com/contact/) directamente. [Obteña máis información sobre LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).

## <a name="known-limitations"></a>Limitacións coñecidas

- A exportación LiveRamp está usando unha exportación SFTP. Os destinos SFTP detrás dos cortalumes non son compatibles actualmente.
- Se usa unha clave SSH para a autenticación, asegúrese de que [crea a túa clave privada](/azure/virtual-machines/linux/create-ssh-keys-detailed#basic-example) como formato PEM ou SSH.COM. Se estás a usar Putty, converte a túa clave privada exportándoa como Open SSH. Admítense os seguintes formatos de clave privada:
  - RSA en OpenSSL PEM e formato ssh.com
  - DSA en formato OpenSSL PEM e ssh.com
  - ECDSA 256/384/521 en formato OpenSSL PEM
  - ED25519 e RSA en formato de chave OpenSSH
- O tempo de execución dunha exportación depende do rendemento do seu sistema. Recomendamos dous núcleos de CPU e 1 Gb de memoria como configuración mínima do seu servidor.
- As entidades exportadoras con ata 100 millóns de perfís de clientes poden tardar 90 minutos cando se usa a configuración mínima recomendada de dous núcleos de CPU e 1 Gb de memoria.
- O número real de perfís (ou datos) que podes exportar a LiveRamp depende da túa subscrición a LiveRamp.

## <a name="set-up-connection-to-liveramp"></a>Configurar conexión a LiveRamp

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vaia a **Administrar** > **Conexións**.

1. Seleccione **Engadir conexión** e escolle **LiveRamp**.

1. Déalle á conexión un nome recoñecible no campo **Nome para mostrar**. O nome e o tipo de conexión describen esta conexión. Recomendamos escoller un nome que explique o propósito e o destino da conexión.

1. Escolla quen pode usar esta conexión. Por defecto, só son os administradores. Para obter máis información, consulte [Permitir aos colaboradores usar unha conexión para as exportacións](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Escolla se desexa autenticarse mediante SSH ou nome de usuario/contrasinal para a súa conexión e proporcione os detalles necesarios.

1. Seleccione **Verificar** para probar a conexión a LiveRamp.

1. Despois da verificación exitosa, revise [privacidade e cumprimento dos datos](connections.md#data-privacy-and-compliance) e selecciona **Estou de acordo**.

1. Seleccione **Gardar** para completar a conexión.

## <a name="configure-an-export"></a>Configurar unha exportación

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vaia a **Datos** > **Exportacións**.

1. Seleccione **Engadir exportación**.

1. No campo **Conexión da exportación** escolla unha conexión da sección LiveRamp. Póñase en contacto cun administrador se non hai conexión dispoñible.

1. Introduza un nome para a exportación.

1. No **Conectar datos** campo, seleccione **Correo electrónico**, **e enderezo**, ou **Teléfono** para enviar a LiveRamp para resolución de identidade.

   :::image type="content" source="media/export-liveramp-segments.png" alt-text="Conector LiveRamp con asignación de atributos.":::

1. Asigna os atributos correspondentes da súa entidade de *Cliente* para o identificador de clave seleccionado.

1. Seleccione **Engadir atributo** para asignar máis atributos para envialos a LiveRamp.

   > [!TIP]
   > O envío de máis atributos de identificador clave a LiveRamp é probable que provoque a obtención dunha taxa de coincidencia máis alta.

1. Seleccione os segmentos que desexa exportar.

1. Seleccione **Gardar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
