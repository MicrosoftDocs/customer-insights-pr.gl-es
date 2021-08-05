---
title: Exportar datos de Customer Insights a Constant Contact
description: Aprenda a configurar a conexión e exportar a Constant Contact.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b54659f028a141fe8f351645d96e933d47568a39
ms.sourcegitcommit: adb9c43ddaba25e511535d78a4bcf8815f154a7b
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 07/06/2021
ms.locfileid: "6362416"
---
# <a name="export-segments-to-constant-contact-preview"></a>Exportar segmentos a Constant Contact (versión preliminar)

Exporte segmentos de perfís de clientes unificados a Constant Contact e utilíceos para actividades de mercadotecnia. 

## <a name="prerequisites-for-a-connection"></a>Requisitos previos para unha conexión

-   Ten unha [conta de Constant Contact](https://www.constantcontact.com/account-home) e as correspondentes credenciais de administrador.
-   Ten [segmentos configurados](segments.md) na información do público.
-   Os perfís de clientes unificados nos segmentos exportados conteñen un campo que representa un enderezo de correo electrónico.

## <a name="known-limitations"></a>Limitacións coñecidas

- Pode exportar ata 1 millón de perfís por exportación a Constant Contact.
- A exportación a Constant Contact está limitada a segmentos.
- A exportación de segmentos de ata 1 millón de perfís a Constant Contact pode tardar ata 1 hora en finalizar. 
- O número de perfís que pode exportar a Constant Contact depende e está limitado ao seu contrato con Constant Contact.

## <a name="set-up-connection-to-constant-contact"></a>Configurar a conexión a Constant Contact

1. Vaia a **Administrar** > **Conexións**.

1. Seleccione **Engadir conexión** e elixa **Constant Contact** para configurar a conexión.

1. Déalle á conexión un nome recoñecible no campo **Nome para mostrar**. O nome e o tipo de conexión describen esta conexión. Recomendamos escoller un nome que explique o propósito e o destino da conexión.

1. Escolla quen pode usar esta conexión. Se non realiza ningunha acción, o valor predeterminado será Administradores. Para obter máis información, consulte [Permitir aos colaboradores usar unha conexión para as exportacións](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Seleccione **Estou de acordo** para confirmar a **Privacidade e cumprimento dos datos**.

1. Seleccione **Conectar** para iniciar a conexión a Constant Contact.

1. Seleccione **Autenticar con Constant Contact** e proporcione as súas credenciais de administrador de Constant Contact. 

1. Seleccione **Autoengadirse como usuario de exportación** e proporcione as súas credenciais de Customer Insights.

1. Seleccione **Gardar** para completar a conexión.

## <a name="configure-an-export"></a>Configurar unha exportación

Pode configurar esta exportación se ten acceso a unha conexión deste tipo. Para obter máis información, consulte [Permisos necesarios para configurar unha exportación](export-destinations.md#set-up-a-new-export).

1. Vaia a **Datos** > **Exportacións**.

1. Seleccione **Engadir destino** para crear unha nova exportación.

1. No campo **Conexión da exportación** escolla unha conexión da sección Constant Contact. Se non ve o nome desta sección, non hai conexións deste tipo dispoñibles para vostede.

1. Insira o seu [**ID de lista Constant Contact**](https://app.constantcontact.com/pages/contacts/ui#lists). Abra unha lista en Constant Contact para atopar o ID da lista no URL.

1. Na sección **Coincidencia de datos**, no campo **Correo electrónico**, seleccione o campo do seu perfil de cliente unificado que representa o enderezo de correo electrónico dun cliente. É necesario exportar segmentos a Constant Contact.

1. Opcionalmente, pode exportar o nome e os apelidos como campos adicionais para crear correos electrónicos máis personalizados. Seleccione **Engadir atributo** para asignar estes campos.

1. Seleccione os segmentos que desexa exportar.

1. Seleccione **Gardar**.

Ao gardar unha exportación non se executa a exportación inmediatamente.

A exportación execútase con cada [actualización programada](system.md#schedule-tab). Tamén pode [exportar datos baixo demanda](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Cumprimento e privacidade dos datos

Cando habilita Dynamics 365 Customer Insights para transmitir datos a Constant Contact, permite a transferencia de datos fóra do límite de cumprimento de Dynamics 365 Customer Insights, incluíndo datos potencialmente confidenciais como os datos persoais. Microsoft transferirá estes datos segundo a súa instrución, pero vostede é responsable de asegurarse de que Constant Contact cumpra as obrigas de privacidade ou seguridade que poida ter. Para obter máis información, consulte a [Declaración de privacidade de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

O administrador de Dynamics 365 Customer Insights pode eliminar este destino de exportación en calquera momento para interromper o uso desta funcionalidade.
