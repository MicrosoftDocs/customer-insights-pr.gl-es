---
title: Solicitudes de dereitos do titular dos datos (DSR) baixo RXPD | Microsoft Docs
description: Responde ás solicitudes dos suxeitos de datos para a capacidade de información sobre o público Dynamics 365 Customer Insights.
ms.date: 08/11/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: c116f7ce208c0288851a4b2230e27784ba3a5337
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 11/02/2021
ms.locfileid: "7732678"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Solicitudes de dereitos do titular dos datos (DSR) baixo RXPD

O Regulamento xeral de protección de datos (RXPD) da Unión Europea está en vigor desde o 25 de maio de 2018. Concédelles dereitos significativos ás persoas con respecto aos seus datos. O obxectivo do RXPD é protexer e activar os dereitos de privacidade das persoas. Atopará máis información sobre o compromiso de Microsoft coa seguranza e o cumprimento no [Centro de confianza de Microsoft](https://www.microsoft.com/trust-center).

Comprometémonos a axudar aos nosos clientes a cumprir os seus requisitos de RXPD. Inclúe o dereito a eliminar e exportar datos que inclúan información persoal, como os ID de usuario, números de teléfono e enderezos de correo electrónico. Os administradores poden implementar as solicitudes dos usuarios para eliminar ou exportar datos persoais.

## <a name="audience-insights"></a>Información do público

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a>Respondendo ás solicitudes de eliminación do suxeito de datos do GDPR para a capacidade de información da audiencia Dynamics 365 Customer Insights

O "dereito á eliminación" de datos persoais dos datos de clientes dunha organización é unha protección clave no Regulamento xeral de protección de datos (RXPD). A eliminación de datos persoais inclúe a eliminación de todos os datos persoais e os rexistros xerados polo sistema, excepto a información do rexistro de auditoría.

#### <a name="manage-data-subject-delete-requests"></a>Xestionar as solicitudes de eliminación do titular dos datos

A información do público ofrece as seguintes experiencias internas para eliminar datos persoais dun cliente específico ou usuario:

- **Xestionar solicitudes de eliminación de datos de clientes**: os datos do cliente de Customer Insights son inxeridos de fontes de datos orixinais externas a Customer Insights. Todas as solicitudes de eliminación de RXPD deben realizarse na orixe de datos orixinal.
- **Xestionar solicitudes de eliminación de datos de usuario de Customer Insights**: Os datos dos usuarios son creados por Customer Insights. Todas as solicitudes de eliminación de RXPD deben realizarse en Customer Insights.

##### <a name="manage-requests-to-delete-customer-data"></a>Xestionar solicitudes de eliminación de datos de clientes

Un administrador de Customer Insights pode seguir estes pasos para eliminar os datos de clientes que se eliminaron na orixe de datos:

1. Inicia sesión en Dynamics 365 Customer Insights.
2. Na información do público, vaia a **Datos** > **Orixes de datos**
3. Para cada orixe de datos da lista que contén datos de clientes eliminados:
   1. Seleccione (...) e, a seguir, seleccione **Actualizar**.
   2. Consulte o estado da orixe de datos en **Estado**. A aparición dunha marca de verificación significa que a actualización tivo éxito. Un triángulo de aviso significa que algo saíu mal. Se aparece un triángulo de aviso, póñase en contacto con D365CI@microsoft.com.

> [!div class="mx-imgBorder"]
> ![Manipulación de solicitudes de eliminación de RXPD para datos de clientes.](audience-insights/media/gdpr-data-sources.png "Manipulación de solicitudes de eliminación de RXPD para datos de clientes")

##### <a name="manage-delete-requests-for-user-data"></a>Xestionar solicitudes de eliminación de datos de usuario

Un administrador de Customer Insights pode seguir estes pasos para eliminar os datos de usuarios de Customer Insights:

1. Inicia sesión en Dynamics 365 Customer Insights.
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

Para eliminar os datos de consentimento de usuarios específicos, elimínaos das fontes de datos inxeridas coa capacidade de xestión de consentimento. Despois de actualizar o orixe de datos, os datos eliminados tamén se eliminarán no Centro de consentimento. As aplicacións que usan a entidade de consentimento tamén eliminarán os datos que se eliminaron da fonte despois de a [refrescar](audience-insights/system.md#refresh-processes). Recomendamos actualizar as fontes de datos rapidamente despois de responder a unha solicitude do suxeito de datos para eliminar os datos do usuario de todos os demais procesos e aplicacións.


## <a name="engagement-insights-preview"></a>Información de interacción (versión preliminar)

### <a name="deleting-and-exporting-event-data-containing-end-user-identifiable-information"></a>Eliminación e exportación de datos de eventos que conteñan información de identificación do usuario final

As seguintes seccións describen como eliminar e exportar datos de eventos que poidan conter datos persoais.

Para eliminar ou exportar datos:

1. Etiquete as propiedades do evento que conteñan datos con información persoal.
2. Elimine ou exporte os datos asociados a valores específicos (por exemplo: un ID de usuario especificado).

#### <a name="tag-and-update-event-properties"></a>Etiquetar e actualizar as propiedades dun evento

Os datos persoais están etiquetados nun nivel de propiedades de evento. En primeiro lugar, etiquete as propiedades que preveña eliminar ou exportar.

Para etiquetar unha propiedade de evento como contedora de información persoal, siga estes pasos:

1. Abra a área de traballo que contén o evento.

1. Vaia a **Datos** > **Eventos** para ver a lista de eventos na área de traballo seleccionada.
  
1. Seleccione o evento que quere etiquetar.

1. Seleccione **Editar propiedades** para abrir o panel onde aparecen todas as propiedades do evento seleccionado.
     
1. Seleccione **...** e escolla **Editar** para chegar ao diálogo **Actualizar propiedade**.

   ![Editar evento.](engagement-insights/media/edit-event.png "Editar evento")

1. Na ventá **Actualizar propiedade**, escolla **...** na esquina superior dereita e logo elixa a caixa **Contén EUII**. Escolla **Actualizar** para gardar as modificacións.

   ![Garde as modificacións.](engagement-insights/media/update-property.png "Gardar as modificacións")

   > [!NOTE]
   > Cada vez que o esquema de eventos se modifica ou crea un evento novo, recoméndase que avalíe as propiedades do evento asociadas e que as etiquete ou desetiquete como contedoras de datos persoais se é necesario.

#### <a name="delete-or-export-tagged-event-data"></a>Eliminar ou exportar datos de eventos etiquetados

Se todas as propiedades do evento se etiquetaron correctamente como se describe no paso anterior, un administrador de ambientes pode emitir unha solicitude de eliminación contra os datos do evento etiquetados.

Para xestionar as solicitudes de eliminación ou exportación de información de identificación do usuario final:

1. Vaia a **Administración** > **Ambiente** > **Configuración**.

1. Na sección de **xestión da información de identificación do usuario final (EUII)**, seleccione **Xestionar EUII**.

##### <a name="deletion"></a>Eliminación

Para a eliminación, pode inserir unha lista de ID de usuario separados por comas na sección de **eliminación da información de identificación do usuario final (EUII)**. Estes ID compararanse con todas as propiedades de eventos etiquetadas de todos os proxectos do ambiente actual con coincidencias de cadeas exactas. 

Se un valor dunha propiedade coincide cun dos ID proporcionados, o evento asociado eliminarase permanentemente. Debido á irreversibilidade desta acción, debe confirmar a eliminación despois de seleccionar **Eliminar**.

##### <a name="export"></a>Export

O proceso de exportación é idéntico ao de eliminación á hora de definir os valores das propiedades do evento na sección de **exportación da información de identificación do usuario final (EUII)**. Ademais, terá que proporcionar un **URL de Azure Blob Storage** para especificar o destino de exportación. O URL do BLOB de Azure debe incluír unha [sinatura de acceso compartido (SAS)](/azure/storage/common/storage-sas-overview).

Despois de seleccionar **Exportar**, todos os eventos do equipo actual que conteñan propiedades etiquetadas coincidentes exportaranse en formato CSV ao destino de exportación.

### <a name="good-practices"></a>Recomendacións

* Tente evitar o envío de eventos que conteñan datos persoais.
* Se precisa enviar eventos que conteñan información de identificación do usuario final (EUII), limite o número de eventos e propiedades de eventos que a conteñan. O ideal é limitarse a un destes eventos.
* Asegúrese de que o menor número posible de persoas teña acceso aos datos persoais enviados.
* Para eventos que conteñan datos persoais, asegúrese de definir unha propiedade para que emita un identificador único que poida ligarse facilmente a un usuario específico (por exemplo, un ID de usuario). Isto facilita a segregación de datos e a exportación ou eliminación dos datos adecuados.
* Etiquete só unha propiedade por evento como contedora de datos persoais. O ideal é que sexa unha que só conteña un identificador único.
* Non etiquete as propiedades que conteñan valores detallados (por exemplo, un corpo de solicitude completo). A capacidade de información de interacción emprega coincidencias de cadeas exactas ao decidir que eventos eliminar ou exportar.

[!INCLUDE[footer-include](includes/footer-banner.md)]