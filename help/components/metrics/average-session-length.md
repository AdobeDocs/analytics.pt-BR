---
title: Duração média da sessão (dispositivos móveis)
description: A duração média da sessão do dispositivo móvel.
feature: Metrics
exl-id: e33ac9ca-f1be-4d9c-9247-c5db8fb0102e
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '89'
ht-degree: 41%

---

# Duração média da sessão (dispositivos móveis)

A &quot;Duração média da sessão (dispositivos móveis)&quot; [métrica](overview.md) mostra a quantidade média de tempo em que um determinado item de dimensão está presente por item de dimensão. É semelhante ao [Tempo gasto por visita [segundos]](https://experienceleague.adobe.com/docs/analytics/components/metrics/time-spent-per-visit.html) , exceto que essa métrica usa componentes específicos do SDK móvel como parte do cálculo.

## Como essa métrica é calculada

Essa métrica é calculada usando as [métricas móveis](https://experienceleague.adobe.com/docs/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html?lang=pt-BR) `'Total session length' / ('Launches' - 'First launches'`.
