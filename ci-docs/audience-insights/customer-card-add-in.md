---
title: Suplemento do cartón de cliente das aplicacións de Dynamics 365
description: Mostrar datos de información do público nas aplicacións de Dynamics 365 con este suplemento.
ms.date: 05/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 88492943ddbf9ae30c64d92b261433b74f34f682
ms.sourcegitcommit: d74430270f1b754322287c4f045d7febdae35be2
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 05/18/2021
ms.locfileid: "6059586"
---
# <a name="customer-card-add-in-preview"></a><span data-ttu-id="2943b-103">Complemento do cartón do cliente (vista previa)</span><span class="sxs-lookup"><span data-stu-id="2943b-103">Customer Card Add-in (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="2943b-104">Obteña unha vista de 360 graos dos seus clientes directamente nas aplicacións de Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="2943b-104">Get a 360-degree view of your customers directly in Dynamics 365 apps.</span></span> <span data-ttu-id="2943b-105">Co suplemento do cartón de cliente instalado nunha aplicación de Dynamics 365 compatible, pode escoller mostrar a demografía, a información e as liñas de tempo de actividades.</span><span class="sxs-lookup"><span data-stu-id="2943b-105">With the Customer Card Add-in installed in a supported Dynamics 365 app you can choose to display demographics, insights, and activity timelines.</span></span> <span data-ttu-id="2943b-106">O suplemento recuperará datos de Customer Insights sen afectar aos datos da aplicación de Dynamics 365 conectada.</span><span class="sxs-lookup"><span data-stu-id="2943b-106">The add-in will retrieve data from Customer Insights without affecting the data in the connected Dynamics 365 app.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="2943b-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="2943b-107">Prerequisites</span></span>

- <span data-ttu-id="2943b-108">O suplemento só funciona con aplicacións de Dynamics 365 controladas por modelos, como Sales ou Customer Service, versión 9.0 e posteriores.</span><span class="sxs-lookup"><span data-stu-id="2943b-108">The add-in only works with Dynamics 365 model-driven apps, such as Sales or Customer Service, version 9.0 and later.</span></span>
- <span data-ttu-id="2943b-109">Para que os seus datos de Dynamics 365 se asignen aos perfís de clientes da información do público, deben [inxerirse desde a aplicación de Dynamics 365 mediante o conector de Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="2943b-109">For your Dynamics 365 data to map to the audience insights customer profiles they need to be [ingested from the Dynamics 365 app using the Common Data Service connector](connect-power-query.md).</span></span>
- <span data-ttu-id="2943b-110">Todos os usuarios de Dynamics 365 do suplemento do cartón do cliente deben [engadirse como usuarios](permissions.md) na información do público para ver os datos.</span><span class="sxs-lookup"><span data-stu-id="2943b-110">All Dynamics 365 users of the Customer Card Add-in must be [added as users](permissions.md) in audience insights to see the data.</span></span>
- <span data-ttu-id="2943b-111">Na información do público precísanse [capacidades de busca e filtros configuradas](search-filter-index.md) para que a busca de datos funcione.</span><span class="sxs-lookup"><span data-stu-id="2943b-111">[Configured search and filter capabilities](search-filter-index.md) in audience insights are required for lookup of data to work.</span></span>
- <span data-ttu-id="2943b-112">Cada control do suplemento depende de datos específicos na información do público:</span><span class="sxs-lookup"><span data-stu-id="2943b-112">Each add-in control relies on specific data in audience insights:</span></span>
  - <span data-ttu-id="2943b-113">Control de medidas: require [medidas configuradas](measures.md).</span><span class="sxs-lookup"><span data-stu-id="2943b-113">Measure control: Requires [configured measures](measures.md).</span></span>
  - <span data-ttu-id="2943b-114">Control de intelixencia: require datos xerados mediante [predicións](predictions.md) ou [modelos personalizados](custom-models.md).</span><span class="sxs-lookup"><span data-stu-id="2943b-114">Intelligence control: Requires data generated using [predictions](predictions.md) or [custom models](custom-models.md).</span></span>
  - <span data-ttu-id="2943b-115">Control demográfico: os campos demográficos (como a idade ou o sexo) están dispoñibles no perfil de cliente unificado.</span><span class="sxs-lookup"><span data-stu-id="2943b-115">Demographic control: Demographic fields(such as age or gender) are available in the unified customer profile.</span></span>
  - <span data-ttu-id="2943b-116">Control do enriquecemento: require [enriquecementos](enrichment-hub.md) activos aplicados aos perfís de clientes.</span><span class="sxs-lookup"><span data-stu-id="2943b-116">Enrichment control: Requires active [enrichments](enrichment-hub.md) applied to customer profiles.</span></span>
  - <span data-ttu-id="2943b-117">Control da liña de tempo: require [actividades configuradas](activities.md).</span><span class="sxs-lookup"><span data-stu-id="2943b-117">Timeline control: Requires [configured activities](activities.md).</span></span>

## <a name="install-the-customer-card-add-in"></a><span data-ttu-id="2943b-118">Instalar o complemento do cartón do cliente</span><span class="sxs-lookup"><span data-stu-id="2943b-118">Install the Customer Card Add-in</span></span>

<span data-ttu-id="2943b-119">O complemento de tarxeta de cliente é unha solución para aplicacións de interacción cos clientes en Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="2943b-119">The Customer Card Add-in is a solution for customer engagement apps in Dynamics 365.</span></span> <span data-ttu-id="2943b-120">Para instalar a solución, vaia a AppSource e busque **Tarxeta de cliente de Dynamics**.</span><span class="sxs-lookup"><span data-stu-id="2943b-120">To install the solution, go to AppSource and search for **Dynamics Customer Card**.</span></span> <span data-ttu-id="2943b-121">Seleccione o [Complemento da tarxeta de cliente en AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) e seleccione **Obtelo agora**.</span><span class="sxs-lookup"><span data-stu-id="2943b-121">Select the [Customer Card Add-in on AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) and select **Get It Now**.</span></span>

<span data-ttu-id="2943b-122">Pode que necesite iniciar sesión coas súas credenciais de administrador da aplicación de Dynamics 365 para instalar a solución.</span><span class="sxs-lookup"><span data-stu-id="2943b-122">You may need to sign in with your admin credentials for the Dynamics 365 app to install the solution.</span></span>

<span data-ttu-id="2943b-123">Pode que a solución tarde un tempo en instalarse no seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="2943b-123">It can take some time for the solution to be installed to your environment.</span></span>

## <a name="configure-the-customer-card-add-in"></a><span data-ttu-id="2943b-124">Configurar o complemento de tarxeta de cliente</span><span class="sxs-lookup"><span data-stu-id="2943b-124">Configure the Customer Card Add-in</span></span>

1. <span data-ttu-id="2943b-125">Como administrador, vaia á sección **Configuración** en Dynamics 365 e seleccione **Solucións**.</span><span class="sxs-lookup"><span data-stu-id="2943b-125">As an admin, go to the **Settings** section in Dynamics 365 and select **Solutions**.</span></span>

1. <span data-ttu-id="2943b-126">Seleccione a ligazón **Nome de pantalla** para a solución **Complemento de tarxeta de cliente de Dynamics 365 Customer Insights (vista previa)**.</span><span class="sxs-lookup"><span data-stu-id="2943b-126">Select the **Display Name** link for the **Dynamics 365 Customer Insights Customer Card Add-in (Preview)** solution.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="2943b-127">![Seleccionar o nome para mostrar](media/select-display-name.png "Seleccionar o nome para mostrar")</span><span class="sxs-lookup"><span data-stu-id="2943b-127">![Select display name](media/select-display-name.png "Select display name")</span></span>

1. <span data-ttu-id="2943b-128">Seleccione **Iniciar sesión** e insira as credenciais da conta de administrador que use para configurar Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="2943b-128">Select **Sign in** and enter the credentials for the admin account you use to configure Customer Insights.</span></span>

   > [!NOTE]
   > <span data-ttu-id="2943b-129">Asegúrese de que o bloqueador de ventás emerxentes do navegador non bloquee a ventá de autenticación cando seleccione o botón **Iniciar sesión**.</span><span class="sxs-lookup"><span data-stu-id="2943b-129">Check that the browser pop-up blocker does not block the authentication window when you select the **Sign in** button.</span></span>

1. <span data-ttu-id="2943b-130">Seleccione o ambiente de Customer Insights do que desexa obter datos.</span><span class="sxs-lookup"><span data-stu-id="2943b-130">Select the Customer Insights environment you want to fetch data from.</span></span>

1. <span data-ttu-id="2943b-131">Defina a asignación de campos para rexistros na aplicación de Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="2943b-131">Define the field mapping to records in the Dynamics 365 app.</span></span> <span data-ttu-id="2943b-132">En función dos seus datos en Customer Insights, pode escoller asignar as seguintes opcións:</span><span class="sxs-lookup"><span data-stu-id="2943b-132">Depending on your data in Customer Insights you can choose to map the following options:</span></span>
   - <span data-ttu-id="2943b-133">Para asignar cun contacto, seleccione o campo da entidade de cliente que coincida co ID da súa entidade de contacto.</span><span class="sxs-lookup"><span data-stu-id="2943b-133">To map with a contact, select the field in the Customer entity that matches the ID of your contact entity.</span></span>
   - <span data-ttu-id="2943b-134">Para asignar cunha conta, seleccione o campo da entidade de cliente que coincida co ID da súa entidade de conta.</span><span class="sxs-lookup"><span data-stu-id="2943b-134">To map with an account, select the field in the Customer entity that matches the ID of your account entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="2943b-135">![Campo de ID de contacto](media/contact-id-field.png "Campo de ID de contacto")</span><span class="sxs-lookup"><span data-stu-id="2943b-135">![Contact ID field](media/contact-id-field.png "Contact ID field")</span></span>

1. <span data-ttu-id="2943b-136">Seleccione **Gardar configuración** para gardar os axustes.</span><span class="sxs-lookup"><span data-stu-id="2943b-136">Select **Save configuration** to save the settings.</span></span>

1. <span data-ttu-id="2943b-137">A continuación, ten que asignar roles de seguridade en Dynamics 365 para que os usuarios poidan personalizar e ver a tarxeta de cliente.</span><span class="sxs-lookup"><span data-stu-id="2943b-137">Next, you need to assign security roles in Dynamics 365 so users can customize and see the customer card.</span></span> <span data-ttu-id="2943b-138">En Dynamics 365, vaia a **Configuración** > **Seguranza** > **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="2943b-138">In Dynamics 365, go to **Settings** > **Security** > **Users**.</span></span> <span data-ttu-id="2943b-139">Seleccione os usuarios para editar os roles de usuario e seleccione **Xestionar papeis**.</span><span class="sxs-lookup"><span data-stu-id="2943b-139">Select the users to edit user roles and select **Manage roles**.</span></span>

1. <span data-ttu-id="2943b-140">Asigne o rol de **Personalizador de tarxetas de Customer Insights** aos usuarios que personalizarán o contido mostrado na tarxeta para toda a organización.</span><span class="sxs-lookup"><span data-stu-id="2943b-140">Assign the **Customer Insights Card Customizer** role to users who will customize the content shown on the card for the whole organization.</span></span>

## <a name="add-customer-card-controls-to-forms"></a><span data-ttu-id="2943b-141">Engadir controis de cartón de cliente aos formularios</span><span class="sxs-lookup"><span data-stu-id="2943b-141">Add Customer Card controls to forms</span></span>
  
1. <span data-ttu-id="2943b-142">Para engadir os controis da tarxeta de cliente ao formulario de contacto, diríxase a **Configuración** > **Personalizacións** en Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="2943b-142">To add the Customer Card controls to your Contact form, go to the **Settings** > **Customizations** in Dynamics 365.</span></span>

1. <span data-ttu-id="2943b-143">Seleccione **Personalizar o sistema**.</span><span class="sxs-lookup"><span data-stu-id="2943b-143">Select **Customize the System**.</span></span>

1. <span data-ttu-id="2943b-144">Navegue ata a entidade de **contacto**, expanda o seu menú e logo seleccione **Formularios**.</span><span class="sxs-lookup"><span data-stu-id="2943b-144">Browse to the **Contact** entity, expand it and select **Forms**.</span></span>

1. <span data-ttu-id="2943b-145">Seleccione o formulario de contacto ao que desexa engadir os controis da tarxeta de cliente.</span><span class="sxs-lookup"><span data-stu-id="2943b-145">Select the contact form to which you want to add the Customer Card controls.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="2943b-146">![Seleccionar formulario de contacto](media/contact-active-forms.png "Seleccionar formulario de contacto")</span><span class="sxs-lookup"><span data-stu-id="2943b-146">![Select Contact form](media/contact-active-forms.png "Select Contact form")</span></span>

1. <span data-ttu-id="2943b-147">Para engadir un control no editor de formularios, arrastre calquera campo do **Explorador de campos** ata onde desexe colocar o control.</span><span class="sxs-lookup"><span data-stu-id="2943b-147">To add a control, in the form editor, drag any field from the **Field Explorer** to where you want the control to appear.</span></span>

1. <span data-ttu-id="2943b-148">Seleccione o campo no formulario que acaba de engadir e seleccione **Cambiar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="2943b-148">Select the field on the form that you just added, and select **Change Properties**.</span></span>

1. <span data-ttu-id="2943b-149">Vaia ao separador **Controis** e seleccione **Engadir control**.</span><span class="sxs-lookup"><span data-stu-id="2943b-149">Go to the **Controls** tab and select **Add Control**.</span></span> <span data-ttu-id="2943b-150">Escolla un dos controis personalizados dispoñibles e seleccione **Engadir**.</span><span class="sxs-lookup"><span data-stu-id="2943b-150">Choose one of the available custom controls and select **Add**.</span></span>

1. <span data-ttu-id="2943b-151">Na caixa de diálogo **Propiedades do campo**, desmarque a caixa de verificación **Mostrar etiqueta no formulario**.</span><span class="sxs-lookup"><span data-stu-id="2943b-151">In the **Field Properties** dialog, clear the **Display label on the form** check box.</span></span>

1. <span data-ttu-id="2943b-152">Seleccione a opción **Web** para o control.</span><span class="sxs-lookup"><span data-stu-id="2943b-152">Select the **Web** option for the control.</span></span> <span data-ttu-id="2943b-153">No control de enriquecemento, seleccione o tipo de enriquecemento que desexa amosar configurando o campo **enrichmentType**.</span><span class="sxs-lookup"><span data-stu-id="2943b-153">For the Enrichment control, select which enrichment type you want to display by configuring the **enrichmentType** field.</span></span> <span data-ttu-id="2943b-154">Engada un control de enriquecemento separado para cada tipo de enriquecemento.</span><span class="sxs-lookup"><span data-stu-id="2943b-154">Add a separate enrichment control for each enrichment type.</span></span>

1. <span data-ttu-id="2943b-155">Seleccione **Gardar** e **Publicar** para publicar o formulario de contacto actualizado.</span><span class="sxs-lookup"><span data-stu-id="2943b-155">Select **Save** and **Publish** to publish the updated contact form.</span></span>

1. <span data-ttu-id="2943b-156">Vaia ao formulario de contacto publicado.</span><span class="sxs-lookup"><span data-stu-id="2943b-156">Go to the published contact form.</span></span> <span data-ttu-id="2943b-157">Verá o control que acaba de engadir.</span><span class="sxs-lookup"><span data-stu-id="2943b-157">You'll see the newly added control.</span></span> <span data-ttu-id="2943b-158">É posible que teña que iniciar sesión a primeira vez que o use.</span><span class="sxs-lookup"><span data-stu-id="2943b-158">You might need to sign in the first time you use it.</span></span>

1. <span data-ttu-id="2943b-159">Para personalizar o que quere mostrar no control personalizado, seleccione o botón de edición na esquina superior dereita.</span><span class="sxs-lookup"><span data-stu-id="2943b-159">To customize what you want to show on the custom control, select the edit button in the upper-right corner.</span></span>

## <a name="upgrade-customer-card-add-in"></a><span data-ttu-id="2943b-160">Actualizar complemento do cartón do cliente</span><span class="sxs-lookup"><span data-stu-id="2943b-160">Upgrade Customer Card Add-in</span></span>
<span data-ttu-id="2943b-161">O complemento de tarxeta de cliente non se actualiza automaticamente.</span><span class="sxs-lookup"><span data-stu-id="2943b-161">The Customer Card Add-in doesn't upgrade automatically.</span></span> <span data-ttu-id="2943b-162">Para actualizar á última versión, siga este procedemento na aplicación Dynamics 365 que ten instalado o complemento.</span><span class="sxs-lookup"><span data-stu-id="2943b-162">To upgrade to the latest version, follow this procedure in the Dynamics 365 app that has the Add-in installed.</span></span>

1. <span data-ttu-id="2943b-163">Na aplicación Dynamics 365, vai a **Configuración** > **Personalización** e seleccione **Solucións**.</span><span class="sxs-lookup"><span data-stu-id="2943b-163">In the Dynamics 365 app, go to **Settings** > **Customization** and select **Solutions**.</span></span>

1. <span data-ttu-id="2943b-164">Na táboa de complementos, busque **CustomerInsightsCustomerCard** e seleccione a fila.</span><span class="sxs-lookup"><span data-stu-id="2943b-164">In the table of add-ins look for **CustomerInsightsCustomerCard** and select the row.</span></span>

1. <span data-ttu-id="2943b-165">Seleccione **Aplicar a actualización da solución** na barra de acción.</span><span class="sxs-lookup"><span data-stu-id="2943b-165">Select the **Apply Solution Upgrade** in the action bar.</span></span>

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Actualice a solución na área de personalización das aplicacións de Dynamics 365":::

1. <span data-ttu-id="2943b-167">Despois de iniciar o proceso de actualización, verá un indicador de carga ata que finalice a actualización.</span><span class="sxs-lookup"><span data-stu-id="2943b-167">After starting the upgrade process, you'll see a loading indicator until the upgrade completes.</span></span> <span data-ttu-id="2943b-168">Se non hai ningunha versión máis recente, a actualización amosará unha mensaxe de erro.</span><span class="sxs-lookup"><span data-stu-id="2943b-168">If there's no newer version, the upgrade will show an error message.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
