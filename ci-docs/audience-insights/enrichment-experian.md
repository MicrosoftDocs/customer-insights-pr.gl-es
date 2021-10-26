---
title: Enriquecemento co enriquecemento de terceiros Experian
description: Información xeral sobre o enriquecemento de terceiros Experian.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: fabc3cc9faf4e11f46c396782b561ef61cd0f6d5
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 10/08/2021
ms.locfileid: "7618519"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Enriqueza os perfís de clientes con datos demográficos de Experian (versión preliminar)

Experian é líder mundial en servizos de mercadotecnia e informes de crédito ao consumidor e ás empresas. Cos servizos de enriquecemento de datos de Experian, pode construír unha comprensión máis profunda dos seus clientes enriquecendo os perfís dos seus clientes con datos demográficos como tamaño do fogar, ingresos e moito máis.

## <a name="prerequisites"></a>Requisitos previos

Para configurar Experian, deben cumprirse os seguintes requisitos previos:

- Debe ter unha subscrición activa de Experian. Para obter unha subscrición, [contacte con Experian](https://www.experian.com/marketing-services/contact) directamente. [Obteña máis información acerca do enriquecementos de datos de Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).

- Un administrador configurou xa unha conexión de Experian *ou* ten permisos de [administrador](permissions.md#administrator). Tamén precisa o ID de usuario, o ID de grupo e o número de modelo da súa conta de transporte seguro (ST) con SSH que Experian creou para vostede.

## <a name="supported-countriesregions"></a>Países ou rexións compatibles

Actualmente admítese enriquecer perfís de clientes só nos Estados Unidos.

## <a name="configure-the-enrichment"></a>Configurar o enriquecemento

1. Vaia a **Datos** > **Enriquecemento** e seleccione o separador **Descubrir**.

1. Seleccione **Enriquecer os meus datos** no mosaico Experian.

   > [!div class="mx-imgBorder"]
   > ![Mosaico de Experian.](media/experian-tile.png "Experian tile")
   > 

1. Seleccione unha [conexión](connections.md) da lista despregable. Póñase en contacto cun administrador se non hai conexión dispoñible. Se é administrador, pode crear unha conexión seleccionando **Engadir conexión** e escollendo Experian da lista despregable. 

1. Seleccione **Conectarse a Experian** para confirmar a selección de conexión.

1.  Seleccione **Seguinte** e escolla o **Conxunto de datos do cliente** que quere enriquecer con datos demográficos de Experian. Pode seleccionar a entidade **Cliente** para enriquecer todos os seus perfís de clientes ou seleccione unha entidade de segmento para enriquecer só os perfís de clientes contidos nese segmento.

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Captura de pantalla ao escoller o conxunto de datos do cliente.":::

1. Seleccione **Seguinte** e defina que tipo de campos dos seus perfís unificados se deben empregar para buscar datos demográficos coincidentes de Experian. Polo menos un dos campos **Nome e enderezo**, **Teléfono** ou **Correo electrónico** é requerido. Para unha maior precisión de coincidencia, pódense engadir ata outros dous campos. Esta selección afectará aos campos de asignación aos que ten acceso no seguinte paso.

    > [!TIP]
    > Enviar máis atributos de identificación claves a Experian é probable que produza unha maior taxa de coincidencia.

1. Seleccione **Seguinte** para iniciar a asignación dos campos.

1. Defina que campos dos seus perfís unificados se deben empregar para buscar datos demográficos coincidentes de Experian. Os campos necesarios están marcados.

1. Proporcione un nome para o enriquecemento e un nome para a entidade de saída.

1. Seleccione **Gardar enriquecemento** despois de revisar as súas opcións.

## <a name="configure-the-connection-for-experian"></a>Configurar a conexión de Experian 

Debe ser administrador para configurar as conexións. Seleccione **Engadir conexión** ao configurar un enriquecemento *ou* vaia a **Administrar** > **Conexións** e seleccionr **configurar** no mosaico de Experian.

1. Seleccione **Comezar**.

1. Introduza un nome para a conexión na caixa **Nome de visualización**.

1. Introduza un ID de usuario, ID de grupo e número de modelo válidos para a súa conta de transporte seguro de Experian.

1. Revise e proporcione o seu consentimento para a **Privacidade e cumprimento de datos** seleccionando **Estou de acordo**.

1. Seleccione **Verificar** para validar a configuración.

1. Despois de completar a verificación, seleccione **Gardar**.
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Experian panel de configuración da conexión.":::

## <a name="enrichment-results"></a>Resultados de enriquecemento

Para iniciar o proceso de enriquecemento, seleccione **Executar** na barra de comandos. Tamén pode deixar que o sistema execute o enriquecemento automaticamente como parte dunha [actualización programada](system.md#schedule-tab). O tempo de procesamento dependerá do tamaño dos datos dos seus clientes e dos procesos de enriquecemento configurados para a súa conta por Experian.

Despois de completar o proceso de enriquecemento, pode consultar os datos dos perfís de clientes recentemente enriquecidos en **Os meus enriquecementos**. Ademais, atopará a hora da última actualización e o número de perfís enriquecidos.

Pode acceder a unha vista detallada de cada perfil enriquecido seleccionando **Ver datos enriquecidos**.

## <a name="next-steps"></a>Pasos seguintes

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Cumprimento e privacidade dos datos

Cando permite a Dynamics 365 Customer Insights transmitir datos a Experian, permite a transferencia de datos fóra do límite de cumprimento de Dynamics 365 Customer Insights, incluíndo datos potencialmente confidenciais como os datos persoais. Microsoft transferirá estes datos segundo a súa instrución, pero vostede é responsable de asegurarse de que Experian cumpre coas obrigacións de privacidade ou seguridade que poida ter. Para obter máis información, consulte a [Declaración de privacidade de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
O administrador de Dynamics 365 Customer Insights pode eliminar este enriquecemento en calquera momento para interromper o uso desta funcionalidade.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
