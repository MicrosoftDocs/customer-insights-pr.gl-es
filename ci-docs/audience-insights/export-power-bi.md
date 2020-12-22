---
title: Conector de Power BI
description: Obteña información acerca de como usar o conector de Dynamics 365 Customer Insights en Power BI.
ms.date: 09/21/2020
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d497ca779a337c512a7254524f597cff226bcb45
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405698"
---
# <a name="connector-for-power-bi-preview"></a>Conector de Power BI (vista previa)

Cree visualizacións para os seus datos con Power BI Desktop. Xere información adicional e cree informes cos seus datos de clientes unificados.

## <a name="prerequisites"></a>Requisitos previos

- Ten perfís de clientes unificados.
- A última versión de [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) está instalada no seu computador. [Obtén máis información acerca de Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).

## <a name="configure-the-connector-for-power-bi"></a>Configurar o conector de Power BI

1. En Power BI Desktop, seleccione **Ficheiro** > **Obter datos**.

1. Seleccione **Ver máis** e busque **Dynamics 365 Customer Insights**

1. Seleccione o resultado e **Conectar**.

1. **Inicie sesión** coa mesma conta organizativa que usa para Customer Insights e seleccione **Conectar**.
   > [!NOTE]
   > A conta que indique neste paso úsase para buscar datos de Customer Insights e non ten por que ser a mesma na que iniciou sesión en Power BI. Para restablecer a conta que se usa para a obtención de datos, abra Power BI e vaia a **Ficheiro** > **Opcións** > **Configuración** > **Configuración de orixe de datos**. Na lista de orixes de datos, seleccione **Inicio de sesión en Dynamics 365 Customer Insights** e seleccione **Borrar permisos**.  

1. Na caixa de diálogo **Navegador**. ve a lista de todos os ambientes aos que ten acceso. Amplíe un contorno e abra calquera das carpetas (entidades, medidas, segmentos, enriquecementos). Por exemplo, abra o cartafol **Entidades** para ver todas as entidades que pode importar.

   ![Power BI Connector Navigator](media/power-bi-navigator.png "Power BI Connector Navigator")

1. Seleccione as caixas de verificación xunto ás entidades que hai que incluír e **Cargar**. Pode seleccionar varias entidades de varios ambientes.

1. Verá unha caixa de diálogo de carga mentres se cargan as súas entidades. Unha vez cargadas todas as entidades seleccionadas, pode empregar as capacidades de Power BI para visualizar os datos.

## <a name="large-data-sets"></a>Conxuntos de datos grandes

O conector Customer Insights para Power BI está deseñado para funcionar con conxuntos de datos que conteñen ata 1 millón de perfís de clientes. A importación de conxuntos de datos máis grandes pode funcionar, pero leva moito tempo. Ademais, o proceso podería ter un tempo de espera debido ás limitacións de Power BI. Para obter máis información, consulte [Power BI: recomendacións para grandes conxuntos de datos](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets). 

### <a name="work-with-a-subset-of-data"></a>Traballar cun subconxunto de datos

Considere traballar cun subconxunto dos seus datos. Por exemplo, pode crear [segmentos](segments.md) en vez de exportar todos os rexistros de clientes a Power BI.
