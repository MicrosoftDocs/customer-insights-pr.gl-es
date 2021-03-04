---
title: Instalar e configurar o complemento de cartón de cliente
description: Instale e configure o complemento do cartón do cliente para Dynamics 365 Customer Insights.
ms.date: 01/20/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: a6d5b49380ed129cf147698a16f5f3f597bf7fbc
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268042"
---
# <a name="customer-card-add-in-preview"></a><span data-ttu-id="cc4d2-103">Complemento do cartón do cliente (vista previa)</span><span class="sxs-lookup"><span data-stu-id="cc4d2-103">Customer Card Add-in (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="cc4d2-104">Obteña unha vista de 360 graos dos seus clientes directamente nas aplicacións de Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="cc4d2-104">Get a 360-degree view of your customers directly in Dynamics 365 apps.</span></span> <span data-ttu-id="cc4d2-105">Permite ver datos demográficos, información e cronoloxías de actividades co complemento da tarxeta de cliente.</span><span class="sxs-lookup"><span data-stu-id="cc4d2-105">View demographics, insights, and activity timelines with the Customer Card Add-in.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="cc4d2-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="cc4d2-106">Prerequisites</span></span>

- <span data-ttu-id="cc4d2-107">Aplicación de Dynamics 365 (como Plataforma común de vendas ou Plataforma común de servizo de atención ao cliente), versión 9.0 e posterior con Interface unificada activada.</span><span class="sxs-lookup"><span data-stu-id="cc4d2-107">Dynamics 365 app (such as Sales Hub or Customer Service Hub), version 9.0 and later with Unified Interface enabled.</span></span>
- <span data-ttu-id="cc4d2-108">Perfís de clientes [inxeridos desde a aplicación de Dynamics 365 usando Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="cc4d2-108">Customer profiles [ingested from the Dynamics 365 app using Common Data Service](connect-power-query.md).</span></span>
- <span data-ttu-id="cc4d2-109">Os usuarios do complemento de tarxeta de cliente deben ser [engadidos como usuarios](permissions.md) en información do público.</span><span class="sxs-lookup"><span data-stu-id="cc4d2-109">Users of the Customer Card Add-in need to be [added as users](permissions.md) in audience insights.</span></span>
- <span data-ttu-id="cc4d2-110">[Capacidades de busca e filtraxe configuradas](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="cc4d2-110">[Configured search and filter capabilities](search-filter-index.md).</span></span>
- <span data-ttu-id="cc4d2-111">Control demográfico: os campos demográficos (como a idade ou o sexo) están dispoñibles no perfil de cliente unificado.</span><span class="sxs-lookup"><span data-stu-id="cc4d2-111">Demographic control: Demographic fields(such as age or gender) are available in the unified customer profile.</span></span>
- <span data-ttu-id="cc4d2-112">Control do enriquecemento: require [enriquecementos](enrichment-hub.md) activos aplicados aos perfís de clientes.</span><span class="sxs-lookup"><span data-stu-id="cc4d2-112">Enrichment control: Requires active [enrichments](enrichment-hub.md) applied to customer profiles.</span></span>
- <span data-ttu-id="cc4d2-113">Control intelixente: require datos xerados mediante Azure Machine Learning ([predicións](predictions.md) ou [modelos personalizados](custom-models.md))</span><span class="sxs-lookup"><span data-stu-id="cc4d2-113">Intelligence control: Requires data generated using Azure Machine Learning ([Predictions](predictions.md) or [Custom Models](custom-models.md))</span></span>
- <span data-ttu-id="cc4d2-114">Control de medidas: require [medidas configuradas](measures.md).</span><span class="sxs-lookup"><span data-stu-id="cc4d2-114">Measure control: Requires [configured measures](measures.md).</span></span>
- <span data-ttu-id="cc4d2-115">Control da liña de tempo: require [actividades configuradas](activities.md).</span><span class="sxs-lookup"><span data-stu-id="cc4d2-115">Timeline control: Requires [configured activities](activities.md).</span></span>

## <a name="install-the-customer-card-add-in"></a><span data-ttu-id="cc4d2-116">Instalar o complemento do cartón do cliente</span><span class="sxs-lookup"><span data-stu-id="cc4d2-116">Install the Customer Card Add-in</span></span>

<span data-ttu-id="cc4d2-117">O complemento de tarxeta de cliente é unha solución para aplicacións de interacción cos clientes en Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="cc4d2-117">The Customer Card Add-in is a solution for customer engagement apps in Dynamics 365.</span></span> <span data-ttu-id="cc4d2-118">Para instalar a solución, vaia a AppSource e busque **Tarxeta de cliente de Dynamics**.</span><span class="sxs-lookup"><span data-stu-id="cc4d2-118">To install the solution, go to AppSource and search for **Dynamics Customer Card**.</span></span> <span data-ttu-id="cc4d2-119">Seleccione o [Complemento da tarxeta de cliente en AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) e seleccione **Obtelo agora**.</span><span class="sxs-lookup"><span data-stu-id="cc4d2-119">Select the [Customer Card Add-in on AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) and select **Get It Now**.</span></span>

<span data-ttu-id="cc4d2-120">Pode que necesite iniciar sesión coas súas credenciais de administrador da aplicación de Dynamics 365 para instalar a solución.</span><span class="sxs-lookup"><span data-stu-id="cc4d2-120">You may need to sign in with your admin credentials for the Dynamics 365 app to install the solution.</span></span>

<span data-ttu-id="cc4d2-121">Pode que a solución tarde un tempo en instalarse no seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="cc4d2-121">It can take some time for the solution to be installed to your environment.</span></span>

## <a name="configure-the-customer-card-add-in"></a><span data-ttu-id="cc4d2-122">Configurar o complemento de tarxeta de cliente</span><span class="sxs-lookup"><span data-stu-id="cc4d2-122">Configure the Customer Card Add-in</span></span>

1. <span data-ttu-id="cc4d2-123">Como administrador, vaia á sección **Configuración** en Dynamics 365 e seleccione **Solucións**.</span><span class="sxs-lookup"><span data-stu-id="cc4d2-123">As an admin, go to the **Settings** section in Dynamics 365 and select **Solutions**.</span></span>

1. <span data-ttu-id="cc4d2-124">Seleccione a ligazón **Nome de pantalla** para a solución **Complemento de tarxeta de cliente de Dynamics 365 Customer Insights (vista previa)**.</span><span class="sxs-lookup"><span data-stu-id="cc4d2-124">Select the **Display Name** link for the **Dynamics 365 Customer Insights Customer Card Add-in (Preview)** solution.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="cc4d2-125">![Seleccionar o nome para mostrar](media/select-display-name.png "Seleccionar o nome para mostrar")</span><span class="sxs-lookup"><span data-stu-id="cc4d2-125">![Select display name](media/select-display-name.png "Select display name")</span></span>

1. <span data-ttu-id="cc4d2-126">Seleccione **Iniciar sesión** e insira as credenciais da conta de administrador que use para configurar Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="cc4d2-126">Select **Sign in** and enter the credentials for the admin account you use to configure Customer Insights.</span></span>

   > [!NOTE]
   > <span data-ttu-id="cc4d2-127">Asegúrese de que o bloqueador de ventás emerxentes do navegador non bloquee a ventá de autenticación cando seleccione o botón **Iniciar sesión**.</span><span class="sxs-lookup"><span data-stu-id="cc4d2-127">Check that the browser pop-up blocker does not block the authentication window when you select the **Sign in** button.</span></span>

1. <span data-ttu-id="cc4d2-128">Seleccione o ambiente do que desexa obter datos.</span><span class="sxs-lookup"><span data-stu-id="cc4d2-128">Select the environment you want to fetch data from.</span></span>

1. <span data-ttu-id="cc4d2-129">Defina cal é a asignación de campos para os rexistros na aplicación de Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="cc4d2-129">Define which the field mapping to records in the Dynamics 365 app.</span></span>
   - <span data-ttu-id="cc4d2-130">Para asignar cun contacto, seleccione o campo da entidade de cliente que coincida co ID da súa entidade de contacto.</span><span class="sxs-lookup"><span data-stu-id="cc4d2-130">To map with a contact, select the field in the Customer entity that matches the ID of your contact entity.</span></span>
   - <span data-ttu-id="cc4d2-131">Para asignar cunha conta, seleccione o campo da entidade de cliente que coincida co ID da súa entidade de conta.</span><span class="sxs-lookup"><span data-stu-id="cc4d2-131">To map with an account, select the field in the Customer entity that matches the ID of your account entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="cc4d2-132">![Campo de ID de contacto](media/contact-id-field.png "Campo de ID de contacto")</span><span class="sxs-lookup"><span data-stu-id="cc4d2-132">![Contact ID field](media/contact-id-field.png "Contact ID field")</span></span>

1. <span data-ttu-id="cc4d2-133">Seleccione **Gardar configuración** para gardar os axustes.</span><span class="sxs-lookup"><span data-stu-id="cc4d2-133">Select **Save configuration** to save the settings.</span></span>

1. <span data-ttu-id="cc4d2-134">A continuación, ten que asignar roles de seguridade en Dynamics 365 para que os usuarios poidan personalizar e ver a tarxeta de cliente.</span><span class="sxs-lookup"><span data-stu-id="cc4d2-134">Next, you need to assign security roles in Dynamics 365 so users can customize and see the customer card.</span></span> <span data-ttu-id="cc4d2-135">En Dynamics 365, vaia a **Configuración** > **Seguranza** > **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="cc4d2-135">In Dynamics 365, go to **Settings** > **Security** > **Users**.</span></span> <span data-ttu-id="cc4d2-136">Seleccione os usuarios para editar os roles de usuario e seleccione **Xestionar papeis**.</span><span class="sxs-lookup"><span data-stu-id="cc4d2-136">Select the users to edit user roles and select **Manage roles**.</span></span>

1. <span data-ttu-id="cc4d2-137">Asigne o rol de **Personalizador de tarxetas de Customer Insights** aos usuarios que personalizarán o contido mostrado na tarxeta para toda a organización.</span><span class="sxs-lookup"><span data-stu-id="cc4d2-137">Assign the **Customer Insights Card Customizer** role to users who will customize the content shown on the card for the whole organization.</span></span>

## <a name="add-customer-card-controls-to-forms"></a><span data-ttu-id="cc4d2-138">Engadir controis de cartón de cliente aos formularios</span><span class="sxs-lookup"><span data-stu-id="cc4d2-138">Add Customer Card controls to forms</span></span>
  
1. <span data-ttu-id="cc4d2-139">Para engadir os controis da tarxeta de cliente ao formulario de contacto, diríxase a **Configuración** > **Personalizacións** en Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="cc4d2-139">To add the Customer Card controls to your Contact form, go to the **Settings** > **Customizations** in Dynamics 365.</span></span>

1. <span data-ttu-id="cc4d2-140">Seleccione **Personalizar o sistema**.</span><span class="sxs-lookup"><span data-stu-id="cc4d2-140">Select **Customize the System**.</span></span>

1. <span data-ttu-id="cc4d2-141">Navegue ata a entidade de **contacto**, expanda o seu menú e logo seleccione **Formularios**.</span><span class="sxs-lookup"><span data-stu-id="cc4d2-141">Browse to the **Contact** entity, expand it and select **Forms**.</span></span>

1. <span data-ttu-id="cc4d2-142">Seleccione o formulario de contacto ao que desexa engadir os controis da tarxeta de cliente.</span><span class="sxs-lookup"><span data-stu-id="cc4d2-142">Select the contact form to which you want to add the Customer Card controls.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="cc4d2-143">![Seleccionar formulario de contacto](media/contact-active-forms.png "Seleccionar formulario de contacto")</span><span class="sxs-lookup"><span data-stu-id="cc4d2-143">![Select Contact form](media/contact-active-forms.png "Select Contact form")</span></span>

1. <span data-ttu-id="cc4d2-144">Para engadir un control no editor de formularios, arrastre calquera campo do **Explorador de campos** ata onde desexe colocar o control.</span><span class="sxs-lookup"><span data-stu-id="cc4d2-144">To add a control, in the form editor, drag any field from the **Field Explorer** to where you want the control to appear.</span></span>

1. <span data-ttu-id="cc4d2-145">Seleccione o campo no formulario que acaba de engadir e seleccione **Cambiar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="cc4d2-145">Select the field on the form that you just added, and select **Change Properties**.</span></span>

1. <span data-ttu-id="cc4d2-146">Vaia ao separador **Controis** e seleccione **Engadir control**.</span><span class="sxs-lookup"><span data-stu-id="cc4d2-146">Go to the **Controls** tab and select **Add Control**.</span></span> <span data-ttu-id="cc4d2-147">Escolla un dos controis personalizados dispoñibles e seleccione **Engadir**.</span><span class="sxs-lookup"><span data-stu-id="cc4d2-147">Choose one of the available custom controls and select **Add**.</span></span>

1. <span data-ttu-id="cc4d2-148">Na caixa de diálogo **Propiedades do campo**, desmarque a caixa de verificación **Mostrar etiqueta no formulario**.</span><span class="sxs-lookup"><span data-stu-id="cc4d2-148">In the **Field Properties** dialog, clear the **Display label on the form** check box.</span></span>

1. <span data-ttu-id="cc4d2-149">Seleccione a opción **Web** para o control.</span><span class="sxs-lookup"><span data-stu-id="cc4d2-149">Select the **Web** option for the control.</span></span> <span data-ttu-id="cc4d2-150">No control de enriquecemento, seleccione o tipo de enriquecemento que desexa amosar configurando o campo **enrichmentType**.</span><span class="sxs-lookup"><span data-stu-id="cc4d2-150">For the Enrichment control, select which enrichment type you want to display by configuring the **enrichmentType** field.</span></span> <span data-ttu-id="cc4d2-151">Engada un control de enriquecemento separado para cada tipo de enriquecemento.</span><span class="sxs-lookup"><span data-stu-id="cc4d2-151">Add a separate enrichment control for each enrichment type.</span></span>

1. <span data-ttu-id="cc4d2-152">Seleccione **Gardar** e **Publicar** para publicar o formulario de contacto actualizado.</span><span class="sxs-lookup"><span data-stu-id="cc4d2-152">Select **Save** and **Publish** to publish the updated contact form.</span></span>

1. <span data-ttu-id="cc4d2-153">Vaia ao formulario de contacto publicado.</span><span class="sxs-lookup"><span data-stu-id="cc4d2-153">Go to the published contact form.</span></span> <span data-ttu-id="cc4d2-154">Verá o control que acaba de engadir.</span><span class="sxs-lookup"><span data-stu-id="cc4d2-154">You'll see the newly added control.</span></span> <span data-ttu-id="cc4d2-155">É posible que teña que iniciar sesión a primeira vez que o use.</span><span class="sxs-lookup"><span data-stu-id="cc4d2-155">You might need to sign in the first time you use it.</span></span>

1. <span data-ttu-id="cc4d2-156">Para personalizar o que quere mostrar no control personalizado, seleccione o botón de edición na esquina superior dereita.</span><span class="sxs-lookup"><span data-stu-id="cc4d2-156">To customize what you want to show on the custom control, select the edit button in the upper-right corner.</span></span>

## <a name="upgrade-customer-card-add-in"></a><span data-ttu-id="cc4d2-157">Actualizar complemento do cartón do cliente</span><span class="sxs-lookup"><span data-stu-id="cc4d2-157">Upgrade Customer Card Add-in</span></span>
<span data-ttu-id="cc4d2-158">O complemento de tarxeta de cliente non se actualiza automaticamente.</span><span class="sxs-lookup"><span data-stu-id="cc4d2-158">The Customer Card Add-in doesn't upgrade automatically.</span></span> <span data-ttu-id="cc4d2-159">Para actualizar á última versión, siga este procedemento na aplicación Dynamics 365 que ten instalado o complemento.</span><span class="sxs-lookup"><span data-stu-id="cc4d2-159">To upgrade to the latest version, follow this procedure in the Dynamics 365 app that has the Add-in installed.</span></span>

1. <span data-ttu-id="cc4d2-160">Na aplicación Dynamics 365, vai a **Configuración** > **Personalización** e seleccione **Solucións**.</span><span class="sxs-lookup"><span data-stu-id="cc4d2-160">In the Dynamics 365 app, go to **Settings** > **Customization** and select **Solutions**.</span></span>

1. <span data-ttu-id="cc4d2-161">Na táboa de complementos, busque **CustomerInsightsCustomerCard** e seleccione a fila.</span><span class="sxs-lookup"><span data-stu-id="cc4d2-161">In the table of add-ins look for **CustomerInsightsCustomerCard** and select the row.</span></span>

1. <span data-ttu-id="cc4d2-162">Seleccione **Aplicar a actualización da solución** na barra de acción.</span><span class="sxs-lookup"><span data-stu-id="cc4d2-162">Select the **Apply Solution Upgrade** in the action bar.</span></span>

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Actualice a solución na área de personalización das aplicacións de Dynamics 365":::

1. <span data-ttu-id="cc4d2-164">Despois de iniciar o proceso de actualización, verá un indicador de carga ata que finalice a actualización.</span><span class="sxs-lookup"><span data-stu-id="cc4d2-164">After starting the upgrade process, you'll see a loading indicator until the upgrade completes.</span></span> <span data-ttu-id="cc4d2-165">Se non hai ningunha versión máis recente, a actualización amosará unha mensaxe de erro.</span><span class="sxs-lookup"><span data-stu-id="cc4d2-165">If there's no newer version, the upgrade will show an error message.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]