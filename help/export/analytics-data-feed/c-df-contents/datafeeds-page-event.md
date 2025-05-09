---
description: Tabela de pesquisa para determinar o tipo de uma ocorrência com base no evento da página.
keywords: page;event;page_event;post_page_event
title: Pesquisa de evento da página
feature: Data Feeds
exl-id: ef0467df-b94b-4cec-b312-96d8f42c23b0
source-git-commit: e16b0d7b3fe585dc8e9274a77833ad5af3c63124
workflow-type: tm+mt
source-wordcount: '226'
ht-degree: 4%

---

# Pesquisa de evento da página

Tabela de pesquisa para determinar o tipo de uma ocorrência com base no valor `page_event`. Como mencionado na [referência de coluna de dados](datafeeds-reference.md), as colunas `page_event` e `post_page_event` são tinyint unsigned.

* Consulte [`t()`](/help/implement/vars/functions/t-method.md) para entender a implementação de chamadas de exibição de página para o AppMeasurement e o Web SDK.
* Consulte [`tl()`](/help/implement/vars/functions/tl-method.md) para entender a implementação de chamadas de rastreamento de link para o AppMeasurement e o Web SDK.
* Consulte [Implementar o Adobe Analytics com o Adobe Experience Platform Edge Network](/help/implement/aep-edge/overview.md) para entender como o Adobe Analytics traduz cargas XDM para tipos de evento de página.

| Valor de `page_event` | Valor de `post_page_event` | Descrição |
| --- | --- | --- |
| `0` | `0` | Todas as chamadas de exibição de página padrão. É o valor padrão para a maioria das ocorrências. |
| `10` | `100` | Links personalizados. Defina o tipo de link como `o` (AppMeasurement) ou `xdm.web.webInteraction.type` como `other` (Web SDK ou Mobile SDK). |
| `11` | `101` | Links de download. Defina o tipo de link como `d` (AppMeasurement) ou `xdm.web.webInteraction.type` como `download` (Web SDK ou Mobile SDK). |
| `12` | `102` | Links de saída. Defina o tipo de link como `e` (AppMeasurement) ou `xdm.web.webInteraction.type` como `exit` (Web SDK ou Mobile SDK). |
| `31` | `76` | Início da mídia |
| `32` | `77` | Atualizações de mídia (sem processamento de outra variável) |
| `33` | `78` | Atualizações de mídia (com processamento de outra variável) |
| `40` | `80` | Survey |
| `50` | `50` | Início do streaming de mídia |
| `51` | `51` | Fechamento de mídia de transmissão |
| `52` | `52` | Depuração de mídia de transmissão |
| `53` | `53` | Keep alive de mídia de transmissão |
| `54` | `54` | Início do anúncio de mídia de transmissão |
| `55` | `55` | Fechamento de anúncios de mídia de transmissão |
| `56` | `56` | Mídia de transmissão e depuração |
| `60` | `60` | Início da mídia do Primetime |
| `61` | `61` | Fechamento de mídia do Primetime |
| `62` | `62` | Depuração de mídia do Primetime |
| `63` | `63` | Mantenha a mídia do Primetime ativa |
| `64` | `64` | Início do anúncio de mídia do Primetime |
| `65` | `65` | Anúncio de mídia do Primetime fechado |
| `66` | `66` | Depuração de anúncios de mídia do Primetime |
| `70` | `70` | Inclui dados de atividade do Target |
