---
title: Conectarse a entidades do lago xestionado de Common Data Service
description: Importar datos dun lago de datos xestionado de Common Data Service.
ms.date: 09/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.reviewer: adkuppa
ms.openlocfilehash: 029857e2bbb5f6357a5c01138ceaad78887b7518
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643396"
---
# <a name="connect-to-data-in-a-common-data-service-managed-data-lake"></a><span data-ttu-id="369d7-103">Conectar cos datos dun lago de datos xestionado de Common Data Service</span><span class="sxs-lookup"><span data-stu-id="369d7-103">Connect to data in a Common Data Service managed data lake</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="369d7-104">Este artigo ofrece información sobre como os clientes existentes de Dynamics 365 poden conectarse rapidamente ás súas entidades analíticas no lago xestionado de Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="369d7-104">This article provides information on how existing Dynamics 365 customers can quickly connect to their analytical entities in the Common Data Service managed lake.</span></span> <span data-ttu-id="369d7-105">Debe ser administrador na organización de Common Data Service para continuar e ver a lista de entidades dispoñibles no lago xestionado.</span><span class="sxs-lookup"><span data-stu-id="369d7-105">You must be an admin on the Common Data Service organization to proceed and see the list of entities available in the managed lake.</span></span>

## <a name="important-considerations"></a><span data-ttu-id="369d7-106">Consideracións importantes</span><span class="sxs-lookup"><span data-stu-id="369d7-106">Important considerations</span></span>

<span data-ttu-id="369d7-107">Os datos almacenados nos servizos en liña como Azure Data Lake Storage poden almacenarse nunha localización diferente a onde se procesaron ou almacenaron os datos en Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="369d7-107">Data stored in online services, such as Azure Data Lake Storage, may be stored in a different location than where data is processed or stored in Dynamics 365 Customer Insights.</span></span><span data-ttu-id="369d7-108"> Ao importar ou conectarse a datos almacenados en servizos en liña, acepta que os datos poden ser transferidos a e almacenados con Dynamics 365 Customer Insights. [Obteña máis información no Centro de confianza de Microsoft.](https://www.microsoft.com/trust-center)</span><span class="sxs-lookup"><span data-stu-id="369d7-108"> By importing or connecting to data stored in online services, you agree that data can be transferred to and stored with Dynamics 365 Customer Insights. [Learn more at the Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span></span>

## <a name="connect-to-a-common-data-service-managed-lake"></a><span data-ttu-id="369d7-109">Conectarse a un lago xestionado por Common Data Service</span><span class="sxs-lookup"><span data-stu-id="369d7-109">Connect to a Common Data Service managed lake</span></span>

1. <span data-ttu-id="369d7-110">Na información do público, vaia a **Datos** > **Orixes de datos**.</span><span class="sxs-lookup"><span data-stu-id="369d7-110">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="369d7-111">Seleccione **Engadir orixe de datos**.</span><span class="sxs-lookup"><span data-stu-id="369d7-111">Select **Add data source**.</span></span>

3. <span data-ttu-id="369d7-112">Seleccione **Conectar a Common Data Service** e seleccione **Seguinte**.</span><span class="sxs-lookup"><span data-stu-id="369d7-112">Select **Connect to Common Data Service** and select **Next**.</span></span>

4. <span data-ttu-id="369d7-113">Escriba un **Nome** para a orixe de datos e seleccione **Seguinte**.</span><span class="sxs-lookup"><span data-stu-id="369d7-113">Enter a **Name** for the data source and select **Next**.</span></span>

5. <span data-ttu-id="369d7-114">Proporcione o **Enderezo do servidor** da súa organización de Common Data Service e seleccione **Iniciar sesión**.</span><span class="sxs-lookup"><span data-stu-id="369d7-114">Provide the **Server address** for your Common Data Service organization, and select **Sign in**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="369d7-115">![Caixa de diálogo para inserir o enderezo do servidor de Common Data Service](media/enter-CDS-org-details.png)</span><span class="sxs-lookup"><span data-stu-id="369d7-115">![Dialog box to enter Common Data Service server address](media/enter-CDS-org-details.png)</span></span>

6. <span data-ttu-id="369d7-116">Seleccione as entidades que desexa inxerir na lista dispoñible.</span><span class="sxs-lookup"><span data-stu-id="369d7-116">Select the entities you want to ingest from the available list.</span></span>    

   > [!NOTE]
   > <span data-ttu-id="369d7-117">Se algunhas entidades xa están seleccionadas, poderían ser empregadas por outras aplicacións de Dynamics 365 (como Dynamics 365 Sales Insights ou Customer Service Insights).</span><span class="sxs-lookup"><span data-stu-id="369d7-117">If some entities are already selected, they might be used by other Dynamics 365 applications (such as Dynamics 365 Sales Insights or Customer Service Insights).</span></span> <span data-ttu-id="369d7-118">Non se pode cambiar a selección.</span><span class="sxs-lookup"><span data-stu-id="369d7-118">You can't change the selection.</span></span> <span data-ttu-id="369d7-119">Estas entidades estarán dispoñibles unha vez que se cree a orixe de datos.</span><span class="sxs-lookup"><span data-stu-id="369d7-119">These entities will be available once the data source is created.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="369d7-120">![Caixa de diálogo que mostra unha lista de entidades na organización Common Data Service](media/select-analytical-entities.png)</span><span class="sxs-lookup"><span data-stu-id="369d7-120">![Dialog box showing a list of entities in the Common Data Service org](media/select-analytical-entities.png)</span></span>

7. <span data-ttu-id="369d7-121">Garde a selección para comezar a sincronizar as entidades seleccionadas no lago xestionado por Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="369d7-121">Save your selection to start syncing the selected entities to the Common Data Service managed lake.</span></span> <span data-ttu-id="369d7-122">Atopará a conexión acabada de engadir na páxina **Orixes de datos**.</span><span class="sxs-lookup"><span data-stu-id="369d7-122">You'll find the newly added connection on the **Data sources** page.</span></span> <span data-ttu-id="369d7-123">Porase en cola para actualizar e mostrar o reconto de entidades como 0 ata que se sincronicen todas as entidades.</span><span class="sxs-lookup"><span data-stu-id="369d7-123">It will be queued for refresh and show the entities count as 0 until all the entities are synced.</span></span>

<span data-ttu-id="369d7-124">Só unha orixe de datos dun ambiente pode usar ao mesmo tempo o mesmo lago xestionado de Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="369d7-124">Only one data source of an environment can simultaneously use the same Common Data Service managed lake.</span></span>

## <a name="edit-a-common-data-service-managed-lake-data-source"></a><span data-ttu-id="369d7-125">Editar unha orixe de datos de lago xestionado por Common Data Service</span><span class="sxs-lookup"><span data-stu-id="369d7-125">Edit a Common Data Service managed lake data source</span></span>

<span data-ttu-id="369d7-126">Só edita a selección da entidades despois de crear a orixe de datos.</span><span class="sxs-lookup"><span data-stu-id="369d7-126">You only edit the entity selection after creating the data source.</span></span> <span data-ttu-id="369d7-127">Por exemplo, se se engadiron entidades adicionais a Common Data Service e tamén quere importalos.</span><span class="sxs-lookup"><span data-stu-id="369d7-127">For example, if additional entities were added to Common Data Service and you want to import them too.</span></span>    
<span data-ttu-id="369d7-128">Para conectar cun Common Data Service diferente, [cree unha orixe de datos nova](#connect-to-a-common-data-service-managed-lake).</span><span class="sxs-lookup"><span data-stu-id="369d7-128">To connect to a different Common Data Service, [create a new data source](#connect-to-a-common-data-service-managed-lake).</span></span>

1. <span data-ttu-id="369d7-129">Na información do público, vaia a **Datos** > **Orixes de datos**.</span><span class="sxs-lookup"><span data-stu-id="369d7-129">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="369d7-130">A carón da orixe de datos que desexa actualizar, seleccione os tres puntos.</span><span class="sxs-lookup"><span data-stu-id="369d7-130">Next to the data source you'd like to update, select the ellipsis.</span></span>

3. <span data-ttu-id="369d7-131">Seleccione a opción **Editar** da lista.</span><span class="sxs-lookup"><span data-stu-id="369d7-131">Select the **Edit** option from the list.</span></span>

4. <span data-ttu-id="369d7-132">Seleccione entidades adicionais da lista de entidades dispoñibles e seleccione **Gardar**.</span><span class="sxs-lookup"><span data-stu-id="369d7-132">Select additional entities from the available list of entities and select **Save**.</span></span>
