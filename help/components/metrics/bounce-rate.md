---
title: Taxa de rejeição
description: A proporção de visitas com exatamente uma ocorrência pelo número de entradas.
feature: Metrics
exl-id: 2d4929df-3843-4ad2-abe6-5c01d3eac557
source-git-commit: 9185ef6c570dd2fb0e54ce89f9833001d3e71b60
workflow-type: tm+mt
source-wordcount: '154'
ht-degree: 50%

---

# Taxa de rejeição

A métrica &quot;Taxa de rejeição&quot; mostra a proporção de visitas que continham exatamente uma ocorrência em relação ao número de visitas nessa página. É possível utilizar essa métrica para entender quais itens de dimensão têm a maior taxa de rejeição, ou para ver a taxa de rejeição total do site coletada ao longo do tempo. As altas taxas de rejeição podem esclarecer problemas com seu site ou aplicativo, como: design insatisfatório, tempos de carregamento lentos, conteúdo irrelevante ou uma incompatibilidade entre a intenção do visitante e o conteúdo da página.

Aqui está um exemplo: digamos que a página inicial de um site receba 500 visitantes em um mês. No entanto, 250 desses visitantes saem do site após visualizar a página inicial e não prosseguem para nenhuma outra página. Como resultado, a taxa de rejeição da página inicial seria de 50%.

## Como essa métrica é calculada

Essa métrica é calculada usando a fórmula [`Bounces`](bounces.md) `divided by` [`Entries`](entries.md).
