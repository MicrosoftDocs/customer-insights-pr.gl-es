---
title: Conexións a outros servizos de Customer Insights.
description: Comparta datos con outros servizos.
ms.date: 04/09/2021
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: overview
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: e78e18b75ee9797b5fc76486615992e301e4c650
ms.sourcegitcommit: bb1ca84bc38e81fb2ff2961c457384b7beb5b5fa
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 01/15/2022
ms.locfileid: "7977735"
---
# <a name="connections-preview-overview"></a>Visión xeral de conexións (versión preliminar)

As conexións son a clave para permitir o intercambio de datos desde e ata Customer Insights. Cada conexión establece o uso compartido de datos cun servizo específico. As conexións son a base para [configurar enriquecementos de terceiros](enrichment-hub.md) e [configurar as exportacións](export-destinations.md). A mesma conexión pódese usar varias veces. Por exemplo, unha conexión a Dynamics 365 Marketing funciona para exportacións múltiples e unha conexión de Leadspace pode usarse para varios enriquecementos.

Vaia a **Administrar** > **Conexións** para crear e ver conexións.

O separador **Conexións** mostra todas as conexións activas. A lista mostra unha fila para cada conexión. 

Obteña unha visión xeral rápida, descrición e descubra o que pode facer con cada opción de extensibilidade no separador **Descubrir**.

### <a name="exports"></a>Exportacións

Só os administradores poden configurar novas conexións, pero poden conceder acceso aos colaboradores para que empreguen as conexións existentes. Os administradores controlan onde poden ir os datos, os colaboradores definen a carga útil e a frecuencia que se axustan ás súas necesidades. Para obter máis información, consulte [Permitir aos colaboradores usar unha conexión para as exportacións](#allow-contributors-to-use-a-connection-for-exports).

### <a name="enrichments"></a>Enriquecementos

Só os administradores poden configurar novas conexións, pero as conexións creadas están sempre dispoñibles tanto para administradores como para colaboradores. Os administradores xestionan as credenciais e consenten as transferencias de datos. As conexións poden ser usadas para enriquecementos por administradores e colaboradores.

## <a name="add-a-new-connection"></a>Engadir unha nova conexión

Para engadir conexións, cómpre ter [permisos de administrador](permissions.md). Se se conecta a outros servizos de Microsoft, supoñemos que ambos os servizos están na mesma organización.

1. Vaia a **Administrar** > **Conexións (versión preliminar)**.

1. Vaia ao separador **Conexións**.

1. Seleccione **Engadir conexión** para crear unha nova conexión. Escolla no menú despregable o tipo de conexión que desexa crear.

1. No panel **Configurar a conexión**, proporcione os detalles requiridos. 
   1. O **Nome de visualización** e o tipo de conexión describen unha conexión. Recomendamos escoller un nome que explique o propósito e o destino desta conexión.
   1. Os campos exactos dependen do servizo ao que se conecte. Pode coñecer os detalles dun tipo de conexión específico no artigo sobre o servizo de destino.
   1. Se [usa o seu propio Key Vault](use-azure-key-vault.md) para gardar segredos, active **Usar Key Vault** e escolla o segredo da lista.

1. Seleccione **Gardar** para crear a conexión.

Tamén pode seleccionar **Configurar** nun mosaico do separador **Descubrir**.

### <a name="allow-contributors-to-use-a-connection-for-exports"></a>Permitir aos colaboradores usar unha conexión para exportacións

Ao configurar ou editar unha conexión de exportación, elixa aos usuarios que poden usar esta conexión específica para definir [exportacións](export-destinations.md). De xeito predeterminado, hai unha conexión dispoñible para usuarios con función de administrador. Pode cambiar esta configuración en **Escoller quen pode usar esta conexión** e permitir aos usuarios con función de colaborador usar esta conexión.

- Os colaboradores non poderán ver nin editar a conexión. Só verán o nome de visualización e o seu tipo ao crear unha exportación.
- Ao compartir unha conexión, permítelle aos colaboradores usar unha conexión. Os colaboradores verán as conexións compartidas cando configuren as exportacións. Poden xestionar todas as exportacións que utilizan esta conexión específica.
- Pode cambiar esta configuración mantendo as exportacións que xa foron definidas polos colaboradores.

## <a name="edit-a-connection"></a>Editar unha conexión

1. Vaia a **Administrar** > **Conexións (versión preliminar)**.

1. Vaia ao separador **Conexións**.

1. Seleccione os tres puntos verticais para a conexión que desexa editar.

1. Seleccione **Editar**.

1. Cambie os valores que desexa actualizar e seccione **Gardar**.

## <a name="remove-a-connection"></a>Eliminar unha conexión

Se a conexión que vai eliminar é utilizada por enriquecementos ou exportacións, primeiro cómpre desprendela ou eliminala. O diálogo de eliminación guiarao aos enriquecementos ou exportacións relevantes. 

Os enriquecementos e exportacións desconectados quedan inactivos. Reactíveos engadíndolles outra conexión na páxina [Enriquecementos](enrichment-hub.md) ou [Exportacións](export-destinations.md).

1. Vaia a **Administrar** > **Conexións (versión preliminar)**.

1. Vaia ao separador **Conexións**.

1. Seleccione os tres puntos verticais para a conexión que desexa eliminar.

1. Seleccione **Eliminar** do menú despregable. Aparecerá un diálogo de confirmación.

   1. Se hai enriquecementos ou exportacións usando esta conexión, seleccione o botón para ver que está a usar a conexión.
      - **Exportacións:** Pode eliminar ou desconectar as exportacións para poder eliminar a conexión. Para desconectar unha exportación, os administradores poden usar a acción **Desconectar**. Esta acción está dispoñible para exportacións individuais e múltiples seleccionadas. Ao desconectar manterá a configuración de exportación, pero non se executará ata que se lle engada outra conexión.
      - **Enriquecementos:** Pode eliminar ou desactivar os enriquecementos para poder eliminar a conexión. 
   1. Unha vez que a conexión non teña máis dependencias, volva a **Administrar** > **Conexións** e tente eliminar de novo a conexión.

1. Para confirmar a eliminación, seleccione **Quitar**.

## <a name="set-up-connections-with-secrets-managed-by-your-own-key-vault"></a>Configurar conexións con segredos xestionados polo seu Key Vault

Algunhas conexións precisan segredos como claves ou contrasinais de API. Algunhas conexións admiten segredos almacenados no seu Key Vault. Máis información sobre as conexións compatibles e como configurar [o seu propio Key Vault para obter información sobre o público](use-azure-key-vault.md).
