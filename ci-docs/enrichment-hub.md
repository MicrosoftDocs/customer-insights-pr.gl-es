---
title: Visión xeral do enriquecemento de datos (vista previa).
description: Use as capacidades de Microsoft e outros servizos de terceiros para enriquecer os datos dos seus clientes.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-enrichments
- ci-enrichment-details
- ci-enrichment-wizard
- customerInsights
ms.openlocfilehash: 0c2a900190b4ab6e93098d05a2fd66bcd2b847fd
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245877"
---
# <a name="data-enrichment-preview-overview"></a>Visión xeral do enriquecemento de datos (vista previa).

Use datos de fontes como Microsoft e outros socios para enriquecer os seus datos de clientes. Os enriquecementos de terceiros configúranse usando [conexións](connections.md), que un administrador configura con credenciais e proporciona o consentimento para as transferencias de datos. Tanto os administradores como os colaboradores poden usar as conexións para configurar os enriquecementos.  

## <a name="multiple-enrichments-of-the-same-type"></a>Enriquecementos múltiples do mesmo tipo

A entidade que se vai enriquecer especifícase durante a configuración de enriquecemento, que lle permite enriquecer só un subconxunto dos seus perfís. Por exemplo, enriqueceza datos só para un segmento específico. Pode configurar varios enriquecementos do mesmo tipo e reutilizar a mesma conexión. Algúns enriquecementos terán límites do número de enriquecementos do mesmo tipo que se poden crear. Os límites e o uso actual pódense ver en cada ficha do **Descubrir** ficha da **Enriquecemento** páxina.

## <a name="enrich-data-sources-before-unification"></a>Enriquece as fontes de datos antes da unificación

Podes enriquecer os datos dos teus clientes antes da unificación de datos para axudar a aumentar a calidade dunha coincidencia de datos. Para obter máis información, consulte [orixe de datos enriquecemento](data-sources-enrichment.md).

## <a name="create-an-enrichment"></a>Crear un enriquecemento

Necesitas ter Colaborador ou Administrador [permisos](permissions.md) para crear ou editar enriquecementos.

Vaia a **Datos** > **Enriquecemento**. O **Descubrir** mostra todas as opcións de enriquecemento compatibles.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Páxina da plataforma común de enriquecemento.":::

# <a name="individual-consumers-b-to-c"></a>[Consumidores individuais (B2C)](#tab/b2c)

- [Identidade AbiliTec](enrichment-liveramp.md) proporcionado por LiveRamp AbiliTec
- [Marcas](enrichment-microsoft.md) fornecidas por Microsoft
- [Demografía](enrichment-experian.md) fornecida por Experian
- [Enderezos mellorados](enrichment-enhanced-addresses.md) fornecidos por Microsoft
- [Intereses](enrichment-microsoft.md) fornecidos por Microsoft
- [Datos de localización](enrichment-azure-maps.md) proporcionado por Microsoft Azure Mapas
- [Datos de localización](enrichment-here.md) subministrados por HERE Technologies
- [Datos personalizados SFTP](enrichment-SFTP-custom-import.md) a través do protocolo de transferencia segura de ficheiros (SFTP)

# <a name="business-accounts-b-to-b"></a>[Contas empresariais (B2B)](#tab/b2b)

- [Datos de participación da conta](enrichment-office.md) proporcionado por Microsoft
- [Datos da empresa](enrichment-dnb.md) proporcionado por Dun & Bradstreet
- [Datos da empresa](enrichment-leadspace.md) proporcionados por Leadspace
- [Enderezos mellorados](enrichment-enhanced-addresses.md) fornecidos por Microsoft
- [Datos da empresa mellorados](enrichment-enhanced-company-data.md) proporcionado por Microsoft
- [Datos de localización](enrichment-azure-maps.md) proporcionado por Microsoft Azure Mapas
- [Datos de localización](enrichment-here.md) subministrados por HERE Technologies
- [Datos personalizados SFTP](enrichment-SFTP-custom-import.md) a través do protocolo de transferencia segura de ficheiros (SFTP)

---

## <a name="manage-existing-enrichments"></a>Xestionar os enriquecementos existentes

Vaia a **Datos** > **Enriquecemento**. No **Os meus enriquecementos** pestana, ver os enriquecementos configurados, o seu estado, o número de clientes enriquecidos e a última vez que se actualizaron os datos. Podes ordenar a lista de enriquecementos por calquera columna ou utilizar a caixa de busca para atopar o enriquecemento que queres xestionar.

Seleccione o enriquecemento para ver as accións dispoñibles.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Opcións para xestionar os enriquecementos na lista de enriquecementos.":::

- **Ver** detalles do enriquecemento co número de perfís de clientes enriquecidos.
- **Editar** a configuración do enriquecemento.
- [**Corre**](#run-or-refresh-enrichments) o enriquecemento para actualizar os perfís dos clientes cos datos máis recentes. Executa varios enriquecementos á vez seleccionándoos na lista.
- **Activar** ou **Desactivar** un enriquecemento. Os enriquecementos inactivos non se actualizarán durante a [actualización programada](schedule-refresh.md).
- **Eliminar** o enriquecemento.

Tamén podes crear [segmentos](segments.md) ou [medidas](measures.md) de enriquecementos.

## <a name="run-or-refresh-enrichments"></a>Executar ou actualizar enriquecementos

Unha vez executados, os enriquecementos pódense actualizar nunha programación automática ou actualizar manualmente baixo demanda.

1. Para actualizar manualmente un ou máis enriquecementos, selecciónaos e escólleos **Corre**. Para [programar unha actualización automática](schedule-refresh.md), Ir a **Admin** > **Sistema** > **Horario**. O tempo de procesamento depende do tamaño dos datos dos clientes.

1. Opcionalmente, [ver o progreso do proceso de enriquecemento](#see-the-progress-of-the-enrichment-process).

1. Despois de completar o proceso de enriquecemento, vai a **Os meus enriquecementos** para revisar os datos dos perfís de clientes recentemente enriquecidos, a hora da última actualización e o número de perfís enriquecidos.

1. Seleccione o enriquecemento para ver [resultados de enriquecemento](#view-enrichment-results).

### <a name="see-the-progress-of-the-enrichment-process"></a>Vexa o progreso do proceso de enriquecemento

Pode atopar detalles sobre o procesamento dun enriquecemento, incluído o estado e os problemas potenciais mentres se actualiza ou despois de completar a actualización. Comprenda que procesos están implicados para actualizar un enriquecemento e canto tardou en executalos. Admítese o estado de enriquecemento para Experian, Leadspace, HERE Technologies, SFTP Import e Azure Maps.

1. Vaia a **Datos** > **Enriquecemento**.
1. No **Os meus enriquecementos** ficha, seleccione o estado do enriquecemento para abrir un panel lateral.
1. No panel **Detalles do progreso**, expanda a sección **Enriquecementos**.
1. No enriquecemento no que desexa ver o progreso, seleccione **Ver detalles**.
1. No panel **Detalles da tarefa**, seleccione **Amosar detalles** para ver os procesos implicados na actualización do enriquecemento e o seu estado.

[!INCLUDE [progress-details-pane](includes/progress-details-pane.md)]

## <a name="view-enrichment-results"></a>Ver resultados de enriquecemento

Despois dunha carreira de enriquecemento completada, revise os resultados do enriquecemento.

1. Vaia a **Datos** > **Enriquecemento**.
1. No **Os meus enriquecementos** ficha, seleccione o enriquecemento que desexa ver.

Todos os enriquecementos mostran información básica como o número de perfís enriquecidos e o número de perfís enriquecidos ao longo do tempo. O **Vista previa de clientes enriquecidos** o mosaico mostra unha mostra da entidade de enriquecemento xerada. Para ver unha vista detallada, seleccione **Ver máis** e selecciona o **Datos** ficha.

:::image type="content" source="media/enrichments-results.png" alt-text="Páxina de resultados de enriquecementos.":::

Se está dispoñible, o **Número de clientes enriquecidos por campo** proporciona un detalle da cobertura de cada campo enriquecido.

Algúns enriquecementos tamén mostran información específica do tipo de enriquecemento. Para obter máis información, consulte a documentación relacionada.

[!INCLUDE [footer-include](includes/footer-banner.md)]
