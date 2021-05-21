---
title: Duração média da sessão (dispositivos móveis)
description: A duração média da sessão do dispositivo móvel.
exl-id: e33ac9ca-f1be-4d9c-9247-c5db8fb0102e
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '83'
ht-degree: 100%

---

# Duração média da sessão (dispositivos móveis)

A métrica “Duração média da sessão (móvel)” mostra a quantidade média de tempo que um determinado item de dimensão está presente por item de dimensão. É semelhante à métrica [Tempo médio no site](average-time-on-site.md), exceto que essa métrica usa componentes específicos do SDK móvel como parte do cálculo.

## Como essa métrica é calculada

Essa métrica é calculada usando as [métricas móveis](https://docs.adobe.com/content/help/pt-BR/mobile-services/using/get-started-ug/mobile-metrics/metrics-reference.html) `'Total session length' / ('Launches' - 'First launches'`.
