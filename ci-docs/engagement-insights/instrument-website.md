---
title: Engadir código a un sitio web
description: Como engadir un fragmento de código para capturar eventos no seu sitio web.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 04/30/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: b5467da775a621c436bd9ddedb272506acc1e2b31dcf7c87feb5dd11e2daae2b
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035092"
---
# <a name="install-the-code-snippet-on-a-website"></a>Instalar o fragmento de código nun sitio web

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Este artigo describe a forma na que un administrador instala o fragmento de código nun sitio web. Comezará a ver eventos na súa área de traballo pouco despois de engadir o script no sitio web. Para obter máis información, consulte [Xestión de áreas de traballo e ambientes](manage-environments-workspaces.md). Para capturar eventos en aplicacións móbiles, consulte [Descrición xeral dos recursos para programadores](developer-resources.md).


### <a name="prerequisites"></a>Requisitos previos

* Debe ter permisos de administrador na área de traballo para almacenar os datos.
* O seu sitio web ou proxecto debe estar aloxado en liña para enviar datos de actividade. O servidor non aceptará datos enviados desde un ficheiro local.


## <a name="add-code-to-your-website"></a>Engadir código a un sitio web
1.  Vaia a **Administración** > **Área de traballo** e logo seleccione **Guía de instalación**.
1. Seleccione **Copiar código** para copiar o fragmento de código. Por defecto, a clave de inxestión da súa área de traballo está incorporada no fragmento de código.
:::image type="content" source="media/copy-code.png" alt-text="Captura de pantalla da páxina do fragmento de código.":::
3. Engada o fragmento de código copiado ao seu sitio web, preto da <head> etiqueta e antes de calquera outra etiqueta de CSS ou script.
4.  Publique o sitio web actualizado e agarde uns minutos para capturar o tráfico web entrante.
5.  Para ver os seus datos, seleccione a área de traballo no conmutador de áreas de traballo no panel de navegación. A continuación, seleccione un dos informes na sección **Descubrir**.

## <a name="configuration-options"></a>Opcións de configuración

Pode cambiar as seguintes opcións de configuración no fragmento de código:

- **ingestionKey** : a clave de inxestión empregada para enviar eventos á súa área de traballo. Pode cambiar a clave de inxestión para enviar eventos a unha área de traballo diferente. Unha clave de inxestión é exclusiva de cada área de traballo. 
- **autoCapture** : especifica se se capturan as visualizacións das páxinas e as interaccións co sitio web. Ten dúas opcións:
    - **view**: definido como *true* para capturar as visualizacións das páxinas. As visualizacións das páxinas captúranse como [eventos](glossary.md#event) de *visualización*, un tipo de [evento base](glossary.md#base-event).
    - **click** : definido como *true* para capturar as interaccións dos visitantes no sitio web. As interaccións captúranse como [eventos](glossary.md#event) de *acción*, un tipo de [evento base](glossary.md#base-event).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
