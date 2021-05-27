---
title: Enriquecer perfís de clientes unificados
description: Use capacidades para enriquecer os datos dos seus clientes.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: c8e4a7247ccf575a62440038180010916b09d51b
ms.sourcegitcommit: f9e2fa3f11ecf11a5d9cccc376fdeb1ecea54880
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 04/28/2021
ms.locfileid: "5954485"
---
# <a name="enrichment-for-customer-profiles-preview"></a>Enriquecemento dos perfís de clientes (vista previa)

Use datos de fontes como Microsoft e outros socios para enriquecer os seus datos de clientes.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Páxina da plataforma común de enriquecemento":::

Na información do público, vaia a **Datos** > **Enriquecemento** para traballar con opcións de enriquecemento.    
Debe ter permisos de colaborador ou administrador para crear ou editar enriquecementos. Para obter máis información, consulte [Permisos](permissions.md).

No separador **Descubrir**, atopará os seguintes enriquecementos:

- [Marcas](enrichment-microsoft.md) fornecidas por Microsoft
- [Intereses](enrichment-microsoft.md) fornecidos por Microsoft
- [Enderezos mellorados](enrichment-enhanced-addresses.md) fornecidos por Microsoft
- [Datos da empresa](enrichment-leadspace.md) proporcionados por Leadspace
- [Datos demográficos](enrichment-experian.md) proporcionados por Experian
- [Datos de localización](enrichment-here.md) subministrados por HERE Technologies
- [Datos personalizados](enrichment-SFTP-custom-import.md) a través do protocolo seguro de transferencia de ficheiros (SFTP)

No separador **Os meus enriquecementos**, pode ver os enriquecementos que configurou e editar as súas propiedades.

## <a name="manage-existing-enrichments"></a>Xestionar os enriquecementos existentes

Vaia a **Os meus enriquecementos** para ver todos os enriquecementos configurados. Cada enriquecemento represéntase como unha liña que inclúe información adicional sobre o enriquecemento.

Seleccione un enriquecemento para ver as opcións dispoñibles. Tamén pode seleccionar os puntos suspensivos (...) nun elemento da lista para ver as opcións.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Opcións para xestionar os enriquecementos na lista de enriquecementos":::

- **Ver** detalles do enriquecemento co número de perfís de clientes enriquecidos.
- **Editar** a configuración do enriquecemento.
- **Execute** o enriquecemento para actualizar os perfís dos clientes cos últimos datos.
- **Desactivar** un enriquecemento existente para evitar que se actualice automaticamente con cada actualización programada. Os datos da última actualización exitosa seguirán dispoñibles. **Activar** un enriquecemento inactivo para reiniciar a actualización automática con cada actualización programada.
- **Eliminar** un enriquecemento.

Pode executar ou desactivar varios enriquecementos á vez seleccionándoos na lista. As opcións de visualización e edición non están dispoñibles como acción masiva e só funcionan para un enriquecemento á vez.

## <a name="enrichments-and-connections"></a>Enriquecementos e conexións

Os enriquecementos de terceiros configúranse usando [conexións](connections.md), que un administrador configura con credenciais e proporciona o consentimento para as transferencias de datos. A conexión pode ser usada para configurar enriquecementos por administradores e colaboradores.  

## <a name="multiple-enrichments-of-the-same-type"></a>Enriquecementos múltiples do mesmo tipo

A entidade que se vai enriquecer especifícase durante a configuración de enriquecemento, que lle permite enriquecer só un subconxunto dos seus perfís. Por exemplo, enriqueza os datos só dun segmento específico. Pode configurar varios enriquecementos do mesmo tipo e reutilizar a mesma conexión. Algúns enriquecementos terán límites do número de enriquecementos do mesmo tipo que se poden crear. Os límites e o uso actual pódense ver na páxina **Enriquecemento**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
