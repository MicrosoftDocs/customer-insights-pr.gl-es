---
title: Configuración de seguranza en Customer Insights
description: Obtén información sobre a configuración de seguranza en Dynamics 365 Customer Insights.
ms.date: 06/08/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 163deb9bed4f82d742c46cace27dd128f0aca18b
ms.sourcegitcommit: 8e9f0a9693fd8d91ad0227735ff03688fef5406f
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 06/10/2022
ms.locfileid: "8947413"
---
# <a name="security-settings-in-customer-insights"></a>Configuración de seguranza en Customer Insights

O **Seguridade** páxina lista opcións para configurar os permisos de usuario e funcións que axudan a facer Dynamics 365 Customer Insights máis seguro. Só os administradores poden acceder a esta páxina.

Ir a **Admin** > **Seguridade** para configurar os axustes.

O **Seguridade** páxina inclúe as seguintes pestanas:

- [Usuarios](#users-tab)
- [API](#apis-tab)
- [Ligazóns privadas](#private-links-tab)
- [Key Vault](#key-vault-tab)
- [Acceda de forma segura aos datos do cliente con Customer Lockbox (vista previa)](#securely-access-customer-data-with-customer-lockbox-preview)

## <a name="users-tab"></a>Ficha Usuarios

O acceso a Customer Insights está restrinxido aos usuarios da túa organización que foron engadidos á aplicación por un administrador. O **Usuarios** permite xestionar o acceso dos usuarios e os seus permisos. Para obter máis información, consulte [Permisos de usuario](permissions.md).

## <a name="apis-tab"></a>Pestana APIs

Consulta e xestiona as claves para usar o [API de Customer Insights](apis.md) cos datos do seu entorno.

Podes crear novas chaves primarias e secundarias seleccionando **Rexenerar primaria** ou **Rexenerar secundaria**. 

Para bloquear o acceso da API ao contorno, seleccione **Desactivar**. Se as API están desactivadas, podes seleccionar **Activar** para conceder acceso de novo.

## <a name="private-links-tab"></a>Pestana Ligazóns privadas

[Ligazón privada Azure](/azure/private-link/private-link-overview) imos conectar Customer Insights ao teu Azure Data Lake Storage conta a través dun punto final privado na súa rede virtual. Para os datos dunha conta de almacenamento, que non está exposta á Internet pública, Private Link habilita a conexión a esa rede restrinxida.

> [!IMPORTANT]
> Requisito mínimo de función para configurar unha conexión Private Link:
>
> - Customer Insights: Administrador
> - Función integrada de Azure: [Colaborador da conta de almacenamento](/azure/role-based-access-control/built-in-roles#storage-account-contributor)
> - Permisos para o rol personalizado de Azure: [Microsoft.Storage/storageAccounts/read e Microsoft.Storage/storageAccounts/PrivateEndpointConnectionsApproval/action](/azure/role-based-access-control/resource-provider-operations#microsoftstorage)
>

Configurar a ligazón privada en Customer Insights é un proceso de dous pasos. En primeiro lugar, inicias a creación dunha ligazón privada desde **Admin** > **Seguridade** > **Ligazóns privadas** en Customer Insights. O **Engadir ligazón privada** o panel enumera as contas de almacenamento do teu inquilino que tes permisos para ver. Selecciona a conta de almacenamento e dá o teu consentimento para crear a ligazón privada.

A continuación, cómpre aprobar a ligazón privada no lado da conta de Data Lake Storage. Abre a ligazón que aparece na pantalla para aprobar a nova ligazón privada.

## <a name="key-vault-tab"></a>Pestana Key Vault

O **Bóveda de chaves** pestana permíteche vincular e xestionar o teu propio [Bóveda de chaves Azure](/azure/key-vault/general/basic-concepts) ao medio ambiente.
A key vault específica pódese usar para probar e usar segredos no límite de cumprimento dunha organización. Customer Insights pode usar os segredos de Azure Key Vault para [establecer conexións](connections.md) a sistemas de terceiros.

Para obter máis información, consulte [Traer o seu propio Azure Key Vault](use-azure-key-vault.md).

## <a name="securely-access-customer-data-with-customer-lockbox-preview"></a>Acceda de forma segura aos datos do cliente con Customer Lockbox (vista previa)

Customer Insights está usando o Power Platform Capacidade de Lockbox do cliente. Customer Lockbox ofrece unha interface para revisar e aprobar (ou rexeitar) solicitudes de acceso a datos. Estas solicitudes prodúcense cando se precisa o acceso aos datos dos clientes para resolver un caso de asistencia. Para utilizar esta función, Customer Insights debe ter unha conexión existente con a Microsoft Dataverse ambiente no seu inquilino.

Para obter máis información sobre Customer Lockbox, consulte [resumo](/power-platform/admin/about-lockbox#summary) de Power Platform Caixa de bloqueo do cliente. O artigo tamén describe o [fluxo de traballo](/power-platform/admin/about-lockbox#workflow) e o requirido [montar](/power-platform/admin/about-lockbox#enable-the-lockbox-policy) para activar Customer Lockbox.

> [!IMPORTANT]
> Administradores globais para Power Platform ou Power Platform os administradores poden aprobar as solicitudes de Customer Lockbox emitidas para Customer Insights.

[!INCLUDE [footer-include](includes/footer-banner.md)]
