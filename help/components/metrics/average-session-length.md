---
title: Duração média da sessão (dispositivos móveis)
description: A duração média da sessão do dispositivo móvel.
feature: Metrics
exl-id: e33ac9ca-f1be-4d9c-9247-c5db8fb0102e
TQID: https://experienceleague.adobe.com/4TaQP7sH0pADpnwoQR-aqOpKqKvcuUXU1vmE3-ETOzM
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 83
ht-degree: 36%

---

# Duração média da sessão (dispositivos móveis)

A [métrica](overview.md) da &quot;Duração média da sessão (móvel)&quot; mostra a quantidade média de tempo que um determinado item de dimensão está presente por item de dimensão. É semelhante à métrica [[!UICONTROL Tempo gasto por visita (segundos)]](time-spent-per-visit.md), exceto que essa métrica usa componentes específicos do SDK móvel como parte do cálculo.

## Como essa métrica é calculada

Esta métrica é calculada usando as [métricas de ciclo de vida](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/metrics/) `'Total Session length' / ('Launches' - 'First launches'`.
