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
# <a name="connector-for-power-bi-preview"></a><span data-ttu-id="f9426-103">Conector de Power BI (vista previa)</span><span class="sxs-lookup"><span data-stu-id="f9426-103">Connector for Power BI (preview)</span></span>

<span data-ttu-id="f9426-104">Cree visualizacións para os seus datos con Power BI Desktop.</span><span class="sxs-lookup"><span data-stu-id="f9426-104">Create visualizations for your data with the Power BI Desktop.</span></span> <span data-ttu-id="f9426-105">Xere información adicional e cree informes cos seus datos de clientes unificados.</span><span class="sxs-lookup"><span data-stu-id="f9426-105">Generate additional insights and build reports with your unified customer data.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f9426-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="f9426-106">Prerequisites</span></span>

- <span data-ttu-id="f9426-107">Ten perfís de clientes unificados.</span><span class="sxs-lookup"><span data-stu-id="f9426-107">You have unified customer profiles.</span></span>
- <span data-ttu-id="f9426-108">A última versión de [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) está instalada no seu computador.</span><span class="sxs-lookup"><span data-stu-id="f9426-108">The latest version of [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) is installed on your computer.</span></span> <span data-ttu-id="f9426-109">[Obtén máis información acerca de Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).</span><span class="sxs-lookup"><span data-stu-id="f9426-109">[Learn more about Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).</span></span>

## <a name="configure-the-connector-for-power-bi"></a><span data-ttu-id="f9426-110">Configurar o conector de Power BI</span><span class="sxs-lookup"><span data-stu-id="f9426-110">Configure the connector for Power BI</span></span>

1. <span data-ttu-id="f9426-111">En Power BI Desktop, seleccione **Ficheiro** > **Obter datos**.</span><span class="sxs-lookup"><span data-stu-id="f9426-111">In Power BI Desktop, select **File** > **Get Data**.</span></span>

1. <span data-ttu-id="f9426-112">Seleccione **Ver máis** e busque **Dynamics 365 Customer Insights**</span><span class="sxs-lookup"><span data-stu-id="f9426-112">Select **See more** and search for **Dynamics 365 Customer Insights**</span></span>

1. <span data-ttu-id="f9426-113">Seleccione o resultado e **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="f9426-113">Select the result and select **Connect**.</span></span>

1. <span data-ttu-id="f9426-114">**Inicie sesión** coa mesma conta organizativa que usa para Customer Insights e seleccione **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="f9426-114">**Sign in** with the same organizational account you use for Customer Insights and select **Connect**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="f9426-115">A conta que indique neste paso úsase para buscar datos de Customer Insights e non ten por que ser a mesma na que iniciou sesión en Power BI.</span><span class="sxs-lookup"><span data-stu-id="f9426-115">The account you indicate in this step is used to fetch data from Customer Insights and doesn't need to be the same you are signed in to Power BI.</span></span> <span data-ttu-id="f9426-116">Para restablecer a conta que se usa para a obtención de datos, abra Power BI e vaia a **Ficheiro** > **Opcións** > **Configuración** > **Configuración de orixe de datos**.</span><span class="sxs-lookup"><span data-stu-id="f9426-116">To reset the account that is used for data fetching, open Power BI and go to **File** > **Options** > **Settings** > **Data source settings**.</span></span> <span data-ttu-id="f9426-117">Na lista de orixes de datos, seleccione **Inicio de sesión en Dynamics 365 Customer Insights** e seleccione **Borrar permisos**.</span><span class="sxs-lookup"><span data-stu-id="f9426-117">In the list of data sources, select **Dynamics 365 Customer Insights Login** and select **Clear permissions**.</span></span>  

1. <span data-ttu-id="f9426-118">Na caixa de diálogo **Navegador**.</span><span class="sxs-lookup"><span data-stu-id="f9426-118">In the **Navigator** dialog box.</span></span> <span data-ttu-id="f9426-119">ve a lista de todos os ambientes aos que ten acceso.</span><span class="sxs-lookup"><span data-stu-id="f9426-119">you see the list of all environments you have access to.</span></span> <span data-ttu-id="f9426-120">Amplíe un contorno e abra calquera das carpetas (entidades, medidas, segmentos, enriquecementos).</span><span class="sxs-lookup"><span data-stu-id="f9426-120">Expand an environment and open any of the folders (entities, measures, segments, enrichments).</span></span> <span data-ttu-id="f9426-121">Por exemplo, abra o cartafol **Entidades** para ver todas as entidades que pode importar.</span><span class="sxs-lookup"><span data-stu-id="f9426-121">For example, open the **Entities** folder, to see all entities you can import.</span></span>

   <span data-ttu-id="f9426-122">![Power BI Connector Navigator](media/power-bi-navigator.png "Power BI Connector Navigator")</span><span class="sxs-lookup"><span data-stu-id="f9426-122">![Power BI Connector Navigator](media/power-bi-navigator.png "Power BI Connector Navigator")</span></span>

1. <span data-ttu-id="f9426-123">Seleccione as caixas de verificación xunto ás entidades que hai que incluír e **Cargar**.</span><span class="sxs-lookup"><span data-stu-id="f9426-123">Select the check boxes next to the entities to include and **Load**.</span></span> <span data-ttu-id="f9426-124">Pode seleccionar varias entidades de varios ambientes.</span><span class="sxs-lookup"><span data-stu-id="f9426-124">You can select multiple entities from multiple environments.</span></span>

1. <span data-ttu-id="f9426-125">Verá unha caixa de diálogo de carga mentres se cargan as súas entidades.</span><span class="sxs-lookup"><span data-stu-id="f9426-125">You'll see a loading dialog box while your entities are loaded.</span></span> <span data-ttu-id="f9426-126">Unha vez cargadas todas as entidades seleccionadas, pode empregar as capacidades de Power BI para visualizar os datos.</span><span class="sxs-lookup"><span data-stu-id="f9426-126">Once all of your selected entities have loaded, you can use the capabilities of Power BI to visualize the data.</span></span>

## <a name="large-data-sets"></a><span data-ttu-id="f9426-127">Conxuntos de datos grandes</span><span class="sxs-lookup"><span data-stu-id="f9426-127">Large data sets</span></span>

<span data-ttu-id="f9426-128">O conector Customer Insights para Power BI está deseñado para funcionar con conxuntos de datos que conteñen ata 1 millón de perfís de clientes.</span><span class="sxs-lookup"><span data-stu-id="f9426-128">The Customer Insights connector for Power BI is designed to work for data sets that contain up to 1 million customer profiles.</span></span> <span data-ttu-id="f9426-129">A importación de conxuntos de datos máis grandes pode funcionar, pero leva moito tempo.</span><span class="sxs-lookup"><span data-stu-id="f9426-129">Importing larger data sets may work, but it takes a long time.</span></span> <span data-ttu-id="f9426-130">Ademais, o proceso podería ter un tempo de espera debido ás limitacións de Power BI.</span><span class="sxs-lookup"><span data-stu-id="f9426-130">Additionally, the process could run into a time-out because of Power BI limitations.</span></span> <span data-ttu-id="f9426-131">Para obter máis información, consulte [Power BI: recomendacións para grandes conxuntos de datos](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets).</span><span class="sxs-lookup"><span data-stu-id="f9426-131">For more information, see [Power BI: Recommendations for large data sets](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets).</span></span> 

### <a name="work-with-a-subset-of-data"></a><span data-ttu-id="f9426-132">Traballar cun subconxunto de datos</span><span class="sxs-lookup"><span data-stu-id="f9426-132">Work with a subset of data</span></span>

<span data-ttu-id="f9426-133">Considere traballar cun subconxunto dos seus datos.</span><span class="sxs-lookup"><span data-stu-id="f9426-133">Consider working with a subset of your data.</span></span> <span data-ttu-id="f9426-134">Por exemplo, pode crear [segmentos](segments.md) en vez de exportar todos os rexistros de clientes a Power BI.</span><span class="sxs-lookup"><span data-stu-id="f9426-134">For example, you can create [segments](segments.md) instead of exporting all customer records to Power BI.</span></span>
