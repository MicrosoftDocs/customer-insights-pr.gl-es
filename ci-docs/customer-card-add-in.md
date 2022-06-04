---
title: Complemento da tarxeta de cliente para as aplicacións de Dynamics 365 (contén vídeo)
description: Mostra os datos do perfil do cliente de Customer Insights nas aplicacións de Dynamics 365 con este complemento.
ms.date: 02/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
searchScope:
- ci-customers-page
- ci-search-filter
- ci-customer-card
- customerInsights
ms.openlocfilehash: 8508880bb3274bb491a314a043a5222d4d381073
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755634"
---
# <a name="customer-card-add-in-preview"></a>Complemento do cartón do cliente (vista previa)

Obteña unha vista de 360 graos dos seus clientes directamente nas aplicacións de Dynamics 365. Co complemento de tarxeta de cliente instalado nunha aplicación de Dynamics 365 compatible, pode escoller amosar campos de perfil de cliente, estatísticas e cronoloxía da actividade. O suplemento recuperará datos de Customer Insights sen afectar aos datos da aplicación de Dynamics 365 conectada.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN1qv]

## <a name="prerequisites"></a>Requisitos previos

- O suplemento só funciona con aplicacións de Dynamics 365 controladas por modelos, como Sales ou Customer Service, versión 9.0 e posteriores.
- Para que os seus datos de Dynamics 365 se asignen aos perfís de clientes de Customer Insights, recomendamos que [inxerido desde a aplicación Dynamics 365 mediante o Microsoft Dataverse conector](connect-power-query.md). Se utilizas un método diferente para inxerir contactos (ou contas) de Dynamics 365, debes asegurarte de que`contactid` (ou`accountid`) defínese como o campo [clave principal para ese orixe de datos no paso do mapa do proceso de unificación de datos](map-entities.md#select-primary-key-and-semantic-type-for-attributes).
- Todos os usuarios de Dynamics 365 do complemento da tarxeta de cliente deben ser [engadidos como usuarios](permissions.md) en Customer Insights para ver os datos.
- [Capacidades de busca e filtro configuradas](search-filter-index.md) en Customer Insights son necesarios para que funcione a busca de datos.
- Cada control de complemento depende de datos específicos de Customer Insights. Algúns datos e controis só están dispoñibles en contornos de tipos específicos. A configuración do complemento informarache se un control non está dispoñible debido ao tipo de ambiente seleccionado. Obteña máis información acerca de [casos de uso de contornos](work-with-business-accounts.md).
  - **Control de medidas**: require [medidas configuradas](measures.md) do tipo de atributos do cliente.
  - **Control de intelixencia** : Require datos xerados mediante [predicións ou modelos personalizados](predictions-overview.md).
  - **Control dos detalles do cliente**: todos os campos do perfil están dispoñibles no perfil de cliente unificado.
  - **Control do enriquecemento**: require [enriquecementos](enrichment-hub.md) activos aplicados aos perfís de clientes. O complemento da tarxeta admite estes enriquecementos: [Marcas](enrichment-microsoft.md) proporcionado por Microsoft, [Intereses](enrichment-microsoft.md) proporcionado por Microsoft e [Datos de compromiso da oficina](enrichment-office.md) proporcionado por Microsoft.
  - **Control de contactos**: require definición de entidade semántica de contactos tipo.
  - **Control da liña de tempo**: require [actividades configuradas](activities.md).

## <a name="install-the-customer-card-add-in"></a>Instalar o complemento do cartón do cliente

O complemento de tarxeta de cliente é unha solución para aplicacións de interacción cos clientes en Dynamics 365. Para instalar a solución, vaia a AppSource e busque **Tarxeta de cliente de Dynamics**. Seleccione o [Complemento da tarxeta de cliente en AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) e seleccione **Obtelo agora**.

Pode que necesite iniciar sesión coas súas credenciais de administrador da aplicación de Dynamics 365 para instalar a solución. Pode que a solución tarde un tempo en instalarse no seu ambiente.

## <a name="configure-the-customer-card-add-in"></a>Configurar o complemento de tarxeta de cliente

1. Como administrador, vaia á sección **Configuración** en Dynamics 365 e seleccione **Solucións**.

1. Seleccione a ligazón **Nome de pantalla** para a solución **Complemento de tarxeta de cliente de Dynamics 365 Customer Insights (vista previa)**.

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

Dependendo do seu escenario, pode escoller engadir controis ao formulario de **Contacto** ou de **Conta**. Se o teu ambiente de Customer Insights é para contas empresariais, recomendamos engadir os controis ao formulario Conta. Nese caso, substitúa "contacto" nos pasos seguintes por "conta".

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

## <a name="troubleshooting"></a>Resolución de problemas

### <a name="controls-from-customer-card-add-in-dont-find-data"></a>Os controis do complemento da tarxeta de cliente non atopan datos

**Problema:**

Mesmo con campos de identificación configurados correctamente, os controis non poden atopar datos de ningún cliente.  

**Resolución:**

1. Asegúrate de configurar o complemento de tarxeta segundo as instrucións: [Configure o complemento da tarxeta de cliente](#configure-the-customer-card-add-in)

1. Revisa a configuración da inxestión de datos. Edite o orixe de datos para o sistema Dynamics 365 que contén o GUID do ID de contacto. Se o GUID de ID de contacto aparece con caracteres en maiúsculas Power Query editor, proba os seguintes pasos:
    1. Edita o orixe de datos para abrir o orixe de datos en Power Query Editor.
    1. Seleccione a columna ID de contacto.
    1. Seleccione **Transformar** na barra de cabeceira para ver as accións dispoñibles.
    1. Seleccione **minúscula**. Valida se os GUID da táboa están agora en minúscula.
    1. Garde a orixe de datos.
    1. Executar procesos de inxestión, unificación e posterior de datos para propagar os cambios no GUID.

Despois de que o sistema complete a actualización completa, os controis do complemento da tarxeta de cliente deberían mostrar os datos esperados.

[!INCLUDE [footer-include](includes/footer-banner.md)]