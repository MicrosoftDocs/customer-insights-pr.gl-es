---
title: Traia a súa propia key vault de Azure (versión preliminar)
description: Aprende a configurar Customer Insights para utilizar a túa propia bóveda de claves de Azure para xestionar os segredos.
ms.date: 08/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: 229fb5698a02d1d73c30442f61c7b1b5fce918bf
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 08/10/2022
ms.locfileid: "9246153"
---
# <a name="bring-your-own-azure-key-vault-preview"></a>Traia a súa propia key vault de Azure (versión preliminar)

Vinculando un dedicado [Bóveda de chaves Azure](/azure/key-vault/general/basic-concepts) a un ambiente de Customer Insights axuda ás organizacións a cumprir os requisitos de cumprimento.

## <a name="link-the-key-vault-to-the-customer-insights-environment"></a>Vincula a bóveda de claves ao contorno de Customer Insights

Configura a bóveda de claves dedicada para organizar e utilizar segredos nos límites de cumprimento dunha organización.

### <a name="prerequisites"></a>Requisitos previos

- Unha subscrición de Azure activa.

- An [Administrador](permissions.md#admin) papel [asignado](permissions.md#add-users) en Customer Insights.

- [Colaborador](/azure/role-based-access-control/built-in-roles#contributor) e [Administrador de acceso de usuarios](/azure/role-based-access-control/built-in-roles#user-access-administrator) roles na bóveda de claves ou no grupo de recursos ao que pertence a bóveda de claves. Para obter máis información, vaia a [Engadir ou eliminar as asignacións de funcións de Azure usando o portal de Azure](/azure/role-based-access-control/role-assignments-portal). Se non ten o rol de administrador de acceso de usuario na bóveda de claves, configure os permisos de control de acceso baseados en funcións para o principal do servizo Azure para Dynamics 365 Customer Insights por separado. Siga os pasos para [usar un principal de servizo de Azure](connect-service-principal.md) para a key vault que debería estar ligada.

- A bóveda de claves debe ter un firewall de Key Vault **desactivado**.

- A bóveda de chaves está na mesma [Localización Azure](https://azure.microsoft.com/global-infrastructure/geographies/#overview) como o entorno de Customer Insights. En Customer Insights, vai a **Admin** > **Sistema** e o **Sobre** ficha para ver a rexión do entorno.

### <a name="recommendations"></a>Recomendacións

- [Use unha bóveda de chaves separada ou dedicada](/azure/key-vault/general/best-practices#why-we-recommend-separate-key-vaults) que contén só os segredos necesarios para Customer Insights.

- Siga as [prácticas recomendadas para usar Key Vault](/azure/key-vault/general/best-practices#turn-on-logging) para o acceso de control, a copia de seguridade, a auditoría e as opcións de recuperación.

### <a name="link-a-key-vault-to-the-environment"></a>Vincular unha key vault ao ambiente

1. Ir a **Admin** > **Seguridade** e, a continuación, seleccione **Bóveda de chaves** ficha.
1. No mosaico **Key Vault**, seleccione **Configurar**.
1. Escolla unha **Subscrición**.
1. Escolla unha key vault da lista despregable **Key Vault**. Se hai demasiadas bóvedas de claves dispoñibles, seleccione un grupo de recursos para limitar os resultados da busca.
1. Revise a [Privacidade dos datos e cumprimento](connections.md#data-privacy-and-compliance) e seleccione **Estou de acordo**.
1. Seleccione **Gardar**.

O **Bóveda de chaves** O mosaico mostra o nome da bóveda de claves ligada, a subscrición e o grupo de recursos. Está listo para usarse na configuración da conexión.
Para obter máis información sobre os permisos da bóveda de claves que se conceden a Customer Insights, vai a [Permisos concedidos na bóveda de chaves](#permissions-granted-on-the-key-vault).

## <a name="use-the-key-vault-in-the-connection-setup"></a>Utilice a key vault na configuración da conexión

Cando [establecer conexións](connections.md) a [terceiros compatibles](#supported-connection-types) sistemas, use os segredos do Key Vault ligado para configurar as conexións.

1. Vaia a **Administrar** > **Conexións**.
1. Seleccione **Engadir conexión**.
1. Para os tipos de conexión admitidos, hai dispoñible un conmutador de **Usar Key Vault** se ligou unha key vault.
1. En lugar de introducir o segredo manualmente, escolla o nome do segredo que apunte ao valor do segredo na bóveda de claves.

   :::image type="content" source="media/use-key-vault-secret.png" alt-text="Panel de conexión cunha conexión SFTP que usa un segredo de Key Vault.":::

1. Seleccione **Gardar** para crear a conexión.

## <a name="supported-connection-types"></a>Tipos de conexión admitidos

As seguintes conexións de [exportación](export-destinations.md) son compatibles:

* [ActiveCampaign](export-active-campaign.md)
* [Autopilot](export-autopilot.md)
* [DotDigital](export-dotdigital.md)
* [Google Ads](export-google-ads.md)
* [Klaviyo](export-klaviyo.md)
* [LiveRamp](export-liveramp.md)
* [Marketo](export-marketo.md)
* [Omnisend](export-omnisend.md)
* [Salesforce Marketing Cloud](export-salesforce.md)
* [Sendgrid](export-sendgrid.md)
* [Sendinblue](export-sendinblue.md)
* [SFTP](export-sftp.md)

## <a name="permissions-granted-on-the-key-vault"></a>Permisos concedidos na bóveda de chaves

Os seguintes permisos concédense a Customer Insights nunha bóveda de claves ligada, se é o caso [Política de acceso a Key Vault](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) ou [Control de acceso baseado en roles de Azure](/azure/key-vault/general/rbac-guide?tabs=azure-cli) está activado.

### <a name="key-vault-access-policy"></a>Política de acceso a Key Vault

| Tipo        | Permisos          |
| ----------- | -------------------- |
| Tecla         | [Obter claves](/rest/api/keyvault/keys/get-keys/get-keys), [Obter clave](/rest/api/keyvault/keys/get-key/get-key)                                 |
| Segredo      | [Obtén segredos](/rest/api/keyvault/secrets/get-secrets/get-secrets), [Obter segredo](/rest/api/keyvault/secrets/get-secret/get-secret)                     |
| Certificado | [Obter certificados](/rest/api/keyvault/certificates/get-certificates/get-certificates), [Obter certificado](/rest/api/keyvault/certificates/get-certificate/get-certificate) |

Os valores anteriores son o mínimo para enumerar e ler durante a execución.

### <a name="azure-role-based-access-control"></a>Control de acceso baseado en funcións de Azure

O [Roles de usuario de Key Vault Reader e Key Vault Secrets](/azure/key-vault/general/rbac-guide?tabs=azure-cli) engadirase a Customer Insights.

## <a name="frequently-asked-questions"></a>Preguntas máis frecuentes

### <a name="can-customer-insights-write-secrets-or-overwrite-secrets-into-the-key-vault"></a>Pode Customer Insights escribir segredos ou sobrescribir segredos na bóveda de claves?

Non. Só os permisos de lectura e lista indicados en [permisos concedidos](#permissions-granted-on-the-key-vault) concédense a Customer Insights. O sistema non pode engadir, eliminar nin sobrescribir segredos na key vault. Esa é tamén a razón pola que non pode introducir credenciais cando unha conexión usa Key Vault.

### <a name="can-i-change-a-connection-from-using-key-vault-secrets-to-default-authentication"></a>Podo cambiar unha conexión que use segredos de Key Vault pola autenticación predeterminada?

Non. Non pode volver a unha conexión predeterminada despois de configurala usando un segredo dunha key vault ligada. Cree unha conexión separada e elimine a antiga se xa non a necesita.

### <a name="how-can-i-revoke-access-to-a-key-vault-for-customer-insights"></a>Como podo revogar o acceso a unha bóveda de claves para Customer Insights?

Se o [Política de acceso a Key Vault](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) ou [Control de acceso baseado en roles de Azure](/azure/key-vault/general/rbac-guide?tabs=azure-cli) está activado, elimine os permisos para o principal do servizo`0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` co nome `Dynamics 365 AI for Customer Insights`. Todas as conexións que usan a key vault deixarán de funcionar.

### <a name="a-secret-thats-used-in-a-connection-got-removed-from-the-key-vault-what-can-i-do"></a>Un segredo que se usa nunha conexión foi eliminado da key vault. Que podo facer?

Aparece unha notificación en Customer Insights cando xa non se pode acceder a un segredo configurado da bóveda de claves. Active [eliminación temporal](/azure/key-vault/general/soft-delete-overview) na key vault para restaurar segredos se se eliminan accidentalmente.

### <a name="a-connection-doesnt-work-but-my-secret-is-in-the-key-vault-what-might-be-the-cause"></a>Unha conexión non funciona, pero o meu segredo está na key vault. Cal pode ser a causa?

Aparece unha notificación en Customer Insights cando non pode acceder á bóveda de claves. A causa pode ser:

- Elimináronse os permisos para o principal do servizo de Customer Insights. Deben ser restaurados manualmente.

- A devasa da key vault está activada. O firewall debe estar desactivado para que a bóveda de claves sexa accesible de novo para Customer Insights.
