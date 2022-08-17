---
title: Usa o teu propio Azure Data Lake Storage Conta Gen2
author: mukeshpo
description: Obtén información sobre os requisitos para usar o teu propio Azure Data Lake Storage conta para almacenar datos de Customer Insights.
ms.author: mukeshpo
ms.date: 06/08/2022
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.reviewer: mhart
ms.openlocfilehash: d2ff49c324c5c5c28213f362ff330d441fcb6052
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: gl-ES
ms.lasthandoff: 08/10/2022
ms.locfileid: "9246199"
---
# <a name="use-your-own-azure-data-lake-storage-gen2-account"></a>Usa o teu propio Azure Data Lake Storage Conta Gen2

Dynamics 365 Customer Insights ofrécelle a opción de almacenar todos os teus datos [Azure Data Lake Storage Xeración 2](/azure/storage/blobs/data-lake-storage-introduction).

Ao gardar datos en Data Lake Storage, aceptas que os datos se transferirán e almacenen na localización xeográfica adecuada para esa conta de almacenamento de Azure. Para obter máis información, consulte [Centro de confianza de Microsoft](https://www.microsoft.com/trust-center).

Os administradores de Customer Insights poden [crear ambientes](create-environment.md) e [especificar a opción de almacenamento de datos](create-environment.md#step-2-configure-data-storage) no proceso.

## <a name="prerequisites-to-use-your-storage-account"></a>Requisitos previos para usar a túa conta de almacenamento

- Azure Data Lake Storage as contas deben estar na mesma rexión de Azure que seleccionou ao crear o ambiente de Customer Insights. Podes consultar a rexión do contorno de Customer Insights en **Admin** > **Sistema** > **Sobre**.
- Data Lake Storage debe ser Gen2 e ter [espazo de nomes xerárquico habilitado](/azure/storage/blobs/create-data-lake-storage-account). As contas de almacenamento Gen1 non son compatibles.
- Un recipiente chamado`customerinsights` ten que existir na conta de almacenamento. Tes que crealo antes de usar o teu propio Data Lake Storage en Customer Insights. O administrador que configura o ambiente de Customer Insights necesita o rol de Colaborador de datos de blob de almacenamento ou propietario de datos de blob de almacenamento na conta de almacenamento ou no`customerinsights` envase. Para obter máis información sobre como asignar permisos nunha conta de almacenamento, consulte [Crea unha conta de almacenamento](/azure/storage/common/storage-account-create?toc=%2Fazure%2Fstorage%2Fblobs%2Ftoc.json&tabs=azure-portal).

## <a name="connect-customer-insights-with-your-storage-account"></a>Conecta Customer Insights coa túa conta de almacenamento

Cando cree un novo ambiente, asegúrese de que existe a conta de Data Lake Storage e que se cumpren todos os requisitos previos.

1. No **Almacenamento de datos** paso durante a creación do ambiente, configurado **Garda os datos de saída** a **Azure Data Lake Storage Xeración 2**.
1. Escolle como **Conecta o teu almacenamento**. Podes escoller entre unha opción baseada en recursos e unha opción baseada na subscrición para a autenticación. Para obter máis información, consulte [Conectar a un Azure Data Lake Storage conta mediante un principal de servizo de Azure](connect-service-principal.md).
   - Para **Subscrición de Azure**, escolle o **Subscrición**, **de recursos**, e **Conta de almacenamento** que contén o`customerinsights` envase.
   - Para **Clave da conta**, proporcionar o **Nome da conta** e o **Clave da conta** para a conta de Data Lake Storage. O uso deste método de autenticación implica que se lle informa se a súa organización rota as claves. Debes [actualizar a configuración do entorno](manage-environments.md#edit-an-existing-environment) coa nova chave cando se xire.
1. Escolla se quere usar Azure Private Link para conectarse á conta de almacenamento e [crear a conexión a Private Link](security-overview.md#set-up-an-azure-private-link) cun proceso de dous pasos.

Cando se completan os procesos do sistema como a inxestión de datos, o sistema crea os cartafoles correspondentes na conta de almacenamento. Os ficheiros de datos e os ficheiros *model.json* créanse e engádense aos cartafoles en función do nome do proceso.

Se crea varios contornos de Customer Insights e elixe gardar as entidades de saída deses ambientes na súa conta de almacenamento, Customer Insights crea cartafoles separados para cada ambiente con `ci_environmentID` no recipiente.
