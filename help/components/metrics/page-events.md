---
title: Eventos de página
description: O número de ações de rastreamento de link acionadas.
feature: Metrics
exl-id: 1afe86e3-65b3-4e4e-b436-ed7cb5da9641
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '142'
ht-degree: 50%

---

# Eventos de página

Os &quot;Eventos de página&quot; [métrica](overview.md) mostra o número de vezes que qualquer chamada de rastreamento de link foi feita. Essa métrica é útil para entender quais páginas têm o conteúdo mais envolvente. A medição dessa métrica é mais útil quando há a possibilidade de um visitante executar uma ação na página sem navegar até uma nova página.

## Como essa métrica é calculada

Essa métrica conta tudo [Chamadas de rastreamento de link (`tl()`)](/help/implement/vars/functions/tl-method.md) em um conjunto de relatórios. Todos os tipos de links estão incluídos (links personalizados, links de download e links de saída). Não inclui [Chamadas de rastreamento de exibição de página (`t()`)](/help/implement/vars/functions/t-method.md).

## Comparar a métricas semelhantes

* **Eventos de página versus [Exibições de página](page-views.md)**: os eventos de página contam o número de chamadas de rastreamento de link (`tl()`) e exclua chamadas de rastreamento de visualização de página (`t()`). As exibições de página são o oposto; conta o número de chamadas de rastreamento de exibição de página e exclui os links.
