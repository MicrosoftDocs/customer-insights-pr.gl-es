---
title: Exportar datos de Customer Insights ao Xestor de anuncios de Facebook
description: Aprenda a configurar a conexión ao Xestor de anuncios de Facebook.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c839f9dc7e403412c0e3d936392d45a43bc63545
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269972"
---
# <a name="connector-for-facebook-ads-manager-preview"></a>Conector para o Xestor de anuncios de Facebook (vista previa)

Exporte segmentos de perfís de clientes unificados ao Xestor de anuncios de Facebook para crear campañas en Facebook e Instagram.

## <a name="prerequisites"></a>Requisitos previos

- Debe ter unha [**Conta de anuncios de Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) que inclúa unha [**Conta empresarial de Facebook**](https://business.facebook.com/).
- Debe ser administrador na [**Conta de anuncios de Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).

## <a name="connect-to-facebook-ads-manager"></a>Conectarse ao Xestor de anuncios de Facebook

1. Vaia a **Administrador** > **Exportar destinos**.

1. En **Xestor de anuncios de Facebook** seleccione **Configurar**.

1. Déalle ao seu destino da exploración un nome recoñecible no campo **Nome para mostrar**.

1. Seleccione **Continuar con Facebook** para iniciar sesión na súa Conta de anuncios de Facebook.

1. Permitir o permiso de **xestión_anuncios** despois de autenticarse con Facebook.

1. Seleccione a **conta publicitaria de Facebook** coa que desexa traballar.

1. Seleccione un **Público personalizado existente** da lista despregable ou cree un **Novo público personalizado**. Para obter máis información, consulte [**Públicos no Xestor de anuncios de Facebook**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).

1. Seleccione **Estou de acordo** para confirmar a **Privacidade e cumprimento dos datos**.

1. Seleccione **Seguinte** para configurar a exportación.

## <a name="configure-the-connector"></a>Configurar o conector

1. No **campo Escoller o identificador clave**, seleccione **Correo electrónico**, **Nome e enderezo** ou **Teléfono** para enviar ao Xestor de anuncios de Facebook.

1. Asigne os atributos correspondentes desde a súa entidade de cliente unificada para o identificador de clave seleccionado.
   > [CONSELLO] As mellores posibilidades de coincidencia danse se selecciona **Correo electrónico** como identificador clave. Se engade identificadores adicionais pode mellorar a coincidencia.

1. Seleccione **Engadir atributo** para asignar atributos adicionais que enviar ao Xestor de anuncios de Facebook. Os atributos do Administrador de anuncios de Facebook asígnanse aos seguintes nomes amigables de usuario: **FN** = **Nome**, **LN** = **Apelidos**, **FI** = **Inicial nome**, **PHONE** = **Teléfono**, **GEN** = **Sexo**, **DOB** = **Data de nacemento**, **ST** = **Estado**, **CT** = **Cidade**, **ZIP** = **Código postal**, **COUNTRY** = **País/rexión**

1. Seleccione os segmentos que desexa exportar.

1. Seleccione **Gardar**.

## <a name="export-the-data"></a>Exportar os datos

Pode [exportar datos baixo demanda](export-destinations.md). A exportación tamén se executará con todas as [actualizacións programadas](system.md#schedule-tab).

## <a name="known-limitations"></a>Limitacións coñecidas

- Ata 10 millóns de perfís de clientes por exportación ao Xestor de anuncios de Facebook 
- A exportación ao Xestor de anuncios de Facebook está limitada a segmentos
- A exportación de segmentos cun total de 10 millón de perfís pode tardar ata 90 minutos en finalizar

## <a name="data-privacy-and-compliance"></a>Cumprimento e privacidade dos datos

Cando habilita Dynamics 365 Customer Insights para transmitir datos ao xestor de anuncios de Facebook, permite a transferencia de datos fóra do límite de cumprimento de Dynamics 365 Customer Insights, incluíndo datos potencialmente confidenciais como os datos persoais. Microsoft transferirá estes datos segundo a súa instrución, pero vostede é responsable de garantir que Anuncios de Facebook cumpra as obrigas de privacidade ou seguridade que poida ter. Para obter máis información, consulte a [Declaración de privacidade de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
O administrador de Dynamics 365 Customer Insights pode eliminar este destino de exportación en calquera momento para interromper o uso desta funcionalidade.


[!INCLUDE[footer-include](../includes/footer-banner.md)]