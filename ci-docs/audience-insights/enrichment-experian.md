---
title: Enriquecemento co enriquecemento de terceiros de Experian
description: Información xeral sobre o enriquecemento de terceiros de Experian.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 9cf2a7fa18ecc022ea67f6829f52381ad59f3172
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896371"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Enriquecer os perfís de clientes con datos demográficos de Experian (previsualización)

Experian é líder mundial en servizos de márketing e informes de crédito para consumidores e empresas. Cos servizos de enriquecemento de datos de Experian, pode adquirir unha comprensión máis profunda dos seus clientes enriquecendo os perfís dos seus clientes con datos demográficos como o tamaño do fogar, os ingresos e moito máis.

## <a name="prerequisites"></a>Requisitos previos

Para configurar Experian, deben cumprirse os seguintes requisitos previos:

- Vostede ten unha subscrición a Experian activa. Para obter unha subscrición, [contacte con Experian](https://www.experian.com/marketing-services/contact) directamente. [Máis información sobre o enriquecemento de información de Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).

- Un administrador configurou xa unha conexión de Experian *ou* ten permisos de [administrador](permissions.md#administrator). Tamén precisa o ID de usuario, o ID de grupo e o número de modelo da súa conta de transporte seguro (ST) habilitada para SSH que Experian creou para vostede.

## <a name="configure-the-enrichment"></a>Configurar o enriquecemento

1. Vaia a **Datos** > **Enriquecemento** e seleccione o separador **Descubrir**.

1. Seleccione **Enriquece os meus datos** no mosaico de Experian.

   > [!div class="mx-imgBorder"]
   > ![Mosaico de Experian](media/experian-tile.png "Mosaico de Experian")
   > 

1. Seleccione unha [conexión](connections.md) da lista despregable. Póñase en contacto cun administrador se non hai conexión dispoñible. Se é administrador, pode crear unha conexión seleccionando **Engadir conexión** e escollendo Experian desde o menú despregable. 

1. Seleccione **Conectar con Experian** para confirmar a selección da conexión.

1.  Seleccione **Seguinte** e escolla o **Conxunto de datos do cliente** que quere enriquecer cos datos demográficos de Experian. Pode seleccionar a entidade **Cliente** para enriquecer todos os seus perfís de clientes ou seleccione unha entidade de segmento para enriquecer só os perfís de clientes contidos nese segmento.

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Captura de pantalla ao escoller o conxunto de datos do cliente.":::

1. Seleccione **Seguinte** e defina o tipo de campos dos perfís unificados que se debe usar para buscar os datos demográficos coincidentes de Experian. Polo menos un dos campos **Nome e enderezo**, **Teléfono** ou **Correo electrónico** é requerido. Para unha maior precisión de coincidencia, pódense engadir ata outros dous campos. Esta selección afectará aos campos de asignación aos que ten acceso no seguinte paso.

    > [!TIP]
    > É probable que máis atributos de identificadores clave enviados a Experian produzan unha maior taxa de coincidencia.

1. Seleccione **Seguinte** para iniciar a asignación dos campos.

1. Defina que campos dos perfís unificados se deben usar para buscar os datos demográficos coincidentes de Experian. Os campos necesarios están marcados.

1. Proporcione un nome para o enriquecemento e un nome para a entidade de saída.

1. Seleccione **Gardar enriquecemento** despois de revisar as súas opcións.

## <a name="configure-the-connection-for-experian"></a>Configurar a conexión de Experian 

Debe ser administrador para configurar as conexións. Seleccione **Engadir conexión** ao configurar un enriquecemento *ou* vaia a **Administrar** > **Conexións** e seleccione **Configurar** no mosaico de Experian.

1. Seleccione **Comezar**.

1. Introduza un nome para a conexión na caixa **Nome de visualización**.

1. Introduza un ID de usuario, un ID de grupo e un número de modelo válidos para a súa conta de Transporte seguro de Experian.

1. Revise e proporcione o seu consentimento para a **Privacidade de datos e cumprimento** seleccionando a caixa de verificación **Estou de acordo**

1. Seleccione **Verificar** para validar a configuración.

1. Despois de completar a verificación, seleccione **Gardar**.
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Panel de configuración da conexión de Experian.":::

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
