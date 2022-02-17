---
title: Carrinhos
description: O número de ocorrências em que um visitante adicionou seu primeiro produto ao carrinho.
feature: Metrics
exl-id: 890bbaba-0140-4995-bbd2-c69aedc801e5
source-git-commit: 7d5383e1ee3bee189d3dd48bc6b899f4108f7ba8
workflow-type: tm+mt
source-wordcount: '135'
ht-degree: 100%

---

# Carrinhos

A métrica &quot;Carrinhos&quot; mostra o número de hits em que um visitante adicionou o primeiro produto ao carrinho.

## Como essa métrica é calculada

Essa métrica conta o número de ocorrências em que `scOpen` existe na variável [`events`](/help/implement/vars/page-vars/events/events-overview.md).

## Diferença entre &quot;Carrinhos&quot; e &quot;Visualizações do carrinho&quot;

Como as métricas &quot;Carrinhos&quot; e &quot;Visualizações de carrinho&quot; são eventos que exigem implementação, a própria organização decide a diferença exata entre essas duas métricas. No entanto, a Adobe projetou essas métricas para o seguinte:

* A métrica “Carrinhos” é acionada apenas uma vez por compra quando um visitante adiciona seu primeiro produto ao carrinho de compras.
* A métrica “Adições ao carrinho” é acionada para cada produto adicionado ao carrinho.

Para o primeiro produto, são acionadas as métricas &quot;Carrinhos&quot; e &quot;Adições ao carrinho&quot;. Mais uma vez, estas orientações não são concretas; a organização determina a lógica de implementação exata.
