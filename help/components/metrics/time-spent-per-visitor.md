---
title: Tempo gasto por visitante (segundos)
description: A métrica “Tempo gasto por visitante (segundos)” mostra a quantidade média de tempo que os visitantes interagem com um determinado item de dimensão durante todo o período de visita.
feature: Metrics
exl-id: 80f38bab-2ee1-4d0d-ba53-9b2c7c85e481
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 85%

---

# Tempo gasto por visitante (segundos)

A [!UICONTROL métrica Tempo gasto por visitante (segundos)] [mostra o tempo médio pelo qual os visitantes interagem com determinado item de dimensão durante todo o período de visita.](overview.md)

Essa métrica não está disponível no Data Warehouse devido à sua arquitetura de processamento diferente.

## Como essa métrica é calculada

Essa métrica utiliza a fórmula [`Total seconds spent`](total-seconds-spent.md) `divided by` [`Unique visitors`](unique-visitors.md).

## Porcentagens acima de 100%

Essa métrica frequentemente contém porcentagens acima de 100%. O denominador é o tempo gasto por visitante na dimensão inteira, e o numerador é o tempo gasto por visitante no item de dimensão. Se o tempo gasto por visitante na dimensão inteira for menor que o tempo gasto por visitante em um determinado item de dimensão, você verá porcentagens acima de 100%. A classificação de relatórios classificados por essa métrica mostra valores de tempo gasto por visitante com anomalias, o que geralmente não é útil. A Adobe recomenda classificar por outra métrica, como [Visitas](visits.md), em relatórios classificados.

Consulte [Visão geral do tempo gasto](time-spent.md) para obter mais informações gerais sobre o tempo gasto.
