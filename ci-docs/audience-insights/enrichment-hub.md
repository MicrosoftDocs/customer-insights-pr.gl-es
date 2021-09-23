---
title: Enriquecer perfís de clientes unificados
description: Use capacidades para enriquecer os datos dos seus clientes.
ms.date: 08/31/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 992c45e30e2dff00f5207290940b56b2fe1c08ad
ms.sourcegitcommit: b9a81c2acd42d774669d2db3d0430c7d81de991c
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 09/02/2021
ms.locfileid: "7469970"
---
# <a name="enrichment-for-customer-profiles-preview"></a>Enriquecemento dos perfís de clientes (vista previa)

Use datos de fontes como Microsoft e outros socios para enriquecer os seus datos de clientes.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Páxina da plataforma común de enriquecemento.":::

Na información do público, vaia a **Datos** > **Enriquecemento** para traballar con opcións de enriquecemento.  

Debe ter permisos de colaborador ou administrador para crear ou editar enriquecementos. Para obter máis información, consulte [Permisos](permissions.md).

No separador **Descubrir**, atopará os seguintes enriquecementos:

- [Azure Maps](enrichment-azure-maps.md) fornecido por Microsoft
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

## <a name="see-the-progress-of-the-enrichment-process"></a>Vexa o progreso do proceso de enriquecemento

Pode atopar detalles sobre o procesamento dun enriquecemento, incluído o estado e os problemas potenciais mentres se actualiza ou despois de completar a actualización. Comprenda que procesos están implicados para actualizar un enriquecemento e canto tardou en executalos. Admítese o estado de enriquecemento para Experian, Leadspace, HERE Technologies, SFTP Import e Azure Maps.

Para ver o estado dun enriquecemento

1. Vaia a **Datos** > **Enriquecemento**. 
1. No separador **Os meus enriquecementos**, seleccione o estado dun enriquecemento para abrir un panel lateral. 
1. No panel **Detalles do progreso**, expanda a sección **Enriquecementos**. 
1. No enriquecemento no que desexa ver o progreso, seleccione **Ver detalles**. 
1. No panel **Detalles da tarefa**, seleccione **Amosar detalles** para ver os procesos implicados na actualización do enriquecemento e o seu estado. 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
