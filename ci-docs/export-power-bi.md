---
title: Conector de Power BI (vista previa)
description: Obteña información acerca de como usar o conector de Dynamics 365 Customer Insights en Power BI.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 656a695b8b3f1ec2b5fbaad69feba7f1f0b73dee
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196668"
---
# <a name="power-bi-connector-preview"></a>Conector de Power BI (vista previa)

Crea visualizacións para os teus datos co Microsoft Power BI Escritorio. Xere información adicional e cree informes cos seus datos de clientes unificados.

## <a name="prerequisites"></a>Requisitos previos

- Perfís de clientes unificados.
- A última versión de [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) está instalado no seu computador. [Obtén máis información acerca de Power BI Desktop](/power-bi/desktop-what-is-desktop).

## <a name="configure-the-connector-for-power-bi"></a>Configurar o conector de Power BI

1. En Power BI Desktop, seleccione **Ficheiro** > **Obter datos**.

1. Seleccione **Ver máis** e busque **Dynamics 365 Customer Insights**

1. Seleccione **Conectar**.

1. **Inicie sesión** coa mesma conta organizativa que usa para Customer Insights e seleccione **Conectar**.
   > [!NOTE]
   > A conta que indique neste paso úsase para buscar datos de Customer Insights e non ten por que ser a mesma na que iniciou sesión en Power BI. Para restablecer a conta que se usa para a obtención de datos, abra Power BI e vaia a **Ficheiro** > **Opcións** > **Configuración** > **Configuración de orixe de datos**. Na lista de orixes de datos, seleccione **Inicio de sesión en Dynamics 365 Customer Insights** e seleccione **Borrar permisos**.  

1. No **Navegador** caixa de diálogo, ver a lista de todos os ambientes aos que tes acceso. Amplíe un contorno e abra calquera das carpetas (entidades, medidas, segmentos, enriquecementos). Por exemplo, abra o cartafol **Entidades** para ver todas as entidades que pode importar.

   :::image type="content" source="media/power-bi-navigator.png" alt-text="Power BI Connector Navigator.":::

1. Seleccione as caixas de verificación xunto ás entidades que hai que incluír e **Cargar**. Pode seleccionar varias entidades de varios ambientes.

   Aparece un cadro de diálogo de carga mentres se cargan as túas entidades. Unha vez que se cargaron todas as entidades seleccionadas, utiliza as capacidades de Power BI para visualizar os datos.

## <a name="large-data-sets"></a>Conxuntos de datos grandes

O conector Customer Insights para Power BI está deseñado para funcionar con conxuntos de datos que conteñen ata 1 millón de perfís de clientes. É posible que a importación de conxuntos de datos máis grandes funcione, pero leva moito tempo e pode que se agote Power BI limitacións. Para obter máis información, consulte [Power BI: recomendacións para grandes conxuntos de datos](/power-bi/admin/service-premium-what-is#large-datasets).

### <a name="work-with-a-subset-of-data"></a>Traballar cun subconxunto de datos

Considere traballar cun subconxunto dos seus datos. Por exemplo, crear [segmentos](segments.md) en lugar de exportar todos os rexistros de clientes a Power BI.

## <a name="troubleshooting"></a>Resolución de problemas

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a>O contorno de Customer Insights non aparece en Power BI

Ambientes que teñen máis dun [relación](relationships.md) definido entre dúas entidades idénticas en Customer Insights non estará dispoñible no Power BI conector.

Identifica e elimina as relacións duplicadas.

1. Ir a **Datos** > **Relacións** sobre o medio ambiente no que estás de menos Power BI.
1. Identificar relacións duplicadas:
   - Comprobe se hai máis dunha relación definida entre as mesmas dúas entidades.
   - Comprobe se hai unha relación creada entre dúas entidades que están incluídas no proceso de unificación. Hai unha relación implícita definida entre todas as entidades incluídas no proceso de unificación.
1. Elimine as relacións duplicadas identificadas.

Despois de eliminar as relacións duplicadas, intente configurar o conector de Power BI de novo.

### <a name="errors-on-date-fields-when-loading-entities-in-power-bi-desktop"></a>Erros nos campos de data ao cargar entidades en Power BI Desktop

Ao cargar entidades que conteñan campos cun formato de data como MM/DD/AAAA, é posible que atopes erros debido a que os formatos locais non coinciden. Este desaxuste ocorre cando o teu Power BI Desktop o ficheiro está definido noutra configuración rexional que o inglés (Estados Unidos), porque os campos de data en Customer Insights gárdanse en formato estadounidense.

O ficheiro de Power BI Desktop ten unha única configuración rexional que se aplica ao recuperar datos. Para corrixir os erros de data, [establecer a configuración rexional do ficheiro .BPI](/power-bi/fundamentals/supported-languages-countries-regions#choose-the-language-or-locale-of-power-bi-desktop) ao inglés (Estados Unidos).

[!INCLUDE [footer-include](includes/footer-banner.md)]
