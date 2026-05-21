---
title: Semana
description: A semana em que a métrica ocorreu.
feature: Dimensions
exl-id: 944ec843-998c-473f-b8e6-16cf126745b4
TQID: https://experienceleague.adobe.com/Vvr0Svg2khSzWbtWR5hLfveyctOEM-62WU6oxIsvzXs
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 141
ht-degree: 92%

---

# Semana

A [dimensão](overview.md) &#39;Semana&#39; informa a semana em que determinada métrica ocorreu. O primeiro item de dimensão é a primeira semana no intervalo de datas, e o último item de dimensão é a última semana no intervalo de datas. Essa dimensão é essencial para os relatórios de tendências, pois permite visualizar métricas ao longo do tempo.

## Preencher esta dimensão com dados

Essa dimensão funciona imediatamente em todas as implementações. Se um conjunto de relatórios tiver dados, essa dimensão funcionará.

## Itens de dimensão

No Analysis Workspace, os itens de dimensão incluem a data (mês, dia e ano) do primeiro dia da semana.

No Data Warehouse, os itens de dimensão incluem semanas numeradas com base no intervalo de datas da solicitação. Por exemplo, a primeira semana completa é `"Week 1"`. Se uma solicitação inclui uma semana parcial, os dados são agrupados no item de dimensão `"Week 0"`.
