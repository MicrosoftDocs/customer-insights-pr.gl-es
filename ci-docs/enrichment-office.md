---
title: Enriquece os perfís de clientes con datos de Microsoft Office 365
description: Usa datos propietarios de Microsoft Office para enriquecer os seus perfís de clientes con datos de compromiso.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahl
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 7192b7680e73a581dd603de174c57b20bec996dd
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: MT
ms.contentlocale: gl-ES
ms.lasthandoff: 06/13/2022
ms.locfileid: "8954131"
---
# <a name="enrich-customer-profiles-with-engagement-data-preview"></a>Enriquece os perfís de clientes con datos de compromiso (vista previa)

Usa datos de Microsoft Office 365 para enriquecer os perfís da túa conta de cliente con información sobre compromisos mediante Office 365 aplicacións. Os datos de participación consisten en correo electrónico e actividade de reunións, que se agregan a nivel de conta. Por exemplo, o número de correos electrónicos dunha conta empresarial ou o número de reunións coa conta. Non se facilitan datos sobre usuarios individuais.

## <a name="supported-countries-or-regions"></a>Países ou rexións admitidos

Actualmente admitimos as seguintes rexións: Reino Unido, Europa e América do Norte.

## <a name="prerequisites"></a>Requisitos previos

- Un activo Office 365 licenza cloud.
- [Perfís de clientes unificados](customer-profiles.md) baseado en [contas empresariais](work-with-business-accounts.md).
- A [Microsoft Dataverse organización adxunta](create-environment.md#step-3-connect-to-microsoft-dataverse) no teu entorno de Customer Insights.
- [Administrador](permissions.md#admin) permisos.
- Consentimento do teu Office 365 administrador de inquilinos para usar Office 365 datos a proporcionar **Insights para a organización** dentro das aplicacións de Dynamics 365.

## <a name="configure-the-enrichment"></a>Configurar o enriquecemento

1. Vaia a **Datos** > **Enriquecemento** e seleccione o separador **Descubrir**.

1. Seleccione **Enriquece os meus datos** no **Compromiso da conta** tella.

   :::image type="content" source="media/enrichment-office-tile.png" alt-text="Mosaico de compromiso da conta.":::

1. Revisa a vista xeral e, a continuación, selecciona **A continuación**.

1. Introduza os enderezos de correo electrónico da súa organización para os que se van agregar os datos de Office. Só se procesan os datos dos enderezos de correo electrónico indicados para a comunicación relevante. Unha boa práctica é utilizar grupos de correo electrónico, por exemplo, *Equipo de vendas dos EUA*, que podes xestionar Office 365. Resólvese e móstrase o número de enderezos de correo electrónico dos grupos. O número total de enderezos de correo electrónico debe ser polo menos 2 e non pode superar os 2.500.

   :::image type="content" source="media/enrichment-office-email-addresses.png" alt-text="Enderezos de correo electrónico de compromiso da conta.":::

1. Revisa e proporciona o teu consentimento para [Office 365 consentimento do administrador do inquilino](#office-365-tenant-administrator-consent) mediante a selección **Estou de acordo**.

1. Seleccione **Seguinte**.

1. Seleccione o **Conxunto de datos de contacto** e escolle o perfil que queres enriquecer. Seleccione **Seguinte**.

1. Asigne o campo do enderezo de correo electrónico de contacto e seleccione **A continuación**.

1. Proporcionar a **Nome** para o enriquecemento e o **Entidade de saída**.

1. Seleccione **Gardar enriquecemento** despois de revisar as súas opcións.

1. Seleccione **Pechar** para volver ao **Enriquecementos** páxina.

### <a name="office-365-tenant-administrator-consent"></a>Office 365 consentimento do administrador do inquilino

Consentimento dun Office 365 O administrador do inquilino é necesario para activar o enriquecemento. Envíase un correo electrónico a Office 365 administradores de inquilinos cando se garda o enriquecemento, o que lles pide que revisen e consentin para permitir que as aplicacións de Dynamics 365 utilicen as súas empresas.Office 365 datos a proporcionar **Insights para a organización**. O Office 365 O administrador do inquilino tamén pode consentir directamente no seu Office 365 consola de administración, seleccionando **Insights para a organización**.

## <a name="running-the-enrichment-for-the-first-time"></a>Realizando o enriquecemento por primeira vez

Cando se inicia o enriquecemento por primeira vez, despois do Office 365 O administrador do inquilino deu o seu consentimento para descargar os datos de Office 365 comeza. Este proceso leva algún tempo. A primeira carreira de enriquecemento programarase cun atraso de seis horas. Podes ver o número de días que cobren os datos na páxina de descrición xeral da participación na conta despois de que remate o enriquecemento. Cun gran volume de datos, volve executar o enriquecemento despois duns días. Asegura que os datos estean completos durante toda a xanela de tempo, que é dun ano.

Dependendo do tamaño dos teus datos de Office, pode tardar varias horas en completarse.

Cando executa un enriquecemento, Microsoft procesará os datos dentro do Office 365 límite de cumprimento para crear coñecementos agregados, que despois se engaden ao seu contorno de Customer Insights. Non hai datos a nivel individual (por exemplo, o corpo de ningún correo electrónico ou invitación do calendario) que están dispoñibles para os usuarios de Customer Insights.

Seleccione **Corre** para iniciar o proceso de enriquecemento.

[!INCLUDE [progress-details-pane](includes/progress-details-pane.md)]

## <a name="enrichment-results"></a>Resultados de enriquecemento

[!INCLUDE [enrichment-results](includes/enrichment-results.md)] Este é o *Oficina* entidade. O *Office_UserEntity* contén os ID de Active Directory para os enderezos de correo electrónico que se escolleron durante a configuración do enriquecemento.

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

## <a name="see-enrichment-data-on-the-customer-card"></a>Vexa datos de enriquecemento na tarxeta de cliente

O compromiso da conta tamén se pode ver nas tarxetas de clientes individuais. Vaia a **Clientes** e seleccione un perfil de cliente. Na tarxeta do cliente, atoparás a puntuación de compromiso da conta, o número total de correos electrónicos e o número total de reunións acumuladas durante o último ano. Tamén atoparás gráficos que mostran o correo electrónico e o historial de reunións.

:::image type="content" source="media/enrichment-office-customer-card.png" alt-text="Cartón de cliente con datos enriquecidos.":::

## <a name="next-steps"></a>Pasos seguintes

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]
Por exemplo, un segmento que contén todos os clientes que teñen un valor superior a 60 *días desde o último correo electrónico* e *días desde a última reunión*. Ese segmento contén contas obsoletas que podes tentar reactivar.

[!INCLUDE [footer-include](includes/footer-banner.md)]
