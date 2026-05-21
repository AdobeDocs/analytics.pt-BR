---
title: Tempo gasto por visitante (segundos)
description: A métrica “Tempo gasto por visitante (segundos)” mostra a quantidade média de tempo que os visitantes interagem com um determinado item de dimensão durante todo o período de visita.
feature: Metrics
exl-id: 80f38bab-2ee1-4d0d-ba53-9b2c7c85e481
TQID: https://experienceleague.adobe.com/NFmA2Q80h2WOTRwoJ882aFMG60y2HKngR0Ew0qnxb8o
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 182
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
