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
ms.openlocfilehash: 5b22c1464b3f089551f485f98d6d93840ff77136
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 02/25/2022
ms.locfileid: "8355889"
---
# <a name="bring-your-own-azure-key-vault-preview"></a>Traia a súa propia key vault de Azure (versión preliminar)

Ligar unha [Key vault de Azure](/azure/key-vault/general/basic-concepts) específica a un contorno de información sobre o público axuda ás organizacións a cumprir os requisitos de cumprimento.
A key vault específica pódese usar para probar e usar segredos no límite de cumprimento dunha organización. As estatísticas do público poden usar os segredos de Azure Key Vault para [configurar conexións](connections.md) a sistemas de terceiros.

## <a name="link-the-key-vault-to-the-audience-insights-environment"></a>Vincular a key vault ao contorno de información do público

### <a name="prerequisites"></a>Requisitos previos

Para configurar o key vault nas estatísticas do público, deben cumprirse os seguintes requisitos previos:

- Ten unha subscrición a Azure activa.

- Ten un rol de [Administrador](permissions.md#administrator) na información do público. Obteña máis información sobre [permisos do usuario en estatísticas de audiencia](permissions.md#assign-roles-and-permissions).

- Ten os roles de [Colaborador](/azure/role-based-access-control/built-in-roles#contributor) e [Administrador de acceso de usuario](/azure/role-based-access-control/built-in-roles#user-access-administrator) na key vault ou no grupo de recursos ao que pertence a key vault. Para obter máis información, vaia a [Engadir ou eliminar as asignacións de funcións de Azure usando o portal de Azure](/azure/role-based-access-control/role-assignments-portal). Se non ten a función de administrador de acceso de usuario no key vault, debe configurar os permisos de control de acceso baseados en funcións para o principal do servizo de Azure para Dynamics 365 Customer Insights por separado. Siga os pasos para [usar un principal de servizo de Azure](connect-service-principal.md) para a key vault que debería estar ligada.

- A key vault debe ter a devasa de Key Vault **desactivada**.

- A key vault está na mesma [localización de Azure](https://azure.microsoft.com/global-infrastructure/geographies/#overview) que o contorno da información do público. A rexión do contorno con información sobre o público aparece en **Administrador** > **Sistema** > **Acerca de** > **Rexión**.

### <a name="link-a-key-vault-to-the-environment"></a>Vincular unha key vault ao ambiente

1. Vaia a **Administrador** > **Sistema** e, a continuación, seleccione a pestana **Seguranza**.
1. No mosaico **Key Vault**, seleccione **Configurar**.
1. Escolla unha **Subscrición**.
1. Escolla unha key vault da lista despregable **Key Vault**. Se aparecen demasiadas key vault, seleccione un grupo de recursos para limitar os resultados da busca.
1. Acepte a declaración de **Privacidade e cumprimento dos datos**.
1. Seleccione **Gardar**.

:::image type="content" source="media/set-up-azure-key-vault.png" alt-text="Pasos para configurar un key vault ligado en información sobre o público.":::

O mosaico **Key Vault** agora amosa o nome do key vault ligado, o grupo de recursos e a subscrición. Está listo para usarse na configuración da conexión.
Para obter detalles sobre os permisos da key vault se conceden á información sobre o público, vaia a [Permisos concedidos na key vault para a información do público](#permissions-granted-on-the-key-vault-to-audience-insights), máis tarde neste artigo.

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

## <a name="permissions-granted-on-the-key-vault-to-audience-insights"></a>Permisos concedidos na key vault para a información do público

Os seguintes permisos concédense aos datos de audiencia nunha key vault ligada se a [Política de acceso a Key Vault](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) ou o [Control de acceso baseado en funcións de Azure](/azure/key-vault/general/rbac-guide?tabs=azure-cli) está activado.

### <a name="key-vault-access-policy"></a>Política de acceso a Key Vault

| Tipo        | Permisos          |
| ----------- | -------------------- |
| Tecla         | [Obter claves](/rest/api/keyvault/get-keys), [Obter clave](/rest/api/keyvault/get-key)                                 |
| Segredo      | [Obtén segredos](/rest/api/keyvault/get-secrets), [Obter segredo](/rest/api/keyvault/get-secret)                     |
| Certificado | [Obter certificados](/rest/api/keyvault/get-certificates), [Obter certificado](/rest/api/keyvault/get-certificate) |

Os valores anteriores son o mínimo para enumerar e ler durante a execución.

### <a name="azure-role-based-access-control"></a>Control de acceso baseado en funcións de Azure

Engadiranse os papeis de Usuario de Key Vault Reader e Key Vault Secrets para obter información sobre o público. Para obter máis detalles sobre estes roles, vaia a [Funcións integradas de Azure para operacións de plano de datos de Key Vault](/azure/key-vault/general/rbac-guide?tabs=azure-cli).

## <a name="recommendations"></a>Recomendacións

- Empregue unha key vault separada ou específica que só conteña os segredos necesarios para a información do público. Obteña máis información sobre por que [se recomendan key vaults separadas](/azure/key-vault/general/best-practices#why-we-recommend-separate-key-vaults).

- Siga as [prácticas recomendadas para usar Key Vault](/azure/key-vault/general/best-practices#turn-on-logging) para o acceso de control, a copia de seguridade, a auditoría e as opcións de recuperación.

## <a name="frequently-asked-questions"></a>Preguntas máis frecuentes

### <a name="can-audience-insights-write-secrets-or-overwrite-secrets-into-the-key-vault"></a>A información do público pode escribir ou sobrescribir segredos na key vault?

Non. Só os permisos de lectura e enumeración descritos na sección [permisos concedidos](#permissions-granted-on-the-key-vault-to-audience-insights) anterior deste artigo concédense á información do público. O sistema non pode engadir, eliminar nin sobrescribir segredos na key vault. Esa é tamén a razón pola que non pode introducir credenciais cando unha conexión usa Key Vault.

### <a name="can-i-change-a-connection-from-using-key-vault-secrets-to-default-authentication"></a>Podo cambiar unha conexión que use segredos de Key Vault pola autenticación predeterminada?

Non. Non pode volver a unha conexión predeterminada despois de configurala usando un segredo dunha key vault ligada. Cree unha conexión separada e elimine a antiga se xa non a necesita.

### <a name="how-can-i-revoke-access-to-a-key-vault-for-audience-insights"></a>Como podo revogar o acceso a unha key vault para obter información sobre o público?

Dependendo de se a [Política de acceso a Key Vault](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) ou o [Control de acceso baseado en funcións de Azure](/azure/key-vault/general/rbac-guide?tabs=azure-cli) está activado, ten que eliminar os permisos para o principal do servizo `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` co nome `Dynamics 365 AI for Customer Insights`. Todas as conexións que usan a key vault deixarán de funcionar.

### <a name="a-secret-thats-used-in-a-connection-got-removed-from-the-key-vault-what-can-i-do"></a>Un segredo que se usa nunha conexión foi eliminado da key vault. Que podo facer?

Aparece unha notificación nas estatísticas do público cando xa non se pode acceder a un segredo configurado desde a key vault. Active [eliminación temporal](/azure/key-vault/general/soft-delete-overview) na key vault para restaurar segredos se se eliminan accidentalmente.

### <a name="a-connection-doesnt-work-but-my-secret-is-in-the-key-vault-what-might-be-the-cause"></a>Unha conexión non funciona, pero o meu segredo está na key vault. Cal pode ser a causa?

Aparece unha notificación nas estatísticas do público cando non pode acceder ao key vault. A causa pode ser:

- Elimináronse os permisos para o director do servizo de información de audiencia. Deben ser restaurados manualmente.

- A devasa da key vault está activada. Débese desactivar a devasa para que a key vault sexa accesible de novo para a información do público.
