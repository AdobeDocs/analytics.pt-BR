---
title: Semana
description: A semana em que a métrica ocorreu.
feature: Dimensions
exl-id: 944ec843-998c-473f-b8e6-16cf126745b4
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '141'
ht-degree: 100%

---

# Semana

A dimensão “Semana” informa a semana em que uma determinada métrica ocorreu. O primeiro item de dimensão é a primeira semana no intervalo de datas, e o último item de dimensão é a última semana no intervalo de datas. Essa dimensão é essencial para os relatórios de tendências, pois permite visualizar métricas ao longo do tempo.

## Preencher esta dimensão com dados

Essa dimensão funciona imediatamente em todas as implementações. Se um conjunto de relatórios tiver dados, essa dimensão funcionará.

## Itens de dimensão

No Analysis Workspace, os itens de dimensão incluem a data (mês, dia e ano) do primeiro dia da semana.

No Data Warehouse, os itens de dimensão incluem semanas numeradas com base no intervalo de datas da solicitação. Por exemplo, a primeira semana completa é `"Week 1"`. Se uma solicitação inclui uma semana parcial, os dados são agrupados no item de dimensão `"Week 0"`.
