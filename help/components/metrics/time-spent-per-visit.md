---
title: Tempo gasto por visita (métricas)
description: A quantidade de tempo gasto por visita para o item de dimensão.
feature: Metrics
exl-id: 0f951196-66a2-4733-bb62-4555a9331efb
TQID: https://experienceleague.adobe.com/X1RtHTTmu0VIblFC3jANE7d6bIbtm4W5OvqFZDp8bLE
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '263'
ht-degree: 88%
---
# Tempo gasto por visita (segundos)

>[!BEGINSHADEBOX]

*Esta página de ajuda descreve como o &quot;Tempo gasto por visita&quot; funciona como uma métrica. Consulte a dimensão [Tempo gasto por visita](../dimensions/time-spent-per-visit.md) para obter mais informações.*

>[!ENDSHADEBOX]

A [métrica](overview.md) de &quot;Tempo gasto por visita (segundos)&quot; mostra a quantidade média de tempo que os visitantes interagem com um determinado item de dimensão durante cada visita.

Essa métrica não está disponível no Data Warehouse devido à sua arquitetura de processamento diferente.

## Como essa métrica é calculada

Essa métrica usa a fórmula [`[Total seconds spent]`](total-seconds-spent.md) `divided by (`[`[Visits]`](visits.md) `minus` [`[Bounces]`](bounces.md)`)`.

## Comparação com o tempo médio no site

Essa métrica e o [Tempo médio gasto no site](average-time-on-site.md) são semelhantes, mas têm várias diferenças principais. Ambas as métricas usam &quot;Total de segundos gastos&quot; como o numerador. No entanto, o &quot;Tempo médio no site&quot; usa as sequências que incluem um item de dimensão como seu denominador. O tempo gasto por visita usa a contagem de visitas como denominador.

Como resultado, essas métricas geram resultados semelhantes no nível da visita, mas são diferentes no nível do hit.

## Porcentagens acima de 100%

Essa métrica frequentemente contém porcentagens acima de 100%. O denominador é o tempo gasto por visita da dimensão inteira, e o numerador é o tempo gasto pelo item de dimensão por visita. Se o tempo gasto por visita da dimensão inteira for menor que o tempo gasto por visita de um determinado item de dimensão, você verá percentuais acima de 100%. Ordenar relatórios classificados por essa métrica mostra o tempo de anomalia gasto por valores de visita, que normalmente não é importante. A Adobe recomenda classificar por outra métrica, como [Visitas](visits.md), em relatórios classificados.

Consulte [Visão geral do tempo gasto](time-spent.md) para obter mais informações gerais sobre o tempo gasto.
