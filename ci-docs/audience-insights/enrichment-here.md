---
title: Enriquecemento co enriquecemento de terceiros de HERE Technologies
description: Información xeral sobre o enriquecemento de terceiros de HERE Technologies.
ms.date: 12/10/2020
ms.reviewer: jodahl
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 258e37de9d9685d9ebc30b3c6b8d238d583431b4
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269512"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a>Enriquecemento de perfís de clientes con HERE Technologies (vista previa)

HERE Technologies é unha empresa de plataformas de localización que ofrece servizos e datos centrados na situación. Cos servizos de enriquecemento de datos de HERE Technologies, pode construír unha comprensión máis precisa da situación dos seus clientes coa normalización de enderezos, a extracción de latitude e lonxitude e moito máis.

## <a name="prerequisites"></a>Requisitos previos

Para configurar os enriquecementos de HERE Technologies, deben cumprirse os seguintes requisitos previos:

- Ten unha subscrición activa de HERE Technologies. Para obter unha subscrición, pode [inscribirse aquí](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) ou [poñerse en contacto con HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directamente. [Obteña máis información sobre o enriquecemento de localización de HERE Technologies.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- Ten a clave da API de HERE Technologies.

- Ten permisos de [administrador](permissions.md#administrator).

## <a name="configuration"></a>Configuración

1. Vaia a **Datos** > **Enriquecemento**.

1. No mosaico de HERE Technologies, seleccione **Enriquecer os meus datos**.

   > [!div class="mx-imgBorder"]
   > ![Mosaico de HERE Technologies](media/HERE-tile.png "Mosaico de HERE Technologies")

1. Insira unha **clave da API de HERE Technologies** activa. Revise e proporcione o seu consentimento para a **Privacidade e cumprimento dos datos** seleccionando a caixa de verificación **Estou de acordo**. 

1. Confirme ambas as entradas seleccionando **Conectarse a HERE**.

1.  Seleccione **Engadir datos** e escolla o **conxunto de datos de cliente** que desexa enriquecer coa localización de HERE Technologies. Pode seleccionar a entidade **Cliente** para enriquecer todos os seus perfís de clientes ou seleccione unha entidade de segmento para enriquecer só os perfís de clientes contidos nese segmento.

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="Captura de pantalla ao escoller o conxunto de datos do cliente.":::

1. Escolla se desexa asignar campos ao enderezo principal e/ou secundario. Pode especificar unha asignación de campo para ambos os enderezos (por exemplo, un enderezo de casa e un de empresa) e enriquecer os perfís de ambos os enderezos por separado. Seleccione **Seguinte**.

1. Defina os campos dos perfís unificados que se deben empregar para buscar datos de localización coincidentes de HERE Technologies. Os campos **Rúa 1** e **Código postal** son obrigatorios para o enderezo primario e/ou secundario seleccionado. Para unha maior precisión de coincidencia, pódense engadir máis campos.

   > [!div class="mx-imgBorder"]
   > ![Páxina de configuración de enriquecemento de HERE Technologies](media/enrichment-HERE-configuration.png "Páxina de configuración de enriquecemento de HERE Technologies")

1. Seleccione **Aplicar** para completar a asignación de campos.

## <a name="enrichment-results"></a>Resultados de enriquecemento

Para iniciar o proceso de enriquecemento, seleccione **Executar** na barra de comandos. Tamén pode deixar que o sistema execute o enriquecemento automaticamente como parte dunha [actualización programada](system.md#schedule-tab). O tempo de procesamento dependerá do tamaño dos datos dos seus clientes e dos tempos de resposta da API de HERE Technologies.

Despois de completar o proceso de enriquecemento, pode consultar os datos dos perfís de clientes recentemente enriquecidos en **Os meus enriquecementos**. Ademais, atopará a hora da última actualización e o número de perfís enriquecidos.

Pode acceder a unha vista detallada de cada perfil enriquecido seleccionando **Ver datos enriquecidos**.

## <a name="next-steps"></a>Pasos seguintes

Crear sobre os seus datos enriquecidos de clientes. Cree [segmentos](segments.md), [medidas](measures.md) e incluso [exporte os datos](export-destinations.md) para ofrecer experiencias personalizadas aos seus clientes.

## <a name="data-privacy-and-compliance"></a>Cumprimento e privacidade dos datos

Cando habilita Dynamics 365 Customer Insights para transmitir datos a HERE Technologies, permite a transferencia de datos fóra do límite de cumprimento de Dynamics 365 Customer Insights, incluíndo datos potencialmente confidenciais como os datos persoais. Microsoft transferirá estes datos segundo a súa instrución, pero vostede é responsable de garantir que HERE Technologies cumpra as obrigas de privacidade ou seguridade que poida ter. Para obter máis información, consulte a [Declaración de privacidade de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
O administrador de Dynamics 365 Customer Insights pode eliminar este enriquecemento en calquera momento para interromper o uso desta funcionalidade.


[!INCLUDE[footer-include](../includes/footer-banner.md)]