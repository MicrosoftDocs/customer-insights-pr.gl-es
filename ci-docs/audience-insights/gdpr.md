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
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Solicitudes de dereitos do titular dos datos (DSR) baixo RXPD

## <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a>Responder ás solicitudes de eliminación dos titulares dos datos segunco o RXPD para a capacidade de información do público de Dynamics 365 Customer Insights

O "dereito á eliminación" de datos persoais dos datos de clientes dunha organización é unha protección clave no Regulamento xeral de protección de datos (RXPD). A eliminación de datos persoais inclúe a eliminación de todos os datos persoais e os rexistros xerados polo sistema, excepto a información do rexistro de auditoría.

### <a name="manage-data-subject-delete-requests"></a>Xestionar as solicitudes de eliminación do titular dos datos

A información do público ofrece as seguintes experiencias internas para eliminar datos persoais dun cliente específico ou usuario:

- **Xestionar solicitudes de eliminación de datos de clientes**: os datos do cliente de Customer Insights son inxeridos de fontes de datos orixinais externas a Customer Insights. Todas as solicitudes de eliminación de RXPD deben realizarse na orixe de datos orixinal.
- **Xestionar solicitudes de eliminación de datos de usuario de Customer Insights**: Os datos dos usuarios son creados por Customer Insights. Todas as solicitudes de eliminación de RXPD deben realizarse en Customer Insights.

#### <a name="manage-delete-requests-for-customer-data"></a>Xestionar solicitudes de eliminación de datos de clientes

Un administrador de Customer Insights pode seguir estes pasos para eliminar os datos de clientes que se eliminaron na orixe de datos:

1. Inicie sesión en Dynamics 365 Customer Insights.
2. Na información do público, vaia a **Datos** > **Orixes de datos**
3. Para cada orixe de datos da lista que contén datos de clientes eliminados:
   1. Seleccione (...) e, a seguir, seleccione **Actualizar**.
   2. Consulte o estado da orixe de datos en **Estado**. A aparición dunha marca de verificación significa que a actualización tivo éxito. Un triángulo de aviso significa que algo saíu mal. Se aparece un triángulo de aviso, póñase en contacto con D365CI@microsoft.com.

> [!div class="mx-imgBorder"]
> ![Manipulación de solicitudes de eliminación de RXPD para datos de clientes](media/gdpr-data-sources.png "Manipulación de solicitudes de eliminación de RXPD para datos de clientes")

#### <a name="manage-delete-requests-for-user-data"></a>Xestionar solicitudes de eliminación de datos de usuario

Un administrador de Customer Insights pode seguir estes pasos para eliminar os datos de usuarios de Customer Insights:

1. Inicie sesión en Dynamics 365 Customer Insights.
2. Na información do público, vaia a **Administrar** > **Permisos**.
3. Marque a caixa de verificación do usuario que desexe eliminar.
4. Seleccione **Quitar**.

> [!div class="mx-imgBorder"]
> ![Xestionar solicitudes de eliminación segundo o RXPD para datos de usuario](media/gdpr-permissions.png "Xestionar solicitudes de eliminación segundo o RXPD para datos de usuario")

## <a name="responding-to-gdpr-data-subject-export-requests"></a>Responder a solicitudes de exportación de titulares dos datos segundo o RXPD

Como parte do noso compromiso de asociarnos con vostede na aplicación do Regulamento xeral de protección de datos (RXPD), elaboramos documentación para axudarlle a prepararse. Esta documentación describe os pasos que pode seguir hoxe para apoiar o cumprimento do RXPD cando se empregan as estatísticas do público.

### <a name="manage-export-and-view-requests"></a>Xestionar solicitudes de exportación e visualización

O dereito de portabilidade de datos permite a un titular solicitar unha copia dos seus datos persoais nun formato electrónico (definido como un "formato estruturado, utilizado comunmente, lexible por máquinas e interoperable") que pode ser transmitido a outro controlador de datos.

#### <a name="export-customer-data-tenant-admin"></a>Exportar datos de clientes (administrador de arrendatarios)

Un administrador de arrendatarios pode seguir estes pasos para exportar datos:

1. Envíe un correo electrónico a D365CI@microsoft.com especificando o enderezo de correo electrónico do cliente na solicitude. O equipo de Customer Insights enviará un correo electrónico ao enderezo de correo electrónico do administrador do arrendatario rexistrado e pedirá confirmación para exportar datos.
2. Recoñeza a confirmación para exportar os datos do cliente solicitado.
3. Reciba os datos exportados a través do enderezo de correo electrónico do administrador do arrendatario.

#### <a name="export-user-data-tenant-admin"></a>Exportar datos de usuario (administrador de arrendatarios)

1. Envíe un correo electrónico a D365CI@microsoft.com especificando o enderezo de correo electrónico do usuario na solicitude. O equipo de Customer Insights enviará un correo electrónico ao enderezo de correo electrónico do administrador do arrendatario rexistrado e pedirá confirmación para exportar datos.
2. Recoñeza a confirmación para exportar os datos do usuario solicitado.
3. Reciba os datos exportados a través do enderezo de correo electrónico do administrador do arrendatario.
