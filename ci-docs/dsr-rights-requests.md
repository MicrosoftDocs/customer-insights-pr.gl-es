---
title: Solicitudes de dereitos do titular dos datos (DSR) baixo RXPD | Microsoft Docs
description: Responda ás solicitudes do titular dos datos para Dynamics 365 Customer Insights.
ms.date: 08/11/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: af2583295627f98e980adbca4f216b9c34c3cad8
ms.sourcegitcommit: bf65bc0a54cdab71680e658e1617bee7b2c2bb68
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 05/27/2022
ms.locfileid: "8808544"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Solicitudes de dereitos do titular dos datos (DSR) baixo RXPD

O Regulamento xeral de protección de datos (RXPD) da Unión Europea está en vigor desde o 25 de maio de 2018. Concédelles dereitos significativos ás persoas con respecto aos seus datos. O obxectivo do RXPD é protexer e activar os dereitos de privacidade das persoas. Atopará máis información sobre o compromiso de Microsoft coa seguranza e o cumprimento no [Centro de confianza de Microsoft](https://www.microsoft.com/trust-center).

Comprometémonos a axudar aos nosos clientes a cumprir os seus requisitos de RXPD. Inclúe o dereito a eliminar e exportar datos que inclúan información persoal, como os ID de usuario, números de teléfono e enderezos de correo electrónico. Os administradores poden implementar as solicitudes dos usuarios para eliminar ou exportar datos persoais.

## <a name="dynamics-365-customer-insights"></a>Dynamics 365 Customer Insights

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights"></a>Responder a solicitudes de eliminación de titulares dos datos RXPD para Dynamics 365 Customer Insights

O "dereito á eliminación" de datos persoais dos datos de clientes dunha organización é unha protección clave no Regulamento xeral de protección de datos (RXPD). A eliminación de datos persoais inclúe a eliminación de todos os datos persoais e os rexistros xerados polo sistema, excepto a información do rexistro de auditoría.

#### <a name="manage-data-subject-delete-requests"></a>Xestionar as solicitudes de eliminación do titular dos datos

Customer Insights ofrece as seguintes experiencias dentro do produto para eliminar datos persoais dun cliente ou usuario específico:

- **Xestionar solicitudes de eliminación de datos de clientes**: os datos do cliente de Customer Insights son inxeridos de fontes de datos orixinais externas a Customer Insights. Todas as solicitudes de eliminación de RXPD deben realizarse na orixe de datos orixinal.
- **Xestionar solicitudes de eliminación de datos de usuario de Customer Insights**: Os datos dos usuarios son creados por Customer Insights. Todas as solicitudes de eliminación de RXPD deben realizarse en Customer Insights.

##### <a name="manage-requests-to-delete-customer-data"></a>Xestionar solicitudes de eliminación de datos de clientes

Un administrador de Customer Insights pode seguir estes pasos para eliminar os datos de clientes que se eliminaron na orixe de datos:

1. Inicie sesión en Dynamics 365 Customer Insights.
2. Ir a **Datos** > **Fontes de datos**
3. Para cada orixe de datos da lista que contén datos de clientes eliminados:
   1. Seleccione os puntos suspensivos verticais (&vellip;) e, a continuación, seleccione **Actualizar**.
   2. Consulte o estado da orixe de datos en **Estado**. A aparición dunha marca de verificación significa que a actualización tivo éxito. Un triángulo de aviso significa que algo saíu mal. Se aparece un triángulo de aviso, póñase en contacto con D365CI@microsoft.com.

> [!div class="mx-imgBorder"]
> ![Manipulación de solicitudes de eliminación de RXPD para datos de clientes.](media/gdpr-data-sources.png "Manipulación de solicitudes de eliminación de RXPD para datos de clientes")

##### <a name="manage-delete-requests-for-user-data"></a>Xestionar solicitudes de eliminación de datos de usuario

Un administrador de Customer Insights pode seguir estes pasos para eliminar os datos de usuarios de Customer Insights:

1. Inicie sesión en Dynamics 365 Customer Insights.
2. Ir a **Admin** > **Seguridade** > **Permisos**.
3. Marque a caixa de verificación do usuario que desexe eliminar.
4. Seleccione **Quitar**.

### <a name="responding-to-gdpr-data-subject-export-requests"></a>Responder a solicitudes de exportación de titulares dos datos segundo o RXPD

Como parte do noso compromiso de colaborar contigo na túa viaxe ao Regulamento Xeral de Protección de Datos (GDPR), elaboramos documentación para axudarche a responder ás solicitudes dos interesados.

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

Para eliminar os datos de consentimento de usuarios específicos, elimínaos das fontes de datos inxeridas coa capacidade de xestión de consentimento. Despois de actualizar o orixe de datos, os datos eliminados tamén se eliminarán no Centro de consentimento. As aplicacións que usan a entidade de consentimento tamén eliminarán os datos que se eliminaron da fonte despois de a [refrescar](system.md#refresh-processes). Recomendamos actualizar as fontes de datos rapidamente despois de responder a unha solicitude do suxeito de datos para eliminar os datos do usuario de todos os demais procesos e aplicacións.

[!INCLUDE [footer-include](includes/footer-banner.md)]