---
title: Duração média da sessão (dispositivos móveis)
description: A duração média da sessão do dispositivo móvel.
exl-id: e33ac9ca-f1be-4d9c-9247-c5db8fb0102e
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: ht
source-wordcount: '81'
ht-degree: 100%

---

# Duração média da sessão (dispositivos móveis)

A métrica “Duração média da sessão (móvel)” mostra a quantidade média de tempo que um determinado item de dimensão está presente por item de dimensão. É semelhante à métrica [Tempo médio no site](average-time-on-site.md), exceto que essa métrica usa componentes específicos do SDK móvel como parte do cálculo.

## Como essa métrica é calculada

Essa métrica é calculada usando as [métricas móveis](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html?lang=pt-BR) `'Total session length' / ('Launches' - 'First launches'`.
