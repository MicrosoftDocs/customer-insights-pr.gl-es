---
title: Conectar os datos de Common Data Model a unha conta de Azure Data Lake
description: Traballe con datos de Common Data Model usando Azure Data Lake Storage.
ms.date: 05/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 93871f8029053d4ed4a116d3af3550b7684ee11ea8633e937138245e193a44e6
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033124"
---
# <a name="connect-to-a-common-data-model-folder-using-an-azure-data-lake-account"></a>Conectar cun cartafol de Common Data Model cunha conta de Azure Data Lake

Este artigo ofrece información sobre como inxerir datos desde un cartafol de Common Data Model usando a súa conta de Azure Data Lake Storage Gen2.

## <a name="important-considerations"></a>Consideracións importantes

- Os datos do seu Azure Data Lake deben seguir o estándar do modelo de datos comúns. De momento non se admiten outros formatos.

- A inxestión de datos admite contas de almacentamento de Azure Data Lake *Gen2* exclusivamente. Non pode usar as contas de almacenamento de Azure Data Lake Gen1 para inxerir datos.

- Para autenticarse cunha entidade de seguranza do servizo de Azure, asegúrese de que está configurada no seu inquilino. Para obter máis información, consulte [Conectar información do público a unha conta de Azure Data Lake Storage Gen2 cunha entidade principal de seguranza do servizo de Azure](connect-service-principal.md).

- O Azure Data Lake que desexa conectar e do que inxerir datos ten que estar na mesma rexión de Azure que o ambiente de Dynamics 365 Customer Insights. Non se admiten conexións a un cartafol de Common Data Model desde un lago de datos nunha rexión de Azure diferente. Para coñecer a rexión de Azure do entorno, vaia a **Administrar** > **Sistema** > **Acerca de** na información do público.

- Os datos almacenados en servizos en liña pódense almacenar nun lugar diferente a onde se procesan ou almacenan os datos en Dynamics 365 Customer Insights. Ao importar ou conectarse a datos almacenados en servizos en liña, acepta que os datos poden ser transferidos a e almacenados con Dynamics 365 Customer Insights. [Obteña máis información no Centro de confianza de Microsoft.](https://www.microsoft.com/trust-center)

## <a name="connect-to-a-common-data-model-folder"></a>Conectarse a un cartafol de Common Data Model

1. Na información do público, vaia a **Datos** > **Orixes de datos**.

1. Seleccione **Engadir orixe de datos**.

1. Seleccione **Conectarse a un cartafol de Common Data Model**, introduza un **Nome** para a orixe de datos e seleccione **Seguinte**. Dea nome ás instrucións: 
   - Comece por unha letra.
   - Use só letras e números. Non se permiten caracteres especiais nin espazos.
   - Empregue entre 3 e 64 caracteres.

1. Pode escoller entre usar unha opción baseada en recursos e unha opción baseada na subscrición para a autenticación. Para obter máis información, consulte [Conectar información do público a unha conta de Azure Data Lake Storage Gen2 cunha entidade principal de seguranza do servizo de Azure](connect-service-principal.md). Introduza a información do **contedor** e seleccione **Seguinte**.
   > [!div class="mx-imgBorder"]
   > ![Cadro de diálogo para introducir novos detalles de conexión para Azure Data Lake.](media/enter-new-storage-details.png)
   > [!NOTE]
   > Precisa unha das seguintes funcións no contedor ou na conta de almacenamento mencionada anteriormente para poder conectarse e crear unha orixe de datos:
   >  - Lector de datos do BLOB de almacenamento
   >  - Propietario dos datos do BLOB de almacenamento
   >  - Colaborador de datos do BLOB de almacenamento

1. No diálogo **Seleccionar un cartafol de Common Data Model**, seleccione o ficheiro model.json ou manifest.json desde o que importar datos e seleccione **Seguinte**.
   > [!NOTE]
   > Calquera ficheiro model.json ou manifest.json asociado a outra orixe de datos do contorno non aparecerá na lista.

1. Obterá unha lista de entidades dispoñibles no ficheiro model.json ou manifest.json seleccionado. Pode revisar e seleccionar na lista de entidades dispoñibles e seleccionar **Gardar**. Todas as entidades seleccionadas inxeriranse a partir da orixe de datos nova.
   > [!div class="mx-imgBorder"]
   > ![Caixa de diálogo que mostra unha lista de entidades dun ficheiro model.json.](media/review-entities.png)

8. Indique que entidades de datos quere para activar a creación de perfís de datos e seleccione **Gardar**. A creación de perfís de datos activa as análises e outras funcionalidades. Pode seleccionar a entidade enteira, que selecciona todos os atributos da entidade, ou seleccionar certos atributos que elixa. Por defecto, ningunha entidade está habilitada para a creación de perfís de datos.
   > [!div class="mx-imgBorder"]
   > ![Cadro de diálogo que mostra a creación de perfís de datos.](media/dataprofiling-entities.png)

9. Despois de gardar as súas seleccións, abrirase a páxina **Fontes de datos**. Agora debe ver a conexión do cartafol Common Data Model como orixe de datos.

> [!NOTE]
> Un ficheiro model.json ou manifest.json só pode asociarse cunha orixe de datos no mesmo ambiente. Non obstante, o mesmo ficheiro model.json ou manifest.json pode usarse para fontes de datos en múltiples contornos.

## <a name="edit-a-common-data-model-folder-data-source"></a>Editar unha orixe de datos do cartafol de Common Data Model

Pode actualizar a clave de acceso da conta de almacenamento que contén o cartafol de Common Data Model. Tamén pode cambiar o ficheiro model.json ou manifest.json. Para conectarse a un contedor diferente da súa conta de almacenamento ou cambiar o nome da conta, [cree unha nova conexión de orixe de datos](#connect-to-a-common-data-model-folder).

1. Na información do público, vaia a **Datos** > **Orixes de datos**.

2. A carón da orixe de datos que desexa actualizar, seleccione os tres puntos.

3. Seleccione a opción **Editar** da lista.

4. Tamén pode actualizar a **Clave de acceso** e seleccionar **Seguinte**.

   ![Diálogo para editar e actualizar unha clave de acceso para un orixe de datos existente.](media/edit-access-key.png)

5. Opcionalmente, pode actualizar desde unha conexión de clave de conta a unha conexión baseada en recursos ou baseada nunha subscrición. Para obter máis información, consulte [Conectar información do público a unha conta de Azure Data Lake Storage Gen2 cunha entidade principal de seguranza do servizo de Azure](connect-service-principal.md). Non pode cambiar a información do **contedor** ao actualizar a conexión.
   > [!div class="mx-imgBorder"]

   > ![Caixa de diálogo para introducir os detalles da conexión de Azure Data Lake nunha conta de almacenamento existente.](media/enter-existing-storage-details.png)

   > [!NOTE]
   > Precisa unha das seguintes funcións no contedor ou na conta de almacenamento mencionada anteriormente para poder conectarse e crear unha orixe de datos:
   >  - Lector de datos do BLOB de almacenamento
   >  - Propietario dos datos do BLOB de almacenamento
   >  - Colaborador de datos do BLOB de almacenamento


6. Opcionalmente, escolla un ficheiro model.json ou manifest.json diferente cun conxunto diferente de entidades do contedor.

7. Opcionalmente, pode seleccionar entidades adicionais para inxerir. Tamén pode eliminar calquera entidade xa seleccionada se non hai dependencias.

   > [!IMPORTANT]
   > Se hai dependencias no ficheiro model.json ou manifest.json existente e no conxunto de entidades, verá unha mensaxe de erro e non poderá seleccionar un ficheiro model.json ou manifest.json diferente. Elimine esas dependencias antes de cambiar o ficheiro model.json ou manifest.json ou cree unha nova orixe de datos co ficheiro model.json ou manifest.json que desexe usar para evitar eliminar as dependencias.

8. Opcionalmente, pode seleccionar atributos ou entidades adicionais para habilitar a creación de perfís de datos ou desactivar os xa seleccionados.   


[!INCLUDE[footer-include](../includes/footer-banner.md)]