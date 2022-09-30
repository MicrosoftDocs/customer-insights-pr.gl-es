---
title: Xestionar ambientes
description: Aprende a xestionar os contornos de Customer Insights existentes como administrador.
ms.date: 08/15/2022
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-about
- customerInsights
ms.openlocfilehash: 6d48f7088d722b27ca69cd591178651bdb6e2c23
ms.sourcegitcommit: f959c85871777e5f4eab289e91b2fd114cd72153
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 09/23/2022
ms.locfileid: "9588810"
---
# <a name="manage-environments"></a>Xestionar ambientes

Administradores [crear](create-environment.md) e xestionar ambientes. Poden cambiar algunhas opcións de configuración en ambientes existentes. Negocio, tipo, rexión, opción de almacenamento e Dataverse a configuración arranxouse despois de crear o ambiente. Se queres cambiar esta configuración, [restablecer o ambiente](#reset-an-existing-environment-preview) ou [crear un novo ambiente](create-environment.md).

## <a name="edit-an-existing-environment"></a>Editar un ambiente existente

Edite os detalles dun ambiente existente, como o nome ou a configuración predeterminada.

1. Seleccione o selector de **ambiente** na cabeceira da aplicación.

1. Seleccione a icona de **edición**.

   :::image type="content" source="media/edit-environment.png" alt-text="Icona para editar a configuración do contorno.":::

1. No **Editar entorno** panel, actualice a configuración do entorno.

1. Seleccione **Revisa e remata**, entón **Actualizar** para aplicar os cambios.

## <a name="change-the-owner-of-an-environment"></a>Cambiar o propietario dun ambiente

Varios usuarios poden ter permisos de administrador, pero só un usuario é o propietario dun ambiente. Por defecto, é o administrador quen crea un ambiente inicialmente. Como administrador dun ambiente, pode asignarlle a propiedade a outro usuario con permisos de administrador.

1. Seleccione o selector de **ambiente** na cabeceira da aplicación.

1. Seleccione a icona de **edición**.

1. No **Editar entorno** panel, vai ao **Información básica** paso.

1. No **Cambiar propietario do entorno** campo, escolla o novo propietario do entorno.  

1. Seleccione **Revisa e remata**, entón **Actualizar** para aplicar os cambios.

## <a name="claim-ownership-of-an-environment"></a>Reivindicar a propiedade dun contorno

Se se elimina ou se suspende a conta de usuario do propietario, o ambiente non terá propietario. Calquera usuario administrador pode reclamar a propiedade e converterse no novo propietario. O administrador propietario pode seguir sendo o propietario do entorno ou [cambiar a propiedade a outro administrador](#change-the-owner-of-an-environment).

Para reclamar a propiedade, selecciona **Tomar propiedade** botón que se mostra na parte superior de cada páxina en Customer Insights cando o propietario orixinal deixou a organización.

## <a name="reset-an-existing-environment-preview"></a>Restablecer un ambiente existente (vista previa)

Como propietario dun ambiente, restablece un ambiente a un estado baleiro se queres eliminar todas as configuracións e eliminar os datos inxeridos.

1. Seleccione o selector de **ambiente** na cabeceira da aplicación.

1. Seleccione o ambiente que quere restablecer e seleccione os puntos suspensivos verticais (&vellip;).

1. Escolle **Restablecer (vista previa)**.

   :::image type="content" source="media/reset-environment.png" alt-text="Control para restablecer un ambiente.":::

1. Escolla se quere restablecer todo o ambiente, todo excepto as fontes de datos ou calquera cousa que estea configurada enriba do perfil de cliente unificado.

1. Para confirmar, introduza o nome do entorno e seleccione **Restablecer**.

## <a name="delete-an-existing-environment"></a>Eliminar un ambiente existente

Como propietario dun ambiente, podes eliminalo.

> [!IMPORTANT]
> A eliminación dun ambiente non elimina a conexión a un Dataverse ambiente. Se pensas conectar o mesmo Dataverse a un novo ambiente de Customer Insights no futuro, debes [eliminar esa conexión ao Dataverse ambiente](customer-insights-dataverse.md#remove-an-existing-connection-to-a-dataverse-environment).

1. Seleccione o selector de **ambiente** na cabeceira da aplicación.

1. Seleccione o ambiente que quere eliminar e seleccione os puntos suspensivos verticais (&vellip;). 

1. Escolle **Eliminar**.

   :::image type="content" source="media/delete-environment.png" alt-text="Control para eliminar o ambiente.":::

1. Para confirmar a eliminación, insira o nome do ambiente e seleccione **Eliminar**.

[!INCLUDE [footer-include](includes/footer-banner.md)]
