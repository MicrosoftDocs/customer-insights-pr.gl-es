---
title: Enriquece os perfís de clientes con datos de Microsoft Office 365
description: Usa datos propietarios de Microsoft Office para enriquecer os seus perfís de clientes con datos de compromiso.
ms.date: 12/03/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahl
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 47239bd7f0c89742cf9c673bb2ebe4c41d853233
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376828"
---
# <a name="enrich-customer-profiles-with-engagement-data-preview"></a>Enriquece os perfís de clientes con datos de compromiso (vista previa)

Usa datos de Microsoft Office 365 para enriquecer os perfís da túa conta de cliente con información sobre compromisos mediante Office 365 aplicacións. Os datos de participación consisten en correo electrónico e actividade de reunións, que se agregan a nivel de conta. Por exemplo, o número de correos electrónicos dunha conta empresarial ou o número de reunións coa conta. Non se facilitan datos sobre usuarios individuais. 

Este enriquecemento está dispoñible nas seguintes rexións: Reino Unido, Europa e América do Norte.

## <a name="prerequisites"></a>Requisitos previos

Para configurar o enriquecemento, débense cumprir os seguintes requisitos previos:

- Tes un activo Office 365 licenza cloud.
- Tes [perfís de clientes unificados](customer-profiles.md) baseado en [contas empresariais](work-with-business-accounts.md).
- O teu ambiente de Customer Insights debe ter un [Microsoft Dataverse organización adxunta](create-environment.md#step-3-connect-to-microsoft-dataverse).
- Tes [administrador](permissions.md#admin) permisos.
- Tes ou podes obter o consentimento do teu Office 365 administrador de inquilinos para usar Office 365 datos a proporcionar **Insights para a organización** dentro das aplicacións de Dynamics 365.

## <a name="configure-the-enrichment"></a>Configurar o enriquecemento

1. Na información do público, vaia a **Datos** > **Enriquecemento**.

1. Vaia ao **Descubrir** ficha e seleccione **Enriquece os meus datos** no **Compromiso da conta** tella.

   :::image type="content" source="media/enrichment-office-tile.png" alt-text="Mosaico de compromiso da conta.":::
   
1. Seleccione **A continuación** no **Visión xeral** paso e introduce os enderezos de correo electrónico da túa organización para os que se van agregar os datos de Office. Só se procesan os datos dos enderezos de correo electrónico indicados para a comunicación relevante. Unha boa práctica é utilizar grupos de correo electrónico, por exemplo, *Equipo de vendas dos EUA*, que se xestionan facilmente en Office 365. Resólvese e móstrase o número de enderezos de correo electrónico dos grupos. O número total de enderezos de correo electrónico debe ser polo menos 2 e non pode superar os 2.500.

   :::image type="content" source="media/enrichment-office-email-addresses.png" alt-text="Enderezos de correo electrónico de compromiso da conta.":::

1. Revisa a declaración de consentimento, selecciona **Estou de acordo** caixa de verificación e seleccione **A continuación**.

1. Seleccione o conxunto de datos do cliente e seleccione **A continuación**.

1. Asigne o campo do enderezo de correo electrónico de contacto e seleccione **A continuación**.

1. Revisa a configuración do enriquecemento, dálle un nome ao enriquecemento e selecciona **Gardar enriquecemento** para salvar o enriquecemento.

## <a name="office-365-tenant-administrator-consent"></a>Office 365 consentimento do administrador do inquilino

Consentimento dun Office 365 O administrador do inquilino é necesario para activar o enriquecemento. Envíase un correo electrónico a Office 365 administradores de inquilinos cando se garda o enriquecemento, o que lles pide que revisen e consentin para permitir que as aplicacións de Dynamics 365 utilicen as súas empresas.Office 365 datos a proporcionar **Insights para a organización**. O Office 365 O administrador do inquilino tamén pode consentir directamente no seu Office 365 consola de administración, seleccionando **Insights para a organización**.

## <a name="running-the-enrichment-for-the-first-time"></a>Realizando o enriquecemento por primeira vez

Cando se inicia o enriquecemento por primeira vez, despois do Office 365 O administrador do inquilino deu o seu consentimento para descargar os datos de Office 365 comeza. Este proceso leva algún tempo. A primeira carreira de enriquecemento programarase cun atraso de seis horas. Podes ver o número de días que cobren os datos na páxina de descrición xeral do compromiso da conta despois de que remate o enriquecemento. Cun gran volume de datos, volve executar o enriquecemento despois duns días. Garante que os datos estean completos durante toda a xanela de tempo, que é dun ano.

Para iniciar o proceso, seleccione **Corre** na páxina de configuración da participación da conta. Ademais, podes permitir que o sistema execute o enriquecemento automaticamente como parte dunha [actualización programada](system.md#schedule-tab). Por defecto, o enriquecemento realízase unha vez por semana.

Dependendo do tamaño dos teus datos de Office, pode tardar varias horas en completarse.

Cando executa un enriquecemento, Microsoft procesará os datos dentro do Office 365 límite de cumprimento para crear información agregada, que despois se engaden ao seu contorno de Customer Insights. Non hai datos a nivel individual (por exemplo, o corpo de ningún correo electrónico ou invitación do calendario) que están dispoñibles para os usuarios de Customer Insights. 

[!INCLUDE [progress-details-pane](../includes/progress-details-pane.md)]

## <a name="enrichment-results"></a>Resultados de enriquecemento

Despois de executar o proceso de enriquecemento, vai a **Os meus enriquecementos** para revisar os resultados do enriquecemento. Atoparás o número total de clientes enriquecidos e unha visión xeral dos resultados do enriquecemento. Inclúe o número de correos electrónicos procesados e reunións, o número de días para os que se agregaron os datos e moito máis.

Tamén atoparás un gráfico co número de clientes enriquecidos ao longo do tempo e unha vista previa dos datos de enriquecemento.  

:::image type="content" source="media/enrichment-office-results-overview.png" alt-text="Versión preliminar dos resultados despois de executar o proceso de enriquecemento.":::

Todos os datos son agregados ata o nivel de conta. O sistema calcula unha puntuación de compromiso, que varía de 0 a 100, para cada conta. A puntuación do compromiso proporciona unha medida composta do compromiso da conta entre correos electrónicos e reunións en relación coas outras contas. A seguinte lista contén os datos agregados que proporciona o enriquecemento da conta:



| Datos                                                                              | Nome da columna                              |
| :-------------------------------------------------------------------------------- |:---------------------------------------- |
| Puntuación da interacción                                                                  |  EngagementScore                         |
| Número de correos electrónicos á conta                                                       |  NoOfEmails_ToAccount                    |
| Número de correos electrónicos da conta                                                     |  NoOfEmails_FromAccount                  | 
| Número de reunións iniciadas por conta                                           |  NoOfMeetings_FromAccount                | 
| Número de reunións iniciadas pola túa organización                                 |  NoOfMeetings_ToAccount                  | 
| Número de persoas da túa organización en reunións con conta                  |  NoOfContactsInvolved_Meetings           | 
| Número de persoas da túa organización en conversas de correo electrónico coa conta       |  NoOfContactsInvolved_Emails             | 
| Número de persoas da conta nas reunións coa túa organización                  |  NoOfAccountContactsInvolved_Meetings    | 
| Número de persoas da conta nas conversas de correo electrónico coa túa organización       |  NoOfAccountContactsInvolved_Emails      | 
| Data de inicio do compromiso (primeiro correo electrónico ou reunión nos datos)                        |  EngagementStartDate                     | 
| Días desde o último correo electrónico                                                             |  Días desde o último correo electrónico                      | 
| Días desde a última reunión                                                           |  Días desde a última reunión                    | 
| Duración media das reunións                                                      |  Duración_media_de_reunións             | 
| Duración media das respostas por correo electrónico da conta                                    |  AverageDuration_Of_AccountEmailReplies  | 
| Data de inicio da agregación                                                            |  Data de inicio da agregación                    | 
| Nivel de agregación (ano, mes ou semana)                                          |  Nivel de agregación                        | 


Revisa os datos enriquecidos seleccionando **Ver máis** na sección de vista previa. Abre o *Oficina* entidade. Tamén podes atopar a entidade que figura no **Enriquecemento** grupo en **Datos** > **Entidades**. Tamén atoparás o *Office_UserEntity*, que contén os ID de Active Directory para os enderezos de correo electrónico que se escolleron durante a configuración do enriquecemento 

## <a name="see-enrichment-data-on-the-customer-card"></a>Vexa datos de enriquecemento na tarxeta de cliente

O compromiso da conta tamén se pode ver nas tarxetas de clientes individuais. Vaia a **Clientes** e seleccione un perfil de cliente. Na tarxeta do cliente, atoparás a puntuación de compromiso da conta, o número total de correos electrónicos e o número total de reunións acumuladas durante o último ano. Tamén atoparás gráficos que mostran o correo electrónico e o historial de reunións.

:::image type="content" source="media/enrichment-office-customer-card.png" alt-text="Cartón de cliente con datos enriquecidos.":::

## <a name="create-segments-and-measures-based-on-the-enriched-data"></a>Crea segmentos e medidas a partir dos datos enriquecidos

Os datos enriquecidos pódense usar para crear segmentos e medidas como se detalla a continuación. Por exemplo, un segmento que contén todos os clientes que teñen un valor superior a 60 *días desde o último correo electrónico* e *días desde a última reunión*. Ese segmento contén contas obsoletas que podes tentar reactivar. 

## <a name="next-steps"></a>Pasos seguintes

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]


[!INCLUDE[footer-include](../includes/footer-banner.md)]
