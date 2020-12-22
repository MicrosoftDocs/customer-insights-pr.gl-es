---
title: Conector de LiveRamp
description: Como exportar datos a LiveRamp.
ms.date: 12/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 86aa8c66a47ee61741082c95f05d2e5ce3f06f35
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667182"
---
# <a name="liverampreg-connector-preview"></a>Conector LiveRamp&reg; (vista previa)

Active os seus datos en LiveRamp para conectarse con máis de 500 plataformas en ecosistemas dixitais, sociais e de televisión. Traballe cos seus datos en LiveRamp para orientar, suprimir e personalizar as campañas publicitarias.

## <a name="prerequisites"></a>Requisitos previos

- Para usar este conector precisa unha subscrición a LiveRamp.
- Para obter unha subscrición, [contacte con LiveRamp](https://liveramp.com/contact/) directamente. [Obteña máis información sobre LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).

## <a name="connect-to-liveramp"></a>Conectar con LiveRamp

1. Na información do público, vaia a **Administrar** > **Destinos de exportación**.

1. No mosaico de **LiveRamp**, seleccione **Configurar**.

1. Déalle ao seu destino un nome recoñecible no campo **Nome para mostrar**.

1. Proporcione un **Nome de usuario** e un **Contrasinal** para a súa conta de LiveRamp Secure FTP (SFTP).
Estas credenciais poden ser diferentes das súas credenciais de LiveRamp Onboarding.

1. Seleccione **Verificar** para probar a conexión a LiveRamp.

1. Despois de facer unha verificación con éxito, proporcione o seu consentimento para a **Privacidade e cumprimento dos datos** seleccionando a caixa de verificación **Estou de acordo**.

1. Seleccione **Seguinte** para configurar o conector LiveRamp.

## <a name="configure-the-connector"></a>Configurar o conector

1. No campo **Escoller o identificador clave**, seleccione **Correo electrónico**, **Nome e enderezo** ou **Teléfono** para envialos a LiveRamp para resolver a identidade.

1. Asigne os atributos correspondentes desde a súa entidade de cliente unificada para o identificador de clave seleccionado.

1. Seleccione **Engadir atributo** para asignar atributos adicionais para enviar a LiveRamp.

   > [!TIP]
   > O envío de máis atributos de identificador clave a LiveRamp é probable que provoque a obtención dunha taxa de coincidencia máis alta.

1. Seleccione os segmentos que desexe exportar a LiveRamp.

1. Seleccione **Gardar**.

> [!div class="mx-imgBorder"]
> ![Conector LiveRamp con asignación de atributos](media/export-liveramp-segments.png "Conector LiveRamp con asignación de atributos")

## <a name="export-the-data"></a>Exportar os datos

A exportación comezará en breve se se cumpren todos os requisitos previos para a exportación. A exportación tamén se executará con todas as [actualizacións programadas](system.md#schedule-tab).
Unha vez rematada a exportación, pode iniciar sesión en LiveRamp Onboarding para activar e distribuír os seus datos.

## <a name="data-privacy-and-compliance"></a>Cumprimento e privacidade dos datos

Cando habilita Dynamics 365 Customer Insights para transmitir datos a LiveRamp, permite a transferencia de datos fóra do límite de cumprimento de Dynamics 365 Customer Insights, incluíndo datos potencialmente confidenciais como os datos persoais. Microsoft transferirá estes datos segundo a súa instrución, pero vostede é responsable de garantir que LiveRamp cumpra as obrigas de privacidade ou seguridade que poida ter. Para obter máis información, consulte a [Declaración de privacidade de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
O administrador de Dynamics 365 Customer Insights pode eliminar este destino de exportación en calquera momento para interromper o uso desta funcionalidade.