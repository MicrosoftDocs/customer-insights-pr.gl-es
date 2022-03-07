---
title: Solicitudes de dereitos do titular dos datos (DSR) baixo RXPD | Microsoft Docs
description: Responda ás solicitudes dos titulares dos datos da capacidade de información do público de Dynamics 365 Customer Insights.
ms.date: 08/11/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: e095eb4f8e194f314d7d6baf6fa6a7a319319d2a
ms.sourcegitcommit: 1946d7af0bd2ca216885bec3c5c95009996d9a28
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 02/25/2022
ms.locfileid: "8350267"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Solicitudes de dereitos do titular dos datos (DSR) baixo RXPD

O Regulamento xeral de protección de datos (RXPD) da Unión Europea está en vigor desde o 25 de maio de 2018. Concédelles dereitos significativos ás persoas con respecto aos seus datos. O obxectivo do RXPD é protexer e activar os dereitos de privacidade das persoas. Atopará máis información sobre o compromiso de Microsoft coa seguranza e o cumprimento no [Centro de confianza de Microsoft](https://www.microsoft.com/trust-center).

Comprometémonos a axudar aos nosos clientes a cumprir os seus requisitos de RXPD. Inclúe o dereito a eliminar e exportar datos que inclúan información persoal, como os ID de usuario, números de teléfono e enderezos de correo electrónico. Os administradores poden implementar as solicitudes dos usuarios para eliminar ou exportar datos persoais.

## <a name="audience-insights"></a>Información do público

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a>Responder ás solicitudes de eliminación dos titulares dos datos segunco o RXPD para a capacidade de información do público de Dynamics 365 Customer Insights

O "dereito á eliminación" de datos persoais dos datos de clientes dunha organización é unha protección clave no Regulamento xeral de protección de datos (RXPD). A eliminación de datos persoais inclúe a eliminación de todos os datos persoais e os rexistros xerados polo sistema, excepto a información do rexistro de auditoría.

#### <a name="manage-data-subject-delete-requests"></a>Xestionar as solicitudes de eliminación do titular dos datos

A información do público ofrece as seguintes experiencias internas para eliminar datos persoais dun cliente específico ou usuario:

- **Xestionar solicitudes de eliminación de datos de clientes**: os datos do cliente de Customer Insights son inxeridos de fontes de datos orixinais externas a Customer Insights. Todas as solicitudes de eliminación de RXPD deben realizarse na orixe de datos orixinal.
- **Xestionar solicitudes de eliminación de datos de usuario de Customer Insights**: Os datos dos usuarios son creados por Customer Insights. Todas as solicitudes de eliminación de RXPD deben realizarse en Customer Insights.

##### <a name="manage-requests-to-delete-customer-data"></a>Xestionar solicitudes de eliminación de datos de clientes

Un administrador de Customer Insights pode seguir estes pasos para eliminar os datos de clientes que se eliminaron na orixe de datos:

1. Inicie sesión en Dynamics 365 Customer Insights.
2. Na información do público, vaia a **Datos** > **Orixes de datos**
3. Para cada orixe de datos da lista que contén datos de clientes eliminados:
   1. Seleccione (...) e, a seguir, seleccione **Actualizar**.
   2. Consulte o estado da orixe de datos en **Estado**. A aparición dunha marca de verificación significa que a actualización tivo éxito. Un triángulo de aviso significa que algo saíu mal. Se aparece un triángulo de aviso, póñase en contacto con D365CI@microsoft.com.

> [!div class="mx-imgBorder"]
> ![Manipulación de solicitudes de eliminación de RXPD para datos de clientes.](audience-insights/media/gdpr-data-sources.png "Manipulación de solicitudes de eliminación de RXPD para datos de clientes")

##### <a name="manage-delete-requests-for-user-data"></a>Xestionar solicitudes de eliminación de datos de usuario

Un administrador de Customer Insights pode seguir estes pasos para eliminar os datos de usuarios de Customer Insights:

1. Inicie sesión en Dynamics 365 Customer Insights.
2. Na información do público, vaia a **Administrar** > **Permisos**.
3. Marque a caixa de verificación do usuario que desexe eliminar.
4. Seleccione **Quitar**.

### <a name="responding-to-gdpr-data-subject-export-requests"></a>Responder a solicitudes de exportación de titulares dos datos segundo o RXPD

Como parte do noso compromiso de asociarnos con vostede na aplicación do Regulamento xeral de protección de datos (RXPD), elaboramos documentación para axudarlle a prepararse. Esta documentación describe os pasos que pode seguir hoxe para apoiar o cumprimento do RXPD cando se empregan as estatísticas do público.

#### <a name="manage-export-and-view-requests"></a>Xestionar solicitudes de exportación e visualización

O dereito de portabilidade de datos permite a un titular solicitar unha copia dos seus datos persoais nun formato electrónico (definido como un "formato estruturado, utilizado comunmente, lexible por máquinas e interoperable") que pode ser transmitido a outro controlador de datos.

##### <a name="export-customer-data-tenant-admin"></a>Exportar datos de clientes (administrador de arrendatarios)

Un administrador de arrendatarios pode seguir estes pasos para exportar datos:

1. Envíe un correo electrónico a D365CI@microsoft.com especificando o enderezo de correo electrónico do cliente na solicitude. O equipo de Customer Insights enviará un correo electrónico ao enderezo de correo electrónico do administrador do arrendatario rexistrado e pedirá confirmación para exportar datos.
2. Recoñeza a confirmación para exportar os datos do cliente solicitado.
3. Reciba os datos exportados a través do enderezo de correo electrónico do administrador do arrendatario.

##### <a name="export-user-data-tenant-admin"></a>Exportar datos de usuario (administrador de arrendatarios)

1. Envíe un correo electrónico a D365CI@microsoft.com especificando o enderezo de correo electrónico do usuario na solicitude. O equipo de Customer Insights enviará un correo electrónico ao enderezo de correo electrónico do administrador do arrendatario rexistrado e pedirá confirmación para exportar datos.
2. Recoñeza a confirmación para exportar os datos do usuario solicitado.
3. Reciba os datos exportados a través do enderezo de correo electrónico do administrador do arrendatario.

## <a name="consent-management-preview"></a>Xestión do consentimento (vista previa)

A capacidade de xestión do consentimento non recolle directamente datos do usuario. Só importa e procesa os datos de consentimento que proporcionan os usuarios noutras aplicacións.

Para eliminar os datos de consentimento de usuarios específicos, elimínaos das fontes de datos inxeridas coa capacidade de xestión do consentimento. Despois de actualizar o orixe de datos, os datos eliminados tamén se eliminarán no Centro de consentimento. As aplicacións que usan a entidade de consentimento tamén eliminarán os datos que se eliminaron da fonte despois de a [refrescar](audience-insights/system.md#refresh-processes). Recomendamos actualizar as fontes de datos rapidamente despois de responder a unha solicitude do suxeito de datos para eliminar os datos do usuario de todos os demais procesos e aplicacións.


<!-- ## Engagement insights (preview)

### Deleting and exporting event data containing end user identifiable information

The following sections describe how to delete and export event data that might contain personal data.

To delete or export data:

1. Tag event properties that contain data with personal information.
2. Delete or export data associated with specific values (for example: a specified user ID).

#### Tag and update event properties

Personal data is tagged on an event property level. First, tag the properties being considered for deletion or export.

To tag an event property as containing personal information, follow these steps:

1. Open the workspace containing the event.

1. Go to **Data** > **Events** to see the list of events in the selected workspace.
  
1. Select the event you want to tag.

1. Select **Edit properties** to open the pane listing all properties of the selected event.
     
1. Select **...** and then choose **Edit** to reach the **Update property** dialog.

   ![Edit event.](engagement-insights/media/edit-event.png "Edit event")

1. In the **Update Property** window, choose **...** in the upper right corner, and then choose the **Contains EUII** box. Choose **Update** to save your changes.

   ![Save your changes.](engagement-insights/media/update-property.png "Save your changes")

   > [!NOTE]
   > Every time the event schema changes or you create a new event, it's recommended that you evaluate the associated event properties and tag or untag them as containing personal data, if necessary.

#### Delete or export tagged event data

If all event properties have been tagged appropriately as described in the previous step, an environment admin can issue a deletion request against the tagged event data.

To manage EUII deletion or export requests

1. Go to **Admin** > **Environment** > **Settings**.

1. In the **Manage end user identifiable information (EUII)** section, select **Manage EUII**.

##### Deletion

For deletion, you can enter a list of comma-separated user IDs in the **Delete end user identifiable information (EUII)** section. These IDs will then be compared with all tagged event properties of all projects in the current environment via exact string matching. 

If a property value matches one of the provided IDs, the associated event will be permanently deleted. Due to the irreversibility of this action, you must confirm the deletion after selecting **Delete**.

##### Export

The export process is identical to the deletion process when it comes to defining event property values in the **Export end user identifiable information (EUII)** section. Additionally, you'll need to provide an **Azure blob storage URL** to specify the export destination. The Azure Blob URL must include a [Shared Access Signature (SAS)](/azure/storage/common/storage-sas-overview).

After selecting **Export**, all events of the current team that contain matching tagged properties will be exported in CSV format to the export destination.

### Good practices

* Try to avoid sending any events that contain personal data.
* If you need to send events containing EUII data, limit the number of events and event properties that contain EUII data. Ideally, limit yourself to one such event.
* Make sure that as few people as possible have access to the sent personal data.
* For events containing personal data, make sure that you set one property to emit a unique identifier that can easily be linked to a specific user (for example, a user ID). This makes it easier to segregate data and to export or delete the right data.
* Only tag one property per event as containing personal data. Ideally one that only contains a unique identifier.
* Do not tag properties containing verbose values (for example, an entire request body). Engagement insights capability uses exact string matching when deciding which events to delete or export. -->

[!INCLUDE[footer-include](includes/footer-banner.md)]