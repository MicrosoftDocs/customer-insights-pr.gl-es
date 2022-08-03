---
title: Use o consentimento do cliente
description: Respecta as preferencias de consentimento dos teus clientes en Customer Insights importando os datos de consentimento.
ms.date: 06/07/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 99fe24cb47a8c20f629182d9a1c6adfd36a1eaf7
ms.sourcegitcommit: c45c3e044034bf866b0662f80a59166cee4ababe
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 07/22/2022
ms.locfileid: "9188045"
---
# <a name="use-customer-consent"></a>Use o consentimento do cliente

As normas de protección de datos e privacidade ofrecen ás persoas o dereito a gobernar como unha organización utiliza os seus datos persoais. Exemplos destas normativas son o Regulamento xeral de protección de datos na Unión Europea ou a Lei de privacidade do consumidor de California nos Estados Unidos. Esta normativa permite que as persoas poidan optar por que os seus datos persoais sexan recollidos, procesados ou compartidos con terceiros.  

Os clientes poden optar por retirar ou negar o seu consentimento para formas específicas de contacto. Tamén poden solicitar que desactive a recollida, almacenamento, uso ou venda dos seus datos persoais. É importante que a túa organización respecte o consentimento de todos os clientes e as preferencias de privacidade.  

Dynamics 365 Customer Insights axúdache a cumprir as solicitudes dos teus clientes importando e almacenando as súas preferencias como parte dos perfís de clientes unificados.

Se os datos de consentimento se almacenan por separado dos seus perfís de cliente, [engade os teus datos de consentimento como un novo orixe de datos](#import-and-unify-consent-data). O orixe de datos que contén os datos de consentimento engádese ao proceso de unificación de datos. A unificación exitosa dos datos de consentimento e dos perfís de clientes leva entón a perfís de clientes unificados que conteñen a información de consentimento. Para os perfís de clientes que xa conteñen información de consentimento, vai directamente a [utilizar datos de consentimento](#use-consent-data) sección.

## <a name="prerequisites"></a>Requisitos previos

A seguinte información debe estar dispoñible nos teus datos de orixe para unificar os datos de consentimento con outros perfís de clientes:

- Clave alternativa para asignar a información de consentimento aos perfís de usuario en Customer Insights. Por exemplo, un enderezo de correo electrónico ou un número de teléfono.
- Valor do consentimento para determinar o estado do consentimento do cliente.

Considere engadir o seguinte *opcional* información:

- Chave principal para actualizar o estado do consentimento se un cliente solicita un cambio.
- Tipo de consentimento, se hai máis dunha forma de procesar a información do cliente.
- Data do consentimento ou calquera outro tipo de datos relevantes para os seus escenarios de consentimento.

Táboa de exemplo dunha base de datos de consentimento simple con varias opcións de consentimento:

|ID de consentimento (chave principal)   |Correo electrónico (clave alternativa)  |Opción de consentimento  |Valor do consentimento  |
|---------|---------|---------|---------|
|1    |  holly@contoso.com       |  Boletín informativo       |  Falso       |
|2    |  holly@contoso.com       |  Actualizacións do produto       |  Verdadeiro       |
|3    |  frank@contoso.com       |  Boletín informativo       | Verdadeiro        |
|4    |  frank@contoso.com       |  Actualizacións do produto       |  Falso       |

## <a name="import-and-unify-consent-data"></a>Importar e unificar os datos de consentimento

Importa os datos de consentimento do mesmo xeito que inxerías outras fontes de datos a Customer Insights. Para obter máis información sobre fontes de datos compatibles e como importalas, consulte [Visión xeral das fontes de datos](data-sources.md).

Para obter máis información sobre como unificar as fontes de datos, consulte [Visión xeral da unificación de datos](data-unification.md).

## <a name="use-consent-data"></a>Use os datos de consentimento

Unha vez que os teus datos de consentimento formen parte dos teus perfís de clientes unificados, podes utilizalos en Customer Insights. Por exemplo, crea un segmento cunha regra para garantir que respectas as preferencias de privacidade e protección de datos dos teus clientes. As regras que admiten as preferencias de consentimento utilízanse para excluír usuarios dun segmento en función dos atributos do perfil. Engade unha regra a un segmento que exclúa os perfís de clientes que non proporcionaron o consentimento para contactar.

Facendo referencia á táboa de exemplo anterior, un segmento podería conter esta regra:`Consent option=Newsletter & Consent value=True`. Esta configuración dá lugar a un segmento que respecta as preferencias de contacto para enviar un boletín.

Para obter máis información sobre os segmentos de construción, consulte [Crear segmentos](segment-builder.md).

Unha vez creado o segmento, podes usar un dos moitos [opcións de exportación](export-destinations.md) para usar o segmento noutras aplicacións.

## <a name="ensure-updated-consent-status"></a>Asegurar o estado de consentimento actualizado

É importante manter actualizado o estado do consentimento dos teus clientes. A actualización programada en Customer Insights sempre importa o estado máis recente das fontes de datos. Esta información é entón procesada mediante a unificación de datos e dá como resultado perfís de clientes actualizados. Estes perfís actualizados utilízanse entón para actualizar segmentos para asegurarse de que traballa coa información máis actualizada.

Noutras palabras, asegúrate de que os datos de orixe que se importan a Customer Insights sempre teñan a información máis recente.

Para obter máis información, consulte [Actualiza segmentos manualmente](segments.md#refresh-segments) ou [configurar unha actualización programada](system.md#schedule-tab).

[!INCLUDE [footer-include](includes/footer-banner.md)]
