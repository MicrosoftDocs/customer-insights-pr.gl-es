---
title: Enriquecer perfís de clientes unificados
description: Use capacidades para enriquecer os datos dos seus clientes.
ms.date: 11/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c25cfbf3808fc1534b54d2d834f1c63ff4c9fe0a
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667092"
---
# <a name="enrichment-for-customer-profiles-preview"></a>Enriquecemento dos perfís de clientes (vista previa)

Use datos de fontes como Microsoft e outros socios para enriquecer os seus datos de clientes.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Páxina da plataforma común de enriquecemento":::

Na información do público, vaia a **Datos** > **Enriquecemento** para traballar con opcións de enriquecemento.    
Debe ter permisos de colaborador ou administrador para crear ou editar enriquecementos. Para obter máis información, consulte [Permisos](permissions.md).

No separador **Descubrir**, atopará os seguintes enriquecementos:

- [Marcas](enrichment-microsoft-graph.md) fornecidas por Microsoft Graph
- [Intereses](enrichment-microsoft-graph.md) fornecidos por Microsoft Graph
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
