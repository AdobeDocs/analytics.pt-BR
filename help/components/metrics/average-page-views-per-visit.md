---
title: Média de exibições de página por visita
description: O número médio de vezes que um determinado item de dimensão apareceu em uma visita.
feature: Metrics
exl-id: fef6e803-e819-4f0f-8cb0-c565328a8bea
TQID: https://experienceleague.adobe.com/sospsPhk77O5qOLcMLmu7gB7rvlxbp8rGqB39LCnQ5g
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: null
workflow-type: tm+mt
source-wordcount: 216
ht-degree: 92%

---

# Média de exibições de página por visita

A dimensão “Média de visualizações de página por visita” exibe quantas visualizações de página ocorreram em média em relação à dimensão desejada. Para dimensões baseadas em tempo, é possível ver a trajetória do número médio de exibições de página dentro de uma visita ao longo do tempo. Esta [métrica](overview.md) é útil quando você quer entender com que frequência os itens de dimensão aparecem em uma visita.

>[!TIP]
>
>Use essa métrica junto com outra métrica (como [Visitas](visits.md)) para obter melhores insights. Se essa métrica for utilizada sozinha, serão obtidos itens de dimensão que contém exibições de página por visita com anomalias, o que geralmente não é útil.

## Como essa métrica é calculada

Essa métrica é calculada usando a fórmula [`Page views`](page-views.md)` divided by `[`Visits`](visits.md).

## Porcentagens acima de 100%

Essa métrica frequentemente contém porcentagens acima de 100%. O denominador é a média de exibições de página por visita em toda a dimensão, e o numerador é a média de exibições de página por visita no item de dimensão. Se a média de exibições de página por visita em toda a dimensão for menor que a média de exibições de página por visita em um determinado item de dimensão, você verá percentuais acima de 100%. A classificação de relatórios classificados por essa métrica mostra valores da média de exibições de página por visita com anomalias, o que geralmente não é útil. A Adobe recomenda classificar por outra métrica, como [Visitas](visits.md), em relatórios classificados.
