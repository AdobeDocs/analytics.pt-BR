---
title: Tempo gasto por visita (métricas)
description: A quantidade de tempo gasto por visita para o item de dimensão.
feature: Dimensions
exl-id: f241eb2d-7e22-47ee-ade8-8aeb7b2b9694
source-git-commit: 10ff98f7ca4697afe5c2dae66be415c0d68c4aac
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Tempo gasto por visita (segundos)

*Esta página de ajuda descreve como o &quot;Tempo gasto por visita&quot; funciona como uma métrica. Consulte a dimensão [Tempo gasto por visita](../dimensions/time-spent-per-visit.md) para obter mais informações.*

A métrica “Tempo gasto por visita (segundos)” mostra a quantidade média de tempo que os visitantes interagem com um determinado item de dimensão durante cada visita.

1. Essa métrica não está disponível no Data Warehouse devido à sua arquitetura de processamento diferente.
2. Como essa métrica é calculada
3. Essa métrica usa a fórmula [`[Total seconds spent]`](total-seconds-spent.md) `divided by (`[`[Visits]`](visits.md) `minus` [`[Bounces]`](bounces.md)`)`.

Comparação com o tempo médio no site

>Essa métrica e o [Tempo médio gasto no site](average-time-on-site.md) são semelhantes, mas têm várias diferenças principais. Ambas as métricas usam &quot;Total de segundos gastos&quot; como o numerador. No entanto, o &quot;Tempo médio no site&quot; usa as sequências que incluem um item de dimensão como seu denominador. O tempo gasto por visita usa a contagem de visitas como denominador.
>
>Como resultado, essas métricas geram resultados semelhantes no nível da visita, mas são diferentes no nível da ocorrência.

Porcentagens acima de 100%[](time-spent-on-page.md)

Essa métrica frequentemente contém porcentagens acima de 100%. O denominador é o tempo gasto por visita da dimensão inteira, e o numerador é o tempo gasto pelo item de dimensão por visita. Se o tempo gasto por visita da dimensão inteira for menor que o tempo gasto por visita de um determinado item de dimensão, você verá percentuais acima de 100%. A classificação de relatórios classificados por essa métrica mostra o tempo de anomalia gasto por valores de visita, que normalmente não é importante. A Adobe recomenda classificar por outra métrica, como [Visitas](visits.md), em relatórios classificados.[](../metrics/time-spent-per-visit.md)

## Consulte [Visão geral do tempo gasto](time-spent.md) para obter mais informações gerais sobre o tempo gasto.

These dimensions work out of the box for all implementations. If a report suite contains data, these dimensions work.

## Dimension items

Multiple dimensions exist for time spent per visit:

* **Time spent per visit - bucketed**: The amount of time is bucketed. Dimension items range from `"Less than 1 minute"` to `"More than 15 hours"`. Visits typically don&#39;t last longer than 12 hours; however, visits can exceed 12 hours if using timestamped hits or data sources.
* **Time spent per visit - granular**: Each number of seconds is a unique dimension item. This dimension is not available in Reports &amp; Analytics or Data Warehouse.

See [Time spent overview](../metrics/time-spent.md) for more general information on time spent.
