---
title: Solicitudes de dereitos do titular dos datos (DSR) baixo RXPD | Microsoft Docs
description: Responda ás solicitudes dos titulares dos datos da capacidade de información do público de Dynamics 365 Customer Insights.
ms.date: 05/14/2020
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: f276a73feca52023391ad92fbc84359921b85328
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405724"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a><span data-ttu-id="85232-103">Solicitudes de dereitos do titular dos datos (DSR) baixo RXPD</span><span class="sxs-lookup"><span data-stu-id="85232-103">Data Subject Rights (DSR) requests under GDPR</span></span>

## <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a><span data-ttu-id="85232-104">Responder ás solicitudes de eliminación dos titulares dos datos segunco o RXPD para a capacidade de información do público de Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="85232-104">Responding to GDPR data subject delete requests for Dynamics 365 Customer Insights audience insights capability</span></span>

<span data-ttu-id="85232-105">O "dereito á eliminación" de datos persoais dos datos de clientes dunha organización é unha protección clave no Regulamento xeral de protección de datos (RXPD).</span><span class="sxs-lookup"><span data-stu-id="85232-105">The “right to erasure” by the removal of personal data from an organization’s customer data is a key protection in the General Data Protection Regulation (GDPR).</span></span> <span data-ttu-id="85232-106">A eliminación de datos persoais inclúe a eliminación de todos os datos persoais e os rexistros xerados polo sistema, excepto a información do rexistro de auditoría.</span><span class="sxs-lookup"><span data-stu-id="85232-106">Removing personal data includes removing all personal data and system-generated logs, except audit log information.</span></span>

### <a name="manage-data-subject-delete-requests"></a><span data-ttu-id="85232-107">Xestionar as solicitudes de eliminación do titular dos datos</span><span class="sxs-lookup"><span data-stu-id="85232-107">Manage data subject delete requests</span></span>

<span data-ttu-id="85232-108">A información do público ofrece as seguintes experiencias internas para eliminar datos persoais dun cliente específico ou usuario:</span><span class="sxs-lookup"><span data-stu-id="85232-108">Audience insights offers the following in-product experiences to delete personal data for a specific customer or user:</span></span>

- <span data-ttu-id="85232-109">**Xestionar solicitudes de eliminación de datos de clientes**: os datos do cliente de Customer Insights son inxeridos de fontes de datos orixinais externas a Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="85232-109">**Manage delete requests for customer data**: Customer data in Customer Insights is ingested from original data sources external to Customer Insights.</span></span> <span data-ttu-id="85232-110">Todas as solicitudes de eliminación de RXPD deben realizarse na orixe de datos orixinal.</span><span class="sxs-lookup"><span data-stu-id="85232-110">All GDPR delete requests must be performed in the original data source.</span></span>
- <span data-ttu-id="85232-111">**Xestionar solicitudes de eliminación de datos de usuario de Customer Insights**: Os datos dos usuarios son creados por Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="85232-111">**Manage delete requests for Customer Insights user data**: Data for users is created by Customer Insights.</span></span> <span data-ttu-id="85232-112">Todas as solicitudes de eliminación de RXPD deben realizarse en Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="85232-112">All GDPR delete requests must be performed in Customer Insights.</span></span>

#### <a name="manage-delete-requests-for-customer-data"></a><span data-ttu-id="85232-113">Xestionar solicitudes de eliminación de datos de clientes</span><span class="sxs-lookup"><span data-stu-id="85232-113">Manage delete requests for customer data</span></span>

<span data-ttu-id="85232-114">Un administrador de Customer Insights pode seguir estes pasos para eliminar os datos de clientes que se eliminaron na orixe de datos:</span><span class="sxs-lookup"><span data-stu-id="85232-114">A Customer Insights admin can follow these steps to remove customer data that was deleted in the data source:</span></span>

1. <span data-ttu-id="85232-115">Inicie sesión en Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="85232-115">Sign in to Dynamics 365 Customer Insights.</span></span>
2. <span data-ttu-id="85232-116">Na información do público, vaia a **Datos** > **Orixes de datos**</span><span class="sxs-lookup"><span data-stu-id="85232-116">In audience insights, go to **Data** > **Data sources**</span></span>
3. <span data-ttu-id="85232-117">Para cada orixe de datos da lista que contén datos de clientes eliminados:</span><span class="sxs-lookup"><span data-stu-id="85232-117">For each data source in the list that contains deleted customer data:</span></span>
   1. <span data-ttu-id="85232-118">Seleccione (...) e, a seguir, seleccione **Actualizar**.</span><span class="sxs-lookup"><span data-stu-id="85232-118">Select (...) and then select **Refresh**.</span></span>
   2. <span data-ttu-id="85232-119">Consulte o estado da orixe de datos en **Estado**.</span><span class="sxs-lookup"><span data-stu-id="85232-119">Check the status of the data source under **Status**.</span></span> <span data-ttu-id="85232-120">A aparición dunha marca de verificación significa que a actualización tivo éxito.</span><span class="sxs-lookup"><span data-stu-id="85232-120">A check mark means the refresh was successful.</span></span> <span data-ttu-id="85232-121">Un triángulo de aviso significa que algo saíu mal.</span><span class="sxs-lookup"><span data-stu-id="85232-121">A warning triangle means something went wrong.</span></span> <span data-ttu-id="85232-122">Se aparece un triángulo de aviso, póñase en contacto con D365CI@microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="85232-122">If a warning triangle is displayed, contact D365CI@microsoft.com.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="85232-123">![Manipulación de solicitudes de eliminación de RXPD para datos de clientes](media/gdpr-data-sources.png "Manipulación de solicitudes de eliminación de RXPD para datos de clientes")</span><span class="sxs-lookup"><span data-stu-id="85232-123">![Handling GDPR delete requests for customer data](media/gdpr-data-sources.png "Handling GDPR delete requests for customer data")</span></span>

#### <a name="manage-delete-requests-for-user-data"></a><span data-ttu-id="85232-124">Xestionar solicitudes de eliminación de datos de usuario</span><span class="sxs-lookup"><span data-stu-id="85232-124">Manage delete requests for user data</span></span>

<span data-ttu-id="85232-125">Un administrador de Customer Insights pode seguir estes pasos para eliminar os datos de usuarios de Customer Insights:</span><span class="sxs-lookup"><span data-stu-id="85232-125">A Customer Insights admin can follow these steps to delete Customer Insights user data:</span></span>

1. <span data-ttu-id="85232-126">Inicie sesión en Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="85232-126">Sign in to Dynamics 365 Customer Insights.</span></span>
2. <span data-ttu-id="85232-127">Na información do público, vaia a **Administrar** > **Permisos**.</span><span class="sxs-lookup"><span data-stu-id="85232-127">In audience insights, go to **Admin** > **Permissions**.</span></span>
3. <span data-ttu-id="85232-128">Marque a caixa de verificación do usuario que desexe eliminar.</span><span class="sxs-lookup"><span data-stu-id="85232-128">Select the check box for the user you want to delete.</span></span>
4. <span data-ttu-id="85232-129">Seleccione **Quitar**.</span><span class="sxs-lookup"><span data-stu-id="85232-129">Select **Remove**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="85232-130">![Xestionar solicitudes de eliminación segundo o RXPD para datos de usuario](media/gdpr-permissions.png "Xestionar solicitudes de eliminación segundo o RXPD para datos de usuario")</span><span class="sxs-lookup"><span data-stu-id="85232-130">![Handling GDPR delete requests foruser data](media/gdpr-permissions.png "Handling GDPR delete requests for user data")</span></span>

## <a name="responding-to-gdpr-data-subject-export-requests"></a><span data-ttu-id="85232-131">Responder a solicitudes de exportación de titulares dos datos segundo o RXPD</span><span class="sxs-lookup"><span data-stu-id="85232-131">Responding to GDPR data subject export requests</span></span>

<span data-ttu-id="85232-132">Como parte do noso compromiso de asociarnos con vostede na aplicación do Regulamento xeral de protección de datos (RXPD), elaboramos documentación para axudarlle a prepararse.</span><span class="sxs-lookup"><span data-stu-id="85232-132">As part of our commitment to partner with you on your journey to the General Data Protection Regulation (GDPR), we’ve developed documentation to help you prepare.</span></span> <span data-ttu-id="85232-133">Esta documentación describe os pasos que pode seguir hoxe para apoiar o cumprimento do RXPD cando se empregan as estatísticas do público.</span><span class="sxs-lookup"><span data-stu-id="85232-133">This documentation describes steps you can take today to support GDPR compliance when using audience insights.</span></span>

### <a name="manage-export-and-view-requests"></a><span data-ttu-id="85232-134">Xestionar solicitudes de exportación e visualización</span><span class="sxs-lookup"><span data-stu-id="85232-134">Manage export and view requests</span></span>

<span data-ttu-id="85232-135">O dereito de portabilidade de datos permite a un titular solicitar unha copia dos seus datos persoais nun formato electrónico (definido como un "formato estruturado, utilizado comunmente, lexible por máquinas e interoperable") que pode ser transmitido a outro controlador de datos.</span><span class="sxs-lookup"><span data-stu-id="85232-135">The right of data portability allows data subjects to request a copy of their personal data in an electronic format (a “structured, commonly used, machine readable, and interoperable format”) that can be transmitted to another data controller.</span></span>

#### <a name="export-customer-data-tenant-admin"></a><span data-ttu-id="85232-136">Exportar datos de clientes (administrador de arrendatarios)</span><span class="sxs-lookup"><span data-stu-id="85232-136">Export customer data (tenant admin)</span></span>

<span data-ttu-id="85232-137">Un administrador de arrendatarios pode seguir estes pasos para exportar datos:</span><span class="sxs-lookup"><span data-stu-id="85232-137">A tenant administrator can follow these steps to export data:</span></span>

1. <span data-ttu-id="85232-138">Envíe un correo electrónico a D365CI@microsoft.com especificando o enderezo de correo electrónico do cliente na solicitude.</span><span class="sxs-lookup"><span data-stu-id="85232-138">Send an email to D365CI@microsoft.com specifying the customer’s email address in the request.</span></span> <span data-ttu-id="85232-139">O equipo de Customer Insights enviará un correo electrónico ao enderezo de correo electrónico do administrador do arrendatario rexistrado e pedirá confirmación para exportar datos.</span><span class="sxs-lookup"><span data-stu-id="85232-139">The Customer Insights team will send an email to the registered tenant admin email address, asking for confirmation to export data.</span></span>
2. <span data-ttu-id="85232-140">Recoñeza a confirmación para exportar os datos do cliente solicitado.</span><span class="sxs-lookup"><span data-stu-id="85232-140">Acknowledge the confirmation to export the data for the requested customer.</span></span>
3. <span data-ttu-id="85232-141">Reciba os datos exportados a través do enderezo de correo electrónico do administrador do arrendatario.</span><span class="sxs-lookup"><span data-stu-id="85232-141">Receive the exported data through the tenant admin email address.</span></span>

#### <a name="export-user-data-tenant-admin"></a><span data-ttu-id="85232-142">Exportar datos de usuario (administrador de arrendatarios)</span><span class="sxs-lookup"><span data-stu-id="85232-142">Export user data (tenant admin)</span></span>

1. <span data-ttu-id="85232-143">Envíe un correo electrónico a D365CI@microsoft.com especificando o enderezo de correo electrónico do usuario na solicitude.</span><span class="sxs-lookup"><span data-stu-id="85232-143">Send an email to D365CI@microsoft.com specifying the user’s email address in the request.</span></span> <span data-ttu-id="85232-144">O equipo de Customer Insights enviará un correo electrónico ao enderezo de correo electrónico do administrador do arrendatario rexistrado e pedirá confirmación para exportar datos.</span><span class="sxs-lookup"><span data-stu-id="85232-144">The Customer Insights team will send an email to the registered tenant admin email address, asking for confirmation to export data.</span></span>
2. <span data-ttu-id="85232-145">Recoñeza a confirmación para exportar os datos do usuario solicitado.</span><span class="sxs-lookup"><span data-stu-id="85232-145">Acknowledge the confirmation to export the data for the requested user.</span></span>
3. <span data-ttu-id="85232-146">Reciba os datos exportados a través do enderezo de correo electrónico do administrador do arrendatario.</span><span class="sxs-lookup"><span data-stu-id="85232-146">Receive the exported data through the tenant admin email address.</span></span>
