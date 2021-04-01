---
title: Enriquecemento co enriquecemento de terceiros de Experian
description: Información xeral sobre o enriquecemento de terceiros de Experian.
ms.date: 12/10/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 4d4723e8f793ee857c4f5204a42be8338c71d4c3
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597785"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Enriquecer os perfís de clientes con datos demográficos de Experian (previsualización)

Experian é líder mundial en servizos de márketing e informes de crédito para consumidores e empresas. Cos servizos de enriquecemento de datos de Experian, pode adquirir unha comprensión máis profunda dos seus clientes enriquecendo os perfís dos seus clientes con datos demográficos como o tamaño do fogar, os ingresos e moito máis.

## <a name="prerequisites"></a>Requisitos previos

Para configurar Experian, deben cumprirse os seguintes requisitos previos:

- Vostede ten unha subscrición a Experian activa. Para obter unha subscrición, [contacte con Experian](https://www.experian.com/marketing-services/contact) directamente. [Máis información sobre o enriquecemento de información de Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).
- Vostede ten o ID de usuario, o ID de parte e o número de modelo para a súa conta de transporte seguro (ST) compatible con SSH que Experian creou para vostede.
- Ten permisos de [administrador](permissions.md#administrator) na información do público.

## <a name="configuration"></a>Configuración

1. Vaia a **Datos** > **Enriquecemento** e seleccione o separador **Descubrir**.

1. Seleccione **Enriquece os meus datos** no mosaico de Experian.

   > [!div class="mx-imgBorder"]
   > ![Mosaico de Experian](media/experian-tile.png "Mosaico de Experian")

1. Seleccione **Comezar** e introduza o ID de usuario, ID de parte e número de modelo para a súa conta de transporte seguro de Experian. Revise e proporcione o seu consentimento para a **Privacidade e cumprimento dos datos** seleccionando a caixa de verificación **Estou de acordo**. Confirme todas as entradas seleccionando **Aplicar**.

## <a name="map-your-fields"></a>Asignar os campos

1.  Seleccione **Engadir datos** e escolla o **conxunto de datos de cliente** que desexa enriquecer cos datos demográficos de Experian. Pode seleccionar a entidade **Cliente** para enriquecer todos os seus perfís de clientes ou seleccione unha entidade de segmento para enriquecer só os perfís de clientes contidos nese segmento.

1. Seleccione os seus identificadores clave de **Nome e enderezo**, **Correo electrónico** ou **Teléfono** para enviar a Experian para a resolución de identidade.

   > [!TIP]
   > É probable que máis atributos de identificadores clave enviados a Experian produzan unha maior taxa de coincidencia.

1. Seleccione **Seguinte** e asigne os atributos correspondentes da súa entidade de cliente unificada para os campos de identificador clave seleccionados.

1. Seleccione **Engadir atributo** para asignar os atributos adicionais que lle gustaría enviar a Experian.

1.  Seleccione **Gardar** para completar a asignación de campos.

    > [!div class="mx-imgBorder"]
    > ![Asignación de campos de Experian](media/experian-field-mapping.png "Asignación de campos de Experian")

## <a name="enrichment-results"></a>Resultados de enriquecemento

Para iniciar o proceso de enriquecemento, seleccione **Executar** na barra de comandos. Tamén pode deixar que o sistema execute o enriquecemento automaticamente como parte dunha [actualización programada](system.md#schedule-tab). O tempo de procesamento dependerá do tamaño dos datos dos seus clientes e dos procesos de enriquecemento configurados para Experian na súa conta.

Despois de completar o proceso de enriquecemento, pode consultar os datos dos perfís de clientes recentemente enriquecidos en **Os meus enriquecementos**. Ademais, atopará a hora da última actualización e o número de perfís enriquecidos.

Pode acceder a unha vista detallada de cada perfil enriquecido seleccionando **Ver datos enriquecidos**.

## <a name="next-steps"></a>Pasos seguintes

Crear sobre os seus datos enriquecidos de clientes. Cree [segmentos](segments.md), [medidas](measures.md) e incluso [exporte os datos](export-destinations.md) para ofrecer experiencias personalizadas aos seus clientes.

## <a name="data-privacy-and-compliance"></a>Cumprimento e privacidade dos datos

Cando habilita Dynamics 365 Customer Insights para transmitir datos a Experian, permite a transferencia de datos fóra do límite de cumprimento de Dynamics 365 Customer Insights, incluíndo datos potencialmente confidenciais como os datos persoais. Microsoft transferirá estes datos segundo a súa instrución, pero vostede é responsable de garantir que Experian cumpra as obrigas de privacidade ou seguridade que poida ter. Para obter máis información, consulte a [Declaración de privacidade de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
O administrador de Dynamics 365 Customer Insights pode eliminar este enriquecemento en calquera momento para interromper o uso desta funcionalidade.


[!INCLUDE[footer-include](../includes/footer-banner.md)]