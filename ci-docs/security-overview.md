---
title: Configuración de seguridade en Dynamics 365 Customer Insights
description: Obtén información sobre a configuración de seguranza en Dynamics 365 Customer Insights.
ms.date: 04/28/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 5d73bacccadc9193d76d8dfafd0365dabc911e00
ms.sourcegitcommit: cf74b8c20d88eb96e1ac86e18cd44fe27aad5ab9
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 04/28/2022
ms.locfileid: "8653788"
---
# <a name="security-overview-page"></a>Páxina de resumo da seguridade

O **Seguridade** páxina lista opcións para configurar os permisos de usuario e funcións que axudan a facer Dynamics 365 Customer Insights máis seguro. Só os administradores poden acceder a esta páxina. 

Ir a **Admin** > **Seguridade** para configurar os axustes.

O **Seguridade** páxina inclúe as seguintes pestanas:
- [Usuarios](#users-tab)
- [API](#apis-tab)
- [Key Vault](#key-vault-tab)

## <a name="users-tab"></a>Ficha Usuarios

O acceso a Customer Insights está restrinxido aos usuarios da túa organización que foron engadidos á aplicación por un administrador. O **Usuarios** permite xestionar o acceso dos usuarios e os seus permisos. Para obter máis información, consulte [Permisos de usuario](permissions.md).

## <a name="apis-tab"></a>Pestana APIs

Consulta e xestiona as claves para usar o [API de Customer Insights](apis.md) cos datos do seu entorno.

Podes crear novas chaves primarias e secundarias seleccionando **Rexenerar primaria** ou **Rexenerar secundaria**. 

Para bloquear o acceso da API ao contorno, seleccione **Desactivar**. Se as API están desactivadas, podes seleccionar **Activar** para conceder acceso de novo.

## <a name="key-vault-tab"></a>Pestana Key Vault

O **Bóveda de chaves** pestana permíteche vincular e xestionar o teu propio [Bóveda de chaves Azure](/azure/key-vault/general/basic-concepts) ao medio ambiente.
A key vault específica pódese usar para probar e usar segredos no límite de cumprimento dunha organización. Customer Insights pode usar os segredos de Azure Key Vault para [establecer conexións](connections.md) a sistemas de terceiros.

Para obter máis información, consulte [Traer o seu propio Azure Key Vault](use-azure-key-vault.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]
