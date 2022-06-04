---
title: Conector de Power BI
description: Obteña información acerca de como usar o conector de Dynamics 365 Customer Insights en Power BI.
ms.date: 07/23/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: e901114703a43b4b4e751e0a93eb4876d7636c00
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642793"
---
# <a name="connector-for-power-bi-preview"></a>Conector de Power BI (vista previa)

Cree visualizacións para os seus datos con Power BI Desktop. Xere información adicional e cree informes cos seus datos de clientes unificados.

## <a name="prerequisites"></a>Requisitos previos

- Ten perfís de clientes unificados.
- A última versión de [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) está instalado no seu computador. [Obtén máis información acerca de Power BI Desktop](/power-bi/desktop-what-is-desktop).

## <a name="configure-the-connector-for-power-bi"></a>Configurar o conector de Power BI

1. En Power BI Desktop, seleccione **Ficheiro** > **Obter datos**.

1. Seleccione **Ver máis** e busque **Dynamics 365 Customer Insights**

1. Seleccione **Conectar**.

1. **Inicie sesión** coa mesma conta organizativa que usa para Customer Insights e seleccione **Conectar**.
   > [!NOTE]
   > A conta que indique neste paso úsase para buscar datos de Customer Insights e non ten por que ser a mesma na que iniciou sesión en Power BI. Para restablecer a conta que se usa para a obtención de datos, abra Power BI e vaia a **Ficheiro** > **Opcións** > **Configuración** > **Configuración de orixe de datos**. Na lista de orixes de datos, seleccione **Inicio de sesión en Dynamics 365 Customer Insights** e seleccione **Borrar permisos**.  

1. Na caixa de diálogo **Navegador**. ve a lista de todos os ambientes aos que ten acceso. Amplíe un contorno e abra calquera das carpetas (entidades, medidas, segmentos, enriquecementos). Por exemplo, abra o cartafol **Entidades** para ver todas as entidades que pode importar.

   ![Power BI Connector Navigator.](media/power-bi-navigator.png "Power BI Connector Navigator")

1. Seleccione as caixas de verificación xunto ás entidades que hai que incluír e **Cargar**. Pode seleccionar varias entidades de varios ambientes.

1. Verá unha caixa de diálogo de carga mentres se cargan as súas entidades. Unha vez cargadas todas as entidades seleccionadas, pode empregar as capacidades de Power BI para visualizar os datos.

## <a name="large-data-sets"></a>Conxuntos de datos grandes

O conector Customer Insights para Power BI está deseñado para funcionar con conxuntos de datos que conteñen ata 1 millón de perfís de clientes. A importación de conxuntos de datos máis grandes pode funcionar, pero leva moito tempo. Ademais, o proceso podería ter un tempo de espera debido ás limitacións de Power BI. Para obter máis información, consulte [Power BI: recomendacións para grandes conxuntos de datos](/power-bi/admin/service-premium-what-is#large-datasets). 

### <a name="work-with-a-subset-of-data"></a>Traballar cun subconxunto de datos

Considere traballar cun subconxunto dos seus datos. Por exemplo, pode crear [segmentos](segments.md) en vez de exportar todos os rexistros de clientes a Power BI.

## <a name="troubleshooting"></a>Resolución de problemas

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a>O contorno de Customer Insights non aparece en Power BI

Ambientes que teñen máis dun [relación](relationships.md) definido entre dúas entidades idénticas en Customer Insights non estará dispoñible no Power BI conector.

Pode identificar e eliminar as relacións duplicadas.

1. Ir a **Datos** > **Relacións** sobre o medio ambiente no que estás de menos Power BI.
2. Identificar relacións duplicadas:
   - Comprobe se hai máis dunha relación definida entre as mesmas dúas entidades.
   - Comprobe se hai unha relación creada entre dúas entidades que están incluídas no proceso de unificación. Hai unha relación implícita definida entre todas as entidades incluídas no proceso de unificación.
3. Elimine as relacións duplicadas identificadas.

Despois de eliminar as relacións duplicadas, intente configurar o conector de Power BI de novo. O ambiente debería estar dispoñible agora.

### <a name="errors-on-date-fields-when-loading-entities-in-power-bi-desktop"></a>Erros nos campos de data ao cargar entidades en Power BI Desktop

Ao cargar entidades que conteñen campos cun formato de data como MM/DD/AAAA, pode atopar erros debido a que os formatos de configuración rexional non coinciden. Este desaxuste ocorre cando o teu Power BI Desktop o ficheiro está definido noutra configuración rexional que o inglés (Estados Unidos), porque os campos de data en Customer Insights gárdanse en formato estadounidense.

O ficheiro de Power BI Desktop ten unha única configuración rexional que se aplica ao recuperar datos. Para que estes campos de data se interpreten correctamente, estableza a configuración rexional do ficheiro .BPI en Inglés (Estados Unidos). [Obteña información sobre como cambiar a configuración rexional dun ficheiro de Power BI Desktop](/power-bi/fundamentals/supported-languages-countries-regions#choose-the-language-or-locale-of-power-bi-desktop).

[!INCLUDE [footer-include](includes/footer-banner.md)]