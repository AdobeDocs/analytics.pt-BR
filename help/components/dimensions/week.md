---
title: Semana
description: A semana em que a métrica ocorreu.
translation-type: tm+mt
source-git-commit: a94b8e090b9a3c75a57fd396cac8486bba2e5d79
workflow-type: tm+mt
source-wordcount: '141'
ht-degree: 61%

---


# Semana

A dimensão “Semana” informa a semana em que uma determinada métrica ocorreu. O primeiro item de dimensão é a primeira semana no intervalo de datas, e o último item de dimensão é a última semana no intervalo de datas. Essa dimensão é essencial para os relatórios de tendências, pois permite visualizar métricas ao longo do tempo.

## Preencher esta dimensão com dados

Essa dimensão funciona imediatamente em todas as implementações. Se um conjunto de relatórios tiver dados, essa dimensão funcionará.

## Itens de dimensão

No Analysis Workspace, os itens de dimensão incluem a data (mês, dia e ano) do primeiro dia da semana.

Na Data Warehouse, os itens de dimensão incluem semanas numeradas com base no intervalo de datas da solicitação. Por exemplo, a primeira semana inteira é `"Week 1"`. Se uma solicitação incluir uma semana parcial, os dados serão agrupados no item de dimensão `"Week 0"`.
