---
title: Exportar datos de Customer Insights a Facebook Xestor de anuncios (contén vídeo)
description: Aprenda a configurar a conexión e exportar ao Xestor de anuncios de Facebook.
ms.date: 04/15/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 781cf10e1bb5ddaf82d4a17c7a77e0c43c41a1c2
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 02/16/2022
ms.locfileid: "8226493"
---
# <a name="export-segments-list-to-facebook-ads-manager-preview"></a>Exportar lista de segmentos ao Xestor de anuncios de Facebook (versión preliminar)

Exporte segmentos de perfís de clientes unificados ao Xestor de anuncios de Facebook para crear campañas en Facebook e Instagram.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO1aN]

## <a name="prerequisites-for-connection"></a>Requisitos previos para a conexión

- Debe ter unha [**conta publicitaria de Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) que inclúa unha [**conta empresarial de Facebook**](https://business.facebook.com/).
- Debe ser administrador da [**Conta de anuncios de Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).

## <a name="known-limitations"></a>Limitacións coñecidas

- Ata 10 millóns de perfís de clientes por exportación ao Xestor de anuncios de Facebook.
- A exportación ao Xestor de anuncios de Facebook está limitada a segmentos.
- Cree ou actualice audiencias personalizadas en Facebook de tipo *lista de clientes* só.
- A exportación de segmentos cun total de 10 millón de perfís de clientes pode levar ata 90 minutos en completarse.

## <a name="set-up-connection-to-facebook-ads-manager"></a>Configurar conexión ao xestor de anuncios de Facebook

Antes de que os usuarios poidan crear unha exportación, un administrador debe configurar a conexión ao servizo e permitir aos colaboradores que utilicen a conexión.

1. Vaia a **Administrar** > **Conexións**.

1. Seleccione **Engadir conexión** e elixa **Xestor de anuncios de Facebook** para configurar a conexión.

1. Déalle á conexión un nome recoñecible no campo **Nome para mostrar**. O nome e o tipo de conexión describen esta conexión. Recomendamos escoller un nome que explique o propósito e o destino da conexión.

1. Escolla quen pode usar esta conexión. Se non realiza ningunha acción, o valor predeterminado será Administradores. Para obter máis información, consulte [Permitir aos colaboradores usar unha conexión para as exportacións](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Autenticar con anuncios de Facebook: 

   1. Seleccione **Continuar con Facebook** para iniciar sesión na súa Conta de anuncios de Facebook.

   1. Permitir o permiso de **xestión_anuncios** despois de autenticarse con Facebook.

   1. Seleccione a **conta publicitaria de Facebook** coa que desexa traballar.

   1. Seleccione un **Público personalizado existente** na lista despregable ou cree un **Novo público personalizado**. Para obter máis información, consulte [**Públicos no Xestor de anuncios de Facebook**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).
      > [!NOTE]
      > Só pode crear ou actualizar públicos personalizados eb Facebook do tipo *lista de clientes* con esta exportación. Nalgúns casos, ve audiencias personalizadas de diferentes tipos na lista despregable. Seleccionar un tipo diferente á *lista de clientes* producirá un fallo na exportación. 

1. Revise a **Privacidade dos datos e cumprimento** e seleccione **Estou de acordo**.

1. Seleccione **Gardar** para completar a conexión.

## <a name="configure-an-export"></a>Configurar unha exportación

Pode configurar esta exportación se ten acceso a unha conexión deste tipo. Para obter máis información, consulte [Permisos necesarios para configurar unha exportación](export-destinations.md#set-up-a-new-export).

1. Vaia a **Datos** > **Exportacións**.

1. Seleccione **Engadir destino** para crear unha nova exportación. 

1. En **Conexión da exportación** escolla unha conexión da sección **Xestor de anuncios de Facebook**. Se non ve o nome desta sección, non ten ningunha conexión deste tipo dispoñible.

1. No **campo Escoller o identificador clave**, seleccione **Correo electrónico**, **Nome e enderezo** ou **Teléfono** para enviar ao Xestor de anuncios de Facebook. 

1. Déalle á conexión un nome recoñecible no campo **Nome para mostrar**.

1. Asigne os atributos correspondentes desde a súa entidade de cliente unificada para o identificador de clave seleccionado.
   > [!TIP]
   > As mellores posibilidades de coincidencia danse se selecciona **Correo electrónico** como identificador clave. Se engade identificadores adicionais pode mellorar a coincidencia.

1. Seleccione **Engadir atributo** para asignar máis atributos para envialos ao Xestor de anuncios de Facebook. Os atributos do Administrador de anuncios de Facebook asígnanse aos seguintes nomes descritivos de usuario: **FN** = **Nome**, **LN** = **Apelidos**, **FI** = **Inicial nome**, **PHONE** = **Teléfono**, **GEN** = **Sexo**, **DOB** = **Data de nacemento**, **ST** = **Estado**, **CT** = **Cidade**, **ZIP** = **Código postal**, **COUNTRY** = **País/rexión**

1. Seleccione os segmentos que desexa exportar.

1. Seleccione **Gardar**.

Ao gardar unha exportación non se executa a exportación inmediatamente.

A exportación execútase con cada [actualización programada](system.md#schedule-tab). 

Tamén pode [exportar datos baixo demanda](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Cumprimento e privacidade dos datos

Cando habilita Dynamics 365 Customer Insights para transmitir datos ao xestor de anuncios de Facebook, permite a transferencia de datos fóra do límite de cumprimento de Dynamics 365 Customer Insights, incluíndo datos potencialmente confidenciais como os datos persoais. Microsoft transferirá estes datos segundo a súa instrución, pero vostede é responsable de garantir que Anuncios de Facebook cumpra as obrigas de privacidade ou seguridade que poida ter. Para obter máis información, consulte a [Declaración de privacidade de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
O administrador de Dynamics 365 Customer Insights pode eliminar este destino de exportación en calquera momento para interromper o uso desta funcionalidade.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
