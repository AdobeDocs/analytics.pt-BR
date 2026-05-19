---
description: O Adobe Audience Manager (Adobe Audience Manager) é uma plataforma eficiente de gerenciamento de dados que ajuda você a criar perfis de público-alvo exclusivos a partir de integrações de dados primárias, secundárias/de parceiros e de terceiros. Para anunciantes, esses perfis de público-alvo ajudam a definir os segmentos mais valiosos para usar em qualquer canal digital.
solution: Analytics
title: Visão geral do Audience Analytics
feature: Audience Analytics
exl-id: 1665a554-8a6f-4b20-99b7-bb3c2c4bf8cc
TQID: https://experienceleague.adobe.com/WPB1fEJx1MaWpUNRCZ48ghAVyKyc5IwoGOdgQQ-tPhI
product_v2:
  - id: d0a3eab4-7b10-4d96-a71e-6c0f8e7b7c87
feature_v2:
  - id: fc7979f3-56c3-43ca-9784-f1ea3dc69c4b
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
  - id: df401a2a-327d-468c-a5e4-b7b7ccd071a0
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
  - id: fd2e3797-f2ea-4b36-a9af-52acf5e90513
source-git-commit: dfbc811c84e295ab4bc69345e3459f349f8a5084
workflow-type: tm+mt
source-wordcount: 522
ht-degree: 11%

---

# Visão geral do Audience Analytics

O Adobe Audience Manager (Adobe Audience Manager) é uma plataforma eficiente de gerenciamento de dados que ajuda você a criar perfis de público-alvo exclusivos a partir de integrações de dados primárias, secundárias/de parceiros e de terceiros. Para anunciantes, esses perfis de público-alvo ajudam a definir os segmentos mais valiosos para usar em qualquer canal digital.

Com a integração do Audience Analytics em vigor, é possível incorporar dados de público-alvo do Adobe Audience Manager, como informações demográficas (por exemplo, sexo ou nível de renda), informações psicográficas (interesses e hobbies), dados de CRM e dados de impressão de anúncio, em qualquer fluxo de trabalho do Analytics.


>[!BEGINSHADEBOX]

Assista a ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Audience Analytics](https://experienceleague.adobe.com/pt-br/docs/analytics-learn/tutorials/integrations/audience-manager/audience-analytics-integrate-aam-segments-into-analytics){target="_blank"} para ver um vídeo de demonstração.

>[!ENDSHADEBOX]


## Principais benefícios {#benefits}

A integração do Audience Analytics apresenta os seguintes benefícios principais:

* É a primeira integração produzida entre uma Plataforma de gerenciamento de dados (DMP) e um mecanismo de análise no mercado.
* Os segmentos são compartilhados do Adobe Audience Manager para o Analytics em tempo real, para informar a descoberta, a segmentação e a otimização de públicos-alvo.
* Todos os segmentos do Adobe Audience Manager são compartilhados por padrão, enriquecendo totalmente os perfis do cliente no Analytics.
* Os administradores de soluções podem habilitar a integração por meio da interface do usuário, com o mínimo de alterações de código necessárias.
* Somente os segmentos que seguem os controles de exportação de dados do Audience Manager são compartilhados.

## Como o Audience Analytics funciona {#works}

![](assets/mc-aud-dataflow.png)

1. Cada vez que um visitante acessa suas propriedades digitais, as ocorrências são coletadas e enviadas para o Analytics.
1. Com o [encaminhamento pelo lado do servidor](/help/admin/tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf.md), cada ocorrência recebida pelo Analytics é automaticamente enviada ao Adobe Audience Manager em tempo real.
1. Por meio da integração do Audience Analytics, para cada ocorrência, a associação de público-alvo de um visitante é pesquisada no Adobe Audience Manager e uma lista de IDs de segmento é retornada ao Analytics para processamento em tempo real.

Como os segmentos do Adobe Audience Manager são inseridos com base na mesma ocorrência, você pode ter certeza de que os dados disponíveis no Adobe Audience Manager sobre um visitante não serão perdidos e estarão atualizados para essa ocorrência. Isso é superior a um plug-in do AppMeasurement, pois um plug-in pode disponibilizar esses segmentos somente na próxima ocorrência (em vez da ocorrência atual).

Além disso, classificamos automaticamente as IDs de segmento da Adobe Audience Manager de acordo com os nomes amigáveis, para que você não precise pesquisar IDs alfanuméricas em relatórios do Analytics.

## Pré-requisitos {#prerequisites}

Verifique se os seguintes pré-requisitos estão em vigor:

* Você é um cliente da Audience Manager e da Adobe Analytics.
* Você é um administrador do Audience Manager.
* Você está usando o Serviço de identidade v1.5 ou posterior.
* Os conjuntos de relatórios do Adobe Audience Manager e do Adobe Analytics são mapeados para a mesma organização da CX Enterprise.
* Você usa [encaminhamento pelo lado do servidor](/help/admin/tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf.md) e implantou o [módulo de Gerenciamento de público-alvo](https://experienceleague.adobe.com/docs/audience-manager/user-guide/implementation-integration-guides/integration-other-solutions/audience-management-module.html?lang=pt-BR) (sem código DIL) - AppMeasurement 1.5 ou posterior.

Esses pré-requisitos estão descritos no [Fluxo de trabalho do Audience Analytics](/help/integrate/c-audience-analytics/c-workflow/audiences-workflow.md).
