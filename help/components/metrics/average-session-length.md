---
title: Duração média da sessão (dispositivos móveis)
description: A duração média da sessão do dispositivo móvel.
feature: Metrics
exl-id: e33ac9ca-f1be-4d9c-9247-c5db8fb0102e
source-git-commit: e32821dd3f30404166554b8437c508172e4764e5
workflow-type: tm+mt
source-wordcount: '80'
ht-degree: 26%

---

# Duração média da sessão (dispositivos móveis)

A &quot;Duração média da sessão (dispositivos móveis)&quot; [métrica](overview.md) mostra a quantidade média de tempo em que um determinado item de dimensão está presente por item de dimensão. É semelhante ao [[!UICONTROL Tempo gasto por visita (segundos)]](time-spent-per-visit.md) , exceto que essa métrica usa componentes específicos do SDK móvel como parte do cálculo.

## Como essa métrica é calculada

Essa métrica é calculada usando o [métricas de ciclo de vida](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/metrics/) `'Total Session length' / ('Launches' - 'First launches'`.
