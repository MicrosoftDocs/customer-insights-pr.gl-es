---
ms.openlocfilehash: a67714de5aae80a0080c0e631ae6f8986eb2a003
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "9611125"
---
- **Rendemento do modelo de adestramento** : As notas A, B ou C indican o rendemento do predición e poden axudarche a tomar a decisión de usar os resultados almacenados na entidade de saída.

  As cualificacións determínanse en función das seguintes regras:
  - **A** cando o modelo predixo con precisión polo menos o 50 % das predicións totais e cando a porcentaxe de predicións precisas para os clientes que abandonaron é superior á taxa de referencia nun 10 % como mínimo.
  - **B** cando o modelo predixo con precisión polo menos o 50 % das predicións totais e cando a porcentaxe de predicións precisas para os clientes que abandonaron é ata un 10 % superior á referencia.
  - **C** cando o modelo predixo con precisión menos do 50 % das previsións totais, ou cando a porcentaxe de predicións precisas para os clientes que produciron é menor que a liña de base.
  - **Liña base** toma a entrada da xanela temporal predición para o modelo (por exemplo, un ano) e crea diferentes fraccións de tempo dividíndoo por 2 ata chegar a un mes ou menos. Utiliza estas fraccións para crear unha regra de negocio para clientes que non compraron neste período de tempo. Considérase que estes clientes abandonaron. Elíxese como modelo de referencia a regra empresarial baseada no tempo coa maior capacidade de predicir quen é probable que se produza.

- **Probabilidade de renovación (número de clientes)**: grupos de clientes en función do risco previsto de renovación. Opcionalmente, [crear segmentos de clientes](../prediction-based-segment.md) con alto risco de rotación. Estes segmentos axudan a comprender onde debe estar o seu corte para a subscrición a segmentos.

- **Factores máis influentes**: hai moitos factores que se teñen en conta á hora de crear a súa predición. Cada un dos factores ten a súa importancia calculada para as predicións agregadas que crea un modelo. Use estes factores para axudar a validar os seus resultados predición. Ou use esta información máis tarde para [crear segmentos](../prediction-based-segment.md) que poderían axudar a influír no risco de abandono dos clientes.