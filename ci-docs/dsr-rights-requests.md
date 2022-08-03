---
title: Solicitudes de dereitos do titular dos datos (DSR) baixo RXPD | Microsoft Docs
description: Responda ás solicitudes do titular dos datos para Dynamics 365 Customer Insights.
ms.date: 05/23/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 6c6ce49c18de3a09d28138316d893e6842919042
ms.sourcegitcommit: ff0f4b5664d995870c91adb87c7d3780a582efca
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 07/13/2022
ms.locfileid: "9146693"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Solicitudes de dereitos do titular dos datos (DSR) baixo RXPD

O Regulamento xeral de protección de datos (RXPD) da Unión Europea está en vigor desde o 25 de maio de 2018. Concédelles dereitos significativos ás persoas con respecto aos seus datos. O obxectivo do RXPD é protexer e activar os dereitos de privacidade das persoas. Atopará máis información sobre o compromiso de Microsoft coa seguranza e o cumprimento no [Centro de confianza de Microsoft](https://www.microsoft.com/trust-center).

Comprometémonos a axudar aos nosos clientes a cumprir os seus requisitos de RXPD. Inclúe o dereito a eliminar e exportar datos que inclúan información persoal, como os ID de usuario, números de teléfono e enderezos de correo electrónico. Os administradores poden implementar as solicitudes dos usuarios para eliminar ou exportar datos persoais.

## <a name="dynamics-365-customer-insights"></a>Dynamics 365 Customer Insights

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights"></a>Responder a solicitudes de eliminación de titulares dos datos RXPD para Dynamics 365 Customer Insights

O "dereito á eliminación" de datos persoais dos datos de clientes dunha organización é unha protección clave no Regulamento xeral de protección de datos (RXPD). A eliminación de datos persoais inclúe a eliminación de todos os datos persoais e os rexistros xerados polo sistema, excepto a información do rexistro de auditoría.

#### <a name="manage-data-subject-delete-requests"></a>Xestionar as solicitudes de eliminación do titular dos datos

Customer Insights ofrece as seguintes experiencias dentro do produto para eliminar datos persoais dun cliente ou usuario específico:

- **Xestionar solicitudes de eliminación de datos de clientes**: os datos do cliente de Customer Insights son inxeridos de fontes de datos orixinais externas a Customer Insights. Realiza primeiro solicitudes de eliminación do GDPR no orixe de datos orixinal.
- **Xestionar solicitudes de eliminación de datos de usuario de Customer Insights**: Os datos dos usuarios son creados por Customer Insights. Todas as solicitudes de eliminación de RXPD deben realizarse en Customer Insights.

##### <a name="manage-requests-to-delete-customer-data"></a>Xestionar solicitudes de eliminación de datos de clientes

Un administrador de Customer Insights pode seguir estes pasos para eliminar os datos de clientes que se eliminaron no orixe de datos. Asegúrate de que a solicitude de eliminación se realizou no teu orixe de datos antes de continuar cos pasos que se indican a continuación. 

1. Inicie sesión en Dynamics 365 Customer Insights.
1. Ir a **Datos** > **Fontes de datos**
1. Para cada orixe de datos da lista que contén datos de clientes eliminados:
   1. Seleccione os puntos suspensivos verticais (&vellip;) e, a continuación, seleccione **Actualizar**.
   1. Consulte o estado da orixe de datos en **Estado**. A aparición dunha marca de verificación significa que a actualización tivo éxito. Un triángulo de aviso significa que algo saíu mal. Se aparece un triángulo de aviso, póñase en contacto con D365CI@microsoft.com.
1. Despois dunha actualización correcta das fontes de datos, executa tamén as actualizacións posteriores. Especialmente, se non tes programada unha actualización completa periódica de Customer Insights. 

> [!IMPORTANT]
> Os segmentos estáticos non se inclúen nunha actualización completa nin se executan actualizacións posteriores despois dunha solicitude de eliminación. Para asegurarse de que tamén se eliminan os datos dos clientes dos segmentos estáticos, recree os segmentos estáticos cos datos de orixe actualizados.

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

### <a name="data-deletion-handling-in-dynamics-365-customer-insights"></a>Tratamento da eliminación de datos Dynamics 365 Customer Insights

1. Os datos eliminaranse (particións de datos e instantáneas de datos) se as particións de datos e as instantáneas de datos están inactivas durante máis de 30 días, o que significa que foron substituídas por unha nova partición e instantánea de datos mediante unha actualización das fontes de datos.
2. Non se eliminan todos os datos e as instantáneas. A partición de datos e a instantánea de datos máis recentes están activas por definición porque se usan en Customer Insights. Para os datos máis recentes, non importa se as fontes de datos non se actualizaron nos últimos 30 días.

[!INCLUDE [footer-include](includes/footer-banner.md)]
