---
title: Duração média da sessão (dispositivos móveis)
description: A duração média da sessão do dispositivo móvel.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '83'
ht-degree: 9%

---


# Duração média da sessão (dispositivos móveis)

A métrica &#39;Duração média da sessão (móvel)&#39; mostra a quantidade média de tempo que um determinado item de dimensão está presente por item de dimensão. É semelhante à métrica Tempo [médio no site](average-time-on-site.md) , exceto que essa métrica usa componentes específicos do SDK móvel como parte de seu cálculo.

## Como essa métrica é calculada

Essa métrica é calculada usando as métricas [](https://docs.adobe.com/content/help/en/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html) móveis `'Total session length' / ('Launches' - 'First launches'`.
