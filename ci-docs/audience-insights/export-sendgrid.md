---
title: Exportar datos de Customer Insights a SendGrid
description: Aprenda a configurar a conexión e exportar a SendGrid.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 03df2ab5fce1da1f4f662e1975533f2b538b47dbdd5cf96aae4f1007163e3729
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036099"
---
# <a name="export-segments-to-sendgrid-preview"></a>Exportar segmentos a SendGrid (versión preliminar)

Exporte segmentos de perfís de clientes unificados a listas de contactos de SendGrid e utilíceos para campañas e mercadotecnia por correo electrónico en SendGrid. 

## <a name="prerequisites-for-a-connection"></a>Requisitos previos para unha conexión

-   Ten unha [Conta de SendGrid](https://sendgrid.com/) e as correspondentes credenciais de administrador.
-   Existen listas de contacto en SendGrid e os ID correspondentes. Para obter máis información, consulte [SendGrid: xestionar contactos](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).
-   Ten [segmentos configurados](segments.md) na información do público.
-   Os perfís de clientes unificados nos segmentos exportados conteñen un campo que representa un enderezo de correo electrónico.

## <a name="known-limitations"></a>Limitacións coñecidas

- Ata 100.000 perfís en total en SendGrid.
- A exportación a SendGrid está limitada a segmentos.
- Exportar ata 100.000 perfís a SendGrid pode tardar unhas horas en completarse. 
- O número de perfís que pode exportar a SendGrid depende e está limitado no seu contrato con SendGrid.

## <a name="set-up-connection-to-sendgrid"></a>Configurar conexión a SendGrid

1. Vaia a **Administrar** > **Conexións**.

1. Seleccione **Engadir conexión** e elixa **SendGrid** para configurar a conexión.

1. Déalle á conexión un nome recoñecible no campo **Nome para mostrar**. O nome e o tipo de conexión describen esta conexión. Recomendamos escoller un nome que explique o propósito e o destino da conexión.

1. Escolla quen pode usar esta conexión. Se non realiza ningunha acción, o valor predeterminado será Administradores. Para obter máis información, consulte [Permitir aos colaboradores usar unha conexión para as exportacións](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Introduza a súa **Clave da API de SendGrid** [Clave da API de SendGrid](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).

1. Seleccione **Estou de acordo** para confirmar a **Privacidade e cumprimento dos datos**.

1. Seleccione **Conectar** para inicializar a conexión a SendGrid.

1. Seleccione **Autoengadirse como usuario de exportación** e proporcione as súas credenciais de Customer Insights.

1. Seleccione **Gardar** para completar a conexión.

## <a name="configure-an-export"></a>Configurar unha exportación

Pode configurar esta exportación se ten acceso a unha conexión deste tipo. Para obter máis información, consulte [Permisos necesarios para configurar unha exportación](export-destinations.md#set-up-a-new-export).

1. Vaia a **Datos** > **Exportacións**.

1. Seleccione **Engadir destino** para crear unha nova exportación.

1. No campo **Conexión da exportación** escolla unha conexión da sección SendGrid. Se non ve o nome desta sección, non hai conexións deste tipo dispoñibles para vostede.

1. Introduza o seu **[ID de lista de SendGrid](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.

1. Na sección **Coincidencia de datos**, no campo **Correo electrónico**, seleccione o campo do seu perfil de cliente unificado que representa o enderezo de correo electrónico dun cliente. Repita os mesmos pasos para outros campos opcionais como **nome**, **apelidos**, **país/rexión**, **estado**, **cidade** e **código postal**.

1. Seleccione os segmentos que desexa exportar. Nós fortemente **recomendamos non exportar máis de 100.000 perfís de clientes en total** a SendGrid. 

1. Seleccione **Gardar**.

Ao gardar unha exportación non se executa a exportación inmediatamente.

A exportación execútase con cada [actualización programada](system.md#schedule-tab). Tamén pode [exportar datos baixo demanda](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Cumprimento e privacidade dos datos

Cando habilita Dynamics 365 Customer Insights para transmitir datos a SendGrid, permite a transferencia de datos fóra do límite de cumprimento de Dynamics 365 Customer Insights, incluíndo datos potencialmente confidenciais como os datos persoais. Microsoft transferirá estes datos segundo a súa instrución, pero vostede é responsable de garantir que SendGrid cumpra as obrigas de privacidade ou seguridade que poida ter. Para obter máis información, consulte a [Declaración de privacidade de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
O administrador de Dynamics 365 Customer Insights pode eliminar este destino de exportación en calquera momento para interromper o uso desta funcionalidade.


[!INCLUDE[footer-include](../includes/footer-banner.md)]