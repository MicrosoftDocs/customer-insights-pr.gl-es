---
title: Enriquece os perfís da empresa con Leadspace (vista previa)
description: Información xeral sobre o enriquecemento de terceiros de Leadspace.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: b58532a541ee22a5e34d0af1a3334ccbd53627b2
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082363"
---
# <a name="enrich-company-profiles-with-leadspace-preview"></a>Enriquece os perfís da empresa con Leadspace (vista previa)

Leadspace é unha empresa de ciencia de datos que ofrece unha plataforma de datos de clientes B-a-B. Permite que os ambientes con perfís de clientes unificados baseados en contas enriquezan os seus datos. Enriqueza *Perfís de clientes* con atributos como o tamaño da empresa, a localización ou a industria. Enriqueza *Perfís de contacto* con atributos como o título, a persoa ou a verificación por correo electrónico.

## <a name="prerequisites"></a>Requisitos previos

- Unha licenza Leadspace activa.
- [Perfís de clientes unificados](customer-profiles.md) baseado en contas.
- Un Leadspace [conexión](connections.md) é [configurado](#configure-the-connection-for-leadspace) por un administrador. Contacte con [Leadspace](https://www.leadspace.com/leadspace-microsoft-dynamics-365/) directamente para obter detalles sobre o seu produto.

## <a name="configure-the-connection-for-leadspace"></a>Configurar a conexión para Leadspace

Debes ser un [administrador](permissions.md#admin) en Customer Insights e ten a "chave perpetua" (referida como **Token de Leadspace**).

1. Seleccione **Engadir conexión** ao configurar un enriquecemento ou ir a **Admin** > **Conexións** e selecciona **Montar** no mosaico Leadspace.

   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Páxina de configuración da conexión de Leadspace.":::

1. Introduza un nome para a conexión e un token de Leadspace válido.

1. Revise e proporcione o seu consentimento para a [Privacidade e cumprimento de datos](#data-privacy-and-compliance) seleccionando **Estou de acordo**.

1. Seleccione **Verificar** para validar a configuración e, a continuación, seleccione **Gardar**.

### <a name="data-privacy-and-compliance"></a>Cumprimento e privacidade dos datos

Cando habilita Dynamics 365 Customer Insights para transmitir datos a Leadspace, permite a transferencia de datos fóra do límite de cumprimento de Dynamics 365 Customer Insights, incluíndo datos potencialmente confidenciais como os datos persoais. Microsoft transferirá estes datos segundo a súa instrución, pero vostede é responsable de garantir que Leadspace cumpra as obrigas de privacidade ou seguridade que poida ter. Para obter máis información, consulte a [Declaración de privacidade de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
O administrador de Dynamics 365 Customer Insights pode eliminar este enriquecemento en calquera momento para interromper o uso desta funcionalidade.

## <a name="configure-the-enrichment"></a>Configurar o enriquecemento

1. Vaia a **Datos** > **Enriquecemento** e seleccione o separador **Descubrir**.

1. Seleccione **Enriquece os meus datos** no **Datos da empresa** do mosaico de Leadspace.

   :::image type="content" source="media/leadspace-tile.png" alt-text="Captura de pantalla do mosaico de Leadspace.":::

1. Revisa a vista xeral e, a continuación, selecciona **A continuación**.

1. Seleccione a conexión. Póñase en contacto cun administrador se non está dispoñible.

1. Seleccione **Seguinte**.

1. Seleccione o **Conxunto de datos do cliente** e escolle o perfil ou segmento que queres enriquecer cos datos da empresa de Leadspace. O *Cliente* a entidade enriquece todos os seus perfís de clientes mentres que un segmento enriquece só os perfís de clientes contidos nese segmento.

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Captura de pantalla ao escoller o conxunto de datos do cliente.":::

1. Define que tipo de campos dos teus perfís unificados queres usar para a correspondencia: o enderezo principal e/ou secundario. Pode especificar unha asignación de campos para ambos os enderezos e enriquecer os perfís de ambos os enderezos por separado. Por exemplo, para un enderezo de casa e un enderezo de empresa. Seleccione **Seguinte**.

1. Asigne os seus campos aos datos da empresa de Leadspace. O campo **Nome da empresa** é obrigatorio. Para unha maior precisión de coincidencia, ata outros dous campos, **Páxina web da empresa** e **Localización da empresa**, pódense engadir.

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Panel de asignación de campos de Leadspace.":::

1. Seleccione **Seguinte** para concluír a asignación do campo.

1. Marque a caixa de verificación se ten *Perfís de contacto* que lle gustaría enriquecer. Customer Insights asignará automaticamente os campos obrigatorios.

   :::image type="content" source="media/enrichment-leadspace-contacts.png" alt-text="Enriquecemento de rexistros de contacto de Leadspace.":::

1. Seleccione **Seguinte**.

1. Proporcionar a **Nome** para o enriquecemento e o **Nome da entidade de saída**.

1. Seleccione **Gardar enriquecemento** despois de revisar as súas opcións.

1. Seleccione **Corre** para iniciar o proceso de enriquecemento ou pechar para volver ao **Enriquecementos** páxina.

## <a name="view-enrichment-results"></a>Ver resultados de enriquecemento

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Para obter máis información, consulte [API de Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).

## <a name="next-steps"></a>Pasos seguintes

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
