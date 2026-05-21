---
description: Tabela de pesquisa para determinar o tipo de uma ocorrência com base no evento da página.
keywords: page;event;page_event;post_page_event
title: Pesquisa de evento da página
feature: Data Feeds
exl-id: ef0467df-b94b-4cec-b312-96d8f42c23b0
TQID: https://experienceleague.adobe.com/QAGYKNnpMl2tM6BRux7BBL-YFpMTgUIXsHT-9bGKWnA
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 226
ht-degree: 100%

---

# Pesquisa de evento da página

Tabela de pesquisa para determinar o tipo de uma ocorrência com base no valor de `page_event`. Como mencionado na [referência da coluna de dados](datafeeds-reference.md), as colunas `page_event` e `post_page_event` são tinyint unsigned.

* Consulte [`t()`](/help/implement/vars/functions/t-method.md) para saber mais sobre a implementação de chamadas de exibição de página no AppMeasurement e no SDK da web.
* Consulte [`tl()`](/help/implement/vars/functions/tl-method.md) para saber mais sobre a implementação de chamadas de rastreamento de link no AppMeasurement e no SDK da web.
* Consulte [Implementar o Adobe Analytics com a Adobe Experience Platform Edge Network](/help/implement/aep-edge/overview.md) para entender como o Adobe Analytics traduz conteúdo XDM para tipos de evento de página.

| Valor de `page_event` | Valor de `post_page_event` | Descrição |
| --- | --- | --- |
| `0` | `0` | Todas as chamadas de exibição de página padrão. É o valor padrão para a maioria das ocorrências. |
| `10` | `100` | Links personalizados. Defina o tipo de link como `o` (AppMeasurement) ou `xdm.web.webInteraction.type` como `other` (SDK da web ou SDK móvel). |
| `11` | `101` | Links de download. Defina o tipo de link como `d` (AppMeasurement) ou `xdm.web.webInteraction.type` como `download` (SDK da web ou SDK móvel). |
| `12` | `102` | Links de saída. Defina o tipo de link como `e` (AppMeasurement) ou `xdm.web.webInteraction.type` como `exit` (SDK da web ou SDK móvel). |
| `31` | `76` | Início de mídia |
| `32` | `77` | Atualizações de mídia (sem processamento de outras variáveis) |
| `33` | `78` | Atualizações de mídia (com processamento de outras variáveis) |
| `40` | `80` | Survey |
| `50` | `50` | Início da mídia de streaming |
| `51` | `51` | Fechamento da mídia de streaming |
| `52` | `52` | Navegação da mídia de streaming |
| `53` | `53` | Keep alive da mídia de streaming |
| `54` | `54` | Início de anúncio da mídia de streaming |
| `55` | `55` | Fechamento de anúncio da mídia de streaming |
| `56` | `56` | Navegação de anúncios da mídia de streaming |
| `60` | `60` | Início da mídia do Primetime |
| `61` | `61` | Fechamento da mídia do Primetime |
| `62` | `62` | Navegação da mídia do Primetime |
| `63` | `63` | Keep alive da mídia do Primetime |
| `64` | `64` | Início de anúncio da mídia do Primetime |
| `65` | `65` | Fechamento de anúncio da mídia do Primetime |
| `66` | `66` | Navegação de anúncio da mídia do Primetime |
| `70` | `70` | Inclui dados de atividade do Target |
