---
title: Conector de Power BI
description: Obteña información acerca de como usar o conector de Dynamics 365 Customer Insights en Power BI.
ms.date: 09/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: e43e2f9dbc84ebfbf2154990a752740f973296cb
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596037"
---
# <a name="connector-for-power-bi-preview"></a><span data-ttu-id="ca2d8-103">Conector de Power BI (vista previa)</span><span class="sxs-lookup"><span data-stu-id="ca2d8-103">Connector for Power BI (preview)</span></span>

<span data-ttu-id="ca2d8-104">Cree visualizacións para os seus datos con Power BI Desktop.</span><span class="sxs-lookup"><span data-stu-id="ca2d8-104">Create visualizations for your data with the Power BI Desktop.</span></span> <span data-ttu-id="ca2d8-105">Xere información adicional e cree informes cos seus datos de clientes unificados.</span><span class="sxs-lookup"><span data-stu-id="ca2d8-105">Generate additional insights and build reports with your unified customer data.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ca2d8-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="ca2d8-106">Prerequisites</span></span>

- <span data-ttu-id="ca2d8-107">Ten perfís de clientes unificados.</span><span class="sxs-lookup"><span data-stu-id="ca2d8-107">You have unified customer profiles.</span></span>
- <span data-ttu-id="ca2d8-108">A última versión de [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) está instalado no seu computador.</span><span class="sxs-lookup"><span data-stu-id="ca2d8-108">The latest version of [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) is installed on your computer.</span></span> <span data-ttu-id="ca2d8-109">[Obtén máis información acerca de Power BI Desktop](/power-bi/desktop-what-is-desktop).</span><span class="sxs-lookup"><span data-stu-id="ca2d8-109">[Learn more about Power BI Desktop](/power-bi/desktop-what-is-desktop).</span></span>

## <a name="configure-the-connector-for-power-bi"></a><span data-ttu-id="ca2d8-110">Configurar o conector de Power BI</span><span class="sxs-lookup"><span data-stu-id="ca2d8-110">Configure the connector for Power BI</span></span>

1. <span data-ttu-id="ca2d8-111">En Power BI Desktop, seleccione **Ficheiro** > **Obter datos**.</span><span class="sxs-lookup"><span data-stu-id="ca2d8-111">In Power BI Desktop, select **File** > **Get Data**.</span></span>

1. <span data-ttu-id="ca2d8-112">Seleccione **Ver máis** e busque **Dynamics 365 Customer Insights**</span><span class="sxs-lookup"><span data-stu-id="ca2d8-112">Select **See more** and search for **Dynamics 365 Customer Insights**</span></span>

1. <span data-ttu-id="ca2d8-113">Seleccione **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="ca2d8-113">Select **Connect**.</span></span>

1. <span data-ttu-id="ca2d8-114">**Inicie sesión** coa mesma conta organizativa que usa para Customer Insights e seleccione **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="ca2d8-114">**Sign in** with the same organizational account you use for Customer Insights and select **Connect**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="ca2d8-115">A conta que indique neste paso úsase para buscar datos de Customer Insights e non ten por que ser a mesma na que iniciou sesión en Power BI.</span><span class="sxs-lookup"><span data-stu-id="ca2d8-115">The account you indicate in this step is used to fetch data from Customer Insights and doesn't need to be the same you are signed in to Power BI.</span></span> <span data-ttu-id="ca2d8-116">Para restablecer a conta que se usa para a obtención de datos, abra Power BI e vaia a **Ficheiro** > **Opcións** > **Configuración** > **Configuración de orixe de datos**.</span><span class="sxs-lookup"><span data-stu-id="ca2d8-116">To reset the account that is used for data fetching, open Power BI and go to **File** > **Options** > **Settings** > **Data source settings**.</span></span> <span data-ttu-id="ca2d8-117">Na lista de orixes de datos, seleccione **Inicio de sesión en Dynamics 365 Customer Insights** e seleccione **Borrar permisos**.</span><span class="sxs-lookup"><span data-stu-id="ca2d8-117">In the list of data sources, select **Dynamics 365 Customer Insights Login** and select **Clear permissions**.</span></span>  

1. <span data-ttu-id="ca2d8-118">Na caixa de diálogo **Navegador**.</span><span class="sxs-lookup"><span data-stu-id="ca2d8-118">In the **Navigator** dialog box.</span></span> <span data-ttu-id="ca2d8-119">ve a lista de todos os ambientes aos que ten acceso.</span><span class="sxs-lookup"><span data-stu-id="ca2d8-119">you see the list of all environments you have access to.</span></span> <span data-ttu-id="ca2d8-120">Amplíe un contorno e abra calquera das carpetas (entidades, medidas, segmentos, enriquecementos).</span><span class="sxs-lookup"><span data-stu-id="ca2d8-120">Expand an environment and open any of the folders (entities, measures, segments, enrichments).</span></span> <span data-ttu-id="ca2d8-121">Por exemplo, abra o cartafol **Entidades** para ver todas as entidades que pode importar.</span><span class="sxs-lookup"><span data-stu-id="ca2d8-121">For example, open the **Entities** folder, to see all entities you can import.</span></span>

   <span data-ttu-id="ca2d8-122">![Power BI Connector Navigator](media/power-bi-navigator.png "Power BI Connector Navigator")</span><span class="sxs-lookup"><span data-stu-id="ca2d8-122">![Power BI Connector Navigator](media/power-bi-navigator.png "Power BI Connector Navigator")</span></span>

1. <span data-ttu-id="ca2d8-123">Seleccione as caixas de verificación xunto ás entidades que hai que incluír e **Cargar**.</span><span class="sxs-lookup"><span data-stu-id="ca2d8-123">Select the check boxes next to the entities to include and **Load**.</span></span> <span data-ttu-id="ca2d8-124">Pode seleccionar varias entidades de varios ambientes.</span><span class="sxs-lookup"><span data-stu-id="ca2d8-124">You can select multiple entities from multiple environments.</span></span>

1. <span data-ttu-id="ca2d8-125">Verá unha caixa de diálogo de carga mentres se cargan as súas entidades.</span><span class="sxs-lookup"><span data-stu-id="ca2d8-125">You'll see a loading dialog box while your entities are loaded.</span></span> <span data-ttu-id="ca2d8-126">Unha vez cargadas todas as entidades seleccionadas, pode empregar as capacidades de Power BI para visualizar os datos.</span><span class="sxs-lookup"><span data-stu-id="ca2d8-126">Once all of your selected entities have loaded, you can use the capabilities of Power BI to visualize the data.</span></span>

## <a name="large-data-sets"></a><span data-ttu-id="ca2d8-127">Conxuntos de datos grandes</span><span class="sxs-lookup"><span data-stu-id="ca2d8-127">Large data sets</span></span>

<span data-ttu-id="ca2d8-128">O conector Customer Insights para Power BI está deseñado para funcionar con conxuntos de datos que conteñen ata 1 millón de perfís de clientes.</span><span class="sxs-lookup"><span data-stu-id="ca2d8-128">The Customer Insights connector for Power BI is designed to work for data sets that contain up to 1 million customer profiles.</span></span> <span data-ttu-id="ca2d8-129">A importación de conxuntos de datos máis grandes pode funcionar, pero leva moito tempo.</span><span class="sxs-lookup"><span data-stu-id="ca2d8-129">Importing larger data sets may work, but it takes a long time.</span></span> <span data-ttu-id="ca2d8-130">Ademais, o proceso podería ter un tempo de espera debido ás limitacións de Power BI.</span><span class="sxs-lookup"><span data-stu-id="ca2d8-130">Additionally, the process could run into a time-out because of Power BI limitations.</span></span> <span data-ttu-id="ca2d8-131">Para obter máis información, consulte [Power BI: recomendacións para grandes conxuntos de datos](/power-bi/admin/service-premium-what-is#large-datasets).</span><span class="sxs-lookup"><span data-stu-id="ca2d8-131">For more information, see [Power BI: Recommendations for large data sets](/power-bi/admin/service-premium-what-is#large-datasets).</span></span> 

### <a name="work-with-a-subset-of-data"></a><span data-ttu-id="ca2d8-132">Traballar cun subconxunto de datos</span><span class="sxs-lookup"><span data-stu-id="ca2d8-132">Work with a subset of data</span></span>

<span data-ttu-id="ca2d8-133">Considere traballar cun subconxunto dos seus datos.</span><span class="sxs-lookup"><span data-stu-id="ca2d8-133">Consider working with a subset of your data.</span></span> <span data-ttu-id="ca2d8-134">Por exemplo, pode crear [segmentos](segments.md) en vez de exportar todos os rexistros de clientes a Power BI.</span><span class="sxs-lookup"><span data-stu-id="ca2d8-134">For example, you can create [segments](segments.md) instead of exporting all customer records to Power BI.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="ca2d8-135">Resolución de problemas</span><span class="sxs-lookup"><span data-stu-id="ca2d8-135">Troubleshooting</span></span>

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a><span data-ttu-id="ca2d8-136">O contorno de Customer Insights non aparece en Power BI</span><span class="sxs-lookup"><span data-stu-id="ca2d8-136">Customer Insights environment doesn't show in Power BI</span></span>

<span data-ttu-id="ca2d8-137">Contornos que teñen máis dunha [relación](relationships.md) definida entre dúas entidades idénticas nas estatísticas de audiencia non estarán dispoñibles no conector de Power BI.</span><span class="sxs-lookup"><span data-stu-id="ca2d8-137">Environments that have more than one [relationship](relationships.md) defined between two identical entities in audience insights will not be available in the Power BI connector.</span></span>

<span data-ttu-id="ca2d8-138">Pode identificar e eliminar as relacións duplicadas.</span><span class="sxs-lookup"><span data-stu-id="ca2d8-138">You can identify and remove the duplicated relationships.</span></span>

1. <span data-ttu-id="ca2d8-139">Na información do público, vaia a **Datos** > **Relacións** no ambiente que lle falta en Power BI.</span><span class="sxs-lookup"><span data-stu-id="ca2d8-139">In audience insights, go to **Data** > **Relationships** on the environment you're missing in Power BI.</span></span>
2. <span data-ttu-id="ca2d8-140">Identificar relacións duplicadas:</span><span class="sxs-lookup"><span data-stu-id="ca2d8-140">Identify duplicated relationships:</span></span>
   - <span data-ttu-id="ca2d8-141">Comprobe se hai máis dunha relación definida entre as mesmas dúas entidades.</span><span class="sxs-lookup"><span data-stu-id="ca2d8-141">Check if there is more than one relationship defined between the same two entities.</span></span>
   - <span data-ttu-id="ca2d8-142">Comprobe se hai unha relación creada entre dúas entidades que están incluídas no proceso de unificación.</span><span class="sxs-lookup"><span data-stu-id="ca2d8-142">Check if there is a relationship created between two entities that are both included in the unification process.</span></span> <span data-ttu-id="ca2d8-143">Hai unha relación implícita definida entre todas as entidades incluídas no proceso de unificación.</span><span class="sxs-lookup"><span data-stu-id="ca2d8-143">There is an implicit relationship defined between all entities included in the unification process.</span></span>
3. <span data-ttu-id="ca2d8-144">Elimine as relacións duplicadas identificadas.</span><span class="sxs-lookup"><span data-stu-id="ca2d8-144">Remove any duplicate relationships identified.</span></span>

<span data-ttu-id="ca2d8-145">Despois de eliminar as relacións duplicadas, intente configurar o conector de Power BI de novo.</span><span class="sxs-lookup"><span data-stu-id="ca2d8-145">After removal of the duplicated relationships, try to configure the Power BI connector again.</span></span> <span data-ttu-id="ca2d8-146">O ambiente debería estar dispoñible agora.</span><span class="sxs-lookup"><span data-stu-id="ca2d8-146">The environment should be available now.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]