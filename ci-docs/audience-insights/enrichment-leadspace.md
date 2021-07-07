---
title: Enriquecemento de perfís de empresa co enriquecemento de terceiros de Leadspace
description: Información xeral sobre o enriquecemento de terceiros de Leadspace.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 0496d10c994cd077a778a6e745e3774e316765ae
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305200"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a>Enriquecemento de perfís de empresa con Leadspace (vista previa)

Leadspace é unha empresa de ciencia de datos que proporciona unha plataforma de datos de clientes B2B. Permite aos clientes con perfís de clientes unificados para empresas enriquecer os seus datos. Os enriquecementos inclúen máis atributos, como o tamaño da empresa, a localización o sector e moito máis.

## <a name="prerequisites"></a>Requisitos previos

Para configurar Leadspace, deben cumprirse os seguintes requisitos previos:

- Ten unha licenza de Leadspace activa.
- Ten [perfís de clientes unificados](customer-profiles.md) para empresas.
- Un administrador xa configurou unha conexión de Leadspace ou vostede ten permisos de [administrador](permissions.md#administrator) e a "clave perpetua" (denominada **Token de Leadspace**). Contacte con [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) directamente para obter detalles sobre o seu produto.

## <a name="configure-the-enrichment"></a>Configurar o enriquecemento

1. Na información do público, vaia a **Datos** > **Enriquecemento**.

1. No mosaico de Leadspace, seleccione **Enriquecer os meus datos** e logo seleccione **Comezar**.

   :::image type="content" source="media/leadspace-tile.png" alt-text="Captura de pantalla do mosaico de Leadspace.":::

1. Seleccione unha [conexión](connections.md) da lista despregable. Póñase en contacto cun administrador se non hai conexión dispoñible. Se é administrador, pode crear unha conexión seleccionando **Engadir conexión** e escollendo **Leadspace**. 

1. Seleccione **Conectar con Leadspace** para confirmar a conexión.

1. Seleccione **Seguinte** e escolla o **Conxunto de datos do cliente** que quere enriquecer cos datos da empresa de Leadspace. Pode seleccionar a entidade **Cliente** para enriquecer todos os seus perfís de clientes ou seleccione unha entidade de segmento para enriquecer só os perfís de clientes contidos nese segmento.

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Captura de pantalla ao escoller o conxunto de datos do cliente.":::

1. Seleccione **Seguinte** e defina os campos dos perfís unificados que se usan para buscar os datos da empresa coincidentes de Leadspace. O campo **Nome da empresa** é obrigatorio. Para unha maior precisión de coincidencia, ata outros dous campos, **Páxina web da empresa** e **Localización da empresa**, pódense engadir.

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Panel de asignación de campos de Leadspace.":::

1. Seleccione **Seguinte** para concluír a asignación do campo.

1. Indique un nome para o enriquecemento e seleccione **Gardar enriquecemento** despois de revisar as súas opcións.


## <a name="configure-the-connection-for-leadspace"></a>Configurar a conexión para Leadspace 

Debe ser administrador para configurar as conexións. Seleccione **Engadir conexión** ao configurar un enriquecemento *ou* vaia a **Administrar** > **Conexións** e seleccione **Configurar** no mosaico de Leadspace.

1. Seleccione **Comezar**. 

1. Introduza un nome para a conexión na caixa **Nome de visualización**.

1. Forneza un token de Leadspace válido.

1. Revise e proporcione o seu consentimento para a **Privacidade e cumprimento de datos** seleccionando **Estou de acordo**.

1. Seleccione **Verificar** para validar a configuración.

1. Despois de completar a verificación, seleccione **Gardar**.
   
   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Páxina de configuración da conexión de Leadspace.":::

## <a name="enrichment-results"></a>Resultados de enriquecemento

Despois de actualizar o enriquecemento, pode revisar os datos da empresa enriquecidos recentemente en [Os meus enriquecementos](enrichment-hub.md). Pode atopar a hora da última actualización e o número de perfís enriquecidos.

Pode acceder a unha vista detallada de cada perfil enriquecido seleccionando **Ver datos enriquecidos**.

Para obter máis información, consulte [API de Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).

## <a name="next-steps"></a>Pasos seguintes

Crear sobre os seus datos enriquecidos de clientes. Cree [segmentos](segments.md) e [medidas](measures.md), e incluso [exporte os datos](export-destinations.md) para ofrecer experiencias personalizadas aos seus clientes.

## <a name="data-privacy-and-compliance"></a>Cumprimento e privacidade dos datos

Cando habilita Dynamics 365 Customer Insights para transmitir datos a Leadspace, permite a transferencia de datos fóra do límite de cumprimento de Dynamics 365 Customer Insights, incluíndo datos potencialmente confidenciais como os datos persoais. Microsoft transferirá estes datos segundo a súa instrución, pero vostede é responsable de garantir que Leadspace cumpra as obrigas de privacidade ou seguridade que poida ter. Para obter máis información, consulte a [Declaración de privacidade de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
O administrador de Dynamics 365 Customer Insights pode eliminar este enriquecemento en calquera momento para interromper o uso desta funcionalidade.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
