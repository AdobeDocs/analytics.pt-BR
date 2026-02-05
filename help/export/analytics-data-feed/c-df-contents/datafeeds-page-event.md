---
description: Tabela de pesquisa para determinar o tipo de uma ocorrência com base no evento da página.
keywords: page;event;page_event;post_page_event
title: Pesquisa de evento da página
feature: Data Feeds
exl-id: ef0467df-b94b-4cec-b312-96d8f42c23b0
source-git-commit: e16b0d7b3fe585dc8e9274a77833ad5af3c63124
workflow-type: ht
source-wordcount: '226'
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
| `40` | `80` | Pesquisa |
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
