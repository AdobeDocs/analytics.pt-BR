---
title: Visualizações de página
description: O número de vezes que um item de dimensão foi definido ou mantido no Adobe Analytics.
feature: Metrics
exl-id: 6b4fb7af-03e2-49e8-a431-f7746c89a626
source-git-commit: 66be48d0f41061d259cc53fb835ebd155294a710
workflow-type: ht
source-wordcount: '169'
ht-degree: 100%

---

# Visualizações de página

A [métrica](overview.md) **[!UICONTROL Visualizações de página]** mostra o número de vezes que um determinado item de dimensão foi definido ou mantido em uma página. É uma das métricas mais comuns e básicas nos relatórios.

## Como essa métrica é calculada

Essa métrica conta todas as chamadas de rastreamento de visualização de página ([`t()`](/help/implement/vars/functions/t-method.md)) em um conjunto de relatórios. Para dimensões, isso inclui ocorrências em que um item de dimensão é definido ou mantido. Isso não inclui chamadas de rastreamento de link ([`tl()`](/help/implement/vars/functions/tl-method.md)) ou dados de [Fontes de dados](/help/import/data-sources/overview.md).

## Comparar com métricas semelhantes

* **Visualizações de página vs [visitas](visits.md)**: as Visualizações de página contam o número de vezes que uma página é exibida. A métrica Visitas conta o número de sessões para visitantes. Uma visita consiste em uma ou mais visualizações de página.
* **Visualizações de página vs. [Eventos de página](page-events.md)**: as Visualizações de página contam o número de chamadas de rastreamento de exibição de página (`t()`) e excluem as chamadas de rastreamento de link (`tl()`). Os eventos de página são o oposto. Eles contam o número de chamadas de rastreamento de link e excluem chamadas de rastreamento de visualização de página.
