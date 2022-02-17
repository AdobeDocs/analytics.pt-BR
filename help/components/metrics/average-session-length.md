---
title: Duração média da sessão (dispositivos móveis)
description: A duração média da sessão do dispositivo móvel.
feature: Metrics
exl-id: e33ac9ca-f1be-4d9c-9247-c5db8fb0102e
source-git-commit: 7966c7d9add0011831c97fbe0dfcca2acd8afb58
workflow-type: tm+mt
source-wordcount: '81'
ht-degree: 100%

---

# Duração média da sessão (dispositivos móveis)

A métrica “Duração média da sessão (móvel)” mostra a quantidade média de tempo que um determinado item de dimensão está presente por item de dimensão. É semelhante à métrica [Tempo médio no site](average-time-on-site.md), exceto que essa métrica usa componentes específicos do SDK móvel como parte do cálculo.

## Como essa métrica é calculada

Essa métrica é calculada usando as [métricas móveis](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html?lang=pt-BR) `'Total session length' / ('Launches' - 'First launches'`.
