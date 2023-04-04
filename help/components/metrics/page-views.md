---
title: Exibições de página
description: O número de vezes que um item de dimensão foi definido ou persistiu no Adobe Analytics.
feature: Metrics
exl-id: 6b4fb7af-03e2-49e8-a431-f7746c89a626
source-git-commit: 1be9a8ceb03f8102a0799f4518db35c1e8cd7b14
workflow-type: tm+mt
source-wordcount: '168'
ht-degree: 33%

---

# Exibições de página

A métrica “Visualizações de página” mostra o número de vezes que um determinado item de dimensão foi definido ou persistiu em uma página. É uma das métricas mais comuns e básicas nos relatórios.

## Como essa métrica é calculada

Essa métrica conta todas as chamadas de rastreamento de visualização de página ([`t()`](/help/implement/vars/functions/t-method.md)) em um conjunto de relatórios. Para dimensões, inclui ocorrências em que um item de dimensão é definido ou mantido. Ela não inclui chamadas de rastreamento de link ([`tl()`](/help/implement/vars/functions/tl-method.md)) ou dados do resumo [Fontes de dados](/help/import/data-sources/overview.md).

## Comparar a métricas semelhantes

* **Exibições de página versus [Visitas](visits.md)**: As exibições de página contam o número de vezes que uma página é exibida. Visitas contam o número de sessões para visitantes. Uma visita consiste em uma ou mais exibições de página.
* **Exibições de página versus [Eventos de página](page-events.md)**: As exibições de página contam o número de chamadas de rastreamento de exibição de página (`t()`) e exclui chamadas de rastreamento de link (`tl()`). Os eventos de página são o oposto; eles contam o número de chamadas de rastreamento de link e excluem chamadas de rastreamento de visualização de página.
