---
title: Exportar segmentos a Facebook Xestor de anuncios (vista previa) (contén vídeo)
description: Aprenda a configurar a conexión e exportar ao Xestor de anuncios de Facebook.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 01be1a075db0da05dc5536aea8a33093f9a2ea13
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195012"
---
# <a name="export-segments-to-facebook-ads-manager-preview"></a>Exportar segmentos a Facebook Xestor de anuncios (vista previa)

Exporte segmentos de perfís de clientes unificados ao Xestor de anuncios de Facebook para crear campañas en Facebook e Instagram.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO1aN]

## <a name="prerequisites"></a>Requisitos previos

- A [Facebook Conta de anuncios](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) que inclúe a [Facebook Conta comercial](https://business.facebook.com/).
- Privilexios de administrador no [Facebook Conta de anuncios](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).

## <a name="known-limitations"></a>Limitacións coñecidas

- Ata 10 millóns de perfís de clientes por exportación a Facebook Xestor de anuncios, que pode levar ata 90 minutos.
- Só segmentos.
- Facebook *lista de clientes* escriba [audiencias personalizadas](https://www.facebook.com/business/help/744354708981227?id=2469097953376494) só.
  > [!NOTE]
  > Nalgúns casos, podes ver públicos personalizados de diferentes tipos na lista despregable. Se selecciona un tipo diferente que non sexa *lista de clientes*, a exportación falla.

## <a name="set-up-connection-to-facebook-ads-manager"></a>Configurar conexión ao xestor de anuncios de Facebook

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vaia a **Administrar** > **Conexións**.

1. Seleccione **Engadir conexión** e escolle **Facebook Xestor de anuncios**.

1. Déalle á conexión un nome recoñecible no campo **Nome para mostrar**. O nome e o tipo de conexión describen esta conexión. Recomendamos escoller un nome que explique o propósito e o destino da conexión.

1. [Permitir que os colaboradores utilicen a conexión para as exportacións](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Autenticar con anuncios de Facebook:

   1. Seleccione **Continuar con Facebook** para iniciar sesión na súa Conta de anuncios de Facebook.

   1. Permitir o permiso de **xestión_anuncios** despois de autenticarse con Facebook.

   1. Seleccione a **conta publicitaria de Facebook** coa que desexa traballar.

   1. Seleccione un **Público personalizado existente** na lista despregable ou cree un **Novo público personalizado**.

1. Revisa o [privacidade e cumprimento dos datos](connections.md#data-privacy-and-compliance) e selecciona **Estou de acordo**.

1. Seleccione **Gardar** para completar a conexión.

## <a name="configure-an-export"></a>Configurar unha exportación

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vaia a **Datos** > **Exportacións**.

1. Seleccione **Engadir exportación**.

1. No **Conexión para exportación** campo, escolla unha conexión entre Facebook Sección Xestor de anuncios. Póñase en contacto cun administrador se non hai conexión dispoñible.

1. Introduza un nome para a exportación.

1. No **Conectar datos** campo, seleccione **Correo electrónico**, **e enderezo**, ou **Teléfono** enviar a Facebook Xestor de anuncios.

1. Asigne os atributos correspondentes desde a súa entidade de cliente unificada para o identificador de clave seleccionado.
   > [!TIP]
   > As mellores posibilidades de coincidencia danse se selecciona **Correo electrónico** como identificador clave. Se engade identificadores adicionais pode mellorar a coincidencia.

1. Seleccione **Engadir atributo** para asignar máis atributos para envialos ao Xestor de anuncios de Facebook. Os atributos do Administrador de anuncios de Facebook asígnanse aos seguintes nomes descritivos de usuario: **FN** = **Nome**, **LN** = **Apelidos**, **FI** = **Inicial nome**, **PHONE** = **Teléfono**, **GEN** = **Sexo**, **DOB** = **Data de nacemento**, **ST** = **Estado**, **CT** = **Cidade**, **ZIP** = **Código postal**, **COUNTRY** = **País/rexión**

1. Seleccione os segmentos que desexa exportar.

1. Seleccione **Gardar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
