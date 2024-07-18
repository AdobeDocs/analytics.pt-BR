---
title: Duração média da sessão (dispositivos móveis)
description: A duração média da sessão do dispositivo móvel.
feature: Metrics
exl-id: e33ac9ca-f1be-4d9c-9247-c5db8fb0102e
source-git-commit: e32821dd3f30404166554b8437c508172e4764e5
workflow-type: tm+mt
source-wordcount: '74'
ht-degree: 29%

---

# Duração média da sessão (dispositivos móveis)

A [métrica](overview.md) da &quot;Duração média da sessão (móvel)&quot; mostra a quantidade média de tempo que um determinado item de dimensão está presente por item de dimensão. É semelhante à métrica [[!UICONTROL Tempo gasto por visita (segundos)]](time-spent-per-visit.md), exceto que essa métrica usa componentes específicos do SDK móvel como parte do cálculo.

## Como essa métrica é calculada

Esta métrica é calculada usando as [métricas de ciclo de vida](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/metrics/) `'Total Session length' / ('Launches' - 'First launches'`.
