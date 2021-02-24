---
title: Tempo gasto por visita
description: A quantidade de tempo gasto por visita para o item de dimensão.
translation-type: tm+mt
source-git-commit: dc5c51f68ab22bd4f1368aa0656c66ee53d99103
workflow-type: tm+mt
source-wordcount: '259'
ht-degree: 100%

---


# Tempo gasto por visita (segundos)

*Esta página de ajuda descreve como o &quot;Tempo gasto por visita&quot; funciona como uma métrica. Consulte a dimensão [Tempo gasto por visita](../dimensions/time-spent-per-visit.md) para obter mais informações.*

A métrica “Tempo gasto por visita (segundos)” mostra a quantidade média de tempo que os visitantes interagem com um determinado item de dimensão durante cada visita.

Essa métrica não está disponível no Data Warehouse devido à sua arquitetura de processamento diferente.

## Como essa métrica é calculada

Essa métrica usa a fórmula [`[Total seconds spent]`](total-seconds-spent.md) `divided by (`[`[Visits]`](visits.md) `minus` [`[Bounces]`](bounces.md)`)`.

## Comparação com o tempo médio no site

Essa métrica e o [Tempo médio gasto no site](average-time-on-site.md) são semelhantes, mas têm várias diferenças principais. Ambas as métricas usam &quot;Total de segundos gastos&quot; como o numerador. No entanto, o &quot;Tempo médio no site&quot; usa as sequências que incluem um item de dimensão como seu denominador. O tempo gasto por visita usa a contagem de visitas como denominador.

Como resultado, essas métricas geram resultados semelhantes no nível da visita, mas são diferentes no nível da ocorrência.

## Porcentagens acima de 100%

Essa métrica frequentemente contém porcentagens acima de 100%. O denominador é o tempo gasto por visita da dimensão inteira, e o numerador é o tempo gasto pelo item de dimensão por visita. Se o tempo gasto por visita da dimensão inteira for menor que o tempo gasto por visita de um determinado item de dimensão, você verá percentuais acima de 100%. A classificação de relatórios classificados por essa métrica mostra o tempo de anomalia gasto por valores de visita, que normalmente não é importante. A Adobe recomenda classificar por outra métrica, como [Visitas](visits.md), em relatórios classificados.

Consulte [Visão geral do tempo gasto](time-spent.md) para obter mais informações gerais sobre o tempo gasto.
