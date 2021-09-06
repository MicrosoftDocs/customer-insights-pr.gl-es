---
title: Enriquecer perfís de clientes unificados
description: Use capacidades para enriquecer os datos dos seus clientes.
ms.date: 07/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: a64bbd754d4013d0a6243074ac9f55991547be82b269047a9937b583baf98697
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032526"
---
# <a name="enrichment-for-customer-profiles-preview"></a>Enriquecemento dos perfís de clientes (vista previa)

Use datos de fontes como Microsoft e outros socios para enriquecer os seus datos de clientes.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Páxina da plataforma común de enriquecemento.":::

Na información do público, vaia a **Datos** > **Enriquecemento** para traballar con opcións de enriquecemento.  

Debe ter permisos de colaborador ou administrador para crear ou editar enriquecementos. Para obter máis información, consulte [Permisos](permissions.md).

No separador **Descubrir**, atopará os seguintes enriquecementos:

- [Marcas](enrichment-microsoft.md) fornecidas por Microsoft
- [Intereses](enrichment-microsoft.md) fornecidos por Microsoft
- [Enderezos mellorados](enrichment-enhanced-addresses.md) fornecidos por Microsoft
- [Datos da empresa](enrichment-leadspace.md) proporcionados por Leadspace
- [Demografía](enrichment-experian.md) fornecida por Experian
- [Datos de localización](enrichment-here.md) subministrados por HERE Technologies
- [Datos personalizados](enrichment-SFTP-custom-import.md) a través do protocolo seguro de transferencia de ficheiros (SFTP)

No separador **Os meus enriquecementos**, pode ver os enriquecementos que configurou e editar as súas propiedades.

## <a name="manage-existing-enrichments"></a>Xestionar os enriquecementos existentes

Vaia ao separador **Os meus enriquecementos** para ver todos os enriquecementos configurados. Cada enriquecemento represéntase como unha liña que inclúe información adicional sobre o enriquecemento.

Seleccione o enriquecemento para ver as opcións dispoñibles. Tamén pode seleccionar os puntos suspensivos (...) nun elemento da lista para ver as opcións. Se configurou varios enriquecementos, pode usar a caixa de busca para atopalo rapidamente.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Opcións para xestionar os enriquecementos na lista de enriquecementos.":::

- **Ver** detalles do enriquecemento co número de perfís de clientes enriquecidos.
- **Editar** a configuración do enriquecemento.
- **Execute** o enriquecemento para actualizar os perfís dos clientes cos últimos datos.
- **Desactivar** un enriquecemento existente para evitar que se actualice automaticamente con cada actualización programada. Os datos da última actualización exitosa seguirán dispoñibles. **Activar** un enriquecemento inactivo para reiniciar a actualización automática con cada actualización programada.
- **Eliminar** o enriquecemento.

Execute ou desactive varios enriquecementos á vez seleccionándoos na lista. As opcións de visualización e edición non están dispoñibles como accións en masa. Só funcionan para un enriquecemento á vez.

## <a name="enrichments-and-connections"></a>Enriquecementos e conexións

Os enriquecementos de terceiros configúranse usando [conexións](connections.md), que un administrador configura con credenciais e proporciona o consentimento para as transferencias de datos. A conexión pode ser usada para configurar enriquecementos por administradores e colaboradores.  

## <a name="multiple-enrichments-of-the-same-type"></a>Enriquecementos múltiples do mesmo tipo

A entidade que se vai enriquecer especifícase durante a configuración de enriquecemento, que lle permite enriquecer só un subconxunto dos seus perfís. Por exemplo, enriqueceza datos só para un segmento específico. Pode configurar varios enriquecementos do mesmo tipo e reutilizar a mesma conexión. Algúns enriquecementos terán límites do número de enriquecementos do mesmo tipo que se poden crear. Os límites e o uso actual pódense ver na páxina **Enriquecemento**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
