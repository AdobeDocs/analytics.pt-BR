---
title: Carrinhos
description: O número de ocorrências em que um visitante adicionou seu primeiro produto ao carrinho.
feature: Metrics
exl-id: 890bbaba-0140-4995-bbd2-c69aedc801e5
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '162'
ht-degree: 45%

---

# Carrinhos

A [métrica](overview.md) de &quot;Carrinhos&quot; mostra o número de ocorrências em que um visitante adicionou seu primeiro produto ao carrinho.

## Como essa métrica é calculada

Essa métrica conta o número de ocorrências em que `scOpen` existe na variável [`events`](/help/implement/vars/page-vars/events/events-overview.md).

## Diferença entre &quot;Carrinhos&quot;, &quot;Visualizações do carrinho&quot; e &quot;Adições ao carrinho&quot;

Como as métricas &quot;Carrinhos&quot;, &quot;Visualizações de carrinho&quot; e &quot;Adições ao carrinho&quot; são eventos que exigem implementação, sua organização decide a diferença exata entre essas métricas. No entanto, o Adobe projetou essas métricas para a seguinte lógica:

* A métrica “Carrinhos” é acionada apenas uma vez por compra quando um visitante adiciona seu primeiro produto ao carrinho de compras.
* A métrica &quot;Visualizações do carrinho&quot; é acionada sempre que um visitante exibe seu carrinho de compras.
* A métrica “Adições ao carrinho” é acionada para cada produto adicionado ao carrinho.

Quando um cliente adiciona seu primeiro produto a um carrinho de compras, o comportamento pretendido é que as métricas &quot;Carrinhos&quot; e &quot;Adições ao carrinho&quot; sejam acionadas. Mais uma vez, estas orientações não são concretas; a organização determina a lógica de implementação exata.
