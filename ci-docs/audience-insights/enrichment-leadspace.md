---
title: Enriquecemento de perfís de empresa co enriquecemento de terceiros de Leadspace
description: Información xeral sobre o enriquecemento de terceiros de Leadspace.
ms.date: 11/24/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 12eed91a7ca4ef7fde0d53cca4a1dfd398b4634f
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269420"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a>Enriquecemento de perfís de empresa con Leadspace (vista previa)

Leadspace é unha empresa de ciencia de datos que proporciona unha plataforma de datos de clientes B2B. Permite aos clientes con perfís de clientes unificados para empresas enriquecer os seus datos. Os enriquecementos incluíen atributos adicionais, como o tamaño da empresa, a localización o sector e moito máis.

## <a name="prerequisites"></a>Requisitos previos

Para configurar Leadspace, deben cumprirse os seguintes requisitos previos:

- Ten unha licenza de Leadspace activa e a "clave perpetua" (coñecida como **Token de Leadspace**). Contacte directamente con [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) para obter máis detalles sobre o seu produto.
- Ten permisos de [administrador](permissions.md#administrator).
- Ten [perfís de clientes unificados](customer-profiles.md) para empresas.

## <a name="configuration"></a>Configuración

1. Na información do público, vaia a **Datos** > **Enriquecemento**.

1. Seleccione **Enriquecer os meus datos** no mosaico de Leadspace.

   :::image type="content" source="media/leadspace-tile.png" alt-text="Captura de pantalla do mosaico de Leadspace.":::

1. Seleccione **Comezar** e logo introduza un **Token de Leadspace** (clave perpetua) activo. Revise e proporcione o seu consentimento para a **Privacidade e cumprimento dos datos** seleccionando a caixa de verificación **Estou de acordo**. Confirme ambas as entradas seleccionando **Conectarse a Leadspace**.

1. Seleccione **Asignar datos** e escolla o conxunto de datos que desexa enriquecer cos datos da empresa de Leadspace. Pode seleccionar a entidade *Cliente* para enriquecer todos os seus perfís de clientes ou seleccione unha entidade de segmento para enriquecer só os perfís de clientes contidos nese segmento.

   :::image type="content" source="media/enrichment-leadspace-select-segment.png" alt-text="Elixa entre o perfil do cliente e o enriquecemento do segmento.":::

1. Seleccione **Seguinte** e defina os campos dos perfís unificados que se deben empregar para buscar os datos da empresa coincidentes de Leadspace. O campo **Nome da empresa** é obrigatorio. Para unha maior precisión de coincidencia, ata outros dous campos, **Páxina web da empresa** e **Localización da empresa**, pódense engadir.

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Panel de asignación de campos de Leadspace.":::
   
1. Seleccione **Aplicar** para completar a asignación de campos.

1. Seleccione **Executar** para enriquecer os perfís da empresa. O tempo que leva un enriquecemento depende do número de perfís de clientes unificados.

## <a name="enrichment-results"></a>Resultados de enriquecemento

Despois de actualizar o enriquecemento, pode revisar os datos da empresa enriquecidos recentemente en [Os meus enriquecementos](enrichment-hub.md). Pode atopar a hora da última actualización e o número de perfís enriquecidos.

Pode acceder a unha vista detallada de cada perfil enriquecido seleccionando **Ver datos enriquecidos**.

Para obter máis información, consulte [API de Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).

## <a name="next-steps"></a>Pasos seguintes

Crear sobre os seus datos enriquecidos de clientes. Cree [segmentos](segments.md), [medidas](measures.md) e incluso [exporte os datos](export-destinations.md) para ofrecer experiencias personalizadas aos seus clientes.

## <a name="data-privacy-and-compliance"></a>Cumprimento e privacidade dos datos

Cando habilita Dynamics 365 Customer Insights para transmitir datos a Leadspace, permite a transferencia de datos fóra do límite de cumprimento de Dynamics 365 Customer Insights, incluíndo datos potencialmente confidenciais como os datos persoais. Microsoft transferirá estes datos segundo a súa instrución, pero vostede é responsable de garantir que Leadspace cumpra as obrigas de privacidade ou seguridade que poida ter. Para obter máis información, consulte a [Declaración de privacidade de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
O administrador de Dynamics 365 Customer Insights pode eliminar este enriquecemento en calquera momento para interromper o uso desta funcionalidade.


[!INCLUDE[footer-include](../includes/footer-banner.md)]