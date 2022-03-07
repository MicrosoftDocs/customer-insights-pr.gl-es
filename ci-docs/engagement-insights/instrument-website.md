---
title: Engadir código a un sitio web
description: Como engadir un fragmento de código para capturar eventos de Dynamics 365 Customer Insights no seu sitio web.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 09/27/2021
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 99e1c04877993a9cd81912e3d400402aab06a7de
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 02/16/2022
ms.locfileid: "8231020"
---
# <a name="install-the-web-sdk-on-a-website"></a>Instalar o SDK web nun sitio web

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Este artigo describe como un administrador instala o kit de ferramentas de desenvolvemento de software web (SDK) nun sitio web. Comezará a ver eventos no seu espazo de traballo pouco despois de instrumentar o seu sitio web. Para obter máis información, consulte [Xestión de áreas de traballo e ambientes](manage-environments-workspaces.md). Para capturar eventos en aplicacións móbiles, consulte [Descrición xeral dos recursos para programadores](developer-resources.md).


### <a name="prerequisites"></a>Requisitos previos

* Debe ter permisos de administrador na área de traballo para almacenar os datos.
* O seu sitio web ou proxecto debe estar aloxado en liña para enviar datos de actividade. O servidor non aceptará datos enviados desde un ficheiro local.


## <a name="add-web-sdk-to-your-website"></a>Engadir un SDK web ao seu sitio web

Vaia a **Administración** > **Área de traballo** e logo seleccione **Guía de instalación**. Hai dúas opcións para instalar o SDK web. O primeiro é usar unha ligazón de descarga e o segundo é instalar un paquete de xestor de paquetes de nós (NPM).

### <a name="option-1-using-the-download-link"></a>Opción 1. Uso da ligazón de descarga

1. Seleccione **Copiar código** para copiar o fragmento de código. Por defecto, a clave de inxestión da súa área de traballo está incorporada no fragmento de código.
  :::image type="content" source="media/copy-code.png" alt-text="Captura de pantalla da páxina do fragmento de código.":::

1. Engada o código copiado ao seu sitio web, preto da <head> etiqueta e antes de calquera outra etiqueta de CSS ou script.
1. Publique o sitio web actualizado e agarde uns minutos para capturar o tráfico web entrante.
1. Para ver os seus datos, seleccione a área de traballo no conmutador de áreas de traballo no panel de navegación. A continuación, seleccione un dos informes na sección **Descubrir**.

### <a name="option-2-using-the-npm-package-recommended-for-javascript-based-web-apps"></a>Opción 2: usar o paquete NPM (recomendado para aplicacións web baseadas en JavaScript)

1. Vaia á nosa [páxina web de NPM](https://www.npmjs.com/package/engagementinsights-web) e siga as instrucións para instalar e configurar o paquete web SDK NPM.
1. Publique o sitio web actualizado e agarde uns minutos para capturar o tráfico web entrante.
1. Para ver os seus datos, seleccione a área de traballo no conmutador de áreas de traballo no panel de navegación. A continuación, seleccione un dos informes na sección **Descubrir**.

## <a name="configuration-options"></a>Opcións de configuración

Pode cambiar as seguintes opcións de configuración no fragmento de código:

- **ingestionKey** : a clave de inxestión empregada para enviar eventos á súa área de traballo. Pode cambiar a clave de inxestión para enviar eventos a unha área de traballo diferente. Unha clave de inxestión é exclusiva de cada área de traballo.
- **autoCapture** : especifica se se capturan as visualizacións das páxinas e as interaccións co sitio web. Ten dúas opcións:
    - **view**: definido como *true* para capturar as visualizacións das páxinas. As visualizacións das páxinas captúranse como [eventos](glossary.md#event) de *visualización*, un tipo de [evento base](glossary.md#base-event).
    - **click** : definido como *true* para capturar as interaccións dos visitantes no sitio web. As interaccións captúranse como [eventos](glossary.md#event) de *acción*, un tipo de [evento base](glossary.md#base-event).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
