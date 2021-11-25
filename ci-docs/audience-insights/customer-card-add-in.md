---
title: Suplemento do cartón de cliente das aplicacións de Dynamics 365
description: Mostrar datos de información do público nas aplicacións de Dynamics 365 con este suplemento.
ms.date: 09/30/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: dbcdcbea8ffd1755b58c322233c08c70a065db36
ms.sourcegitcommit: 31a9b531dacd3a6465b3030c704ff5c085b7e122
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 11/10/2021
ms.locfileid: "7792025"
---
# <a name="customer-card-add-in-preview"></a>Complemento do cartón do cliente (vista previa)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Obteña unha vista de 360 graos dos seus clientes directamente nas aplicacións de Dynamics 365. Co complemento de tarxeta de cliente instalado nunha aplicación de Dynamics 365 compatible, pode escoller amosar campos de perfil de cliente, estatísticas e cronoloxía da actividade. O suplemento recuperará datos de Customer Insights sen afectar aos datos da aplicación de Dynamics 365 conectada.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN1qv]

## <a name="prerequisites"></a>Requisitos previos

- O suplemento só funciona con aplicacións de Dynamics 365 controladas por modelos, como Sales ou Customer Service, versión 9.0 e posteriores.
- Para que os seus datos de Dynamics 365 se asignen aos perfís dos clientes da información da audiencia, deben estar [inxerido desde a aplicación Dynamics 365 mediante o conector Microsoft Dataverse](connect-power-query.md).
- Todos os usuarios de Dynamics 365 do suplemento do cartón do cliente deben [engadirse como usuarios](permissions.md) na información do público para ver os datos.
- Na información do público precísanse [capacidades de busca e filtros configuradas](search-filter-index.md) para que a busca de datos funcione.
- Cada control do suplemento depende de datos específicos na información do público. Algúns datos e controis só están dispoñibles en contornos de tipos específicos. A configuración do complemento informaralle se un control non está dispoñible debido ao tipo de ambiente seleccionado. Obteña máis información acerca de [casos de uso de contornos](work-with-business-accounts.md).
  - **Control de medidas**: require [medidas configuradas](measures.md) do tipo de atributos do cliente.
  - **Control de intelixencia**: require datos xerados mediante [predicións](predictions.md) ou [modelos personalizados](custom-models.md).
  - **Control dos detalles do cliente**: todos os campos do perfil están dispoñibles no perfil de cliente unificado.
  - **Control do enriquecemento**: require [enriquecementos](enrichment-hub.md) activos aplicados aos perfís de clientes. O complemento da tarxeta admite estes enriquecementos: [Marcas](enrichment-microsoft.md) proporcionado por Microsoft, [Intereses](enrichment-microsoft.md) proporcionado por Microsoft.
  - **Control de contactos**: require definición de entidade semántica de contactos tipo.
  - **Control da liña de tempo**: require [actividades configuradas](activities.md).

## <a name="install-the-customer-card-add-in"></a>Instalar o complemento do cartón do cliente

O complemento de tarxeta de cliente é unha solución para aplicacións de interacción cos clientes en Dynamics 365. Para instalar a solución, vai a AppSource e busca **Tarxeta Cliente Dynamics**. Seleccione o [Complemento da tarxeta de cliente en AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) e selecciona [Conseguilo agora\]\(...\).

Pode que necesite iniciar sesión coas súas credenciais de administrador da aplicación de Dynamics 365 para instalar a solución. Pode que a solución tarde un tempo en instalarse no seu ambiente.

## <a name="configure-the-customer-card-add-in"></a>Configurar o complemento de tarxeta de cliente

1. Como administrador, vaia á sección **Configuración** en Dynamics 365 e seleccione **Solucións**.

1. Seleccione o **Nome para mostrar** ligazón para o **Dynamics 365 Customer Insights Complemento da tarxeta de cliente (vista previa)** solución.

   > [!div class="mx-imgBorder"]
   > ![Seleccionar o nome para mostrar.](media/select-display-name.png "Seleccionar o nome para mostrar.")

1. Seleccione **Iniciar sesión** e insira as credenciais da conta de administrador que use para configurar Customer Insights.

   > [!NOTE]
   > Asegúrese de que o bloqueador de ventás emerxentes do navegador non bloquee a ventá de autenticación cando seleccione o botón **Iniciar sesión**.

1. Seleccione o ambiente de Customer Insights do que desexa obter datos.

1. Defina a asignación de campos para rexistros na aplicación de Dynamics 365. En función dos seus datos en Customer Insights, pode escoller asignar as seguintes opcións:
   - Para asignar cun contacto, seleccione o campo da entidade de cliente que coincida co ID da súa entidade de contacto.
   - Para asignar cunha conta, seleccione o campo da entidade de cliente que coincida co ID da súa entidade de conta.

   > [!div class="mx-imgBorder"]
   > ![Campo de ID de contacto.](media/contact-id-field.png "Campo de ID de contacto.")

1. Seleccione **Gardar configuración** para gardar os axustes.

1. A continuación, ten que asignar roles de seguridade en Dynamics 365 para que os usuarios poidan personalizar e ver a tarxeta de cliente. En Dynamics 365, vaia a **Configuración** > **Seguranza** > **Usuarios**. Seleccione os usuarios para editar os roles de usuario e seleccione **Xestionar papeis**.

1. Asigne o rol de **Personalizador de tarxetas de Customer Insights** aos usuarios que personalizarán o contido mostrado na tarxeta para toda a organización.

## <a name="add-customer-card-controls-to-forms"></a>Engadir controis de cartón de cliente aos formularios

Dependendo do seu escenario, pode escoller engadir controis ao formulario de **Contacto** ou de **Conta**. Se o seu contorno de información sobre o público é para contas comerciais, recomendamos engadir os controis ao formulario de conta. Nese caso, substitúa "contacto" nos pasos seguintes por "conta".

1. Para engadir os controis da tarxeta de cliente ao formulario de contacto, diríxase a **Configuración** > **Personalizacións** en Dynamics 365.

1. Seleccione **Personalizar o sistema**.

1. Navegue ata a entidade de **contacto**, expanda o seu menú e logo seleccione **Formularios**.

1. Seleccione o formulario de contacto ao que desexa engadir os controis da tarxeta de cliente.

    > [!div class="mx-imgBorder"]
    > ![Seleccionar formulario de contacto.](media/contact-active-forms.png "Seleccionar formulario de contacto.")

1. Para engadir un control no editor de formularios, arrastre calquera campo do **Explorador de campos** ata onde desexe colocar o control.

1. Seleccione o campo no formulario que acaba de engadir e seleccione **Cambiar propiedades**.

1. Vaia ao separador **Controis** e seleccione **Engadir control**. Escolla un dos controis personalizados dispoñibles e seleccione **Engadir**.

1. Na caixa de diálogo **Propiedades do campo**, desmarque a caixa de verificación **Mostrar etiqueta no formulario**.

1. Seleccione a opción **Web** para o control. No control de enriquecemento, seleccione o tipo de enriquecemento que desexa amosar configurando o campo **enrichmentType**. Engada un control de enriquecemento separado para cada tipo de enriquecemento.

1. Seleccione **Gardar** e **Publicar** para publicar o formulario de contacto actualizado.

1. Vaia ao formulario de contacto publicado. Verá o control que acaba de engadir. É posible que teña que iniciar sesión a primeira vez que o use.

1. Para personalizar o que quere mostrar no control personalizado, seleccione o botón de edición na esquina superior dereita.

## <a name="upgrade-customer-card-add-in"></a>Actualizar complemento do cartón do cliente

O complemento de tarxeta de cliente non se actualiza automaticamente. Para actualizar á última versión, siga estes pasos na aplicación Dynamics 365 que ten instalado o complemento.

1. Na aplicación Dynamics 365, vai a **Configuración** > **Personalización** e seleccione **Solucións**.

1. Na táboa de complementos, busque **CustomerInsightsCustomerCard** e seleccione a fila.

1. Seleccione **Aplicar a actualización da solución** na barra de acción.

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Actualice a solución na área de personalización das aplicacións de Dynamics 365.":::

1. Despois de iniciar o proceso de actualización, verá un indicador de carga ata que finalice a actualización. Se non hai ningunha versión máis recente, a actualización amosará unha mensaxe de erro.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
