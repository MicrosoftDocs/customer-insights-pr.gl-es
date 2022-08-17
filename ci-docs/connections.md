---
title: Visión xeral de conexións (versión preliminar)
description: Conexións a outros servizos de Customer Insights.
ms.date: 08/04/2022
ms.reviewer: nikeller
ms.subservice: audience-insights
ms.topic: overview
author: m-hartmann
ms.author: mhart
manager: shellyha
searchScope:
- ci-connections
- customerInsights
ms.openlocfilehash: 8580dc7d90c75f66f73efc15f8e38f5e10fbb8a7
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245509"
---
# <a name="connections-preview-overview"></a>Visión xeral de conexións (versión preliminar)

As conexións son a clave para permitir o intercambio de datos desde e ata Customer Insights. Cada conexión establece o uso compartido de datos cun servizo específico. Use conexións para [configurar enriquecementos de terceiros](enrichment-hub.md) e [configurar as exportacións](export-destinations.md). A mesma conexión pódese usar varias veces. Por exemplo, unha conexión a Dynamics 365 Marketing funciona para exportacións múltiples e unha conexión de Leadspace pode usarse para varios enriquecementos.

## <a name="export-connections"></a>Exportar conexións

Só os administradores poden configurar novas conexións, pero si poden [conceder acceso aos colaboradores](#allow-contributors-to-use-a-connection-for-exports) para utilizar as conexións existentes. Os administradores controlan onde poden ir os datos, os colaboradores definen a carga útil e a frecuencia que se axustan ás súas necesidades.

## <a name="enrichment-connections"></a>Conexións de enriquecemento

Só os administradores poden configurar novas conexións, pero as conexións creadas sempre están dispoñibles tanto para os administradores como para os colaboradores. Os administradores xestionan as credenciais e consenten as transferencias de datos. As conexións poden ser usadas para enriquecementos por administradores e colaboradores.

## <a name="add-a-new-connection"></a>Engadir unha nova conexión

### <a name="prerequisites"></a>Requisitos previos

- [Permisos de administrador](permissions.md)
- Outros servizos de Microsoft, se os hai, están na mesma organización

1. Vaia a **Administrar** > **Conexións**.

1. Seleccione **Engadir conexión** e escolla o tipo de conexión que quere crear. Ou, vai ao **Descubrir** ficha e seleccione **Montar** nunha ficha de conexión.

1. Déalle á conexión un nome recoñecible no campo **Nome para mostrar**. O nome e o tipo de conexión describen esta conexión. Recomendamos escoller un nome que explique o propósito e o destino da conexión.

1. Introduza os detalles necesarios. Os campos exactos dependen do servizo ao que te conectes. Para obter máis información sobre un tipo de conexión específico, consulte o artigo sobre o servizo de destino.

1. Se [usa o seu propio Key Vault](use-azure-key-vault.md) para gardar segredos, active **Usar Key Vault** e escolla o segredo da lista.

1. Revisa a privacidade e o cumprimento dos datos e selecciona **Estou de acordo**.

1. Seleccione **Gardar** para crear a conexión.

### <a name="data-privacy-and-compliance"></a>Cumprimento e privacidade dos datos

Cando habilitas Dynamics 365 Customer Insights para transmitir datos a terceiros ou outros produtos de Microsoft, vostede permite a transferencia de datos fóra dos límites de conformidade Dynamics 365 Customer Insights, incluíndo datos potencialmente sensibles, como os datos persoais. Microsoft transferirá eses datos segundo as súas instrucións, pero vostede é responsable de asegurarse de que o terceiro cumpra as obrigas de privacidade ou seguridade que poida ter. Para obter máis información, consulte a [Declaración de privacidade de Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

O teu Dynamics 365 Customer Insights o administrador pode eliminar a conexión en calquera momento para deter o uso da funcionalidade.

## <a name="allow-contributors-to-use-a-connection-for-exports"></a>Permitir aos colaboradores usar unha conexión para exportacións

Ao configurar ou editar unha conexión de exportación, escolla que usuarios poden usar esta conexión específica para definir [exportacións](export-destinations.md). Por defecto, hai unha conexión dispoñible para os usuarios con función de administrador. Cambia o **Escolle quen pode usar esta conexión** configuración para permitir que os usuarios con función de colaborador usen esta conexión.

- Os colaboradores non poderán ver nin editar a conexión. Só verán o nome para mostrar e o seu tipo ao crear unha exportación.
- Ao compartir unha conexión, permítelle aos colaboradores usar unha conexión. Os colaboradores verán as conexións compartidas cando configuren as exportacións. Poden xestionar todas as exportacións que utilizan esta conexión específica.
- Pode cambiar esta configuración mantendo as exportacións que xa foron definidas polos colaboradores.

## <a name="manage-existing-connections"></a>Xestionar as conexións existentes

1. Vaia a **Administrar** > **Conexións**.

1. Seleccione o **Enriquecemento** ou **Exportacións** para ver unha lista de conexións de enriquecemento ou exportación, o tipo de conexión, cando se creou e quen ten acceso. Pode ordenar a lista de conexións por calquera columna.

1. Seleccione a conexión para ver as accións dispoñibles.

   - **Editar** a conexión.
   - [**Quitar**](#remove-a-connection) unha conexión.

### <a name="remove-a-connection"></a>Eliminar unha conexión

Se a conexión que estás a eliminar é usada por enriquecementos ou exportacións, primeiro deslámaas ou eliminalas. O diálogo de eliminación guíalle cara aos enriquecementos ou exportacións relevantes.

> [!TIP]
> Os enriquecementos desactivados e as exportacións separadas quedan inactivas. Reactíveos engadíndolles outra conexión na páxina [Enriquecementos](enrichment-hub.md) ou [Exportacións](export-destinations.md).

1. Vaia a **Administrar** > **Conexións**.

1. Seleccione o **Enriquecemento** ou **Exportacións** ficha.

1. Seleccione a conexión que quere eliminar.

1. Seleccione **Eliminar** do menú despregable. Aparecerá un diálogo de confirmación.

   1. Se hai enriquecementos ou exportacións usando esta conexión, seleccione o botón para ver que está a usar a conexión.
      - **Exportacións:** Escolla calquera delas **Quitar** a exportación ou **Desconecta a conexión**. Desconectar a conexión mantén a configuración de exportación, pero non se executará ata que se lle engada outra conexión.
      - **Enriquecementos:** Escolla calquera delas **Eliminar** ou **Desactivar** os enriquecementos.
   1. Unha vez que a conexión non teña máis dependencias, volva a **Administrar** > **Conexións** e tente eliminar de novo a conexión.

1. Para confirmar a eliminación, seleccione **Quitar**.

## <a name="set-up-connections-with-secrets-managed-by-your-own-key-vault"></a>Configurar conexións con segredos xestionados polo seu Key Vault

Algunhas conexións precisan segredos como claves ou contrasinais de API. Algunhas conexións admiten segredos almacenados no seu Key Vault. Obtén máis información sobre as conexións compatibles e sobre como configuralas [o teu propio Key Vault para Customer Insights](use-azure-key-vault.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
