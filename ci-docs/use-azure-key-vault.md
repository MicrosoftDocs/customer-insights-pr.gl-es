---
title: Traia a súa propia key vault de Azure para xestionar segredos
description: Aprenda a configurar Customer Insights para usar a súa propia key vault de Azure.
ms.date: 10/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: 9eb06a1190fe4e8012ecd3d6742b8b3f5f4d6349
ms.sourcegitcommit: cf74b8c20d88eb96e1ac86e18cd44fe27aad5ab9
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 04/28/2022
ms.locfileid: "8653475"
---
# <a name="bring-your-own-azure-key-vault-preview"></a>Traia a súa propia key vault de Azure (versión preliminar)

Vincular un dedicado [Bóveda de chaves Azure](/azure/key-vault/general/basic-concepts) a un ambiente de Customer Insights axuda ás organizacións a cumprir os requisitos de cumprimento.
A key vault específica pódese usar para probar e usar segredos no límite de cumprimento dunha organización. Customer Insights pode usar os segredos de Azure Key Vault para [establecer conexións](connections.md) a sistemas de terceiros.

## <a name="link-the-key-vault-to-the-customer-insights-environment"></a>Vincula a bóveda de claves ao contorno de Customer Insights

### <a name="prerequisites"></a>Requisitos previos

Para configurar a bóveda de claves en Customer Insights, débense cumprir os seguintes requisitos previos:

- Ten unha subscrición a Azure activa.

- Tes un [Administrador](permissions.md#admin) papel en Customer Insights. Máis información sobre [permisos de usuario en Customer Insights](permissions.md#assign-roles-and-permissions).

- Ten os roles de [Colaborador](/azure/role-based-access-control/built-in-roles#contributor) e [Administrador de acceso de usuario](/azure/role-based-access-control/built-in-roles#user-access-administrator) na key vault ou no grupo de recursos ao que pertence a key vault. Para obter máis información, vaia a [Engadir ou eliminar as asignacións de funcións de Azure usando o portal de Azure](/azure/role-based-access-control/role-assignments-portal). Se non ten a función de administrador de acceso de usuario no key vault, debe configurar os permisos de control de acceso baseados en funcións para o principal do servizo de Azure para Dynamics 365 Customer Insights por separado. Siga os pasos para [usar un principal de servizo de Azure](connect-service-principal.md) para a key vault que debería estar ligada.

- A key vault debe ter a devasa de Key Vault **desactivada**.

- A bóveda de chaves está na mesma [Localización Azure](https://azure.microsoft.com/global-infrastructure/geographies/#overview) como o entorno de Customer Insights. A rexión do entorno en Customer Insights aparece en **Admin** > **Sistema** > **Sobre** > **Rexión**.

### <a name="link-a-key-vault-to-the-environment"></a>Vincular unha key vault ao ambiente

1. Ir a **Admin** > **Seguridade** e, a continuación, seleccione **Bóveda de chaves** ficha.
1. No mosaico **Key Vault**, seleccione **Configurar**.
1. Escolla unha **Subscrición**.
1. Escolla unha key vault da lista despregable **Key Vault**. Se aparecen demasiadas key vault, seleccione un grupo de recursos para limitar os resultados da busca.
1. Acepte a declaración de **Privacidade e cumprimento dos datos**.
1. Seleccione **Gardar**.

:::image type="content" source="media/set-up-azure-key-vault.png" alt-text="Pasos para configurar unha bóveda de claves vinculadas en Customer Insights.":::

O mosaico **Key Vault** agora amosa o nome do key vault ligado, o grupo de recursos e a subscrición. Está listo para usarse na configuración da conexión.
Para obter máis información sobre os permisos da bóveda de claves que se conceden a Customer Insights, vai a [Permisos concedidos na bóveda de chaves](#permissions-granted-on-the-key-vault), máis adiante neste artigo.

## <a name="use-the-key-vault-in-the-connection-setup"></a>Utilice a key vault na configuración da conexión

Ao [configurar conexións](connections.md) para sistemas de terceiros, pódense usar os segredos da Key Vault ligada para configurar as conexións.

1. Vaia a **Administrar** > **Conexións**.
1. Seleccione **Engadir conexión**.
1. Para os tipos de conexión admitidos, hai dispoñible un conmutador de **Usar Key Vault** se ligou unha key vault.
1. En lugar de introducir o segredo manualmente, pode escoller o nome secreto que apunta ao valor secreto na key vault.

:::image type="content" source="media/use-key-vault-secret.png" alt-text="Panel de conexión cunha conexión SFTP que usa un segredo de Key Vault.":::

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
| Tecla         | [Obter claves](/rest/api/keyvault/get-keys), [Obter clave](/rest/api/keyvault/get-key)                                 |
| Segredo      | [Obtén segredos](/rest/api/keyvault/get-secrets), [Obter segredo](/rest/api/keyvault/get-secret)                     |
| Certificado | [Obter certificados](/rest/api/keyvault/get-certificates), [Obter certificado](/rest/api/keyvault/get-certificate) |

Os valores anteriores son o mínimo para enumerar e ler durante a execución.

### <a name="azure-role-based-access-control"></a>Control de acceso baseado en funcións de Azure

Engadiranse os roles de usuario Key Vault Reader e Key Vault Secrets para Customer Insights. Para obter máis detalles sobre estes roles, vaia a [Funcións integradas de Azure para operacións de plano de datos de Key Vault](/azure/key-vault/general/rbac-guide?tabs=azure-cli).

## <a name="recommendations"></a>Recomendacións

- Use unha bóveda de claves separada ou dedicada que conteña só os segredos necesarios para Customer Insights. Obteña máis información sobre por que [se recomendan key vaults separadas](/azure/key-vault/general/best-practices#why-we-recommend-separate-key-vaults).

- Siga as [prácticas recomendadas para usar Key Vault](/azure/key-vault/general/best-practices#turn-on-logging) para o acceso de control, a copia de seguridade, a auditoría e as opcións de recuperación.

## <a name="frequently-asked-questions"></a>Preguntas máis frecuentes

### <a name="can-customer-insights-write-secrets-or-overwrite-secrets-into-the-key-vault"></a>Pode Customer Insights escribir segredos ou sobrescribir segredos na bóveda de claves?

Non. Só os permisos de lectura e lista indicados no [permisos concedidos](#permissions-granted-on-the-key-vault) sección anterior deste artigo concédense a Customer Insights. O sistema non pode engadir, eliminar nin sobrescribir segredos na key vault. Esa é tamén a razón pola que non pode introducir credenciais cando unha conexión usa Key Vault.

### <a name="can-i-change-a-connection-from-using-key-vault-secrets-to-default-authentication"></a>Podo cambiar unha conexión que use segredos de Key Vault pola autenticación predeterminada?

Non. Non pode volver a unha conexión predeterminada despois de configurala usando un segredo dunha key vault ligada. Cree unha conexión separada e elimine a antiga se xa non a necesita.

### <a name="how-can-i-revoke-access-to-a-key-vault-for-customer-insights"></a>Como podo revogar o acceso a unha bóveda de claves para Customer Insights?

Dependendo de se a [Política de acceso a Key Vault](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) ou o [Control de acceso baseado en funcións de Azure](/azure/key-vault/general/rbac-guide?tabs=azure-cli) está activado, ten que eliminar os permisos para o principal do servizo `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` co nome `Dynamics 365 AI for Customer Insights`. Todas as conexións que usan a key vault deixarán de funcionar.

### <a name="a-secret-thats-used-in-a-connection-got-removed-from-the-key-vault-what-can-i-do"></a>Un segredo que se usa nunha conexión foi eliminado da key vault. Que podo facer?

Aparece unha notificación en Customer Insights cando xa non se pode acceder a un segredo configurado da bóveda de claves. Active [eliminación temporal](/azure/key-vault/general/soft-delete-overview) na key vault para restaurar segredos se se eliminan accidentalmente.

### <a name="a-connection-doesnt-work-but-my-secret-is-in-the-key-vault-what-might-be-the-cause"></a>Unha conexión non funciona, pero o meu segredo está na key vault. Cal pode ser a causa?

Aparece unha notificación en Customer Insights cando non pode acceder á bóveda de claves. A causa pode ser:

- Elimináronse os permisos do principal do servizo de Customer Insights. Deben ser restaurados manualmente.

- A devasa da key vault está activada. O firewall debe estar desactivado para que a bóveda de claves sexa accesible de novo para Customer Insights.
