---
title: Conectarse a entidades do lago xestionado de Common Data Service
description: Importar datos dun lago de datos xestionado de Common Data Service.
ms.date: 09/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: mhart
ms.openlocfilehash: b1cfab40c1edb32f4a7f359e1195cfb1e879a0d5
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596957"
---
# <a name="connect-to-data-in-a-common-data-service-managed-data-lake"></a><span data-ttu-id="29084-103">Conectar cos datos dun lago de datos xestionado de Common Data Service</span><span class="sxs-lookup"><span data-stu-id="29084-103">Connect to data in a Common Data Service managed data lake</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="29084-104">Este artigo ofrece información sobre como os clientes existentes de Dynamics 365 poden conectarse rapidamente ás súas entidades analíticas no lago xestionado de Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="29084-104">This article provides information on how existing Dynamics 365 customers can quickly connect to their analytical entities in the Common Data Service managed lake.</span></span> <span data-ttu-id="29084-105">Debe ser administrador na organización de Common Data Service para continuar e ver a lista de entidades dispoñibles no lago xestionado.</span><span class="sxs-lookup"><span data-stu-id="29084-105">You must be an admin on the Common Data Service organization to proceed and see the list of entities available in the managed lake.</span></span>

## <a name="important-considerations"></a><span data-ttu-id="29084-106">Consideracións importantes</span><span class="sxs-lookup"><span data-stu-id="29084-106">Important considerations</span></span>

<span data-ttu-id="29084-107">Os datos almacenados nos servizos en liña como Azure Data Lake Storage poden almacenarse nunha localización diferente a onde se procesaron ou almacenaron os datos en Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="29084-107">Data stored in online services, such as Azure Data Lake Storage, may be stored in a different location than where data is processed or stored in Dynamics 365 Customer Insights.</span></span><span data-ttu-id="29084-108"> Ao importar ou conectarse a datos almacenados en servizos en liña, acepta que os datos poden ser transferidos a e almacenados con Dynamics 365 Customer Insights. [Obteña máis información no Centro de confianza de Microsoft.](https://www.microsoft.com/trust-center)</span><span class="sxs-lookup"><span data-stu-id="29084-108"> By importing or connecting to data stored in online services, you agree that data can be transferred to and stored with Dynamics 365 Customer Insights. [Learn more at the Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span></span>

## <a name="connect-to-a-common-data-service-managed-lake"></a><span data-ttu-id="29084-109">Conectarse a un lago xestionado por Common Data Service</span><span class="sxs-lookup"><span data-stu-id="29084-109">Connect to a Common Data Service managed lake</span></span>

1. <span data-ttu-id="29084-110">Na información do público, vaia a **Datos** > **Orixes de datos**.</span><span class="sxs-lookup"><span data-stu-id="29084-110">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="29084-111">Seleccione **Engadir orixe de datos**.</span><span class="sxs-lookup"><span data-stu-id="29084-111">Select **Add data source**.</span></span>

3. <span data-ttu-id="29084-112">Seleccione **Conectar a Common Data Service** e seleccione **Seguinte**.</span><span class="sxs-lookup"><span data-stu-id="29084-112">Select **Connect to Common Data Service** and select **Next**.</span></span>

4. <span data-ttu-id="29084-113">Escriba un **Nome** para a orixe de datos e seleccione **Seguinte**.</span><span class="sxs-lookup"><span data-stu-id="29084-113">Enter a **Name** for the data source and select **Next**.</span></span> <span data-ttu-id="29084-114">Dea nome ás instrucións:</span><span class="sxs-lookup"><span data-stu-id="29084-114">Name guidelines:</span></span> 
   - <span data-ttu-id="29084-115">Comece por unha letra.</span><span class="sxs-lookup"><span data-stu-id="29084-115">Start with a letter.</span></span>
   - <span data-ttu-id="29084-116">Use só letras e números.</span><span class="sxs-lookup"><span data-stu-id="29084-116">Use letters and numbers only.</span></span> <span data-ttu-id="29084-117">Non se permiten caracteres especiais nin espazos.</span><span class="sxs-lookup"><span data-stu-id="29084-117">Special characters and spaces are not allowed.</span></span>
   - <span data-ttu-id="29084-118">Empregue entre 3 e 64 caracteres.</span><span class="sxs-lookup"><span data-stu-id="29084-118">Use between 3 and 64 characters.</span></span>

5. <span data-ttu-id="29084-119">Proporcione o **Enderezo do servidor** da súa organización de Common Data Service e seleccione **Iniciar sesión**.</span><span class="sxs-lookup"><span data-stu-id="29084-119">Provide the **Server address** for your Common Data Service organization, and select **Sign in**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="29084-120">![Caixa de diálogo para inserir o enderezo do servidor de Common Data Service](media/enter-CDS-org-details.png)</span><span class="sxs-lookup"><span data-stu-id="29084-120">![Dialog box to enter Common Data Service server address](media/enter-CDS-org-details.png)</span></span>

6. <span data-ttu-id="29084-121">Seleccione as entidades que desexa inxerir na lista dispoñible.</span><span class="sxs-lookup"><span data-stu-id="29084-121">Select the entities you want to ingest from the available list.</span></span>    

   > [!NOTE]
   > <span data-ttu-id="29084-122">Se algunhas entidades xa están seleccionadas, poderían ser empregadas por outras aplicacións de Dynamics 365 (como Dynamics 365 Sales Insights ou Customer Service Insights).</span><span class="sxs-lookup"><span data-stu-id="29084-122">If some entities are already selected, they might be used by other Dynamics 365 applications (such as Dynamics 365 Sales Insights or Customer Service Insights).</span></span> <span data-ttu-id="29084-123">Non se pode cambiar a selección.</span><span class="sxs-lookup"><span data-stu-id="29084-123">You can't change the selection.</span></span> <span data-ttu-id="29084-124">Estas entidades estarán dispoñibles unha vez que se cree a orixe de datos.</span><span class="sxs-lookup"><span data-stu-id="29084-124">These entities will be available once the data source is created.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="29084-125">![Caixa de diálogo que mostra unha lista de entidades na organización Common Data Service](media/select-analytical-entities.png)</span><span class="sxs-lookup"><span data-stu-id="29084-125">![Dialog box showing a list of entities in the Common Data Service org](media/select-analytical-entities.png)</span></span>

7. <span data-ttu-id="29084-126">Garde a selección para comezar a sincronizar as entidades seleccionadas no lago xestionado por Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="29084-126">Save your selection to start syncing the selected entities to the Common Data Service managed lake.</span></span> <span data-ttu-id="29084-127">Atopará a conexión acabada de engadir na páxina **Orixes de datos**.</span><span class="sxs-lookup"><span data-stu-id="29084-127">You'll find the newly added connection on the **Data sources** page.</span></span> <span data-ttu-id="29084-128">Porase en cola para actualizar e mostrar o reconto de entidades como 0 ata que se sincronicen todas as entidades.</span><span class="sxs-lookup"><span data-stu-id="29084-128">It will be queued for refresh and show the entities count as 0 until all the entities are synced.</span></span>

<span data-ttu-id="29084-129">Só unha orixe de datos dun ambiente pode usar ao mesmo tempo o mesmo lago xestionado de Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="29084-129">Only one data source of an environment can simultaneously use the same Common Data Service managed lake.</span></span>

## <a name="edit-a-common-data-service-managed-lake-data-source"></a><span data-ttu-id="29084-130">Editar unha orixe de datos de lago xestionado por Common Data Service</span><span class="sxs-lookup"><span data-stu-id="29084-130">Edit a Common Data Service managed lake data source</span></span>

<span data-ttu-id="29084-131">Só edita a selección da entidades despois de crear a orixe de datos.</span><span class="sxs-lookup"><span data-stu-id="29084-131">You only edit the entity selection after creating the data source.</span></span> <span data-ttu-id="29084-132">Por exemplo, se se engadiron entidades adicionais a Common Data Service e tamén quere importalos.</span><span class="sxs-lookup"><span data-stu-id="29084-132">For example, if additional entities were added to Common Data Service and you want to import them too.</span></span>    
<span data-ttu-id="29084-133">Para conectar cun Common Data Service diferente, [cree unha orixe de datos nova](#connect-to-a-common-data-service-managed-lake).</span><span class="sxs-lookup"><span data-stu-id="29084-133">To connect to a different Common Data Service, [create a new data source](#connect-to-a-common-data-service-managed-lake).</span></span>

1. <span data-ttu-id="29084-134">Na información do público, vaia a **Datos** > **Orixes de datos**.</span><span class="sxs-lookup"><span data-stu-id="29084-134">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="29084-135">A carón da orixe de datos que desexa actualizar, seleccione os tres puntos.</span><span class="sxs-lookup"><span data-stu-id="29084-135">Next to the data source you'd like to update, select the ellipsis.</span></span>

3. <span data-ttu-id="29084-136">Seleccione a opción **Editar** da lista.</span><span class="sxs-lookup"><span data-stu-id="29084-136">Select the **Edit** option from the list.</span></span>

4. <span data-ttu-id="29084-137">Seleccione entidades adicionais da lista de entidades dispoñibles e seleccione **Gardar**.</span><span class="sxs-lookup"><span data-stu-id="29084-137">Select additional entities from the available list of entities and select **Save**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]