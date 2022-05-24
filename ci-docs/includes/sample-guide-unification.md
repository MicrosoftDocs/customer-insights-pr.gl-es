---
ms.openlocfilehash: 1d79987893986148421c316193b27d268cfe0a0b
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755542"
---
Despois de inxerir os datos, comeza o proceso de unificación de datos para crear un perfil de cliente unificado. Para obter máis información, consulte [Unificación de datos](../data-unification.md).

### <a name="select-source-fields"></a>Seleccione os campos de orixe

1. Despois de inxerir os datos, asigne os contactos desde os datos de comercio electrónico e de fidelización a tipos de datos comúns. Ir a **Datos** > **Unificar**.

1. Seleccione as entidades que representan o perfil do cliente: **eCommerceContacts** e **loyCustomers**.

   ![unificar fontes de datos de comercio electrónico e fidelización.](../media/unify-ecommerce-loyalty.png)

1. Seleccione **ContactId** como clave primaria para **eCommerceContacts** e **LoyaltyID** como clave primaria para **loyCustomers**.

1. Seleccione **Seguinte**. Saltar rexistros duplicados e seleccionar **A continuación**.

### <a name="match-conditions"></a>Condicións do partido

1. Escolle **eCommerceContactos: eCommerce** como a entidade principal e inclúe todos os rexistros.

1. Escolle **loyClientes: LoyaltyScheme** e inclúe todos os rexistros.

1. Engade unha regra:
   - Seleccione **Nome completo** para eCommerceContacts e loyCustomers.
   - Seleccione **Tipo (teléfono, nome, enderezo,...)** para **Normalizar**.
   - Defina o **Nivel de precisión**: **Básico** e **Valor**: **Alto**.
   - Entra **Nome completo, correo electrónico** polo nome.

1. Engade unha segunda condición para o enderezo de correo electrónico:
   - Seleccione **Correo electrónico** para eCommerceContacts e loyCustomers.
   - Deixe Normalizar en branco.
   - Defina o **Nivel de precisión**: **Básico** e **Valor**: **Alto**.

   ![Unificar a regra de coincidencia para o nome e o correo electrónico.](../media/unify-match-rule.png)

1. Seleccione **Feito**.

1. Seleccione **Seguinte**.

### <a name="unify-fields"></a>Unificar campos

1. Cambia o nome de **ContactId** para **Clientes loy** entidade a **Contacto IDLOYALTY** para diferencialo dos outros DNI inxeridos.

1. Seleccione **A continuación** para revisar e despois seleccionar **Crear perfís de clientes**.
