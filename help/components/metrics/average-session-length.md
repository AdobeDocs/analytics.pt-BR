---
title: Duração média da sessão (dispositivos móveis)
description: A duração média da sessão do dispositivo móvel.
translation-type: tm+mt
source-git-commit: 625af73ad2fbe4b44bce00a122c4e65d8964323f
workflow-type: tm+mt
source-wordcount: '83'
ht-degree: 9%

---


# Duração média da sessão (dispositivos móveis)

A métrica &#39;Duração média da sessão (móvel)&#39; mostra a quantidade média de tempo que um determinado valor de dimensão está presente por valor de dimensão. É semelhante à métrica Tempo [médio no site](average-time-on-site.md) , exceto que essa métrica usa componentes específicos do SDK móvel como parte de seu cálculo.

## Como essa métrica é calculada

Essa métrica é calculada usando as métricas [](https://docs.adobe.com/content/help/en/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html) móveis `'Total session length' / ('Launches' - 'First launches'`.
