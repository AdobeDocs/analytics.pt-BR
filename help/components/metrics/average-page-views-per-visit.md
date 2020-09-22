---
title: Média de exibições de página por visita
description: O número médio de vezes que um determinado item de dimensão apareceu em uma visita.
translation-type: tm+mt
source-git-commit: 226bbce18750825d459056ac2a87549614eb3c2c
workflow-type: tm+mt
source-wordcount: '212'
ht-degree: 93%

---


# Média de exibições de página por visita

A dimensão “Média de visualizações de página por visita” exibe quantas visualizações de página ocorreram em média em relação à dimensão desejada. Para dimensões baseadas em tempo, é possível ver a trajetória do número médio de exibições de página dentro de uma visita ao longo do tempo. Essa métrica é útil para entender com que frequência os itens de dimensão aparecem em uma visita.

>[!TIP]
>
>Use this metric alongside another metric (such as [Visits](visits.md)) to obtain better insights. Se essa métrica for utilizada sozinha, serão obtidos itens de dimensão que contém exibições de página por visita com anomalias, o que geralmente não é útil.

## Como essa métrica é calculada

Essa métrica é calculada usando a fórmula [`Page views`](page-views.md)` divided by `[`Visits`](visits.md).

## Porcentagens acima de 100%

Essa métrica frequentemente contém porcentagens acima de 100%. O denominador é a média de exibições de página por visita em toda a dimensão, e o numerador é a média de exibições de página por visita no item de dimensão. Se a média de exibições de página por visita em toda a dimensão for menor que a média de exibições de página por visita em um determinado item de dimensão, você verá percentuais acima de 100%. A classificação de relatórios classificados por essa métrica mostra valores da média de exibições de página por visita com anomalias, o que geralmente não é útil. A Adobe recomenda classificar por outra métrica, como [Visitas](visits.md), em relatórios classificados.