---
title: Tarefas compartidas para escenarios de predición
description: Aprenda a xestionar, solucionar problemas e perfeccionar as predicións.
ms.date: 05/17/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: dccb8dcca8f65f64973e46fed9d83034d58282e2
ms.sourcegitcommit: bcc47d15d4f0eacf008e4dbc09baac7f062b3ca8
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 06/29/2021
ms.locfileid: "6315876"
---
# <a name="manage-predictions"></a><span data-ttu-id="85de3-103">Xestionar predicións</span><span class="sxs-lookup"><span data-stu-id="85de3-103">Manage predictions</span></span>

<span data-ttu-id="85de3-104">Este artigo trata algunhas tarefas que comparten a maioría dos escenarios de predición.</span><span class="sxs-lookup"><span data-stu-id="85de3-104">This article discusses some tasks that most prediction scenarios share.</span></span>

## <a name="troubleshoot-a-failed-prediction"></a><span data-ttu-id="85de3-105">Resolver problemas de predición fallida</span><span class="sxs-lookup"><span data-stu-id="85de3-105">Troubleshoot a failed prediction</span></span>

1. <span data-ttu-id="85de3-106">Vaia a **Intelixencia** > **Predicións** e seleccione o separador **As miñas predicións**.</span><span class="sxs-lookup"><span data-stu-id="85de3-106">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="85de3-107">Seleccione os tres puntos verticais xunto á predición para a que desexa ver os rexistros de erros.</span><span class="sxs-lookup"><span data-stu-id="85de3-107">Select the vertical ellipses next to the prediction you want to view error logs for.</span></span>

1. <span data-ttu-id="85de3-108">Seleccione **Rexistros**.</span><span class="sxs-lookup"><span data-stu-id="85de3-108">Select **Logs**.</span></span>

1. <span data-ttu-id="85de3-109">Revise todos os erros.</span><span class="sxs-lookup"><span data-stu-id="85de3-109">Review all the errors.</span></span> <span data-ttu-id="85de3-110">Existen varios tipos de erros que poden ocorrer e describen que problema causou o erro.</span><span class="sxs-lookup"><span data-stu-id="85de3-110">There are several types of errors that can occur, and they describe what condition caused the error.</span></span> <span data-ttu-id="85de3-111">Por exemplo, un erro que consiste en que non hai datos suficientes para predicir con precisión adoita resolverse cargando datos adicionais en Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="85de3-111">For example, an error that there's not enough data to accurately predict is typically resolved by loading additional data into Customer Insights.</span></span>

## <a name="input-data-usability-report"></a><span data-ttu-id="85de3-112">Informe de usabilidade dos datos de entrada</span><span class="sxs-lookup"><span data-stu-id="85de3-112">Input data usability report</span></span>

<span data-ttu-id="85de3-113">O informe de usabilidade dos datos de entrada ofrece unha visión consolidada dos erros e advertencias que poden xerar as predicións listas para utilizar.</span><span class="sxs-lookup"><span data-stu-id="85de3-113">The input data usability report provides a consolidated view of the errors and warnings that your out-of-box predictions may be generating.</span></span> <span data-ttu-id="85de3-114">Tamén ofrece recomendacións sobre como mellorar o desempeño do modelo.</span><span class="sxs-lookup"><span data-stu-id="85de3-114">It also gives recommendations how to improve the model performance.</span></span>

<span data-ttu-id="85de3-115">O informe estará dispoñible despois de que un modelo finalice o seu proceso de adestramento.</span><span class="sxs-lookup"><span data-stu-id="85de3-115">The report is available after a model has completed its training process.</span></span> <span data-ttu-id="85de3-116">Créase para cada modelo por separado, independentemente de se se completou correctamente ou non.</span><span class="sxs-lookup"><span data-stu-id="85de3-116">It's created for each model separately, regardless if it completed successfully or not.</span></span>

### <a name="view-the-input-data-usability-report"></a><span data-ttu-id="85de3-117">Ver informe de usabilidade dos datos de entrada</span><span class="sxs-lookup"><span data-stu-id="85de3-117">View the input data usability report</span></span>

<span data-ttu-id="85de3-118">Despois de que un modelo listo para usar complete o paso de adestramento, vexa o informe:</span><span class="sxs-lookup"><span data-stu-id="85de3-118">After an out-of-box model has completed its training step, view the report:</span></span>
- <span data-ttu-id="85de3-119">Seleccione os puntos suspensivos xunto ao nome do modelo e escolla **Informe de usabilidade dos datos de entrada**.</span><span class="sxs-lookup"><span data-stu-id="85de3-119">Select the ellipses next to the model name and choose **Input data usability report**.</span></span>
- <span data-ttu-id="85de3-120">Seleccione o estado dun modelo seleccionando **Ver informe de usabilidade dos datos de entrada** no panel lateral.</span><span class="sxs-lookup"><span data-stu-id="85de3-120">Select the status of a model select **See Input data usability report** in the side pane.</span></span>
- <span data-ttu-id="85de3-121">Seleccione un dos modelos da lista e seleccione **Informe de usabilidade dos datos de entrada** na barra de comandos.</span><span class="sxs-lookup"><span data-stu-id="85de3-121">Selecting one of the models in the list and select **Input data usability report** in the command bar.</span></span>
- <span data-ttu-id="85de3-122">Abra a páxina de resultados do modelo e seleccione **Informe de usabilidade dos datos de entrada** na barra de comandos.</span><span class="sxs-lookup"><span data-stu-id="85de3-122">Open the model results page and select **Input data usability report** in the command bar.</span></span>

### <a name="information-in-the-input-data-usability-report"></a><span data-ttu-id="85de3-123">Información no informe de usabilidade dos datos de entrada</span><span class="sxs-lookup"><span data-stu-id="85de3-123">Information in the input data usability report</span></span>

<span data-ttu-id="85de3-124">As seguintes columnas do informe conteñen información útil para mellorar os datos do modelo.</span><span class="sxs-lookup"><span data-stu-id="85de3-124">The following columns in the report contain helpful information to improve the data for the model.</span></span>

:::image type="content" source="media/input-data-usability-report.png" alt-text="Exemplo dun informe de usabilidade dos datos de entrada que mostra unha táboa con erros, avisos e recomendacións.":::

- <span data-ttu-id="85de3-126">Nome: nome descritivo do erro, aviso ou recomendación.</span><span class="sxs-lookup"><span data-stu-id="85de3-126">Name: Descriptive name of the error, warning, or recommendation.</span></span>
- <span data-ttu-id="85de3-127">Paso: puntuación, adestramento ou fase do modelo aos que fai referencia a información.</span><span class="sxs-lookup"><span data-stu-id="85de3-127">Step: Model phase, train or score, the information refers to.</span></span>
- <span data-ttu-id="85de3-128">Estado: gravidade da información (erro, aviso, recomendación).</span><span class="sxs-lookup"><span data-stu-id="85de3-128">State: Severity of the information (error, warning, recommendation).</span></span>
- <span data-ttu-id="85de3-129">Nome da columna: columna dunha entidade que necesita ser modificada para mellorar o desempeño do modelo.</span><span class="sxs-lookup"><span data-stu-id="85de3-129">Column name: Column in an entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="85de3-130">Nome da entidade: nome da entidade que necesita ser modificada para mellorar o desempeño do modelo.</span><span class="sxs-lookup"><span data-stu-id="85de3-130">Entity name: Name of the entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="85de3-131">Detalles: detalles sobre o erro, aviso ou recomendación.</span><span class="sxs-lookup"><span data-stu-id="85de3-131">Details: Details about the error, warning, or recommendation.</span></span>

## <a name="refresh-a-prediction"></a><span data-ttu-id="85de3-132">Actualizar unha predición</span><span class="sxs-lookup"><span data-stu-id="85de3-132">Refresh a prediction</span></span>

<span data-ttu-id="85de3-133">As predicións actualizaranse automaticamente no mesmo [programa que actualiza os seus datos](system.md#schedule-tab) tal e como se configura nos axustes.</span><span class="sxs-lookup"><span data-stu-id="85de3-133">Predictions will automatically refresh on the same [schedule your data refreshes](system.md#schedule-tab) as configured in settings.</span></span> <span data-ttu-id="85de3-134">Tamén pode actualizalos manualmente.</span><span class="sxs-lookup"><span data-stu-id="85de3-134">You can refresh them manually too.</span></span>

1. <span data-ttu-id="85de3-135">Vaia a **Intelixencia** > **Predicións** e seleccione o separador **As miñas predicións**.</span><span class="sxs-lookup"><span data-stu-id="85de3-135">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="85de3-136">Seleccione os tres puntos verticais xunto á predición que quere actualizar.</span><span class="sxs-lookup"><span data-stu-id="85de3-136">Select the vertical ellipses next to the prediction you want to refresh.</span></span>

1. <span data-ttu-id="85de3-137">Seleccione **Actualizar**.</span><span class="sxs-lookup"><span data-stu-id="85de3-137">Select **Refresh**.</span></span>

## <a name="delete-a-prediction"></a><span data-ttu-id="85de3-138">Eliminar unha predición</span><span class="sxs-lookup"><span data-stu-id="85de3-138">Delete a prediction</span></span>

<span data-ttu-id="85de3-139">Eliminar unha predición tamén elimina a súa entidade de saída.</span><span class="sxs-lookup"><span data-stu-id="85de3-139">Deleting a prediction also removes its output entity.</span></span>

1. <span data-ttu-id="85de3-140">Vaia a **Intelixencia** > **Predicións** e seleccione o separador **As miñas predicións**.</span><span class="sxs-lookup"><span data-stu-id="85de3-140">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="85de3-141">Seleccione os tres puntos verticais xunto á predición que quere eliminar.</span><span class="sxs-lookup"><span data-stu-id="85de3-141">Select the vertical ellipses next to the prediction you want to delete.</span></span>

1. <span data-ttu-id="85de3-142">Seleccione **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="85de3-142">Select **Delete**.</span></span>
