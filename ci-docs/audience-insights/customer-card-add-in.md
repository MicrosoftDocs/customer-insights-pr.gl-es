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
# <a name="customer-card-add-in-preview"></a>Complemento do cartón do cliente (vista previa)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Obteña unha vista de 360 graos dos seus clientes directamente nas aplicacións de Dynamics 365. Permite ver datos demográficos, información e cronoloxías de actividades co complemento da tarxeta de cliente.

## <a name="prerequisites"></a>Requisitos previos

- Aplicación de Dynamics 365 (como Plataforma común de vendas ou Plataforma común de servizo de atención ao cliente), versión 9.0 e posterior con Interface unificada activada.
- Perfís de clientes [inxeridos desde a aplicación de Dynamics 365 usando Common Data Service](connect-power-query.md).
- Os usuarios do complemento de tarxeta de cliente deben ser [engadidos como usuarios](permissions.md) en información do público.
- [Capacidades de busca e filtraxe configuradas](search-filter-index.md).
- Control demográfico: os campos demográficos (como a idade ou o sexo) están dispoñibles no perfil de cliente unificado.
- Control do enriquecemento: require [enriquecementos](enrichment-hub.md) activos aplicados aos perfís de clientes.
- Control intelixente: require datos xerados mediante Azure Machine Learning ([predicións](predictions.md) ou [modelos personalizados](custom-models.md))
- Control de medidas: require [medidas configuradas](measures.md).
- Control da liña de tempo: require [actividades configuradas](activities.md).

## <a name="install-the-customer-card-add-in"></a>Instalar o complemento do cartón do cliente

O complemento de tarxeta de cliente é unha solución para aplicacións de interacción cos clientes en Dynamics 365. Para instalar a solución, vaia a AppSource e busque **Tarxeta de cliente de Dynamics**. Seleccione o [Complemento da tarxeta de cliente en AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) e seleccione **Obtelo agora**.

Pode que necesite iniciar sesión coas súas credenciais de administrador da aplicación de Dynamics 365 para instalar a solución.

Pode que a solución tarde un tempo en instalarse no seu ambiente.

## <a name="configure-the-customer-card-add-in"></a>Configurar o complemento de tarxeta de cliente

1. Como administrador, vaia á sección **Configuración** en Dynamics 365 e seleccione **Solucións**.

1. Seleccione a ligazón **Nome de pantalla** para a solución **Complemento de tarxeta de cliente de Dynamics 365 Customer Insights (vista previa)**.

   > [!div class="mx-imgBorder"]
   > ![Seleccionar o nome para mostrar](media/select-display-name.png "Seleccionar o nome para mostrar")

1. Seleccione **Iniciar sesión** e insira as credenciais da conta de administrador que use para configurar Customer Insights.

   > [!NOTE]
   > Asegúrese de que o bloqueador de ventás emerxentes do navegador non bloquee a ventá de autenticación cando seleccione o botón **Iniciar sesión**.

1. Seleccione o ambiente do que desexa obter datos.

1. Defina cal é a asignación de campos para os rexistros na aplicación de Dynamics 365.
   - Para asignar cun contacto, seleccione o campo da entidade de cliente que coincida co ID da súa entidade de contacto.
   - Para asignar cunha conta, seleccione o campo da entidade de cliente que coincida co ID da súa entidade de conta.

   > [!div class="mx-imgBorder"]
   > ![Campo de ID de contacto](media/contact-id-field.png "Campo de ID de contacto")

1. Seleccione **Gardar configuración** para gardar os axustes.

1. A continuación, ten que asignar roles de seguridade en Dynamics 365 para que os usuarios poidan personalizar e ver a tarxeta de cliente. En Dynamics 365, vaia a **Configuración** > **Seguranza** > **Usuarios**. Seleccione os usuarios para editar os roles de usuario e seleccione **Xestionar papeis**.

1. Asigne o rol de **Personalizador de tarxetas de Customer Insights** aos usuarios que personalizarán o contido mostrado na tarxeta para toda a organización.

## <a name="add-customer-card-controls-to-forms"></a>Engadir controis de cartón de cliente aos formularios
  
1. Para engadir os controis da tarxeta de cliente ao formulario de contacto, diríxase a **Configuración** > **Personalizacións** en Dynamics 365.

1. Seleccione **Personalizar o sistema**.

1. Navegue ata a entidade de **contacto**, expanda o seu menú e logo seleccione **Formularios**.

1. Seleccione o formulario de contacto ao que desexa engadir os controis da tarxeta de cliente.

    > [!div class="mx-imgBorder"]
    > ![Seleccionar formulario de contacto](media/contact-active-forms.png "Seleccionar formulario de contacto")

1. Para engadir un control no editor de formularios, arrastre calquera campo do **Explorador de campos** ata onde desexe colocar o control.

1. Seleccione o campo no formulario que acaba de engadir e seleccione **Cambiar propiedades**.

1. Vaia ao separador **Controis** e seleccione **Engadir control**. Escolla un dos controis personalizados dispoñibles e seleccione **Engadir**.

1. Na caixa de diálogo **Propiedades do campo**, desmarque a caixa de verificación **Mostrar etiqueta no formulario**.

1. Seleccione a opción **Web** para o control. No control de enriquecemento, seleccione o tipo de enriquecemento que desexa amosar configurando o campo **enrichmentType**. Engada un control de enriquecemento separado para cada tipo de enriquecemento.

1. Seleccione **Gardar** e **Publicar** para publicar o formulario de contacto actualizado.

1. Vaia ao formulario de contacto publicado. Verá o control que acaba de engadir. É posible que teña que iniciar sesión a primeira vez que o use.

1. Para personalizar o que quere mostrar no control personalizado, seleccione o botón de edición na esquina superior dereita.

## <a name="upgrade-customer-card-add-in"></a>Actualizar complemento do cartón do cliente
O complemento de tarxeta de cliente non se actualiza automaticamente. Para actualizar á última versión, siga este procedemento na aplicación Dynamics 365 que ten instalado o complemento.

1. Na aplicación Dynamics 365, vai a **Configuración** > **Personalización** e seleccione **Solucións**.

1. Na táboa de complementos, busque **CustomerInsightsCustomerCard** e seleccione a fila.

1. Seleccione **Aplicar a actualización da solución** na barra de acción.

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Actualice a solución na área de personalización das aplicacións de Dynamics 365":::

1. Despois de iniciar o proceso de actualización, verá un indicador de carga ata que finalice a actualización. Se non hai ningunha versión máis recente, a actualización amosará unha mensaxe de erro.


[!INCLUDE[footer-include](../includes/footer-banner.md)]