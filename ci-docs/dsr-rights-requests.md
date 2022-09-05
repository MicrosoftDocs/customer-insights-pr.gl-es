---
title: Solicitudes de dereitos do titular dos datos (DSR) baixo RXPD | Microsoft Docs
description: Responda ás solicitudes do titular dos datos para Dynamics 365 Customer Insights.
ms.date: 08/31/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 49251fb46957c4d7ec205b93c9547a3cd380eb11
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387109"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Solicitudes de dereitos do titular dos datos (DSR) baixo RXPD

O Regulamento xeral de protección de datos (RXPD) da Unión Europea está en vigor desde o 25 de maio de 2018. Concédelles dereitos significativos ás persoas con respecto aos seus datos. O obxectivo do RXPD é protexer e activar os dereitos de privacidade das persoas. Lea máis sobre o compromiso de Microsoft coa seguridade e o cumprimento en [Centro de confianza de Microsoft](https://www.microsoft.com/trust-center).

Comprometémonos a axudar aos nosos clientes a cumprir os seus requisitos de RXPD. Inclúe o dereito a eliminar ou exportar datos que inclúan información persoal como ID de usuario, números de teléfono e enderezos de correo electrónico. Os administradores poden implementar as solicitudes dos usuarios para eliminar ou exportar datos persoais.

## <a name="responding-to-gdpr-data-subject-delete-requests-for-customer-insights"></a>Respondendo ás solicitudes de eliminación do suxeito de datos do GDPR para Customer Insights

O "dereito á eliminación" de datos persoais dos datos de clientes dunha organización é unha protección clave no Regulamento xeral de protección de datos (RXPD). A eliminación de datos persoais inclúe a eliminación de todos os datos persoais e os rexistros xerados polo sistema, excepto a información do rexistro de auditoría.

### <a name="manage-data-subject-delete-requests"></a>Xestionar as solicitudes de eliminación do titular dos datos

Customer Insights ofrece as seguintes experiencias dentro do produto para eliminar datos persoais dun cliente ou usuario específico:

- **Xestionar solicitudes de eliminación de datos de clientes**: os datos do cliente de Customer Insights son inxeridos de fontes de datos orixinais externas a Customer Insights. Realiza primeiro solicitudes de eliminación do GDPR no orixe de datos orixinal.
- **Xestionar solicitudes de eliminación de datos de usuario de Customer Insights**: Os datos dos usuarios son creados por Customer Insights. Realiza todas as solicitudes de eliminación do GDPR en Customer Insights.

#### <a name="manage-requests-to-delete-customer-data"></a>Xestionar solicitudes de eliminación de datos de clientes

Como administrador de Customer Insights, elimina os datos de clientes de Customer Insights que se eliminaron no orixe de datos. Verifique que as solicitudes de eliminación do GDPR se realizaron no orixe de datos orixinal.

1. Inicie sesión en Dynamics 365 Customer Insights.

1. Vaia a **Datos** > **Orixes de datos**.

1. Para cada orixe de datos da lista que contén datos de clientes eliminados:
   1. Seleccione orixe de datos e, a continuación, seleccione **Actualizar**.
   1. Consulte o estado da orixe de datos en **Estado**. A aparición dunha marca de verificación significa que a actualización tivo éxito. Un triángulo de aviso significa que algo saíu mal. Se aparece un triángulo de aviso, póñase en contacto con D365CI@microsoft.com.

   :::image type="content" source="media/gdpr-data-sources.png" alt-text="Manipulación de solicitudes de eliminación de RXPD para datos de clientes.":::

1. Despois dunha actualización correcta das fontes de datos, executa tamén as actualizacións posteriores. Especialmente, se non tes programada unha actualización completa periódica de Customer Insights.

   > [!IMPORTANT]
   > Os segmentos estáticos non se inclúen nunha actualización completa nin se executan actualizacións posteriores despois dunha solicitude de eliminación. Para asegurarse de que tamén se eliminan os datos dos clientes dos segmentos estáticos, recree os segmentos estáticos cos datos de orixe actualizados.

#### <a name="manage-delete-requests-for-user-data"></a>Xestionar solicitudes de eliminación de datos de usuario

Como administrador de Customer Insights, elimina os datos do usuario de Customer Insights.

1. Inicie sesión en Dynamics 365 Customer Insights.

1. Ir a **Admin** > **Seguridade** > e seleccione **Usuarios** ficha.

1. Seleccione a caixa de verificación dos usuarios que quere eliminar.

1. Seleccione **Quitar**.

1. Confirme a eliminación.

## <a name="responding-to-gdpr-data-subject-export-requests"></a>Responder a solicitudes de exportación de titulares dos datos segundo o RXPD

O dereito de portabilidade de datos permite a un titular solicitar unha copia dos seus datos persoais nun formato electrónico (definido como un "formato estruturado, utilizado comunmente, lexible por máquinas e interoperable") que pode ser transmitido a outro controlador de datos.

### <a name="manage-export-and-view-requests"></a>Xestionar solicitudes de exportación e visualización

Xestiona solicitudes de exportación de datos de clientes ou usuarios.

#### <a name="export-customer-data-tenant-admin"></a>Exportar datos de clientes (administrador de arrendatarios)

Como administrador de inquilinos, exporta os datos do cliente.

1. Envíe un correo electrónico a D365CI@microsoft.com especificando o enderezo de correo electrónico do cliente na solicitude. O equipo de Customer Insights enviará un correo electrónico ao enderezo de correo electrónico do administrador do arrendatario rexistrado e pedirá confirmación para exportar datos.
2. Recoñeza a confirmación para exportar os datos do cliente solicitado.
3. Reciba os datos exportados a través do enderezo de correo electrónico do administrador do arrendatario.

#### <a name="export-user-data-tenant-admin"></a>Exportar datos de usuario (administrador de arrendatarios)

Como administrador de inquilinos, exporte os datos do usuario.

1. Envíe un correo electrónico a D365CI@microsoft.com especificando o enderezo de correo electrónico do usuario na solicitude. O equipo de Customer Insights envía un correo electrónico ao enderezo de correo electrónico do administrador do inquilino rexistrado, solicitando confirmación para exportar datos.
1. Recoñeza a confirmación para exportar os datos do usuario solicitado.
1. Reciba os datos exportados a través do enderezo de correo electrónico do administrador do arrendatario.

## <a name="data-deletion-handling-in-dynamics-365-customer-insights"></a>Tratamento da eliminación de datos Dynamics 365 Customer Insights

Os datos elimínanse (particións de datos e instantáneas de datos) se as particións de datos e as instantáneas de datos están inactivas durante máis de 30 días, o que significa que foron substituídas por unha nova partición e instantánea de datos mediante unha actualización das fontes de datos.

Non se eliminan todos os datos e as instantáneas. A partición de datos e a instantánea de datos máis recentes están activas porque se utilizan en Customer Insights. Para os datos máis recentes, non importa se as fontes de datos non se actualizaron nos últimos 30 días.

[!INCLUDE [footer-include](includes/footer-banner.md)]
