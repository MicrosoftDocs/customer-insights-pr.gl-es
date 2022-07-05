---
title: Exportar segmentos a LiveRamp (versión preliminar)
description: Aprenda a configurar a conexión e a exportación a LiveRamp.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 3e30a16dcb276fa6c951ad0b42ed0a4792f87ce3
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "9050761"
---
# <a name="export-segments-to-liverampreg-preview"></a>Exportar segmentos a LiveRamp&reg; (versión preliminar)

Active os seus datos en LiveRamp para conectar con máis de 500 plataformas dixitais, sociais e televisivas. Traballe cos seus datos en LiveRamp para orientar, suprimir e personalizar as campañas publicitarias.

## <a name="prerequisites-for-a-connection"></a>Requisitos previos para unha conexión

- Para usar este conector precisa unha subscrición a LiveRamp.
- Para obter unha subscrición, [contacte con LiveRamp](https://liveramp.com/contact/) directamente. [Obteña máis información sobre LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).

## <a name="set-up-connection-to-liveramp"></a>Configurar conexión a LiveRamp

1. Vaia a **Administrar** > **Conexións**.

1. Seleccione **Engadir conexión** e elixa **LiveRamp** para configurar a conexión.

1. Déalle á conexión un nome recoñecible no campo **Nome para mostrar**. O nome e o tipo de conexión describen esta conexión. Recomendamos escoller un nome que explique o propósito e o destino da conexión.

1. Escolla quen pode usar esta conexión. Se non realiza ningunha acción, o valor predeterminado será Administradores. Para obter máis información, consulte [Permitir aos colaboradores usar unha conexión para as exportacións](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Proporcione un **Nome de usuario** e un **Contrasinal** para a súa conta de LiveRamp Secure FTP (SFTP).
Estas credenciais poden ser diferentes das súas credenciais de LiveRamp Onboarding.

1. Seleccione **Verificar** para probar a conexión a LiveRamp.

1. Despois de facer unha verificación con éxito, proporcione o seu consentimento para a **Privacidade e cumprimento dos datos** seleccionando a caixa de verificación **Estou de acordo**.

1. Seleccione **Gardar** para completar a conexión.

## <a name="configure-an-export"></a>Configurar unha exportación

Pode configurar esta exportación se ten acceso a unha conexión deste tipo. Para obter máis información, consulte [Permisos necesarios para configurar unha exportación](export-destinations.md#set-up-a-new-export).

1. Vaia a **Datos** > **Exportacións**.

1. Seleccione **Engadir destino** para crear unha nova exportación.

1. No campo **Conexión da exportación** escolla unha conexión da sección LiveRamp. Se non ve o nome desta sección, non hai conexións deste tipo dispoñibles para vostede.

1. No campo **Escoller o identificador clave**, seleccione **Correo electrónico**, **Nome e enderezo** ou **Teléfono** para envialos a LiveRamp para resolver a identidade.
   > [!div class="mx-imgBorder"]
   > ![Conector LiveRamp con asignación de atributos.](media/export-liveramp-segments.png "Conector LiveRamp con asignación de atributos")

1. Asigna os atributos correspondentes da súa entidade de *Cliente* para o identificador de clave seleccionado.

1. Seleccione **Engadir atributo** para asignar máis atributos para envialos a LiveRamp.

   > [!TIP]
   > O envío de máis atributos de identificador clave a LiveRamp é probable que provoque a obtención dunha taxa de coincidencia máis alta.

1. Seleccione os segmentos que desexe exportar a LiveRamp.

1. Seleccione **Gardar**.

Ao gardar unha exportación non se executa a exportación inmediatamente.

A exportación execútase con cada [actualización programada](system.md#schedule-tab). Tamén pode [exportar datos baixo demanda](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Cumprimento e privacidade dos datos

Cando habilita Dynamics 365 Customer Insights para transmitir datos a LiveRamp, permite a transferencia de datos fóra do límite de cumprimento de Dynamics 365 Customer Insights, incluíndo datos potencialmente confidenciais como os datos persoais. Microsoft transferirá estes datos segundo a súa instrución, pero vostede é responsable de garantir que LiveRamp cumpra as obrigas de privacidade ou seguridade que poida ter. Para obter máis información, consulte a [Declaración de privacidade de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
O administrador de Dynamics 365 Customer Insights pode eliminar este destino de exportación en calquera momento para interromper o uso desta funcionalidade.

[!INCLUDE [footer-include](includes/footer-banner.md)]
