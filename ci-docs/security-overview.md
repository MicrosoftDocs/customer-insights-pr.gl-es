---
title: Configurar a configuración de seguranza
description: Obtén información sobre a configuración de seguranza en Dynamics 365 Customer Insights.
ms.date: 08/02/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: d20d57e9b7724e9921f9341eeaa39141b4555ff1
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387247"
---
# <a name="configure-security-settings"></a>Configurar a configuración de seguranza

Xestione as claves da API, acceda aos datos dos clientes e configure unha ligazón privada de Azure.

## <a name="manage-api-keys"></a>Xestionar claves API

Consulta e xestiona as claves para usar o [API de Customer Insights](apis.md) cos datos do seu entorno.

1. Ir a **Admin** > **Seguridade** e selecciona o **APIs** ficha.

1. Se non se configurou o acceso da API ao contorno, seleccione **Activar** . Ou, para bloquear o acceso da API ao contorno, seleccione **Desactivar** e confirmar.

1. Xestiona as claves da API primaria e secundaria:

   1. Para mostrar a clave de API principal ou secundaria, seleccione a **Mostrar** símbolo.

   1. Para copiar a clave de API principal ou secundaria, seleccione a **Copiar** símbolo.

   1. Para crear novas claves de API primarias ou secundarias, selecciona **Rexenerar primaria** ou **Rexenerar secundaria** .

## <a name="securely-access-customer-data-with-customer-lockbox-preview"></a>Acceda de forma segura aos datos do cliente con Customer Lockbox (vista previa)

Customer Insights usa o Power Platform Capacidade de Lockbox do cliente. Customer Lockbox ofrece unha interface para revisar e aprobar (ou rexeitar) solicitudes de acceso a datos. Estas solicitudes prodúcense cando se precisa o acceso aos datos dos clientes para resolver un caso de asistencia. Para utilizar esta función, Customer Insights debe ter unha conexión existente con a Microsoft Dataverse ambiente no seu inquilino.

Para obter máis información sobre Customer Lockbox, consulte [resumo](/power-platform/admin/about-lockbox#summary) de Power Platform Caixa de bloqueo do cliente. O artigo tamén describe o [fluxo de traballo](/power-platform/admin/about-lockbox#workflow) e o requirido [montar](/power-platform/admin/about-lockbox#enable-the-lockbox-policy) para activar Customer Lockbox.

> [!IMPORTANT]
> Administradores globais para Power Platform ou Power Platform os administradores poden aprobar as solicitudes de Customer Lockbox emitidas para Customer Insights.

## <a name="set-up-an-azure-private-link"></a>Configura unha ligazón privada de Azure

[Ligazón privada Azure](/azure/private-link/private-link-overview) permite que Customer Insights se conecte ao teu Azure Data Lake Storage conta a través dun punto final privado na súa rede virtual. Para os datos dunha conta de almacenamento, que non está exposta á Internet pública, Private Link habilita a conexión a esa rede restrinxida.

> [!IMPORTANT]
> Requisito mínimo de función para configurar unha conexión Private Link:
>
> - Customer Insights: Administrador
> - Función integrada de Azure: [Colaborador da conta de almacenamento](/azure/role-based-access-control/built-in-roles#storage-account-contributor)
> - Permisos para o rol personalizado de Azure: [Microsoft.Storage/storageAccounts/read e Microsoft.Storage/storageAccounts/PrivateEndpointConnectionsApproval/action](/azure/role-based-access-control/resource-provider-operations#microsoftstorage)

1. En Customer Insights, vai a **Admin** > **Seguridade** e selecciona o **Ligazóns privadas** ficha.

1. Seleccione **Engadir ligazón privada** .

   O **Engadir ligazón privada** o panel enumera as contas de almacenamento do teu inquilino que tes permisos para ver.

1. Seleccione a subscrición, o grupo de recursos e a conta de almacenamento.

1. Revisa o [privacidade e cumprimento dos datos](connections.md#data-privacy-and-compliance) e selecciona **Estou de acordo** .

1. Seleccione **Gardar**.

1. Vaia á súa conta de Data Lake Storage e abra a ligazón que aparece na pantalla.

1. Aproba a ligazón privada.


[!INCLUDE [footer-include](includes/footer-banner.md)]
