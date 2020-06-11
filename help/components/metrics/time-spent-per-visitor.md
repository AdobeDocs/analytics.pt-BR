---
title: Tempo gasto por visitante (segundos)
description: null
translation-type: tm+mt
source-git-commit: 5282ad3f6fdd2853979cbfb2707cc07a698f63a7
workflow-type: tm+mt
source-wordcount: '153'
ht-degree: 6%

---


# Tempo gasto por visitante (segundos)

A métrica &#39;Tempo gasto por visitante (segundos)&#39; mostra a quantidade média de tempo que os visitantes interagem com um determinado valor de dimensão durante toda a vida do visitante.

Essa métrica não está disponível no Data Warehouse devido à sua arquitetura de processamento diferente.

## Como essa métrica é calculada

Essa métrica usa a fórmula [`Total seconds spent`](total-seconds-spent.md)`divided by` [`Unique visitors`](unique-visitors.md).

## Porcentagens acima de 100%

Essa métrica frequentemente contém porcentagens acima de 100%. O denominador é o tempo gasto por visitante da dimensão inteira, e o numerador é o tempo gasto pelo valor da dimensão por visitante. Se o tempo gasto por visitante da dimensão inteira for menor que o tempo gasto por visitante de um determinado valor de dimensão, você verá percentuais acima de 100%. A classificação de relatórios classificados por essa métrica mostra o tempo de anomalia gasto por valores de visitante, que normalmente não é valioso. A Adobe recomenda classificar por outra métrica, como [Visitas](visits.md), em relatórios classificados.

Consulte Visão geral [do](time-spent.md) Tempo gasto para obter mais informações gerais sobre o tempo gasto.
