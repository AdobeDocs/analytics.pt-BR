---
description: Saiba mais sobre exemplos de métricas filtradas e ponderadas.
title: Métricas Filtradas E Ponderadas
feature: Calculated Metrics
exl-id: bea46e03-7d05-44c8-b654-c61b1e32becc
source-git-commit: 35f2812c1a1a4eed090e04d67014fcebf88a80ec
workflow-type: tm+mt
source-wordcount: '158'
ht-degree: 63%

---

# Métricas filtradas e ponderadas

Este artigo mostra exemplos de métricas filtradas e ponderadas.

## Taxa de rejeição filtrada

Essa métrica filtrada simples mostra a taxa de rejeição das páginas com mais de 100 visitas:

![Taxa de rejeição filtrada](assets/filtered-bounce-rate.png){zoomable="yes"}

Tenha em mente que esta fórmula depende de um intervalo de tempo consistente. Se você gerar um relatório para um único dia, qualquer página com mais de 20 visitas merece atenção. Se você gerar um relatório de um mês, pode querer filtrar para incluir mais visitas.

## Taxa de rejeição filtrada com percentual

Esse filtro mostra a taxa de rejeição para os primeiros 30% das páginas, quando classificadas por visitas.

![Taxa de rejeição filtrada com percentil](assets/filtered-bounce-rate-with-percentile.png){zoomable="yes"}

## Taxa de rejeição ponderada

Suponha que você deseja classificar pela taxa de rejeição em geral, mas ainda quer exibir as páginas com mais visitas no topo da lista. Você pode criar uma Taxa de rejeição ponderada com a seguinte aparência:

![](assets/weighted-bounce-rate.png)
